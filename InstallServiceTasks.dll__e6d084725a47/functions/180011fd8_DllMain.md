# DllMain

- ea: `0x180011fd8`
- end: `0x180012081`
- name: `DllMain`
- size: `169`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800032c4`

## callees

- `0x180001010`
- `0x1800010c0`
- `0x180003fe4`
- `0x18000a398`
- `0x180011fd8`
- `0x1800130b8`
- `0x180013934`
- `0x1800347f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180011fed`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180011fed`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const unsigned __int16 *v4; // rdx
  struct _GUID *v5; // r8
  bool v6; // r9
  const struct wil::FailureInfo *v8; // rdx
  _BYTE v9[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      LoggingOnProcessAttach(hinstDLL);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&qword_1800630A0);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800630D8);
      if ( wil::details::g_pfnLoggingCallback
        && (char *)wil::details::g_pfnLoggingCallback != (char *)lambda_86b93cd9fdf736389aa9fb0c88a76295_::_lambda_invoker_cdecl_ )
      {
        memset_0(v9, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v9, v8);
      }
      wil::details::g_pfnLoggingCallback = (__int64 (__fastcall *)(_QWORD))lambda_86b93cd9fdf736389aa9fb0c88a76295_::_lambda_invoker_cdecl_;
      WinStoreAuth::AuthenticationInternal::SetMsaClientId(
        (WinStoreAuth::AuthenticationInternal *)lambda_86b93cd9fdf736389aa9fb0c88a76295_::_lambda_invoker_cdecl_,
        v4,
        v5,
        v6);
    }
  }
  else
  {
    McGenEventUnregister_EventUnregister(hinstDLL, fdwReason, lpvReserved);
    TraceLoggingUnregister_EventUnregister(&dword_1800630D8);
    TraceLoggingUnregister_EventUnregister(&qword_1800630A0);
  }
  return 1;
}

```

## disassembly

```asm
0x180011fd8  push    rbx
0x180011fda  sub     rsp, 0C0h
0x180011fe1  mov     rbx, rcx
0x180011fe4  test    edx, edx
0x180011fe6  jz      short loc_180012039
0x180011fe8  cmp     edx, 1
0x180011feb  jnz     short loc_180012056
0x180011fed  call    cs:__imp_DisableThreadLibraryCalls
0x180011ff3  mov     rcx, rbx; hModule
0x180011ff6  call    ?LoggingOnProcessAttach@@YAXPEAUHINSTANCE__@@@Z; LoggingOnProcessAttach(HINSTANCE__ *)
0x180011ffb  lea     rcx, qword_1800630A0; CallbackContext
0x180012002  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180012007  lea     rcx, dword_1800630D8; CallbackContext
0x18001200e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180012013  lea     rcx, _lambda_86b93cd9fdf736389aa9fb0c88a76295____lambda_invoker_cdecl_; this
0x18001201a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012021  test    rax, rax
0x180012024  jz      short loc_18001202B
0x180012026  cmp     rax, rcx
0x180012029  jnz     short loc_180012064
0x18001202b  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x180012032  call    ?SetMsaClientId@AuthenticationInternal@WinStoreAuth@@YAXPEBGU_GUID@@_N@Z; WinStoreAuth::AuthenticationInternal::SetMsaClientId(ushort const *,_GUID,bool)
0x180012037  jmp     short loc_180012056
0x180012039  call    McGenEventUnregister_EventUnregister
0x18001203e  lea     rcx, dword_1800630D8
0x180012045  call    TraceLoggingUnregister_EventUnregister
0x18001204a  lea     rcx, qword_1800630A0
0x180012051  call    TraceLoggingUnregister_EventUnregister
0x180012056  mov     eax, 1
0x18001205b  add     rsp, 0C0h
0x180012062  pop     rbx
0x180012063  retn
0x180012064  xor     edx, edx; Val
0x180012066  mov     r8d, 98h; Size
0x18001206c  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180012071  call    memset_0
0x180012076  lea     rcx, [rsp+0C8h+var_A8]; this
0x18001207b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
