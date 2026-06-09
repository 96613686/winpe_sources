# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<ModernDeployment::Autopilot::Core::AttestationResultState *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18010e880`
- end: `0x18010e98f`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVAttestationResultState@Core@Autopilot@ModernDeployment@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `271`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b820`
- `0x180067008`
- `0x18010e880`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18010e91d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18010e91d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18010e8eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18010e8eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010e95a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010e963`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010e95a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010e963`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010e8c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010e8c8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18010e8fb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18010e8fb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010e950`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010e950`

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
0x18010e880  mov     [rsp-8+arg_0], rbx
0x18010e885  push    rbp
0x18010e886  mov     rbp, rsp
0x18010e889  sub     rsp, 60h
0x18010e88d  mov     rax, cs:__security_cookie
0x18010e894  xor     rax, rsp
0x18010e897  mov     [rbp+var_10], rax
0x18010e89b  mov     [rbp+var_20], 0
0x18010e8a3  mov     [rbp+var_18], 0
0x18010e8ab  lea     rax, [rbp+var_20]
0x18010e8af  mov     [rsp+60h+ppv], rax; ppv
0x18010e8b4  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18010e8bb  xor     edx, edx; pUnkOuter
0x18010e8bd  lea     r8d, [rdx+1]; dwClsContext
0x18010e8c1  lea     rcx, CLSID_GlobalOptions; rclsid
0x18010e8c8  call    cs:__imp_CoCreateInstance
0x18010e8ce  test    eax, eax
0x18010e8d0  js      short loc_18010E8EB
0x18010e8d2  mov     rcx, [rbp+var_20]
0x18010e8d6  mov     rax, [rcx]
0x18010e8d9  lea     r8, [rbp+var_18]
0x18010e8dd  mov     edx, 4
0x18010e8e2  mov     rax, [rax+20h]
0x18010e8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e8eb  call    cs:__imp_GetCurrentProcessId
0x18010e8f1  mov     r8d, eax; dwProcessId
0x18010e8f4  xor     edx, edx; bInheritHandle
0x18010e8f6  mov     ecx, 1000h; dwDesiredAccess
0x18010e8fb  call    cs:__imp_OpenProcess
0x18010e901  mov     rbx, rax
0x18010e904  test    rax, rax
0x18010e907  jz      short loc_18010E96A
0x18010e909  mov     [rbp+TokenHandle], 0
0x18010e911  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18010e915  mov     edx, 8; DesiredAccess
0x18010e91a  mov     rcx, rax; ProcessHandle
0x18010e91d  call    cs:__imp_OpenProcessToken
0x18010e923  test    eax, eax
0x18010e925  jz      short loc_18010E960
0x18010e927  mov     [rbp+ReturnLength], 0
0x18010e92e  mov     [rbp+TokenInformation], 0
0x18010e935  lea     rax, [rbp+ReturnLength]
0x18010e939  mov     [rsp+60h+ppv], rax; ReturnLength
0x18010e93e  mov     r9d, 4; TokenInformationLength
0x18010e944  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18010e948  lea     edx, [r9+19h]; TokenInformationClass
0x18010e94c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18010e950  call    cs:__imp_GetTokenInformation
0x18010e956  mov     rcx, [rbp+TokenHandle]; hObject
0x18010e95a  call    cs:__imp_CloseHandle
0x18010e960  mov     rcx, rbx; hObject
0x18010e963  call    cs:__imp_CloseHandle
0x18010e969  nop
0x18010e96a  lea     rcx, [rbp+var_20]
0x18010e96e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010e973  mov     eax, 1
0x18010e978  mov     rcx, [rbp+var_10]
0x18010e97c  xor     rcx, rsp; StackCookie
0x18010e97f  call    __security_check_cookie
0x18010e984  mov     rbx, [rsp+60h+arg_0]
0x18010e989  add     rsp, 60h
0x18010e98d  pop     rbp
0x18010e98e  retn
```
