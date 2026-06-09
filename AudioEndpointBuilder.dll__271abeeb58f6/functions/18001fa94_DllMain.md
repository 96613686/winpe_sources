# DllMain

- ea: `0x18001fa94`
- end: `0x18001fbb4`
- name: `DllMain`
- size: `288`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003e794`

## callees

- `0x18001fa94`
- `0x18003f7a4`
- `0x1800427b0`
- `0x18005d12c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001faab`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001faab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fab1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fab1`
- `ntdll!EtwRegisterTraceGuidsW` at `0x18001fb1b`
- `ntdll!EtwRegisterTraceGuidsW` at `0x18001fb1b`
- `ntdll!EtwUnregisterTraceGuids` at `0x18001fb6f`
- `ntdll!EtwUnregisterTraceGuids` at `0x18001fb6f`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  _QWORD v5[2]; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v6[168]; // [rsp+50h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    g_hInstance = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
    v5[1] = 0;
    g_hHeap = GetProcessHeap();
    v5[0] = &GUID_NULL;
    g_fEventTracingEnabled = ((__int64 (__fastcall *)(unsigned int (__fastcall *)(enum WMIDPREQUESTCODE, void *, unsigned int *, void *), _QWORD, __int64 *, __int64, _QWORD *, _QWORD, _QWORD, __int64 *))EtwRegisterTraceGuidsW)(
                               AeWmiCallback,
                               0,
                               AEWMIGUID,
                               1,
                               v5,
                               0,
                               0,
                               &qword_180069018) == 0;
    if ( wil::details::g_pfnTelemetryCallback
      && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != AudioEndpointBuilderTelemetryProvider::FallbackTelemetryCallback )
    {
      memset_0(v6, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v6, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64)AudioEndpointBuilderTelemetryProvider::FallbackTelemetryCallback;
  }
  else if ( !fdwReason && !lpvReserved )
  {
    if ( g_fEventTracingEnabled )
    {
      EtwUnregisterTraceGuids(qword_180069018);
      qword_180069018 = 0;
      g_hAEWMITraceHandle = 0;
    }
    WppCleanupUm(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x18001fa94  sub     rsp, 0F8h
0x18001fa9b  cmp     edx, 1
0x18001fa9e  jnz     loc_18001FB56
0x18001faa4  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInstance
0x18001faab  call    cs:__imp_DisableThreadLibraryCalls
0x18001fab1  call    cs:__imp_GetProcessHeap
0x18001fab7  mov     r9d, 1
0x18001fabd  mov     [rsp+0F8h+var_B0], 0
0x18001fac6  mov     cs:g_hHeap, rax
0x18001facd  lea     r8, AEWMIGUID
0x18001fad4  lea     rax, GUID_NULL
0x18001fadb  mov     cs:?g_fEventTracingEnabled@@3HA, 1; int g_fEventTracingEnabled
0x18001fae5  mov     [rsp+0F8h+var_B8], rax
0x18001faea  lea     rcx, ?AeWmiCallback@@YAKW4WMIDPREQUESTCODE@@PEAXPEAK1@Z; AeWmiCallback(WMIDPREQUESTCODE,void *,ulong *,void *)
0x18001faf1  lea     rax, qword_180069018
0x18001faf8  xor     edx, edx
0x18001fafa  mov     [rsp+0F8h+var_C0], rax
0x18001faff  lea     rax, [rsp+0F8h+var_B8]
0x18001fb04  mov     [rsp+0F8h+var_C8], 0
0x18001fb0d  mov     [rsp+0F8h+var_D0], 0
0x18001fb16  mov     [rsp+0F8h+var_D8], rax
0x18001fb1b  call    cs:__imp_EtwRegisterTraceGuidsW
0x18001fb21  test    eax, eax
0x18001fb23  jz      short loc_18001FB2F
0x18001fb25  mov     cs:?g_fEventTracingEnabled@@3HA, 0; int g_fEventTracingEnabled
0x18001fb2f  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001fb36  lea     rcx, ?FallbackTelemetryCallback@AudioEndpointBuilderTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z; AudioEndpointBuilderTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18001fb3d  test    rax, rax
0x18001fb40  jnz     short loc_18001FB92
0x18001fb42  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18001fb49  mov     eax, 1
0x18001fb4e  add     rsp, 0F8h
0x18001fb55  retn
0x18001fb56  test    edx, edx
0x18001fb58  jnz     short loc_18001FB49
0x18001fb5a  test    r8, r8
0x18001fb5d  jnz     short loc_18001FB49
0x18001fb5f  cmp     cs:?g_fEventTracingEnabled@@3HA, r8d; int g_fEventTracingEnabled
0x18001fb66  jz      short loc_18001FB8B
0x18001fb68  mov     rcx, cs:qword_180069018
0x18001fb6f  call    cs:__imp_EtwUnregisterTraceGuids
0x18001fb75  mov     cs:qword_180069018, 0
0x18001fb80  mov     cs:?g_hAEWMITraceHandle@@3_KA, 0; unsigned __int64 g_hAEWMITraceHandle
0x18001fb8b  call    WppCleanupUm
0x18001fb90  jmp     short loc_18001FB49
0x18001fb92  cmp     rax, rcx
0x18001fb95  jz      short loc_18001FB42
0x18001fb97  xor     edx, edx; Val
0x18001fb99  lea     rcx, [rsp+0F8h+var_A8]; void *
0x18001fb9e  mov     r8d, 98h; Size
0x18001fba4  call    memset_0
0x18001fba9  lea     rcx, [rsp+0F8h+var_A8]; this
0x18001fbae  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
