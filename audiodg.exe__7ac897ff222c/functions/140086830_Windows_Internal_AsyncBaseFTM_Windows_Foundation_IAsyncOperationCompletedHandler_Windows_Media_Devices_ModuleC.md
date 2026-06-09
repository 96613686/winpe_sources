# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Devices::ModuleCommandResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x140086830`
- end: `0x14008693a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVModuleCommandResult@Devices@Media@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140086830`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14008688d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14008688d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400868bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400868bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400868fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140086905`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400868fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140086905`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14008689d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14008689d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14008686a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14008686a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400868f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400868f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Devices::ModuleCommandResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x140086830  mov     [rsp-8+arg_0], rbx
0x140086835  push    rbp
0x140086836  mov     rbp, rsp
0x140086839  sub     rsp, 50h
0x14008683d  mov     [rbp+var_18], 0
0x140086845  mov     [rbp+var_8], 0
0x14008684d  lea     rax, [rbp+var_18]
0x140086851  mov     [rsp+50h+ppv], rax; ppv
0x140086856  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x14008685d  xor     edx, edx; pUnkOuter
0x14008685f  lea     r8d, [rdx+1]; dwClsContext
0x140086863  lea     rcx, CLSID_GlobalOptions; rclsid
0x14008686a  call    cs:__imp_CoCreateInstance
0x140086870  test    eax, eax
0x140086872  js      short loc_14008688D
0x140086874  mov     rcx, [rbp+var_18]
0x140086878  mov     rax, [rcx]
0x14008687b  lea     r8, [rbp+var_8]
0x14008687f  mov     edx, 4
0x140086884  mov     rax, [rax+20h]
0x140086888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008688d  call    cs:__imp_GetCurrentProcessId
0x140086893  mov     r8d, eax; dwProcessId
0x140086896  xor     edx, edx; bInheritHandle
0x140086898  mov     ecx, 1000h; dwDesiredAccess
0x14008689d  call    cs:__imp_OpenProcess
0x1400868a3  mov     rbx, rax
0x1400868a6  test    rax, rax
0x1400868a9  jz      short loc_14008690C
0x1400868ab  mov     [rbp+TokenHandle], 0
0x1400868b3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1400868b7  mov     edx, 8; DesiredAccess
0x1400868bc  mov     rcx, rax; ProcessHandle
0x1400868bf  call    cs:__imp_OpenProcessToken
0x1400868c5  test    eax, eax
0x1400868c7  jz      short loc_140086902
0x1400868c9  mov     [rbp+ReturnLength], 0
0x1400868d0  mov     [rbp+TokenInformation], 0
0x1400868d7  lea     rax, [rbp+ReturnLength]
0x1400868db  mov     [rsp+50h+ppv], rax; ReturnLength
0x1400868e0  mov     r9d, 4; TokenInformationLength
0x1400868e6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400868ea  lea     edx, [r9+19h]; TokenInformationClass
0x1400868ee  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400868f2  call    cs:__imp_GetTokenInformation
0x1400868f8  mov     rcx, [rbp+TokenHandle]; hObject
0x1400868fc  call    cs:__imp_CloseHandle
0x140086902  mov     rcx, rbx; hObject
0x140086905  call    cs:__imp_CloseHandle
0x14008690b  nop
0x14008690c  mov     rcx, [rbp+var_18]
0x140086910  test    rcx, rcx
0x140086913  jz      short loc_14008692A
0x140086915  mov     [rbp+var_18], 0
0x14008691d  mov     rdx, [rcx]
0x140086920  mov     rax, [rdx+10h]
0x140086924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086929  nop
0x14008692a  mov     eax, 1
0x14008692f  mov     rbx, [rsp+50h+arg_0]
0x140086934  add     rsp, 50h
0x140086938  pop     rbp
0x140086939  retn
```
