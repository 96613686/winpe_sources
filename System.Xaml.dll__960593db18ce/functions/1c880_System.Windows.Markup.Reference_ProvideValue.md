# System.Windows.Markup.Reference::ProvideValue

- ea: `0x1c880`
- end: `0x1c8ff`
- name: `System.Windows.Markup.Reference::ProvideValue`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x67f0`
- `0x6820`
- `0x11f20`
- `0x1c860`
- `0x1c880`

## string_xrefs

- `0x1c883`: `serviceProvider`

## pseudocode

```c

```

## disassembly

```asm
0x1c880  ldarg.1
0x1c881  brtrue.s loc_1C88E
0x1c883  ldstr    aServiceprovide// "serviceProvider"
0x1c888  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1c88d  throw
0x1c88e  ldarg.1
0x1c88f  ldtoken  System.Xaml.IXamlNameResolver
0x1c894  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c899  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x1c89e  isinst   System.Xaml.IXamlNameResolver
0x1c8a3  stloc.0
0x1c8a4  ldloc.0
0x1c8a5  brtrue.s loc_1C8B7
0x1c8a7  ldstr    aMissingnameres// "MissingNameResolver"
0x1c8ac  call     string System.Xaml.SR::Get(string id)
0x1c8b1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1c8b6  throw
0x1c8b7  ldarg.0
0x1c8b8  call     instance string System.Windows.Markup.Reference::get_Name()
0x1c8bd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1c8c2  brfalse.s loc_1C8D4
0x1c8c4  ldstr    aMusthavename// "MustHaveName"
0x1c8c9  call     string System.Xaml.SR::Get(string id)
0x1c8ce  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1c8d3  throw
0x1c8d4  ldloc.0
0x1c8d5  ldarg.0
0x1c8d6  call     instance string System.Windows.Markup.Reference::get_Name()
0x1c8db  callvirt instance object System.Xaml.IXamlNameResolver::Resolve(string name)
0x1c8e0  stloc.1
0x1c8e1  ldloc.1
0x1c8e2  brtrue.s loc_1C8FD
0x1c8e4  ldc.i4.1
0x1c8e5  newarr   [mscorlib]System.String
0x1c8ea  dup
0x1c8eb  ldc.i4.0
0x1c8ec  ldarg.0
0x1c8ed  call     instance string System.Windows.Markup.Reference::get_Name()
0x1c8f2  stelem.ref
0x1c8f3  stloc.2
0x1c8f4  ldloc.0
0x1c8f5  ldloc.2
0x1c8f6  ldc.i4.1
0x1c8f7  callvirt instance object System.Xaml.IXamlNameResolver::GetFixupToken(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> names, bool canAssignDirectly)
0x1c8fc  stloc.1
0x1c8fd  ldloc.1
0x1c8fe  ret
```
