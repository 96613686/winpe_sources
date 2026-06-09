# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::shutdownAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180075590`
- end: `0x18007569a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?shutdownAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180075590`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007561f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007561f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800755ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800755ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007565c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075665`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007565c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075665`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800755fd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800755fd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180075652`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180075652`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800755ca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800755ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostAPI::shutdownAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180075590  mov     [rsp-8+arg_0], rbx
0x180075595  push    rbp
0x180075596  mov     rbp, rsp
0x180075599  sub     rsp, 50h
0x18007559d  mov     [rbp+var_18], 0
0x1800755a5  mov     [rbp+var_8], 0
0x1800755ad  lea     rax, [rbp+var_18]
0x1800755b1  mov     [rsp+50h+ppv], rax; ppv
0x1800755b6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800755bd  xor     edx, edx; pUnkOuter
0x1800755bf  lea     r8d, [rdx+1]; dwClsContext
0x1800755c3  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800755ca  call    cs:__imp_CoCreateInstance
0x1800755d0  test    eax, eax
0x1800755d2  js      short loc_1800755ED
0x1800755d4  mov     rcx, [rbp+var_18]
0x1800755d8  mov     rax, [rcx]
0x1800755db  lea     r8, [rbp+var_8]
0x1800755df  mov     edx, 4
0x1800755e4  mov     rax, [rax+20h]
0x1800755e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800755ed  call    cs:__imp_GetCurrentProcessId
0x1800755f3  mov     r8d, eax; dwProcessId
0x1800755f6  xor     edx, edx; bInheritHandle
0x1800755f8  mov     ecx, 1000h; dwDesiredAccess
0x1800755fd  call    cs:__imp_OpenProcess
0x180075603  mov     rbx, rax
0x180075606  test    rax, rax
0x180075609  jz      short loc_18007566C
0x18007560b  mov     [rbp+TokenHandle], 0
0x180075613  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180075617  mov     edx, 8; DesiredAccess
0x18007561c  mov     rcx, rax; ProcessHandle
0x18007561f  call    cs:__imp_OpenProcessToken
0x180075625  test    eax, eax
0x180075627  jz      short loc_180075662
0x180075629  mov     [rbp+ReturnLength], 0
0x180075630  mov     [rbp+TokenInformation], 0
0x180075637  lea     rax, [rbp+ReturnLength]
0x18007563b  mov     [rsp+50h+ppv], rax; ReturnLength
0x180075640  mov     r9d, 4; TokenInformationLength
0x180075646  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18007564a  lea     edx, [r9+19h]; TokenInformationClass
0x18007564e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180075652  call    cs:__imp_GetTokenInformation
0x180075658  mov     rcx, [rbp+TokenHandle]; hObject
0x18007565c  call    cs:__imp_CloseHandle
0x180075662  mov     rcx, rbx; hObject
0x180075665  call    cs:__imp_CloseHandle
0x18007566b  nop
0x18007566c  mov     rcx, [rbp+var_18]
0x180075670  test    rcx, rcx
0x180075673  jz      short loc_18007568A
0x180075675  mov     [rbp+var_18], 0
0x18007567d  mov     rdx, [rcx]
0x180075680  mov     rax, [rdx+10h]
0x180075684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075689  nop
0x18007568a  mov     eax, 1
0x18007568f  mov     rbx, [rsp+50h+arg_0]
0x180075694  add     rsp, 50h
0x180075698  pop     rbp
0x180075699  retn
```
