# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1801883b0`
- end: `0x1801884e3`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `307`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1801883b0`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180188451`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180188451`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180188413`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180188413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018849a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801884a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018849a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801884a9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18018848a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18018848a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180188429`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180188429`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801883ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801883ea`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x1801883b0  mov     [rsp-8+arg_0], rbx
0x1801883b5  push    rbp
0x1801883b6  mov     rbp, rsp
0x1801883b9  sub     rsp, 50h
0x1801883bd  xor     edx, edx; pUnkOuter
0x1801883bf  mov     [rbp+var_18], 0
0x1801883c7  lea     rax, [rbp+var_18]
0x1801883cb  mov     [rbp+var_8], 0
0x1801883d3  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1801883da  mov     [rsp+50h+ppv], rax; ppv
0x1801883df  lea     rcx, CLSID_GlobalOptions; rclsid
0x1801883e6  lea     r8d, [rdx+1]; dwClsContext
0x1801883ea  call    cs:__imp_CoCreateInstance
0x1801883f1  nop     dword ptr [rax+rax+00h]
0x1801883f6  test    eax, eax
0x1801883f8  js      short loc_180188413
0x1801883fa  mov     rcx, [rbp+var_18]
0x1801883fe  lea     r8, [rbp+var_8]
0x180188402  mov     edx, 4
0x180188407  mov     rax, [rcx]
0x18018840a  mov     rax, [rax+20h]
0x18018840e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188413  call    cs:__imp_GetCurrentProcessId
0x18018841a  nop     dword ptr [rax+rax+00h]
0x18018841f  xor     edx, edx; bInheritHandle
0x180188421  mov     ecx, 1000h; dwDesiredAccess
0x180188426  mov     r8d, eax; dwProcessId
0x180188429  call    cs:__imp_OpenProcess
0x180188430  nop     dword ptr [rax+rax+00h]
0x180188435  mov     rbx, rax
0x180188438  test    rax, rax
0x18018843b  jz      short loc_1801884B5
0x18018843d  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180188441  mov     [rbp+TokenHandle], 0
0x180188449  mov     edx, 8; DesiredAccess
0x18018844e  mov     rcx, rax; ProcessHandle
0x180188451  call    cs:__imp_OpenProcessToken
0x180188458  nop     dword ptr [rax+rax+00h]
0x18018845d  test    eax, eax
0x18018845f  jz      short loc_1801884A6
0x180188461  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180188465  lea     rax, [rbp+ReturnLength]
0x180188469  mov     r9d, 4; TokenInformationLength
0x18018846f  mov     [rbp+ReturnLength], 0
0x180188476  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18018847a  mov     [rbp+TokenInformation], 0
0x180188481  mov     [rsp+50h+ppv], rax; ReturnLength
0x180188486  lea     edx, [r9+19h]; TokenInformationClass
0x18018848a  call    cs:__imp_GetTokenInformation
0x180188491  nop     dword ptr [rax+rax+00h]
0x180188496  mov     rcx, [rbp+TokenHandle]; hObject
0x18018849a  call    cs:__imp_CloseHandle
0x1801884a1  nop     dword ptr [rax+rax+00h]
0x1801884a6  mov     rcx, rbx; hObject
0x1801884a9  call    cs:__imp_CloseHandle
0x1801884b0  nop     dword ptr [rax+rax+00h]
0x1801884b5  mov     rcx, [rbp+var_18]
0x1801884b9  test    rcx, rcx
0x1801884bc  jz      short loc_1801884D2
0x1801884be  mov     [rbp+var_18], 0
0x1801884c6  mov     rdx, [rcx]
0x1801884c9  mov     rax, [rdx+10h]
0x1801884cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801884d2  mov     rbx, [rsp+50h+arg_0]
0x1801884d7  mov     eax, 1
0x1801884dc  add     rsp, 50h
0x1801884e0  pop     rbp
0x1801884e1  retn
```
