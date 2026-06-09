# Microsoft.VisualStudio.Setup.ElevationRequest::ToString

- ea: `0xb10`
- end: `0xb50`
- name: `Microsoft.VisualStudio.Setup.ElevationRequest::ToString`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0xb10`
- `0xb50`

## pseudocode

```c

```

## disassembly

```asm
0xb10  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xb15  stloc.0
0xb16  ldloc.0
0xb17  ldstr    aElevationreque// "ElevationRequest"
0xb1c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb21  pop
0xb22  ldloc.0
0xb23  ldstr    asc_202C// " { "
0xb28  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb2d  pop
0xb2e  ldarg.0
0xb2f  ldloc.0
0xb30  callvirt instance bool Microsoft.VisualStudio.Setup.ElevationRequest::PrintMembers(class [mscorlib]System.Text.StringBuilder builder)
0xb35  brfalse.s loc_B40
0xb37  ldloc.0
0xb38  ldc.i4.s 0x20
0xb3a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0xb3f  pop
0xb40  ldloc.0
0xb41  ldc.i4.s 0x7D
0xb43  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0xb48  pop
0xb49  ldloc.0
0xb4a  callvirt instance string [mscorlib]System.Object::ToString()
0xb4f  ret
```
