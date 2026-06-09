# Microsoft.VisualStudio.Setup.ExtensionRecords::ToString

- ea: `0x5120`
- end: `0x5160`
- name: `Microsoft.VisualStudio.Setup.ExtensionRecords::ToString`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x5120`
- `0x5160`

## string_xrefs

- `0x5127`: `ExtensionRecords`

## pseudocode

```c

```

## disassembly

```asm
0x5120  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x5125  stloc.0
0x5126  ldloc.0
0x5127  ldstr    aExtensionrecor// "ExtensionRecords"
0x512c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5131  pop
0x5132  ldloc.0
0x5133  ldstr    asc_1FA62// " { "
0x5138  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x513d  pop
0x513e  ldarg.0
0x513f  ldloc.0
0x5140  callvirt instance bool Microsoft.VisualStudio.Setup.ExtensionRecords::PrintMembers(class [mscorlib]System.Text.StringBuilder builder)
0x5145  brfalse.s loc_5150
0x5147  ldloc.0
0x5148  ldc.i4.s 0x20
0x514a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x514f  pop
0x5150  ldloc.0
0x5151  ldc.i4.s 0x7D
0x5153  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x5158  pop
0x5159  ldloc.0
0x515a  callvirt instance string [mscorlib]System.Object::ToString()
0x515f  ret
```
