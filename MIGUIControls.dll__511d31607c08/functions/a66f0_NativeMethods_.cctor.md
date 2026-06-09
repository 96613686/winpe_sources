# NativeMethods::.cctor

- ea: `0xa66f0`
- end: `0xa6751`
- name: `NativeMethods::.cctor`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0xa6b50`
- `0xa6ba0`
- `0xa6bf0`

## string_xrefs

- `0xa66f0`: `NtDll`
- `0xa6710`: `NtDll`
- `0xa6730`: `NtDll`
- `0xa66f5`: `RtlQueryAllFeatureConfigurations`
- `0xa6715`: `RtlQueryFeatureConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0xa66f0  ldstr    aNtdll// "NtDll"
0xa66f5  ldstr    aRtlqueryallfea// "RtlQueryAllFeatureConfigurations"
0xa66fa  ldnull
0xa66fb  ldftn    valuetype NTSTATUS NativeMethods::RtlQueryAllFeatureConfigurationsFallback(valuetype RTL_FEATURE_CONFIGURATION_TYPE _, [out] valuetype RTL_FEATURE_CHANGE_STAMP& ChangeStamp, native int __, native unsigned int& ___)
0xa6701  newobj   instance void RtlQueryAllFeatureConfigurationsFn::.ctor(object object, native int method)
0xa6706  call     T0x2B000028
0xa670b  stsfld   class RtlQueryAllFeatureConfigurationsFn NativeMethods::RtlQueryAllFeatureConfigurationsFnValue
0xa6710  ldstr    aNtdll// "NtDll"
0xa6715  ldstr    aRtlqueryfeatur// "RtlQueryFeatureConfiguration"
0xa671a  ldnull
0xa671b  ldftn    valuetype NTSTATUS NativeMethods::RtlQueryFeatureConfigurationFallback(valuetype RTL_FEATURE_ID _, valuetype RTL_FEATURE_CONFIGURATION_TYPE __, [out] valuetype RTL_FEATURE_CHANGE_STAMP& ChangeStamp, [out] valuetype RTL_FEATURE_CONFIGURATION& Configuration)
0xa6721  newobj   instance void RtlQueryFeatureConfigurationFn::.ctor(object object, native int method)
0xa6726  call     T0x2B000029
0xa672b  stsfld   class RtlQueryFeatureConfigurationFn NativeMethods::RtlQueryFeatureConfigurationFnValue
0xa6730  ldstr    aNtdll// "NtDll"
0xa6735  ldstr    aNtquerywnfstat// "NtQueryWnfStateData"
0xa673a  ldnull
0xa673b  ldftn    valuetype NTSTATUS NativeMethods::NtQueryWnfStateDataFallback(valuetype WIL_WNF_STATE_NAME& StateName, native int TypeId, native int ExplicitScope, int32& ChangeStamp, native int Buffer, int32& BufferSize)
0xa6741  newobj   instance void NtQueryWnfStateDataFn::.ctor(object object, native int method)
0xa6746  call     T0x2B00002A
0xa674b  stsfld   class NtQueryWnfStateDataFn NativeMethods::NtQueryWnfStateDataFnValue
0xa6750  ret
```
