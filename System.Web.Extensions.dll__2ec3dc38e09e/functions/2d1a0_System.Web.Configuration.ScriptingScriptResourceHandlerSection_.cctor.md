# System.Web.Configuration.ScriptingScriptResourceHandlerSection::.cctor

- ea: `0x2d1a0`
- end: `0x2d1eb`
- name: `System.Web.Configuration.ScriptingScriptResourceHandlerSection::.cctor`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x2d0e0`

## string_xrefs

- `0x2d1c0`: `enableCompression`

## pseudocode

```c

```

## disassembly

```asm
0x2d1a0  ldstr    aEnablecaching// "enableCaching"
0x2d1a5  ldtoken  [mscorlib]System.Boolean
0x2d1aa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d1af  ldc.i4.1
0x2d1b0  box      [mscorlib]System.Boolean
0x2d1b5  ldc.i4.0
0x2d1b6  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x2d1bb  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.ScriptingScriptResourceHandlerSection::_propEnableCaching
0x2d1c0  ldstr    aEnablecompress// "enableCompression"
0x2d1c5  ldtoken  [mscorlib]System.Boolean
0x2d1ca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d1cf  ldc.i4.1
0x2d1d0  box      [mscorlib]System.Boolean
0x2d1d5  ldc.i4.0
0x2d1d6  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x2d1db  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.ScriptingScriptResourceHandlerSection::_propEnableCompression
0x2d1e0  call     class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.ScriptingScriptResourceHandlerSection::BuildProperties()
0x2d1e5  stsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.ScriptingScriptResourceHandlerSection::_properties
0x2d1ea  ret
```
