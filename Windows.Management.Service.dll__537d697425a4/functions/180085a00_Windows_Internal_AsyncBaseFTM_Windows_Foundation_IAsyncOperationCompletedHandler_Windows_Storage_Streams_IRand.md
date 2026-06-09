# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStreamReference *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180085a00`
- end: `0x180085b20`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStreamReference@Streams@Storage@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `288`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180067398`
- `0x180085a00`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180085aa1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180085aa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180085a63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180085a63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085aea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085af9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085aea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085af9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180085a3a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180085a3a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180085a79`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180085a79`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180085ada`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180085ada`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStreamReference *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  int TokenInformation; // [rsp+30h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-10h] BYREF
  __int64 v10; // [rsp+48h] [rbp-8h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+28h] BYREF

  ppv = 0;
  v10 = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
    (*(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 4, &v10);
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
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  return 1;
}

```

## disassembly

```asm
0x180085a00  mov     [rsp-8+arg_0], rbx
0x180085a05  push    rbp
0x180085a06  mov     rbp, rsp
0x180085a09  sub     rsp, 50h
0x180085a0d  mov     [rbp+var_10], 0
0x180085a15  mov     [rbp+var_8], 0
0x180085a1d  lea     rax, [rbp+var_10]
0x180085a21  mov     [rsp+50h+ppv], rax; ppv
0x180085a26  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180085a2d  xor     edx, edx; pUnkOuter
0x180085a2f  lea     r8d, [rdx+1]; dwClsContext
0x180085a33  lea     rcx, CLSID_GlobalOptions; rclsid
0x180085a3a  call    cs:__imp_CoCreateInstance
0x180085a41  nop     dword ptr [rax+rax+00h]
0x180085a46  test    eax, eax
0x180085a48  js      short loc_180085A63
0x180085a4a  mov     rcx, [rbp+var_10]
0x180085a4e  mov     rax, [rcx]
0x180085a51  lea     r8, [rbp+var_8]
0x180085a55  mov     edx, 4
0x180085a5a  mov     rax, [rax+20h]
0x180085a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085a63  call    cs:__imp_GetCurrentProcessId
0x180085a6a  nop     dword ptr [rax+rax+00h]
0x180085a6f  mov     r8d, eax; dwProcessId
0x180085a72  xor     edx, edx; bInheritHandle
0x180085a74  mov     ecx, 1000h; dwDesiredAccess
0x180085a79  call    cs:__imp_OpenProcess
0x180085a80  nop     dword ptr [rax+rax+00h]
0x180085a85  mov     rbx, rax
0x180085a88  test    rax, rax
0x180085a8b  jz      short loc_180085B06
0x180085a8d  mov     [rbp+TokenHandle], 0
0x180085a95  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180085a99  mov     edx, 8; DesiredAccess
0x180085a9e  mov     rcx, rax; ProcessHandle
0x180085aa1  call    cs:__imp_OpenProcessToken
0x180085aa8  nop     dword ptr [rax+rax+00h]
0x180085aad  test    eax, eax
0x180085aaf  jz      short loc_180085AF6
0x180085ab1  mov     [rbp+ReturnLength], 0
0x180085ab8  mov     [rbp+TokenInformation], 0
0x180085abf  lea     rax, [rbp+ReturnLength]
0x180085ac3  mov     [rsp+50h+ppv], rax; ReturnLength
0x180085ac8  mov     r9d, 4; TokenInformationLength
0x180085ace  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180085ad2  lea     edx, [r9+19h]; TokenInformationClass
0x180085ad6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180085ada  call    cs:__imp_GetTokenInformation
0x180085ae1  nop     dword ptr [rax+rax+00h]
0x180085ae6  mov     rcx, [rbp+TokenHandle]; hObject
0x180085aea  call    cs:__imp_CloseHandle
0x180085af1  nop     dword ptr [rax+rax+00h]
0x180085af6  mov     rcx, rbx; hObject
0x180085af9  call    cs:__imp_CloseHandle
0x180085b00  nop     dword ptr [rax+rax+00h]
0x180085b05  nop
0x180085b06  lea     rcx, [rbp+var_10]
0x180085b0a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085b0f  mov     eax, 1
0x180085b14  mov     rbx, [rsp+50h+arg_0]
0x180085b19  add     rsp, 50h
0x180085b1d  pop     rbp
0x180085b1e  retn
```
