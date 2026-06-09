# Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::CheckExecutionEnvironment

- ea: `0x180008af0`
- end: `0x180008c12`
- name: `Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::CheckExecutionEnvironment`
- size: `290`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180008af0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008b38`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008b38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008b5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008b5b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180008b8d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180008b8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008bca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008bd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008bca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008bd3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008bc0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008bc0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008b6b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008b6b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::CheckExecutionEnvironment(
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
0x180008af0  mov     [rsp-8+arg_0], rbx
0x180008af5  push    rbp
0x180008af6  mov     rbp, rsp
0x180008af9  sub     rsp, 60h
0x180008afd  mov     rax, cs:__security_cookie
0x180008b04  xor     rax, rsp
0x180008b07  mov     [rbp+var_10], rax
0x180008b0b  xor     edx, edx; pUnkOuter
0x180008b0d  mov     [rbp+var_28], 0
0x180008b15  lea     rax, [rbp+var_28]
0x180008b19  mov     [rbp+var_18], 0
0x180008b21  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180008b28  mov     [rsp+60h+ppv], rax; ppv
0x180008b2d  lea     rcx, CLSID_GlobalOptions; rclsid
0x180008b34  lea     r8d, [rdx+1]; dwClsContext
0x180008b38  call    cs:__imp_CoCreateInstance
0x180008b3e  test    eax, eax
0x180008b40  js      short loc_180008B5B
0x180008b42  mov     rcx, [rbp+var_28]
0x180008b46  lea     r8, [rbp+var_18]
0x180008b4a  mov     edx, 4
0x180008b4f  mov     rax, [rcx]
0x180008b52  mov     rax, [rax+20h]
0x180008b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b5b  call    cs:__imp_GetCurrentProcessId
0x180008b61  xor     edx, edx; bInheritHandle
0x180008b63  mov     ecx, 1000h; dwDesiredAccess
0x180008b68  mov     r8d, eax; dwProcessId
0x180008b6b  call    cs:__imp_OpenProcess
0x180008b71  mov     rbx, rax
0x180008b74  test    rax, rax
0x180008b77  jz      short loc_180008BD9
0x180008b79  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180008b7d  mov     [rbp+TokenHandle], 0
0x180008b85  mov     edx, 8; DesiredAccess
0x180008b8a  mov     rcx, rax; ProcessHandle
0x180008b8d  call    cs:__imp_OpenProcessToken
0x180008b93  test    eax, eax
0x180008b95  jz      short loc_180008BD0
0x180008b97  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180008b9b  lea     rax, [rbp+ReturnLength]
0x180008b9f  mov     r9d, 4; TokenInformationLength
0x180008ba5  mov     [rbp+ReturnLength], 0
0x180008bac  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180008bb0  mov     [rbp+TokenInformation], 0
0x180008bb7  mov     [rsp+60h+ppv], rax; ReturnLength
0x180008bbc  lea     edx, [r9+19h]; TokenInformationClass
0x180008bc0  call    cs:__imp_GetTokenInformation
0x180008bc6  mov     rcx, [rbp+TokenHandle]; hObject
0x180008bca  call    cs:__imp_CloseHandle
0x180008bd0  mov     rcx, rbx; hObject
0x180008bd3  call    cs:__imp_CloseHandle
0x180008bd9  mov     rcx, [rbp+var_28]
0x180008bdd  test    rcx, rcx
0x180008be0  jz      short loc_180008BF6
0x180008be2  mov     [rbp+var_28], 0
0x180008bea  mov     rdx, [rcx]
0x180008bed  mov     rax, [rdx+10h]
0x180008bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bf6  mov     eax, 1
0x180008bfb  mov     rcx, [rbp+var_10]
0x180008bff  xor     rcx, rsp; StackCookie
0x180008c02  call    __security_check_cookie
0x180008c07  mov     rbx, [rsp+60h+arg_0]
0x180008c0c  add     rsp, 60h
0x180008c10  pop     rbp
0x180008c11  retn
```
