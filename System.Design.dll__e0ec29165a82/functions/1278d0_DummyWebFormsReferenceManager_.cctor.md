# DummyWebFormsReferenceManager::.cctor

- ea: `0x1278d0`
- end: `0x127924`
- name: `DummyWebFormsReferenceManager::.cctor`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x127290`

## string_xrefs

- `0x1278d8`: `System.Web, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`
- `0x1278ea`: `System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0x1278fc`: `System.Web.DynamicData, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0x12790e`: `System.Web.Entity, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`

## pseudocode

```c

```

## disassembly

```asm
0x1278d0  ldc.i4.4
0x1278d1  newarr   [mscorlib]System.String
0x1278d6  dup
0x1278d7  ldc.i4.0
0x1278d8  ldstr    aSystemWebVersi// "System.Web, Version=4.0.0.0, Culture=ne"...
0x1278dd  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x1278e2  call     string DummyWebFormsReferenceManager::GetAssemblySpec(class [mscorlib]System.Reflection.AssemblyName assemblyName)
0x1278e7  stelem.ref
0x1278e8  dup
0x1278e9  ldc.i4.1
0x1278ea  ldstr    aSystemWebExten// "System.Web.Extensions, Version=4.0.0.0,"...
0x1278ef  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x1278f4  call     string DummyWebFormsReferenceManager::GetAssemblySpec(class [mscorlib]System.Reflection.AssemblyName assemblyName)
0x1278f9  stelem.ref
0x1278fa  dup
0x1278fb  ldc.i4.2
0x1278fc  ldstr    aSystemWebDynam_0// "System.Web.DynamicData, Version=4.0.0.0"...
0x127901  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x127906  call     string DummyWebFormsReferenceManager::GetAssemblySpec(class [mscorlib]System.Reflection.AssemblyName assemblyName)
0x12790b  stelem.ref
0x12790c  dup
0x12790d  ldc.i4.3
0x12790e  ldstr    aSystemWebEntit// "System.Web.Entity, Version=4.0.0.0, Cul"...
0x127913  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x127918  call     string DummyWebFormsReferenceManager::GetAssemblySpec(class [mscorlib]System.Reflection.AssemblyName assemblyName)
0x12791d  stelem.ref
0x12791e  stsfld   string[] DummyWebFormsReferenceManager::FrameworkTagPrefixAssemblySpecs
0x127923  ret
```
