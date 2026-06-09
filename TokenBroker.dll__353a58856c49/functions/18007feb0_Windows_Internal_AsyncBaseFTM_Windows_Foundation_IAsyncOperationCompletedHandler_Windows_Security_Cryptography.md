# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Cryptography::Core::CryptographicKey *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18007feb0`
- end: `0x18007ffba`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVCryptographicKey@Core@Cryptography@Security@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18007feb0`
- `0x18011b010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007ff72`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007ff72`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007ff3f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007ff3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007ff0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007ff0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ff7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ff85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ff7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ff85`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007ff1d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007ff1d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007feea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007feea`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Cryptography::Core::CryptographicKey *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x18007feb0  mov     [rsp-8+arg_0], rbx
0x18007feb5  push    rbp
0x18007feb6  mov     rbp, rsp
0x18007feb9  sub     rsp, 50h
0x18007febd  mov     [rbp+var_18], 0
0x18007fec5  mov     [rbp+var_8], 0
0x18007fecd  lea     rax, [rbp+var_18]
0x18007fed1  mov     [rsp+50h+ppv], rax; ppv
0x18007fed6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18007fedd  xor     edx, edx; pUnkOuter
0x18007fedf  lea     r8d, [rdx+1]; dwClsContext
0x18007fee3  lea     rcx, CLSID_GlobalOptions; rclsid
0x18007feea  call    cs:__imp_CoCreateInstance
0x18007fef0  test    eax, eax
0x18007fef2  js      short loc_18007FF0D
0x18007fef4  mov     rcx, [rbp+var_18]
0x18007fef8  mov     rax, [rcx]
0x18007fefb  lea     r8, [rbp+var_8]
0x18007feff  mov     edx, 4
0x18007ff04  mov     rax, [rax+20h]
0x18007ff08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ff0d  call    cs:__imp_GetCurrentProcessId
0x18007ff13  mov     r8d, eax; dwProcessId
0x18007ff16  xor     edx, edx; bInheritHandle
0x18007ff18  mov     ecx, 1000h; dwDesiredAccess
0x18007ff1d  call    cs:__imp_OpenProcess
0x18007ff23  mov     rbx, rax
0x18007ff26  test    rax, rax
0x18007ff29  jz      short loc_18007FF8C
0x18007ff2b  mov     [rbp+TokenHandle], 0
0x18007ff33  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18007ff37  mov     edx, 8; DesiredAccess
0x18007ff3c  mov     rcx, rax; ProcessHandle
0x18007ff3f  call    cs:__imp_OpenProcessToken
0x18007ff45  test    eax, eax
0x18007ff47  jz      short loc_18007FF82
0x18007ff49  mov     [rbp+ReturnLength], 0
0x18007ff50  mov     [rbp+TokenInformation], 0
0x18007ff57  lea     rax, [rbp+ReturnLength]
0x18007ff5b  mov     [rsp+50h+ppv], rax; ReturnLength
0x18007ff60  mov     r9d, 4; TokenInformationLength
0x18007ff66  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18007ff6a  lea     edx, [r9+19h]; TokenInformationClass
0x18007ff6e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18007ff72  call    cs:__imp_GetTokenInformation
0x18007ff78  mov     rcx, [rbp+TokenHandle]; hObject
0x18007ff7c  call    cs:__imp_CloseHandle
0x18007ff82  mov     rcx, rbx; hObject
0x18007ff85  call    cs:__imp_CloseHandle
0x18007ff8b  nop
0x18007ff8c  mov     rcx, [rbp+var_18]
0x18007ff90  test    rcx, rcx
0x18007ff93  jz      short loc_18007FFAA
0x18007ff95  mov     [rbp+var_18], 0
0x18007ff9d  mov     rdx, [rcx]
0x18007ffa0  mov     rax, [rdx+10h]
0x18007ffa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ffa9  nop
0x18007ffaa  mov     eax, 1
0x18007ffaf  mov     rbx, [rsp+50h+arg_0]
0x18007ffb4  add     rsp, 50h
0x18007ffb8  pop     rbp
0x18007ffb9  retn
```
