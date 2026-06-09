# CPipeManager::ThreadPoolWorker(ITSAsyncResult *,unsigned __int64)

- ea: `0x18009f840`
- end: `0x18009fb5b`
- name: `?ThreadPoolWorker@CPipeManager@@MEAAJPEAVITSAsyncResult@@_K@Z`
- size: `795`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this, struct ITSAsyncResult *, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180096c70`

## callees

- `0x180001308`
- `0x1800023e4`
- `0x18000ce04`
- `0x18000ce34`
- `0x18002aafc`
- `0x18004f5bc`
- `0x180056260`
- `0x18009d304`
- `0x18009f840`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009f859`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009faa4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009f859`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009faa4`

## string_xrefs

- `0x18009f893`: `CPipeManager is already terminated. Skipping ThreadPoolWorker call.`
- `0x18009f8c3`: `CollabEnableRdpThreadsDpiAwareness`
- `0x18009f8e8`: `Getting RDPAPI_PROP_COLLAB_ENABLE_RDP_THREADS_DPI_AWARENESS property failed. This is expected for non collab scenario.`
- `0x18009f937`: `Current thread DPI awareness`
- `0x18009f9e1`: `TriggeredByEvent set in ThreadPoolWorker.`
- `0x18009fa2c`: `ThreadPoolWorker called while not fully initialized. Flush won't be called.`
- `0x18009fa7a`: `Calling Flush from ThreadPoolWorker.`
- `0x18009fabe`: `Flush completed from ThreadPoolWorker.`
- `0x18009fafd`: `Calling FireOnSignaledEvent from ThreadPoolWorker.`

## pseudocode

```c
__int64 __fastcall CPipeManager::ThreadPoolWorker(CPipeManager *this, struct ITSAsyncResult *a2, __int64 a3)
{
  ULONGLONG TickCount64; // rax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rbx
  bool v10; // zf
  ULONGLONG v11; // r15
  struct DPI_AWARENESS_CONTEXT__ *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  struct DPI_AWARENESS_CONTEXT__ *v15; // rax
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rdi
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // edi
  ULONGLONG v26; // rax
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  int v31; // [rsp+40h] [rbp-20h] BYREF
  __int64 v32; // [rsp+48h] [rbp-18h] BYREF
  __int64 v33; // [rsp+50h] [rbp-10h] BYREF
  const char *v34; // [rsp+58h] [rbp-8h] BYREF
  int v35; // [rsp+90h] [rbp+30h] BYREF
  int v36; // [rsp+A0h] [rbp+40h] BYREF
  const char *v37; // [rsp+A8h] [rbp+48h] BYREF

  TickCount64 = GetTickCount64();
  v9 = 0;
  v36 = 1;
  v10 = (*((_BYTE *)this + 84) & 4) == 0;
  v11 = TickCount64;
  v35 = 0;
  v33 = 0;
  v32 = 0;
  if ( v10 )
  {
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, int *))(**((_QWORD **)this + 1627) + 32LL))(
           *((_QWORD *)this + 1627),
           L"CollabEnableRdpThreadsDpiAwareness",
           &v35) < 0 )
    {
      v35 = 0;
      if ( (unsigned int)CallbackContext > 5 )
      {
        v37 = "Getting RDPAPI_PROP_COLLAB_ENABLE_RDP_THREADS_DPI_AWARENESS property failed. This is expected for non collab scenario.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v12,
          (unsigned int)&word_18027A84E,
          v13,
          v14,
          (__int64)&v37);
      }
    }
    if ( v35 )
    {
      v15 = DpiAwarenessApiWrapper::SetThreadDpiAwarenessContext(v12);
      if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(v37) = (unsigned __int8)v15 & 0xF;
        v31 = v15 != 0 ? 2 : 0;
        v34 = "Current thread DPI awareness";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v37,
          (unsigned int)qword_18027A818,
          v16,
          v17,
          (__int64)&v34,
          (__int64)&v31,
          (__int64)&v37);
      }
    }
    v37 = (char *)this + 48896;
    CTSCriticalSection::Lock((CPipeManager *)((char *)this + 48896));
    if ( *((_QWORD *)this + 1618) )
    {
      TCntPtr<IRdpVCMgr>::SafeRelease(&v33);
      v18 = *((_QWORD *)this + 1618);
      v33 = v18;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v33);
    }
    else
    {
      v18 = 0;
    }
    if ( *((_QWORD *)this + 1619) )
    {
      TCntPtr<IRdpVCMgr>::SafeRelease(&v32);
      v9 = *((_QWORD *)this + 1619);
      v32 = v9;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v32);
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v37);
    if ( a3 == 1 && v18 )
    {
      if ( (unsigned int)CallbackContext > 5 )
      {
        v37 = "TriggeredByEvent set in ThreadPoolWorker.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v19,
          (unsigned int)&word_18027A7F6,
          v20,
          v21,
          (__int64)&v37);
      }
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 24LL))(v18, &v36);
    }
    if ( !*((_DWORD *)this + 3242) && (unsigned int)CallbackContext > 3 )
    {
      v37 = "ThreadPoolWorker called while not fully initialized. Flush won't be called.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v19,
        (unsigned int)&dword_18027A7D4,
        v20,
        v21,
        (__int64)&v37);
    }
    if ( v36 && *((_DWORD *)this + 3242) )
    {
      v34 = (char *)this + 12960;
      CTSCriticalSection::Lock((CPipeManager *)((char *)this + 12960));
      if ( (unsigned int)CallbackContext > 5 )
      {
        v37 = "Calling Flush from ThreadPoolWorker.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v22,
          (unsigned int)word_18027A7B2,
          v23,
          v24,
          (__int64)&v37);
      }
      do
      {
        v25 = CPipeManager::Flush(this);
        v26 = GetTickCount64();
      }
      while ( !v25 && v11 == v26 );
      if ( (unsigned int)CallbackContext > 5 )
      {
        v37 = "Flush completed from ThreadPoolWorker.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v27,
          (unsigned int)qword_18027A790,
          v28,
          v29,
          (__int64)&v37);
      }
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v34);
    }
    if ( a3 == 1 && v9 )
    {
      if ( (unsigned int)CallbackContext > 5 )
      {
        v37 = "Calling FireOnSignaledEvent from ThreadPoolWorker.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v19,
          (unsigned int)&word_18027A76E,
          v20,
          v21,
          (__int64)&v37);
      }
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 32LL))(v9, *((_QWORD *)this + 1617));
    }
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    v37 = "CPipeManager is already terminated. Skipping ThreadPoolWorker call.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v6,
      (unsigned int)qword_18027A870,
      v7,
      v8,
      (__int64)&v37);
  }
  TCntPtr<IRdpVCMgr>::SafeRelease(&v32);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v33);
  return 0;
}

```

## disassembly

```asm
0x18009f840  mov     [rsp-28h+arg_8], rbx
0x18009f845  push    rbp
0x18009f846  push    rsi
0x18009f847  push    rdi
0x18009f848  push    r14
0x18009f84a  push    r15
0x18009f84c  mov     rbp, rsp
0x18009f84f  sub     rsp, 60h
0x18009f853  mov     r14, r8
0x18009f856  mov     rsi, rcx
0x18009f859  call    cs:__imp_GetTickCount64
0x18009f85f  xor     ebx, ebx
0x18009f861  mov     [rbp+arg_10], 1
0x18009f868  test    byte ptr [rsi+54h], 4
0x18009f86c  mov     r15, rax
0x18009f86f  mov     [rbp+arg_0], 0
0x18009f876  mov     [rbp+var_10], 0
0x18009f87e  mov     [rbp+var_18], rbx
0x18009f882  jz      short loc_18009F8B8
0x18009f884  mov     eax, cs:CallbackContext
0x18009f88a  cmp     eax, 4
0x18009f88d  jbe     loc_18009FB33
0x18009f893  lea     rax, aCpipemanagerIs; "CPipeManager is already terminated. Ski"...
0x18009f89a  mov     [rbp+arg_18], rax
0x18009f89e  lea     rdx, qword_18027A870
0x18009f8a5  lea     rax, [rbp+arg_18]
0x18009f8a9  mov     [rsp+60h+var_40], rax
0x18009f8ae  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009f8b3  jmp     loc_18009FB33
0x18009f8b8  mov     rcx, [rsi+32D8h]
0x18009f8bf  lea     r8, [rbp+arg_0]
0x18009f8c3  lea     rdx, aCollabenablerd; "CollabEnableRdpThreadsDpiAwareness"
0x18009f8ca  mov     rax, [rcx]
0x18009f8cd  mov     rax, [rax+20h]
0x18009f8d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f8d6  test    eax, eax
0x18009f8d8  jns     short loc_18009F908
0x18009f8da  mov     eax, cs:CallbackContext
0x18009f8e0  mov     [rbp+arg_0], ebx
0x18009f8e3  cmp     eax, 5
0x18009f8e6  jbe     short loc_18009F908
0x18009f8e8  lea     rax, aGettingRdpapiP; "Getting RDPAPI_PROP_COLLAB_ENABLE_RDP_T"...
0x18009f8ef  mov     [rbp+arg_18], rax
0x18009f8f3  lea     rdx, word_18027A84E
0x18009f8fa  lea     rax, [rbp+arg_18]
0x18009f8fe  mov     [rsp+60h+var_40], rax
0x18009f903  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009f908  cmp     [rbp+arg_0], ebx
0x18009f90b  jz      short loc_18009F962
0x18009f90d  call    ?SetThreadDpiAwarenessContext@DpiAwarenessApiWrapper@@SAPEAUDPI_AWARENESS_CONTEXT__@@PEAU2@@Z; DpiAwarenessApiWrapper::SetThreadDpiAwarenessContext(DPI_AWARENESS_CONTEXT__ *)
0x18009f912  mov     ecx, cs:CallbackContext
0x18009f918  cmp     ecx, 4
0x18009f91b  jbe     short loc_18009F962
0x18009f91d  mov     ecx, eax
0x18009f91f  lea     rdx, qword_18027A818
0x18009f926  and     ecx, 0Fh
0x18009f929  neg     rax
0x18009f92c  mov     dword ptr [rbp+arg_18], ecx
0x18009f92f  sbb     eax, eax
0x18009f931  and     eax, 2
0x18009f934  mov     [rbp+var_20], eax
0x18009f937  lea     rax, aCurrentThreadD; "Current thread DPI awareness"
0x18009f93e  mov     [rbp+var_8], rax
0x18009f942  lea     rax, [rbp+arg_18]
0x18009f946  mov     [rsp+60h+var_30], rax
0x18009f94b  lea     rax, [rbp+var_20]
0x18009f94f  mov     [rsp+60h+var_38], rax
0x18009f954  lea     rax, [rbp+var_8]
0x18009f958  mov     [rsp+60h+var_40], rax
0x18009f95d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009f962  lea     rcx, [rsi+0BF00h]; this
0x18009f969  mov     [rbp+arg_18], rcx
0x18009f96d  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18009f972  cmp     [rsi+3290h], rbx
0x18009f979  jnz     short loc_18009F97F
0x18009f97b  xor     edi, edi
0x18009f97d  jmp     short loc_18009F99C
0x18009f97f  lea     rcx, [rbp+var_10]
0x18009f983  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009f988  mov     rdi, [rsi+3290h]
0x18009f98f  lea     rcx, [rbp+var_10]
0x18009f993  mov     [rbp+var_10], rdi
0x18009f997  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18009f99c  cmp     [rsi+3298h], rbx
0x18009f9a3  jz      short loc_18009F9C2
0x18009f9a5  lea     rcx, [rbp+var_18]
0x18009f9a9  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009f9ae  mov     rbx, [rsi+3298h]
0x18009f9b5  lea     rcx, [rbp+var_18]
0x18009f9b9  mov     [rbp+var_18], rbx
0x18009f9bd  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18009f9c2  lea     rcx, [rbp+arg_18]; this
0x18009f9c6  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18009f9cb  cmp     r14, 1
0x18009f9cf  jnz     short loc_18009FA14
0x18009f9d1  test    rdi, rdi
0x18009f9d4  jz      short loc_18009FA14
0x18009f9d6  mov     eax, cs:CallbackContext
0x18009f9dc  cmp     eax, 5
0x18009f9df  jbe     short loc_18009FA01
0x18009f9e1  lea     rax, aTriggeredbyeve; "TriggeredByEvent set in ThreadPoolWorke"...
0x18009f9e8  mov     [rbp+arg_18], rax
0x18009f9ec  lea     rdx, word_18027A7F6
0x18009f9f3  lea     rax, [rbp+arg_18]
0x18009f9f7  mov     [rsp+60h+var_40], rax
0x18009f9fc  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009fa01  mov     rax, [rdi]
0x18009fa04  lea     rdx, [rbp+arg_10]
0x18009fa08  mov     rcx, rdi
0x18009fa0b  mov     rax, [rax+18h]
0x18009fa0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fa14  lea     rdi, [rsi+32A0h]
0x18009fa1b  cmp     dword ptr [rdi+8], 0
0x18009fa1f  jnz     short loc_18009FA4C
0x18009fa21  mov     eax, cs:CallbackContext
0x18009fa27  cmp     eax, 3
0x18009fa2a  jbe     short loc_18009FA4C
0x18009fa2c  lea     rax, aThreadpoolwork; "ThreadPoolWorker called while not fully"...
0x18009fa33  mov     [rbp+arg_18], rax
0x18009fa37  lea     rdx, dword_18027A7D4
0x18009fa3e  lea     rax, [rbp+arg_18]
0x18009fa42  mov     [rsp+60h+var_40], rax
0x18009fa47  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009fa4c  cmp     [rbp+arg_10], 0
0x18009fa50  jz      loc_18009FAE7
0x18009fa56  cmp     dword ptr [rsi+32A8h], 0
0x18009fa5d  jz      loc_18009FAE7
0x18009fa63  mov     rcx, rdi; this
0x18009fa66  mov     [rbp+var_8], rdi
0x18009fa6a  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18009fa6f  mov     eax, cs:CallbackContext
0x18009fa75  cmp     eax, 5
0x18009fa78  jbe     short loc_18009FA9A
0x18009fa7a  lea     rax, aCallingFlushFr; "Calling Flush from ThreadPoolWorker."
0x18009fa81  mov     [rbp+arg_18], rax
0x18009fa85  lea     rdx, word_18027A7B2
0x18009fa8c  lea     rax, [rbp+arg_18]
0x18009fa90  mov     [rsp+60h+var_40], rax
0x18009fa95  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009fa9a  mov     rcx, rsi; this
0x18009fa9d  call    ?Flush@CPipeManager@@UEAAJXZ; CPipeManager::Flush(void)
0x18009faa2  mov     edi, eax
0x18009faa4  call    cs:__imp_GetTickCount64
0x18009faaa  test    edi, edi
0x18009faac  jnz     short loc_18009FAB3
0x18009faae  cmp     r15, rax
0x18009fab1  jz      short loc_18009FA9A
0x18009fab3  mov     eax, cs:CallbackContext
0x18009fab9  cmp     eax, 5
0x18009fabc  jbe     short loc_18009FADE
0x18009fabe  lea     rax, aFlushCompleted; "Flush completed from ThreadPoolWorker."
0x18009fac5  mov     [rbp+arg_18], rax
0x18009fac9  lea     rdx, qword_18027A790
0x18009fad0  lea     rax, [rbp+arg_18]
0x18009fad4  mov     [rsp+60h+var_40], rax
0x18009fad9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009fade  lea     rcx, [rbp+var_8]; this
0x18009fae2  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18009fae7  cmp     r14, 1
0x18009faeb  jnz     short loc_18009FB33
0x18009faed  test    rbx, rbx
0x18009faf0  jz      short loc_18009FB33
0x18009faf2  mov     eax, cs:CallbackContext
0x18009faf8  cmp     eax, 5
0x18009fafb  jbe     short loc_18009FB1D
0x18009fafd  lea     rax, aCallingFireons_0; "Calling FireOnSignaledEvent from Thread"...
0x18009fb04  mov     [rbp+arg_18], rax
0x18009fb08  lea     rdx, word_18027A76E
0x18009fb0f  lea     rax, [rbp+arg_18]
0x18009fb13  mov     [rsp+60h+var_40], rax
0x18009fb18  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009fb1d  mov     rax, [rbx]
0x18009fb20  mov     rcx, rbx
0x18009fb23  mov     rdx, [rsi+3288h]
0x18009fb2a  mov     rax, [rax+20h]
0x18009fb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fb33  lea     rcx, [rbp+var_18]
0x18009fb37  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009fb3c  lea     rcx, [rbp+var_10]
0x18009fb40  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009fb45  mov     rbx, [rsp+60h+arg_8]
0x18009fb4d  xor     eax, eax
0x18009fb4f  add     rsp, 60h
0x18009fb53  pop     r15
0x18009fb55  pop     r14
0x18009fb57  pop     rdi
0x18009fb58  pop     rsi
0x18009fb59  pop     rbp
0x18009fb5a  retn
```
