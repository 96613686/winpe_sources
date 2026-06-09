# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180016940`
- end: `0x180016a4a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180016940`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a15`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800169cf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800169cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001699d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001699d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001697a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001697a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800169ad`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800169ad`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016a02`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016a02`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180016940  mov     [rsp-8+arg_0], rbx
0x180016945  push    rbp
0x180016946  mov     rbp, rsp
0x180016949  sub     rsp, 50h
0x18001694d  mov     [rbp+var_18], 0
0x180016955  mov     [rbp+var_8], 0
0x18001695d  lea     rax, [rbp+var_18]
0x180016961  mov     [rsp+50h+ppv], rax; ppv
0x180016966  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18001696d  xor     edx, edx; pUnkOuter
0x18001696f  lea     r8d, [rdx+1]; dwClsContext
0x180016973  lea     rcx, CLSID_GlobalOptions; rclsid
0x18001697a  call    cs:__imp_CoCreateInstance
0x180016980  test    eax, eax
0x180016982  js      short loc_18001699D
0x180016984  mov     rcx, [rbp+var_18]
0x180016988  mov     rax, [rcx]
0x18001698b  lea     r8, [rbp+var_8]
0x18001698f  mov     edx, 4
0x180016994  mov     rax, [rax+20h]
0x180016998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001699d  call    cs:__imp_GetCurrentProcessId
0x1800169a3  mov     r8d, eax; dwProcessId
0x1800169a6  xor     edx, edx; bInheritHandle
0x1800169a8  mov     ecx, 1000h; dwDesiredAccess
0x1800169ad  call    cs:__imp_OpenProcess
0x1800169b3  mov     rbx, rax
0x1800169b6  test    rax, rax
0x1800169b9  jz      short loc_180016A1C
0x1800169bb  mov     [rbp+TokenHandle], 0
0x1800169c3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800169c7  mov     edx, 8; DesiredAccess
0x1800169cc  mov     rcx, rax; ProcessHandle
0x1800169cf  call    cs:__imp_OpenProcessToken
0x1800169d5  test    eax, eax
0x1800169d7  jz      short loc_180016A12
0x1800169d9  mov     [rbp+ReturnLength], 0
0x1800169e0  mov     [rbp+TokenInformation], 0
0x1800169e7  lea     rax, [rbp+ReturnLength]
0x1800169eb  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800169f0  mov     r9d, 4; TokenInformationLength
0x1800169f6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800169fa  lea     edx, [r9+19h]; TokenInformationClass
0x1800169fe  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180016a02  call    cs:__imp_GetTokenInformation
0x180016a08  mov     rcx, [rbp+TokenHandle]; hObject
0x180016a0c  call    cs:__imp_CloseHandle
0x180016a12  mov     rcx, rbx; hObject
0x180016a15  call    cs:__imp_CloseHandle
0x180016a1b  nop
0x180016a1c  mov     rcx, [rbp+var_18]
0x180016a20  test    rcx, rcx
0x180016a23  jz      short loc_180016A3A
0x180016a25  mov     [rbp+var_18], 0
0x180016a2d  mov     rdx, [rcx]
0x180016a30  mov     rax, [rdx+10h]
0x180016a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a39  nop
0x180016a3a  mov     eax, 1
0x180016a3f  mov     rbx, [rsp+50h+arg_0]
0x180016a44  add     rsp, 50h
0x180016a48  pop     rbp
0x180016a49  retn
```
