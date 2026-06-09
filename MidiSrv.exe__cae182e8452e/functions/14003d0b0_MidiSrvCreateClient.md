# MidiSrvCreateClient

- ea: `0x14003d0b0`
- end: `0x14003d853`
- name: `MidiSrvCreateClient`
- size: `1955`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, __int64, __int64, _OWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400018e4`
- `0x1400054c0`
- `0x140005868`
- `0x1400058d0`
- `0x1400060ec`
- `0x1400060f8`
- `0x1400072d4`
- `0x140007c20`
- `0x1400091a4`
- `0x14000984c`
- `0x14000a694`
- `0x14000a6b4`
- `0x1400144ac`
- `0x1400152d0`
- `0x14001f64c`
- `0x14001fa84`
- `0x1400261b4`
- `0x14003c874`
- `0x14003cd6c`
- `0x14003d0b0`
- `0x140045eb4`
- `0x14005a010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x14003d44a`
- `RPCRT4!RpcRevertToSelf` at `0x14003d454`
- `RPCRT4!RpcRevertToSelf` at `0x14003d44a`
- `RPCRT4!RpcRevertToSelf` at `0x14003d454`
- `RPCRT4!RpcImpersonateClient` at `0x14003d3e9`
- `RPCRT4!RpcImpersonateClient` at `0x14003d3f6`
- `RPCRT4!RpcImpersonateClient` at `0x14003d3e9`
- `RPCRT4!RpcImpersonateClient` at `0x14003d3f6`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003d32b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003d341`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003d32b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003d341`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003d43d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003d43d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d42a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d42a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003d245`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003d245`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003d412`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003d412`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d379`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d435`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d4a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d69f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d77a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d379`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d435`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d4a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d69f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d77a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d2b6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d390`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d4b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d6b6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d789`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d2b6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d390`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d4b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d6b6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d789`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003d1e4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003d1e4`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14003d55f`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14003d55f`

## string_xrefs

- `0x14003d841`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14003d29d`: `avcore\midi2\service\exe\midisrvrpc.cpp`
- `0x14003d354`: `avcore\midi2\service\exe\midisrvrpc.cpp`
- `0x14003d47f`: `avcore\midi2\service\exe\midisrvrpc.cpp`
- `0x14003d676`: `avcore\midi2\service\exe\midisrvrpc.cpp`
- `0x14003d116`: `MidiSrvCreateClient`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MidiSrvCreateClient(
        RPC_BINDING_HANDLE BindingHandle,
        __int64 a2,
        __int64 a3,
        _OWORD *a4,
        _QWORD *a5)
{
  _DWORD *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  CMidiSrv *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rcx
  volatile signed __int32 *v13; // rbx
  HRESULT v14; // eax
  __int64 v15; // rdx
  __int64 *Local; // rax
  void *v17; // rax
  void *v18; // rsi
  unsigned int v19; // edi
  volatile signed __int32 *v20; // rbx
  RPC_STATUS v22; // eax
  __int64 v23; // rdx
  HANDLE v24; // r14
  HANDLE v25; // rdi
  DWORD LastError; // ebx
  const char *v27; // r9
  WCHAR *v28; // r8
  LPWSTR *v29; // rdx
  _QWORD *v30; // rax
  __int64 v31; // r8
  unsigned __int64 v32; // rdx
  void **v33; // rdi
  __int64 v34; // rbx
  int MidiClient; // eax
  volatile signed __int32 *v36; // rbx
  __int64 v37; // rcx
  int v38; // edx
  void **v39; // r9
  volatile signed __int32 *v40; // rbx
  volatile signed __int32 *v41; // rbx
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  unsigned int Pid; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v46; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v47; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+68h] [rbp-98h] BYREF
  __int64 v49; // [rsp+70h] [rbp-90h] BYREF
  PSRWLOCK SRWLock[3]; // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall **v51)(); // [rsp+90h] [rbp-70h] BYREF
  _QWORD v52[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-58h]
  DWORD CurrentThreadId; // [rsp+B0h] [rbp-50h]
  __int64 v55; // [rsp+B8h] [rbp-48h]
  char v56; // [rsp+C0h] [rbp-40h]
  __int128 *v57; // [rsp+C8h] [rbp-38h]
  __int64 *v58; // [rsp+D0h] [rbp-30h]
  void **v59; // [rsp+D8h] [rbp-28h]
  __int64 *v60; // [rsp+E0h] [rbp-20h]
  const wchar_t *v61; // [rsp+F0h] [rbp-10h] BYREF
  void *v62[2]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v63; // [rsp+108h] [rbp+8h]
  unsigned __int64 v64; // [rsp+110h] [rbp+10h]
  LPWSTR lpFilename[2]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v66; // [rsp+128h] [rbp+28h]
  DWORD nSize[4]; // [rsp+130h] [rbp+30h]
  _OWORD v68[2]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v69[32]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v49 = a2;
  v48 = a3;
  v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    v61 = L"Enter";
    *(_QWORD *)&v68[0] = 0;
    SRWLock[0] = (PSRWLOCK)"MidiSrvCreateClient";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v7,
      (unsigned int)&dword_14008B27C,
      v8,
      v9,
      (__int64)SRWLock,
      (__int64)v68,
      (__int64)&v61);
  }
  *(_OWORD *)SRWLock = 0;
  v47 = 0;
  v10 = g_MidiService;
  v11 = *((_QWORD *)g_MidiService + 15);
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  v12 = *((_QWORD *)v10 + 15);
  *(_QWORD *)&v47 = *((_QWORD *)v10 + 14);
  v13 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
  *((_QWORD *)&v47 + 1) = v12;
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  *(_OWORD *)v62 = 0;
  v63 = 0;
  v64 = 7;
  LOWORD(v62[0]) = 0;
  v14 = CoInitializeEx(0, 0);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v14,
      v42);
  v51 = off_14005BA00;
  v52[0] = 0;
  v52[1] = &v51;
  v53 = 0;
  CurrentThreadId = 0;
  v55 = 0;
  v56 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v15) = 1;
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         retaddr,
                         v15);
    v52[0] = Local;
    if ( Local )
    {
      v53 = *Local;
      *Local = (__int64)v52;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  v57 = &v47;
  v58 = &v49;
  v59 = v62;
  v60 = &v48;
  v17 = operator new[](0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v18 = v17;
  if ( !v17 )
  {
    v19 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      (const char *)0x8007000ELL,
      v42);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v52);
    CoUninitialize();
    std::wstring::~wstring(v62);
    v20 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
    if ( !*((_QWORD *)&v47 + 1) )
      return v19;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) != 1 )
      return v19;
    (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
    if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) != 1 )
      return v19;
    goto LABEL_17;
  }
  memset_0(v17, 0, 0x58u);
  Pid = 0;
  hObject = 0;
  if ( I_RpcBindingInqLocalClientPID(BindingHandle, &Pid) )
  {
    v22 = I_RpcBindingInqLocalClientPID(BindingHandle, &Pid);
    v23 = 161;
    goto LABEL_21;
  }
  if ( RpcImpersonateClient(BindingHandle) )
  {
    v22 = RpcImpersonateClient(BindingHandle);
    v23 = 165;
    goto LABEL_21;
  }
  v24 = OpenProcess(0x448u, 0, Pid);
  v25 = hObject;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v25);
    SetLastError(LastError);
  }
  hObject = v24;
  if ( RpcRevertToSelf() )
  {
    v22 = RpcRevertToSelf();
    v23 = 167;
LABEL_21:
    v19 = v22 | 0x80010000;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      (const char *)(v22 | 0x80010000),
      v42);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v52);
    operator delete(v18);
    CoUninitialize();
    std::wstring::~wstring(v62);
    v20 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
    if ( !*((_QWORD *)&v47 + 1) )
      return v19;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) != 1 )
      return v19;
    (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
    if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) != 1 )
      return v19;
LABEL_17:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    return v19;
  }
  if ( (((unsigned __int64)hObject + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v19 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xA8,
            (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
            v27);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v52);
    operator delete(v18);
    CoUninitialize();
    std::wstring::~wstring(v62);
    v20 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
    goto LABEL_37;
  }
  v46 = 0;
  *(_OWORD *)lpFilename = 0;
  v66 = 0;
  *(_QWORD *)nSize = 0;
  std::wstring::_Construct<1,unsigned short const *>(lpFilename, &v46, 1);
  std::wstring::resize(lpFilename);
  v28 = (WCHAR *)lpFilename;
  if ( *(_QWORD *)nSize > 7u )
    v28 = lpFilename[0];
  if ( K32GetModuleFileNameExW(hObject, 0, v28, nSize[0]) )
  {
    v29 = lpFilename;
    if ( *(_QWORD *)nSize > 7u )
      v29 = (LPWSTR *)lpFilename[0];
    memset(v68, 0, sizeof(v68));
    std::wstring::_Construct<1,unsigned short const *>(v68, v29, v66);
    v30 = (_QWORD *)std::filesystem::path::filename(v68, v69);
    if ( v30[3] > 7u )
      v30 = (_QWORD *)*v30;
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v30 + v32) );
    if ( v32 > v64 )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        v62,
        v32,
        v31,
        v30);
    }
    else
    {
      v33 = v62;
      if ( v64 > 7 )
        v33 = (void **)v62[0];
      v63 = v32;
      v34 = 2 * v32;
      memmove_0(v33, v30, 2 * v32);
      *(_WORD *)((char *)v33 + v34) = 0;
    }
    std::wstring::~wstring(v69);
    std::wstring::~wstring(v68);
  }
  std::shared_ptr<CMidiSessionTracker>::operator=(SRWLock, (char *)g_MidiService + 48);
  v68[0] = *a4;
  MidiClient = CMidiClientManager::CreateMidiClient(SRWLock[0], (__int64)&hObject, v48, (__int64)v18);
  v19 = MidiClient;
  if ( MidiClient < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      (const char *)(unsigned int)MidiClient,
      v43);
    std::wstring::~wstring(lpFilename);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v52);
    operator delete(v18);
    CoUninitialize();
    std::wstring::~wstring(v62);
    v36 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
    if ( *((_QWORD *)&v47 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
        if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
      }
    }
    v20 = (volatile signed __int32 *)SRWLock[1];
LABEL_37:
    if ( !v20 )
      return v19;
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) != 1 )
      return v19;
    (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
    if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) != 1 )
      return v19;
    goto LABEL_17;
  }
  *a5 = v18;
  if ( (_QWORD)v47 )
  {
    v37 = *(unsigned int *)(v48 + 4);
    v38 = *(_DWORD *)(v48 + 8);
    v39 = v62;
    if ( v64 > 7 )
      v39 = (void **)v62[0];
    v68[0] = *(_OWORD *)(v48 + 16);
    CMidiSrvTraceLogger::LogMidi2CreateClient(v37, 0, v49, v39, v68, v38, v37, Pid);
  }
  std::wstring::~wstring(lpFilename);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v52);
  CoUninitialize();
  std::wstring::~wstring(v62);
  v40 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
  if ( *((_QWORD *)&v47 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
      if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
    }
  }
  v41 = (volatile signed __int32 *)SRWLock[1];
  if ( SRWLock[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&SRWLock[1][1], 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
      if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14003d0b0  push    rbp
0x14003d0b2  push    rbx
0x14003d0b3  push    rsi
0x14003d0b4  push    rdi
0x14003d0b5  push    r12
0x14003d0b7  push    r13
0x14003d0b9  push    r14
0x14003d0bb  push    r15
0x14003d0bd  lea     rbp, [rsp-98h]
0x14003d0c5  sub     rsp, 198h
0x14003d0cc  mov     rax, cs:__security_cookie
0x14003d0d3  xor     rax, rsp
0x14003d0d6  mov     [rbp+0D0h+var_50], rax
0x14003d0dd  mov     r12, r9
0x14003d0e0  mov     rdi, rcx
0x14003d0e3  mov     [rsp+1D0h+var_160], rdx
0x14003d0e8  mov     [rsp+1D0h+var_168], r8
0x14003d0ed  mov     r15, [rbp+0D0h+arg_20]
0x14003d0f4  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003d0f9  mov     rcx, [rax+8]
0x14003d0fd  mov     eax, [rcx]
0x14003d0ff  xor     r14d, r14d
0x14003d102  cmp     eax, 4
0x14003d105  jbe     short loc_14003D14A
0x14003d107  lea     rax, aEnter; "Enter"
0x14003d10e  mov     [rbp+0D0h+var_E0], rax
0x14003d112  mov     qword ptr [rbp+0D0h+var_90], r14
0x14003d116  lea     rax, aMidisrvcreatec; "MidiSrvCreateClient"
0x14003d11d  mov     [rsp+1D0h+SRWLock], rax
0x14003d122  lea     rax, [rbp+0D0h+var_E0]
0x14003d126  mov     [rsp+1D0h+var_1A0], rax
0x14003d12b  lea     rax, [rbp+0D0h+var_90]
0x14003d12f  mov     [rsp+1D0h+var_1A8], rax
0x14003d134  lea     rax, [rsp+1D0h+SRWLock]
0x14003d139  mov     [rsp+1D0h+var_1B0], rax; int
0x14003d13e  lea     rdx, dword_14008B27C
0x14003d145  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003d14a  xorps   xmm0, xmm0
0x14003d14d  movdqu  xmmword ptr [rsp+1D0h+SRWLock], xmm0
0x14003d153  xorps   xmm1, xmm1
0x14003d156  movdqu  [rsp+1D0h+var_178], xmm1
0x14003d15c  mov     rdx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14003d163  mov     rax, [rdx+78h]
0x14003d167  test    rax, rax
0x14003d16a  jz      short loc_14003D170
0x14003d16c  lock inc dword ptr [rax+8]
0x14003d170  mov     rcx, [rdx+78h]
0x14003d174  mov     rax, [rdx+70h]
0x14003d178  mov     qword ptr [rsp+1D0h+var_178], rax
0x14003d17d  mov     rbx, qword ptr [rsp+1D0h+var_178+8]
0x14003d182  mov     qword ptr [rsp+1D0h+var_178+8], rcx
0x14003d187  or      r13, 0FFFFFFFFFFFFFFFFh
0x14003d18b  test    rbx, rbx
0x14003d18e  jz      short loc_14003D1C7
0x14003d190  mov     eax, r13d
0x14003d193  lock xadd [rbx+8], eax
0x14003d198  add     eax, r13d
0x14003d19b  jnz     short loc_14003D1C7
0x14003d19d  mov     rax, [rbx]
0x14003d1a0  mov     rcx, rbx
0x14003d1a3  mov     rax, [rax]
0x14003d1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d1ab  mov     eax, r13d
0x14003d1ae  lock xadd [rbx+0Ch], eax
0x14003d1b3  add     eax, r13d
0x14003d1b6  jnz     short loc_14003D1C7
0x14003d1b8  mov     rax, [rbx]
0x14003d1bb  mov     rcx, rbx
0x14003d1be  mov     rax, [rax+8]
0x14003d1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d1c7  xorps   xmm0, xmm0
0x14003d1ca  movups  xmmword ptr [rbp+0D0h+var_D8], xmm0
0x14003d1ce  xor     ebx, ebx
0x14003d1d0  mov     [rbp+0D0h+var_C8], rbx
0x14003d1d4  mov     [rbp+0D0h+var_C0], 7
0x14003d1dc  mov     word ptr [rbp+0D0h+var_D8], bx
0x14003d1e0  xor     edx, edx; dwCoInit
0x14003d1e2  xor     ecx, ecx; pvReserved
0x14003d1e4  call    cs:__imp_CoInitializeEx
0x14003d1ea  mov     rcx, [rbp+0D8h]; this
0x14003d1f1  test    eax, eax
0x14003d1f3  js      loc_14003D83E
0x14003d1f9  lea     rax, off_14005BA00
0x14003d200  mov     [rbp+0D0h+var_140], rax
0x14003d204  mov     [rbp+0D0h+var_138], rbx
0x14003d208  lea     rax, [rbp+0D0h+var_140]
0x14003d20c  mov     [rbp+0D0h+var_130], rax
0x14003d210  mov     [rbp+0D0h+var_128], rbx
0x14003d214  mov     [rbp+0D0h+var_120], ebx
0x14003d217  mov     [rbp+0D0h+var_118], rbx
0x14003d21b  mov     [rbp+0D0h+var_110], bl
0x14003d21e  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, rbx; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14003d225  jz      short loc_14003D24E
0x14003d227  mov     dl, 1
0x14003d229  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14003d22e  mov     [rbp+0D0h+var_138], rax
0x14003d232  test    rax, rax
0x14003d235  jz      short loc_14003D24E
0x14003d237  mov     rcx, [rax]
0x14003d23a  mov     [rbp+0D0h+var_128], rcx
0x14003d23e  lea     rcx, [rbp+0D0h+var_138]
0x14003d242  mov     [rax], rcx
0x14003d245  call    cs:__imp_GetCurrentThreadId
0x14003d24b  mov     [rbp+0D0h+var_120], eax
0x14003d24e  lea     rax, [rsp+1D0h+var_178]
0x14003d253  mov     [rbp+0D0h+var_108], rax
0x14003d257  lea     rax, [rsp+1D0h+var_160]
0x14003d25c  mov     [rbp+0D0h+var_100], rax
0x14003d260  lea     rax, [rbp+0D0h+var_D8]
0x14003d264  mov     [rbp+0D0h+var_F8], rax
0x14003d268  lea     rax, [rsp+1D0h+var_168]
0x14003d26d  mov     [rbp+0D0h+var_F0], rax
0x14003d271  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003d278  mov     r14d, 58h ; 'X'
0x14003d27e  mov     ecx, r14d; unsigned __int64
0x14003d281  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14003d286  mov     rsi, rax
0x14003d289  test    rax, rax
0x14003d28c  jnz     short loc_14003D30D
0x14003d28e  mov     rcx, [rbp+0D8h]; this
0x14003d295  mov     edi, 8007000Eh
0x14003d29a  mov     r9d, edi; char *
0x14003d29d  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003d2a4  lea     edx, [r14+42h]; void *
0x14003d2a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d2ad  lea     rcx, [rbp+0D0h+var_138]; this
0x14003d2b1  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x14003d2b6  call    cs:__imp_CoUninitialize
0x14003d2bc  lea     rcx, [rbp+0D0h+var_D8]; void *
0x14003d2c0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003d2c5  mov     rbx, qword ptr [rsp+1D0h+var_178+8]
0x14003d2ca  test    rbx, rbx
0x14003d2cd  jz      short loc_14003D306
0x14003d2cf  mov     eax, r13d
0x14003d2d2  lock xadd [rbx+8], eax
0x14003d2d7  add     eax, r13d
0x14003d2da  jnz     short loc_14003D306
0x14003d2dc  mov     rax, [rbx]
0x14003d2df  mov     rcx, rbx
0x14003d2e2  mov     rax, [rax]
0x14003d2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d2ea  mov     ecx, r13d
0x14003d2ed  lock xadd [rbx+0Ch], ecx
0x14003d2f2  add     ecx, r13d
0x14003d2f5  jnz     short loc_14003D306
0x14003d2f7  mov     rcx, [rbx]
0x14003d2fa  mov     rax, [rcx+8]
0x14003d2fe  mov     rcx, rbx
0x14003d301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d306  mov     eax, edi
0x14003d308  jmp     loc_14003D81B
0x14003d30d  mov     r8, r14; Size
0x14003d310  xor     edx, edx; Val
0x14003d312  mov     rcx, rsi; void *
0x14003d315  call    memset_0
0x14003d31a  mov     [rsp+1D0h+Pid], ebx
0x14003d31e  mov     [rsp+1D0h+hObject], rbx
0x14003d323  lea     rdx, [rsp+1D0h+Pid]; Pid
0x14003d328  mov     rcx, rdi; Binding
0x14003d32b  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14003d331  mov     rcx, rdi; BindingHandle
0x14003d334  test    eax, eax
0x14003d336  jz      loc_14003D3E9
0x14003d33c  lea     rdx, [rsp+1D0h+Pid]; Pid
0x14003d341  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14003d347  mov     edx, 0A1h; void *
0x14003d34c  mov     edi, eax
0x14003d34e  or      edi, 80010000h
0x14003d354  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003d35b  mov     r9d, edi; char *
0x14003d35e  mov     rcx, [rbp+0D8h]; this
0x14003d365  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d36a  mov     rcx, [rsp+1D0h+hObject]; hObject
0x14003d36f  lea     rax, [rcx-1]
0x14003d373  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003d377  ja      short loc_14003D37F
0x14003d379  call    cs:__imp_CloseHandle
0x14003d37f  lea     rcx, [rbp+0D0h+var_138]; this
0x14003d383  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x14003d388  mov     rcx, rsi; Block
0x14003d38b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003d390  call    cs:__imp_CoUninitialize
0x14003d396  lea     rcx, [rbp+0D0h+var_D8]; void *
0x14003d39a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003d39f  mov     rbx, qword ptr [rsp+1D0h+var_178+8]
0x14003d3a4  test    rbx, rbx
0x14003d3a7  jz      loc_14003D306
0x14003d3ad  mov     eax, r13d
0x14003d3b0  lock xadd [rbx+8], eax
0x14003d3b5  add     eax, r13d
0x14003d3b8  jnz     loc_14003D306
0x14003d3be  mov     rax, [rbx]
0x14003d3c1  mov     rcx, rbx
0x14003d3c4  mov     rax, [rax]
0x14003d3c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d3cc  mov     edx, r13d
0x14003d3cf  lock xadd [rbx+0Ch], edx
0x14003d3d4  add     edx, r13d
0x14003d3d7  jnz     loc_14003D306
0x14003d3dd  mov     rdx, [rbx]
0x14003d3e0  mov     rax, [rdx+8]
0x14003d3e4  jmp     loc_14003D2FE
0x14003d3e9  call    cs:__imp_RpcImpersonateClient
0x14003d3ef  test    eax, eax
0x14003d3f1  jz      short loc_14003D406
0x14003d3f3  mov     rcx, rdi; BindingHandle
0x14003d3f6  call    cs:__imp_RpcImpersonateClient
0x14003d3fc  mov     edx, 0A5h
0x14003d401  jmp     loc_14003D34C
0x14003d406  mov     r8d, [rsp+1D0h+Pid]; dwProcessId
0x14003d40b  xor     edx, edx; bInheritHandle
0x14003d40d  mov     ecx, 448h; dwDesiredAccess
0x14003d412  call    cs:__imp_OpenProcess
0x14003d418  mov     r14, rax
0x14003d41b  mov     rdi, [rsp+1D0h+hObject]
0x14003d420  lea     rdx, [rdi-1]
0x14003d424  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14003d428  ja      short loc_14003D445
0x14003d42a  call    cs:__imp_GetLastError
0x14003d430  mov     ebx, eax
0x14003d432  mov     rcx, rdi; hObject
0x14003d435  call    cs:__imp_CloseHandle
0x14003d43b  mov     ecx, ebx; dwErrCode
0x14003d43d  call    cs:__imp_SetLastError
0x14003d443  xor     ebx, ebx
0x14003d445  mov     [rsp+1D0h+hObject], r14
0x14003d44a  call    cs:__imp_RpcRevertToSelf
0x14003d450  test    eax, eax
0x14003d452  jz      short loc_14003D464
0x14003d454  call    cs:__imp_RpcRevertToSelf
0x14003d45a  mov     edx, 0A7h
0x14003d45f  jmp     loc_14003D34C
0x14003d464  mov     rax, [rsp+1D0h+hObject]
0x14003d469  inc     rax
0x14003d46c  test    rax, 0FFFFFFFFFFFFFFFEh
0x14003d472  jnz     loc_14003D511
0x14003d478  mov     rcx, [rbp+0D8h]; this
0x14003d47f  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003d486  mov     edx, 0A8h; void *
0x14003d48b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14003d490  mov     edi, eax
0x14003d492  mov     rcx, [rsp+1D0h+hObject]; hObject
0x14003d497  lea     rdx, [rcx-1]
0x14003d49b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14003d49f  ja      short loc_14003D4A7
0x14003d4a1  call    cs:__imp_CloseHandle
0x14003d4a7  lea     rcx, [rbp+0D0h+var_138]; this
0x14003d4ab  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x14003d4b0  mov     rcx, rsi; Block
0x14003d4b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003d4b8  call    cs:__imp_CoUninitialize
0x14003d4be  lea     rcx, [rbp+0D0h+var_D8]; void *
0x14003d4c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003d4c7  mov     rbx, qword ptr [rsp+1D0h+var_178+8]
0x14003d4cc  test    rbx, rbx
0x14003d4cf  jz      loc_14003D306
0x14003d4d5  mov     eax, r13d
0x14003d4d8  lock xadd [rbx+8], eax
0x14003d4dd  add     eax, r13d
0x14003d4e0  jnz     loc_14003D306
0x14003d4e6  mov     rax, [rbx]
0x14003d4e9  mov     rcx, rbx
0x14003d4ec  mov     rax, [rax]
0x14003d4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d4f4  mov     eax, r13d
0x14003d4f7  lock xadd [rbx+0Ch], eax
0x14003d4fc  add     eax, r13d
0x14003d4ff  jnz     loc_14003D306
0x14003d505  mov     rax, [rbx]
0x14003d508  mov     rax, [rax+8]
0x14003d50c  jmp     loc_14003D2FE
0x14003d511  mov     [rsp+1D0h+var_180], bx
0x14003d516  xorps   xmm0, xmm0
0x14003d519  movups  xmmword ptr [rbp+0D0h+lpFilename], xmm0
0x14003d51d  mov     [rbp+0D0h+var_A8], rbx
0x14003d521  mov     qword ptr [rbp+0D0h+nSize], rbx
0x14003d525  mov     r8d, 1
0x14003d52b  lea     rdx, [rsp+1D0h+var_180]
0x14003d530  lea     rcx, [rbp+0D0h+lpFilename]
0x14003d534  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003d539  mov     edx, 105h
0x14003d53e  lea     rcx, [rbp+0D0h+lpFilename]; Src
0x14003d542  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14003d547  mov     r9, qword ptr [rbp+0D0h+nSize]; nSize
0x14003d54b  lea     r8, [rbp+0D0h+lpFilename]
0x14003d54f  cmp     r9, 7
0x14003d553  cmova   r8, [rbp+0D0h+lpFilename]; lpFilename
0x14003d558  xor     edx, edx; hModule
0x14003d55a  mov     rcx, [rsp+1D0h+hObject]; hProcess
0x14003d55f  call    cs:__imp_K32GetModuleFileNameExW
0x14003d565  test    eax, eax
0x14003d567  jz      loc_14003D60E
0x14003d56d  lea     rdx, [rbp+0D0h+lpFilename]
0x14003d571  cmp     qword ptr [rbp+0D0h+nSize], 7
0x14003d576  cmova   rdx, [rbp+0D0h+lpFilename]
0x14003d57b  xorps   xmm0, xmm0
0x14003d57e  movups  [rbp+0D0h+var_90], xmm0
0x14003d582  xorps   xmm1, xmm1
0x14003d585  movdqu  [rbp+0D0h+var_80], xmm1
0x14003d58a  mov     r8, [rbp+0D0h+var_A8]
  ... truncated ...
```
