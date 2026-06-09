# DllMain

- ea: `0x180015ce4`
- end: `0x180015de4`
- name: `DllMain`
- size: `256`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180002524`

## callees

- `0x180001008`
- `0x18000316c`
- `0x180011a10`
- `0x180015924`
- `0x180015ce4`
- `0x18002c938`
- `0x18002cc80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180015cf5`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180015cf5`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180015d7a`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180015d94`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180015d7a`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180015d94`
- `ntdll!EtwEventUnregister` at `0x180015dae`
- `ntdll!EtwEventUnregister` at `0x180015dae`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  REGHANDLE v6; // rcx
  REGHANDLE v7; // rcx
  __int64 v8; // rcx
  const struct wil::FailureInfo *v10; // rdx
  _BYTE v11[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    LoggingOnProcessAttach(hinstDLL);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AICSettings>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_AICSettings>::GetImpl'::`2'::impl,
                            v4,
                            v5) )
    {
      TraceLoggingRegister_EventRegister_EventSetInformation(&dword_1800651E8);
      TraceLoggingRegister_EventRegister_EventSetInformation(&dword_1800651B0);
    }
    if ( wil::details::g_pfnLoggingCallback
      && (char *)wil::details::g_pfnLoggingCallback != (char *)lambda_2d5a9ce2c51b82703091e323603be588_::_lambda_invoker_cdecl_ )
    {
      memset_0(v11, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v11, v10);
    }
    wil::details::g_pfnLoggingCallback = (__int64 (__fastcall *)(_QWORD))lambda_2d5a9ce2c51b82703091e323603be588_::_lambda_invoker_cdecl_;
  }
  else if ( !fdwReason )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AICSettings>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_AICSettings>::GetImpl'::`2'::impl,
                            fdwReason,
                            lpvReserved) )
    {
      v6 = RegHandle;
      dword_1800651E8 = 0;
      RegHandle = 0;
      EventUnregister(v6);
      v7 = qword_1800651D0;
      dword_1800651B0 = 0;
      qword_1800651D0 = 0;
      EventUnregister(v7);
    }
    v8 = qword_180065240;
    dword_180065220 = 0;
    qword_180065240 = 0;
    EtwEventUnregister(v8);
    McGenEventUnregister_EtwEventUnregister();
  }
  return 1;
}

```

## disassembly

```asm
0x180015ce4  push    rbx
0x180015ce6  sub     rsp, 0C0h
0x180015ced  mov     rbx, rcx
0x180015cf0  cmp     edx, 1
0x180015cf3  jnz     short loc_180015D50
0x180015cf5  call    cs:__imp_DisableThreadLibraryCalls
0x180015cfb  mov     rcx, rbx; hModule
0x180015cfe  call    ?LoggingOnProcessAttach@@YAXPEAUHINSTANCE__@@@Z; LoggingOnProcessAttach(HINSTANCE__ *)
0x180015d03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AICSettings@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AICSettings@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AICSettings> `wil::Feature<__WilFeatureTraits_Feature_AICSettings>::GetImpl(void)'::`2'::impl
0x180015d0a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AICSettings@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AICSettings>::__private_IsEnabled(wil::ReportingKind)
0x180015d0f  test    al, al
0x180015d11  jz      short loc_180015D2B
0x180015d13  lea     rcx, dword_1800651E8; CallbackContext
0x180015d1a  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x180015d1f  lea     rcx, dword_1800651B0; CallbackContext
0x180015d26  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x180015d2b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015d32  lea     rcx, _lambda_2d5a9ce2c51b82703091e323603be588____lambda_invoker_cdecl_
0x180015d39  test    rax, rax
0x180015d3c  jz      short loc_180015D47
0x180015d3e  cmp     rax, rcx
0x180015d41  jnz     loc_180015DC7
0x180015d47  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x180015d4e  jmp     short loc_180015DB9
0x180015d50  xor     ebx, ebx
0x180015d52  test    edx, edx
0x180015d54  jnz     short loc_180015DB9
0x180015d56  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AICSettings@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AICSettings@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AICSettings> `wil::Feature<__WilFeatureTraits_Feature_AICSettings>::GetImpl(void)'::`2'::impl
0x180015d5d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AICSettings@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AICSettings>::__private_IsEnabled(wil::ReportingKind)
0x180015d62  test    al, al
0x180015d64  jz      short loc_180015D9A
0x180015d66  mov     rcx, cs:RegHandle; RegHandle
0x180015d6d  mov     cs:dword_1800651E8, ebx
0x180015d73  mov     cs:RegHandle, rbx
0x180015d7a  call    cs:__imp_EventUnregister
0x180015d80  mov     rcx, cs:qword_1800651D0; RegHandle
0x180015d87  mov     cs:dword_1800651B0, ebx
0x180015d8d  mov     cs:qword_1800651D0, rbx
0x180015d94  call    cs:__imp_EventUnregister
0x180015d9a  mov     rcx, cs:qword_180065240
0x180015da1  mov     cs:dword_180065220, ebx
0x180015da7  mov     cs:qword_180065240, rbx
0x180015dae  call    cs:__imp_EtwEventUnregister
0x180015db4  call    McGenEventUnregister_EtwEventUnregister
0x180015db9  mov     eax, 1
0x180015dbe  add     rsp, 0C0h
0x180015dc5  pop     rbx
0x180015dc6  retn
0x180015dc7  xor     edx, edx; Val
0x180015dc9  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180015dce  mov     r8d, 98h; Size
0x180015dd4  call    memset_0
0x180015dd9  lea     rcx, [rsp+0C8h+var_A8]; this
0x180015dde  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
