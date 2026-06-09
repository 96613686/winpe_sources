# System.Web.Configuration.ScriptingProfileServiceSection::.cctor

- ea: `0x2cf80`
- end: `0x2cff6`
- name: `System.Web.Configuration.ScriptingProfileServiceSection::.cctor`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x2ce40`

## string_xrefs

- `0x2cf9f`: `readAccessProperties`
- `0x2cfc5`: `writeAccessProperties`

## pseudocode

```c

```

## disassembly

```asm
0x2cf80  ldstr    aEnabled_0// "enabled"
0x2cf85  ldtoken  [mscorlib]System.Boolean
0x2cf8a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cf8f  ldc.i4.0
0x2cf90  box      [mscorlib]System.Boolean
0x2cf95  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object)
0x2cf9a  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.ScriptingProfileServiceSection::_propEnabled
0x2cf9f  ldstr    aReadaccessprop// "readAccessProperties"
0x2cfa4  ldtoken  string[]
0x2cfa9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cfae  ldc.i4.0
0x2cfaf  newarr   [mscorlib]System.String
0x2cfb4  newobj   instance void [System.Web]System.Web.UI.WebControls.StringArrayConverter::.ctor()
0x2cfb9  ldnull
0x2cfba  ldc.i4.0
0x2cfbb  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x2cfc0  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.ScriptingProfileServiceSection::_propEnableForReading
0x2cfc5  ldstr    aWriteaccesspro// "writeAccessProperties"
0x2cfca  ldtoken  string[]
0x2cfcf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cfd4  ldc.i4.0
0x2cfd5  newarr   [mscorlib]System.String
0x2cfda  newobj   instance void [System.Web]System.Web.UI.WebControls.StringArrayConverter::.ctor()
0x2cfdf  ldnull
0x2cfe0  ldc.i4.0
0x2cfe1  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x2cfe6  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.ScriptingProfileServiceSection::_propEnableForWriting
0x2cfeb  call     class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.ScriptingProfileServiceSection::BuildProperties()
0x2cff0  stsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.ScriptingProfileServiceSection::_properties
0x2cff5  ret
```
