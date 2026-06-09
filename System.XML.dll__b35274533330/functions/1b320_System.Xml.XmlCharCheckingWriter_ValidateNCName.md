# System.Xml.XmlCharCheckingWriter::ValidateNCName

- ea: `0x1b320`
- end: `0x1b36d`
- name: `System.Xml.XmlCharCheckingWriter::ValidateNCName`
- size: `77`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1af80`
- `0x1afd0`
- `0x1b0d0`
- `0x1b2e0`
- `0x1b730`
- `0x1b780`
- `0x1b850`
- `0x1ba60`

## callees

- `0xe810`
- `0x128e0`
- `0x1b320`
- `0x622f0`
- `0x62370`

## string_xrefs

- `0x1b328`: `Xml_EmptyName`
- `0x1b353`: `Xml_BadStartNameChar`
- `0x1b34c`: `Xml_BadNameChar`

## pseudocode

```c

```

## disassembly

```asm
0x1b320  ldarg.1
0x1b321  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b326  brtrue.s loc_1B338
0x1b328  ldstr    aXmlEmptyname// "Xml_EmptyName"
0x1b32d  call     string System.Xml.Res::GetString(string name)
0x1b332  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1b337  throw
0x1b338  ldarg.1
0x1b339  ldc.i4.0
0x1b33a  call     int32 System.Xml.ValidateNames::ParseNCName(string s, int32 offset)
0x1b33f  stloc.0
0x1b340  ldloc.0
0x1b341  ldarg.1
0x1b342  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b347  beq.s    loc_1B36C
0x1b349  ldloc.0
0x1b34a  brfalse.s loc_1B353
0x1b34c  ldstr    aXmlBadnamechar// "Xml_BadNameChar"
0x1b351  br.s     loc_1B358
0x1b353  ldstr    aXmlBadstartnam// "Xml_BadStartNameChar"
0x1b358  ldarg.1
0x1b359  ldloc.0
0x1b35a  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(string data, int32 invCharIndex)
0x1b35f  stloc.1
0x1b360  ldloc.1
0x1b361  call     string System.Xml.Res::GetString(string name, object[] args)
0x1b366  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1b36b  throw
0x1b36c  ret
```
