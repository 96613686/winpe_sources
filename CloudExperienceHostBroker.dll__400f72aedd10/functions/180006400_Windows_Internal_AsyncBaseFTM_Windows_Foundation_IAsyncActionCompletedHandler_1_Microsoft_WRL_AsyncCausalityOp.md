# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::SyncEngine::WriteTargetingIdentifierAsyncActionActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180006400`
- end: `0x18000650a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?WriteTargetingIdentifierAsyncActionActionName@SyncEngine@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006400`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000645d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000645d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000648f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000648f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064d5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000646d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000646d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000643a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000643a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800064c2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800064c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::SyncEngine::WriteTargetingIdentifierAsyncActionActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180006400  mov     [rsp-8+arg_0], rbx
0x180006405  push    rbp
0x180006406  mov     rbp, rsp
0x180006409  sub     rsp, 50h
0x18000640d  mov     [rbp+var_18], 0
0x180006415  mov     [rbp+var_8], 0
0x18000641d  lea     rax, [rbp+var_18]
0x180006421  mov     [rsp+50h+ppv], rax; ppv
0x180006426  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18000642d  xor     edx, edx; pUnkOuter
0x18000642f  lea     r8d, [rdx+1]; dwClsContext
0x180006433  lea     rcx, CLSID_GlobalOptions; rclsid
0x18000643a  call    cs:__imp_CoCreateInstance
0x180006440  test    eax, eax
0x180006442  js      short loc_18000645D
0x180006444  mov     rcx, [rbp+var_18]
0x180006448  mov     rax, [rcx]
0x18000644b  lea     r8, [rbp+var_8]
0x18000644f  mov     edx, 4
0x180006454  mov     rax, [rax+20h]
0x180006458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000645d  call    cs:__imp_GetCurrentProcessId
0x180006463  mov     r8d, eax; dwProcessId
0x180006466  xor     edx, edx; bInheritHandle
0x180006468  mov     ecx, 1000h; dwDesiredAccess
0x18000646d  call    cs:__imp_OpenProcess
0x180006473  mov     rbx, rax
0x180006476  test    rax, rax
0x180006479  jz      short loc_1800064DC
0x18000647b  mov     [rbp+TokenHandle], 0
0x180006483  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180006487  mov     edx, 8; DesiredAccess
0x18000648c  mov     rcx, rax; ProcessHandle
0x18000648f  call    cs:__imp_OpenProcessToken
0x180006495  test    eax, eax
0x180006497  jz      short loc_1800064D2
0x180006499  mov     [rbp+ReturnLength], 0
0x1800064a0  mov     [rbp+TokenInformation], 0
0x1800064a7  lea     rax, [rbp+ReturnLength]
0x1800064ab  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800064b0  mov     r9d, 4; TokenInformationLength
0x1800064b6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800064ba  lea     edx, [r9+19h]; TokenInformationClass
0x1800064be  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800064c2  call    cs:__imp_GetTokenInformation
0x1800064c8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800064cc  call    cs:__imp_CloseHandle
0x1800064d2  mov     rcx, rbx; hObject
0x1800064d5  call    cs:__imp_CloseHandle
0x1800064db  nop
0x1800064dc  mov     rcx, [rbp+var_18]
0x1800064e0  test    rcx, rcx
0x1800064e3  jz      short loc_1800064FA
0x1800064e5  mov     [rbp+var_18], 0
0x1800064ed  mov     rdx, [rcx]
0x1800064f0  mov     rax, [rdx+10h]
0x1800064f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064f9  nop
0x1800064fa  mov     eax, 1
0x1800064ff  mov     rbx, [rsp+50h+arg_0]
0x180006504  add     rsp, 50h
0x180006508  pop     rbp
0x180006509  retn
```
