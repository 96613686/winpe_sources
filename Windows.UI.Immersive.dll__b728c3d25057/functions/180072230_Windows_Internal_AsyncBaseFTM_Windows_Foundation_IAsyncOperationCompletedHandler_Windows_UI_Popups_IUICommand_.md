# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180072230`
- end: `0x180072338`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `264`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180072230`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800722bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800722bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007228d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007228d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007229d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007229d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800722fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072305`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800722fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072305`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800722f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800722f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007226a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007226a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180072230  mov     [rsp-8+arg_0], rbx
0x180072235  push    rbp
0x180072236  mov     rbp, rsp
0x180072239  sub     rsp, 50h
0x18007223d  xor     edx, edx; pUnkOuter
0x18007223f  mov     [rbp+var_18], 0
0x180072247  lea     rax, [rbp+var_18]
0x18007224b  mov     [rbp+var_8], 0
0x180072253  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18007225a  mov     [rsp+50h+ppv], rax; ppv
0x18007225f  lea     rcx, CLSID_GlobalOptions; rclsid
0x180072266  lea     r8d, [rdx+1]; dwClsContext
0x18007226a  call    cs:__imp_CoCreateInstance
0x180072270  test    eax, eax
0x180072272  js      short loc_18007228D
0x180072274  mov     rcx, [rbp+var_18]
0x180072278  lea     r8, [rbp+var_8]
0x18007227c  mov     edx, 4
0x180072281  mov     rax, [rcx]
0x180072284  mov     rax, [rax+20h]
0x180072288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007228d  call    cs:__imp_GetCurrentProcessId
0x180072293  xor     edx, edx; bInheritHandle
0x180072295  mov     ecx, 1000h; dwDesiredAccess
0x18007229a  mov     r8d, eax; dwProcessId
0x18007229d  call    cs:__imp_OpenProcess
0x1800722a3  mov     rbx, rax
0x1800722a6  test    rax, rax
0x1800722a9  jz      short loc_18007230B
0x1800722ab  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800722af  mov     [rbp+TokenHandle], 0
0x1800722b7  mov     edx, 8; DesiredAccess
0x1800722bc  mov     rcx, rax; ProcessHandle
0x1800722bf  call    cs:__imp_OpenProcessToken
0x1800722c5  test    eax, eax
0x1800722c7  jz      short loc_180072302
0x1800722c9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800722cd  lea     rax, [rbp+ReturnLength]
0x1800722d1  mov     r9d, 4; TokenInformationLength
0x1800722d7  mov     [rbp+ReturnLength], 0
0x1800722de  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800722e2  mov     [rbp+TokenInformation], 0
0x1800722e9  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800722ee  lea     edx, [r9+19h]; TokenInformationClass
0x1800722f2  call    cs:__imp_GetTokenInformation
0x1800722f8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800722fc  call    cs:__imp_CloseHandle
0x180072302  mov     rcx, rbx; hObject
0x180072305  call    cs:__imp_CloseHandle
0x18007230b  mov     rcx, [rbp+var_18]
0x18007230f  test    rcx, rcx
0x180072312  jz      short loc_180072328
0x180072314  mov     [rbp+var_18], 0
0x18007231c  mov     rdx, [rcx]
0x18007231f  mov     rax, [rdx+10h]
0x180072323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072328  mov     rbx, [rsp+50h+arg_0]
0x18007232d  mov     eax, 1
0x180072332  add     rsp, 50h
0x180072336  pop     rbp
0x180072337  retn
```
