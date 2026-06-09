# LanguageOverlayServiceModule::_Initialize(ushort const *)

- ea: `0x180011ccc`
- end: `0x1800120a8`
- name: `?_Initialize@LanguageOverlayServiceModule@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@KP6AXK@Z$1?_ReleaseSharedService@details@raii@@YAXK@ZU?$integral_constant@_K$0A@@wistd@@KK$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `988`
- prototype: `__int64 __fastcall(LPVOID lpContext)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001021c`

## callees

- `0x180003a00`
- `0x180005db4`
- `0x18000a008`
- `0x18000a6cc`
- `0x180011318`
- `0x180011ccc`
- `0x180012a98`
- `0x18002818c`
- `0x180062f00`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011f6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011f6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011f5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011fbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011f5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011fbb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011e77`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011e77`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180011ebb`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180011ebb`
- `combase!__imp_CoGetSharedServiceId` at `0x180011d55`
- `combase!__imp_CoGetSharedServiceId` at `0x180011d55`
- `combase!__imp_CoAddRefSharedService` at `0x180011d72`
- `combase!__imp_CoAddRefSharedService` at `0x180011d72`
- `msvcp_win!_Mtx_unlock` at `0x180012003`
- `msvcp_win!_Mtx_unlock` at `0x180012003`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011d1b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011d38`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011d1b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180011d38`
- `msvcp_win!_Mtx_lock` at `0x180011d0c`
- `msvcp_win!_Mtx_lock` at `0x180011d0c`

## string_xrefs

- `0x180012033`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180012096`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180012048`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayservicemodule.cpp`
- `0x18001205d`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayservicemodule.cpp`
- `0x180012072`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayservicemodule.cpp`
- `0x180012084`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayservicemodule.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
unsigned int *__fastcall LanguageOverlayServiceModule::_Initialize(char *lpContext, unsigned int *a2, const WCHAR *a3)
{
  char *v6; // r14
  __int64 v7; // rcx
  int SharedServiceId; // eax
  unsigned int v9; // r13d
  char *v10; // rbx
  __int64 v11; // rax
  volatile signed __int32 *v12; // rcx
  HRESULT v13; // eax
  int v14; // eax
  const char *v15; // r9
  SERVICE_STATUS_HANDLE v16; // r12
  volatile signed __int32 *v17; // rsi
  HANDLE *v18; // rdi
  HANDLE v19; // r12
  HANDLE v20; // rsi
  DWORD LastError; // r13d
  const char *v22; // r9
  HANDLE v23; // rcx
  LPVOID v24; // rdx
  const char *v25; // r9
  int ppv; // [rsp+20h] [rbp-60h]
  int ppva; // [rsp+20h] [rbp-60h]
  HANDLE hObject; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v30; // [rsp+38h] [rbp-48h]
  unsigned int v31; // [rsp+3Ch] [rbp-44h]
  _QWORD v32[5]; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v33; // [rsp+68h] [rbp-18h] BYREF
  LPVOID v34; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v34 = a2;
  v6 = lpContext + 16;
  v32[2] = lpContext + 16;
  if ( _Mtx_lock((_Mtx_t)(lpContext + 16)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)v6 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v6 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( *((_DWORD *)lpContext + 31) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
  v33 = 0;
  SharedServiceId = CoGetSharedServiceId(&v33);
  if ( SharedServiceId < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlayservicemodule.cpp",
      (const char *)(unsigned int)SharedServiceId,
      ppv);
  v9 = v33;
  v30 = v33;
  CoAddRefSharedService(v33);
  v31 = v9;
  v10 = (char *)operator new(0x198u);
  v32[0] = v10;
  *(_OWORD *)v10 = 0;
  *((_DWORD *)v10 + 2) = 1;
  *((_DWORD *)v10 + 3) = 1;
  *(_QWORD *)v10 = &std::_Ref_count_obj2<WorkManager>::`vftable';
  WorkManager::WorkManager((WorkManager *)(v10 + 16));
  if ( v10 != (char *)-16LL )
  {
    v11 = *((_QWORD *)v10 + 4);
    if ( !v11 || !*(_DWORD *)(v11 + 8) )
    {
      _InterlockedIncrement((volatile signed __int32 *)v10 + 2);
      _InterlockedIncrement((volatile signed __int32 *)v10 + 3);
      *((_QWORD *)v10 + 3) = v10 + 16;
      v12 = (volatile signed __int32 *)*((_QWORD *)v10 + 4);
      *((_QWORD *)v10 + 4) = v10;
      if ( v12 && _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v10)(v10);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
  }
  v32[3] = v10 + 16;
  v32[4] = v10;
  LODWORD(v32[0]) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    &hObject,
    (int *)v32);
  v34 = 0;
  v13 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v34);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlayservicemodule.cpp",
      (const char *)(unsigned int)v13,
      ppva);
  v14 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v34 + 24LL))(v34, 5, 1);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlayservicemodule.cpp",
      (const char *)(unsigned int)v14,
      ppva);
  v16 = RegisterServiceCtrlHandlerExW(a3, LanguageOverlayServiceModule::_ServiceControlCallback, lpContext);
  if ( !v16 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlayservicemodule.cpp",
      v15);
  _InterlockedIncrement((volatile signed __int32 *)v10 + 2);
  *((_QWORD *)lpContext + 12) = v10 + 16;
  v17 = (volatile signed __int32 *)*((_QWORD *)lpContext + 13);
  *((_QWORD *)lpContext + 13) = v10;
  if ( v17 )
  {
    if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  *((_DWORD *)lpContext + 30) = v33;
  *(_QWORD *)(lpContext + 124) = 2;
  *((_QWORD *)lpContext + 17) = v16;
  v18 = (HANDLE *)(lpContext + 144);
  if ( v18 == &hObject )
  {
    v23 = hObject;
  }
  else
  {
    v19 = hObject;
    v20 = *v18;
    if ( *v18 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v22);
      SetLastError(LastError);
      v9 = v30;
    }
    *v18 = v19;
    v23 = 0;
    hObject = 0;
  }
  *a2 = v9;
  v31 = 0;
  v24 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
    v23 = hObject;
  }
  if ( v23 && !CloseHandle(v23) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v10)(v10);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
  }
  _Mtx_unlock((_Mtx_t)v6);
  return a2;
}

```

## disassembly

```asm
0x180011ccc  mov     [rsp-38h+arg_18], rbx
0x180011cd1  push    rbp
0x180011cd2  push    rsi
0x180011cd3  push    rdi
0x180011cd4  push    r12
0x180011cd6  push    r13
0x180011cd8  push    r14
0x180011cda  push    r15
0x180011cdc  mov     rbp, rsp
0x180011cdf  sub     rsp, 80h
0x180011ce6  mov     rax, cs:__security_cookie
0x180011ced  xor     rax, rsp
0x180011cf0  mov     [rbp+var_8], rax
0x180011cf4  mov     r12, r8
0x180011cf7  mov     r15, rdx
0x180011cfa  mov     rdi, rcx
0x180011cfd  mov     [rbp+var_10], rdx
0x180011d01  lea     r14, [rcx+10h]
0x180011d05  mov     [rbp+var_30], r14
0x180011d09  mov     rcx, r14; _Mtx_t
0x180011d0c  call    cs:__imp__Mtx_lock
0x180011d12  test    eax, eax
0x180011d14  jz      short loc_180011D22
0x180011d16  mov     ecx, 5
0x180011d1b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180011d21  int     3; Trap to Debugger
0x180011d22  mov     eax, [r14+4Ch]
0x180011d26  cmp     eax, 7FFFFFFFh
0x180011d2b  jnz     short loc_180011D3F
0x180011d2d  dec     eax
0x180011d2f  mov     [r14+4Ch], eax
0x180011d33  mov     ecx, 6
0x180011d38  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180011d3e  nop
0x180011d3f  cmp     dword ptr [rdi+7Ch], 1
0x180011d43  jz      short loc_180011D4A
0x180011d45  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180011d4a  mov     [rbp+var_18], 0
0x180011d51  lea     rcx, [rbp+var_18]
0x180011d55  call    cs:__imp_CoGetSharedServiceId
0x180011d5b  mov     rcx, [rbp+38h]; this
0x180011d5f  test    eax, eax
0x180011d61  js      loc_180012045
0x180011d67  mov     r13d, [rbp+var_18]
0x180011d6b  mov     [rbp+var_48], r13d
0x180011d6f  mov     ecx, r13d
0x180011d72  call    cs:__imp_CoAddRefSharedService
0x180011d78  mov     [rbp+var_44], r13d
0x180011d7c  mov     ecx, 198h; Size
0x180011d81  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011d86  mov     rbx, rax
0x180011d89  mov     [rbp+var_40], rax
0x180011d8d  xorps   xmm0, xmm0
0x180011d90  movups  xmmword ptr [rax], xmm0
0x180011d93  mov     dword ptr [rax+8], 1
0x180011d9a  mov     dword ptr [rax+0Ch], 1
0x180011da1  lea     rax, ??_7?$_Ref_count_obj2@VWorkManager@@@std@@6B@; const std::_Ref_count_obj2<WorkManager>::`vftable'
0x180011da8  mov     [rbx], rax
0x180011dab  lea     rsi, [rbx+10h]
0x180011daf  mov     rcx, rsi; this
0x180011db2  call    ??0WorkManager@@QEAA@XZ; WorkManager::WorkManager(void)
0x180011db7  nop
0x180011db8  test    rsi, rsi
0x180011dbb  jz      short loc_180011E35
0x180011dbd  mov     rax, [rsi+10h]
0x180011dc1  test    rax, rax
0x180011dc4  jz      short loc_180011DCC
0x180011dc6  cmp     dword ptr [rax+8], 0
0x180011dca  jnz     short loc_180011E35
0x180011dcc  lock inc dword ptr [rbx+8]
0x180011dd0  lock inc dword ptr [rbx+0Ch]
0x180011dd4  mov     [rsi+8], rsi
0x180011dd8  mov     rcx, [rsi+10h]
0x180011ddc  mov     [rsi+10h], rbx
0x180011de0  test    rcx, rcx
0x180011de3  jz      short loc_180011DFE
0x180011de5  or      eax, 0FFFFFFFFh
0x180011de8  lock xadd [rcx+0Ch], eax
0x180011ded  cmp     eax, 1
0x180011df0  jnz     short loc_180011DFE
0x180011df2  mov     rax, [rcx]
0x180011df5  mov     rax, [rax+8]
0x180011df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dfe  or      eax, 0FFFFFFFFh
0x180011e01  lock xadd [rbx+8], eax
0x180011e06  cmp     eax, 1
0x180011e09  jnz     short loc_180011E35
0x180011e0b  mov     rax, [rbx]
0x180011e0e  mov     rcx, rbx
0x180011e11  mov     rax, [rax]
0x180011e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e19  or      eax, 0FFFFFFFFh
0x180011e1c  lock xadd [rbx+0Ch], eax
0x180011e21  cmp     eax, 1
0x180011e24  jnz     short loc_180011E35
0x180011e26  mov     rax, [rbx]
0x180011e29  mov     rcx, rbx
0x180011e2c  mov     rax, [rax+8]
0x180011e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e35  mov     [rbp+var_28], rsi
0x180011e39  mov     [rbp+var_20], rbx
0x180011e3d  mov     dword ptr [rbp+var_40], 1
0x180011e44  lea     rdx, [rbp+var_40]
0x180011e48  lea     rcx, [rbp+hObject]
0x180011e4c  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180011e51  nop
0x180011e52  mov     [rbp+var_10], 0
0x180011e5a  lea     rax, [rbp+var_10]
0x180011e5e  mov     qword ptr [rsp+80h+ppv], rax; int
0x180011e63  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180011e6a  xor     edx, edx; pUnkOuter
0x180011e6c  lea     r8d, [rdx+1]; dwClsContext
0x180011e70  lea     rcx, CLSID_GlobalOptions; rclsid
0x180011e77  call    cs:__imp_CoCreateInstance
0x180011e7d  mov     rcx, [rbp+38h]; this
0x180011e81  test    eax, eax
0x180011e83  js      loc_18001205A
0x180011e89  mov     rcx, [rbp+var_10]
0x180011e8d  mov     rax, [rcx]
0x180011e90  mov     edx, 5
0x180011e95  lea     r8d, [rdx-4]
0x180011e99  mov     rax, [rax+18h]
0x180011e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ea2  mov     rcx, [rbp+38h]; this
0x180011ea6  test    eax, eax
0x180011ea8  js      loc_18001206F
0x180011eae  mov     r8, rdi; lpContext
0x180011eb1  lea     rdx, ?_ServiceControlCallback@LanguageOverlayServiceModule@@CAKKKPEAX0@Z; lpHandlerProc
0x180011eb8  mov     rcx, r12; lpServiceName
0x180011ebb  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180011ec1  mov     r12, rax
0x180011ec4  mov     rcx, [rbp+38h]; this
0x180011ec8  test    rax, rax
0x180011ecb  jz      loc_180012084
0x180011ed1  lock inc dword ptr [rbx+8]
0x180011ed5  mov     [rdi+60h], rsi
0x180011ed9  mov     rsi, [rdi+68h]
0x180011edd  mov     [rdi+68h], rbx
0x180011ee1  test    rsi, rsi
0x180011ee4  jz      short loc_180011F1D
0x180011ee6  or      eax, 0FFFFFFFFh
0x180011ee9  lock xadd [rsi+8], eax
0x180011eee  cmp     eax, 1
0x180011ef1  jnz     short loc_180011F1D
0x180011ef3  mov     rax, [rsi]
0x180011ef6  mov     rcx, rsi
0x180011ef9  mov     rax, [rax]
0x180011efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f01  or      eax, 0FFFFFFFFh
0x180011f04  lock xadd [rsi+0Ch], eax
0x180011f09  cmp     eax, 1
0x180011f0c  jnz     short loc_180011F1D
0x180011f0e  mov     rax, [rsi]
0x180011f11  mov     rcx, rsi
0x180011f14  mov     rax, [rax+8]
0x180011f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f1d  mov     eax, [rbp+var_18]
0x180011f20  mov     [rdi+78h], eax
0x180011f23  mov     qword ptr [rdi+7Ch], 2
0x180011f2b  mov     [rdi+88h], r12
0x180011f32  add     rdi, 90h
0x180011f39  lea     rax, [rbp+hObject]
0x180011f3d  cmp     rdi, rax
0x180011f40  jz      short loc_180011F84
0x180011f42  mov     r12, [rbp+hObject]
0x180011f46  mov     rsi, [rdi]
0x180011f49  test    rsi, rsi
0x180011f4c  jz      short loc_180011F79
0x180011f4e  call    cs:__imp_GetLastError
0x180011f54  mov     r13d, eax
0x180011f57  mov     rcx, rsi; hObject
0x180011f5a  call    cs:__imp_CloseHandle
0x180011f60  mov     rcx, [rbp+38h]; this
0x180011f64  test    eax, eax
0x180011f66  jz      loc_180012096
0x180011f6c  mov     ecx, r13d; dwErrCode
0x180011f6f  call    cs:__imp_SetLastError
0x180011f75  mov     r13d, [rbp+var_48]
0x180011f79  mov     [rdi], r12
0x180011f7c  xor     ecx, ecx
0x180011f7e  mov     [rbp+hObject], rcx
0x180011f82  jmp     short loc_180011F88
0x180011f84  mov     rcx, [rbp+hObject]
0x180011f88  mov     [r15], r13d
0x180011f8b  mov     [rbp+var_44], 0
0x180011f92  mov     rdx, [rbp+var_10]
0x180011f96  test    rdx, rdx
0x180011f99  jz      short loc_180011FB6
0x180011f9b  mov     [rbp+var_10], 0
0x180011fa3  mov     rax, [rdx]
0x180011fa6  mov     rcx, rdx
0x180011fa9  mov     rax, [rax+10h]
0x180011fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fb2  mov     rcx, [rbp+hObject]; hObject
0x180011fb6  test    rcx, rcx
0x180011fb9  jz      short loc_180011FC9
0x180011fbb  call    cs:__imp_CloseHandle
0x180011fc1  mov     rcx, [rbp+38h]; this
0x180011fc5  test    eax, eax
0x180011fc7  jz      short loc_180012033
0x180011fc9  or      edi, 0FFFFFFFFh
0x180011fcc  mov     eax, edi
0x180011fce  lock xadd [rbx+8], eax
0x180011fd3  add     eax, edi
0x180011fd5  jnz     short loc_180012000
0x180011fd7  mov     rax, [rbx]
0x180011fda  mov     rcx, rbx
0x180011fdd  mov     rax, [rax]
0x180011fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fe5  mov     eax, edi
0x180011fe7  lock xadd [rbx+0Ch], eax
0x180011fec  add     eax, edi
0x180011fee  jnz     short loc_180012000
0x180011ff0  mov     rdx, [rbx]
0x180011ff3  mov     rcx, rbx
0x180011ff6  mov     rax, [rdx+8]
0x180011ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fff  nop
0x180012000  mov     rcx, r14; _Mtx_t
0x180012003  call    cs:__imp__Mtx_unlock
0x180012009  mov     rax, r15
0x18001200c  mov     rcx, [rbp+var_8]
0x180012010  xor     rcx, rsp; StackCookie
0x180012013  call    __security_check_cookie
0x180012018  mov     rbx, [rsp+80h+arg_18]
0x180012020  add     rsp, 80h
0x180012027  pop     r15
0x180012029  pop     r14
0x18001202b  pop     r13
0x18001202d  pop     r12
0x18001202f  pop     rdi
0x180012030  pop     rsi
0x180012031  pop     rbp
0x180012032  retn
0x180012033  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001203a  mov     edx, 0A0Bh; void *
0x18001203f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012045  mov     r9d, eax; char *
0x180012048  lea     r8, aOnecoreBaseLan_5; "onecore\\base\\languageoverlay\\service"...
0x18001204f  mov     edx, 0B3h; void *
0x180012054  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001205a  mov     r9d, eax; char *
0x18001205d  lea     r8, aOnecoreBaseLan_5; "onecore\\base\\languageoverlay\\service"...
0x180012064  mov     edx, 0C5h; void *
0x180012069  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001206f  mov     r9d, eax; char *
0x180012072  lea     r8, aOnecoreBaseLan_5; "onecore\\base\\languageoverlay\\service"...
0x180012079  mov     edx, 0C6h; void *
0x18001207e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012084  lea     r8, aOnecoreBaseLan_5; "onecore\\base\\languageoverlay\\service"...
0x18001208b  mov     edx, 0CDh; void *
0x180012090  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180012096  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001209d  mov     edx, 0A0Bh; void *
0x1800120a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
