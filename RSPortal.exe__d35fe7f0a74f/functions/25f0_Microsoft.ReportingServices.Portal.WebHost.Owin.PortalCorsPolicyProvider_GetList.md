# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::GetList

- ea: `0x25f0`
- end: `0x2621`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::GetList`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x24d0`

## callees

- `0x25f0`

## pseudocode

```c

```

## disassembly

```asm
0x25f0  ldarg.2
0x25f1  ldc.i4.1
0x25f2  newarr   [mscorlib]System.Char
0x25f7  dup
0x25f8  ldc.i4.0
0x25f9  ldc.i4.s 0x2C
0x25fb  stelem.i2
0x25fc  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2601  stloc.0
0x2602  ldc.i4.0
0x2603  stloc.1
0x2604  br.s     loc_261A
0x2606  ldloc.0
0x2607  ldloc.1
0x2608  ldelem.ref
0x2609  stloc.2
0x260a  ldarg.1
0x260b  ldloc.2
0x260c  callvirt instance string [mscorlib]System.String::Trim()
0x2611  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x2616  ldloc.1
0x2617  ldc.i4.1
0x2618  add
0x2619  stloc.1
0x261a  ldloc.1
0x261b  ldloc.0
0x261c  ldlen
0x261d  conv.i4
0x261e  blt.s    loc_2606
0x2620  ret
```
