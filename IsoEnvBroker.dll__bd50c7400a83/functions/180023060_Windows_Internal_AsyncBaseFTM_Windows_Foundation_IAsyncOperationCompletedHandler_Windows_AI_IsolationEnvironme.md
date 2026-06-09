# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180023060`
- end: `0x18002316a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180023060`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800230ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800230ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800230bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800230bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002312c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023135`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002312c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023135`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002309a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002309a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023122`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023122`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800230cd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800230cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180023060  mov     [rsp-8+arg_0], rbx
0x180023065  push    rbp
0x180023066  mov     rbp, rsp
0x180023069  sub     rsp, 50h
0x18002306d  mov     [rbp+var_18], 0
0x180023075  mov     [rbp+var_8], 0
0x18002307d  lea     rax, [rbp+var_18]
0x180023081  mov     [rsp+50h+ppv], rax; ppv
0x180023086  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18002308d  xor     edx, edx; pUnkOuter
0x18002308f  lea     r8d, [rdx+1]; dwClsContext
0x180023093  lea     rcx, CLSID_GlobalOptions; rclsid
0x18002309a  call    cs:__imp_CoCreateInstance
0x1800230a0  test    eax, eax
0x1800230a2  js      short loc_1800230BD
0x1800230a4  mov     rcx, [rbp+var_18]
0x1800230a8  mov     rax, [rcx]
0x1800230ab  lea     r8, [rbp+var_8]
0x1800230af  mov     edx, 4
0x1800230b4  mov     rax, [rax+20h]
0x1800230b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230bd  call    cs:__imp_GetCurrentProcessId
0x1800230c3  mov     r8d, eax; dwProcessId
0x1800230c6  xor     edx, edx; bInheritHandle
0x1800230c8  mov     ecx, 1000h; dwDesiredAccess
0x1800230cd  call    cs:__imp_OpenProcess
0x1800230d3  mov     rbx, rax
0x1800230d6  test    rax, rax
0x1800230d9  jz      short loc_18002313C
0x1800230db  mov     [rbp+TokenHandle], 0
0x1800230e3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800230e7  mov     edx, 8; DesiredAccess
0x1800230ec  mov     rcx, rax; ProcessHandle
0x1800230ef  call    cs:__imp_OpenProcessToken
0x1800230f5  test    eax, eax
0x1800230f7  jz      short loc_180023132
0x1800230f9  mov     [rbp+ReturnLength], 0
0x180023100  mov     [rbp+TokenInformation], 0
0x180023107  lea     rax, [rbp+ReturnLength]
0x18002310b  mov     [rsp+50h+ppv], rax; ReturnLength
0x180023110  mov     r9d, 4; TokenInformationLength
0x180023116  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002311a  lea     edx, [r9+19h]; TokenInformationClass
0x18002311e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180023122  call    cs:__imp_GetTokenInformation
0x180023128  mov     rcx, [rbp+TokenHandle]; hObject
0x18002312c  call    cs:__imp_CloseHandle
0x180023132  mov     rcx, rbx; hObject
0x180023135  call    cs:__imp_CloseHandle
0x18002313b  nop
0x18002313c  mov     rcx, [rbp+var_18]
0x180023140  test    rcx, rcx
0x180023143  jz      short loc_18002315A
0x180023145  mov     [rbp+var_18], 0
0x18002314d  mov     rdx, [rcx]
0x180023150  mov     rax, [rdx+10h]
0x180023154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023159  nop
0x18002315a  mov     eax, 1
0x18002315f  mov     rbx, [rsp+50h+arg_0]
0x180023164  add     rsp, 50h
0x180023168  pop     rbp
0x180023169  retn
```
