# CDShowSource::CDShowSource(ushort const *,IMFByteStream *,IPropertyStore *,int,long *)

- ea: `0x180034274`
- end: `0x180034b31`
- name: `??0CDShowSource@@IEAA@PEBGPEAUIMFByteStream@@PEAUIPropertyStore@@HPEAJ@Z`
- size: `2237`
- prototype: `CDShowSource *__fastcall(CDShowSource *this, unsigned __int16 *, struct IMFByteStream *, struct IPropertyStore *, int, int *)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033b00`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x18002f998`
- `0x180032a50`
- `0x180034274`
- `0x180034b38`
- `0x180034d1c`
- `0x180035484`
- `0x180035768`
- `0x180035974`
- `0x1800359b0`
- `0x180035b14`
- `0x180035b84`
- `0x180048f30`
- `0x18004d7cc`
- `0x1800501dc`
- `0x180051ce4`
- `0x1800545e4`
- `0x1800545fc`
- `0x180054614`
- `0x18005462c`
- `0x180054644`
- `0x180073d0c`
- `0x180074160`
- `0x180074a06`
- `0x18007c8e8`
- `0x18008aaac`
- `0x180095050`
- `0x1800975e4`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x18003453a`
- `api-ms-win-crt-string-l1-1-0!memset` at `0x180034649`
- `api-ms-win-crt-string-l1-1-0!memset` at `0x18003453a`
- `api-ms-win-crt-string-l1-1-0!memset` at `0x180034649`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800348b0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800348b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003478e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003497f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034a15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003478e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003497f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034a15`
- `MFPlat!CreatePropertyStore` at `0x18003456f`
- `MFPlat!CreatePropertyStore` at `0x18003456f`
- `MFPlat!MFCreateTelemetrySession` at `0x1800345da`
- `MFPlat!MFCreateTelemetrySession` at `0x1800345da`

## pseudocode

```c
CDShowSource *__fastcall CDShowSource::CDShowSource(
        CDShowSource *this,
        unsigned __int16 *a2,
        struct IMFByteStream *a3,
        struct IPropertyStore *a4,
        int a5,
        int *a6)
{
  int v8; // ecx
  int v9; // r15d
  unsigned int v10; // r9d
  _QWORD *v11; // r14
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v13; // ebx
  __int128 v14; // xmm0
  int v15; // edi
  int v16; // r13d
  struct CDShowStream *v17; // rbx
  IPropertyStore *v18; // rcx
  char *v19; // r8
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  CDShowSBEWrapper *v23; // rcx
  CDShowWrapper *v24; // r8
  IPropertyStore *v25; // rcx
  CDShowWrapper *v26; // rcx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  int v31; // eax
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  unsigned int i; // r14d
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  int *v43; // rax
  unsigned int v45; // [rsp+20h] [rbp-A9h]
  char v46[8]; // [rsp+30h] [rbp-99h] BYREF
  IPropertyStore *ppStore; // [rsp+38h] [rbp-91h] BYREF
  struct CDShowStream *v48; // [rsp+40h] [rbp-89h] BYREF
  struct IMFByteStream *v49; // [rsp+48h] [rbp-81h]
  unsigned __int16 *v50; // [rsp+50h] [rbp-79h]
  PROPVARIANT pvar; // [rsp+58h] [rbp-71h] BYREF
  __int16 v52; // [rsp+70h] [rbp-59h] BYREF
  void (__fastcall ***v53)(_QWORD, GUID *, char *); // [rsp+78h] [rbp-51h]
  int *v54; // [rsp+88h] [rbp-41h]
  GUID v55; // [rsp+90h] [rbp-39h] BYREF
  int v56; // [rsp+A0h] [rbp-29h] BYREF
  GUID v57; // [rsp+B0h] [rbp-19h] BYREF

  v50 = a2;
  v49 = a3;
  v54 = a6;
  CDSSourceObjectBase::CDSSourceObjectBase((CDShowSource *)((char *)this + 32), a6);
  v9 = 1;
  *((_DWORD *)this + 36) = 1148407123;
  *((_DWORD *)this + 37) = 17;
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
  {
    v56 = 1397584708;
    McTemplateU0s4pu_EventWriteTransfer(v8, (unsigned int)Object_Create, (unsigned int)&v56, (_DWORD)this + 144, 17);
  }
  *(_QWORD *)this = &CDShowSource::`vftable'{for `IMFMediaSourceEx'};
  *((_QWORD *)this + 1) = &CDShowSource::`vftable'{for `IMFGetService'};
  *((_QWORD *)this + 2) = &CDShowSource::`vftable'{for `IMFRateSupport'};
  *((_QWORD *)this + 3) = &CDShowSource::`vftable'{for `IMFRateControl'};
  *((_QWORD *)this + 4) = &CDShowSource::`vftable'{for `CDSSourceObjectBase'};
  *((_QWORD *)this + 13) = &CDShowSource::`vftable'{for `IMFPMPClient'};
  *((_QWORD *)this + 14) = &CDShowSource::`vftable'{for `IMFTrustedInput'};
  *((_QWORD *)this + 15) = &CDShowSource::`vftable'{for `IMFClockConsumer'};
  *((_QWORD *)this + 16) = &CDShowSource::`vftable'{for `IMFTelemetryComponent'};
  *((_QWORD *)this + 17) = &CDShowSource::`vftable'{for `IReferenceClock'};
  CDShowSource::OnDShowWrapperStartAsyncCallback::OnDShowWrapperStartAsyncCallback((CDShowSource *)((char *)this + 152));
  CDShowSource::OnDShowWrapperStopAsyncCallback::OnDShowWrapperStopAsyncCallback((CDShowSource *)((char *)this + 160));
  CDShowSource::OnDShowWrapperPauseAsyncCallback::OnDShowWrapperPauseAsyncCallback((CDShowSource *)((char *)this + 168));
  CDShowSource::OnDShowWrapperSetRateAsyncCallback::OnDShowWrapperSetRateAsyncCallback((CDShowSource *)((char *)this + 176));
  CDShowPreferenceManager::CDShowPreferenceManager((CDShowSource *)((char *)this + 184), a4, a6);
  COpQueue::COpQueue((CDShowSource *)((char *)this + 224), (CDShowSource *)((char *)this + 48), a6, v10, v45);
  *((_QWORD *)this + 89) = this;
  *((_QWORD *)this + 28) = &CDShowSourceOpQueue::`vftable';
  *((_QWORD *)this + 90) = 0;
  CSourceStateManager::CSourceStateManager((CDShowSource *)((char *)this + 728));
  *((_QWORD *)this + 92) = 0;
  CStreamAggregator::CStreamAggregator((CDShowSource *)((char *)this + 744), a6);
  *((_QWORD *)this + 102) = 0;
  *((_WORD *)this + 416) = 0;
  *((_BYTE *)this + 834) = 0;
  memset_0((char *)this + 840, 0, 0xA0u);
  *((_DWORD *)this + 205) |= 1u;
  *((_QWORD *)this + 101) = &CTPtrArray<SampleSinkEntry,20>::`vftable';
  *((_QWORD *)this + 125) = 0;
  *((_DWORD *)this + 252) = 0;
  *((_QWORD *)this + 103) = 0;
  *((_QWORD *)this + 127) = 0;
  *((_QWORD *)this + 128) = 1065353216;
  *((_QWORD *)this + 129) = 0;
  *((_DWORD *)this + 260) = 0;
  *((_QWORD *)this + 131) = 0;
  CDShowSource::OnTimerAsyncCallback::OnTimerAsyncCallback((CDShowSource *)((char *)this + 1056));
  *((_QWORD *)this + 133) = 0;
  v11 = (_QWORD *)((char *)this + 1096);
  *((_QWORD *)this + 134) = 0;
  *((_QWORD *)this + 135) = 0;
  *((_QWORD *)this + 136) = 0;
  *((_QWORD *)this + 137) = 0;
  *((_QWORD *)this + 138) = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v46, "CDShowSource::CDShowSource", 131);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *v11 )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v13 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 296LL))(*v11);
    v14 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*v11 + 280LL))(*v11, &v57);
    *((_DWORD *)ThreadRelativeContext + 504) = v13;
    *((_OWORD *)ThreadRelativeContext + 125) = v14;
  }
  v15 = *a6;
  v16 = 0;
  v17 = 0;
  v48 = 0;
  memset(&pvar, 0, sizeof(pvar));
  memset(&v52, 0, 0x18u);
  ppStore = a4;
  if ( a4 && (((void (__fastcall *)(struct IPropertyStore *))a4->lpVtbl->AddRef)(a4), (v18 = ppStore) != 0)
    || (CreatePropertyStore(&ppStore), (v18 = ppStore) != 0) )
  {
    ((void (__fastcall *)(IPropertyStore *, __int64 *, __int16 *))v18->lpVtbl->GetValue)(
      v18,
      MFPKEY_TELEMETRY_SESSION,
      &v52);
    v19 = (char *)this + 1096;
    if ( v52 == 13 )
    {
      (**v53)(v53, &GUID_627d2ca6_e1cd_4898_999d_101308f1d431, v19);
    }
    else
    {
      v55 = GUID_00000000_0000_0000_0000_000000000000;
      v57 = GUID_00000000_0000_0000_0000_000000000000;
      if ( (int)MFCreateTelemetrySession(&v57, &v55, v19) >= 0 )
      {
        CMFPropVariant::operator=(&v52, *v11);
        ((void (__fastcall *)(IPropertyStore *, __int64 *, __int16 *))ppStore->lpVtbl->SetValue)(
          ppStore,
          MFPKEY_TELEMETRY_SESSION,
          &v52);
      }
    }
    if ( *v11 )
    {
      ComSmartPtr<IBaseFilter>::operator=((char *)this + 1104, (char *)this + 1096);
      (*(void (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*v11 + 336LL))(*v11, &GUID_MFDSTelemetrySessionOwnership);
    }
  }
  memset(&pvar, 0, sizeof(pvar));
  if ( v15 < 0 )
  {
    v20 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v20 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext(v20);
      if ( *((_DWORD *)v21 + 499) != v15 )
        CallStackContext::TraceFailure(v21, "CDShowSource::CDShowSource", 175, v15);
    }
    if ( !g_wppLevels )
      goto LABEL_83;
    v22 = 16;
LABEL_23:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids, this, v15);
LABEL_83:
    v9 = 0;
    goto LABEL_84;
  }
  if ( *((int *)this + 54) <= 0 )
  {
    v26 = (CDShowWrapper *)operator new(0x1F0u);
    if ( v26 )
      v24 = CDShowWrapper::CDShowWrapper(v26, this, v50, v49, a5);
    else
      v24 = 0;
    *((_QWORD *)this + 92) = v24;
  }
  else
  {
    v23 = (CDShowSBEWrapper *)operator new(0x300u);
    if ( v23 )
      v24 = CDShowSBEWrapper::CDShowSBEWrapper(v23, this, v50, v49, a5, *((_DWORD *)this + 54));
    else
      v24 = 0;
    v25 = ppStore;
    *((_QWORD *)this + 92) = v24;
    if ( v25 )
    {
      pvar.lVal = 0;
      pvar.vt = 22;
      ((void (__fastcall *)(IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v25->lpVtbl->SetValue)(
        v25,
        &MFPKEY_SBESourceMode,
        &pvar);
      v24 = (CDShowWrapper *)*((_QWORD *)this + 92);
    }
  }
  if ( !v24 )
  {
    v27 = (__int64 *)CallStackTracing::s_wpInstance;
    v15 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = &qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v27 + 8) )
    {
      v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
      if ( *((_DWORD *)v29 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v29, "CDShowSource::CDShowSource", 195, -2147024882);
    }
    if ( g_wppLevels )
    {
      v30 = 17;
LABEL_45:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v30,
        &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids,
        this,
        -2147024882);
    }
    goto LABEL_83;
  }
  v31 = (*(__int64 (__fastcall **)(CDShowWrapper *, IPropertyStore *))(*(_QWORD *)v24 + 40LL))(v24, ppStore);
  v15 = v31;
  if ( v31 < 0 )
  {
    v32 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v32 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v33 = CallStackTracing::GetThreadRelativeContext(v32);
      if ( *((_DWORD *)v33 + 499) != v15 )
        CallStackContext::TraceFailure(v33, "CDShowSource::CDShowSource", 197, v15);
    }
    if ( !g_wppLevels )
      goto LABEL_83;
    v22 = 18;
    goto LABEL_23;
  }
  v16 = v31;
  PropVariantClear(&pvar);
  for ( i = 0; i < *(_DWORD *)(*((_QWORD *)this + 92) + 288LL); ++i )
  {
    ComSmartPtr<CDShowStream>::operator=(&v48, 0);
    v35 = CTPtrArray<CDShowStream,20>::operator[](*((_QWORD *)this + 92) + 88LL, i);
    v15 = CDShowStream::CreateInstance(i + 1, this, *(struct CDSSampleSink **)(v35 + 8), &v48);
    if ( v15 < 0 )
    {
      v40 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v40 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
        if ( *((_DWORD *)v42 + 499) != v15 )
          CallStackContext::TraceFailure(v42, "CDShowSource::CDShowSource", 209, v15);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids, this, v15);
      v17 = v48;
      goto LABEL_83;
    }
    v17 = v48;
    if ( !(unsigned int)CTPtrArray<CDShowStream,20>::Add((char *)this + 808, v48) )
    {
      v37 = (__int64 *)CallStackTracing::s_wpInstance;
      v15 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v38;
        if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
        {
          v37 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v37 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
        if ( *((_DWORD *)v39 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v39, "CDShowSource::CDShowSource", 217, -2147024882);
      }
      if ( g_wppLevels )
      {
        v30 = 20;
        goto LABEL_45;
      }
      goto LABEL_83;
    }
    if ( v17 )
      (*(void (__fastcall **)(struct CDShowStream *))(*(_QWORD *)v17 + 8LL))(v17);
    v36 = CTPtrArray<CDShowStream,20>::operator[]((char *)this + 808, i);
    *(_DWORD *)(v36 + 180) = *(_DWORD *)(*((_QWORD *)this + 92) + 472LL);
  }
LABEL_84:
  v43 = v54;
  *((_DWORD *)this + 258) = v9;
  if ( !v9 )
    v16 = v15;
  *v43 = v16;
  if ( ppStore )
    ((void (__fastcall *)(IPropertyStore *))ppStore->lpVtbl->Release)(ppStore);
  CMFPropVariant::Clear((CMFPropVariant *)&v52);
  if ( v17 )
    (*(void (__fastcall **)(struct CDShowStream *))(*(_QWORD *)v17 + 16LL))(v17);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v46);
  return this;
}

```

## disassembly

```asm
0x180034274  push    rbp
0x180034276  push    rbx
0x180034277  push    rsi
0x180034278  push    rdi
0x180034279  push    r12
0x18003427b  push    r13
0x18003427d  push    r14
0x18003427f  push    r15
0x180034281  lea     rbp, [rsp-0Fh]
0x180034286  sub     rsp, 0D8h
0x18003428d  mov     rax, cs:__security_cookie
0x180034294  xor     rax, rsp
0x180034297  mov     [rbp+47h+var_50], rax
0x18003429b  mov     r13, [rbp+47h+arg_28]
0x18003429f  mov     rsi, rcx
0x1800342a2  mov     [rbp+47h+var_C0], rdx
0x1800342a6  add     rcx, 20h ; ' '; this
0x1800342aa  mov     rdx, r13; int *
0x1800342ad  mov     [rsp+110h+var_C8], r8
0x1800342b2  mov     r12, r9
0x1800342b5  mov     [rbp+47h+var_88], r13
0x1800342b9  call    ??0CDSSourceObjectBase@@QEAA@PEAJ@Z; CDSSourceObjectBase::CDSSourceObjectBase(long *)
0x1800342be  lea     r9, [rsi+90h]
0x1800342c5  mov     r15d, 1
0x1800342cb  mov     dword ptr [r9], 44734D53h
0x1800342d2  mov     dword ptr [r9+4], 11h
0x1800342da  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, r15b
0x1800342e1  jz      short loc_1800342FF
0x1800342e3  lea     r8, [rbp+47h+var_70]
0x1800342e7  mov     [rbp+47h+var_70], 534D7344h
0x1800342ee  lea     rdx, Object_Create
0x1800342f5  mov     byte ptr [rsp+110h+var_F0], 11h; unsigned int
0x1800342fa  call    McTemplateU0s4pu_EventWriteTransfer
0x1800342ff  lea     rax, ??_7CDShowSource@@6BIMFMediaSourceEx@@@; const CDShowSource::`vftable'{for `IMFMediaSourceEx'}
0x180034306  mov     [rsi], rax
0x180034309  lea     rcx, [rsi+98h]; this
0x180034310  lea     rax, ??_7CDShowSource@@6BIMFGetService@@@; const CDShowSource::`vftable'{for `IMFGetService'}
0x180034317  mov     [rsi+8], rax
0x18003431b  lea     rax, ??_7CDShowSource@@6BIMFRateSupport@@@; const CDShowSource::`vftable'{for `IMFRateSupport'}
0x180034322  mov     [rsi+10h], rax
0x180034326  lea     rax, ??_7CDShowSource@@6BIMFRateControl@@@; const CDShowSource::`vftable'{for `IMFRateControl'}
0x18003432d  mov     [rsi+18h], rax
0x180034331  lea     rax, ??_7CDShowSource@@6BCDSSourceObjectBase@@@; const CDShowSource::`vftable'{for `CDSSourceObjectBase'}
0x180034338  mov     [rsi+20h], rax
0x18003433c  lea     rax, ??_7CDShowSource@@6BIMFPMPClient@@@; const CDShowSource::`vftable'{for `IMFPMPClient'}
0x180034343  mov     [rsi+68h], rax
0x180034347  lea     rax, ??_7CDShowSource@@6BIMFTrustedInput@@@; const CDShowSource::`vftable'{for `IMFTrustedInput'}
0x18003434e  mov     [rsi+70h], rax
0x180034352  lea     rax, ??_7CDShowSource@@6BIMFClockConsumer@@@; const CDShowSource::`vftable'{for `IMFClockConsumer'}
0x180034359  mov     [rsi+78h], rax
0x18003435d  lea     rax, ??_7CDShowSource@@6BIMFTelemetryComponent@@@; const CDShowSource::`vftable'{for `IMFTelemetryComponent'}
0x180034364  mov     [rsi+80h], rax
0x18003436b  lea     rax, ??_7CDShowSource@@6BIReferenceClock@@@; const CDShowSource::`vftable'{for `IReferenceClock'}
0x180034372  mov     [rsi+88h], rax
0x180034379  call    ??0OnDShowWrapperStartAsyncCallback@CDShowSource@@QEAA@XZ; CDShowSource::OnDShowWrapperStartAsyncCallback::OnDShowWrapperStartAsyncCallback(void)
0x18003437e  lea     rcx, [rsi+0A0h]; this
0x180034385  call    ??0OnDShowWrapperStopAsyncCallback@CDShowSource@@QEAA@XZ; CDShowSource::OnDShowWrapperStopAsyncCallback::OnDShowWrapperStopAsyncCallback(void)
0x18003438a  lea     rcx, [rsi+0A8h]; this
0x180034391  call    ??0OnDShowWrapperPauseAsyncCallback@CDShowSource@@QEAA@XZ; CDShowSource::OnDShowWrapperPauseAsyncCallback::OnDShowWrapperPauseAsyncCallback(void)
0x180034396  lea     rcx, [rsi+0B0h]; this
0x18003439d  call    ??0OnDShowWrapperSetRateAsyncCallback@CDShowSource@@QEAA@XZ; CDShowSource::OnDShowWrapperSetRateAsyncCallback::OnDShowWrapperSetRateAsyncCallback(void)
0x1800343a2  lea     rcx, [rsi+0B8h]; this
0x1800343a9  mov     r8, r13; int *
0x1800343ac  mov     rdx, r12; struct IPropertyStore *
0x1800343af  call    ??0CDShowPreferenceManager@@QEAA@PEAUIPropertyStore@@PEAJ@Z; CDShowPreferenceManager::CDShowPreferenceManager(IPropertyStore *,long *)
0x1800343b4  lea     rbx, [rsi+0E0h]
0x1800343bb  mov     r8, r13; int *
0x1800343be  mov     rcx, rbx; this
0x1800343c1  lea     rdx, [rsi+30h]; struct CMFCSLock *
0x1800343c5  call    ??0COpQueue@@QEAA@PEAVCMFCSLock@@PEAJKK@Z; COpQueue::COpQueue(CMFCSLock *,long *,ulong,ulong)
0x1800343ca  lea     rax, ??_7CDShowSourceOpQueue@@6B@; const CDShowSourceOpQueue::`vftable'
0x1800343d1  mov     [rbx+1E8h], rsi
0x1800343d8  xor     edi, edi
0x1800343da  mov     [rbx], rax
0x1800343dd  lea     rcx, [rsi+2D8h]; this
0x1800343e4  mov     [rbx+1F0h], rdi
0x1800343eb  call    ??0CSourceStateManager@@QEAA@XZ; CSourceStateManager::CSourceStateManager(void)
0x1800343f0  lea     rcx, [rsi+2E8h]; this
0x1800343f7  mov     [rsi+2E0h], rdi
0x1800343fe  mov     rdx, r13; int *
0x180034401  call    ??0CStreamAggregator@@QEAA@PEAJ@Z; CStreamAggregator::CStreamAggregator(long *)
0x180034406  lea     rbx, [rsi+328h]
0x18003440d  xor     eax, eax
0x18003440f  mov     [rbx+8], rdi
0x180034413  lea     rcx, [rbx+20h]; void *
0x180034417  mov     [rbx+18h], ax
0x18003441b  xor     edx, edx; Val
0x18003441d  mov     r8d, 0A0h; Size
0x180034423  mov     [rbx+1Ah], al
0x180034426  call    memset_0
0x18003442b  or      [rbx+0Ch], r15d
0x18003442f  lea     rax, ??_7?$CTPtrArray@USampleSinkEntry@@$0BE@@@6B@; const CTPtrArray<SampleSinkEntry,20>::`vftable'
0x180034436  mov     [rbx], rax
0x180034439  lea     rcx, [rsi+420h]; this
0x180034440  mov     [rbx+0C0h], rdi
0x180034447  mov     [rbx+0C8h], edi
0x18003444d  mov     [rbx+10h], rdi
0x180034451  mov     [rsi+3F8h], rdi
0x180034458  mov     qword ptr [rsi+400h], 3F800000h
0x180034463  mov     [rsi+408h], rdi
0x18003446a  mov     [rsi+410h], edi
0x180034470  mov     [rsi+418h], rdi
0x180034477  call    ??0OnTimerAsyncCallback@CDShowSource@@QEAA@XZ; CDShowSource::OnTimerAsyncCallback::OnTimerAsyncCallback(void)
0x18003447c  mov     [rsi+428h], rdi
0x180034483  lea     r14, [rsi+448h]
0x18003448a  mov     [rsi+430h], rdi
0x180034491  lea     rdx, aCdshowsourceCd; "CDShowSource::CDShowSource"
0x180034498  mov     [rsi+438h], rdi
0x18003449f  lea     rcx, [rsp+110h+var_E0]; this
0x1800344a4  mov     [rsi+440h], rdi
0x1800344ab  mov     r8d, 83h; int
0x1800344b1  mov     [r14], rdi
0x1800344b4  mov     [rsi+450h], rdi
0x1800344bb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800344c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800344c7  cmp     [rcx+8], dil
0x1800344cb  jz      short loc_180034515
0x1800344cd  cmp     [r14], rdi
0x1800344d0  jz      short loc_180034515
0x1800344d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800344d7  mov     rcx, [r14]
0x1800344da  mov     rdi, rax
0x1800344dd  mov     rax, [rcx]
0x1800344e0  mov     rax, [rax+128h]
0x1800344e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344ec  mov     rcx, [r14]
0x1800344ef  lea     rdx, [rbp+47h+var_60]
0x1800344f3  mov     ebx, eax
0x1800344f5  mov     rax, [rcx]
0x1800344f8  mov     rax, [rax+118h]
0x1800344ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034504  movups  xmm0, xmmword ptr [rax]
0x180034507  mov     [rdi+7E0h], ebx
0x18003450d  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180034515  mov     edi, [r13+0]
0x180034519  lea     rcx, [rbp+47h+var_A0]; void *
0x18003451d  xorps   xmm0, xmm0
0x180034520  xor     eax, eax
0x180034522  xor     r13d, r13d
0x180034525  mov     qword ptr [rbp+47h+pvar+10h], rax
0x180034529  xor     ebx, ebx
0x18003452b  xor     edx, edx; Val
0x18003452d  mov     [rsp+110h+var_D0], rbx
0x180034532  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x180034536  lea     r8d, [r13+18h]; Size
0x18003453a  call    cs:__imp_memset
0x180034541  nop     dword ptr [rax+rax+00h]
0x180034546  mov     [rsp+110h+ppStore], r12
0x18003454b  test    r12, r12
0x18003454e  jz      short loc_18003456A
0x180034550  mov     rax, [r12]
0x180034554  mov     rcx, r12
0x180034557  mov     rax, [rax+8]
0x18003455b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034560  mov     rcx, [rsp+110h+ppStore]
0x180034565  test    rcx, rcx
0x180034568  jnz     short loc_180034589
0x18003456a  lea     rcx, [rsp+110h+ppStore]; ppStore
0x18003456f  call    cs:__imp_CreatePropertyStore
0x180034576  nop     dword ptr [rax+rax+00h]
0x18003457b  mov     rcx, [rsp+110h+ppStore]
0x180034580  test    rcx, rcx
0x180034583  jz      loc_18003463F
0x180034589  mov     rax, [rcx]
0x18003458c  lea     r8, [rbp+47h+var_A0]
0x180034590  lea     rdx, MFPKEY_TELEMETRY_SESSION
0x180034597  mov     rax, [rax+28h]
0x18003459b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800345a0  mov     eax, 0Dh
0x1800345a5  mov     r8, r14
0x1800345a8  cmp     ax, [rbp+47h+var_A0]
0x1800345ac  jnz     short loc_1800345C1
0x1800345ae  mov     rcx, [rbp+47h+var_98]
0x1800345b2  lea     rdx, _GUID_627d2ca6_e1cd_4898_999d_101308f1d431
0x1800345b9  mov     rax, [rcx]
0x1800345bc  mov     rax, [rax]
0x1800345bf  jmp     short loc_18003460D
0x1800345c1  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800345c8  lea     rdx, [rbp+47h+var_80]
0x1800345cc  lea     rcx, [rbp+47h+var_60]
0x1800345d0  movdqu  [rbp+47h+var_80], xmm0
0x1800345d5  movdqu  [rbp+47h+var_60], xmm0
0x1800345da  call    cs:__imp_MFCreateTelemetrySession
0x1800345e1  nop     dword ptr [rax+rax+00h]
0x1800345e6  test    eax, eax
0x1800345e8  js      short loc_180034612
0x1800345ea  mov     rdx, [r14]
0x1800345ed  lea     rcx, [rbp+47h+var_A0]
0x1800345f1  call    ??4CMFPropVariant@@QEAAAEAV0@PEAUIUnknown@@@Z; CMFPropVariant::operator=(IUnknown *)
0x1800345f6  mov     rcx, [rsp+110h+ppStore]
0x1800345fb  lea     r8, [rbp+47h+var_A0]
0x1800345ff  lea     rdx, MFPKEY_TELEMETRY_SESSION
0x180034606  mov     rax, [rcx]
0x180034609  mov     rax, [rax+30h]
0x18003460d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034612  cmp     [r14], rbx
0x180034615  jz      short loc_18003463F
0x180034617  mov     rdx, r14
0x18003461a  lea     rcx, [rsi+450h]
0x180034621  call    ??4?$ComSmartPtr@UIBaseFilter@@@@QEAAPEAUIBaseFilter@@AEBV0@@Z; ComSmartPtr<IBaseFilter>::operator=(ComSmartPtr<IBaseFilter> const &)
0x180034626  mov     rcx, [r14]
0x180034629  lea     rdx, GUID_MFDSTelemetrySessionOwnership
0x180034630  mov     rax, [rcx]
0x180034633  mov     rax, [rax+150h]
0x18003463a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003463f  xor     edx, edx; Val
0x180034641  lea     rcx, [rbp+47h+pvar]; void *
0x180034645  lea     r8d, [rdx+18h]; Size
0x180034649  call    cs:__imp_memset
0x180034650  nop     dword ptr [rax+rax+00h]
0x180034655  test    edi, edi
0x180034657  jns     short loc_1800346B6
0x180034659  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034660  test    rcx, rcx
0x180034663  jnz     short loc_180034671
0x180034665  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003466a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180034671  cmp     [rcx+8], bl
0x180034674  jz      short loc_18003469B
0x180034676  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003467b  cmp     [rax+7CCh], edi
0x180034681  jz      short loc_18003469B
0x180034683  mov     r9d, edi; int
0x180034686  lea     rdx, aCdshowsourceCd; "CDShowSource::CDShowSource"
0x18003468d  mov     r8d, 0AFh; int
0x180034693  mov     rcx, rax; this
0x180034696  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003469b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800346a2  jb      loc_180034AB8
0x1800346a8  mov     edx, 10h
0x1800346ad  mov     [rsp+110h+var_F0], edi
0x1800346b1  jmp     loc_180034817
0x1800346b6  cmp     [rsi+0D8h], ebx
0x1800346bc  jle     short loc_180034737
0x1800346be  mov     ecx, 300h; Size
0x1800346c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800346c8  mov     rcx, rax; this
0x1800346cb  test    rax, rax
0x1800346ce  jz      short loc_1800346F7
0x1800346d0  mov     eax, [rsi+0D8h]
0x1800346d6  mov     rdx, rsi; struct CDShowSource *
0x1800346d9  mov     r9, [rsp+110h+var_C8]; struct IMFByteStream *
0x1800346de  mov     r8, [rbp+47h+var_C0]; unsigned __int16 *
0x1800346e2  mov     [rsp+110h+var_E8], eax; int
0x1800346e6  mov     eax, [rbp+47h+arg_20]
0x1800346e9  mov     [rsp+110h+var_F0], eax; int
0x1800346ed  call    ??0CDShowSBEWrapper@@QEAA@PEAVCDShowSource@@PEBGPEAUIMFByteStream@@HH@Z; CDShowSBEWrapper::CDShowSBEWrapper(CDShowSource *,ushort const *,IMFByteStream *,int,int)
0x1800346f2  mov     r8, rax
0x1800346f5  jmp     short loc_1800346FA
0x1800346f7  xor     r8d, r8d
0x1800346fa  mov     rcx, [rsp+110h+ppStore]
0x1800346ff  mov     [rsi+2E0h], r8
0x180034706  test    rcx, rcx
0x180034709  jz      short loc_180034770
0x18003470b  mov     eax, 16h
0x180034710  mov     dword ptr [rbp+47h+pvar+8], ebx
0x180034713  mov     word ptr [rbp+47h+pvar], ax
0x180034717  lea     r8, [rbp+47h+pvar]
0x18003471b  mov     rax, [rcx]
0x18003471e  lea     rdx, MFPKEY_SBESourceMode
0x180034725  mov     rax, [rax+30h]
0x180034729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003472e  mov     r8, [rsi+2E0h]
0x180034735  jmp     short loc_180034770
0x180034737  mov     ecx, 1F0h; Size
0x18003473c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034741  mov     rcx, rax; this
0x180034744  test    rax, rax
0x180034747  jz      short loc_180034766
0x180034749  mov     eax, [rbp+47h+arg_20]
0x18003474c  mov     rdx, rsi; struct CDShowSource *
0x18003474f  mov     r9, [rsp+110h+var_C8]; struct IMFByteStream *
0x180034754  mov     r8, [rbp+47h+var_C0]; unsigned __int16 *
0x180034758  mov     [rsp+110h+var_F0], eax; int
0x18003475c  call    ??0CDShowWrapper@@QEAA@PEAVCDShowSource@@PEBGPEAUIMFByteStream@@H@Z; CDShowWrapper::CDShowWrapper(CDShowSource *,ushort const *,IMFByteStream *,int)
0x180034761  mov     r8, rax
0x180034764  jmp     short loc_180034769
0x180034766  xor     r8d, r8d
0x180034769  mov     [rsi+2E0h], r8
0x180034770  test    r8, r8
0x180034773  jnz     loc_180034836
0x180034779  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034780  mov     r14d, 8007000Eh
0x180034786  mov     edi, r14d
0x180034789  test    rcx, rcx
0x18003478c  jnz     short loc_1800347D5
0x18003478e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180034795  nop     dword ptr [rax+rax+00h]
0x18003479a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800347a1  mov     rcx, rax
0x1800347a4  test    rax, rax
0x1800347a7  jz      short loc_1800347C7
0x1800347a9  mov     rax, [rax]
0x1800347ac  mov     edx, 7F0h
0x1800347b1  mov     rax, [rax+8]
0x1800347b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800347ba  test    eax, eax
0x1800347bc  jz      short loc_1800347C7
0x1800347be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800347c5  jmp     short loc_1800347D5
  ... truncated ...
```
