# Changelog
All notable changes to the "ddlparse" module will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).


## [1.9.0winkelband] - 2020-12-26
### Added
- Add supports PostgreSQL and PostGIS data-type
  - `LTREE`
  - `GEOMETRY`
  - `RASTER`
- Add supports SQL Object Type
  - `External Table`


## [1.9.0] - 2020-11-04
### Added
- Add supports Cloud Spanner data-type.
  - `STRING`
  - `BYTES`

- Add supports MySQL data-type.
  - `BINARY`
  - `VARBINARY`

- Add supports PostgreSQL data-type.
  - `BYTEA`


## [1.8.0] - 2020-08-22
### Added
- Add `DdlParseColumn.character_set` property.
- Add supports for parsing MySQL FOREIGN KEY options MATCH, ON DELETE and ON UPDATE


## [1.7.0] - 2020-08-13
### Added
- Add `DdlParseColumn.default` property.
- Add `DdlParseColumn.auto_increment` property.
- Add `DdlParseColumn.encode` property.
- Add `DdlParseColumn.distkey` property.
- Add `DdlParseColumn.sortkey` property.

### Fixed
- Fix parse of column name with space character.


## [1.6.1] - 2020-08-08
### Fixed
- Fix parse Redshift `ENCODE` attribute.


## [1.6.0] - 2020-07-18
### Added
- Add property.
  - `DdlParseColumn.is_unsigned`
  - `DdlParseColumn.is_zerofill`
- Add supports for numeric type attributes of MySQL.
  - `UNSIGNED`
  - `ZEROFILL`
- Add supports MySQL data-type.
  - `TINYINT`
  - `SMALLINT`
  - `MEDIUMINT`
  - `DEC`
  - `FIXED`

### Fixed
- Miner fix.


## [1.5.0] - 2020-07-06
### Added
- Add supports for Python 3.8

### Removed
- End of support for Python 3.4

### Fixed
- Fix parse for column-constraint.
- Miner fix.


## [1.4.0] - 2019-12-08
### Added
- Add supports to BigQuery `NUMERIC` data type.

#### Data-type Conditions

|BigQuery Data Type|Source Data Type|Precision|Scale|Database|Exapmle Source Data Type|
|:--|:--|:-:|:-:|:--|:--|
|**INT64**|(NUMERIC\|NUMBER\|DECIMAL)|< 19|= 0|-|NUMERIC(18)|
|**FLOAT64**|(NUMERIC\|NUMBER\|DECIMAL)|< 19|> 0|-|NUMERIC(18, 1)|
|**NUMERIC**|(NUMERIC\|NUMBER\|DECIMAL)|>= 19|-|-|NUMERIC(19)|
|**NUMERIC**|(NUMERIC\|NUMBER\|DECIMAL)|\*|-|-|NUMBER(\*, 0)|
|**INT64**|(NUMERIC\|NUMBER\|DECIMAL)|None|-|default|DECIMAL|
|**NUMERIC**|(NUMERIC\|NUMBER\|DECIMAL)|None|-|`DdlParse.DATABASE.oracle`<br>`DdlParse.DATABASE.postgresql`|NUMBER<br>NUMERIC|

### Fixed
- Fix parsing failure for include `(*)` format of Oracle `NUMBER` data type.


## [1.3.1] - 2019-12-05
### Fixed
- Fixed parsing failure for columns include dot at default values.


## [1.3.0] - 2019-06-15
### Added
- Add supports the parse of `COMMENT` statements.
- Add `DdlParseColumn.comment` property.
- Add `DdlParseColumn.description` property for the `DdlParseColumn.comment` property alias.
- Add supports column comments in BigQuery DDL.


## [1.2.3] - 2019-02-17
### Fixed
- Fix parse error for MySQL DDL with 'FOREIGN KEY'.
- Fix not completely parsed with block comments.


## [1.2.2] - 2019-02-02
### Added
- Add supports PostgreSQL data type.
    - `UUID`

### Fixed
- Fix FutureWarning of Python 3.7.
- Fix parse `DEFAULT` value.
    - Add parse regex of `DEFAULT` value.


## [1.2.1] - 2019-01-27
### Added
- Add supports for Python 3.7.
    - Pass Python 3.7 test.
- Add supports PostgreSQL data type.
    - `CHARACTER VARYING`
    - `JSON`
    - Array type

### Fixed
- Fix parse `DEFAULT` value.
    - Add decimal point to `DEFAULT` parse character.


## [1.2.0] - 2019-01-02
### Added
- Add `DdlParseTable.to_bigquery_ddl` function.
    - BigQuery DDL (CREATE TABLE) statement generate function.
- Add `DdlParseColumn.bigquery_legacy_data_type` property.
    - Get BigQuery Legacy SQL data property.
    - Alias of `DdlParseColumn.bigquery_data_type` property.
- Add `DdlParseColumn.bigquery_standard_data_type` property.
    - Get BigQuery Standard SQL data property.


## [1.1.3] - 2018-08-02
### Added
- Add support inline comment.
- Add support constraint name with quotes.
- Add support Oracle Length Semantics for Character Datatypes.


## [1.1.2] - 2018-03-25
### Added
- Add support Oracle data type.
    - `CLOB`, `NCLOB`
    - `NUMBER` with no length & scale specification

### Fixed
- Miner fix.


## [1.1.1] - 2018-03-25
### Fixed
- Fix Postgres/Redshift parse of "::" syntax in field attribute.


## [1.1.0] - 2018-01-14
### Added
- Add `source_database` option.
- Add `to_bigquery_fields` method to Columns dicttionary(`DdlParseColumnDict` class).

### Fixed
- Fix BigQuery convert of Oracle data type.
    - Oracle 'DATE' -> BigQuery 'DATETIME'
    - Oracle 'NUMBER' -> BigQuery 'INTEGER' or 'FLOAT'


## [1.0.2] - 2018-01-09
### Fixed
- Miner enhancement.
    - `ddlparse.py` : Exclude unused module.
    - `example.py` : Modified comment.
    - `README.md` : Miner fix.


## [1.0.1] - 2018-01-07
### Fixed
- Miner enhancement.


## [1.0.0]
### Added
- Initial released.


[1.9.0]: https://github.com/shinichi-takii/ddlparse/compare/v1.8.0...v1.9.0
[1.8.0]: https://github.com/shinichi-takii/ddlparse/compare/v1.7.0...v1.8.0
[1.7.0]: https://github.com/shinichi-takii/ddlparse/compare/v1.6.1...v1.7.0
[1.6.1]: https://github.com/shinichi-takii/ddlparse/compare/v1.6.0...v1.6.1
[1.6.0]: https://github.com/shinichi-takii/ddlparse/compare/v1.5.0...v1.6.0
[1.5.0]: https://github.com/shinichi-takii/ddlparse/compare/v1.4.0...v1.5.0
[1.4.0]: https://github.com/shinichi-takii/ddlparse/compare/v1.3.1...v1.4.0
[1.3.1]: https://github.com/shinichi-takii/ddlparse/compare/v1.3.0...v1.3.1
[1.3.0]: https://github.com/shinichi-takii/ddlparse/compare/v1.2.3...v1.3.0
[1.2.3]: https://github.com/shinichi-takii/ddlparse/compare/v1.2.2...v1.2.3
[1.2.2]: https://github.com/shinichi-takii/ddlparse/compare/v1.2.1...v1.2.2
[1.2.1]: https://github.com/shinichi-takii/ddlparse/compare/v1.2.0...v1.2.1
[1.2.0]: https://github.com/shinichi-takii/ddlparse/compare/v1.1.3...v1.2.0
[1.1.3]: https://github.com/shinichi-takii/ddlparse/compare/v1.1.2...v1.1.3
[1.1.2]: https://github.com/shinichi-takii/ddlparse/compare/v1.1.1...v1.1.2
[1.1.1]: https://github.com/shinichi-takii/ddlparse/compare/v1.1.0...v1.1.1
[1.1.0]: https://github.com/shinichi-takii/ddlparse/compare/1.0.2...v1.1.0
[1.0.2]: https://github.com/shinichi-takii/ddlparse/compare/1.0.1...1.0.2
[1.0.1]: https://github.com/shinichi-takii/ddlparse/compare/1.0.0...1.0.1
[1.0.0]: https://github.com/shinichi-takii/ddlparse/releases/tag/1.0.0
