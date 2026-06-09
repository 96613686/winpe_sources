# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStreamReference *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180084dc0`
- end: `0x180084eb5`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStreamReference@Streams@Storage@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `245`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180067008`
- `0x180084dc0`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180084e4f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180084e4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180084e1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180084e1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084e8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084e95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084e8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084e95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180084dfa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180084dfa`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180084e2d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180084e2d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180084e82`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180084e82`

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
0x180084dc0  mov     [rsp-8+arg_0], rbx
0x180084dc5  push    rbp
0x180084dc6  mov     rbp, rsp
0x180084dc9  sub     rsp, 50h
0x180084dcd  mov     [rbp+var_10], 0
0x180084dd5  mov     [rbp+var_8], 0
0x180084ddd  lea     rax, [rbp+var_10]
0x180084de1  mov     [rsp+50h+ppv], rax; ppv
0x180084de6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180084ded  xor     edx, edx; pUnkOuter
0x180084def  lea     r8d, [rdx+1]; dwClsContext
0x180084df3  lea     rcx, CLSID_GlobalOptions; rclsid
0x180084dfa  call    cs:__imp_CoCreateInstance
0x180084e00  test    eax, eax
0x180084e02  js      short loc_180084E1D
0x180084e04  mov     rcx, [rbp+var_10]
0x180084e08  mov     rax, [rcx]
0x180084e0b  lea     r8, [rbp+var_8]
0x180084e0f  mov     edx, 4
0x180084e14  mov     rax, [rax+20h]
0x180084e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084e1d  call    cs:__imp_GetCurrentProcessId
0x180084e23  mov     r8d, eax; dwProcessId
0x180084e26  xor     edx, edx; bInheritHandle
0x180084e28  mov     ecx, 1000h; dwDesiredAccess
0x180084e2d  call    cs:__imp_OpenProcess
0x180084e33  mov     rbx, rax
0x180084e36  test    rax, rax
0x180084e39  jz      short loc_180084E9C
0x180084e3b  mov     [rbp+TokenHandle], 0
0x180084e43  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180084e47  mov     edx, 8; DesiredAccess
0x180084e4c  mov     rcx, rax; ProcessHandle
0x180084e4f  call    cs:__imp_OpenProcessToken
0x180084e55  test    eax, eax
0x180084e57  jz      short loc_180084E92
0x180084e59  mov     [rbp+ReturnLength], 0
0x180084e60  mov     [rbp+TokenInformation], 0
0x180084e67  lea     rax, [rbp+ReturnLength]
0x180084e6b  mov     [rsp+50h+ppv], rax; ReturnLength
0x180084e70  mov     r9d, 4; TokenInformationLength
0x180084e76  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180084e7a  lea     edx, [r9+19h]; TokenInformationClass
0x180084e7e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180084e82  call    cs:__imp_GetTokenInformation
0x180084e88  mov     rcx, [rbp+TokenHandle]; hObject
0x180084e8c  call    cs:__imp_CloseHandle
0x180084e92  mov     rcx, rbx; hObject
0x180084e95  call    cs:__imp_CloseHandle
0x180084e9b  nop
0x180084e9c  lea     rcx, [rbp+var_10]
0x180084ea0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180084ea5  mov     eax, 1
0x180084eaa  mov     rbx, [rsp+50h+arg_0]
0x180084eaf  add     rsp, 50h
0x180084eb3  pop     rbp
0x180084eb4  retn
```
