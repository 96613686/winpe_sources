# System.Xml.Serialization.XmlSerializationReader::InitPrimitiveIDs

- ea: `0x88610`
- end: `0x88b93`
- name: `System.Xml.Serialization.XmlSerializationReader::InitPrimitiveIDs`
- size: `1411`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x88c00`
- `0x89540`
- `0x89ec0`

## callees

- `0xc240`
- `0x13200`
- `0x21cc0`
- `0x88610`

## string_xrefs

- `0x88624`: `http://www.w3.org/2001/XMLSchema`
- `0x8863a`: `http://microsoft.com/wsdl/types/`
- `0x888fb`: `anyURI`
- `0x88b83`: `token`
- `0x88aab`: `NMTOKEN`
- `0x88ac6`: `NMTOKENS`

## pseudocode

```c

```

## disassembly

```asm
0x88610  ldarg.0
0x88611  ldfld    string System.Xml.Serialization.XmlSerializationReader::tokenID
0x88616  brfalse.s loc_88619
0x88618  ret
0x88619  ldarg.0
0x8861a  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8861f  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88624  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x88629  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x8862e  stloc.0
0x8862f  ldarg.0
0x88630  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88635  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x8863a  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x8863f  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88644  stloc.1
0x88645  ldarg.0
0x88646  ldarg.0
0x88647  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8864c  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88651  ldstr    aString// "string"
0x88656  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x8865b  stfld    string System.Xml.Serialization.XmlSerializationReader::stringID
0x88660  ldarg.0
0x88661  ldarg.0
0x88662  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88667  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x8866c  ldstr    aInt_0// "int"
0x88671  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88676  stfld    string System.Xml.Serialization.XmlSerializationReader::intID
0x8867b  ldarg.0
0x8867c  ldarg.0
0x8867d  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88682  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88687  ldstr    aBoolean// "boolean"
0x8868c  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88691  stfld    string System.Xml.Serialization.XmlSerializationReader::booleanID
0x88696  ldarg.0
0x88697  ldarg.0
0x88698  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8869d  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x886a2  ldstr    aShort// "short"
0x886a7  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x886ac  stfld    string System.Xml.Serialization.XmlSerializationReader::shortID
0x886b1  ldarg.0
0x886b2  ldarg.0
0x886b3  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x886b8  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x886bd  ldstr    aLong_0// "long"
0x886c2  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x886c7  stfld    string System.Xml.Serialization.XmlSerializationReader::longID
0x886cc  ldarg.0
0x886cd  ldarg.0
0x886ce  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x886d3  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x886d8  ldstr    aFloat_0// "float"
0x886dd  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x886e2  stfld    string System.Xml.Serialization.XmlSerializationReader::floatID
0x886e7  ldarg.0
0x886e8  ldarg.0
0x886e9  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x886ee  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x886f3  ldstr    aDouble_0// "double"
0x886f8  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x886fd  stfld    string System.Xml.Serialization.XmlSerializationReader::doubleID
0x88702  ldarg.0
0x88703  ldarg.0
0x88704  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88709  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x8870e  ldstr    aDecimal_0// "decimal"
0x88713  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88718  stfld    string System.Xml.Serialization.XmlSerializationReader::decimalID
0x8871d  ldarg.0
0x8871e  ldarg.0
0x8871f  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88724  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88729  ldstr    aDatetime_0// "dateTime"
0x8872e  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88733  stfld    string System.Xml.Serialization.XmlSerializationReader::dateTimeID
0x88738  ldarg.0
0x88739  ldarg.0
0x8873a  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8873f  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88744  ldstr    aQname// "QName"
0x88749  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x8874e  stfld    string System.Xml.Serialization.XmlSerializationReader::qnameID
0x88753  ldarg.0
0x88754  ldarg.0
0x88755  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8875a  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x8875f  ldstr    aDate// "date"
0x88764  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88769  stfld    string System.Xml.Serialization.XmlSerializationReader::dateID
0x8876e  ldarg.0
0x8876f  ldarg.0
0x88770  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88775  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x8877a  ldstr    aTime// "time"
0x8877f  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88784  stfld    string System.Xml.Serialization.XmlSerializationReader::timeID
0x88789  ldarg.0
0x8878a  ldarg.0
0x8878b  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88790  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88795  ldstr    aHexbinary// "hexBinary"
0x8879a  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x8879f  stfld    string System.Xml.Serialization.XmlSerializationReader::hexBinaryID
0x887a4  ldarg.0
0x887a5  ldarg.0
0x887a6  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x887ab  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x887b0  ldstr    aBase64binary// "base64Binary"
0x887b5  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x887ba  stfld    string System.Xml.Serialization.XmlSerializationReader::base64BinaryID
0x887bf  ldarg.0
0x887c0  ldarg.0
0x887c1  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x887c6  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x887cb  ldstr    aUnsignedbyte// "unsignedByte"
0x887d0  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x887d5  stfld    string System.Xml.Serialization.XmlSerializationReader::unsignedByteID
0x887da  ldarg.0
0x887db  ldarg.0
0x887dc  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x887e1  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x887e6  ldstr    aByte_0// "byte"
0x887eb  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x887f0  stfld    string System.Xml.Serialization.XmlSerializationReader::byteID
0x887f5  ldarg.0
0x887f6  ldarg.0
0x887f7  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x887fc  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88801  ldstr    aUnsignedshort// "unsignedShort"
0x88806  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x8880b  stfld    string System.Xml.Serialization.XmlSerializationReader::unsignedShortID
0x88810  ldarg.0
0x88811  ldarg.0
0x88812  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88817  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x8881c  ldstr    aUnsignedint// "unsignedInt"
0x88821  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88826  stfld    string System.Xml.Serialization.XmlSerializationReader::unsignedIntID
0x8882b  ldarg.0
0x8882c  ldarg.0
0x8882d  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88832  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88837  ldstr    aUnsignedlong// "unsignedLong"
0x8883c  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88841  stfld    string System.Xml.Serialization.XmlSerializationReader::unsignedLongID
0x88846  ldarg.0
0x88847  ldarg.0
0x88848  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8884d  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88852  ldstr    aDecimal_0// "decimal"
0x88857  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x8885c  stfld    string System.Xml.Serialization.XmlSerializationReader::oldDecimalID
0x88861  ldarg.0
0x88862  ldarg.0
0x88863  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88868  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x8886d  ldstr    aTimeinstant// "timeInstant"
0x88872  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88877  stfld    string System.Xml.Serialization.XmlSerializationReader::oldTimeInstantID
0x8887c  ldarg.0
0x8887d  ldarg.0
0x8887e  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88883  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88888  ldstr    aChar_0// "char"
0x8888d  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88892  stfld    string System.Xml.Serialization.XmlSerializationReader::charID
0x88897  ldarg.0
0x88898  ldarg.0
0x88899  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8889e  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x888a3  ldstr    aGuid_0// "guid"
0x888a8  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x888ad  stfld    string System.Xml.Serialization.XmlSerializationReader::guidID
0x888b2  call     bool System.LocalAppContextSwitches::get_EnableTimeSpanSerialization()
0x888b7  brfalse.s loc_888D4
0x888b9  ldarg.0
0x888ba  ldarg.0
0x888bb  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x888c0  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x888c5  ldstr    aTimespan// "TimeSpan"
0x888ca  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x888cf  stfld    string System.Xml.Serialization.XmlSerializationReader::timeSpanID
0x888d4  ldarg.0
0x888d5  ldarg.0
0x888d6  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x888db  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x888e0  ldstr    aBase64_0// "base64"
0x888e5  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x888ea  stfld    string System.Xml.Serialization.XmlSerializationReader::base64ID
0x888ef  ldarg.0
0x888f0  ldarg.0
0x888f1  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x888f6  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x888fb  ldstr    aAnyuri// "anyURI"
0x88900  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88905  stfld    string System.Xml.Serialization.XmlSerializationReader::anyURIID
0x8890a  ldarg.0
0x8890b  ldarg.0
0x8890c  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88911  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88916  ldstr    aDuration// "duration"
0x8891b  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88920  stfld    string System.Xml.Serialization.XmlSerializationReader::durationID
0x88925  ldarg.0
0x88926  ldarg.0
0x88927  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8892c  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88931  ldstr    aEntity_1// "ENTITY"
0x88936  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x8893b  stfld    string System.Xml.Serialization.XmlSerializationReader::ENTITYID
0x88940  ldarg.0
0x88941  ldarg.0
0x88942  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88947  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x8894c  ldstr    aEntities// "ENTITIES"
0x88951  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88956  stfld    string System.Xml.Serialization.XmlSerializationReader::ENTITIESID
0x8895b  ldarg.0
0x8895c  ldarg.0
0x8895d  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88962  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88967  ldstr    aGday// "gDay"
0x8896c  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88971  stfld    string System.Xml.Serialization.XmlSerializationReader::gDayID
0x88976  ldarg.0
0x88977  ldarg.0
0x88978  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x8897d  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88982  ldstr    aGmonth// "gMonth"
0x88987  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x8898c  stfld    string System.Xml.Serialization.XmlSerializationReader::gMonthID
0x88991  ldarg.0
0x88992  ldarg.0
0x88993  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88998  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x8899d  ldstr    aGmonthday// "gMonthDay"
0x889a2  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x889a7  stfld    string System.Xml.Serialization.XmlSerializationReader::gMonthDayID
0x889ac  ldarg.0
0x889ad  ldarg.0
0x889ae  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x889b3  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x889b8  ldstr    aGyear// "gYear"
0x889bd  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x889c2  stfld    string System.Xml.Serialization.XmlSerializationReader::gYearID
0x889c7  ldarg.0
0x889c8  ldarg.0
0x889c9  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x889ce  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x889d3  ldstr    aGyearmonth// "gYearMonth"
0x889d8  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x889dd  stfld    string System.Xml.Serialization.XmlSerializationReader::gYearMonthID
0x889e2  ldarg.0
0x889e3  ldarg.0
0x889e4  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x889e9  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x889ee  ldstr    aId_0// "ID"
0x889f3  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x889f8  stfld    string System.Xml.Serialization.XmlSerializationReader::IDID
0x889fd  ldarg.0
0x889fe  ldarg.0
0x889ff  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88a04  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88a09  ldstr    aIdref// "IDREF"
0x88a0e  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88a13  stfld    string System.Xml.Serialization.XmlSerializationReader::IDREFID
0x88a18  ldarg.0
0x88a19  ldarg.0
0x88a1a  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88a1f  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88a24  ldstr    aIdrefs// "IDREFS"
0x88a29  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88a2e  stfld    string System.Xml.Serialization.XmlSerializationReader::IDREFSID
0x88a33  ldarg.0
0x88a34  ldarg.0
0x88a35  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88a3a  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88a3f  ldstr    aInteger_0// "integer"
0x88a44  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88a49  stfld    string System.Xml.Serialization.XmlSerializationReader::integerID
0x88a4e  ldarg.0
0x88a4f  ldarg.0
0x88a50  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88a55  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88a5a  ldstr    aLanguage// "language"
0x88a5f  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88a64  stfld    string System.Xml.Serialization.XmlSerializationReader::languageID
0x88a69  ldarg.0
0x88a6a  ldarg.0
0x88a6b  ldfld    class System.Xml.XmlReader System.Xml.Serialization.XmlSerializationReader::r
0x88a70  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReader::get_NameTable()
0x88a75  ldstr    aName_0// "Name"
0x88a7a  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x88a7f  stfld    string System.Xml.Serialization.XmlSerializationReader::NameID
0x88a84  ldarg.0
0x88a85  ldarg.0
  ... truncated ...
```
