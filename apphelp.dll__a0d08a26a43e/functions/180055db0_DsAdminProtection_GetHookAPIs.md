# DsAdminProtection_GetHookAPIs

- ea: `0x180055db0`
- end: `0x180055e76`
- name: `DsAdminProtection_GetHookAPIs`
- size: `198`
- prototype: `struct tagHOOKAPI *__fastcall(__int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18001bfe8`
- `0x180055db0`
- `0x180055e7c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180055dfb`
- `ntdll!RtlAllocateHeap` at `0x180055dfb`

## string_xrefs

- `0x180055e0d`: `WEBVIEW2LOADER.DLL`
- `0x180055e2d`: `CreateCoreWebView2EnvironmentWithOptions`
- `0x180055e14`: `CreateCoreWebView2Environment`

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
0x180055db0  push    rbx
0x180055db2  sub     rsp, 20h
0x180055db6  mov     rbx, r8
0x180055db9  mov     cs:?g_pAPIHooks@NS_AdminProtection@@3PEAUtagHOOKAPI@@EA, 0; tagHOOKAPI * NS_AdminProtection::g_pAPIHooks
0x180055dc4  mov     dword ptr [r8], 0
0x180055dcb  call    Feature_ShadowAdminPCATelemetry__private_IsEnabledDeviceUsageNoInline
0x180055dd0  test    eax, eax
0x180055dd2  jz      loc_180055E69
0x180055dd8  call    DsInitialize
0x180055ddd  test    eax, eax
0x180055ddf  jnz     loc_180055E69
0x180055de5  mov     rcx, gs:60h
0x180055dee  lea     edx, [rax+8]; Flags
0x180055df1  mov     r8d, 90h; Size
0x180055df7  mov     rcx, [rcx+30h]; HeapHandle
0x180055dfb  call    cs:__imp_RtlAllocateHeap
0x180055e01  mov     cs:?g_pAPIHooks@NS_AdminProtection@@3PEAUtagHOOKAPI@@EA, rax; tagHOOKAPI * NS_AdminProtection::g_pAPIHooks
0x180055e08  test    rax, rax
0x180055e0b  jz      short loc_180055E70
0x180055e0d  lea     rdx, aWebview2loader; "WEBVIEW2LOADER.DLL"
0x180055e14  lea     rcx, aCreatecorewebv; "CreateCoreWebView2Environment"
0x180055e1b  mov     [rax], rdx
0x180055e1e  mov     [rax+8], rcx
0x180055e22  lea     rcx, ?APIHook_CreateCoreWebView2Environment@NS_AdminProtection@@YAJPEBG0PEAUICoreWebView2EnvironmentOptions@@PEAUICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler@@@Z; NS_AdminProtection::APIHook_CreateCoreWebView2Environment(ushort const *,ushort const *,ICoreWebView2EnvironmentOptions *,ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler *)
0x180055e29  mov     [rax+10h], rcx
0x180055e2d  lea     rcx, aCreatecorewebv_0; "CreateCoreWebView2EnvironmentWithOption"...
0x180055e34  mov     [rax+38h], rcx
0x180055e38  lea     rcx, ?APIHook_CreateCoreWebView2EnvironmentWithOptions@NS_AdminProtection@@YAJPEBG0PEAUICoreWebView2EnvironmentOptions@@PEAUICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler@@@Z; NS_AdminProtection::APIHook_CreateCoreWebView2EnvironmentWithOptions(ushort const *,ushort const *,ICoreWebView2EnvironmentOptions *,ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler *)
0x180055e3f  mov     [rax+40h], rcx
0x180055e43  lea     rcx, aGetavailableco; "GetAvailableCoreWebView2BrowserVersionS"...
0x180055e4a  mov     [rax+68h], rcx
0x180055e4e  lea     rcx, ?APIHook_GetAvailableCoreWebView2BrowserVersionString@NS_AdminProtection@@YAJPEBGPEAPEAG@Z; NS_AdminProtection::APIHook_GetAvailableCoreWebView2BrowserVersionString(ushort const *,ushort * *)
0x180055e55  mov     [rax+70h], rcx
0x180055e59  mov     [rax+30h], rdx
0x180055e5d  mov     [rax+60h], rdx
0x180055e61  mov     dword ptr [rbx], 3
0x180055e67  jmp     short loc_180055E70
0x180055e69  mov     rax, cs:?g_pAPIHooks@NS_AdminProtection@@3PEAUtagHOOKAPI@@EA; tagHOOKAPI * NS_AdminProtection::g_pAPIHooks
0x180055e70  add     rsp, 20h
0x180055e74  pop     rbx
0x180055e75  retn
```
