# System.Xml.XmlWellFormedWriter::WriteDocType

- ea: `0x3cb00`
- end: `0x3cc46`
- name: `System.Xml.XmlWellFormedWriter::WriteDocType`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callees

- `0xf1e0`
- `0xf280`
- `0xfc50`
- `0x128e0`
- `0x3cb00`
- `0x3e4e0`
- `0x40770`
- `0x622f0`
- `0x62370`

## string_xrefs

- `0x3cb0b`: `Xml_EmptyName`
- `0x3cb9c`: `Xml_InvalidCharacter`
- `0x3cbce`: `Xml_InvalidCharacter`
- `0x3cc02`: `Xml_InvalidCharacter`
- `0x3cb2c`: `Xml_DtdNotAllowedInFragment`
- `0x3cb53`: `Xml_DtdAlreadyWritten`
- `0x3cbe1`: `sysid`

## pseudocode

```c

```

## disassembly

```asm
0x3cb00  ldarg.1
0x3cb01  brfalse.s loc_3CB0B
0x3cb03  ldarg.1
0x3cb04  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3cb09  brtrue.s loc_3CB1B
0x3cb0b  ldstr    aXmlEmptyname// "Xml_EmptyName"
0x3cb10  call     string System.Xml.Res::GetString(string name)
0x3cb15  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3cb1a  throw
0x3cb1b  ldarg.1
0x3cb1c  ldc.i4.1
0x3cb1d  call     string System.Xml.XmlConvert::VerifyQName(string name, valuetype System.Xml.ExceptionType exceptionType)
0x3cb22  pop
0x3cb23  ldarg.0
0x3cb24  ldfld    valuetype System.Xml.ConformanceLevel System.Xml.XmlWellFormedWriter::conformanceLevel
0x3cb29  ldc.i4.1
0x3cb2a  bne.un.s loc_3CB3C
0x3cb2c  ldstr    aXmlDtdnotallow// "Xml_DtdNotAllowedInFragment"
0x3cb31  call     string System.Xml.Res::GetString(string name)
0x3cb36  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3cb3b  throw
0x3cb3c  ldarg.0
0x3cb3d  ldc.i4.4
0x3cb3e  call     instance void System.Xml.XmlWellFormedWriter::AdvanceState(valuetype Token token)
0x3cb43  ldarg.0
0x3cb44  ldfld    bool System.Xml.XmlWellFormedWriter::dtdWritten
0x3cb49  brfalse.s loc_3CB63
0x3cb4b  ldarg.0
0x3cb4c  ldc.i4.s 0x10
0x3cb4e  stfld    valuetype State System.Xml.XmlWellFormedWriter::currentState
0x3cb53  ldstr    aXmlDtdalreadyw// "Xml_DtdAlreadyWritten"
0x3cb58  call     string System.Xml.Res::GetString(string name)
0x3cb5d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3cb62  throw
0x3cb63  ldarg.0
0x3cb64  ldfld    valuetype System.Xml.ConformanceLevel System.Xml.XmlWellFormedWriter::conformanceLevel
0x3cb69  brtrue.s loc_3CB7D
0x3cb6b  ldarg.0
0x3cb6c  ldc.i4.2
0x3cb6d  stfld    valuetype System.Xml.ConformanceLevel System.Xml.XmlWellFormedWriter::conformanceLevel
0x3cb72  ldarg.0
0x3cb73  ldsfld   valuetype State[] System.Xml.XmlWellFormedWriter::StateTableDocument
0x3cb78  stfld    valuetype State[] System.Xml.XmlWellFormedWriter::stateTable
0x3cb7d  ldarg.0
0x3cb7e  ldfld    bool System.Xml.XmlWellFormedWriter::checkCharacters
0x3cb83  brfalse  loc_3CC21
0x3cb88  ldarg.2
0x3cb89  brfalse.s loc_3CBBA
0x3cb8b  ldarg.0
0x3cb8c  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlWellFormedWriter::xmlCharType
0x3cb91  ldarg.2
0x3cb92  call     instance int32 System.Xml.XmlCharType::IsPublicId(string str)
0x3cb97  dup
0x3cb98  stloc.0
0x3cb99  ldc.i4.0
0x3cb9a  blt.s    loc_3CBBA
0x3cb9c  ldstr    aXmlInvalidchar// "Xml_InvalidCharacter"
0x3cba1  ldarg.2
0x3cba2  ldloc.0
0x3cba3  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(string data, int32 invCharIndex)
0x3cba8  stloc.1
0x3cba9  ldloc.1
0x3cbaa  call     string System.Xml.Res::GetString(string name, object[] args)
0x3cbaf  ldstr    aPubid// "pubid"
0x3cbb4  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x3cbb9  throw
0x3cbba  ldarg.3
0x3cbbb  brfalse.s loc_3CBEC
0x3cbbd  ldarg.0
0x3cbbe  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlWellFormedWriter::xmlCharType
0x3cbc3  ldarg.3
0x3cbc4  call     instance int32 System.Xml.XmlCharType::IsOnlyCharData(string str)
0x3cbc9  dup
0x3cbca  stloc.0
0x3cbcb  ldc.i4.0
0x3cbcc  blt.s    loc_3CBEC
0x3cbce  ldstr    aXmlInvalidchar// "Xml_InvalidCharacter"
0x3cbd3  ldarg.3
0x3cbd4  ldloc.0
0x3cbd5  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(string data, int32 invCharIndex)
0x3cbda  stloc.1
0x3cbdb  ldloc.1
0x3cbdc  call     string System.Xml.Res::GetString(string name, object[] args)
0x3cbe1  ldstr    aSysid// "sysid"
0x3cbe6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x3cbeb  throw
0x3cbec  ldarg.s  4
0x3cbee  brfalse.s loc_3CC21
0x3cbf0  ldarg.0
0x3cbf1  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlWellFormedWriter::xmlCharType
0x3cbf6  ldarg.s  4
0x3cbf8  call     instance int32 System.Xml.XmlCharType::IsOnlyCharData(string str)
0x3cbfd  dup
0x3cbfe  stloc.0
0x3cbff  ldc.i4.0
0x3cc00  blt.s    loc_3CC21
0x3cc02  ldstr    aXmlInvalidchar// "Xml_InvalidCharacter"
0x3cc07  ldarg.s  4
0x3cc09  ldloc.0
0x3cc0a  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(string data, int32 invCharIndex)
0x3cc0f  stloc.1
0x3cc10  ldloc.1
0x3cc11  call     string System.Xml.Res::GetString(string name, object[] args)
0x3cc16  ldstr    aSubset// "subset"
0x3cc1b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x3cc20  throw
0x3cc21  ldarg.0
0x3cc22  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3cc27  ldarg.1
0x3cc28  ldarg.2
0x3cc29  ldarg.3
0x3cc2a  ldarg.s  4
0x3cc2c  callvirt instance void System.Xml.XmlWriter::WriteDocType(string name, string pubid, string sysid, string subset)
0x3cc31  ldarg.0
0x3cc32  ldc.i4.1
0x3cc33  stfld    bool System.Xml.XmlWellFormedWriter::dtdWritten
0x3cc38  leave.s  loc_3CC45
0x3cc3a  pop
0x3cc3b  ldarg.0
0x3cc3c  ldc.i4.s 0x10
0x3cc3e  stfld    valuetype State System.Xml.XmlWellFormedWriter::currentState
0x3cc43  rethrow
0x3cc45  ret
```
