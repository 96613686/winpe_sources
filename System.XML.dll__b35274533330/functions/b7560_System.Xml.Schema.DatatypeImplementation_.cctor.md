# System.Xml.Schema.DatatypeImplementation::.cctor

- ea: `0xb7560`
- end: `0xb7ff2`
- name: `System.Xml.Schema.DatatypeImplementation::.cctor`
- size: `2706`
- prototype: ``
- caller_count: `0`
- callee_count: `73`
- tags: `registry_config, broker_com_uri`

## callees

- `0x132e0`
- `0xb81a0`
- `0xb85f0`
- `0xb9350`
- `0xb93c0`
- `0xb9410`
- `0xb94c0`
- `0xb9590`
- `0xb9690`
- `0xb9790`
- `0xb9890`
- `0xb99d0`
- `0xb9a90`
- `0xb9b30`
- `0xb9ce0`
- `0xb9d00`
- `0xb9d20`
- `0xb9d40`
- `0xb9d60`
- `0xb9d90`
- `0xb9dc0`
- `0xb9df0`
- `0xb9e20`
- `0xb9e50`
- `0xb9e80`
- `0xb9eb0`
- `0xb9fb0`
- `0xba0d0`
- `0xba200`
- `0xba330`
- `0xba3a0`
- `0xba3e0`
- `0xba420`
- `0xba450`
- `0xba480`
- `0xba4c0`
- `0xba4f0`
- `0xba560`
- `0xba5a0`
- `0xba5e0`
- `0xba620`
- `0xba7b0`
- `0xba840`
- `0xba890`
- `0xba8f0`
- `0xba9d0`
- `0xbaad0`
- `0xbabc0`
- `0xbacb0`
- `0xbad40`

## string_xrefs

- `0xb757b`: `http://www.w3.org/2001/XMLSchema`
- `0xb758f`: `http://www.w3.org/2001/XMLSchema`
- `0xb7d35`: `anyURI`
- `0xb7f81`: `token`
- `0xb7cba`: `NMTOKEN`
- `0xb7cce`: `NMTOKENS`
- `0xb7b1c`: `nmtoken`
- `0xb7b2f`: `nmtokens`

## pseudocode

```c

```

## disassembly

```asm
0xb7560  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xb7565  stsfld   class [mscorlib]System.Collections.Hashtable System.Xml.Schema.DatatypeImplementation::builtinTypes
0xb756a  ldc.i4.s 0x37
0xb756c  newarr   System.Xml.Schema.XmlSchemaSimpleType
0xb7571  stsfld   class System.Xml.Schema.XmlSchemaSimpleType[] System.Xml.Schema.DatatypeImplementation::enumToTypeCode
0xb7576  ldstr    aAnysimpletype// "anySimpleType"
0xb757b  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xb7580  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xb7585  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.DatatypeImplementation::QnAnySimpleType
0xb758a  ldstr    aAnytype// "anyType"
0xb758f  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xb7594  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xb7599  stsfld   class System.Xml.XmlQualifiedName System.Xml.Schema.DatatypeImplementation::QnAnyType
0xb759e  newobj   instance void System.Xml.Schema.StringFacetsChecker::.ctor()
0xb75a3  stsfld   class System.Xml.Schema.FacetsChecker System.Xml.Schema.DatatypeImplementation::stringFacetsChecker
0xb75a8  newobj   instance void System.Xml.Schema.MiscFacetsChecker::.ctor()
0xb75ad  stsfld   class System.Xml.Schema.FacetsChecker System.Xml.Schema.DatatypeImplementation::miscFacetsChecker
0xb75b2  newobj   instance void System.Xml.Schema.Numeric2FacetsChecker::.ctor()
0xb75b7  stsfld   class System.Xml.Schema.FacetsChecker System.Xml.Schema.DatatypeImplementation::numeric2FacetsChecker
0xb75bc  newobj   instance void System.Xml.Schema.BinaryFacetsChecker::.ctor()
0xb75c1  stsfld   class System.Xml.Schema.FacetsChecker System.Xml.Schema.DatatypeImplementation::binaryFacetsChecker
0xb75c6  newobj   instance void System.Xml.Schema.DateTimeFacetsChecker::.ctor()
0xb75cb  stsfld   class System.Xml.Schema.FacetsChecker System.Xml.Schema.DatatypeImplementation::dateTimeFacetsChecker
0xb75d0  newobj   instance void System.Xml.Schema.DurationFacetsChecker::.ctor()
0xb75d5  stsfld   class System.Xml.Schema.FacetsChecker System.Xml.Schema.DatatypeImplementation::durationFacetsChecker
0xb75da  newobj   instance void System.Xml.Schema.ListFacetsChecker::.ctor()
0xb75df  stsfld   class System.Xml.Schema.FacetsChecker System.Xml.Schema.DatatypeImplementation::listFacetsChecker
0xb75e4  newobj   instance void System.Xml.Schema.QNameFacetsChecker::.ctor()
0xb75e9  stsfld   class System.Xml.Schema.FacetsChecker System.Xml.Schema.DatatypeImplementation::qnameFacetsChecker
0xb75ee  newobj   instance void System.Xml.Schema.UnionFacetsChecker::.ctor()
0xb75f3  stsfld   class System.Xml.Schema.FacetsChecker System.Xml.Schema.DatatypeImplementation::unionFacetsChecker
0xb75f8  newobj   instance void System.Xml.Schema.Datatype_anySimpleType::.ctor()
0xb75fd  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_anySimpleType
0xb7602  newobj   instance void System.Xml.Schema.Datatype_anyURI::.ctor()
0xb7607  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_anyURI
0xb760c  newobj   instance void System.Xml.Schema.Datatype_base64Binary::.ctor()
0xb7611  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_base64Binary
0xb7616  newobj   instance void System.Xml.Schema.Datatype_boolean::.ctor()
0xb761b  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_boolean
0xb7620  newobj   instance void System.Xml.Schema.Datatype_byte::.ctor()
0xb7625  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_byte
0xb762a  newobj   instance void System.Xml.Schema.Datatype_char::.ctor()
0xb762f  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_char
0xb7634  newobj   instance void System.Xml.Schema.Datatype_date::.ctor()
0xb7639  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_date
0xb763e  newobj   instance void System.Xml.Schema.Datatype_dateTime::.ctor()
0xb7643  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_dateTime
0xb7648  newobj   instance void System.Xml.Schema.Datatype_dateTimeNoTimeZone::.ctor()
0xb764d  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_dateTimeNoTz
0xb7652  newobj   instance void System.Xml.Schema.Datatype_dateTimeTimeZone::.ctor()
0xb7657  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_dateTimeTz
0xb765c  newobj   instance void System.Xml.Schema.Datatype_day::.ctor()
0xb7661  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_day
0xb7666  newobj   instance void System.Xml.Schema.Datatype_decimal::.ctor()
0xb766b  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_decimal
0xb7670  newobj   instance void System.Xml.Schema.Datatype_double::.ctor()
0xb7675  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_double
0xb767a  newobj   instance void System.Xml.Schema.Datatype_doubleXdr::.ctor()
0xb767f  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_doubleXdr
0xb7684  newobj   instance void System.Xml.Schema.Datatype_duration::.ctor()
0xb7689  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_duration
0xb768e  newobj   instance void System.Xml.Schema.Datatype_ENTITY::.ctor()
0xb7693  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_ENTITY
0xb7698  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_ENTITY
0xb769d  ldc.i4.1
0xb769e  ldnull
0xb769f  callvirt instance class System.Xml.Schema.XmlSchemaDatatype System.Xml.Schema.DatatypeImplementation::DeriveByList(int32 minSize, class System.Xml.Schema.XmlSchemaType schemaType)
0xb76a4  castclass System.Xml.Schema.DatatypeImplementation
0xb76a9  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_ENTITIES
0xb76ae  newobj   instance void System.Xml.Schema.Datatype_ENUMERATION::.ctor()
0xb76b3  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_ENUMERATION
0xb76b8  newobj   instance void System.Xml.Schema.Datatype_fixed::.ctor()
0xb76bd  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_fixed
0xb76c2  newobj   instance void System.Xml.Schema.Datatype_float::.ctor()
0xb76c7  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_float
0xb76cc  newobj   instance void System.Xml.Schema.Datatype_floatXdr::.ctor()
0xb76d1  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_floatXdr
0xb76d6  newobj   instance void System.Xml.Schema.Datatype_hexBinary::.ctor()
0xb76db  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_hexBinary
0xb76e0  newobj   instance void System.Xml.Schema.Datatype_ID::.ctor()
0xb76e5  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_ID
0xb76ea  newobj   instance void System.Xml.Schema.Datatype_IDREF::.ctor()
0xb76ef  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_IDREF
0xb76f4  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_IDREF
0xb76f9  ldc.i4.1
0xb76fa  ldnull
0xb76fb  callvirt instance class System.Xml.Schema.XmlSchemaDatatype System.Xml.Schema.DatatypeImplementation::DeriveByList(int32 minSize, class System.Xml.Schema.XmlSchemaType schemaType)
0xb7700  castclass System.Xml.Schema.DatatypeImplementation
0xb7705  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_IDREFS
0xb770a  newobj   instance void System.Xml.Schema.Datatype_int::.ctor()
0xb770f  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_int
0xb7714  newobj   instance void System.Xml.Schema.Datatype_integer::.ctor()
0xb7719  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_integer
0xb771e  newobj   instance void System.Xml.Schema.Datatype_language::.ctor()
0xb7723  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_language
0xb7728  newobj   instance void System.Xml.Schema.Datatype_long::.ctor()
0xb772d  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_long
0xb7732  newobj   instance void System.Xml.Schema.Datatype_month::.ctor()
0xb7737  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_month
0xb773c  newobj   instance void System.Xml.Schema.Datatype_monthDay::.ctor()
0xb7741  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_monthDay
0xb7746  newobj   instance void System.Xml.Schema.Datatype_Name::.ctor()
0xb774b  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_Name
0xb7750  newobj   instance void System.Xml.Schema.Datatype_NCName::.ctor()
0xb7755  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_NCName
0xb775a  newobj   instance void System.Xml.Schema.Datatype_negativeInteger::.ctor()
0xb775f  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_negativeInteger
0xb7764  newobj   instance void System.Xml.Schema.Datatype_NMTOKEN::.ctor()
0xb7769  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_NMTOKEN
0xb776e  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_NMTOKEN
0xb7773  ldc.i4.1
0xb7774  ldnull
0xb7775  callvirt instance class System.Xml.Schema.XmlSchemaDatatype System.Xml.Schema.DatatypeImplementation::DeriveByList(int32 minSize, class System.Xml.Schema.XmlSchemaType schemaType)
0xb777a  castclass System.Xml.Schema.DatatypeImplementation
0xb777f  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_NMTOKENS
0xb7784  newobj   instance void System.Xml.Schema.Datatype_nonNegativeInteger::.ctor()
0xb7789  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_nonNegativeInteger
0xb778e  newobj   instance void System.Xml.Schema.Datatype_nonPositiveInteger::.ctor()
0xb7793  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_nonPositiveInteger
0xb7798  newobj   instance void System.Xml.Schema.Datatype_normalizedString::.ctor()
0xb779d  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_normalizedString
0xb77a2  newobj   instance void System.Xml.Schema.Datatype_NOTATION::.ctor()
0xb77a7  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_NOTATION
0xb77ac  newobj   instance void System.Xml.Schema.Datatype_positiveInteger::.ctor()
0xb77b1  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_positiveInteger
0xb77b6  newobj   instance void System.Xml.Schema.Datatype_QName::.ctor()
0xb77bb  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_QName
0xb77c0  newobj   instance void System.Xml.Schema.Datatype_QNameXdr::.ctor()
0xb77c5  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_QNameXdr
0xb77ca  newobj   instance void System.Xml.Schema.Datatype_short::.ctor()
0xb77cf  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_short
0xb77d4  newobj   instance void System.Xml.Schema.Datatype_string::.ctor()
0xb77d9  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_string
0xb77de  newobj   instance void System.Xml.Schema.Datatype_time::.ctor()
0xb77e3  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_time
0xb77e8  newobj   instance void System.Xml.Schema.Datatype_timeNoTimeZone::.ctor()
0xb77ed  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_timeNoTz
0xb77f2  newobj   instance void System.Xml.Schema.Datatype_timeTimeZone::.ctor()
0xb77f7  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_timeTz
0xb77fc  newobj   instance void System.Xml.Schema.Datatype_token::.ctor()
0xb7801  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_token
0xb7806  newobj   instance void System.Xml.Schema.Datatype_unsignedByte::.ctor()
0xb780b  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_unsignedByte
0xb7810  newobj   instance void System.Xml.Schema.Datatype_unsignedInt::.ctor()
0xb7815  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_unsignedInt
0xb781a  newobj   instance void System.Xml.Schema.Datatype_unsignedLong::.ctor()
0xb781f  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_unsignedLong
0xb7824  newobj   instance void System.Xml.Schema.Datatype_unsignedShort::.ctor()
0xb7829  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_unsignedShort
0xb782e  newobj   instance void System.Xml.Schema.Datatype_uuid::.ctor()
0xb7833  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_uuid
0xb7838  newobj   instance void System.Xml.Schema.Datatype_year::.ctor()
0xb783d  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_year
0xb7842  newobj   instance void System.Xml.Schema.Datatype_yearMonth::.ctor()
0xb7847  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_yearMonth
0xb784c  newobj   instance void System.Xml.Schema.Datatype_normalizedStringV1Compat::.ctor()
0xb7851  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_normalizedStringV1Compat
0xb7856  newobj   instance void System.Xml.Schema.Datatype_tokenV1Compat::.ctor()
0xb785b  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_tokenV1Compat
0xb7860  newobj   instance void System.Xml.Schema.Datatype_anyAtomicType::.ctor()
0xb7865  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_anyAtomicType
0xb786a  newobj   instance void System.Xml.Schema.Datatype_dayTimeDuration::.ctor()
0xb786f  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_dayTimeDuration
0xb7874  newobj   instance void System.Xml.Schema.Datatype_untypedAtomicType::.ctor()
0xb7879  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_untypedAtomicType
0xb787e  newobj   instance void System.Xml.Schema.Datatype_yearMonthDuration::.ctor()
0xb7883  stsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_yearMonthDuration
0xb7888  ldc.i4.s 0xD
0xb788a  newarr   System.Xml.Schema.DatatypeImplementation
0xb788f  dup
0xb7890  ldc.i4.0
0xb7891  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_string
0xb7896  stelem.ref
0xb7897  dup
0xb7898  ldc.i4.1
0xb7899  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_ID
0xb789e  stelem.ref
0xb789f  dup
0xb78a0  ldc.i4.2
0xb78a1  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_IDREF
0xb78a6  stelem.ref
0xb78a7  dup
0xb78a8  ldc.i4.3
0xb78a9  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_IDREFS
0xb78ae  stelem.ref
0xb78af  dup
0xb78b0  ldc.i4.4
0xb78b1  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_ENTITY
0xb78b6  stelem.ref
0xb78b7  dup
0xb78b8  ldc.i4.5
0xb78b9  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_ENTITIES
0xb78be  stelem.ref
0xb78bf  dup
0xb78c0  ldc.i4.6
0xb78c1  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_NMTOKEN
0xb78c6  stelem.ref
0xb78c7  dup
0xb78c8  ldc.i4.7
0xb78c9  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_NMTOKENS
0xb78ce  stelem.ref
0xb78cf  dup
0xb78d0  ldc.i4.8
0xb78d1  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_NOTATION
0xb78d6  stelem.ref
0xb78d7  dup
0xb78d8  ldc.i4.s 9
0xb78da  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_ENUMERATION
0xb78df  stelem.ref
0xb78e0  dup
0xb78e1  ldc.i4.s 0xA
0xb78e3  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_QNameXdr
0xb78e8  stelem.ref
0xb78e9  dup
0xb78ea  ldc.i4.s 0xB
0xb78ec  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_NCName
0xb78f1  stelem.ref
0xb78f2  stsfld   class System.Xml.Schema.DatatypeImplementation[] System.Xml.Schema.DatatypeImplementation::c_tokenizedTypes
0xb78f7  ldc.i4.s 0xD
0xb78f9  newarr   System.Xml.Schema.DatatypeImplementation
0xb78fe  dup
0xb78ff  ldc.i4.0
0xb7900  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_string
0xb7905  stelem.ref
0xb7906  dup
0xb7907  ldc.i4.1
0xb7908  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_ID
0xb790d  stelem.ref
0xb790e  dup
0xb790f  ldc.i4.2
0xb7910  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_IDREF
0xb7915  stelem.ref
0xb7916  dup
0xb7917  ldc.i4.3
0xb7918  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_IDREFS
0xb791d  stelem.ref
0xb791e  dup
0xb791f  ldc.i4.4
0xb7920  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_ENTITY
0xb7925  stelem.ref
0xb7926  dup
0xb7927  ldc.i4.5
0xb7928  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_ENTITIES
0xb792d  stelem.ref
0xb792e  dup
0xb792f  ldc.i4.6
0xb7930  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_NMTOKEN
0xb7935  stelem.ref
0xb7936  dup
0xb7937  ldc.i4.7
0xb7938  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_NMTOKENS
0xb793d  stelem.ref
0xb793e  dup
0xb793f  ldc.i4.8
0xb7940  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_NOTATION
0xb7945  stelem.ref
0xb7946  dup
0xb7947  ldc.i4.s 9
0xb7949  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_ENUMERATION
0xb794e  stelem.ref
0xb794f  dup
0xb7950  ldc.i4.s 0xA
0xb7952  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_QName
0xb7957  stelem.ref
0xb7958  dup
0xb7959  ldc.i4.s 0xB
0xb795b  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_NCName
0xb7960  stelem.ref
0xb7961  stsfld   class System.Xml.Schema.DatatypeImplementation[] System.Xml.Schema.DatatypeImplementation::c_tokenizedTypesXsd
0xb7966  ldc.i4.s 0x26
0xb7968  newarr   SchemaDatatypeMap
0xb796d  dup
0xb796e  ldc.i4.0
0xb796f  ldstr    aBinBase64// "bin.base64"
0xb7974  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_base64Binary
0xb7979  newobj   instance void SchemaDatatypeMap::.ctor(string name, class System.Xml.Schema.DatatypeImplementation type)
0xb797e  stelem.ref
0xb797f  dup
0xb7980  ldc.i4.1
0xb7981  ldstr    aBinHex// "bin.hex"
0xb7986  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_hexBinary
0xb798b  newobj   instance void SchemaDatatypeMap::.ctor(string name, class System.Xml.Schema.DatatypeImplementation type)
0xb7990  stelem.ref
0xb7991  dup
0xb7992  ldc.i4.2
0xb7993  ldstr    aBoolean// "boolean"
0xb7998  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_boolean
0xb799d  newobj   instance void SchemaDatatypeMap::.ctor(string name, class System.Xml.Schema.DatatypeImplementation type)
0xb79a2  stelem.ref
0xb79a3  dup
0xb79a4  ldc.i4.3
0xb79a5  ldstr    aChar_0// "char"
0xb79aa  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_char
0xb79af  newobj   instance void SchemaDatatypeMap::.ctor(string name, class System.Xml.Schema.DatatypeImplementation type)
0xb79b4  stelem.ref
0xb79b5  dup
0xb79b6  ldc.i4.4
0xb79b7  ldstr    aDate// "date"
0xb79bc  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_date
0xb79c1  newobj   instance void SchemaDatatypeMap::.ctor(string name, class System.Xml.Schema.DatatypeImplementation type)
  ... truncated ...
```
