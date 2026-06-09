# DsAdminProtection_GetHookAPIs

- ea: `0x180055da0`
- end: `0x180055e66`
- name: `DsAdminProtection_GetHookAPIs`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18001bfe8`
- `0x180055da0`
- `0x180055e6c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180055deb`
- `ntdll!RtlAllocateHeap` at `0x180055deb`

## string_xrefs

- `0x180055e04`: `CreateCoreWebView2Environment`
- `0x180055dfd`: `WEBVIEW2LOADER.DLL`
- `0x180055e1d`: `CreateCoreWebView2EnvironmentWithOptions`

## pseudocode

```c
struct tagHOOKAPI *__fastcall DsAdminProtection_GetHookAPIs(__int64 a1, __int64 a2, _DWORD *a3)
{
  struct tagHOOKAPI *result; // rax

  NS_AdminProtection::g_pAPIHooks = 0;
  *a3 = 0;
  if ( !(unsigned int)Feature_ShadowAdminPCATelemetry__private_IsEnabledDeviceUsageNoInline()
    || (unsigned int)DsInitialize() )
  {
    return NS_AdminProtection::g_pAPIHooks;
  }
  result = (struct tagHOOKAPI *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x90u);
  NS_AdminProtection::g_pAPIHooks = result;
  if ( result )
  {
    *(_QWORD *)result = "WEBVIEW2LOADER.DLL";
    *((_QWORD *)result + 1) = "CreateCoreWebView2Environment";
    *((_QWORD *)result + 2) = NS_AdminProtection::APIHook_CreateCoreWebView2Environment;
    *((_QWORD *)result + 7) = "CreateCoreWebView2EnvironmentWithOptions";
    *((_QWORD *)result + 8) = NS_AdminProtection::APIHook_CreateCoreWebView2EnvironmentWithOptions;
    *((_QWORD *)result + 13) = "GetAvailableCoreWebView2BrowserVersionString";
    *((_QWORD *)result + 14) = NS_AdminProtection::APIHook_GetAvailableCoreWebView2BrowserVersionString;
    *((_QWORD *)result + 6) = "WEBVIEW2LOADER.DLL";
    *((_QWORD *)result + 12) = "WEBVIEW2LOADER.DLL";
    *a3 = 3;
  }
  return result;
}

```

## disassembly

```asm
0x180055da0  push    rbx
0x180055da2  sub     rsp, 20h
0x180055da6  mov     rbx, r8
0x180055da9  mov     cs:?g_pAPIHooks@NS_AdminProtection@@3PEAUtagHOOKAPI@@EA, 0; tagHOOKAPI * NS_AdminProtection::g_pAPIHooks
0x180055db4  mov     dword ptr [r8], 0
0x180055dbb  call    Feature_ShadowAdminPCATelemetry__private_IsEnabledDeviceUsageNoInline
0x180055dc0  test    eax, eax
0x180055dc2  jz      loc_180055E59
0x180055dc8  call    DsInitialize
0x180055dcd  test    eax, eax
0x180055dcf  jnz     loc_180055E59
0x180055dd5  mov     rcx, gs:60h
0x180055dde  lea     edx, [rax+8]; Flags
0x180055de1  mov     r8d, 90h; Size
0x180055de7  mov     rcx, [rcx+30h]; HeapHandle
0x180055deb  call    cs:__imp_RtlAllocateHeap
0x180055df1  mov     cs:?g_pAPIHooks@NS_AdminProtection@@3PEAUtagHOOKAPI@@EA, rax; tagHOOKAPI * NS_AdminProtection::g_pAPIHooks
0x180055df8  test    rax, rax
0x180055dfb  jz      short loc_180055E60
0x180055dfd  lea     rdx, aWebview2loader; "WEBVIEW2LOADER.DLL"
0x180055e04  lea     rcx, aCreatecorewebv; "CreateCoreWebView2Environment"
0x180055e0b  mov     [rax], rdx
0x180055e0e  mov     [rax+8], rcx
0x180055e12  lea     rcx, ?APIHook_CreateCoreWebView2Environment@NS_AdminProtection@@YAJPEBG0PEAUICoreWebView2EnvironmentOptions@@PEAUICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler@@@Z; NS_AdminProtection::APIHook_CreateCoreWebView2Environment(ushort const *,ushort const *,ICoreWebView2EnvironmentOptions *,ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler *)
0x180055e19  mov     [rax+10h], rcx
0x180055e1d  lea     rcx, aCreatecorewebv_0; "CreateCoreWebView2EnvironmentWithOption"...
0x180055e24  mov     [rax+38h], rcx
0x180055e28  lea     rcx, ?APIHook_CreateCoreWebView2EnvironmentWithOptions@NS_AdminProtection@@YAJPEBG0PEAUICoreWebView2EnvironmentOptions@@PEAUICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler@@@Z; NS_AdminProtection::APIHook_CreateCoreWebView2EnvironmentWithOptions(ushort const *,ushort const *,ICoreWebView2EnvironmentOptions *,ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler *)
0x180055e2f  mov     [rax+40h], rcx
0x180055e33  lea     rcx, aGetavailableco; "GetAvailableCoreWebView2BrowserVersionS"...
0x180055e3a  mov     [rax+68h], rcx
0x180055e3e  lea     rcx, ?APIHook_GetAvailableCoreWebView2BrowserVersionString@NS_AdminProtection@@YAJPEBGPEAPEAG@Z; NS_AdminProtection::APIHook_GetAvailableCoreWebView2BrowserVersionString(ushort const *,ushort * *)
0x180055e45  mov     [rax+70h], rcx
0x180055e49  mov     [rax+30h], rdx
0x180055e4d  mov     [rax+60h], rdx
0x180055e51  mov     dword ptr [rbx], 3
0x180055e57  jmp     short loc_180055E60
0x180055e59  mov     rax, cs:?g_pAPIHooks@NS_AdminProtection@@3PEAUtagHOOKAPI@@EA; tagHOOKAPI * NS_AdminProtection::g_pAPIHooks
0x180055e60  add     rsp, 20h
0x180055e64  pop     rbx
0x180055e65  retn
```
