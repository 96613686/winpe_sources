# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180015390`
- end: `0x18001549a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180015390`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001541f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001541f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800153ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800153ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001545c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015465`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001545c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015465`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800153ca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800153ca`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800153fd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800153fd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015452`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015452`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IMapView<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180015390  mov     [rsp-8+arg_0], rbx
0x180015395  push    rbp
0x180015396  mov     rbp, rsp
0x180015399  sub     rsp, 50h
0x18001539d  mov     [rbp+var_18], 0
0x1800153a5  mov     [rbp+var_8], 0
0x1800153ad  lea     rax, [rbp+var_18]
0x1800153b1  mov     [rsp+50h+ppv], rax; ppv
0x1800153b6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800153bd  xor     edx, edx; pUnkOuter
0x1800153bf  lea     r8d, [rdx+1]; dwClsContext
0x1800153c3  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800153ca  call    cs:__imp_CoCreateInstance
0x1800153d0  test    eax, eax
0x1800153d2  js      short loc_1800153ED
0x1800153d4  mov     rcx, [rbp+var_18]
0x1800153d8  mov     rax, [rcx]
0x1800153db  lea     r8, [rbp+var_8]
0x1800153df  mov     edx, 4
0x1800153e4  mov     rax, [rax+20h]
0x1800153e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153ed  call    cs:__imp_GetCurrentProcessId
0x1800153f3  mov     r8d, eax; dwProcessId
0x1800153f6  xor     edx, edx; bInheritHandle
0x1800153f8  mov     ecx, 1000h; dwDesiredAccess
0x1800153fd  call    cs:__imp_OpenProcess
0x180015403  mov     rbx, rax
0x180015406  test    rax, rax
0x180015409  jz      short loc_18001546C
0x18001540b  mov     [rbp+TokenHandle], 0
0x180015413  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180015417  mov     edx, 8; DesiredAccess
0x18001541c  mov     rcx, rax; ProcessHandle
0x18001541f  call    cs:__imp_OpenProcessToken
0x180015425  test    eax, eax
0x180015427  jz      short loc_180015462
0x180015429  mov     [rbp+ReturnLength], 0
0x180015430  mov     [rbp+TokenInformation], 0
0x180015437  lea     rax, [rbp+ReturnLength]
0x18001543b  mov     [rsp+50h+ppv], rax; ReturnLength
0x180015440  mov     r9d, 4; TokenInformationLength
0x180015446  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18001544a  lea     edx, [r9+19h]; TokenInformationClass
0x18001544e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180015452  call    cs:__imp_GetTokenInformation
0x180015458  mov     rcx, [rbp+TokenHandle]; hObject
0x18001545c  call    cs:__imp_CloseHandle
0x180015462  mov     rcx, rbx; hObject
0x180015465  call    cs:__imp_CloseHandle
0x18001546b  nop
0x18001546c  mov     rcx, [rbp+var_18]
0x180015470  test    rcx, rcx
0x180015473  jz      short loc_18001548A
0x180015475  mov     [rbp+var_18], 0
0x18001547d  mov     rdx, [rcx]
0x180015480  mov     rax, [rdx+10h]
0x180015484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015489  nop
0x18001548a  mov     eax, 1
0x18001548f  mov     rbx, [rsp+50h+arg_0]
0x180015494  add     rsp, 50h
0x180015498  pop     rbp
0x180015499  retn
```
