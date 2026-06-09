# DefaultComparer::Compare

- ea: `0xcc60`
- end: `0xccb2`
- name: `DefaultComparer::Compare`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x4c0`
- `0x8440`
- `0xcc60`
- `0xccc0`

## pseudocode

```c

```

## disassembly

```asm
0xcc60  ldarg.1
0xcc61  isinst   Microsoft.ManagementConsole.ResultNode
0xcc66  stloc.0
0xcc67  ldloc.0
0xcc68  brtrue.s loc_CC7F
0xcc6a  call     string Microsoft.ManagementConsole.Internal.Strings::get_ListViewCompareNullObject()
0xcc6f  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0xcc74  ldstr    aObject1// "object1"
0xcc79  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xcc7e  throw
0xcc7f  ldarg.2
0xcc80  isinst   Microsoft.ManagementConsole.ResultNode
0xcc85  stloc.1
0xcc86  ldloc.1
0xcc87  brtrue.s loc_CC9E
0xcc89  call     string Microsoft.ManagementConsole.Internal.Strings::get_ListViewCompareNullObject()
0xcc8e  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0xcc93  ldstr    aObject2// "object2"
0xcc98  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xcc9d  throw
0xcc9e  ldarg.0
0xcc9f  ldloc.0
0xcca0  call     instance string DefaultComparer::GetStringToCompare(class Microsoft.ManagementConsole.ResultNode node)
0xcca5  ldarg.0
0xcca6  ldloc.1
0xcca7  call     instance string DefaultComparer::GetStringToCompare(class Microsoft.ManagementConsole.ResultNode node)
0xccac  call     int32 [mscorlib]System.String::Compare(string, string)
0xccb1  ret
```
