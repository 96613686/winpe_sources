# ExtensionArray::get_Item

- ea: `0x15740`
- end: `0x15787`
- name: `ExtensionArray::get_Item`
- size: `71`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x5cf0`
- `0x6f70`
- `0x15a70`

## callees

- `0x4fa0`
- `0x15740`

## pseudocode

```c

```

## disassembly

```asm
0x15740  ldarg.0
0x15741  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x15746  stloc.0
0x15747  br.s     loc_15768
0x15749  ldloc.0
0x1574a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1574f  castclass Microsoft.ReportingServices.Diagnostics.Extension
0x15754  stloc.1
0x15755  ldarg.1
0x15756  ldloc.1
0x15757  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x1575c  ldc.i4.5
0x1575d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x15762  brtrue.s loc_15768
0x15764  ldloc.1
0x15765  stloc.2
0x15766  leave.s  loc_15785
0x15768  ldloc.0
0x15769  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1576e  brtrue.s loc_15749
0x15770  leave.s  loc_15783
0x15772  ldloc.0
0x15773  isinst   [mscorlib]System.IDisposable
0x15778  stloc.3
0x15779  ldloc.3
0x1577a  brfalse.s loc_15782
0x1577c  ldloc.3
0x1577d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15782  endfinally
0x15783  ldnull
0x15784  ret
0x15785  ldloc.2
0x15786  ret
```
