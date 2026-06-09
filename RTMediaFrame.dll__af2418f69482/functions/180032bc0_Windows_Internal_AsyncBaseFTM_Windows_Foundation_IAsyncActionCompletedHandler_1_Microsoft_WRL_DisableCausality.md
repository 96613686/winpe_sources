# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::DisableCausality>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180032bc0`
- end: `0x180032cca`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00UDisableCausality@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180032bc0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032c1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032c1d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180032c4f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180032c4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032c8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032c95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032c8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032c95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032bfa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032bfa`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180032c2d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180032c2d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180032c82`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180032c82`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::DisableCausality>::CheckExecutionEnvironment(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  LPVOID v6; // rcx
  int TokenInformation; // [rsp+30h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-18h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-10h] BYREF
  __int64 v11; // [rsp+48h] [rbp-8h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+28h] BYREF

  ppv = 0;
  v11 = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
    (*(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 4, &v11);
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
0x180032bc0  mov     [rsp-8+arg_0], rbx
0x180032bc5  push    rbp
0x180032bc6  mov     rbp, rsp
0x180032bc9  sub     rsp, 50h
0x180032bcd  mov     [rbp+var_18], 0
0x180032bd5  mov     [rbp+var_8], 0
0x180032bdd  lea     rax, [rbp+var_18]
0x180032be1  mov     [rsp+50h+ppv], rax; ppv
0x180032be6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180032bed  xor     edx, edx; pUnkOuter
0x180032bef  lea     r8d, [rdx+1]; dwClsContext
0x180032bf3  lea     rcx, CLSID_GlobalOptions; rclsid
0x180032bfa  call    cs:__imp_CoCreateInstance
0x180032c00  test    eax, eax
0x180032c02  js      short loc_180032C1D
0x180032c04  mov     rcx, [rbp+var_18]
0x180032c08  mov     rax, [rcx]
0x180032c0b  lea     r8, [rbp+var_8]
0x180032c0f  mov     edx, 4
0x180032c14  mov     rax, [rax+20h]
0x180032c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c1d  call    cs:__imp_GetCurrentProcessId
0x180032c23  mov     r8d, eax; dwProcessId
0x180032c26  xor     edx, edx; bInheritHandle
0x180032c28  mov     ecx, 1000h; dwDesiredAccess
0x180032c2d  call    cs:__imp_OpenProcess
0x180032c33  mov     rbx, rax
0x180032c36  test    rax, rax
0x180032c39  jz      short loc_180032C9C
0x180032c3b  mov     [rbp+TokenHandle], 0
0x180032c43  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180032c47  mov     edx, 8; DesiredAccess
0x180032c4c  mov     rcx, rax; ProcessHandle
0x180032c4f  call    cs:__imp_OpenProcessToken
0x180032c55  test    eax, eax
0x180032c57  jz      short loc_180032C92
0x180032c59  mov     [rbp+ReturnLength], 0
0x180032c60  mov     [rbp+TokenInformation], 0
0x180032c67  lea     rax, [rbp+ReturnLength]
0x180032c6b  mov     [rsp+50h+ppv], rax; ReturnLength
0x180032c70  mov     r9d, 4; TokenInformationLength
0x180032c76  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180032c7a  lea     edx, [r9+19h]; TokenInformationClass
0x180032c7e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180032c82  call    cs:__imp_GetTokenInformation
0x180032c88  mov     rcx, [rbp+TokenHandle]; hObject
0x180032c8c  call    cs:__imp_CloseHandle
0x180032c92  mov     rcx, rbx; hObject
0x180032c95  call    cs:__imp_CloseHandle
0x180032c9b  nop
0x180032c9c  mov     rcx, [rbp+var_18]
0x180032ca0  test    rcx, rcx
0x180032ca3  jz      short loc_180032CBA
0x180032ca5  mov     [rbp+var_18], 0
0x180032cad  mov     rdx, [rcx]
0x180032cb0  mov     rax, [rdx+10h]
0x180032cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cb9  nop
0x180032cba  mov     eax, 1
0x180032cbf  mov     rbx, [rsp+50h+arg_0]
0x180032cc4  add     rsp, 50h
0x180032cc8  pop     rbp
0x180032cc9  retn
```
