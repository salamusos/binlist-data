require 'csv'

task default: %w[test]

task :test do
  csv = CSV.read("iin-user-contributions.csv", { headers: true, header_converters: :symbol, converters: :all})
  iins = csv.map { |r| r[:iin] }
  if iins.sort_by(&:to_s) == iins then
    puts 'Sorted correctly'
  else
    puts 'Not sorted correctly'
    exit(1)
  end
end
