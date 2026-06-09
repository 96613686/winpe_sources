# System.Xml.Schema.XmlSchemaInference::.cctor

- ea: `0xec470`
- end: `0xec6af`
- name: `System.Xml.Schema.XmlSchemaInference::.cctor`
- size: `575`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x132e0`

## string_xrefs

- `0xec475`: `http://www.w3.org/2001/XMLSchema`
- `0xec489`: `http://www.w3.org/2001/XMLSchema`
- `0xec49d`: `http://www.w3.org/2001/XMLSchema`
- `0xec4b1`: `http://www.w3.org/2001/XMLSchema`
- `0xec4c5`: `http://www.w3.org/2001/XMLSchema`
- `0xec4d9`: `http://www.w3.org/2001/XMLSchema`
- `0xec4ed`: `http://www.w3.org/2001/XMLSchema`
- `0xec501`: `http://www.w3.org/2001/XMLSchema`
- `0xec515`: `http://www.w3.org/2001/XMLSchema`
- `0xec529`: `http://www.w3.org/2001/XMLSchema`
- `0xec53d`: `http://www.w3.org/2001/XMLSchema`
- `0xec551`: `http://www.w3.org/2001/XMLSchema`
- `0xec565`: `http://www.w3.org/2001/XMLSchema`
- `0xec579`: `http://www.w3.org/2001/XMLSchema`
- `0xec58d`: `http://www.w3.org/2001/XMLSchema`
- `0xec5a1`: `http://www.w3.org/2001/XMLSchema`
- `0xec5b5`: `http://www.w3.org/2001/XMLSchema`
- `0xec5c9`: `http://www.w3.org/2001/XMLSchema`
- `0xec5dd`: `http://www.w3.org/2001/XMLSchema`
- `0xec5f1`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c

```

## disassembly

```asm
0xec470  ldstr    aBoolean// "boolean"
0xec475  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec47a  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec47f  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_boolean
0xec484  ldstr    aByte_0// "byte"
0xec489  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec48e  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec493  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_byte
0xec498  ldstr    aUnsignedbyte// "unsignedByte"
0xec49d  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec4a2  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec4a7  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_unsignedByte
0xec4ac  ldstr    aShort// "short"
0xec4b1  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec4b6  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec4bb  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_short
0xec4c0  ldstr    aUnsignedshort// "unsignedShort"
0xec4c5  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec4ca  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec4cf  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_unsignedShort
0xec4d4  ldstr    aInt_0// "int"
0xec4d9  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec4de  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec4e3  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_int
0xec4e8  ldstr    aUnsignedint// "unsignedInt"
0xec4ed  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec4f2  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec4f7  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_unsignedInt
0xec4fc  ldstr    aLong_0// "long"
0xec501  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec506  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec50b  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_long
0xec510  ldstr    aUnsignedlong// "unsignedLong"
0xec515  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec51a  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec51f  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_unsignedLong
0xec524  ldstr    aInteger_0// "integer"
0xec529  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec52e  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec533  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_integer
0xec538  ldstr    aDecimal_0// "decimal"
0xec53d  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec542  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec547  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_decimal
0xec54c  ldstr    aFloat_0// "float"
0xec551  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec556  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec55b  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_float
0xec560  ldstr    aDouble_0// "double"
0xec565  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec56a  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec56f  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_double
0xec574  ldstr    aDuration// "duration"
0xec579  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec57e  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec583  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_duration
0xec588  ldstr    aDatetime_0// "dateTime"
0xec58d  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec592  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec597  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_dateTime
0xec59c  ldstr    aTime// "time"
0xec5a1  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec5a6  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec5ab  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_time
0xec5b0  ldstr    aDate// "date"
0xec5b5  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec5ba  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec5bf  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_date
0xec5c4  ldstr    aGyearmonth// "gYearMonth"
0xec5c9  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec5ce  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec5d3  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_gYearMonth
0xec5d8  ldstr    aString// "string"
0xec5dd  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec5e2  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec5e7  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_string
0xec5ec  ldstr    aAnysimpletype// "anySimpleType"
0xec5f1  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xec5f6  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xec5fb  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_anySimpleType
0xec600  ldc.i4.s 0x13
0xec602  newarr   System.Xml.XmlQualifiedName
0xec607  dup
0xec608  ldc.i4.0
0xec609  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_boolean
0xec60e  stelem.ref
0xec60f  dup
0xec610  ldc.i4.1
0xec611  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_byte
0xec616  stelem.ref
0xec617  dup
0xec618  ldc.i4.2
0xec619  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_unsignedByte
0xec61e  stelem.ref
0xec61f  dup
0xec620  ldc.i4.3
0xec621  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_short
0xec626  stelem.ref
0xec627  dup
0xec628  ldc.i4.4
0xec629  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_unsignedShort
0xec62e  stelem.ref
0xec62f  dup
0xec630  ldc.i4.5
0xec631  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_int
0xec636  stelem.ref
0xec637  dup
0xec638  ldc.i4.6
0xec639  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_unsignedInt
0xec63e  stelem.ref
0xec63f  dup
0xec640  ldc.i4.7
0xec641  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_long
0xec646  stelem.ref
0xec647  dup
0xec648  ldc.i4.8
0xec649  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_unsignedLong
0xec64e  stelem.ref
0xec64f  dup
0xec650  ldc.i4.s 9
0xec652  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_integer
0xec657  stelem.ref
0xec658  dup
0xec659  ldc.i4.s 0xA
0xec65b  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_decimal
0xec660  stelem.ref
0xec661  dup
0xec662  ldc.i4.s 0xB
0xec664  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_float
0xec669  stelem.ref
0xec66a  dup
0xec66b  ldc.i4.s 0xC
0xec66d  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_double
0xec672  stelem.ref
0xec673  dup
0xec674  ldc.i4.s 0xD
0xec676  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_duration
0xec67b  stelem.ref
0xec67c  dup
0xec67d  ldc.i4.s 0xE
0xec67f  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_dateTime
0xec684  stelem.ref
0xec685  dup
0xec686  ldc.i4.s 0xF
0xec688  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_time
0xec68d  stelem.ref
0xec68e  dup
0xec68f  ldc.i4.s 0x10
0xec691  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_date
0xec696  stelem.ref
0xec697  dup
0xec698  ldc.i4.s 0x11
0xec69a  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_gYearMonth
0xec69f  stelem.ref
0xec6a0  dup
0xec6a1  ldc.i4.s 0x12
0xec6a3  ldsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaInference::ST_string
0xec6a8  stelem.ref
0xec6a9  stsfld   class System.Xml.XmlQualifiedName[] System.Xml.Schema.XmlSchemaInference::SimpleTypes
0xec6ae  ret
```
