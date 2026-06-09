# Microsoft.VisualStudio.Setup.CheckForUpdatesResult::ToString

- ea: `0x26c0`
- end: `0x2700`
- name: `Microsoft.VisualStudio.Setup.CheckForUpdatesResult::ToString`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x26c0`
- `0x2700`

## string_xrefs

- `0x26c7`: `CheckForUpdatesResult`

## pseudocode

```c

```

## disassembly

```asm
0x26c0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x26c5  stloc.0
0x26c6  ldloc.0
0x26c7  ldstr    aCheckforupdate// "CheckForUpdatesResult"
0x26cc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x26d1  pop
0x26d2  ldloc.0
0x26d3  ldstr    asc_7A60// " { "
0x26d8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x26dd  pop
0x26de  ldarg.0
0x26df  ldloc.0
0x26e0  callvirt instance bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::PrintMembers(class [mscorlib]System.Text.StringBuilder builder)
0x26e5  brfalse.s loc_26F0
0x26e7  ldloc.0
0x26e8  ldc.i4.s 0x20
0x26ea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x26ef  pop
0x26f0  ldloc.0
0x26f1  ldc.i4.s 0x7D
0x26f3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x26f8  pop
0x26f9  ldloc.0
0x26fa  callvirt instance string [mscorlib]System.Object::ToString()
0x26ff  ret
```
