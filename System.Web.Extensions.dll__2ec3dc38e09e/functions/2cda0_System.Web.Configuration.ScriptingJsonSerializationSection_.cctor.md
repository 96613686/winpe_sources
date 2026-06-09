# System.Web.Configuration.ScriptingJsonSerializationSection::.cctor

- ea: `0x2cda0`
- end: `0x2ce23`
- name: `System.Web.Configuration.ScriptingJsonSerializationSection::.cctor`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x2ccb0`

## string_xrefs

- `0x2cde8`: `maxJsonLength`

## pseudocode

```c

```

## disassembly

```asm
0x2cda0  ldstr    aConverters// "converters"
0x2cda5  ldtoken  System.Web.Configuration.ConvertersCollection
0x2cdaa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cdaf  ldnull
0x2cdb0  ldc.i4.1
0x2cdb1  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x2cdb6  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.ScriptingJsonSerializationSection::_propConverters
0x2cdbb  ldstr    aRecursionlimit// "recursionLimit"
0x2cdc0  ldtoken  [mscorlib]System.Int32
0x2cdc5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cdca  ldc.i4.s 0x64
0x2cdcc  box      [mscorlib]System.Int32
0x2cdd1  ldnull
0x2cdd2  ldc.i4.1
0x2cdd3  ldc.i4   0x7FFFFFFF
0x2cdd8  newobj   instance void [System.Configuration]System.Configuration.IntegerValidator::.ctor(int32, int32)
0x2cddd  ldc.i4.0
0x2cdde  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x2cde3  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.ScriptingJsonSerializationSection::_propRecursionLimitLimit
0x2cde8  ldstr    aMaxjsonlength// "maxJsonLength"
0x2cded  ldtoken  [mscorlib]System.Int32
0x2cdf2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cdf7  ldc.i4   0x19000
0x2cdfc  box      [mscorlib]System.Int32
0x2ce01  ldnull
0x2ce02  ldc.i4.1
0x2ce03  ldc.i4   0x7FFFFFFF
0x2ce08  newobj   instance void [System.Configuration]System.Configuration.IntegerValidator::.ctor(int32, int32)
0x2ce0d  ldc.i4.0
0x2ce0e  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x2ce13  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.ScriptingJsonSerializationSection::_propMaxJsonLength
0x2ce18  call     class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.ScriptingJsonSerializationSection::BuildProperties()
0x2ce1d  stsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.ScriptingJsonSerializationSection::_properties
0x2ce22  ret
```
