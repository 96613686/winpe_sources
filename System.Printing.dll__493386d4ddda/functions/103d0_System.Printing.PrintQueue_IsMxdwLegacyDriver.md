# System.Printing.PrintQueue::IsMxdwLegacyDriver

- ea: `0x103d0`
- end: `0x1040f`
- name: `System.Printing.PrintQueue::IsMxdwLegacyDriver`
- size: `63`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xca20`
- `0xd580`
- `0xdea0`

## callees

- `0xa730`
- `0xee60`
- `0xf600`
- `0x103d0`

## string_xrefs

- `0x103f1`: `Microsoft XPS Document Writer`

## pseudocode

```c

```

## disassembly

```asm
0x103d0  ldc.i4.0
0x103d1  stloc.0
0x103d2  ldarg.0
0x103d3  call     instance bool System.Printing.PrintQueue::get_InPartialTrust()
0x103d8  brfalse.s loc_103E5
0x103da  ldc.i4.2
0x103db  newobj   instance void [System.Drawing]System.Drawing.Printing.PrintingPermission::.ctor(valuetype [System.Drawing]System.Drawing.Printing.PrintingPermissionLevel)
0x103e0  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x103e5  nop
0x103e6  ldarg.0
0x103e7  callvirt instance class System.Printing.PrintDriver System.Printing.PrintQueue::get_QueueDriver()
0x103ec  callvirt instance string System.Printing.PrintSystemObject::get_Name()
0x103f1  ldstr    aMicrosoftXpsDo// "Microsoft XPS Document Writer"
0x103f6  ldc.i4.5
0x103f7  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x103fc  stloc.0
0x103fd  leave.s  loc_1040D
0x103ff  ldarg.0
0x10400  call     instance bool System.Printing.PrintQueue::get_InPartialTrust()
0x10405  brfalse.s loc_1040C
0x10407  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x1040c  endfinally
0x1040d  ldloc.0
0x1040e  ret
```
