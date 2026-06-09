# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::Pickers::UpdateFilesResult *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1802c15e0`
- end: `0x1802c1714`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUpdateFilesResult@Pickers@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `308`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1802c15e0`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802c1681`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802c1681`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1802c1643`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1802c1643`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802c16ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802c16d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802c16ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802c16d9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802c16ba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802c16ba`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802c1659`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802c1659`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802c161a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802c161a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::Pickers::UpdateFilesResult *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x1802c15e0  mov     [rsp-8+arg_0], rbx
0x1802c15e5  push    rbp
0x1802c15e6  mov     rbp, rsp
0x1802c15e9  sub     rsp, 50h
0x1802c15ed  mov     [rbp+var_18], 0
0x1802c15f5  mov     [rbp+var_8], 0
0x1802c15fd  lea     rax, [rbp+var_18]
0x1802c1601  mov     [rsp+50h+ppv], rax; ppv
0x1802c1606  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1802c160d  xor     edx, edx; pUnkOuter
0x1802c160f  lea     r8d, [rdx+1]; dwClsContext
0x1802c1613  lea     rcx, CLSID_GlobalOptions; rclsid
0x1802c161a  call    cs:__imp_CoCreateInstance
0x1802c1621  nop     dword ptr [rax+rax+00h]
0x1802c1626  test    eax, eax
0x1802c1628  js      short loc_1802C1643
0x1802c162a  mov     rcx, [rbp+var_18]
0x1802c162e  mov     rax, [rcx]
0x1802c1631  lea     r8, [rbp+var_8]
0x1802c1635  mov     edx, 4
0x1802c163a  mov     rax, [rax+20h]
0x1802c163e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c1643  call    cs:__imp_GetCurrentProcessId
0x1802c164a  nop     dword ptr [rax+rax+00h]
0x1802c164f  mov     r8d, eax; dwProcessId
0x1802c1652  xor     edx, edx; bInheritHandle
0x1802c1654  mov     ecx, 1000h; dwDesiredAccess
0x1802c1659  call    cs:__imp_OpenProcess
0x1802c1660  nop     dword ptr [rax+rax+00h]
0x1802c1665  mov     rbx, rax
0x1802c1668  test    rax, rax
0x1802c166b  jz      short loc_1802C16E6
0x1802c166d  mov     [rbp+TokenHandle], 0
0x1802c1675  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1802c1679  mov     edx, 8; DesiredAccess
0x1802c167e  mov     rcx, rax; ProcessHandle
0x1802c1681  call    cs:__imp_OpenProcessToken
0x1802c1688  nop     dword ptr [rax+rax+00h]
0x1802c168d  test    eax, eax
0x1802c168f  jz      short loc_1802C16D6
0x1802c1691  mov     [rbp+ReturnLength], 0
0x1802c1698  mov     [rbp+TokenInformation], 0
0x1802c169f  lea     rax, [rbp+ReturnLength]
0x1802c16a3  mov     [rsp+50h+ppv], rax; ReturnLength
0x1802c16a8  mov     r9d, 4; TokenInformationLength
0x1802c16ae  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1802c16b2  lea     edx, [r9+19h]; TokenInformationClass
0x1802c16b6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1802c16ba  call    cs:__imp_GetTokenInformation
0x1802c16c1  nop     dword ptr [rax+rax+00h]
0x1802c16c6  mov     rcx, [rbp+TokenHandle]; hObject
0x1802c16ca  call    cs:__imp_CloseHandle
0x1802c16d1  nop     dword ptr [rax+rax+00h]
0x1802c16d6  mov     rcx, rbx; hObject
0x1802c16d9  call    cs:__imp_CloseHandle
0x1802c16e0  nop     dword ptr [rax+rax+00h]
0x1802c16e5  nop
0x1802c16e6  mov     rcx, [rbp+var_18]
0x1802c16ea  test    rcx, rcx
0x1802c16ed  jz      short loc_1802C1703
0x1802c16ef  mov     [rbp+var_18], 0
0x1802c16f7  mov     rdx, [rcx]
0x1802c16fa  mov     rax, [rdx+10h]
0x1802c16fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c1703  mov     eax, 1
0x1802c1708  mov     rbx, [rsp+50h+arg_0]
0x1802c170d  add     rsp, 50h
0x1802c1711  pop     rbp
0x1802c1712  retn
```
