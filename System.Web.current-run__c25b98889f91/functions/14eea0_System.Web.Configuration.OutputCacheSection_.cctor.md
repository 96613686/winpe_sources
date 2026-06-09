# System.Web.Configuration.OutputCacheSection::.cctor

- ea: `0x14eea0`
- end: `0x14eff4`
- name: `System.Web.Configuration.OutputCacheSection::.cctor`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x158570`

## string_xrefs

- `0x14eee0`: `sendCacheControlHeader`
- `0x14eea0`: `enableOutputCache`
- `0x14eec0`: `enableFragmentCache`
- `0x14ef20`: `enableKernelCacheForVaryByStar`

## pseudocode

```c

```

## disassembly

```asm
0x14eea0  ldstr    aEnableoutputca// "enableOutputCache"
0x14eea5  ldtoken  [mscorlib]System.Boolean
0x14eeaa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14eeaf  ldc.i4.1
0x14eeb0  box      [mscorlib]System.Boolean
0x14eeb5  ldc.i4.0
0x14eeb6  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14eebb  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propEnableOutputCache
0x14eec0  ldstr    aEnablefragment// "enableFragmentCache"
0x14eec5  ldtoken  [mscorlib]System.Boolean
0x14eeca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14eecf  ldc.i4.1
0x14eed0  box      [mscorlib]System.Boolean
0x14eed5  ldc.i4.0
0x14eed6  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14eedb  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propEnableFragmentCache
0x14eee0  ldstr    aSendcachecontr// "sendCacheControlHeader"
0x14eee5  ldtoken  [mscorlib]System.Boolean
0x14eeea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14eeef  ldc.i4.1
0x14eef0  box      [mscorlib]System.Boolean
0x14eef5  ldc.i4.0
0x14eef6  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14eefb  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propSendCacheControlHeader
0x14ef00  ldstr    aOmitvarystar// "omitVaryStar"
0x14ef05  ldtoken  [mscorlib]System.Boolean
0x14ef0a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14ef0f  ldc.i4.0
0x14ef10  box      [mscorlib]System.Boolean
0x14ef15  ldc.i4.0
0x14ef16  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14ef1b  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propOmitVaryStar
0x14ef20  ldstr    aEnablekernelca// "enableKernelCacheForVaryByStar"
0x14ef25  ldtoken  [mscorlib]System.Boolean
0x14ef2a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14ef2f  ldc.i4.0
0x14ef30  box      [mscorlib]System.Boolean
0x14ef35  ldc.i4.0
0x14ef36  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14ef3b  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propEnableKernelCacheForVaryByStar
0x14ef40  ldstr    aDefaultprovide// "defaultProvider"
0x14ef45  ldtoken  [mscorlib]System.String
0x14ef4a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14ef4f  ldstr    aAspnetinternal// "AspNetInternalProvider"
0x14ef54  ldnull
0x14ef55  call     class [System.Configuration]System.Configuration.ConfigurationValidatorBase System.Web.Configuration.StdValidatorsAndConverters::get_NonEmptyStringValidator()
0x14ef5a  ldc.i4.0
0x14ef5b  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14ef60  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propDefaultProviderName
0x14ef65  ldstr    aProviders// "providers"
0x14ef6a  ldtoken  [System.Configuration]System.Configuration.ProviderSettingsCollection
0x14ef6f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14ef74  ldnull
0x14ef75  ldc.i4.0
0x14ef76  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14ef7b  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propProviders
0x14ef80  newobj   instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::.ctor()
0x14ef85  stsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.OutputCacheSection::_properties
0x14ef8a  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.OutputCacheSection::_properties
0x14ef8f  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propEnableOutputCache
0x14ef94  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14ef99  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.OutputCacheSection::_properties
0x14ef9e  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propEnableFragmentCache
0x14efa3  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14efa8  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.OutputCacheSection::_properties
0x14efad  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propSendCacheControlHeader
0x14efb2  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14efb7  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.OutputCacheSection::_properties
0x14efbc  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propOmitVaryStar
0x14efc1  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14efc6  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.OutputCacheSection::_properties
0x14efcb  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propEnableKernelCacheForVaryByStar
0x14efd0  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14efd5  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.OutputCacheSection::_properties
0x14efda  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propDefaultProviderName
0x14efdf  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14efe4  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.OutputCacheSection::_properties
0x14efe9  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.OutputCacheSection::_propProviders
0x14efee  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14eff3  ret
```
