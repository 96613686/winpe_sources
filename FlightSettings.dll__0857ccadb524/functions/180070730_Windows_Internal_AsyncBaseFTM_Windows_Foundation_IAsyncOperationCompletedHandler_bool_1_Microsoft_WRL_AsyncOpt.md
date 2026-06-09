# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180070730`
- end: `0x180070825`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `245`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b19c`
- `0x180070730`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800707bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800707bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007078d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007078d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800707fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070805`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800707fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070805`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007079d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007079d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800707f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800707f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007076a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007076a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
  return 1;
}

```

## disassembly

```asm
0x180070730  mov     [rsp-8+arg_0], rbx
0x180070735  push    rbp
0x180070736  mov     rbp, rsp
0x180070739  sub     rsp, 50h
0x18007073d  mov     [rbp+var_10], 0
0x180070745  mov     [rbp+var_8], 0
0x18007074d  lea     rax, [rbp+var_10]
0x180070751  mov     [rsp+50h+ppv], rax; ppv
0x180070756  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18007075d  xor     edx, edx; pUnkOuter
0x18007075f  lea     r8d, [rdx+1]; dwClsContext
0x180070763  lea     rcx, CLSID_GlobalOptions; rclsid
0x18007076a  call    cs:__imp_CoCreateInstance
0x180070770  test    eax, eax
0x180070772  js      short loc_18007078D
0x180070774  mov     rcx, [rbp+var_10]
0x180070778  mov     rax, [rcx]
0x18007077b  lea     r8, [rbp+var_8]
0x18007077f  mov     edx, 4
0x180070784  mov     rax, [rax+20h]
0x180070788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007078d  call    cs:__imp_GetCurrentProcessId
0x180070793  mov     r8d, eax; dwProcessId
0x180070796  xor     edx, edx; bInheritHandle
0x180070798  mov     ecx, 1000h; dwDesiredAccess
0x18007079d  call    cs:__imp_OpenProcess
0x1800707a3  mov     rbx, rax
0x1800707a6  test    rax, rax
0x1800707a9  jz      short loc_18007080C
0x1800707ab  mov     [rbp+TokenHandle], 0
0x1800707b3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800707b7  mov     edx, 8; DesiredAccess
0x1800707bc  mov     rcx, rax; ProcessHandle
0x1800707bf  call    cs:__imp_OpenProcessToken
0x1800707c5  test    eax, eax
0x1800707c7  jz      short loc_180070802
0x1800707c9  mov     [rbp+ReturnLength], 0
0x1800707d0  mov     [rbp+TokenInformation], 0
0x1800707d7  lea     rax, [rbp+ReturnLength]
0x1800707db  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800707e0  mov     r9d, 4; TokenInformationLength
0x1800707e6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800707ea  lea     edx, [r9+19h]; TokenInformationClass
0x1800707ee  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800707f2  call    cs:__imp_GetTokenInformation
0x1800707f8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800707fc  call    cs:__imp_CloseHandle
0x180070802  mov     rcx, rbx; hObject
0x180070805  call    cs:__imp_CloseHandle
0x18007080b  nop
0x18007080c  lea     rcx, [rbp+var_10]
0x180070810  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180070815  mov     eax, 1
0x18007081a  mov     rbx, [rsp+50h+arg_0]
0x18007081f  add     rsp, 50h
0x180070823  pop     rbp
0x180070824  retn
```
