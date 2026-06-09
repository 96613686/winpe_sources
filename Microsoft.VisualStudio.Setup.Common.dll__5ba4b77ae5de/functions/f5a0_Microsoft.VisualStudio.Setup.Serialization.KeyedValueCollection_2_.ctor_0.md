# Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2::.ctor_0

- ea: `0xf5a0`
- end: `0xf5d3`
- name: `Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2::.ctor_0`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0xef40`

## string_xrefs

- `0xf5a7`: `comparer`

## pseudocode

```c

```

## disassembly

```asm
0xf5a0  ldarg.0
0xf5a1  call     instance void [mscorlib]System.Object::.ctor()
0xf5a6  ldarg.1
0xf5a7  ldstr    aComparer// "comparer"
0xf5ac  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xf5b1  ldarg.0
0xf5b2  ldarg.1
0xf5b3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0xf5b8  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0> class Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<var<u1>, !!T0>::store
0xf5bd  ldarg.0
0xf5be  ldtoken  var<u1>
0xf5c3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf5c8  call     bool Microsoft.VisualStudio.Setup.Serialization.Extensions::IsNullable(class [mscorlib]System.Type type)
0xf5cd  stfld    bool class Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<var<u1>, !!T0>::isNullable
0xf5d2  ret
```
