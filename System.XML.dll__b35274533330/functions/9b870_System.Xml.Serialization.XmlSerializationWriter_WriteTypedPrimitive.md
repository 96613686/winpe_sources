# System.Xml.Serialization.XmlSerializationWriter::WriteTypedPrimitive

- ea: `0x9b870`
- end: `0x9bc29`
- name: `System.Xml.Serialization.XmlSerializationWriter::WriteTypedPrimitive`
- size: `953`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9d090`

## callees

- `0xc240`
- `0x10000`
- `0x10020`
- `0x10030`
- `0x10040`
- `0x10050`
- `0x10060`
- `0x10070`
- `0x10080`
- `0x10090`
- `0x100a0`
- `0x100b0`
- `0x100f0`
- `0x10130`
- `0x10220`
- `0x40780`
- `0x407b0`
- `0x407d0`
- `0x408d0`
- `0x40910`
- `0x51f40`
- `0x78a80`
- `0x9b5e0`
- `0x9b610`
- `0x9b680`
- `0x9b870`
- `0x9bca0`
- `0x9c470`

## string_xrefs

- `0x9b872`: `http://www.w3.org/2001/XMLSchema`
- `0x9bb32`: `http://www.w3.org/2001/XMLSchema`
- `0x9bbcf`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x9b9bd`: `http://microsoft.com/wsdl/types/`
- `0x9bad5`: `http://microsoft.com/wsdl/types/`

## pseudocode

```c

```

## disassembly

```asm
0x9b870  ldnull
0x9b871  stloc.0
0x9b872  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x9b877  stloc.2
0x9b878  ldc.i4.1
0x9b879  stloc.3
0x9b87a  ldc.i4.0
0x9b87b  stloc.s  4
0x9b87d  ldarg.3
0x9b87e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x9b883  stloc.s  5
0x9b885  ldc.i4.0
0x9b886  stloc.s  6
0x9b888  ldloc.s  5
0x9b88a  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x9b88f  stloc.s  7
0x9b891  ldloc.s  7
0x9b893  ldc.i4.3
0x9b894  sub
0x9b895  switch   loc_9B90A, loc_9B9AB, loc_9B9DF, loc_9B9C8, loc_9B921, loc_9B9F6, loc_9B8F3, loc_9BA0D, loc_9B938, loc_9BA24, loc_9B94F, loc_9B966, loc_9B97D, loc_9B994, loc_9BA3B, loc_9B8DF
0x9b8da  br       loc_9BA3B
0x9b8df  ldarg.3
0x9b8e0  castclass [mscorlib]System.String
0x9b8e5  stloc.0
0x9b8e6  ldstr    aString// "string"
0x9b8eb  stloc.1
0x9b8ec  ldc.i4.0
0x9b8ed  stloc.3
0x9b8ee  br       loc_9BB92
0x9b8f3  ldarg.3
0x9b8f4  unbox.any [mscorlib]System.Int32
0x9b8f9  call     string System.Xml.XmlConvert::ToString(int32 value)
0x9b8fe  stloc.0
0x9b8ff  ldstr    aInt_0// "int"
0x9b904  stloc.1
0x9b905  br       loc_9BB92
0x9b90a  ldarg.3
0x9b90b  unbox.any [mscorlib]System.Boolean
0x9b910  call     string System.Xml.XmlConvert::ToString(bool value)
0x9b915  stloc.0
0x9b916  ldstr    aBoolean// "boolean"
0x9b91b  stloc.1
0x9b91c  br       loc_9BB92
0x9b921  ldarg.3
0x9b922  unbox.any [mscorlib]System.Int16
0x9b927  call     string System.Xml.XmlConvert::ToString(int16 value)
0x9b92c  stloc.0
0x9b92d  ldstr    aShort// "short"
0x9b932  stloc.1
0x9b933  br       loc_9BB92
0x9b938  ldarg.3
0x9b939  unbox.any [mscorlib]System.Int64
0x9b93e  call     string System.Xml.XmlConvert::ToString(int64 value)
0x9b943  stloc.0
0x9b944  ldstr    aLong_0// "long"
0x9b949  stloc.1
0x9b94a  br       loc_9BB92
0x9b94f  ldarg.3
0x9b950  unbox.any [mscorlib]System.Single
0x9b955  call     string System.Xml.XmlConvert::ToString(float32 value)
0x9b95a  stloc.0
0x9b95b  ldstr    aFloat_0// "float"
0x9b960  stloc.1
0x9b961  br       loc_9BB92
0x9b966  ldarg.3
0x9b967  unbox.any [mscorlib]System.Double
0x9b96c  call     string System.Xml.XmlConvert::ToString(float64 value)
0x9b971  stloc.0
0x9b972  ldstr    aDouble_0// "double"
0x9b977  stloc.1
0x9b978  br       loc_9BB92
0x9b97d  ldarg.3
0x9b97e  unbox.any [mscorlib]System.Decimal
0x9b983  call     string System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Decimal value)
0x9b988  stloc.0
0x9b989  ldstr    aDecimal_0// "decimal"
0x9b98e  stloc.1
0x9b98f  br       loc_9BB92
0x9b994  ldarg.3
0x9b995  unbox.any [mscorlib]System.DateTime
0x9b99a  call     string System.Xml.Serialization.XmlSerializationWriter::FromDateTime(valuetype [mscorlib]System.DateTime value)
0x9b99f  stloc.0
0x9b9a0  ldstr    aDatetime_0// "dateTime"
0x9b9a5  stloc.1
0x9b9a6  br       loc_9BB92
0x9b9ab  ldarg.3
0x9b9ac  unbox.any [mscorlib]System.Char
0x9b9b1  call     string System.Xml.Serialization.XmlSerializationWriter::FromChar(char value)
0x9b9b6  stloc.0
0x9b9b7  ldstr    aChar_0// "char"
0x9b9bc  stloc.1
0x9b9bd  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x9b9c2  stloc.2
0x9b9c3  br       loc_9BB92
0x9b9c8  ldarg.3
0x9b9c9  unbox.any [mscorlib]System.Byte
0x9b9ce  call     string System.Xml.XmlConvert::ToString(unsigned int8 value)
0x9b9d3  stloc.0
0x9b9d4  ldstr    aUnsignedbyte// "unsignedByte"
0x9b9d9  stloc.1
0x9b9da  br       loc_9BB92
0x9b9df  ldarg.3
0x9b9e0  unbox.any [mscorlib]System.SByte
0x9b9e5  call     string System.Xml.XmlConvert::ToString(int8 value)
0x9b9ea  stloc.0
0x9b9eb  ldstr    aByte_0// "byte"
0x9b9f0  stloc.1
0x9b9f1  br       loc_9BB92
0x9b9f6  ldarg.3
0x9b9f7  unbox.any [mscorlib]System.UInt16
0x9b9fc  call     string System.Xml.XmlConvert::ToString(unsigned int16 value)
0x9ba01  stloc.0
0x9ba02  ldstr    aUnsignedshort// "unsignedShort"
0x9ba07  stloc.1
0x9ba08  br       loc_9BB92
0x9ba0d  ldarg.3
0x9ba0e  unbox.any [mscorlib]System.UInt32
0x9ba13  call     string System.Xml.XmlConvert::ToString(unsigned int32 value)
0x9ba18  stloc.0
0x9ba19  ldstr    aUnsignedint// "unsignedInt"
0x9ba1e  stloc.1
0x9ba1f  br       loc_9BB92
0x9ba24  ldarg.3
0x9ba25  unbox.any [mscorlib]System.UInt64
0x9ba2a  call     string System.Xml.XmlConvert::ToString(unsigned int64 value)
0x9ba2f  stloc.0
0x9ba30  ldstr    aUnsignedlong// "unsignedLong"
0x9ba35  stloc.1
0x9ba36  br       loc_9BB92
0x9ba3b  ldloc.s  5
0x9ba3d  ldtoken  System.Xml.XmlQualifiedName
0x9ba42  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9ba47  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9ba4c  brfalse.s loc_9BA89
0x9ba4e  ldstr    aQname// "QName"
0x9ba53  stloc.1
0x9ba54  ldc.i4.1
0x9ba55  stloc.s  6
0x9ba57  ldarg.1
0x9ba58  brtrue.s loc_9BA69
0x9ba5a  ldarg.0
0x9ba5b  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9ba60  ldloc.1
0x9ba61  ldloc.2
0x9ba62  callvirt instance void System.Xml.XmlWriter::WriteStartElement(string localName, string ns)
0x9ba67  br.s     loc_9BA76
0x9ba69  ldarg.0
0x9ba6a  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9ba6f  ldarg.1
0x9ba70  ldarg.2
0x9ba71  callvirt instance void System.Xml.XmlWriter::WriteStartElement(string localName, string ns)
0x9ba76  ldarg.0
0x9ba77  ldarg.3
0x9ba78  castclass System.Xml.XmlQualifiedName
0x9ba7d  ldc.i4.0
0x9ba7e  call     instance string System.Xml.Serialization.XmlSerializationWriter::FromXmlQualifiedName(class System.Xml.XmlQualifiedName xmlQualifiedName, bool ignoreEmpty)
0x9ba83  stloc.0
0x9ba84  br       loc_9BB92
0x9ba89  ldloc.s  5
0x9ba8b  ldtoken  unsigned int8[]
0x9ba90  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9ba95  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9ba9a  brfalse.s loc_9BAB0
0x9ba9c  ldsfld   string [mscorlib]System.String::Empty
0x9baa1  stloc.0
0x9baa2  ldc.i4.1
0x9baa3  stloc.s  4
0x9baa5  ldstr    aBase64binary// "base64Binary"
0x9baaa  stloc.1
0x9baab  br       loc_9BB92
0x9bab0  ldloc.s  5
0x9bab2  ldtoken  [mscorlib]System.Guid
0x9bab7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9babc  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9bac1  brfalse.s loc_9BAE0
0x9bac3  ldarg.3
0x9bac4  unbox.any [mscorlib]System.Guid
0x9bac9  call     string System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid value)
0x9bace  stloc.0
0x9bacf  ldstr    aGuid_0// "guid"
0x9bad4  stloc.1
0x9bad5  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x9bada  stloc.2
0x9badb  br       loc_9BB92
0x9bae0  ldloc.s  5
0x9bae2  ldtoken  [mscorlib]System.TimeSpan
0x9bae7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9baec  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9baf1  brfalse.s loc_9BB11
0x9baf3  call     bool System.LocalAppContextSwitches::get_EnableTimeSpanSerialization()
0x9baf8  brfalse.s loc_9BB11
0x9bafa  ldarg.3
0x9bafb  unbox.any [mscorlib]System.TimeSpan
0x9bb00  call     string System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.TimeSpan value)
0x9bb05  stloc.0
0x9bb06  ldstr    aTimespan// "TimeSpan"
0x9bb0b  stloc.1
0x9bb0c  br       loc_9BB92
0x9bb11  ldtoken  class System.Xml.XmlNode[]
0x9bb16  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9bb1b  ldloc.s  5
0x9bb1d  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x9bb22  brfalse.s loc_9BB89
0x9bb24  ldarg.1
0x9bb25  brtrue.s loc_9BB3E
0x9bb27  ldarg.0
0x9bb28  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9bb2d  ldstr    aAnytype// "anyType"
0x9bb32  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x9bb37  callvirt instance void System.Xml.XmlWriter::WriteStartElement(string localName, string ns)
0x9bb3c  br.s     loc_9BB4B
0x9bb3e  ldarg.0
0x9bb3f  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9bb44  ldarg.1
0x9bb45  ldarg.2
0x9bb46  callvirt instance void System.Xml.XmlWriter::WriteStartElement(string localName, string ns)
0x9bb4b  ldarg.3
0x9bb4c  castclass class System.Xml.XmlNode[]
0x9bb51  stloc.s  8
0x9bb53  ldc.i4.0
0x9bb54  stloc.s  9
0x9bb56  br.s     loc_9BB75
0x9bb58  ldloc.s  8
0x9bb5a  ldloc.s  9
0x9bb5c  ldelem.ref
0x9bb5d  brfalse.s loc_9BB6F
0x9bb5f  ldloc.s  8
0x9bb61  ldloc.s  9
0x9bb63  ldelem.ref
0x9bb64  ldarg.0
0x9bb65  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9bb6a  callvirt instance void System.Xml.XmlNode::WriteTo(class System.Xml.XmlWriter w)
0x9bb6f  ldloc.s  9
0x9bb71  ldc.i4.1
0x9bb72  add
0x9bb73  stloc.s  9
0x9bb75  ldloc.s  9
0x9bb77  ldloc.s  8
0x9bb79  ldlen
0x9bb7a  conv.i4
0x9bb7b  blt.s    loc_9BB58
0x9bb7d  ldarg.0
0x9bb7e  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9bb83  callvirt instance void System.Xml.XmlWriter::WriteEndElement()
0x9bb88  ret
0x9bb89  ldarg.0
0x9bb8a  ldloc.s  5
0x9bb8c  call     instance class [mscorlib]System.Exception System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(class [mscorlib]System.Type type)
0x9bb91  throw
0x9bb92  ldloc.s  6
0x9bb94  brtrue.s loc_9BBB5
0x9bb96  ldarg.1
0x9bb97  brtrue.s loc_9BBA8
0x9bb99  ldarg.0
0x9bb9a  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9bb9f  ldloc.1
0x9bba0  ldloc.2
0x9bba1  callvirt instance void System.Xml.XmlWriter::WriteStartElement(string localName, string ns)
0x9bba6  br.s     loc_9BBB5
0x9bba8  ldarg.0
0x9bba9  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9bbae  ldarg.1
0x9bbaf  ldarg.2
0x9bbb0  callvirt instance void System.Xml.XmlWriter::WriteStartElement(string localName, string ns)
0x9bbb5  ldarg.s  4
0x9bbb7  brfalse.s loc_9BBC1
0x9bbb9  ldarg.0
0x9bbba  ldloc.1
0x9bbbb  ldloc.2
0x9bbbc  call     instance void System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string name, string ns)
0x9bbc1  ldloc.0
0x9bbc2  brtrue.s loc_9BBE0
0x9bbc4  ldarg.0
0x9bbc5  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9bbca  ldstr    aNil// "nil"
0x9bbcf  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2001/XMLSchema-instan"...
0x9bbd4  ldstr    aTrue// "true"
0x9bbd9  callvirt instance void System.Xml.XmlWriter::WriteAttributeString(string localName, string ns, string value)
0x9bbde  br.s     loc_9BC1D
0x9bbe0  ldloc.s  4
0x9bbe2  brfalse.s loc_9BC00
0x9bbe4  ldarg.0
0x9bbe5  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9bbea  ldarg.3
0x9bbeb  castclass unsigned int8[]
0x9bbf0  ldc.i4.0
0x9bbf1  ldarg.3
0x9bbf2  castclass unsigned int8[]
0x9bbf7  ldlen
0x9bbf8  conv.i4
0x9bbf9  call     void System.Xml.Serialization.XmlCustomFormatter::WriteArrayBase64(class System.Xml.XmlWriter writer, unsigned int8[] inData, int32 start, int32 count)
0x9bbfe  br.s     loc_9BC1D
0x9bc00  ldloc.3
0x9bc01  brfalse.s loc_9BC11
0x9bc03  ldarg.0
0x9bc04  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9bc09  ldloc.0
0x9bc0a  callvirt instance void System.Xml.XmlWriter::WriteRaw(string data)
0x9bc0f  br.s     loc_9BC1D
0x9bc11  ldarg.0
  ... truncated ...
```
