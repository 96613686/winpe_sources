# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::GetType

- ea: `0xa70`
- end: `0xacf`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::GetType`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x160`

## callees

- `0xa60`
- `0xa70`
- `0xb50`

## pseudocode

```c

```

## disassembly

```asm
0xa70  ldarg.0
0xa71  brtrue.s loc_A7E
0xa73  ldstr    aRdltypename// "rdlTypeName"
0xa78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa7d  throw
0xa7e  ldarg.0
0xa7f  callvirt instance string [mscorlib]System.String::Trim()
0xa84  ldsfld   string [mscorlib]System.String::Empty
0xa89  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xa8e  brfalse.s loc_ACB
0xa90  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType> Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_AllSupportedTypes()
0xa95  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType>::GetEnumerator()
0xa9a  stloc.0
0xa9b  br.s     loc_AB7
0xa9d  ldloc.0
0xa9e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType>::get_Current()
0xaa3  stloc.1
0xaa4  ldloc.1
0xaa5  callvirt instance string Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_Name()
0xaaa  ldarg.0
0xaab  ldc.i4.5
0xaac  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xab1  brfalse.s loc_AB7
0xab3  ldloc.1
0xab4  stloc.2
0xab5  leave.s  loc_ACD
0xab7  ldloc.0
0xab8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xabd  brtrue.s loc_A9D
0xabf  leave.s  loc_ACB
0xac1  ldloc.0
0xac2  brfalse.s loc_ACA
0xac4  ldloc.0
0xac5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaca  endfinally
0xacb  ldnull
0xacc  ret
0xacd  ldloc.2
0xace  ret
```
