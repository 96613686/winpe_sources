# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<ModernDeployment::Autopilot::Core::AttestationResultState *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180111dc0`
- end: `0x180111efa`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVAttestationResultState@Core@Autopilot@ModernDeployment@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `314`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180111dc0`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180111e6f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180111e6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180111e31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180111e31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111eb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111ec7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111eb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111ec7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180111e08`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180111e08`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180111e47`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180111e47`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180111ea8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180111ea8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<ModernDeployment::Autopilot::Core::AttestationResultState *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-28h] BYREF
  int TokenInformation; // [rsp+3Ch] [rbp-24h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-20h] BYREF
  __int64 v11; // [rsp+48h] [rbp-18h] BYREF

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
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  return 1;
}

```

## disassembly

```asm
0x180111dc0  mov     [rsp-8+arg_0], rbx
0x180111dc5  push    rbp
0x180111dc6  mov     rbp, rsp
0x180111dc9  sub     rsp, 60h
0x180111dcd  mov     rax, cs:__security_cookie
0x180111dd4  xor     rax, rsp
0x180111dd7  mov     [rbp+var_10], rax
0x180111ddb  mov     [rbp+var_20], 0
0x180111de3  mov     [rbp+var_18], 0
0x180111deb  lea     rax, [rbp+var_20]
0x180111def  mov     [rsp+60h+ppv], rax; ppv
0x180111df4  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180111dfb  xor     edx, edx; pUnkOuter
0x180111dfd  lea     r8d, [rdx+1]; dwClsContext
0x180111e01  lea     rcx, CLSID_GlobalOptions; rclsid
0x180111e08  call    cs:__imp_CoCreateInstance
0x180111e0f  nop     dword ptr [rax+rax+00h]
0x180111e14  test    eax, eax
0x180111e16  js      short loc_180111E31
0x180111e18  mov     rcx, [rbp+var_20]
0x180111e1c  mov     rax, [rcx]
0x180111e1f  lea     r8, [rbp+var_18]
0x180111e23  mov     edx, 4
0x180111e28  mov     rax, [rax+20h]
0x180111e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180111e31  call    cs:__imp_GetCurrentProcessId
0x180111e38  nop     dword ptr [rax+rax+00h]
0x180111e3d  mov     r8d, eax; dwProcessId
0x180111e40  xor     edx, edx; bInheritHandle
0x180111e42  mov     ecx, 1000h; dwDesiredAccess
0x180111e47  call    cs:__imp_OpenProcess
0x180111e4e  nop     dword ptr [rax+rax+00h]
0x180111e53  mov     rbx, rax
0x180111e56  test    rax, rax
0x180111e59  jz      short loc_180111ED4
0x180111e5b  mov     [rbp+TokenHandle], 0
0x180111e63  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180111e67  mov     edx, 8; DesiredAccess
0x180111e6c  mov     rcx, rax; ProcessHandle
0x180111e6f  call    cs:__imp_OpenProcessToken
0x180111e76  nop     dword ptr [rax+rax+00h]
0x180111e7b  test    eax, eax
0x180111e7d  jz      short loc_180111EC4
0x180111e7f  mov     [rbp+ReturnLength], 0
0x180111e86  mov     [rbp+TokenInformation], 0
0x180111e8d  lea     rax, [rbp+ReturnLength]
0x180111e91  mov     [rsp+60h+ppv], rax; ReturnLength
0x180111e96  mov     r9d, 4; TokenInformationLength
0x180111e9c  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180111ea0  lea     edx, [r9+19h]; TokenInformationClass
0x180111ea4  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180111ea8  call    cs:__imp_GetTokenInformation
0x180111eaf  nop     dword ptr [rax+rax+00h]
0x180111eb4  mov     rcx, [rbp+TokenHandle]; hObject
0x180111eb8  call    cs:__imp_CloseHandle
0x180111ebf  nop     dword ptr [rax+rax+00h]
0x180111ec4  mov     rcx, rbx; hObject
0x180111ec7  call    cs:__imp_CloseHandle
0x180111ece  nop     dword ptr [rax+rax+00h]
0x180111ed3  nop
0x180111ed4  lea     rcx, [rbp+var_20]
0x180111ed8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180111edd  mov     eax, 1
0x180111ee2  mov     rcx, [rbp+var_10]
0x180111ee6  xor     rcx, rsp; StackCookie
0x180111ee9  call    __security_check_cookie
0x180111eee  mov     rbx, [rsp+60h+arg_0]
0x180111ef3  add     rsp, 60h
0x180111ef7  pop     rbp
0x180111ef8  retn
```
