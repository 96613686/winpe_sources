# Microsoft.BIServer.Configuration.Extension::Equals

- ea: `0x25a0`
- end: `0x25f0`
- name: `Microsoft.BIServer.Configuration.Extension::Equals`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x24b0`
- `0x24d0`
- `0x24f0`
- `0x25a0`

## pseudocode

```c

```

## disassembly

```asm
0x25a0  ldc.i4.1
0x25a1  stloc.0
0x25a2  ldarg.1
0x25a3  isinst   Microsoft.BIServer.Configuration.Extension
0x25a8  brtrue.s loc_25AC
0x25aa  ldc.i4.0
0x25ab  ret
0x25ac  ldarg.1
0x25ad  castclass Microsoft.BIServer.Configuration.Extension
0x25b2  stloc.1
0x25b3  ldarg.0
0x25b4  call     instance string Microsoft.BIServer.Configuration.Extension::get_Assembly()
0x25b9  ldloc.1
0x25ba  callvirt instance string Microsoft.BIServer.Configuration.Extension::get_Assembly()
0x25bf  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x25c4  brtrue.s loc_25EC
0x25c6  ldarg.0
0x25c7  call     instance string Microsoft.BIServer.Configuration.Extension::get_Class()
0x25cc  ldloc.1
0x25cd  callvirt instance string Microsoft.BIServer.Configuration.Extension::get_Class()
0x25d2  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x25d7  brtrue.s loc_25EC
0x25d9  ldarg.0
0x25da  call     instance string Microsoft.BIServer.Configuration.Extension::get_Configuration()
0x25df  ldloc.1
0x25e0  callvirt instance string Microsoft.BIServer.Configuration.Extension::get_Configuration()
0x25e5  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x25ea  brfalse.s loc_25EE
0x25ec  ldc.i4.0
0x25ed  stloc.0
0x25ee  ldloc.0
0x25ef  ret
```
