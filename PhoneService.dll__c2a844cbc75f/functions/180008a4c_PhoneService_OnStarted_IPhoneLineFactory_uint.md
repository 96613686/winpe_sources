# PhoneService::_OnStarted(IPhoneLineFactory * *,uint)

- ea: `0x180008a4c`
- end: `0x180008f3d`
- name: `?_OnStarted@PhoneService@@IEAAJPEAPEAUIPhoneLineFactory@@I@Z`
- size: `1265`
- prototype: `__int64 __fastcall(PhoneService *__hidden this, struct IPhoneLineFactory **, unsigned int)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800075d0`
- `0x180007ba0`

## callees

- `0x1800012b8`
- `0x180005660`
- `0x180006e94`
- `0x180007b04`
- `0x180008570`
- `0x180008a4c`
- `0x180009008`
- `0x18000ec68`
- `0x18001e024`
- `0x18002c580`
- `0x18004c324`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008ad0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008ad0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008dfd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008dfd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008c86`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e07`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180008f11`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180008f11`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180008a83`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180008a83`

## string_xrefs

- `0x180008dd1`: `PhoneService: Phone RPC server started. Setting PhoneApiReady.`
- `0x180008ece`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneService::_OnStarted(PhoneService *this, struct IPhoneLineFactory **a2, int a3)
{
  int v6; // eax
  BackTraceCollection *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // r8
  HRESULT v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  PhoneController *v14; // rax
  BackTraceCollection *v15; // rcx
  PhoneController *v16; // rbx
  struct ATL::CAtlModule *v17; // rcx
  struct InternalSinkMessageDispatcher *v18; // rax
  BackTraceCollection *v19; // rcx
  struct InternalSinkMessageDispatcher *v20; // rbx
  struct ATL::CAtlModule *v21; // rcx
  int Sinks; // eax
  BackTraceCollection *v23; // rcx
  unsigned int v24; // edi
  __int64 v25; // r8
  __int64 v26; // r9
  LPVOID v27; // rcx
  int v28; // eax
  BackTraceCollection *v29; // rcx
  const unsigned __int16 *v30; // rdx
  int v31; // eax
  BackTraceCollection *v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  void *v35; // rcx
  signed int LastError; // eax
  BackTraceCollection *v37; // rcx
  __int64 v38; // r8
  int v39; // eax
  BackTraceCollection *v40; // rcx
  LPVOID v41; // rcx
  __int64 v42; // r8
  BackTraceCollection *v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  BackTraceCollection *v46; // rcx
  LPVOID v47; // rcx
  const char *v48; // [rsp+40h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-18h] BYREF

  v6 = RoInitialize(1);
  v8 = v6;
  if ( v6 < 0 )
  {
    BackTraceCollection::Capture(v7, v6);
    Log_HREvent_0(v8, 1, v9, 200);
    return v8;
  }
  ppv = 0;
  v11 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
    if ( v11 >= 0 )
      goto LABEL_8;
    v13 = 214;
  }
  else
  {
    v13 = 210;
  }
  Log_HREvent_0((unsigned int)v11, 0, v12, v13);
LABEL_8:
  *((_QWORD *)this + 31) = 0;
  v14 = (PhoneController *)operator new(0x2E8u);
  v16 = v14;
  if ( !v14 )
  {
    BackTraceCollection::Capture(v15, -2147024882);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 215);
    BackTraceCollection::Capture(v46, -2147024882);
    v45 = 218;
    goto LABEL_35;
  }
  memset_0(v14, 0, 0x2E8u);
  PhoneController::PhoneController(v16);
  v17 = ATL::_pAtlModule;
  *(_QWORD *)v16 = &ATL::CComObject<PhoneController>::`vftable'{for `IPhoneController'};
  *((_QWORD *)v16 + 1) = &ATL::CComObject<PhoneController>::`vftable'{for `IDialQueueClient'};
  *((_QWORD *)v16 + 2) = &ATL::CComObject<PhoneController>::`vftable'{for `IDispatcherQueueCallback'};
  *((_QWORD *)v16 + 3) = &ATL::CComObject<PhoneController>::`vftable'{for `IOneShotTimerCallback'};
  *((_QWORD *)v16 + 4) = &ATL::CComObject<PhoneController>::`vftable'{for `IAudioRoutingStateChangeListener'};
  *((_QWORD *)v16 + 5) = &ATL::CComObject<PhoneController>::`vftable'{for `IRecordingStateChangeListener'};
  *((_QWORD *)v16 + 6) = &ATL::CComObject<PhoneController>::`vftable'{for `ISimpleModemCompletion'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v17 + 8LL))(v17);
  (*(void (__fastcall **)(PhoneController *))(*(_QWORD *)v16 + 8LL))(v16);
  (*(void (__fastcall **)(PhoneController *))(*(_QWORD *)v16 + 8LL))(v16);
  *((_QWORD *)this + 31) = v16;
  (*(void (__fastcall **)(PhoneController *))(*(_QWORD *)v16 + 16LL))(v16);
  v18 = (struct InternalSinkMessageDispatcher *)operator new(0xF0u);
  v20 = v18;
  if ( !v18 )
  {
    BackTraceCollection::Capture(v19, -2147024882);
    Log_HREvent_2(2147942414LL, 1, v42, 25);
    BackTraceCollection::Capture(v43, -2147024882);
    v45 = 223;
LABEL_35:
    Log_HREvent_0(2147942414LL, 1, v44, v45);
    v47 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v47 + 16LL))(v47);
    }
    v24 = -2147024882;
    goto LABEL_38;
  }
  memset_0(v18, 0, 0xF0u);
  *((_DWORD *)v20 + 48) = 1;
  *(_QWORD *)v20 = &InternalSinkMessageDispatcher::`vftable';
  *((_QWORD *)v20 + 3) = -1;
  *((_QWORD *)v20 + 4) = -1;
  *((_QWORD *)v20 + 5) = -1;
  *((_QWORD *)v20 + 6) = -1;
  *((_QWORD *)v20 + 7) = -1;
  *((_QWORD *)v20 + 8) = -1;
  *((_QWORD *)v20 + 9) = -1;
  *((_QWORD *)v20 + 10) = -1;
  *((_QWORD *)v20 + 11) = -1;
  *((_QWORD *)v20 + 12) = -1;
  *((_QWORD *)v20 + 13) = -1;
  *((_QWORD *)v20 + 14) = -1;
  *((_QWORD *)v20 + 15) = -1;
  *((_QWORD *)v20 + 16) = -1;
  *((_QWORD *)v20 + 17) = -1;
  *((_QWORD *)v20 + 18) = -1;
  *((_QWORD *)v20 + 19) = -1;
  *((_QWORD *)v20 + 20) = -1;
  *((_QWORD *)v20 + 21) = -1;
  *((_QWORD *)v20 + 22) = -1;
  *((_QWORD *)v20 + 23) = -1;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)v20 + 5, 0, 0);
  v21 = ATL::_pAtlModule;
  *(_QWORD *)v20 = &ATL::CComObject<InternalSinkMessageDispatcher>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v21 + 8LL))(v21);
  (*(void (__fastcall **)(struct InternalSinkMessageDispatcher *))(*(_QWORD *)v20 + 8LL))(v20);
  (*(void (__fastcall **)(struct InternalSinkMessageDispatcher *))(*(_QWORD *)v20 + 8LL))(v20);
  (*(void (__fastcall **)(struct InternalSinkMessageDispatcher *))(*(_QWORD *)v20 + 16LL))(v20);
  *((_DWORD *)v20 + 48) = 0;
  Sinks = PhoneService::_CreateSinks(this, v20);
  v24 = Sinks;
  if ( Sinks >= 0 )
  {
    v28 = (*(__int64 (__fastcall **)(_QWORD, struct InternalSinkMessageDispatcher *, _QWORD, struct IPhoneLineFactory **, int, _QWORD))(**((_QWORD **)this + 31) + 24LL))(
            *((_QWORD *)this + 31),
            v20,
            0,
            a2,
            a3,
            0);
    v24 = v28;
    if ( v28 >= 0 )
    {
      v30 = (const unsigned __int16 *)*((_QWORD *)this + 27);
      if ( v30 == *((const unsigned __int16 **)this + 28) )
        v30 = 0;
      v31 = SecurePhoneRpcServer::Initialize(
              (PhoneService *)((char *)this + 184),
              v30,
              (struct IPhoneServiceRpcIdleStateSink *)(((unsigned __int64)this + 184) & -(__int64)(this != 0)),
              *((struct IPhoneController **)this + 31),
              *((struct PhoneNotificationManager **)this + 34));
      v24 = v31;
      if ( v31 >= 0 )
      {
        if ( (unsigned int)dword_1800B3200 > 4 )
        {
          v48 = "PhoneService: Phone RPC server started. Setting PhoneApiReady.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (__int64)v32,
            (int)&unk_1800A54E0,
            v33,
            v34,
            (const unsigned __int16 **)&v48);
        }
        v35 = (void *)*((_QWORD *)this + 26);
        if ( v35 && !SetEvent(v35) )
        {
          LastError = GetLastError();
          v24 = LastError;
          if ( LastError > 0 )
            v24 = (unsigned __int16)LastError | 0x80070000;
          BackTraceCollection::Capture(v37, v24);
          Log_HREvent_0(v24, 0, v38, 248);
          (*(void (__fastcall **)(struct InternalSinkMessageDispatcher *))(*(_QWORD *)v20 + 16LL))(v20);
          goto LABEL_13;
        }
        v39 = PhoneService::_PublishInitialized(this, 1);
        v24 = v39;
        if ( v39 >= 0 )
        {
          (*(void (__fastcall **)(struct InternalSinkMessageDispatcher *))(*(_QWORD *)v20 + 16LL))(v20);
          v41 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v41 + 16LL))(v41);
          }
          v24 = 0;
          goto LABEL_38;
        }
        BackTraceCollection::Capture(v40, v39);
        v26 = 252;
      }
      else
      {
        BackTraceCollection::Capture(v32, v31);
        v26 = 238;
      }
    }
    else
    {
      BackTraceCollection::Capture(v29, v28);
      v26 = 234;
    }
  }
  else
  {
    BackTraceCollection::Capture(v23, Sinks);
    v26 = 226;
  }
  Log_HREvent_0(v24, 1, v25, v26);
  (*(void (__fastcall **)(struct InternalSinkMessageDispatcher *))(*(_QWORD *)v20 + 16LL))(v20);
LABEL_13:
  v27 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
  }
LABEL_38:
  RoUninitialize();
  return v24;
}

```

## disassembly

```asm
0x180008a4c  mov     [rsp-38h+arg_18], rbx
0x180008a51  push    rbp
0x180008a52  push    rsi
0x180008a53  push    rdi
0x180008a54  push    r12
0x180008a56  push    r13
0x180008a58  push    r14
0x180008a5a  push    r15
0x180008a5c  mov     rbp, rsp
0x180008a5f  sub     rsp, 60h
0x180008a63  mov     rax, cs:__security_cookie
0x180008a6a  xor     rax, rsp
0x180008a6d  mov     [rbp+var_10], rax
0x180008a71  mov     rsi, rcx
0x180008a74  mov     r13d, 1
0x180008a7a  mov     ecx, r13d
0x180008a7d  mov     r15d, r8d
0x180008a80  mov     r14, rdx
0x180008a83  call    cs:__imp_RoInitialize
0x180008a89  xor     r12d, r12d
0x180008a8c  mov     ebx, eax
0x180008a8e  test    eax, eax
0x180008a90  jns     short loc_180008AB0
0x180008a92  mov     edx, eax; int
0x180008a94  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180008a99  mov     r9d, 0C8h
0x180008a9f  mov     edx, r13d
0x180008aa2  mov     ecx, ebx
0x180008aa4  call    Log_HREvent_0
0x180008aa9  mov     eax, ebx
0x180008aab  jmp     loc_180008F19
0x180008ab0  lea     rax, [rbp+var_18]
0x180008ab4  mov     [rbp+var_18], r12
0x180008ab8  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180008abf  mov     [rsp+60h+ppv], rax; ppv
0x180008ac4  mov     r8d, r13d; dwClsContext
0x180008ac7  lea     rcx, CLSID_GlobalOptions; rclsid
0x180008ace  xor     edx, edx; pUnkOuter
0x180008ad0  call    cs:__imp_CoCreateInstance
0x180008ad6  test    eax, eax
0x180008ad8  jns     short loc_180008AE2
0x180008ada  mov     r9d, 0D2h
0x180008ae0  jmp     short loc_180008B04
0x180008ae2  mov     rcx, [rbp+var_18]
0x180008ae6  mov     r8, r13
0x180008ae9  mov     edx, 5
0x180008aee  mov     rax, [rcx]
0x180008af1  mov     rax, [rax+18h]
0x180008af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008afa  test    eax, eax
0x180008afc  jns     short loc_180008B0D
0x180008afe  mov     r9d, 0D6h
0x180008b04  xor     edx, edx
0x180008b06  mov     ecx, eax
0x180008b08  call    Log_HREvent_0
0x180008b0d  mov     edi, 2E8h
0x180008b12  mov     [rsi+0F8h], r12
0x180008b19  mov     ecx, edi; Size
0x180008b1b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008b20  mov     rbx, rax
0x180008b23  test    rax, rax
0x180008b26  jz      loc_180008EBC
0x180008b2c  mov     r8d, edi; Size
0x180008b2f  xor     edx, edx; Val
0x180008b31  mov     rcx, rax; void *
0x180008b34  call    memset_0
0x180008b39  mov     rcx, rbx; this
0x180008b3c  call    ??0PhoneController@@IEAA@XZ; PhoneController::PhoneController(void)
0x180008b41  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008b48  lea     rax, ??_7?$CComObject@VPhoneController@@@ATL@@6BIPhoneController@@@; const ATL::CComObject<PhoneController>::`vftable'{for `IPhoneController'}
0x180008b4f  mov     [rbx], rax
0x180008b52  lea     rax, ??_7?$CComObject@VPhoneController@@@ATL@@6BIDialQueueClient@@@; const ATL::CComObject<PhoneController>::`vftable'{for `IDialQueueClient'}
0x180008b59  mov     [rbx+8], rax
0x180008b5d  lea     rax, ??_7?$CComObject@VPhoneController@@@ATL@@6BIDispatcherQueueCallback@@@; const ATL::CComObject<PhoneController>::`vftable'{for `IDispatcherQueueCallback'}
0x180008b64  mov     [rbx+10h], rax
0x180008b68  lea     rax, ??_7?$CComObject@VPhoneController@@@ATL@@6BIOneShotTimerCallback@@@; const ATL::CComObject<PhoneController>::`vftable'{for `IOneShotTimerCallback'}
0x180008b6f  mov     [rbx+18h], rax
0x180008b73  lea     rax, ??_7?$CComObject@VPhoneController@@@ATL@@6BIAudioRoutingStateChangeListener@@@; const ATL::CComObject<PhoneController>::`vftable'{for `IAudioRoutingStateChangeListener'}
0x180008b7a  mov     [rbx+20h], rax
0x180008b7e  lea     rax, ??_7?$CComObject@VPhoneController@@@ATL@@6BIRecordingStateChangeListener@@@; const ATL::CComObject<PhoneController>::`vftable'{for `IRecordingStateChangeListener'}
0x180008b85  mov     [rbx+28h], rax
0x180008b89  lea     rax, ??_7?$CComObject@VPhoneController@@@ATL@@6BISimpleModemCompletion@@@; const ATL::CComObject<PhoneController>::`vftable'{for `ISimpleModemCompletion'}
0x180008b90  mov     [rbx+30h], rax
0x180008b94  mov     rax, [rcx]
0x180008b97  mov     rax, [rax+8]
0x180008b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ba0  mov     rax, [rbx]
0x180008ba3  mov     rcx, rbx
0x180008ba6  mov     rax, [rax+8]
0x180008baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008baf  mov     rax, [rbx]
0x180008bb2  mov     rcx, rbx
0x180008bb5  mov     rax, [rax+8]
0x180008bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bbe  mov     [rsi+0F8h], rbx
0x180008bc5  mov     rcx, rbx
0x180008bc8  mov     rax, [rbx]
0x180008bcb  mov     rax, [rax+10h]
0x180008bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bd4  mov     edi, 0F0h
0x180008bd9  mov     ecx, edi; Size
0x180008bdb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008be0  mov     rbx, rax
0x180008be3  test    rax, rax
0x180008be6  jz      loc_180008E91
0x180008bec  mov     r8d, edi; Size
0x180008bef  xor     edx, edx; Val
0x180008bf1  mov     rcx, rax; void *
0x180008bf4  call    memset_0
0x180008bf9  lea     rax, ??_7InternalSinkMessageDispatcher@@6B@; const InternalSinkMessageDispatcher::`vftable'
0x180008c00  mov     [rbx+0C0h], r13d
0x180008c07  mov     [rbx], rax
0x180008c0a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180008c11  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008c15  xor     r8d, r8d; Flags
0x180008c18  xor     edx, edx; dwSpinCount
0x180008c1a  mov     [rbx+18h], rax
0x180008c1e  mov     [rbx+20h], rax
0x180008c22  mov     [rbx+28h], rax
0x180008c26  mov     [rbx+30h], rax
0x180008c2a  mov     [rbx+38h], rax
0x180008c2e  mov     [rbx+40h], rax
0x180008c32  mov     [rbx+48h], rax
0x180008c36  mov     [rbx+50h], rax
0x180008c3a  mov     [rbx+58h], rax
0x180008c3e  mov     [rbx+60h], rax
0x180008c42  mov     [rbx+68h], rax
0x180008c46  mov     [rbx+70h], rax
0x180008c4a  mov     [rbx+78h], rax
0x180008c4e  mov     [rbx+80h], rax
0x180008c55  mov     [rbx+88h], rax
0x180008c5c  mov     [rbx+90h], rax
0x180008c63  mov     [rbx+98h], rax
0x180008c6a  mov     [rbx+0A0h], rax
0x180008c71  mov     [rbx+0A8h], rax
0x180008c78  mov     [rbx+0B0h], rax
0x180008c7f  mov     [rbx+0B8h], rax
0x180008c86  call    cs:__imp_InitializeCriticalSectionEx
0x180008c8c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008c93  lea     rax, ??_7?$CComObject@VInternalSinkMessageDispatcher@@@ATL@@6B@; const ATL::CComObject<InternalSinkMessageDispatcher>::`vftable'
0x180008c9a  mov     [rbx], rax
0x180008c9d  mov     rax, [rcx]
0x180008ca0  mov     rax, [rax+8]
0x180008ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ca9  mov     rax, [rbx]
0x180008cac  mov     rcx, rbx
0x180008caf  mov     rax, [rax+8]
0x180008cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cb8  mov     rax, [rbx]
0x180008cbb  mov     rcx, rbx
0x180008cbe  mov     rax, [rax+8]
0x180008cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc7  mov     rax, [rbx]
0x180008cca  mov     rcx, rbx
0x180008ccd  mov     rax, [rax+10h]
0x180008cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cd6  mov     rdx, rbx; struct InternalSinkMessageDispatcher *
0x180008cd9  mov     [rbx+0C0h], r12d
0x180008ce0  mov     rcx, rsi; this
0x180008ce3  call    ?_CreateSinks@PhoneService@@IEAAJPEAVInternalSinkMessageDispatcher@@@Z; PhoneService::_CreateSinks(InternalSinkMessageDispatcher *)
0x180008ce8  mov     edi, eax
0x180008cea  test    eax, eax
0x180008cec  jns     short loc_180008D36
0x180008cee  mov     edx, eax; int
0x180008cf0  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180008cf5  mov     r9d, 0E2h
0x180008cfb  mov     edx, r13d
0x180008cfe  mov     ecx, edi
0x180008d00  call    Log_HREvent_0
0x180008d05  mov     rcx, [rbx]
0x180008d08  mov     rax, [rcx+10h]
0x180008d0c  mov     rcx, rbx
0x180008d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d14  mov     rcx, [rbp+var_18]
0x180008d18  test    rcx, rcx
0x180008d1b  jz      loc_180008F11
0x180008d21  mov     [rbp+var_18], r12
0x180008d25  mov     rax, [rcx]
0x180008d28  mov     rax, [rax+10h]
0x180008d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d31  jmp     loc_180008F11
0x180008d36  mov     rcx, [rsi+0F8h]
0x180008d3d  mov     r9, r14
0x180008d40  mov     [rsp+60h+var_38], r12
0x180008d45  xor     r8d, r8d
0x180008d48  mov     rdx, rbx
0x180008d4b  mov     dword ptr [rsp+60h+ppv], r15d
0x180008d50  mov     rax, [rcx]
0x180008d53  mov     rax, [rax+18h]
0x180008d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d5c  mov     edi, eax
0x180008d5e  test    eax, eax
0x180008d60  jns     short loc_180008D71
0x180008d62  mov     edx, eax; int
0x180008d64  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180008d69  mov     r9d, 0EAh
0x180008d6f  jmp     short loc_180008CFB
0x180008d71  mov     rdx, [rsi+0D8h]
0x180008d78  lea     rcx, [rsi+0B8h]; this
0x180008d7f  mov     r10, [rsi+110h]
0x180008d86  mov     rax, rsi
0x180008d89  mov     r9, [rsi+0F8h]; struct IPhoneController *
0x180008d90  neg     rax
0x180008d93  mov     [rsp+60h+ppv], r10; struct PhoneNotificationManager *
0x180008d98  sbb     r8, r8
0x180008d9b  and     r8, rcx; struct IPhoneServiceRpcIdleStateSink *
0x180008d9e  cmp     rdx, [rsi+0E0h]
0x180008da5  cmovz   rdx, r12; unsigned __int16 *
0x180008da9  call    ?Initialize@SecurePhoneRpcServer@@QEAAJPEBGPEAUIPhoneServiceRpcIdleStateSink@@PEAUIPhoneController@@PEAVPhoneNotificationManager@@@Z; SecurePhoneRpcServer::Initialize(ushort const *,IPhoneServiceRpcIdleStateSink *,IPhoneController *,PhoneNotificationManager *)
0x180008dae  mov     edi, eax
0x180008db0  test    eax, eax
0x180008db2  jns     short loc_180008DC6
0x180008db4  mov     edx, eax; int
0x180008db6  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180008dbb  mov     r9d, 0EEh
0x180008dc1  jmp     loc_180008CFB
0x180008dc6  mov     eax, cs:dword_1800B3200
0x180008dcc  cmp     eax, 4
0x180008dcf  jbe     short loc_180008DF1
0x180008dd1  lea     rax, aPhoneservicePh; "PhoneService: Phone RPC server started."...
0x180008dd8  mov     [rbp+var_20], rax
0x180008ddc  lea     rdx, unk_1800A54E0
0x180008de3  lea     rax, [rbp+var_20]
0x180008de7  mov     [rsp+60h+ppv], rax
0x180008dec  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180008df1  mov     rcx, [rsi+0D0h]; hEvent
0x180008df8  test    rcx, rcx
0x180008dfb  jz      short loc_180008E3E
0x180008dfd  call    cs:__imp_SetEvent
0x180008e03  test    eax, eax
0x180008e05  jnz     short loc_180008E3E
0x180008e07  call    cs:__imp_GetLastError
0x180008e0d  mov     edi, eax
0x180008e0f  test    eax, eax
0x180008e11  jle     short loc_180008E1C
0x180008e13  movzx   edi, ax
0x180008e16  or      edi, 80070000h
0x180008e1c  mov     edx, edi; int
0x180008e1e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180008e23  xor     edx, edx
0x180008e25  mov     r9d, 0F8h
0x180008e2b  mov     ecx, edi
0x180008e2d  call    Log_HREvent_0
0x180008e32  mov     rax, [rbx]
0x180008e35  mov     rax, [rax+10h]
0x180008e39  jmp     loc_180008D0C
0x180008e3e  mov     edx, r13d; int
0x180008e41  mov     rcx, rsi; this
0x180008e44  call    ?_PublishInitialized@PhoneService@@AEAAJH@Z; PhoneService::_PublishInitialized(int)
0x180008e49  mov     edi, eax
0x180008e4b  test    eax, eax
0x180008e4d  jns     short loc_180008E61
0x180008e4f  mov     edx, eax; int
0x180008e51  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180008e56  mov     r9d, 0FCh
0x180008e5c  jmp     loc_180008CFB
0x180008e61  mov     rax, [rbx]
0x180008e64  mov     rcx, rbx
0x180008e67  mov     rax, [rax+10h]
0x180008e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e70  mov     rcx, [rbp+var_18]
0x180008e74  test    rcx, rcx
0x180008e77  jz      short loc_180008E89
0x180008e79  mov     [rbp+var_18], r12
0x180008e7d  mov     rax, [rcx]
0x180008e80  mov     rax, [rax+10h]
0x180008e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e89  mov     edi, r12d
0x180008e8c  jmp     loc_180008F11
0x180008e91  mov     ebx, 8007000Eh
0x180008e96  mov     edx, ebx; int
0x180008e98  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180008e9d  mov     r9d, 19h
0x180008ea3  mov     edx, r13d
0x180008ea6  mov     ecx, ebx
0x180008ea8  call    Log_HREvent_2
0x180008ead  mov     edx, ebx; int
0x180008eaf  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180008eb4  mov     r9d, 0DFh
0x180008eba  jmp     short loc_180008EEC
0x180008ebc  mov     ebx, 8007000Eh
0x180008ec1  mov     edx, ebx; int
0x180008ec3  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180008ec8  mov     r9d, 0D7h
0x180008ece  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180008ed5  mov     edx, r13d
0x180008ed8  mov     ecx, ebx
0x180008eda  call    Log_HREvent_7
0x180008edf  mov     edx, ebx; int
0x180008ee1  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180008ee6  mov     r9d, 0DAh
0x180008eec  mov     edx, r13d
0x180008eef  mov     ecx, ebx
0x180008ef1  call    Log_HREvent_0
0x180008ef6  mov     rcx, [rbp+var_18]
0x180008efa  test    rcx, rcx
0x180008efd  jz      short loc_180008F0F
0x180008eff  mov     [rbp+var_18], r12
0x180008f03  mov     rax, [rcx]
0x180008f06  mov     rax, [rax+10h]
  ... truncated ...
```
