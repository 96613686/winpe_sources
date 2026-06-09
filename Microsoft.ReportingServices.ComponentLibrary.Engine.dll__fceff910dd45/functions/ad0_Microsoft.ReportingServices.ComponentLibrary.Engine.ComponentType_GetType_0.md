# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::GetType_0

- ea: `0xad0`
- end: `0xb22`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::GetType_0`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xb30`

## callees

- `0xa60`
- `0xad0`
- `0xb60`

## pseudocode

```c

```

## disassembly

```asm
0xad0  ldarg.0
0xad1  ldnull
0xad2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xad7  brfalse.s loc_AE4
0xad9  ldstr    aRdltype// "rdlType"
0xade  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xae3  throw
0xae4  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType> Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_AllSupportedTypes()
0xae9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType>::GetEnumerator()
0xaee  stloc.0
0xaef  br.s     loc_B0A
0xaf1  ldloc.0
0xaf2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType>::get_Current()
0xaf7  stloc.1
0xaf8  ldloc.1
0xaf9  callvirt instance class [mscorlib]System.Type Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_RdlType()
0xafe  ldarg.0
0xaff  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xb04  brfalse.s loc_B0A
0xb06  ldloc.1
0xb07  stloc.2
0xb08  leave.s  loc_B20
0xb0a  ldloc.0
0xb0b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb10  brtrue.s loc_AF1
0xb12  leave.s  loc_B1E
0xb14  ldloc.0
0xb15  brfalse.s loc_B1D
0xb17  ldloc.0
0xb18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb1d  endfinally
0xb1e  ldnull
0xb1f  ret
0xb20  ldloc.2
0xb21  ret
```
