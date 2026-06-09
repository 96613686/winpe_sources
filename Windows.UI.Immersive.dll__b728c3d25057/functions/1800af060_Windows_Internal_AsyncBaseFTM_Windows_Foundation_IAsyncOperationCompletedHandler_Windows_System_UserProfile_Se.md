# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::UserProfile::SetAccountPictureResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800af060`
- end: `0x1800af169`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4SetAccountPictureResult@UserProfile@System@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `265`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800af060`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800af0ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800af0ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800af0bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800af0bd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800af0cd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800af0cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af12c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af135`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af12c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800af135`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800af122`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800af122`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800af09a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800af09a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::UserProfile::SetAccountPictureResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x1800af060  mov     [rsp-8+arg_0], rbx
0x1800af065  push    rbp
0x1800af066  mov     rbp, rsp
0x1800af069  sub     rsp, 50h
0x1800af06d  mov     [rbp+var_18], 0
0x1800af075  mov     [rbp+var_8], 0
0x1800af07d  lea     rax, [rbp+var_18]
0x1800af081  mov     [rsp+50h+ppv], rax; ppv
0x1800af086  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800af08d  xor     edx, edx; pUnkOuter
0x1800af08f  lea     r8d, [rdx+1]; dwClsContext
0x1800af093  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800af09a  call    cs:__imp_CoCreateInstance
0x1800af0a0  test    eax, eax
0x1800af0a2  js      short loc_1800AF0BD
0x1800af0a4  mov     rcx, [rbp+var_18]
0x1800af0a8  mov     rax, [rcx]
0x1800af0ab  lea     r8, [rbp+var_8]
0x1800af0af  mov     edx, 4
0x1800af0b4  mov     rax, [rax+20h]
0x1800af0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af0bd  call    cs:__imp_GetCurrentProcessId
0x1800af0c3  mov     r8d, eax; dwProcessId
0x1800af0c6  xor     edx, edx; bInheritHandle
0x1800af0c8  mov     ecx, 1000h; dwDesiredAccess
0x1800af0cd  call    cs:__imp_OpenProcess
0x1800af0d3  mov     rbx, rax
0x1800af0d6  test    rax, rax
0x1800af0d9  jz      short loc_1800AF13C
0x1800af0db  mov     [rbp+TokenHandle], 0
0x1800af0e3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800af0e7  mov     edx, 8; DesiredAccess
0x1800af0ec  mov     rcx, rax; ProcessHandle
0x1800af0ef  call    cs:__imp_OpenProcessToken
0x1800af0f5  test    eax, eax
0x1800af0f7  jz      short loc_1800AF132
0x1800af0f9  mov     [rbp+ReturnLength], 0
0x1800af100  mov     [rbp+TokenInformation], 0
0x1800af107  lea     rax, [rbp+ReturnLength]
0x1800af10b  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800af110  mov     r9d, 4; TokenInformationLength
0x1800af116  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800af11a  lea     edx, [r9+19h]; TokenInformationClass
0x1800af11e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800af122  call    cs:__imp_GetTokenInformation
0x1800af128  mov     rcx, [rbp+TokenHandle]; hObject
0x1800af12c  call    cs:__imp_CloseHandle
0x1800af132  mov     rcx, rbx; hObject
0x1800af135  call    cs:__imp_CloseHandle
0x1800af13b  nop
0x1800af13c  mov     rcx, [rbp+var_18]
0x1800af140  test    rcx, rcx
0x1800af143  jz      short loc_1800AF159
0x1800af145  mov     [rbp+var_18], 0
0x1800af14d  mov     rdx, [rcx]
0x1800af150  mov     rax, [rdx+10h]
0x1800af154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af159  mov     eax, 1
0x1800af15e  mov     rbx, [rsp+50h+arg_0]
0x1800af163  add     rsp, 50h
0x1800af167  pop     rbp
0x1800af168  retn
```
