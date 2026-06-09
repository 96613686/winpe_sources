# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const LogoffSoundAction,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18004a0b0`
- end: `0x18004a1ba`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?LogoffSoundAction@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004a0b0`
- `0x18009d010`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x18004a11d`
- `KERNEL32!OpenProcess` at `0x18004a11d`
- `KERNEL32!GetCurrentProcessId` at `0x18004a10d`
- `KERNEL32!GetCurrentProcessId` at `0x18004a10d`
- `KERNEL32!CloseHandle` at `0x18004a17c`
- `KERNEL32!CloseHandle` at `0x18004a185`
- `KERNEL32!CloseHandle` at `0x18004a17c`
- `KERNEL32!CloseHandle` at `0x18004a185`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a0ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a0ea`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004a13f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004a13f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004a172`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004a172`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const LogoffSoundAction,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x18004a0b0  mov     [rsp-8+arg_0], rbx
0x18004a0b5  push    rbp
0x18004a0b6  mov     rbp, rsp
0x18004a0b9  sub     rsp, 50h
0x18004a0bd  mov     [rbp+var_18], 0
0x18004a0c5  mov     [rbp+var_8], 0
0x18004a0cd  lea     rax, [rbp+var_18]
0x18004a0d1  mov     [rsp+50h+ppv], rax; ppv
0x18004a0d6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18004a0dd  xor     edx, edx; pUnkOuter
0x18004a0df  lea     r8d, [rdx+1]; dwClsContext
0x18004a0e3  lea     rcx, CLSID_GlobalOptions; rclsid
0x18004a0ea  call    cs:__imp_CoCreateInstance
0x18004a0f0  test    eax, eax
0x18004a0f2  js      short loc_18004A10D
0x18004a0f4  mov     rcx, [rbp+var_18]
0x18004a0f8  mov     rax, [rcx]
0x18004a0fb  lea     r8, [rbp+var_8]
0x18004a0ff  mov     edx, 4
0x18004a104  mov     rax, [rax+20h]
0x18004a108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a10d  call    cs:__imp_GetCurrentProcessId
0x18004a113  mov     r8d, eax; dwProcessId
0x18004a116  xor     edx, edx; bInheritHandle
0x18004a118  mov     ecx, 1000h; dwDesiredAccess
0x18004a11d  call    cs:__imp_OpenProcess
0x18004a123  mov     rbx, rax
0x18004a126  test    rax, rax
0x18004a129  jz      short loc_18004A18C
0x18004a12b  mov     [rbp+TokenHandle], 0
0x18004a133  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18004a137  mov     edx, 8; DesiredAccess
0x18004a13c  mov     rcx, rax; ProcessHandle
0x18004a13f  call    cs:__imp_OpenProcessToken
0x18004a145  test    eax, eax
0x18004a147  jz      short loc_18004A182
0x18004a149  mov     [rbp+ReturnLength], 0
0x18004a150  mov     [rbp+TokenInformation], 0
0x18004a157  lea     rax, [rbp+ReturnLength]
0x18004a15b  mov     [rsp+50h+ppv], rax; ReturnLength
0x18004a160  mov     r9d, 4; TokenInformationLength
0x18004a166  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18004a16a  lea     edx, [r9+19h]; TokenInformationClass
0x18004a16e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004a172  call    cs:__imp_GetTokenInformation
0x18004a178  mov     rcx, [rbp+TokenHandle]; hObject
0x18004a17c  call    cs:__imp_CloseHandle
0x18004a182  mov     rcx, rbx; hObject
0x18004a185  call    cs:__imp_CloseHandle
0x18004a18b  nop
0x18004a18c  mov     rcx, [rbp+var_18]
0x18004a190  test    rcx, rcx
0x18004a193  jz      short loc_18004A1AA
0x18004a195  mov     [rbp+var_18], 0
0x18004a19d  mov     rdx, [rcx]
0x18004a1a0  mov     rax, [rdx+10h]
0x18004a1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1a9  nop
0x18004a1aa  mov     eax, 1
0x18004a1af  mov     rbx, [rsp+50h+arg_0]
0x18004a1b4  add     rsp, 50h
0x18004a1b8  pop     rbp
0x18004a1b9  retn
```
