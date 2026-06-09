# Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope

- ea: `0x25590`
- end: `0x255e0`
- name: `Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope`
- size: `80`
- prototype: ``
- caller_count: `37`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x8690`
- `0x86a0`
- `0x8940`
- `0x8990`
- `0xb530`
- `0xfa30`
- `0x10a50`
- `0x118c0`
- `0x126f0`
- `0x129b0`
- `0x131a0`
- `0x153a0`
- `0x15960`
- `0x15b40`
- `0x15bb0`
- `0x16580`
- `0x16e60`
- `0x17570`
- `0x17e10`
- `0x183e0`
- `0x19f70`
- `0x19ff0`
- `0x1e260`
- `0x21b30`
- `0x21f00`
- `0x22530`
- `0x23da0`
- `0x240e0`
- `0x25a90`
- `0x29720`
- `0x29740`
- `0x29770`
- `0x29790`
- `0x297d0`
- `0x29800`
- `0x2b290`
- `0x35140`

## callees

- `0x97d0`
- `0x25520`
- `0x25550`
- `0x25590`
- `0x25cd0`
- `0x25ce0`
- `0x25cf0`

## pseudocode

```c

```

## disassembly

```asm
0x25590  ldarg.0
0x25591  brtrue.s loc_2559E
0x25593  ldstr    aScopeIsNull// "scope is null"
0x25598  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x2559d  throw
0x2559e  ldloca.s 0
0x255a0  initobj  Microsoft.ReportingServices.Modeling.SRObjectDescriptor
0x255a6  ldloca.s 0
0x255a8  ldarg.0
0x255a9  callvirt instance string Microsoft.ReportingServices.Modeling.IValidationScope::get_ObjectType()
0x255ae  call     instance void Microsoft.ReportingServices.Modeling.SRObjectDescriptor::set_ObjectType(string value)
0x255b3  ldarg.0
0x255b4  callvirt instance string Microsoft.ReportingServices.Modeling.IValidationScope::get_ObjectName()
0x255b9  brfalse.s loc_255DE
0x255bb  ldloca.s 0
0x255bd  ldarg.0
0x255be  callvirt instance string Microsoft.ReportingServices.Modeling.IValidationScope::get_ObjectName()
0x255c3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x255c8  ldc.i4.0
0x255c9  bgt.s    loc_255D3
0x255cb  ldarg.0
0x255cc  callvirt instance string Microsoft.ReportingServices.Modeling.IValidationScope::get_ObjectID()
0x255d1  br.s     loc_255D9
0x255d3  ldarg.0
0x255d4  callvirt instance string Microsoft.ReportingServices.Modeling.IValidationScope::get_ObjectName()
0x255d9  call     instance void Microsoft.ReportingServices.Modeling.SRObjectDescriptor::set_ObjectName(string value)
0x255de  ldloc.0
0x255df  ret
```
