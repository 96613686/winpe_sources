# System.Web.HttpCachePolicy::SetCacheability_0

- ea: `0x14390`
- end: `0x14406`
- name: `System.Web.HttpCachePolicy::SetCacheability_0`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x3fa0`
- `0x21640`

## callees

- `0x137b0`
- `0x14390`
- `0x188c0`
- `0x188f0`
- `0x34fa0`

## string_xrefs

- `0x143f4`: `cacheability`
- `0x143ea`: `Cacheability_for_field_must_be_private_or_nocache`

## pseudocode

```c

```

## disassembly

```asm
0x14390  ldarg.2
0x14391  brtrue.s loc_1439E
0x14393  ldstr    aField// "field"
0x14398  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1439d  throw
0x1439e  ldarg.1
0x1439f  ldc.i4.1
0x143a0  beq.s    loc_143C8
0x143a2  ldarg.1
0x143a3  ldc.i4.2
0x143a4  bne.un.s loc_143EA
0x143a6  ldarg.0
0x143a7  ldfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_privateFields
0x143ac  brtrue.s loc_143B9
0x143ae  ldarg.0
0x143af  newobj   instance void System.Web.HttpDictionary::.ctor()
0x143b4  stfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_privateFields
0x143b9  ldarg.0
0x143ba  ldfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_privateFields
0x143bf  ldarg.2
0x143c0  ldarg.2
0x143c1  callvirt instance void System.Web.HttpDictionary::SetValue(string key, object value)
0x143c6  br.s     loc_143FF
0x143c8  ldarg.0
0x143c9  ldfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_noCacheFields
0x143ce  brtrue.s loc_143DB
0x143d0  ldarg.0
0x143d1  newobj   instance void System.Web.HttpDictionary::.ctor()
0x143d6  stfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_noCacheFields
0x143db  ldarg.0
0x143dc  ldfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_noCacheFields
0x143e1  ldarg.2
0x143e2  ldarg.2
0x143e3  callvirt instance void System.Web.HttpDictionary::SetValue(string key, object value)
0x143e8  br.s     loc_143FF
0x143ea  ldstr    aCacheabilityFo// "Cacheability_for_field_must_be_private_"...
0x143ef  call     string System.Web.SR::GetString(string name)
0x143f4  ldstr    aCacheability// "cacheability"
0x143f9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x143fe  throw
0x143ff  ldarg.0
0x14400  call     instance void System.Web.HttpCachePolicy::Dirtied()
0x14405  ret
```
