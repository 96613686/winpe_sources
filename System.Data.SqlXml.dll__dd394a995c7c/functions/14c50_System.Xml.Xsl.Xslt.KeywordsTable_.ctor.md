# System.Xml.Xsl.Xslt.KeywordsTable::.ctor

- ea: `0x14c50`
- end: `0x15423`
- name: `System.Xml.Xsl.Xslt.KeywordsTable::.ctor`
- size: `2003`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0xa9f0`
- `0x21300`

## string_xrefs

- `0x14d2b`: `comment`
- `0x14c81`: `apply-templates`
- `0x153f1`: `xmlns`
- `0x15303`: `http://www.w3.org/XML/1998/namespace`
- `0x14cc5`: `call-template`
- `0x152f2`: `urn:schemas-microsoft-com:xslt`
- `0x14d4d`: `copy-of`
- `0x14e5d`: `extension-element-prefixes`
- `0x150d2`: `omit-xml-declaration`
- `0x1529d`: `template`
- `0x15402`: `xpath-default-namespace`

## pseudocode

```c

```

## disassembly

```asm
0x14c50  ldarg.0
0x14c51  call     instance void [mscorlib]System.Object::.ctor()
0x14c56  ldarg.0
0x14c57  ldarg.1
0x14c58  stfld    class [System.Xml]System.Xml.XmlNameTable System.Xml.Xsl.Xslt.KeywordsTable::NameTable
0x14c5d  ldarg.0
0x14c5e  ldarg.1
0x14c5f  ldstr    aAnalyzeString// "analyze-string"
0x14c64  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14c69  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::AnalyzeString
0x14c6e  ldarg.0
0x14c6f  ldarg.1
0x14c70  ldstr    aApplyImports// "apply-imports"
0x14c75  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14c7a  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::ApplyImports
0x14c7f  ldarg.0
0x14c80  ldarg.1
0x14c81  ldstr    aApplyTemplates// "apply-templates"
0x14c86  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14c8b  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::ApplyTemplates
0x14c90  ldarg.0
0x14c91  ldarg.1
0x14c92  ldstr    aAssembly// "assembly"
0x14c97  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14c9c  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Assembly
0x14ca1  ldarg.0
0x14ca2  ldarg.1
0x14ca3  ldstr    aAttribute// "attribute"
0x14ca8  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14cad  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Attribute
0x14cb2  ldarg.0
0x14cb3  ldarg.1
0x14cb4  ldstr    aAttributeSet// "attribute-set"
0x14cb9  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14cbe  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::AttributeSet
0x14cc3  ldarg.0
0x14cc4  ldarg.1
0x14cc5  ldstr    aCallTemplate// "call-template"
0x14cca  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14ccf  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::CallTemplate
0x14cd4  ldarg.0
0x14cd5  ldarg.1
0x14cd6  ldstr    aCaseOrder// "case-order"
0x14cdb  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14ce0  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::CaseOrder
0x14ce5  ldarg.0
0x14ce6  ldarg.1
0x14ce7  ldstr    aCdataSectionEl// "cdata-section-elements"
0x14cec  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14cf1  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::CDataSectionElements
0x14cf6  ldarg.0
0x14cf7  ldarg.1
0x14cf8  ldstr    aCharacter// "character"
0x14cfd  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14d02  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Character
0x14d07  ldarg.0
0x14d08  ldarg.1
0x14d09  ldstr    aCharacterMap// "character-map"
0x14d0e  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14d13  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::CharacterMap
0x14d18  ldarg.0
0x14d19  ldarg.1
0x14d1a  ldstr    aChoose// "choose"
0x14d1f  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14d24  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Choose
0x14d29  ldarg.0
0x14d2a  ldarg.1
0x14d2b  ldstr    aComment// "comment"
0x14d30  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14d35  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Comment
0x14d3a  ldarg.0
0x14d3b  ldarg.1
0x14d3c  ldstr    aCopy// "copy"
0x14d41  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14d46  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Copy
0x14d4b  ldarg.0
0x14d4c  ldarg.1
0x14d4d  ldstr    aCopyOf// "copy-of"
0x14d52  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14d57  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::CopyOf
0x14d5c  ldarg.0
0x14d5d  ldarg.1
0x14d5e  ldstr    aCount// "count"
0x14d63  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14d68  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Count
0x14d6d  ldarg.0
0x14d6e  ldarg.1
0x14d6f  ldstr    aDataType// "data-type"
0x14d74  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14d79  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::DataType
0x14d7e  ldarg.0
0x14d7f  ldarg.1
0x14d80  ldstr    aDecimalFormat// "decimal-format"
0x14d85  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14d8a  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::DecimalFormat
0x14d8f  ldarg.0
0x14d90  ldarg.1
0x14d91  ldstr    aDecimalSeparat// "decimal-separator"
0x14d96  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14d9b  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::DecimalSeparator
0x14da0  ldarg.0
0x14da1  ldarg.1
0x14da2  ldstr    aDefaultCollati// "default-collation"
0x14da7  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14dac  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::DefaultCollation
0x14db1  ldarg.0
0x14db2  ldarg.1
0x14db3  ldstr    aDefaultValidat// "default-validation"
0x14db8  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14dbd  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::DefaultValidation
0x14dc2  ldarg.0
0x14dc3  ldarg.1
0x14dc4  ldstr    aDigit// "digit"
0x14dc9  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14dce  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Digit
0x14dd3  ldarg.0
0x14dd4  ldarg.1
0x14dd5  ldstr    aDisableOutputE// "disable-output-escaping"
0x14dda  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14ddf  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::DisableOutputEscaping
0x14de4  ldarg.0
0x14de5  ldarg.1
0x14de6  ldstr    aDoctypePublic// "doctype-public"
0x14deb  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14df0  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::DocTypePublic
0x14df5  ldarg.0
0x14df6  ldarg.1
0x14df7  ldstr    aDoctypeSystem// "doctype-system"
0x14dfc  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14e01  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::DocTypeSystem
0x14e06  ldarg.0
0x14e07  ldarg.1
0x14e08  ldstr    aDocument// "document"
0x14e0d  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14e12  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Document
0x14e17  ldarg.0
0x14e18  ldarg.1
0x14e19  ldstr    aElement// "element"
0x14e1e  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14e23  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Element
0x14e28  ldarg.0
0x14e29  ldarg.1
0x14e2a  ldstr    aElements// "elements"
0x14e2f  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14e34  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Elements
0x14e39  ldarg.0
0x14e3a  ldarg.1
0x14e3b  ldstr    aEncoding_0// "encoding"
0x14e40  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14e45  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Encoding
0x14e4a  ldarg.0
0x14e4b  ldarg.1
0x14e4c  ldstr    aExcludeResultP// "exclude-result-prefixes"
0x14e51  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14e56  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::ExcludeResultPrefixes
0x14e5b  ldarg.0
0x14e5c  ldarg.1
0x14e5d  ldstr    aExtensionEleme// "extension-element-prefixes"
0x14e62  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14e67  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::ExtensionElementPrefixes
0x14e6c  ldarg.0
0x14e6d  ldarg.1
0x14e6e  ldstr    aFallback// "fallback"
0x14e73  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14e78  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Fallback
0x14e7d  ldarg.0
0x14e7e  ldarg.1
0x14e7f  ldstr    aForEach// "for-each"
0x14e84  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14e89  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::ForEach
0x14e8e  ldarg.0
0x14e8f  ldarg.1
0x14e90  ldstr    aForEachGroup// "for-each-group"
0x14e95  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14e9a  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::ForEachGroup
0x14e9f  ldarg.0
0x14ea0  ldarg.1
0x14ea1  ldstr    aFormat// "format"
0x14ea6  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14eab  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Format
0x14eb0  ldarg.0
0x14eb1  ldarg.1
0x14eb2  ldstr    aFrom// "from"
0x14eb7  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14ebc  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::From
0x14ec1  ldarg.0
0x14ec2  ldarg.1
0x14ec3  ldstr    aFunction// "function"
0x14ec8  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14ecd  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Function
0x14ed2  ldarg.0
0x14ed3  ldarg.1
0x14ed4  ldstr    aGroupingSepara// "grouping-separator"
0x14ed9  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14ede  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::GroupingSeparator
0x14ee3  ldarg.0
0x14ee4  ldarg.1
0x14ee5  ldstr    aGroupingSize// "grouping-size"
0x14eea  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14eef  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::GroupingSize
0x14ef4  ldarg.0
0x14ef5  ldarg.1
0x14ef6  ldstr    aHref// "href"
0x14efb  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14f00  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Href
0x14f05  ldarg.0
0x14f06  ldarg.1
0x14f07  ldstr    aId// "id"
0x14f0c  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14f11  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Id
0x14f16  ldarg.0
0x14f17  ldarg.1
0x14f18  ldstr    aIf// "if"
0x14f1d  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14f22  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::If
0x14f27  ldarg.0
0x14f28  ldarg.1
0x14f29  ldstr    aImplementsPref// "implements-prefix"
0x14f2e  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14f33  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::ImplementsPrefix
0x14f38  ldarg.0
0x14f39  ldarg.1
0x14f3a  ldstr    aImport// "import"
0x14f3f  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14f44  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Import
0x14f49  ldarg.0
0x14f4a  ldarg.1
0x14f4b  ldstr    aImportSchema// "import-schema"
0x14f50  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14f55  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::ImportSchema
0x14f5a  ldarg.0
0x14f5b  ldarg.1
0x14f5c  ldstr    aInclude// "include"
0x14f61  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14f66  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Include
0x14f6b  ldarg.0
0x14f6c  ldarg.1
0x14f6d  ldstr    aIndent// "indent"
0x14f72  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14f77  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Indent
0x14f7c  ldarg.0
0x14f7d  ldarg.1
0x14f7e  ldstr    aInfinity_1// "infinity"
0x14f83  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14f88  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Infinity
0x14f8d  ldarg.0
0x14f8e  ldarg.1
0x14f8f  ldstr    aKey// "key"
0x14f94  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14f99  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Key
0x14f9e  ldarg.0
0x14f9f  ldarg.1
0x14fa0  ldstr    aLang// "lang"
0x14fa5  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14faa  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Lang
0x14faf  ldarg.0
0x14fb0  ldarg.1
0x14fb1  ldstr    aLanguage// "language"
0x14fb6  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14fbb  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Language
0x14fc0  ldarg.0
0x14fc1  ldarg.1
0x14fc2  ldstr    aLetterValue// "letter-value"
0x14fc7  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14fcc  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::LetterValue
0x14fd1  ldarg.0
0x14fd2  ldarg.1
0x14fd3  ldstr    aLevel// "level"
0x14fd8  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14fdd  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Level
0x14fe2  ldarg.0
0x14fe3  ldarg.1
0x14fe4  ldstr    aMatch// "match"
0x14fe9  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14fee  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Match
0x14ff3  ldarg.0
0x14ff4  ldarg.1
0x14ff5  ldstr    aMatchingSubstr// "matching-substring"
0x14ffa  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x14fff  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::MatchingSubstring
0x15004  ldarg.0
0x15005  ldarg.1
0x15006  ldstr    aMediaType// "media-type"
0x1500b  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x15010  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::MediaType
0x15015  ldarg.0
0x15016  ldarg.1
0x15017  ldstr    aMessage// "message"
0x1501c  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x15021  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Message
0x15026  ldarg.0
0x15027  ldarg.1
0x15028  ldstr    aMethod// "method"
0x1502d  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x15032  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::Method
0x15037  ldarg.0
0x15038  ldarg.1
0x15039  ldstr    aMinusSign// "minus-sign"
0x1503e  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x15043  stfld    string System.Xml.Xsl.Xslt.KeywordsTable::MinusSign
  ... truncated ...
```
