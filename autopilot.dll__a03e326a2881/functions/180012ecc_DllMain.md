# DllMain

- ea: `0x180012ecc`
- end: `0x180012f42`
- name: `DllMain`
- size: `118`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004424`

## callees

- `0x180005374`
- `0x180011e10`
- `0x180012ecc`
- `0x180013218`
- `0x180013250`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012edc`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012edc`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      McGenEventRegister_EventRegister();
      if ( wil::details::g_pfnLoggingCallback
        && (void (__fastcall *)(Microsoft::Windows::Autopilot *__hidden, const struct wil::FailureInfo *))wil::details::g_pfnLoggingCallback != Microsoft::Windows::Autopilot::FailureResultLoggingCallback )
      {
        memset_0(v5, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v5, v4);
      }
      wil::details::g_pfnLoggingCallback = (__int64)Microsoft::Windows::Autopilot::FailureResultLoggingCallback;
    }
  }
  else
  {
    wil::details::g_pfnLoggingCallback = 0;
    McGenEventUnregister_EventUnregister(hinstDLL, fdwReason, lpvReserved);
  }
  return 1;
}

```

## disassembly

```asm
0x180012ecc  sub     rsp, 0C8h
0x180012ed3  test    edx, edx
0x180012ed5  jz      short loc_180012F08
0x180012ed7  cmp     edx, 1
0x180012eda  jnz     short loc_180012F18
0x180012edc  call    cs:__imp_DisableThreadLibraryCalls
0x180012ee2  call    McGenEventRegister_EventRegister
0x180012ee7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012eee  lea     rcx, ?FailureResultLoggingCallback@Autopilot@Windows@Microsoft@@YAXAEBUFailureInfo@wil@@@Z; Microsoft::Windows::Autopilot::FailureResultLoggingCallback(wil::FailureInfo const &)
0x180012ef5  test    rax, rax
0x180012ef8  jz      short loc_180012EFF
0x180012efa  cmp     rax, rcx
0x180012efd  jnz     short loc_180012F25
0x180012eff  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x180012f06  jmp     short loc_180012F18
0x180012f08  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, 0
0x180012f13  call    McGenEventUnregister_EventUnregister
0x180012f18  mov     eax, 1
0x180012f1d  add     rsp, 0C8h
0x180012f24  retn
0x180012f25  xor     edx, edx; Val
0x180012f27  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180012f2c  mov     r8d, 98h; Size
0x180012f32  call    memset_0
0x180012f37  lea     rcx, [rsp+0C8h+var_A8]; this
0x180012f3c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
