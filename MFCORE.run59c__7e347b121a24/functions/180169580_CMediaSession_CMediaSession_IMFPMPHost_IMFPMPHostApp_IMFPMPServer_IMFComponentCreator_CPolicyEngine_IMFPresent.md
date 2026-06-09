# CMediaSession::CMediaSession(IMFPMPHost *,IMFPMPHostApp *,IMFPMPServer *,IMFComponentCreator *,CPolicyEngine *,IMFPresentationClock *,IMFAttributes *,long *)

- ea: `0x180169580`
- end: `0x18016ab25`
- name: `??0CMediaSession@@QEAA@PEAUIMFPMPHost@@PEAUIMFPMPHostApp@@PEAUIMFPMPServer@@PEAUIMFComponentCreator@@PEAVCPolicyEngine@@PEAUIMFPresentationClock@@PEAUIMFAttributes@@PEAJ@Z`
- size: `5541`
- prototype: `CMediaSession *__usercall@<rax>(CMediaSession *__hidden this@<rcx>, struct IMFPMPHost *@<rdx>, struct IMFPMPHostApp *@<r8>, struct IMFPMPServer *@<r9>, struct IMFComponentCreator *, struct CPolicyEngine *, struct IMFPresentationClock *, struct IMFAttributes *, int *)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802122a4`

## callees

- `0x18000de14`
- `0x18001616c`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004d16c`
- `0x180050d6c`
- `0x180063f00`
- `0x180067eec`
- `0x18008b3a0`
- `0x1800bf958`
- `0x1800dcc60`
- `0x1800ec0e0`
- `0x180106a10`
- `0x180130fe8`
- `0x18014c1d8`
- `0x18014cd0c`
- `0x18014e1a4`
- `0x1801646ac`
- `0x180165228`
- `0x1801656b0`
- `0x180167458`
- `0x180168f68`
- `0x180169580`
- `0x1801807e0`
- `0x1801b0894`
- `0x1802583a8`
- `0x180258480`
- `0x180273f44`
- `0x18028d838`
- `0x18028d890`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801696ea`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801696ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18016aac6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18016aac6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18016991e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18016991e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180169c7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180169c7e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180169c50`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180169c50`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18016a9ca`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18016a9ca`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180169c66`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180169c66`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180169d54`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180169d54`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18016a344`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18016a344`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180169dc9`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180169dc9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180169ede`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180169ede`
- `MFPlat!MFCreateTelemetrySession` at `0x180169be6`
- `MFPlat!MFCreateTelemetrySession` at `0x18016a3be`
- `MFPlat!MFCreateTelemetrySession` at `0x180169be6`
- `MFPlat!MFCreateTelemetrySession` at `0x18016a3be`
- `MFPlat!MFAllocateSerialWorkQueue` at `0x18016a493`
- `MFPlat!MFAllocateSerialWorkQueue` at `0x18016a493`

## pseudocode

```c
CMediaSession *__fastcall CMediaSession::CMediaSession(
        CMediaSession *this,
        struct IMFPMPHost *a2,
        struct IMFPMPHostApp *a3,
        struct IMFPMPServer *a4,
        struct IMFComponentCreator *a5,
        struct CPolicyEngine *a6,
        struct IMFPresentationClock *a7,
        struct IMFAttributes *a8,
        int *a9)
{
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  unsigned int v11; // r8d
  char *v12; // rbx
  char *v13; // rdi
  unsigned int v14; // r8d
  int ActivationFactory; // esi
  CallStackTracing *v16; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v18; // ebx
  __int128 *v19; // rax
  __int128 v20; // xmm0
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  char v23; // cl
  __int64 v24; // rax
  __int64 v25; // r9
  __int64 v26; // r8
  __int64 v27; // r8
  struct IMFComponentCreator **v28; // rdi
  struct IMFAttributesVtbl *lpVtbl; // rax
  HGLOBAL v30; // r13
  LPVOID v31; // rbx
  signed int LastError; // eax
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  CallStackTracing *v36; // rcx
  struct CallStackContext *v37; // rax
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  _QWORD *v42; // rax
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  CallStackTracing *v48; // rcx
  struct CallStackContext *v49; // rax
  __int64 v50; // rsi
  struct IMFComponentCreator *v51; // rbx
  __int64 (__fastcall *v52)(__int64, _QWORD, struct IMFComponentCreator *, _BYTE *); // rdi
  _QWORD *v53; // rax
  CallStackTracing *v54; // rcx
  struct CallStackContext *v55; // rax
  struct IMFComponentCreator *v56; // rcx
  const unsigned __int16 *v57; // rdx
  CallStackTracing *v58; // rcx
  struct CallStackContext *v59; // rax
  __int64 v60; // rsi
  struct IMFComponentCreator *v61; // rbx
  __int64 (__fastcall *v62)(__int64, _QWORD, struct IMFComponentCreator *, _BYTE *); // rdi
  _QWORD *v63; // rax
  CallStackTracing *v64; // rcx
  struct CallStackContext *v65; // rax
  CallStackTracing *v66; // rcx
  struct CallStackContext *v67; // rax
  struct IMFAttributesVtbl *v68; // rax
  struct IMFTopoLoader **v69; // rbx
  HRESULT v70; // eax
  CallStackTracing *v71; // rcx
  struct CallStackContext *v72; // rax
  CallStackTracing *v73; // rcx
  struct CallStackContext *v74; // rax
  CallStackTracing *v75; // rcx
  struct CallStackContext *v76; // rax
  _QWORD *v77; // rbx
  CallStackTracing *v78; // rcx
  struct CallStackContext *v79; // rax
  CallStackTracing *v80; // rcx
  struct CallStackContext *v81; // rax
  CallStackTracing *v82; // rcx
  struct CallStackContext *v83; // rax
  CMFTimeManager *v84; // rax
  CMFTimeManager *v85; // rax
  CallStackTracing *v86; // rcx
  struct CallStackContext *v87; // rax
  CallStackTracing *v88; // rcx
  struct CallStackContext *v89; // rax
  CallStackTracing *v90; // rcx
  struct CallStackContext *v91; // rax
  CallStackTracing *v92; // rcx
  struct CallStackContext *v93; // rax
  CallStackTracing *v94; // rcx
  struct CallStackContext *v95; // rax
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // r8
  GUID *v99; // rax
  __int64 v100; // rcx
  int v101; // ecx
  unsigned int v102; // r8d
  int v103; // r9d
  _BYTE v105[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v106; // [rsp+48h] [rbp-B8h] BYREF
  struct IMFComponentCreator *v107; // [rsp+50h] [rbp-B0h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp-A8h] BYREF
  SIZE_T dwBytes; // [rsp+60h] [rbp-A0h] BYREF
  struct IMFTelemetrySession *v110; // [rsp+68h] [rbp-98h] BYREF
  GUID v111; // [rsp+70h] [rbp-90h] BYREF
  HGLOBAL hMem; // [rsp+80h] [rbp-80h] BYREF
  __int64 v113; // [rsp+88h] [rbp-78h] BYREF
  void *v114; // [rsp+90h] [rbp-70h] BYREF
  struct IUnknown *v115; // [rsp+98h] [rbp-68h] BYREF
  int *v116; // [rsp+A0h] [rbp-60h]
  IID rclsid; // [rsp+B0h] [rbp-50h] BYREF
  GUID v118; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING string[4]; // [rsp+D0h] [rbp-30h] BYREF

  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 624);
  v107 = a5;
  *(_QWORD *)&v111.Data1 = a3;
  *(_QWORD *)&rclsid.Data1 = a2;
  v106 = a6;
  ppstm = (LPSTREAM)a4;
  v116 = a9;
  COpQueue::COpQueue(
    (CMediaSession *)((char *)this + 32),
    (CMediaSession *)((char *)this + 624),
    a9,
    (unsigned int)a4,
    1u);
  *((_DWORD *)this + 138) = 1;
  *(_QWORD *)this = &CMediaSession::`vftable'{for `IMFMediaSession'};
  *((_QWORD *)this + 1) = &CMediaSession::`vftable'{for `IMFRateSupport'};
  *((_QWORD *)this + 2) = &CMediaSession::`vftable'{for `IMFRateControl'};
  *((_QWORD *)this + 3) = &CMediaSession::`vftable'{for `IMFGetMultipleServiceProviders'};
  *((_QWORD *)this + 4) = &CMediaSession::`vftable'{for `COpQueue'};
  *((_QWORD *)this + 65) = &CMediaSession::`vftable'{for `IMFCodecAPIRemoting'};
  *((_QWORD *)this + 66) = &CMediaSession::`vftable'{for `IMFMediaTypeChangeRemoting'};
  *((_QWORD *)this + 67) = &CMediaSession::`vftable'{for `IMFPresentationClockAggregateClient'};
  *((_QWORD *)this + 68) = &CMediaSession::`vftable'{for `IMFTelemetryComponent'};
  *((_QWORD *)this + 70) = &CMediaSession::OnSourceEventAsyncCallback::`vftable';
  *((_QWORD *)this + 71) = &CMediaSession::OnDelayedSourceEventAsyncCallback::`vftable';
  *((_QWORD *)this + 72) = &CMediaSession::OnBitPumpEventAsyncCallback::`vftable';
  *((_QWORD *)this + 73) = &CMediaSession::OnDelayedBitPumpEventAsyncCallback::`vftable';
  *((_QWORD *)this + 74) = &CMediaSession::OnSinkEventAsyncCallback::`vftable';
  *((_QWORD *)this + 75) = &CMediaSession::OnTimerAsyncCallback::`vftable';
  *((_QWORD *)this + 76) = &CMediaSession::OnFinalizeSinksAsyncCallback::`vftable';
  *((_QWORD *)this + 77) = &CMediaSession::OnEnsureTrustAsyncCallback::`vftable';
  InitializeCriticalSection(v9);
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = a7;
  if ( a7 )
    ((void (__fastcall *)(struct IMFPresentationClock *))a7->lpVtbl->AddRef)(a7);
  *((_QWORD *)this + 88) = 0;
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 95) = 0;
  v12 = (char *)this + 768;
  *((_QWORD *)this + 96) = 0;
  v13 = (char *)this + 776;
  *((_QWORD *)this + 97) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 100) = 0;
  *((_DWORD *)this + 202) = 0;
  *((_QWORD *)this + 104) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_DWORD *)this + 180) = 0;
  *((_DWORD *)this + 186) = 0;
  *((_DWORD *)this + 199) = 0;
  *((_QWORD *)this + 91) = 1065353216;
  *((_QWORD *)this + 92) = 0;
  *(_QWORD *)((char *)this + 788) = 0;
  *((_QWORD *)this + 103) = (char *)this + 816;
  *((_QWORD *)this + 102) = (char *)this + 816;
  COOEHandler::COOEHandler((CMediaSession *)((char *)this + 840), &dword_18037E948, v11);
  COOEHandler::COOEHandler((CMediaSession *)((char *)this + 856), &dword_18037E950, v14);
  CMFMediaEventGenerator::CMFMediaEventGenerator((CMediaSession *)((char *)this + 872), a9);
  *((_QWORD *)this + 127) = this;
  *((_QWORD *)this + 125) = 0;
  *((_QWORD *)this + 126) = 0;
  *((_QWORD *)this + 128) = 0;
  *((_QWORD *)this + 129) = 0;
  *((_DWORD *)this + 260) = 0;
  *((_DWORD *)this + 366) = 0;
  *((_QWORD *)this + 182) = 0;
  *((_QWORD *)this + 181) = 0;
  *((_QWORD *)this + 180) = 0;
  *((_QWORD *)this + 184) = 0;
  *((_QWORD *)this + 185) = 0;
  *((_QWORD *)this + 186) = &CMediaSessionPresentationHandler::OnFinalizeSinkAsyncCallback::`vftable';
  *((_DWORD *)this + 378) = 0;
  *((_QWORD *)this + 191) = (char *)this + 1624;
  *((_QWORD *)this + 192) = 0;
  *(_QWORD *)((char *)this + 1548) = 0;
  *((_DWORD *)this + 386) = 0;
  *((_QWORD *)this + 195) = 0;
  *(_QWORD *)((char *)this + 1572) = 0;
  *((_DWORD *)this + 392) = 0;
  *((_QWORD *)this + 187) = this;
  *((_QWORD *)this + 188) = this;
  *((_QWORD *)this + 190) = this;
  *((_QWORD *)this + 198) = this;
  *((_QWORD *)this + 199) = 0;
  *((_QWORD *)this + 201) = 0;
  *((_QWORD *)this + 202) = 0;
  *((_WORD *)this + 496) = 0;
  *((_DWORD *)this + 400) = 0;
  CMediaSessionTelemetry::CMediaSessionTelemetry((CMediaSession *)((char *)this + 1624));
  *((_QWORD *)this + 2612) = &CMediaSession::OnShutdownAsyncCallback::`vftable';
  *((_QWORD *)this + 2613) = 0;
  ActivationFactory = *a9;
  *((_DWORD *)this + 196) = 0;
  v115 = 0;
  hMem = 0;
  v114 = 0;
  v110 = 0;
  v113 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v105, "CMediaSession::CMediaSession", 987);
  v16 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 202) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 202) + 296LL))(*((_QWORD *)this + 202));
    v19 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**((_QWORD **)this + 202) + 280LL))(
                        *((_QWORD *)this + 202),
                        string);
    v16 = CallStackTracing::s_wpInstance;
    v20 = *v19;
    *((_DWORD *)ThreadRelativeContext + 504) = v18;
    v12 = (char *)this + 768;
    *((_OWORD *)ThreadRelativeContext + 125) = v20;
    v13 = (char *)this + 776;
  }
  if ( ActivationFactory < 0 )
  {
    if ( !v16 )
    {
      CallStackTracing::InitInstance();
      v16 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext(v16);
      if ( *((_DWORD *)v21 + 499) != ActivationFactory )
        CallStackContext::TraceFailure(v21, "CMediaSession::CMediaSession", 987, ActivationFactory);
    }
    if ( g_wppLevels )
    {
      v22 = 44;
LABEL_227:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        &WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids,
        this,
        ActivationFactory);
      goto LABEL_228;
    }
    goto LABEL_228;
  }
  v23 = dword_1803CEFD0;
  v24 = dword_1803CEFD0 & 3;
  *((_QWORD *)this + 180) = 0;
  qword_1803CEFB0[v24] = this;
  dword_1803CEFD0 = (v23 + 1) & 3;
  *((_QWORD *)this + 104) = (char *)this + 624;
  if ( !*((_QWORD *)this + 129) )
  {
    *((_DWORD *)this + 260) = 1;
    *((_QWORD *)this + 129) = (char *)this + 1048;
    v25 = 0;
    *((_QWORD *)this + 131) = 0;
    do
    {
      v26 = v25 + 2 * v25 + 1;
      ++v25;
      v27 = *((_QWORD *)this + 129) + 8 * v26;
      *(_QWORD *)(v27 + 8) = *((_QWORD *)this + 128);
      *((_QWORD *)this + 128) = v27;
    }
    while ( v25 != 16 );
  }
  CMediaSession::WaitOnEvent(this, 0);
  ComSmartPtr<CPMPStreamStub>::operator=((char *)this + 760, *(_QWORD *)&rclsid.Data1);
  ComSmartPtr<CPMPStreamStub>::operator=(v12, *(_QWORD *)&v111.Data1);
  ComSmartPtr<CPMPStreamStub>::operator=(v13, ppstm);
  v28 = (struct IMFComponentCreator **)((char *)this + 752);
  ComSmartPtr<CPMPStreamStub>::operator=((char *)this + 752, v107);
  ComSmartPtr<CPMPStreamStub>::operator=((char *)this + 1000, v106);
  v118 = GUID_00000000_0000_0000_0000_000000000000;
  if ( a8 )
  {
    lpVtbl = a8->lpVtbl;
    dwBytes = 0;
    if ( ((int (__fastcall *)(struct IMFAttributes *, GUID *, GUID *, struct IMFTelemetrySession **))lpVtbl->GetUnknown)(
           a8,
           &GUID_627d2ca6_e1cd_4898_999d_101308f1d431,
           &GUID_627d2ca6_e1cd_4898_999d_101308f1d431,
           &v110) < 0 )
    {
      ((void (__fastcall *)(struct IMFAttributes *, void *, GUID *))a8->lpVtbl->GetGUID)(
        a8,
        &MEDIA_TELEMETRY_SESSION_ID,
        &v118);
      ((void (__fastcall *)(struct IMFAttributes *, void *, char *))a8->lpVtbl->GetUINT32)(
        a8,
        &MEDIA_TELEMETRY_INSTANCE_ID,
        (char *)&dwBytes + 4);
      rclsid = GUID_00000000_0000_0000_0000_000000000000;
      v111 = v118;
      MFCreateTelemetrySession(&v111, &rclsid, &v110);
      (*(void (__fastcall **)(struct IMFTelemetrySession *, _QWORD))(*(_QWORD *)v110 + 360LL))(v110, HIDWORD(dwBytes));
    }
    else
    {
      v118 = *(GUID *)(*(__int64 (__fastcall **)(struct IMFTelemetrySession *, HSTRING *))(*(_QWORD *)v110 + 280LL))(
                        v110,
                        string);
      HIDWORD(dwBytes) = (*(__int64 (__fastcall **)(struct IMFTelemetrySession *))(*(_QWORD *)v110 + 296LL))(v110);
    }
    CMediaSession::SetSession((CMediaSession *)((char *)this + 544), v110);
    if ( ((int (__fastcall *)(struct IMFAttributes *, void *, SIZE_T *))a8->lpVtbl->GetBlobSize)(
           a8,
           &MFP_PMP_MPM_PROPERTIES,
           &dwBytes) < 0 )
    {
      v30 = 0;
    }
    else
    {
      ppstm = 0;
      v106 = 0;
      hMem = GlobalAlloc(2u, (unsigned int)dwBytes);
      v30 = hMem;
      v31 = GlobalLock(hMem);
      if ( !v31 )
      {
        LastError = GetLastError();
        ActivationFactory = LastError;
        if ( LastError > 0 )
          ActivationFactory = (unsigned __int16)LastError | 0x80070000;
        if ( ActivationFactory < 0 )
        {
          v33 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v33 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v33 + 8) )
          {
            v34 = CallStackTracing::GetThreadRelativeContext(v33);
            if ( *((_DWORD *)v34 + 499) != ActivationFactory )
              CallStackContext::TraceFailure(v34, "CMediaSession::CMediaSession", 1051, ActivationFactory);
          }
          if ( !g_wppLevels )
            goto LABEL_34;
          v35 = 46;
          goto LABEL_33;
        }
      }
      ActivationFactory = ((__int64 (__fastcall *)(struct IMFAttributes *, void *, LPVOID, _QWORD, SIZE_T *))a8->lpVtbl->GetBlob)(
                            a8,
                            &MFP_PMP_MPM_PROPERTIES,
                            v31,
                            (unsigned int)dwBytes,
                            &dwBytes);
      GlobalUnlock(v30);
      if ( ActivationFactory < 0 )
      {
        v36 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v36 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v36 + 8) )
        {
          v37 = CallStackTracing::GetThreadRelativeContext(v36);
          if ( *((_DWORD *)v37 + 499) != ActivationFactory )
            CallStackContext::TraceFailure(v37, "CMediaSession::CMediaSession", 1055, ActivationFactory);
        }
        if ( !g_wppLevels )
          goto LABEL_34;
        v35 = 47;
        goto LABEL_33;
      }
      ActivationFactory = CreateStreamOnHGlobal(v30, 0, &ppstm);
      if ( ActivationFactory < 0 )
      {
        v38 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v38 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v38 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext(v38);
          if ( *((_DWORD *)v39 + 499) != ActivationFactory )
            CallStackContext::TraceFailure(v39, "CMediaSession::CMediaSession", 1057, ActivationFactory);
        }
        if ( !g_wppLevels )
          goto LABEL_34;
        v35 = 48;
        goto LABEL_33;
      }
      ActivationFactory = CMFWinRTActivate::LoadPropertiesFromIStream(ppstm, &v106);
      if ( ActivationFactory < 0 )
      {
        v40 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v40 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v41 = CallStackTracing::GetThreadRelativeContext(v40);
          if ( *((_DWORD *)v41 + 499) != ActivationFactory )
            CallStackContext::TraceFailure(v41, "CMediaSession::CMediaSession", 1058, ActivationFactory);
        }
        if ( !g_wppLevels )
          goto LABEL_34;
        v35 = 49;
LABEL_33:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v35,
          &WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids,
          this,
          ActivationFactory);
LABEL_34:
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v106);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppstm);
        goto LABEL_228;
      }
      if ( v106 )
      {
        *(_QWORD *)&rclsid.Data1 = 0;
        *(_QWORD *)&v111.Data1 = 0;
        v107 = 0;
        v105[0] = 0;
        v42 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, L"Windows.Foundation.PropertyValue");
        ActivationFactory = RoGetActivationFactory(*v42, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v111);
        if ( ActivationFactory < 0 )
        {
          v43 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v43 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v43 + 8) )
          {
            v44 = CallStackTracing::GetThreadRelativeContext(v43);
            if ( *((_DWORD *)v44 + 499) != ActivationFactory )
              CallStackContext::TraceFailure(v44, "CMediaSession::CMediaSession", 1066, ActivationFactory);
          }
          if ( !g_wppLevels )
            goto LABEL_69;
          v45 = 50;
LABEL_68:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v45,
            &WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids,
            this,
            ActivationFactory);
LABEL_69:
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v107);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v111);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&rclsid);
          goto LABEL_34;
        }
        ActivationFactory = (**(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, IID *))v106)(
                              v106,
                              &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                              &rclsid);
        if ( ActivationFactory < 0 )
        {
          v46 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v46 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v46 + 8) )
          {
            v47 = CallStackTracing::GetThreadRelativeContext(v46);
            if ( *((_DWORD *)v47 + 499) != ActivationFactory )
              CallStackContext::TraceFailure(v47, "CMediaSession::CMediaSession", 1067, ActivationFactory);
          }
          if ( !g_wppLevels )
            goto LABEL_69;
          v45 = 51;
          goto LABEL_68;
        }
        *(GUID *)string = v118;
        ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, HSTRING *, struct IMFComponentCreator **))(**(_QWORD **)&v111.Data1 + 160LL))(
                              *(_QWORD *)&v111.Data1,
                              string,
                              &v107);
        if ( ActivationFactory < 0 )
        {
          v48 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v48 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v48 + 8) )
          {
            v49 = CallStackTracing::GetThreadRelativeContext(v48);
            if ( *((_DWORD *)v49 + 499) != ActivationFactory )
              CallStackContext::TraceFailure(v49, "CMediaSession::CMediaSession", 1068, ActivationFactory);
          }
          if ( !g_wppLevels )
            goto LABEL_69;
          v45 = 52;
          goto LABEL_68;
        }
        v50 = *(_QWORD *)&rclsid.Data1;
        v51 = v107;
        v52 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IMFComponentCreator *, _BYTE *))(**(_QWORD **)&rclsid.Data1
                                                                                               + 80LL);
        v53 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, L"Windows.Media.TelemetrySessionId");
        ActivationFactory = v52(v50, *v53, v51, v105);
        if ( ActivationFactory < 0 )
        {
          v54 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v54 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v54 + 8) )
          {
            v55 = CallStackTracing::GetThreadRelativeContext(v54);
            if ( *((_DWORD *)v55 + 499) != ActivationFactory )
              CallStackContext::TraceFailure(v55, "CMediaSession::CMediaSession", 1069, ActivationFactory);
          }
          if ( !g_wppLevels )
            goto LABEL_69;
          v45 = 53;
          goto LABEL_68;
        }
        v56 = v107;
        if ( v107 )
        {
          v107 = 0;
          (*(void (__fastcall **)(struct IMFComponentCreator *))(*(_QWORD *)v56 + 16LL))(v56);
        }
        ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFComponentCreator **))(**(_QWORD **)&v111.Data1 + 80LL))(
                              *(_QWORD *)&v111.Data1,
                              HIDWORD(dwBytes),
                              &v107);
        if ( ActivationFactory < 0 )
        {
          v58 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v58 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v58 + 8) )
          {
            v59 = CallStackTracing::GetThreadRelativeContext(v58);
            if ( *((_DWORD *)v59 + 499) != ActivationFactory )
              CallStackContext::TraceFailure(v59, "CMediaSession::CMediaSession", 1071, ActivationFactory);
          }
          if ( !g_wppLevels )
            goto LABEL_69;
          v45 = 54;
          goto LABEL_68;
        }
        v60 = *(_QWORD *)&rclsid.Data1;
        v61 = v107;
        v62 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IMFComponentCreator *, _BYTE *))(**(_QWORD **)&rclsid.Data1
                                                                                               + 80LL);
        v63 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[34])v57);
        ActivationFactory = v62(v60, *v63, v61, v105);
        if ( ActivationFactory < 0 )
        {
          v64 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v64 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v64 + 8) )
          {
            v65 = CallStackTracing::GetThreadRelativeContext(v64);
            if ( *((_DWORD *)v65 + 499) != ActivationFactory )
              CallStackContext::TraceFailure(v65, "CMediaSession::CMediaSession", 1072, ActivationFactory);
          }
          if ( !g_wppLevels )
            goto LABEL_69;
          v45 = 55;
          goto LABEL_68;
        }
        ActivationFactory = (**(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, struct IUnknown **))v106)(
                              v106,
                              &GUID_00000000_0000_0000_c000_000000000046,
                              &v115);
        if ( ActivationFactory < 0 )
        {
          v66 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v66 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v66 + 8) )
          {
            v67 = CallStackTracing::GetThreadRelativeContext(v66);
            if ( *((_DWORD *)v67 + 499) != ActivationFactory )
              CallStackContext::TraceFailure(v67, "CMediaSession::CMediaSession", 1074, ActivationFactory);
          }
          if ( !g_wppLevels )
            goto LABEL_69;
          v45 = 56;
          goto LABEL_68;
        }
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v107);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v111);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&rclsid);
        v28 = (struct IMFComponentCreator **)((char *)this + 752);
      }
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v106);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppstm);
    }
    v68 = a8->lpVtbl;
    hMem = v30;
    rclsid = 0;
    v69 = (struct IMFTopoLoader **)((char *)this + 704);
    if ( ((int (__fastcall *)(struct IMFAttributes *, const IID *, IID *))v68->GetGUID)(
           a8,
           &MF_SESSION_TOPOLOADER,
           &rclsid) >= 0 )
    {
      v70 = CoCreateInstance(&rclsid, 0, 1u, &IID_IMFTopoLoader, (LPVOID *)this + 88);
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 57, &WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids, this, v70);
    }
    *((_DWORD *)this + 169) = MFGetAttributeUINT32(a8, &MF_LOW_LATENCY, 0);
    *((_DWORD *)this + 198) = MFGetAttributeUINT32(a8, &MF_SESSION_PREROLL_FROM_RATE0, 0);
  }
  else
  {
    *(GUID *)string = GUID_00000000_0000_0000_0000_000000000000;
    MFCreateTelemetrySession(&v118, string, &v110);
    CMediaSession::SetSession((CMediaSession *)((char *)this + 544), v110);
    v69 = (struct IMFTopoLoader **)((char *)this + 704);
  }
  if ( !*v69 )
  {
    ActivationFactory = MediaSessionCreateTopoLoader(*v28, v115, v69);
    if ( ActivationFactory < 0 )
    {
      v71 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v71 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v71 + 8) )
      {
        v72 = CallStackTracing::GetThreadRelativeContext(v71);
        if ( *((_DWORD *)v72 + 499) != ActivationFactory )
          CallStackContext::TraceFailure(v72, "CMediaSession::CMediaSession", 1121, ActivationFactory);
      }
      if ( g_wppLevels )
      {
        v22 = 58;
        goto LABEL_227;
      }
      goto LABEL_228;
    }
  }
  if ( ((__int64 (__fastcall *)(struct IMFTopoLoader *, GUID *, __int64 *))(*v69)->lpVtbl->QueryInterface)(
         *v69,
         &GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803,
         &v113) >= 0 )
    (*(void (__fastcall **)(__int64, struct IMFTelemetrySession *))(*(_QWORD *)v113 + 32LL))(v113, v110);
  ActivationFactory = MFAllocateSerialWorkQueue(5u, (DWORD *)this + 400);
  if ( ActivationFactory < 0 )
  {
    v73 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v73 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v73 + 8) )
    {
      v74 = CallStackTracing::GetThreadRelativeContext(v73);
      if ( *((_DWORD *)v74 + 499) != ActivationFactory )
        CallStackContext::TraceFailure(v74, "CMediaSession::CMediaSession", 1131, ActivationFactory);
    }
    if ( g_wppLevels )
    {
      v22 = 59;
      goto LABEL_227;
    }
    goto LABEL_228;
  }
  ActivationFactory = MFCreateMediaProcessor(&v114);
  if ( ActivationFactory < 0 )
  {
    v75 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v75 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v75 + 8) )
    {
      v76 = CallStackTracing::GetThreadRelativeContext(v75);
      if ( *((_DWORD *)v76 + 499) != ActivationFactory )
        CallStackContext::TraceFailure(v76, "CMediaSession::CMediaSession", 1133, ActivationFactory);
    }
    if ( g_wppLevels )
    {
      v22 = 60;
      goto LABEL_227;
    }
    goto LABEL_228;
  }
  v77 = (_QWORD *)((char *)this + 712);
  ActivationFactory = (**(__int64 (__fastcall ***)(void *, GUID *, char *))v114)(
                        v114,
                        &GUID_fe3de6ec_1e5d_4741_9c4d_2a348a43f9fc,
                        (char *)this + 712);
  if ( ActivationFactory < 0 )
  {
    v78 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v78 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v78 + 8) )
    {
      v79 = CallStackTracing::GetThreadRelativeContext(v78);
      if ( *((_DWORD *)v79 + 499) != ActivationFactory )
        CallStackContext::TraceFailure(v79, "CMediaSession::CMediaSession", 1134, ActivationFactory);
    }
    if ( g_wppLevels )
    {
      v22 = 61;
      goto LABEL_227;
    }
    goto LABEL_228;
  }
  if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    WPP_SF_qqqq(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      62,
      &WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids,
      this,
      *v77,
      (char *)this + 560,
      this);
  ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(*(_QWORD *)*v77 + 32LL))(
                        *v77,
                        (char *)this + 560,
                        *v77);
  if ( ActivationFactory < 0 )
  {
    v80 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v80 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v80 + 8) )
    {
      v81 = CallStackTracing::GetThreadRelativeContext(v80);
      if ( *((_DWORD *)v81 + 499) != ActivationFactory )
        CallStackContext::TraceFailure(v81, "CMediaSession::CMediaSession", 1139, ActivationFactory);
    }
    if ( g_wppLevels )
    {
      v22 = 63;
      goto LABEL_227;
    }
    goto LABEL_228;
  }
  if ( !*((_QWORD *)this + 86) )
  {
    ActivationFactory = CMFPresentationClock::CreateInstanceAsyncTimeSource((struct IMFPresentationClock **)this + 86);
    if ( ActivationFactory < 0 )
    {
      v82 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v82 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v82 + 8) )
      {
        v83 = CallStackTracing::GetThreadRelativeContext(v82);
        if ( *((_DWORD *)v83 + 499) != ActivationFactory )
          CallStackContext::TraceFailure(v83, "CMediaSession::CMediaSession", 1156, ActivationFactory);
      }
      if ( g_wppLevels )
      {
        v22 = 64;
        goto LABEL_227;
      }
      goto LABEL_228;
    }
  }
  v84 = (CMFTimeManager *)operator new(0x360u);
  if ( !v84 )
  {
    *((_QWORD *)this + 100) = 0;
LABEL_220:
    v94 = CallStackTracing::s_wpInstance;
    ActivationFactory = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v94 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v94 + 8) )
    {
      v95 = CallStackTracing::GetThreadRelativeContext(v94);
      if ( *((_DWORD *)v95 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v95, "CMediaSession::CMediaSession", 1161, -2147024882);
    }
    if ( g_wppLevels )
    {
      v22 = 65;
      goto LABEL_227;
    }
    goto LABEL_228;
  }
  v85 = CMFTimeManager::CMFTimeManager(v84);
  *((_QWORD *)this + 100) = v85;
  if ( !v85 )
    goto LABEL_220;
  ActivationFactory = CMediaSessionTopologyValidator::Initialize((CMediaSession *)((char *)this + 1512), a8);
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = CMediaSession::CreateQualityManager(this, a8);
    if ( ActivationFactory >= 0 )
    {
      if ( *((_QWORD *)this + 199) )
      {
        ActivationFactory = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v77 + 112LL))(*v77);
        if ( ActivationFactory < 0 )
        {
          v90 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v90 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v90 + 8) )
          {
            v91 = CallStackTracing::GetThreadRelativeContext(v90);
            if ( *((_DWORD *)v91 + 499) != ActivationFactory )
              CallStackContext::TraceFailure(v91, "CMediaSession::CMediaSession", 1169, ActivationFactory);
          }
          if ( g_wppLevels )
          {
            v22 = 68;
            goto LABEL_227;
          }
          goto LABEL_228;
        }
        ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 199) + 32LL))(
                              *((_QWORD *)this + 199),
                              *((_QWORD *)this + 86));
        if ( ActivationFactory < 0 )
        {
          v92 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v92 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v92 + 8) )
          {
            v93 = CallStackTracing::GetThreadRelativeContext(v92);
            if ( *((_DWORD *)v93 + 499) != ActivationFactory )
              CallStackContext::TraceFailure(v93, "CMediaSession::CMediaSession", 1171, ActivationFactory);
          }
          if ( g_wppLevels )
          {
            v22 = 69;
            goto LABEL_227;
          }
          goto LABEL_228;
        }
      }
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_qqq(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          70,
          &WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids,
          this,
          *v77,
          (char *)this + 872);
      goto LABEL_228;
    }
    v88 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v88 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v88 + 8) )
    {
      v89 = CallStackTracing::GetThreadRelativeContext(v88);
      if ( *((_DWORD *)v89 + 499) != ActivationFactory )
        CallStackContext::TraceFailure(v89, "CMediaSession::CMediaSession", 1165, ActivationFactory);
    }
    if ( g_wppLevels )
    {
      v22 = 67;
      goto LABEL_227;
    }
  }
  else
  {
    v86 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v86 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v86 + 8) )
    {
      v87 = CallStackTracing::GetThreadRelativeContext(v86);
      if ( *((_DWORD *)v87 + 499) != ActivationFactory )
        CallStackContext::TraceFailure(v87, "CMediaSession::CMediaSession", 1163, ActivationFactory);
    }
    if ( g_wppLevels )
    {
      v22 = 66;
      goto LABEL_227;
    }
  }
LABEL_228:
  GlobalFree(hMem);
  if ( ActivationFactory < 0 )
  {
    v96 = *((_QWORD *)this + 202);
    if ( !v96
      || !(*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v96 + 320LL))(
            v96,
            &MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT) )
    {
      v97 = *((_QWORD *)this + 202);
      v98 = 0;
      v118 = GUID_00000000_0000_0000_0000_000000000000;
      if ( v97 )
      {
        v99 = (GUID *)(*(__int64 (__fastcall **)(__int64, HSTRING *, _QWORD))(*(_QWORD *)v97 + 280LL))(v97, string, 0);
        v100 = *((_QWORD *)this + 202);
        v118 = *v99;
        v98 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v100 + 296LL))(v100);
      }
      if ( (unsigned int)dword_1803A6618 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1803A6618, 0x400000000000LL, v98) )
      {
        hMem = &v118;
        dwBytes = __PAIR64__(v102, ActivationFactory);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v101,
          (unsigned int)&unk_1803933C3,
          v102,
          v103,
          (__int64)&dwBytes,
          (__int64)&hMem,
          (__int64)&dwBytes + 4);
      }
    }
  }
  *v116 = ActivationFactory;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v105);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v113);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v110);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v114);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v115);
  return this;
}

```

## disassembly

```asm
0x180169580  push    rbp
0x180169582  push    rbx
0x180169583  push    rsi
0x180169584  push    rdi
0x180169585  push    r12
0x180169587  push    r13
0x180169589  push    r14
0x18016958b  push    r15
0x18016958d  lea     rbp, [rsp-8]
0x180169592  sub     rsp, 108h
0x180169599  mov     rax, cs:__security_cookie
0x1801695a0  xor     rax, rsp
0x1801695a3  mov     [rbp+40h+var_50], rax
0x1801695a7  mov     rax, [rbp+40h+arg_20]
0x1801695ab  lea     rdi, [rcx+270h]
0x1801695b2  mov     rsi, [rbp+40h+arg_40]
0x1801695b9  mov     r14, rcx
0x1801695bc  mov     r12, [rbp+40h+arg_38]
0x1801695c3  add     rcx, 20h ; ' '; this
0x1801695c7  mov     [rsp+140h+var_F0], rax
0x1801695cc  mov     rax, [rbp+40h+arg_28]
0x1801695d0  mov     qword ptr [rsp+140h+var_D0], r8
0x1801695d5  mov     r8, rsi; int *
0x1801695d8  mov     qword ptr [rbp+40h+rclsid.Data1], rdx
0x1801695dc  mov     rdx, rdi; struct CMFCSLock *
0x1801695df  mov     [rsp+140h+var_F8], rax
0x1801695e4  mov     [rsp+140h+ppstm], r9
0x1801695e9  mov     [rbp+40h+var_A0], rsi
0x1801695ed  mov     dword ptr [rsp+140h+ppv], 1; unsigned int
0x1801695f5  call    ??0COpQueue@@QEAA@PEAVCMFCSLock@@PEAJKK@Z; COpQueue::COpQueue(CMFCSLock *,long *,ulong,ulong)
0x1801695fa  lea     rax, ??_7CMediaSession@@6BIMFMediaSession@@@; const CMediaSession::`vftable'{for `IMFMediaSession'}
0x180169601  mov     dword ptr [r14+228h], 1
0x18016960c  mov     [r14], rax
0x18016960f  lea     r13, [r14+220h]
0x180169616  lea     rax, ??_7CMediaSession@@6BIMFRateSupport@@@; const CMediaSession::`vftable'{for `IMFRateSupport'}
0x18016961d  mov     rcx, rdi; lpCriticalSection
0x180169620  mov     [r14+8], rax
0x180169624  lea     rax, ??_7CMediaSession@@6BIMFRateControl@@@; const CMediaSession::`vftable'{for `IMFRateControl'}
0x18016962b  mov     [r14+10h], rax
0x18016962f  lea     rax, ??_7CMediaSession@@6BIMFGetMultipleServiceProviders@@@; const CMediaSession::`vftable'{for `IMFGetMultipleServiceProviders'}
0x180169636  mov     [r14+18h], rax
0x18016963a  lea     rax, ??_7CMediaSession@@6BCOpQueue@@@; const CMediaSession::`vftable'{for `COpQueue'}
0x180169641  mov     [r14+20h], rax
0x180169645  lea     rax, ??_7CMediaSession@@6BIMFCodecAPIRemoting@@@; const CMediaSession::`vftable'{for `IMFCodecAPIRemoting'}
0x18016964c  mov     [r14+208h], rax
0x180169653  lea     rax, ??_7CMediaSession@@6BIMFMediaTypeChangeRemoting@@@; const CMediaSession::`vftable'{for `IMFMediaTypeChangeRemoting'}
0x18016965a  mov     [r14+210h], rax
0x180169661  lea     rax, ??_7CMediaSession@@6BIMFPresentationClockAggregateClient@@@; const CMediaSession::`vftable'{for `IMFPresentationClockAggregateClient'}
0x180169668  mov     [r14+218h], rax
0x18016966f  lea     rax, ??_7CMediaSession@@6BIMFTelemetryComponent@@@; const CMediaSession::`vftable'{for `IMFTelemetryComponent'}
0x180169676  mov     [r13+0], rax
0x18016967a  lea     rax, ??_7OnSourceEventAsyncCallback@CMediaSession@@6B@; const CMediaSession::OnSourceEventAsyncCallback::`vftable'
0x180169681  mov     [r14+230h], rax
0x180169688  lea     rax, ??_7OnDelayedSourceEventAsyncCallback@CMediaSession@@6B@; const CMediaSession::OnDelayedSourceEventAsyncCallback::`vftable'
0x18016968f  mov     [r14+238h], rax
0x180169696  lea     rax, ??_7OnBitPumpEventAsyncCallback@CMediaSession@@6B@; const CMediaSession::OnBitPumpEventAsyncCallback::`vftable'
0x18016969d  mov     [r14+240h], rax
0x1801696a4  lea     rax, ??_7OnDelayedBitPumpEventAsyncCallback@CMediaSession@@6B@; const CMediaSession::OnDelayedBitPumpEventAsyncCallback::`vftable'
0x1801696ab  mov     [r14+248h], rax
0x1801696b2  lea     rax, ??_7OnSinkEventAsyncCallback@CMediaSession@@6B@; const CMediaSession::OnSinkEventAsyncCallback::`vftable'
0x1801696b9  mov     [r14+250h], rax
0x1801696c0  lea     rax, ??_7OnTimerAsyncCallback@CMediaSession@@6B@; const CMediaSession::OnTimerAsyncCallback::`vftable'
0x1801696c7  mov     [r14+258h], rax
0x1801696ce  lea     rax, ??_7OnFinalizeSinksAsyncCallback@CMediaSession@@6B@; const CMediaSession::OnFinalizeSinksAsyncCallback::`vftable'
0x1801696d5  mov     [r14+260h], rax
0x1801696dc  lea     rax, ??_7OnEnsureTrustAsyncCallback@CMediaSession@@6B@; const CMediaSession::OnEnsureTrustAsyncCallback::`vftable'
0x1801696e3  mov     [r14+268h], rax
0x1801696ea  call    cs:__imp_InitializeCriticalSection
0x1801696f1  nop     dword ptr [rax+rax+00h]
0x1801696f6  mov     rcx, [rbp+40h+arg_30]
0x1801696fd  xor     edx, edx
0x1801696ff  mov     [r14+298h], rdx
0x180169706  mov     [r14+2A0h], rdx
0x18016970d  mov     [r14+2A8h], rdx
0x180169714  mov     [r14+2B0h], rcx
0x18016971b  test    rcx, rcx
0x18016971e  jz      short loc_18016972F
0x180169720  mov     rax, [rcx]
0x180169723  mov     rax, [rax+8]
0x180169727  call    cs:__guard_dispatch_icall_fptr
0x18016972d  xor     edx, edx
0x18016972f  mov     [r14+2C0h], rdx
0x180169736  lea     rax, [r14+330h]
0x18016973d  mov     [r14+2C8h], rdx
0x180169744  lea     r15, [r14+2F8h]
0x18016974b  mov     [r15], rdx
0x18016974e  lea     rbx, [r14+300h]
0x180169755  mov     [rbx], rdx
0x180169758  lea     rdi, [r14+308h]
0x18016975f  mov     [rdi], rdx
0x180169762  lea     rcx, [r14+348h]; this
0x180169769  mov     [r14+2F0h], rdx
0x180169770  mov     [r14+320h], rdx
0x180169777  mov     [r14+328h], edx
0x18016977e  mov     [r14+340h], rdx
0x180169785  mov     [r14+2B8h], rdx
0x18016978c  mov     [r14+2D0h], edx
0x180169793  mov     [r14+2E8h], edx
0x18016979a  mov     [r14+31Ch], edx
0x1801697a1  lea     rdx, dword_18037E948; unsigned int *
0x1801697a8  mov     qword ptr [r14+2D8h], 3F800000h
0x1801697b3  mov     qword ptr [r14+2E0h], 0
0x1801697be  mov     qword ptr [r14+314h], 0
0x1801697c9  mov     [r14+338h], rax
0x1801697d0  mov     [rax], rax
0x1801697d3  call    ??0COOEHandler@@QEAA@QEBKK@Z; COOEHandler::COOEHandler(ulong const * const,ulong)
0x1801697d8  lea     rcx, [r14+358h]; this
0x1801697df  lea     rdx, dword_18037E950; unsigned int *
0x1801697e6  call    ??0COOEHandler@@QEAA@QEBKK@Z; COOEHandler::COOEHandler(ulong const * const,ulong)
0x1801697eb  lea     rcx, [r14+368h]; this
0x1801697f2  mov     rdx, rsi; int *
0x1801697f5  call    ??0CMFMediaEventGenerator@@QEAA@PEAJ@Z; CMFMediaEventGenerator::CMFMediaEventGenerator(long *)
0x1801697fa  xor     edx, edx
0x1801697fc  mov     [r14+3F8h], r14
0x180169803  lea     rax, ??_7OnFinalizeSinkAsyncCallback@CMediaSessionPresentationHandler@@6B@; const CMediaSessionPresentationHandler::OnFinalizeSinkAsyncCallback::`vftable'
0x18016980a  mov     [r14+3E8h], rdx
0x180169811  lea     rcx, [r14+658h]; this
0x180169818  mov     [r14+3F0h], rdx
0x18016981f  mov     [r14+400h], rdx
0x180169826  mov     [r14+408h], rdx
0x18016982d  mov     [r14+410h], edx
0x180169834  mov     [r14+5B8h], edx
0x18016983b  mov     [r14+5B0h], rdx
0x180169842  mov     [r14+5A8h], rdx
0x180169849  mov     [r14+5A0h], rdx
0x180169850  mov     [r14+5C0h], rdx
0x180169857  mov     [r14+5C8h], rdx
0x18016985e  mov     [r14+5D0h], rax
0x180169865  mov     [r14+5E8h], edx
0x18016986c  mov     [r14+5F8h], rcx
0x180169873  mov     [r14+600h], rdx
0x18016987a  mov     [r14+60Ch], rdx
0x180169881  mov     [r14+608h], edx
0x180169888  mov     [r14+618h], rdx
0x18016988f  mov     [r14+624h], rdx
0x180169896  mov     [r14+620h], edx
0x18016989d  mov     [r14+5D8h], r14
0x1801698a4  mov     [r14+5E0h], r14
0x1801698ab  mov     [r14+5F0h], r14
0x1801698b2  mov     [r14+630h], r14
0x1801698b9  mov     [r14+638h], rdx
0x1801698c0  mov     [r14+648h], rdx
0x1801698c7  mov     [r14+650h], rdx
0x1801698ce  mov     [r14+3E0h], dx
0x1801698d6  mov     [r14+640h], edx
0x1801698dd  call    ??0CMediaSessionTelemetry@@QEAA@XZ; CMediaSessionTelemetry::CMediaSessionTelemetry(void)
0x1801698e2  lea     rax, ??_7OnShutdownAsyncCallback@CMediaSession@@6B@; const CMediaSession::OnShutdownAsyncCallback::`vftable'
0x1801698e9  mov     [r14+51A0h], rax
0x1801698f0  lea     rcx, [r14+270h]; lpCriticalSection
0x1801698f7  xor     eax, eax
0x1801698f9  mov     [r14+51A8h], rax
0x180169900  mov     esi, [rsi]
0x180169902  mov     [r14+310h], eax
0x180169909  mov     [rbp+40h+var_A8], rax
0x18016990d  mov     [rbp+40h+hMem], rax
0x180169911  mov     [rbp+40h+var_B0], rax
0x180169915  mov     [rsp+140h+var_D8], rax
0x18016991a  mov     [rbp+40h+var_B8], rax
0x18016991e  call    cs:__imp_EnterCriticalSection
0x180169925  nop     dword ptr [rax+rax+00h]
0x18016992a  mov     r8d, 3DBh; int
0x180169930  lea     rdx, aCmediasessionC; "CMediaSession::CMediaSession"
0x180169937  lea     rcx, [rsp+140h+var_100]; this
0x18016993c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180169941  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180169948  cmp     byte ptr [rcx+8], 0
0x18016994c  jz      short loc_1801699BA
0x18016994e  cmp     qword ptr [r14+650h], 0
0x180169956  jz      short loc_1801699BA
0x180169958  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016995d  mov     rcx, [r14+650h]
0x180169964  mov     rdi, rax
0x180169967  mov     rax, [rcx]
0x18016996a  mov     rax, [rax+128h]
0x180169971  call    cs:__guard_dispatch_icall_fptr
0x180169977  mov     rcx, [r14+650h]
0x18016997e  lea     rdx, [rbp+40h+string]
0x180169982  mov     ebx, eax
0x180169984  mov     rax, [rcx]
0x180169987  mov     rax, [rax+118h]
0x18016998e  call    cs:__guard_dispatch_icall_fptr
0x180169994  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016999b  movups  xmm0, xmmword ptr [rax]
0x18016999e  mov     [rdi+7E0h], ebx
0x1801699a4  lea     rbx, [r14+300h]
0x1801699ab  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1801699b3  lea     rdi, [r14+308h]
0x1801699ba  test    esi, esi
0x1801699bc  jns     short loc_180169A18
0x1801699be  test    rcx, rcx
0x1801699c1  jnz     short loc_1801699CF
0x1801699c3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1801699c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801699cf  cmp     byte ptr [rcx+8], 0
0x1801699d3  jz      short loc_1801699FA
0x1801699d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801699da  cmp     [rax+7CCh], esi
0x1801699e0  jz      short loc_1801699FA
0x1801699e2  mov     r9d, esi; int
0x1801699e5  lea     rdx, aCmediasessionC; "CMediaSession::CMediaSession"
0x1801699ec  mov     r8d, 3DBh; int
0x1801699f2  mov     rcx, rax; this
0x1801699f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801699fa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180169a01  jb      loc_18016A9C6
0x180169a07  mov     edx, 2Ch ; ','
0x180169a0c  lea     r8, WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids
0x180169a13  jmp     loc_18016A9AF
0x180169a18  mov     ecx, cs:dword_1803CEFD0
0x180169a1e  lea     rdx, qword_1803CEFB0
0x180169a25  mov     eax, ecx
0x180169a27  xor     esi, esi
0x180169a29  and     eax, 3
0x180169a2c  mov     [r14+5A0h], rsi
0x180169a33  mov     [rdx+rax*8], r14
0x180169a37  lea     eax, [rcx+1]
0x180169a3a  and     eax, 3
0x180169a3d  mov     cs:dword_1803CEFD0, eax
0x180169a43  lea     rax, [r14+270h]
0x180169a4a  mov     [r14+340h], rax
0x180169a51  cmp     [r14+408h], rsi
0x180169a58  jnz     short loc_180169AAA
0x180169a5a  lea     rax, [r14+418h]
0x180169a61  mov     dword ptr [r14+410h], 1
0x180169a6c  mov     [r14+408h], rax
0x180169a73  mov     r9d, esi
0x180169a76  mov     [rax], rsi
0x180169a79  mov     rax, [r14+408h]
0x180169a80  lea     r8, ds:1[r9*2]
0x180169a88  add     r8, r9
0x180169a8b  inc     r9
0x180169a8e  lea     r8, [rax+r8*8]
0x180169a92  mov     rax, [r14+400h]
0x180169a99  mov     [r8+8], rax
0x180169a9d  mov     [r14+400h], r8
0x180169aa4  cmp     r9, 10h
0x180169aa8  jnz     short loc_180169A79
0x180169aaa  xor     edx, edx; unsigned int
0x180169aac  mov     rcx, r14; this
0x180169aaf  call    ?WaitOnEvent@CMediaSession@@AEAAXK@Z; CMediaSession::WaitOnEvent(ulong)
0x180169ab4  mov     rdx, qword ptr [rbp+40h+rclsid.Data1]
0x180169ab8  mov     rcx, r15
0x180169abb  call    ??4?$ComSmartPtr@VCPMPStreamStub@@@@QEAAPEAVCPMPStreamStub@@PEAV1@@Z; ComSmartPtr<CPMPStreamStub>::operator=(CPMPStreamStub *)
0x180169ac0  mov     rdx, qword ptr [rsp+140h+var_D0]
0x180169ac5  mov     rcx, rbx
0x180169ac8  call    ??4?$ComSmartPtr@VCPMPStreamStub@@@@QEAAPEAVCPMPStreamStub@@PEAV1@@Z; ComSmartPtr<CPMPStreamStub>::operator=(CPMPStreamStub *)
0x180169acd  mov     rdx, [rsp+140h+ppstm]
0x180169ad2  mov     rcx, rdi
0x180169ad5  call    ??4?$ComSmartPtr@VCPMPStreamStub@@@@QEAAPEAVCPMPStreamStub@@PEAV1@@Z; ComSmartPtr<CPMPStreamStub>::operator=(CPMPStreamStub *)
0x180169ada  mov     rdx, [rsp+140h+var_F0]
0x180169adf  lea     rdi, [r14+2F0h]
0x180169ae6  mov     rcx, rdi
0x180169ae9  call    ??4?$ComSmartPtr@VCPMPStreamStub@@@@QEAAPEAVCPMPStreamStub@@PEAV1@@Z; ComSmartPtr<CPMPStreamStub>::operator=(CPMPStreamStub *)
0x180169aee  mov     rdx, [rsp+140h+var_F8]
0x180169af3  lea     rcx, [r14+3E8h]
0x180169afa  call    ??4?$ComSmartPtr@VCPMPStreamStub@@@@QEAAPEAVCPMPStreamStub@@PEAV1@@Z; ComSmartPtr<CPMPStreamStub>::operator=(CPMPStreamStub *)
0x180169aff  lea     r15, WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids
0x180169b06  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180169b0d  movdqu  [rbp+40h+var_80], xmm0
0x180169b12  test    r12, r12
0x180169b15  jz      loc_18016A3AC
0x180169b1b  mov     rax, [r12]
0x180169b1f  lea     rdx, _GUID_627d2ca6_e1cd_4898_999d_101308f1d431
0x180169b26  lea     r9, [rsp+140h+var_D8]
0x180169b2b  mov     dword ptr [rsp+140h+dwBytes], esi
0x180169b2f  mov     r8, rdx
0x180169b32  mov     dword ptr [rsp+140h+dwBytes+4], esi
0x180169b36  mov     rcx, r12
0x180169b39  mov     rax, [rax+88h]
0x180169b40  call    cs:__guard_dispatch_icall_fptr
0x180169b46  test    eax, eax
0x180169b48  js      short loc_180169B89
0x180169b4a  mov     rcx, [rsp+140h+var_D8]
0x180169b4f  lea     rdx, [rbp+40h+string]
0x180169b53  mov     rax, [rcx]
0x180169b56  mov     rax, [rax+118h]
0x180169b5d  call    cs:__guard_dispatch_icall_fptr
0x180169b63  mov     rcx, [rsp+140h+var_D8]
0x180169b68  movups  xmm0, xmmword ptr [rax]
0x180169b6b  movdqu  [rbp+40h+var_80], xmm0
0x180169b70  mov     rax, [rcx]
0x180169b73  mov     rax, [rax+128h]
0x180169b7a  call    cs:__guard_dispatch_icall_fptr
0x180169b80  mov     dword ptr [rsp+140h+dwBytes+4], eax
0x180169b84  jmp     loc_180169C0B
0x180169b89  mov     rax, [r12]
0x180169b8d  lea     r8, [rbp+40h+var_80]
0x180169b91  lea     rdx, MEDIA_TELEMETRY_SESSION_ID
0x180169b98  mov     rcx, r12
0x180169b9b  mov     rax, [rax+50h]
0x180169b9f  call    cs:__guard_dispatch_icall_fptr
0x180169ba5  mov     rax, [r12]
0x180169ba9  lea     r8, [rsp+140h+dwBytes+4]
0x180169bae  lea     rdx, MEDIA_TELEMETRY_INSTANCE_ID
0x180169bb5  mov     rcx, r12
0x180169bb8  mov     rax, [rax+38h]
0x180169bbc  call    cs:__guard_dispatch_icall_fptr
0x180169bc2  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180169bc9  lea     r8, [rsp+140h+var_D8]
0x180169bce  lea     rdx, [rbp+40h+rclsid]
  ... truncated ...
```
