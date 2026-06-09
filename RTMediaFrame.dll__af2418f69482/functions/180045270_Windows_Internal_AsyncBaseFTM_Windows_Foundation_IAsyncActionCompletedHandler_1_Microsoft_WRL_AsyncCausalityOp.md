# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const GeotagHelper_SetGeotagAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180045270`
- end: `0x180045364`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?GeotagHelper_SetGeotagAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `244`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800019c0`
- `0x180045270`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800452cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800452cd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800452ff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800452ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004533c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045345`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004533c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045345`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800452aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800452aa`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800452dd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800452dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045332`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045332`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const GeotagHelper_SetGeotagAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  int TokenInformation; // [rsp+30h] [rbp-20h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-18h] BYREF
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
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppv);
  return 1;
}

```

## disassembly

```asm
0x180045270  mov     [rsp-8+arg_0], rbx
0x180045275  push    rbp
0x180045276  mov     rbp, rsp
0x180045279  sub     rsp, 50h
0x18004527d  xor     edx, edx; pUnkOuter
0x18004527f  mov     [rbp+var_10], 0
0x180045287  lea     rax, [rbp+var_10]
0x18004528b  mov     [rbp+var_8], 0
0x180045293  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18004529a  mov     [rsp+50h+ppv], rax; ppv
0x18004529f  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800452a6  lea     r8d, [rdx+1]; dwClsContext
0x1800452aa  call    cs:__imp_CoCreateInstance
0x1800452b0  test    eax, eax
0x1800452b2  js      short loc_1800452CD
0x1800452b4  mov     rcx, [rbp+var_10]
0x1800452b8  lea     r8, [rbp+var_8]
0x1800452bc  mov     edx, 4
0x1800452c1  mov     rax, [rcx]
0x1800452c4  mov     rax, [rax+20h]
0x1800452c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452cd  call    cs:__imp_GetCurrentProcessId
0x1800452d3  xor     edx, edx; bInheritHandle
0x1800452d5  mov     ecx, 1000h; dwDesiredAccess
0x1800452da  mov     r8d, eax; dwProcessId
0x1800452dd  call    cs:__imp_OpenProcess
0x1800452e3  mov     rbx, rax
0x1800452e6  test    rax, rax
0x1800452e9  jz      short loc_18004534B
0x1800452eb  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800452ef  mov     [rbp+TokenHandle], 0
0x1800452f7  mov     edx, 8; DesiredAccess
0x1800452fc  mov     rcx, rax; ProcessHandle
0x1800452ff  call    cs:__imp_OpenProcessToken
0x180045305  test    eax, eax
0x180045307  jz      short loc_180045342
0x180045309  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004530d  lea     rax, [rbp+ReturnLength]
0x180045311  mov     r9d, 4; TokenInformationLength
0x180045317  mov     [rbp+ReturnLength], 0
0x18004531e  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180045322  mov     [rbp+TokenInformation], 0
0x180045329  mov     [rsp+50h+ppv], rax; ReturnLength
0x18004532e  lea     edx, [r9+19h]; TokenInformationClass
0x180045332  call    cs:__imp_GetTokenInformation
0x180045338  mov     rcx, [rbp+TokenHandle]; hObject
0x18004533c  call    cs:__imp_CloseHandle
0x180045342  mov     rcx, rbx; hObject
0x180045345  call    cs:__imp_CloseHandle
0x18004534b  lea     rcx, [rbp+var_10]
0x18004534f  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180045354  mov     rbx, [rsp+50h+arg_0]
0x180045359  mov     eax, 1
0x18004535e  add     rsp, 50h
0x180045362  pop     rbp
0x180045363  retn
```
