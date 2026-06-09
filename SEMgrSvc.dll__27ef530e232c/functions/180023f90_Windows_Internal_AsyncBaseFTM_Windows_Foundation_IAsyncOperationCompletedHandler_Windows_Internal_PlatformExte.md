# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180023f90`
- end: `0x18002409a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180023f90`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023fca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023fca`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002401f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002401f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023fed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023fed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002405c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024065`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002405c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024065`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180023ffd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180023ffd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024052`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024052`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180023f90  mov     [rsp-8+arg_0], rbx
0x180023f95  push    rbp
0x180023f96  mov     rbp, rsp
0x180023f99  sub     rsp, 50h
0x180023f9d  mov     [rbp+var_18], 0
0x180023fa5  mov     [rbp+var_8], 0
0x180023fad  lea     rax, [rbp+var_18]
0x180023fb1  mov     [rsp+50h+ppv], rax; ppv
0x180023fb6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180023fbd  xor     edx, edx; pUnkOuter
0x180023fbf  lea     r8d, [rdx+1]; dwClsContext
0x180023fc3  lea     rcx, CLSID_GlobalOptions; rclsid
0x180023fca  call    cs:__imp_CoCreateInstance
0x180023fd0  test    eax, eax
0x180023fd2  js      short loc_180023FED
0x180023fd4  mov     rcx, [rbp+var_18]
0x180023fd8  mov     rax, [rcx]
0x180023fdb  lea     r8, [rbp+var_8]
0x180023fdf  mov     edx, 4
0x180023fe4  mov     rax, [rax+20h]
0x180023fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fed  call    cs:__imp_GetCurrentProcessId
0x180023ff3  mov     r8d, eax; dwProcessId
0x180023ff6  xor     edx, edx; bInheritHandle
0x180023ff8  mov     ecx, 1000h; dwDesiredAccess
0x180023ffd  call    cs:__imp_OpenProcess
0x180024003  mov     rbx, rax
0x180024006  test    rax, rax
0x180024009  jz      short loc_18002406C
0x18002400b  mov     [rbp+TokenHandle], 0
0x180024013  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180024017  mov     edx, 8; DesiredAccess
0x18002401c  mov     rcx, rax; ProcessHandle
0x18002401f  call    cs:__imp_OpenProcessToken
0x180024025  test    eax, eax
0x180024027  jz      short loc_180024062
0x180024029  mov     [rbp+ReturnLength], 0
0x180024030  mov     [rbp+TokenInformation], 0
0x180024037  lea     rax, [rbp+ReturnLength]
0x18002403b  mov     [rsp+50h+ppv], rax; ReturnLength
0x180024040  mov     r9d, 4; TokenInformationLength
0x180024046  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002404a  lea     edx, [r9+19h]; TokenInformationClass
0x18002404e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180024052  call    cs:__imp_GetTokenInformation
0x180024058  mov     rcx, [rbp+TokenHandle]; hObject
0x18002405c  call    cs:__imp_CloseHandle
0x180024062  mov     rcx, rbx; hObject
0x180024065  call    cs:__imp_CloseHandle
0x18002406b  nop
0x18002406c  mov     rcx, [rbp+var_18]
0x180024070  test    rcx, rcx
0x180024073  jz      short loc_18002408A
0x180024075  mov     [rbp+var_18], 0
0x18002407d  mov     rdx, [rcx]
0x180024080  mov     rax, [rdx+10h]
0x180024084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024089  nop
0x18002408a  mov     eax, 1
0x18002408f  mov     rbx, [rsp+50h+arg_0]
0x180024094  add     rsp, 50h
0x180024098  pop     rbp
0x180024099  retn
```
