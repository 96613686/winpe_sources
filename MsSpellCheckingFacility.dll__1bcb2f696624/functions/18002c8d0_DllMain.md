# DllMain

- ea: `0x18002c8d0`
- end: `0x18002ca12`
- name: `DllMain`
- size: `322`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180061184`

## callees

- `0x18002c8d0`
- `0x180062314`
- `0x180069e70`
- `0x18006c8cc`
- `0x18006c8f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18002c90b`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18002c90b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c9ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c9ef`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // ebx
  __int64 v5; // rdx
  signed int v6; // eax
  __int64 v7; // rdx
  bool v8; // sf
  const struct wil::FailureInfo *v9; // rdx
  const struct wil::FailureInfo *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r8
  _BYTE v13[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason != 1 )
  {
    if ( !fdwReason )
    {
      if ( Windows::Globalization::Spelling::g_hActivationMutex )
        CloseHandle(Windows::Globalization::Spelling::g_hActivationMutex);
      McGenEventUnregister_EventUnregister(
        WINDOWS_SPELLCHECKER_ETW_PROVIDER_Context,
        *(_QWORD *)&fdwReason,
        lpvReserved);
      McGenEventUnregister_EventUnregister(SPELL_CHECKING_ETW_PROVIDER_Context, v11, v12);
    }
    return 1;
  }
  DisableThreadLibraryCalls(hinstDLL);
  v3 = 0;
  Windows::Globalization::Spelling::g_hActivationMutex = 0;
  v6 = McGenEventRegister_EventRegister(
         SPELL_CHECKING_ETW_PROVIDER,
         v5,
         SPELL_CHECKING_ETW_PROVIDER_Context,
         SPELL_CHECKING_ETW_PROVIDER_Context);
  v8 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    v8 = v6 < 0;
  }
  if ( !v8 )
  {
    v6 = McGenEventRegister_EventRegister(
           WINDOWS_SPELLCHECKER_ETW_PROVIDER,
           v7,
           WINDOWS_SPELLCHECKER_ETW_PROVIDER_Context,
           WINDOWS_SPELLCHECKER_ETW_PROVIDER_Context);
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
  }
  if ( wil::details::g_pfnTelemetryCallback
    && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != SpellingTelemetry::FallbackTelemetryCallback )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v9);
  }
  wil::details::g_pfnTelemetryCallback = (__int64)SpellingTelemetry::FallbackTelemetryCallback;
  if ( wil::g_pfnResultFromCaughtException
    && (void (__fastcall __noreturn *)())wil::g_pfnResultFromCaughtException != lambda_906adaf3f77e93a07a1eb1f1aa265d4c_::_lambda_invoker_cdecl_ )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v10);
  }
  wil::g_pfnResultFromCaughtException = (__int64)lambda_906adaf3f77e93a07a1eb1f1aa265d4c_::_lambda_invoker_cdecl_;
  if ( v6 >= 0 && !ATL::CAtlBaseModule::m_bInitFailed )
    return 1;
  return v3;
}

```

## disassembly

```asm
0x18002c8d0  push    rbx
0x18002c8d2  sub     rsp, 0C0h
0x18002c8d9  cmp     edx, 1
0x18002c8dc  jz      short loc_18002C90B
0x18002c8de  test    edx, edx
0x18002c8e0  jz      loc_18002C9E3
0x18002c8e6  mov     ebx, 1
0x18002c8eb  mov     eax, ebx
0x18002c8ed  add     rsp, 0C0h
0x18002c8f4  pop     rbx
0x18002c8f5  retn
0x18002c8f6  mov     cs:?g_pfnResultFromCaughtException@wil@@3P6AJX_EEA, rdx
0x18002c8fd  test    eax, eax
0x18002c8ff  js      short loc_18002C8EB
0x18002c901  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, bl; bool ATL::CAtlBaseModule::m_bInitFailed
0x18002c907  jz      short loc_18002C8E6
0x18002c909  jmp     short loc_18002C8EB
0x18002c90b  call    cs:__imp_DisableThreadLibraryCalls
0x18002c911  xor     ebx, ebx
0x18002c913  lea     r9, SPELL_CHECKING_ETW_PROVIDER_Context
0x18002c91a  lea     r8, SPELL_CHECKING_ETW_PROVIDER_Context
0x18002c921  mov     cs:?g_hActivationMutex@Spelling@Globalization@Windows@@3PEAXEA, rbx; void * Windows::Globalization::Spelling::g_hActivationMutex
0x18002c928  lea     rcx, SPELL_CHECKING_ETW_PROVIDER
0x18002c92f  call    McGenEventRegister_EventRegister
0x18002c934  test    eax, eax
0x18002c936  jle     short loc_18002C942
0x18002c938  movzx   eax, ax
0x18002c93b  or      eax, 80070000h
0x18002c940  test    eax, eax
0x18002c942  js      short loc_18002C96A
0x18002c944  lea     r9, WINDOWS_SPELLCHECKER_ETW_PROVIDER_Context
0x18002c94b  lea     r8, WINDOWS_SPELLCHECKER_ETW_PROVIDER_Context
0x18002c952  lea     rcx, WINDOWS_SPELLCHECKER_ETW_PROVIDER
0x18002c959  call    McGenEventRegister_EventRegister
0x18002c95e  test    eax, eax
0x18002c960  jle     short loc_18002C96A
0x18002c962  movzx   eax, ax
0x18002c965  or      eax, 80070000h
0x18002c96a  mov     rcx, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18002c971  lea     rdx, ?FallbackTelemetryCallback@SpellingTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; SpellingTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18002c978  test    rcx, rcx
0x18002c97b  jz      short loc_18002C99F
0x18002c97d  cmp     rcx, rdx
0x18002c980  jz      short loc_18002C99F
0x18002c982  xor     edx, edx; Val
0x18002c984  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18002c989  mov     r8d, 98h; Size
0x18002c98f  call    memset_0
0x18002c994  lea     rcx, [rsp+0C8h+var_A8]; this
0x18002c999  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002c99f  mov     rcx, cs:?g_pfnResultFromCaughtException@wil@@3P6AJX_EEA
0x18002c9a6  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rdx
0x18002c9ad  lea     rdx, _lambda_906adaf3f77e93a07a1eb1f1aa265d4c____lambda_invoker_cdecl_
0x18002c9b4  test    rcx, rcx
0x18002c9b7  jz      loc_18002C8F6
0x18002c9bd  cmp     rcx, rdx
0x18002c9c0  jz      loc_18002C8F6
0x18002c9c6  xor     edx, edx; Val
0x18002c9c8  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18002c9cd  mov     r8d, 98h; Size
0x18002c9d3  call    memset_0
0x18002c9d8  lea     rcx, [rsp+0C8h+var_A8]; this
0x18002c9dd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002c9e3  mov     rcx, cs:?g_hActivationMutex@Spelling@Globalization@Windows@@3PEAXEA; hObject
0x18002c9ea  test    rcx, rcx
0x18002c9ed  jz      short loc_18002C9F5
0x18002c9ef  call    cs:__imp_CloseHandle
0x18002c9f5  lea     rcx, WINDOWS_SPELLCHECKER_ETW_PROVIDER_Context
0x18002c9fc  call    McGenEventUnregister_EventUnregister
0x18002ca01  lea     rcx, SPELL_CHECKING_ETW_PROVIDER_Context
0x18002ca08  call    McGenEventUnregister_EventUnregister
0x18002ca0d  jmp     loc_18002C8E6
```
