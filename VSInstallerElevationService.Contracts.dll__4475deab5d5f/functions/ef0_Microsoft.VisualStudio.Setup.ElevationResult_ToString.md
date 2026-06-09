# Microsoft.VisualStudio.Setup.ElevationResult::ToString

- ea: `0xef0`
- end: `0xf30`
- name: `Microsoft.VisualStudio.Setup.ElevationResult::ToString`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0xef0`
- `0xf30`

## pseudocode

```c

```

## disassembly

```asm
0xef0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xef5  stloc.0
0xef6  ldloc.0
0xef7  ldstr    aElevationresul// "ElevationResult"
0xefc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf01  pop
0xf02  ldloc.0
0xf03  ldstr    asc_202C// " { "
0xf08  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf0d  pop
0xf0e  ldarg.0
0xf0f  ldloc.0
0xf10  callvirt instance bool Microsoft.VisualStudio.Setup.ElevationResult::PrintMembers(class [mscorlib]System.Text.StringBuilder builder)
0xf15  brfalse.s loc_F20
0xf17  ldloc.0
0xf18  ldc.i4.s 0x20
0xf1a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0xf1f  pop
0xf20  ldloc.0
0xf21  ldc.i4.s 0x7D
0xf23  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0xf28  pop
0xf29  ldloc.0
0xf2a  callvirt instance string [mscorlib]System.Object::ToString()
0xf2f  ret
```
