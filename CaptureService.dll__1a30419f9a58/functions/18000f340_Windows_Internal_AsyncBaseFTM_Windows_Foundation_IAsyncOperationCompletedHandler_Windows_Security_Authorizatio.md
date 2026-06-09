# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18000f340`
- end: `0x18000f435`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `245`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007630`
- `0x18000f340`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f37a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f37a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f39d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f39d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000f3cf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000f3cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f40c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f415`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f40c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f415`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f402`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f402`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f3ad`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f3ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return 1;
}

```

## disassembly

```asm
0x18000f340  mov     [rsp-8+arg_0], rbx
0x18000f345  push    rbp
0x18000f346  mov     rbp, rsp
0x18000f349  sub     rsp, 50h
0x18000f34d  mov     [rbp+var_10], 0
0x18000f355  mov     [rbp+var_8], 0
0x18000f35d  lea     rax, [rbp+var_10]
0x18000f361  mov     [rsp+50h+ppv], rax; ppv
0x18000f366  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18000f36d  xor     edx, edx; pUnkOuter
0x18000f36f  lea     r8d, [rdx+1]; dwClsContext
0x18000f373  lea     rcx, CLSID_GlobalOptions; rclsid
0x18000f37a  call    cs:__imp_CoCreateInstance
0x18000f380  test    eax, eax
0x18000f382  js      short loc_18000F39D
0x18000f384  mov     rcx, [rbp+var_10]
0x18000f388  mov     rax, [rcx]
0x18000f38b  lea     r8, [rbp+var_8]
0x18000f38f  mov     edx, 4
0x18000f394  mov     rax, [rax+20h]
0x18000f398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f39d  call    cs:__imp_GetCurrentProcessId
0x18000f3a3  mov     r8d, eax; dwProcessId
0x18000f3a6  xor     edx, edx; bInheritHandle
0x18000f3a8  mov     ecx, 1000h; dwDesiredAccess
0x18000f3ad  call    cs:__imp_OpenProcess
0x18000f3b3  mov     rbx, rax
0x18000f3b6  test    rax, rax
0x18000f3b9  jz      short loc_18000F41C
0x18000f3bb  mov     [rbp+TokenHandle], 0
0x18000f3c3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000f3c7  mov     edx, 8; DesiredAccess
0x18000f3cc  mov     rcx, rax; ProcessHandle
0x18000f3cf  call    cs:__imp_OpenProcessToken
0x18000f3d5  test    eax, eax
0x18000f3d7  jz      short loc_18000F412
0x18000f3d9  mov     [rbp+ReturnLength], 0
0x18000f3e0  mov     [rbp+TokenInformation], 0
0x18000f3e7  lea     rax, [rbp+ReturnLength]
0x18000f3eb  mov     [rsp+50h+ppv], rax; ReturnLength
0x18000f3f0  mov     r9d, 4; TokenInformationLength
0x18000f3f6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000f3fa  lea     edx, [r9+19h]; TokenInformationClass
0x18000f3fe  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000f402  call    cs:__imp_GetTokenInformation
0x18000f408  mov     rcx, [rbp+TokenHandle]; hObject
0x18000f40c  call    cs:__imp_CloseHandle
0x18000f412  mov     rcx, rbx; hObject
0x18000f415  call    cs:__imp_CloseHandle
0x18000f41b  nop
0x18000f41c  lea     rcx, [rbp+var_10]
0x18000f420  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f425  mov     eax, 1
0x18000f42a  mov     rbx, [rsp+50h+arg_0]
0x18000f42f  add     rsp, 50h
0x18000f433  pop     rbp
0x18000f434  retn
```
