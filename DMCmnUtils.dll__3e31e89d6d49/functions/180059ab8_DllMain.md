# DllMain

- ea: `0x180059ab8`
- end: `0x180059b96`
- name: `DllMain`
- size: `222`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800070e4`

## callees

- `0x180001160`
- `0x180001224`
- `0x1800592a4`
- `0x180059ab8`
- `0x180059ca8`
- `0x180059cd4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180059ac9`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180059ac9`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rdx
  __int64 v4; // rdx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180102138);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180102298);
      McGenEventRegister_EventRegister(MDM_PUSHROUTER, v3, MDM_PUSHROUTER_Context, MDM_PUSHROUTER_Context);
      McGenEventRegister_EventRegister(
        MDM_ENTERPRISE_DIAGNOSTICS,
        v4,
        MDM_ENTERPRISE_DIAGNOSTICS_Context,
        MDM_ENTERPRISE_DIAGNOSTICS_Context);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::GetImpl'::`2'::impl) )
        TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180102260);
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::GetImpl'::`2'::impl) )
      TraceLoggingUnregister_EventUnregister(&dword_180102260);
    TraceLoggingUnregister_EventUnregister(&dword_180102138);
    TraceLoggingUnregister_EventUnregister(&dword_180102298);
    McGenEventUnregister_EventUnregister(MDM_PUSHROUTER_Context);
    McGenEventUnregister_EventUnregister(MDM_ENTERPRISE_DIAGNOSTICS_Context);
  }
  return 1;
}

```

## disassembly

```asm
0x180059ab8  sub     rsp, 28h
0x180059abc  test    edx, edx
0x180059abe  jz      short loc_180059B3F
0x180059ac0  cmp     edx, 1
0x180059ac3  jnz     loc_180059B8B
0x180059ac9  call    cs:__imp_DisableThreadLibraryCalls
0x180059ad0  nop     dword ptr [rax+rax+00h]
0x180059ad5  lea     rcx, dword_180102138; CallbackContext
0x180059adc  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180059ae1  lea     rcx, dword_180102298; CallbackContext
0x180059ae8  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180059aed  lea     r9, MDM_PUSHROUTER_Context
0x180059af4  lea     r8, MDM_PUSHROUTER_Context
0x180059afb  lea     rcx, MDM_PUSHROUTER
0x180059b02  call    McGenEventRegister_EventRegister
0x180059b07  lea     r9, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180059b0e  lea     r8, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180059b15  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS
0x180059b1c  call    McGenEventRegister_EventRegister
0x180059b21  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::GetImpl(void)'::`2'::impl
0x180059b28  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::__private_IsEnabled(void)
0x180059b2d  test    al, al
0x180059b2f  jz      short loc_180059B8B
0x180059b31  lea     rcx, dword_180102260; CallbackContext
0x180059b38  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180059b3d  jmp     short loc_180059B8B
0x180059b3f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::GetImpl(void)'::`2'::impl
0x180059b46  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::__private_IsEnabled(void)
0x180059b4b  test    al, al
0x180059b4d  jz      short loc_180059B5B
0x180059b4f  lea     rcx, dword_180102260
0x180059b56  call    TraceLoggingUnregister_EventUnregister
0x180059b5b  lea     rcx, dword_180102138
0x180059b62  call    TraceLoggingUnregister_EventUnregister
0x180059b67  lea     rcx, dword_180102298
0x180059b6e  call    TraceLoggingUnregister_EventUnregister
0x180059b73  lea     rcx, MDM_PUSHROUTER_Context
0x180059b7a  call    McGenEventUnregister_EventUnregister
0x180059b7f  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180059b86  call    McGenEventUnregister_EventUnregister
0x180059b8b  mov     eax, 1
0x180059b90  add     rsp, 28h
0x180059b94  retn
```
