# System.Xaml.XamlServices::Transform_0

- ea: `0xcc00`
- end: `0xcc7c`
- name: `System.Xaml.XamlServices::Transform_0`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0xcbf0`

## callees

- `0x6720`
- `0x6730`
- `0x6740`
- `0x6760`
- `0x6770`
- `0xb310`
- `0xcc00`
- `0xf3c0`
- `0xf4a0`

## string_xrefs

- `0xcc03`: `xamlReader`
- `0xcc11`: `xamlWriter`

## pseudocode

```c

```

## disassembly

```asm
0xcc00  ldarg.0
0xcc01  brtrue.s loc_CC0E
0xcc03  ldstr    aXamlreader_0// "xamlReader"
0xcc08  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcc0d  throw
0xcc0e  ldarg.1
0xcc0f  brtrue.s loc_CC1C
0xcc11  ldstr    aXamlwriter_0// "xamlWriter"
0xcc16  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcc1b  throw
0xcc1c  ldarg.0
0xcc1d  isinst   System.Xaml.IXamlLineInfo
0xcc22  stloc.0
0xcc23  ldarg.1
0xcc24  isinst   System.Xaml.IXamlLineInfoConsumer
0xcc29  stloc.1
0xcc2a  ldc.i4.0
0xcc2b  stloc.2
0xcc2c  ldloc.0
0xcc2d  brfalse.s loc_CC6A
0xcc2f  ldloc.0
0xcc30  callvirt instance bool System.Xaml.IXamlLineInfo::get_HasLineInfo()
0xcc35  brfalse.s loc_CC6A
0xcc37  ldloc.1
0xcc38  brfalse.s loc_CC6A
0xcc3a  ldloc.1
0xcc3b  callvirt instance bool System.Xaml.IXamlLineInfoConsumer::get_ShouldProvideLineInfo()
0xcc40  brfalse.s loc_CC6A
0xcc42  ldc.i4.1
0xcc43  stloc.2
0xcc44  br.s     loc_CC6A
0xcc46  ldloc.2
0xcc47  brfalse.s loc_CC63
0xcc49  ldloc.0
0xcc4a  callvirt instance int32 System.Xaml.IXamlLineInfo::get_LineNumber()
0xcc4f  brfalse.s loc_CC63
0xcc51  ldloc.1
0xcc52  ldloc.0
0xcc53  callvirt instance int32 System.Xaml.IXamlLineInfo::get_LineNumber()
0xcc58  ldloc.0
0xcc59  callvirt instance int32 System.Xaml.IXamlLineInfo::get_LinePosition()
0xcc5e  callvirt instance void System.Xaml.IXamlLineInfoConsumer::SetLineInfo(int32 lineNumber, int32 linePosition)
0xcc63  ldarg.1
0xcc64  ldarg.0
0xcc65  callvirt instance void System.Xaml.XamlWriter::WriteNode(class System.Xaml.XamlReader reader)
0xcc6a  ldarg.0
0xcc6b  callvirt instance bool System.Xaml.XamlReader::Read()
0xcc70  brtrue.s loc_CC46
0xcc72  ldarg.2
0xcc73  brfalse.s loc_CC7B
0xcc75  ldarg.1
0xcc76  callvirt instance void System.Xaml.XamlWriter::Close()
0xcc7b  ret
```
