# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18000a280`
- end: `0x18000a38a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a280`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a2dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a2dd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a30f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a30f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a34c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a34c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a355`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a2ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a2ba`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000a2ed`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000a2ed`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a342`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a342`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
  void *TokenHandle; // [rsp+40h] [rbp-10h] BYREF
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
0x18000a280  mov     [rsp-8+arg_0], rbx
0x18000a285  push    rbp
0x18000a286  mov     rbp, rsp
0x18000a289  sub     rsp, 50h
0x18000a28d  mov     [rbp+var_18], 0
0x18000a295  mov     [rbp+var_8], 0
0x18000a29d  lea     rax, [rbp+var_18]
0x18000a2a1  mov     [rsp+50h+ppv], rax; ppv
0x18000a2a6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18000a2ad  xor     edx, edx; pUnkOuter
0x18000a2af  lea     r8d, [rdx+1]; dwClsContext
0x18000a2b3  lea     rcx, CLSID_GlobalOptions; rclsid
0x18000a2ba  call    cs:__imp_CoCreateInstance
0x18000a2c0  test    eax, eax
0x18000a2c2  js      short loc_18000A2DD
0x18000a2c4  mov     rcx, [rbp+var_18]
0x18000a2c8  mov     rax, [rcx]
0x18000a2cb  lea     r8, [rbp+var_8]
0x18000a2cf  mov     edx, 4
0x18000a2d4  mov     rax, [rax+20h]
0x18000a2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2dd  call    cs:__imp_GetCurrentProcessId
0x18000a2e3  mov     r8d, eax; dwProcessId
0x18000a2e6  xor     edx, edx; bInheritHandle
0x18000a2e8  mov     ecx, 1000h; dwDesiredAccess
0x18000a2ed  call    cs:__imp_OpenProcess
0x18000a2f3  mov     rbx, rax
0x18000a2f6  test    rax, rax
0x18000a2f9  jz      short loc_18000A35C
0x18000a2fb  mov     [rbp+TokenHandle], 0
0x18000a303  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000a307  mov     edx, 8; DesiredAccess
0x18000a30c  mov     rcx, rax; ProcessHandle
0x18000a30f  call    cs:__imp_OpenProcessToken
0x18000a315  test    eax, eax
0x18000a317  jz      short loc_18000A352
0x18000a319  mov     [rbp+ReturnLength], 0
0x18000a320  mov     [rbp+TokenInformation], 0
0x18000a327  lea     rax, [rbp+ReturnLength]
0x18000a32b  mov     [rsp+50h+ppv], rax; ReturnLength
0x18000a330  mov     r9d, 4; TokenInformationLength
0x18000a336  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000a33a  lea     edx, [r9+19h]; TokenInformationClass
0x18000a33e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000a342  call    cs:__imp_GetTokenInformation
0x18000a348  mov     rcx, [rbp+TokenHandle]; hObject
0x18000a34c  call    cs:__imp_CloseHandle
0x18000a352  mov     rcx, rbx; hObject
0x18000a355  call    cs:__imp_CloseHandle
0x18000a35b  nop
0x18000a35c  mov     rcx, [rbp+var_18]
0x18000a360  test    rcx, rcx
0x18000a363  jz      short loc_18000A37A
0x18000a365  mov     [rbp+var_18], 0
0x18000a36d  mov     rdx, [rcx]
0x18000a370  mov     rax, [rdx+10h]
0x18000a374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a379  nop
0x18000a37a  mov     eax, 1
0x18000a37f  mov     rbx, [rsp+50h+arg_0]
0x18000a384  add     rsp, 50h
0x18000a388  pop     rbp
0x18000a389  retn
```
