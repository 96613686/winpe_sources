# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180024e10`
- end: `0x180024f1a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180024e10`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024e9f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024e9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024e6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024e6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024edc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ee5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024edc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ee5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024ed2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024ed2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024e4a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024e4a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180024e7d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180024e7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180024e10  mov     [rsp-8+arg_0], rbx
0x180024e15  push    rbp
0x180024e16  mov     rbp, rsp
0x180024e19  sub     rsp, 50h
0x180024e1d  mov     [rbp+var_18], 0
0x180024e25  mov     [rbp+var_8], 0
0x180024e2d  lea     rax, [rbp+var_18]
0x180024e31  mov     [rsp+50h+ppv], rax; ppv
0x180024e36  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180024e3d  xor     edx, edx; pUnkOuter
0x180024e3f  lea     r8d, [rdx+1]; dwClsContext
0x180024e43  lea     rcx, CLSID_GlobalOptions; rclsid
0x180024e4a  call    cs:__imp_CoCreateInstance
0x180024e50  test    eax, eax
0x180024e52  js      short loc_180024E6D
0x180024e54  mov     rcx, [rbp+var_18]
0x180024e58  mov     rax, [rcx]
0x180024e5b  lea     r8, [rbp+var_8]
0x180024e5f  mov     edx, 4
0x180024e64  mov     rax, [rax+20h]
0x180024e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e6d  call    cs:__imp_GetCurrentProcessId
0x180024e73  mov     r8d, eax; dwProcessId
0x180024e76  xor     edx, edx; bInheritHandle
0x180024e78  mov     ecx, 1000h; dwDesiredAccess
0x180024e7d  call    cs:__imp_OpenProcess
0x180024e83  mov     rbx, rax
0x180024e86  test    rax, rax
0x180024e89  jz      short loc_180024EEC
0x180024e8b  mov     [rbp+TokenHandle], 0
0x180024e93  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180024e97  mov     edx, 8; DesiredAccess
0x180024e9c  mov     rcx, rax; ProcessHandle
0x180024e9f  call    cs:__imp_OpenProcessToken
0x180024ea5  test    eax, eax
0x180024ea7  jz      short loc_180024EE2
0x180024ea9  mov     [rbp+ReturnLength], 0
0x180024eb0  mov     [rbp+TokenInformation], 0
0x180024eb7  lea     rax, [rbp+ReturnLength]
0x180024ebb  mov     [rsp+50h+ppv], rax; ReturnLength
0x180024ec0  mov     r9d, 4; TokenInformationLength
0x180024ec6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180024eca  lea     edx, [r9+19h]; TokenInformationClass
0x180024ece  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180024ed2  call    cs:__imp_GetTokenInformation
0x180024ed8  mov     rcx, [rbp+TokenHandle]; hObject
0x180024edc  call    cs:__imp_CloseHandle
0x180024ee2  mov     rcx, rbx; hObject
0x180024ee5  call    cs:__imp_CloseHandle
0x180024eeb  nop
0x180024eec  mov     rcx, [rbp+var_18]
0x180024ef0  test    rcx, rcx
0x180024ef3  jz      short loc_180024F0A
0x180024ef5  mov     [rbp+var_18], 0
0x180024efd  mov     rdx, [rcx]
0x180024f00  mov     rax, [rdx+10h]
0x180024f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f09  nop
0x180024f0a  mov     eax, 1
0x180024f0f  mov     rbx, [rsp+50h+arg_0]
0x180024f14  add     rsp, 50h
0x180024f18  pop     rbp
0x180024f19  retn
```
