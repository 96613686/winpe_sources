# System.Windows.Markup.ServiceProviders::AddService

- ea: `0x42910`
- end: `0x42973`
- name: `System.Windows.Markup.ServiceProviders::AddService`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x2c100`
- `0x42910`

## string_xrefs

- `0x42919`: `serviceType`
- `0x42967`: `serviceType`
- `0x42927`: `service`
- `0x4295d`: `ServiceTypeAlreadyAdded`

## pseudocode

```c

```

## disassembly

```asm
0x42910  ldarg.1
0x42911  ldnull
0x42912  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x42917  brfalse.s loc_42924
0x42919  ldstr    aServicetype// "serviceType"
0x4291e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x42923  throw
0x42924  ldarg.2
0x42925  brtrue.s loc_42932
0x42927  ldstr    aService// "service"
0x4292c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x42931  throw
0x42932  ldarg.0
0x42933  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> System.Windows.Markup.ServiceProviders::_objDict
0x42938  ldarg.1
0x42939  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::ContainsKey(var<u1>)
0x4293e  brtrue.s loc_4294E
0x42940  ldarg.0
0x42941  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> System.Windows.Markup.ServiceProviders::_objDict
0x42946  ldarg.1
0x42947  ldarg.2
0x42948  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::Add(var<u1>, !!T0)
0x4294d  ret
0x4294e  ldarg.0
0x4294f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> System.Windows.Markup.ServiceProviders::_objDict
0x42954  ldarg.1
0x42955  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::get_Item(void)
0x4295a  ldarg.2
0x4295b  beq.s    loc_42972
0x4295d  ldstr    aServicetypealr// "ServiceTypeAlreadyAdded"
0x42962  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x42967  ldstr    aServicetype// "serviceType"
0x4296c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x42971  throw
0x42972  ret
```
