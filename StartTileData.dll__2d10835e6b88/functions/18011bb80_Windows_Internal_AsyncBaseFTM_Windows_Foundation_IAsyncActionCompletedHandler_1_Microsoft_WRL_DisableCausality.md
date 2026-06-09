# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::DisableCausality>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18011bb80`
- end: `0x18011bc8a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00UDisableCausality@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18011bb80`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18011bbdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18011bbdd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18011bc0f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18011bc0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011bc4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011bc55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011bc4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011bc55`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011bbba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011bbba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18011bc42`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18011bc42`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18011bbed`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18011bbed`

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
0x18011bb80  mov     [rsp-8+arg_0], rbx
0x18011bb85  push    rbp
0x18011bb86  mov     rbp, rsp
0x18011bb89  sub     rsp, 50h
0x18011bb8d  mov     [rbp+var_18], 0
0x18011bb95  mov     [rbp+var_8], 0
0x18011bb9d  lea     rax, [rbp+var_18]
0x18011bba1  mov     [rsp+50h+ppv], rax; ppv
0x18011bba6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18011bbad  xor     edx, edx; pUnkOuter
0x18011bbaf  lea     r8d, [rdx+1]; dwClsContext
0x18011bbb3  lea     rcx, CLSID_GlobalOptions; rclsid
0x18011bbba  call    cs:__imp_CoCreateInstance
0x18011bbc0  test    eax, eax
0x18011bbc2  js      short loc_18011BBDD
0x18011bbc4  mov     rcx, [rbp+var_18]
0x18011bbc8  mov     rax, [rcx]
0x18011bbcb  lea     r8, [rbp+var_8]
0x18011bbcf  mov     edx, 4
0x18011bbd4  mov     rax, [rax+20h]
0x18011bbd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bbdd  call    cs:__imp_GetCurrentProcessId
0x18011bbe3  mov     r8d, eax; dwProcessId
0x18011bbe6  xor     edx, edx; bInheritHandle
0x18011bbe8  mov     ecx, 1000h; dwDesiredAccess
0x18011bbed  call    cs:__imp_OpenProcess
0x18011bbf3  mov     rbx, rax
0x18011bbf6  test    rax, rax
0x18011bbf9  jz      short loc_18011BC5C
0x18011bbfb  mov     [rbp+TokenHandle], 0
0x18011bc03  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18011bc07  mov     edx, 8; DesiredAccess
0x18011bc0c  mov     rcx, rax; ProcessHandle
0x18011bc0f  call    cs:__imp_OpenProcessToken
0x18011bc15  test    eax, eax
0x18011bc17  jz      short loc_18011BC52
0x18011bc19  mov     [rbp+ReturnLength], 0
0x18011bc20  mov     [rbp+TokenInformation], 0
0x18011bc27  lea     rax, [rbp+ReturnLength]
0x18011bc2b  mov     [rsp+50h+ppv], rax; ReturnLength
0x18011bc30  mov     r9d, 4; TokenInformationLength
0x18011bc36  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18011bc3a  lea     edx, [r9+19h]; TokenInformationClass
0x18011bc3e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18011bc42  call    cs:__imp_GetTokenInformation
0x18011bc48  mov     rcx, [rbp+TokenHandle]; hObject
0x18011bc4c  call    cs:__imp_CloseHandle
0x18011bc52  mov     rcx, rbx; hObject
0x18011bc55  call    cs:__imp_CloseHandle
0x18011bc5b  nop
0x18011bc5c  mov     rcx, [rbp+var_18]
0x18011bc60  test    rcx, rcx
0x18011bc63  jz      short loc_18011BC7A
0x18011bc65  mov     [rbp+var_18], 0
0x18011bc6d  mov     rdx, [rcx]
0x18011bc70  mov     rax, [rdx+10h]
0x18011bc74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bc79  nop
0x18011bc7a  mov     eax, 1
0x18011bc7f  mov     rbx, [rsp+50h+arg_0]
0x18011bc84  add     rsp, 50h
0x18011bc88  pop     rbp
0x18011bc89  retn
```
