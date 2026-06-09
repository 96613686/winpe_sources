# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18009b660`
- end: `0x18009b755`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `245`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001f5f4`
- `0x18009b660`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009b6ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009b6ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009b6bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009b6bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b72c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b735`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b72c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b735`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18009b6cd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18009b6cd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009b69a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009b69a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009b722`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009b722`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  int TokenInformation; // [rsp+30h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-10h] BYREF
  __int64 v10; // [rsp+48h] [rbp-8h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+28h] BYREF

  ppv = 0;
  v10 = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
    (*(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 4, &v10);
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
0x18009b660  mov     [rsp-8+arg_0], rbx
0x18009b665  push    rbp
0x18009b666  mov     rbp, rsp
0x18009b669  sub     rsp, 50h
0x18009b66d  mov     [rbp+var_10], 0
0x18009b675  mov     [rbp+var_8], 0
0x18009b67d  lea     rax, [rbp+var_10]
0x18009b681  mov     [rsp+50h+ppv], rax; ppv
0x18009b686  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18009b68d  xor     edx, edx; pUnkOuter
0x18009b68f  lea     r8d, [rdx+1]; dwClsContext
0x18009b693  lea     rcx, CLSID_GlobalOptions; rclsid
0x18009b69a  call    cs:__imp_CoCreateInstance
0x18009b6a0  test    eax, eax
0x18009b6a2  js      short loc_18009B6BD
0x18009b6a4  mov     rcx, [rbp+var_10]
0x18009b6a8  mov     rax, [rcx]
0x18009b6ab  lea     r8, [rbp+var_8]
0x18009b6af  mov     edx, 4
0x18009b6b4  mov     rax, [rax+20h]
0x18009b6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b6bd  call    cs:__imp_GetCurrentProcessId
0x18009b6c3  mov     r8d, eax; dwProcessId
0x18009b6c6  xor     edx, edx; bInheritHandle
0x18009b6c8  mov     ecx, 1000h; dwDesiredAccess
0x18009b6cd  call    cs:__imp_OpenProcess
0x18009b6d3  mov     rbx, rax
0x18009b6d6  test    rax, rax
0x18009b6d9  jz      short loc_18009B73C
0x18009b6db  mov     [rbp+TokenHandle], 0
0x18009b6e3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18009b6e7  mov     edx, 8; DesiredAccess
0x18009b6ec  mov     rcx, rax; ProcessHandle
0x18009b6ef  call    cs:__imp_OpenProcessToken
0x18009b6f5  test    eax, eax
0x18009b6f7  jz      short loc_18009B732
0x18009b6f9  mov     [rbp+ReturnLength], 0
0x18009b700  mov     [rbp+TokenInformation], 0
0x18009b707  lea     rax, [rbp+ReturnLength]
0x18009b70b  mov     [rsp+50h+ppv], rax; ReturnLength
0x18009b710  mov     r9d, 4; TokenInformationLength
0x18009b716  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18009b71a  lea     edx, [r9+19h]; TokenInformationClass
0x18009b71e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18009b722  call    cs:__imp_GetTokenInformation
0x18009b728  mov     rcx, [rbp+TokenHandle]; hObject
0x18009b72c  call    cs:__imp_CloseHandle
0x18009b732  mov     rcx, rbx; hObject
0x18009b735  call    cs:__imp_CloseHandle
0x18009b73b  nop
0x18009b73c  lea     rcx, [rbp+var_10]
0x18009b740  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009b745  mov     eax, 1
0x18009b74a  mov     rbx, [rsp+50h+arg_0]
0x18009b74f  add     rsp, 50h
0x18009b753  pop     rbp
0x18009b754  retn
```
