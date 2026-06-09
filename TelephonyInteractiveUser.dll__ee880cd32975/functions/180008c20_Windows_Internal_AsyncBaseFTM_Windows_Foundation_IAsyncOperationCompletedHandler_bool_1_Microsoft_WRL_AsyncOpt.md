# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180008c20`
- end: `0x180008d42`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `290`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180008c20`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008c68`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008c68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008c8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008c8b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180008cbd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180008cbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d03`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008cf0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008cf0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008c9b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008c9b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  LPVOID v6; // rcx
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-28h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-20h] BYREF
  int TokenInformation; // [rsp+44h] [rbp-1Ch] BYREF
  __int64 v12; // [rsp+48h] [rbp-18h] BYREF

  ppv = 0;
  v12 = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
    (*(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 4, &v12);
  CurrentProcessId = GetCurrentProcessId();
  v4 = OpenProcess(0x1000u, 0, CurrentProcessId);
  v5 = v4;
  if ( v4 )
  {
    TokenHandle = 0;
    if ( OpenProcessToken(v4, 8u, &TokenHandle) )
    {
      ReturnLength = 0;
      TokenInformation = 0;
      GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
      CloseHandle(TokenHandle);
    }
    CloseHandle(v5);
  }
  v6 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return 1;
}

```

## disassembly

```asm
0x180008c20  mov     [rsp-8+arg_0], rbx
0x180008c25  push    rbp
0x180008c26  mov     rbp, rsp
0x180008c29  sub     rsp, 60h
0x180008c2d  mov     rax, cs:__security_cookie
0x180008c34  xor     rax, rsp
0x180008c37  mov     [rbp+var_10], rax
0x180008c3b  xor     edx, edx; pUnkOuter
0x180008c3d  mov     [rbp+var_28], 0
0x180008c45  lea     rax, [rbp+var_28]
0x180008c49  mov     [rbp+var_18], 0
0x180008c51  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180008c58  mov     [rsp+60h+ppv], rax; ppv
0x180008c5d  lea     rcx, CLSID_GlobalOptions; rclsid
0x180008c64  lea     r8d, [rdx+1]; dwClsContext
0x180008c68  call    cs:__imp_CoCreateInstance
0x180008c6e  test    eax, eax
0x180008c70  js      short loc_180008C8B
0x180008c72  mov     rcx, [rbp+var_28]
0x180008c76  lea     r8, [rbp+var_18]
0x180008c7a  mov     edx, 4
0x180008c7f  mov     rax, [rcx]
0x180008c82  mov     rax, [rax+20h]
0x180008c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c8b  call    cs:__imp_GetCurrentProcessId
0x180008c91  xor     edx, edx; bInheritHandle
0x180008c93  mov     ecx, 1000h; dwDesiredAccess
0x180008c98  mov     r8d, eax; dwProcessId
0x180008c9b  call    cs:__imp_OpenProcess
0x180008ca1  mov     rbx, rax
0x180008ca4  test    rax, rax
0x180008ca7  jz      short loc_180008D09
0x180008ca9  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180008cad  mov     [rbp+TokenHandle], 0
0x180008cb5  mov     edx, 8; DesiredAccess
0x180008cba  mov     rcx, rax; ProcessHandle
0x180008cbd  call    cs:__imp_OpenProcessToken
0x180008cc3  test    eax, eax
0x180008cc5  jz      short loc_180008D00
0x180008cc7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180008ccb  lea     rax, [rbp+ReturnLength]
0x180008ccf  mov     r9d, 4; TokenInformationLength
0x180008cd5  mov     [rbp+ReturnLength], 0
0x180008cdc  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180008ce0  mov     [rbp+TokenInformation], 0
0x180008ce7  mov     [rsp+60h+ppv], rax; ReturnLength
0x180008cec  lea     edx, [r9+19h]; TokenInformationClass
0x180008cf0  call    cs:__imp_GetTokenInformation
0x180008cf6  mov     rcx, [rbp+TokenHandle]; hObject
0x180008cfa  call    cs:__imp_CloseHandle
0x180008d00  mov     rcx, rbx; hObject
0x180008d03  call    cs:__imp_CloseHandle
0x180008d09  mov     rcx, [rbp+var_28]
0x180008d0d  test    rcx, rcx
0x180008d10  jz      short loc_180008D26
0x180008d12  mov     [rbp+var_28], 0
0x180008d1a  mov     rdx, [rcx]
0x180008d1d  mov     rax, [rdx+10h]
0x180008d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d26  mov     eax, 1
0x180008d2b  mov     rcx, [rbp+var_10]
0x180008d2f  xor     rcx, rsp; StackCookie
0x180008d32  call    __security_check_cookie
0x180008d37  mov     rbx, [rsp+60h+arg_0]
0x180008d3c  add     rsp, 60h
0x180008d40  pop     rbp
0x180008d41  retn
```
