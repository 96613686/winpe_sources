# CPipeManager::ProcessGfxSourceUpdates(void)

- ea: `0x1800594a4`
- end: `0x18005a557`
- name: `?ProcessGfxSourceUpdates@CPipeManager@@IEAAJXZ`
- size: `4275`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18005a85c`

## callees

- `0x180001308`
- `0x180001948`
- `0x180001ab0`
- `0x180001f84`
- `0x18000202c`
- `0x180002c94`
- `0x18000ce04`
- `0x18000ce34`
- `0x18001053c`
- `0x180010cd8`
- `0x180010d14`
- `0x18001218c`
- `0x180014b84`
- `0x180028a30`
- `0x18002aafc`
- `0x18003bf64`
- `0x18003fefc`
- `0x180043674`
- `0x18004447c`
- `0x180049c40`
- `0x18004f5bc`
- `0x1800583f8`
- `0x1800594a4`
- `0x180076090`
- `0x180077aa0`
- `0x180079770`
- `0x18007a664`
- `0x180158180`
- `0x18019c010`

## string_xrefs

- `0x180059b2a`: `PipeManagerError_ProcessGfxSrcUpdatesGetBAsFail`
- `0x18005a0e9`: `PipeManagerError_ProcessGfxSrcUpdatesGetBAsFail`
- `0x18005a14b`: `PipeManagerError_ProcessGfxSrcUpdatesGetBAsFail`
- `0x18005a1ad`: `PipeManagerError_ProcessGfxSrcUpdatesGetBAsFail`
- `0x18005a20f`: `PipeManagerError_ProcessGfxSrcUpdatesGetBAsFail`
- `0x18005a26e`: `PipeManagerError_ProcessGfxSrcUpdatesGetBAsFail`
- `0x18005a260`: `pUpdateBA`
- `0x180059676`: `Frame: Encode: Processing updates for surface.`
- `0x18005a03d`: `PipeManagerError_ProcessGfxSrcUpdatesUpdateFrameCtxFail`
- `0x18005a065`: `UpdateFrameContext failed`
- `0x180059c8e`: `ProcessGfxSourceUpdates`
- `0x180059d2b`: `ProcessGfxSourceUpdates`
- `0x180059dc8`: `ProcessGfxSourceUpdates`
- `0x180059e65`: `ProcessGfxSourceUpdates`
- `0x180059f02`: `ProcessGfxSourceUpdates`
- `0x180059f9f`: `ProcessGfxSourceUpdates`
- `0x18005a07e`: `ProcessGfxSourceUpdates`
- `0x180059778`: `Frame: Encode: Adding redraw rect to the spoiled and Update BA`
- `0x180059a9e`: `PipeManagerError_ProcessGfxSrcUpdatesRedrawRectFail`
- `0x180059ae3`: `PipeManagerError_ProcessGfxSrcUpdatesRedrawRectFail`
- `0x180059ac6`: `AddBA(spUpdateBA) from PrimarySurfaceRedrawPending failed`
- `0x180059c4d`: `PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail`
- `0x180059cea`: `PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail`
- `0x180059d87`: `PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail`
- `0x180059e24`: `PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail`
- `0x180059ec1`: `PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail`
- `0x180059f5e`: `PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail`
- `0x180059ffb`: `PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail`
- `0x180059e4c`: `pUpdateBA->GetPixelCount failed`
- `0x180059868`: `Frame: Encode: Primitive and update BAs are empty`
- `0x180059bc0`: `PipeManagerError_ProcessGfxSrcUpdatesOutOfSurfBounds`
- `0x180059c08`: `PipeManagerError_ProcessGfxSrcUpdatesOutOfSurfBounds`
- `0x180059beb`: `Update coordinates outside of the surface`

## pseudocode

```c
__int64 __fastcall CPipeManager::ProcessGfxSourceUpdates(CPipeManager *this)
{
  __int64 v2; // rbx
  unsigned int v3; // esi
  __int64 v4; // rcx
  __int64 v5; // rcx
  int Next; // eax
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rdi
  RdpSurface *v10; // r15
  int v11; // eax
  int v12; // ecx
  __int64 v13; // r13
  __int64 *v14; // r12
  signed int updated; // eax
  int v16; // r11d
  int v17; // r10d
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // r10d
  int v22; // r11d
  __int64 v23; // rsi
  int v24; // r10d
  int v25; // r11d
  signed int v26; // eax
  signed int v27; // eax
  signed int v28; // eax
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  signed int v32; // eax
  signed int v33; // eax
  signed int v34; // eax
  __int64 v35; // rdx
  signed int v36; // eax
  signed int v37; // eax
  int v38; // eax
  char v39; // si
  unsigned int v40; // eax
  __int64 v41; // rax
  signed int v42; // eax
  signed int v43; // eax
  __int64 v44; // rcx
  int v45; // ecx
  int v46; // r8d
  int v47; // r9d
  const char *v48; // rax
  __int16 *v49; // rdx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v51; // edx
  const char *v52; // rcx
  const char **v53; // rax
  int v54; // r15d
  int v55; // r12d
  __int64 v56; // rax
  int v57; // r8d
  int v58; // r9d
  unsigned __int64 v59; // r12
  __int64 v60; // rax
  int v61; // r8d
  int v62; // r9d
  char v63; // r15
  unsigned int v64; // eax
  int v65; // r8d
  int v66; // r9d
  unsigned int v67; // ebx
  int v69; // [rsp+20h] [rbp-B9h]
  int *v70; // [rsp+30h] [rbp-A9h]
  int *v71; // [rsp+40h] [rbp-99h]
  const char **v72; // [rsp+48h] [rbp-91h]
  _QWORD v73[2]; // [rsp+50h] [rbp-89h] BYREF
  int v74[4]; // [rsp+60h] [rbp-79h] BYREF
  const char *v75; // [rsp+70h] [rbp-69h] BYREF
  RdpSurface *v76; // [rsp+78h] [rbp-61h] BYREF
  int v77; // [rsp+80h] [rbp-59h] BYREF
  int v78; // [rsp+84h] [rbp-55h]
  int v79; // [rsp+88h] [rbp-51h]
  int v80; // [rsp+8Ch] [rbp-4Dh]
  __int64 v81; // [rsp+90h] [rbp-49h] BYREF
  __int64 v82; // [rsp+98h] [rbp-41h] BYREF
  int v83; // [rsp+A0h] [rbp-39h]
  int v84; // [rsp+A4h] [rbp-35h]
  int v85; // [rsp+A8h] [rbp-31h]
  int v86; // [rsp+ACh] [rbp-2Dh]
  int v87; // [rsp+B0h] [rbp-29h]
  int v88; // [rsp+B4h] [rbp-25h] BYREF
  int v89; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v90; // [rsp+C0h] [rbp-19h]
  __int64 v91; // [rsp+C8h] [rbp-11h] BYREF
  __int128 v92; // [rsp+D0h] [rbp-9h] BYREF
  _OWORD v93[5]; // [rsp+E0h] [rbp+7h] BYREF
  char *v94; // [rsp+140h] [rbp+67h] BYREF
  const char *v95; // [rsp+148h] [rbp+6Fh] BYREF
  const char *v96; // [rsp+150h] [rbp+77h] BYREF
  const char *v97; // [rsp+158h] [rbp+7Fh] BYREF

  v76 = 0;
  v2 = 0;
  v91 = 0;
  v82 = 0;
  v3 = 0;
  v94 = (char *)this + 48896;
  CTSCriticalSection::Lock((CPipeManager *)((char *)this + 48896));
  TCntPtr<IRdpPipeEvents>::operator=(&v91, (char *)this + 13040);
  if ( *((_QWORD *)this + 1625) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v82);
    v2 = *((_QWORD *)this + 1625);
    v82 = v2;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v82);
  }
  v83 = *((_DWORD *)this + 13260);
  v84 = *((_DWORD *)this + 13261);
  v85 = *((_DWORD *)this + 13262);
  v86 = *((_DWORD *)this + 13263);
  v87 = *((_DWORD *)this + 13264);
  *((_DWORD *)this + 13260) = 0;
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v94);
  PerfCounterSetRdpIntervalMarker(*((struct IRDPPerfCounterGeneric **)this + 6598), *((_DWORD *)this + 13250), 0);
  v81 = *((_QWORD *)this + 6237);
  while ( (unsigned int)CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::GetNext(v4, &v81, &v76) )
  {
    CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::AddTail((char *)this + 49024, v76);
    TCntPtr<RdpSurface>::operator=(&v76, 0);
  }
  v81 = *((_QWORD *)this + 6181);
  Next = CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::GetNext(v5, &v81, &v76);
  v9 = v91;
  while ( 1 )
  {
    if ( !Next )
    {
      if ( v2 )
      {
        v54 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 152LL))(v2);
        v55 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 176LL))(v2);
      }
      else
      {
        v54 = 0;
        v55 = 0;
      }
      *((_DWORD *)this + 13342) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1623) + 48LL))(*((_QWORD *)this + 1623));
      if ( *((_DWORD *)this + 13257)
        || *((_DWORD *)this + 13259)
        || (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1623) + 48LL))(*((_QWORD *)this + 1623))
        || v54
        || v55
        || (unsigned int)CPipeManager::IsDetectedVideoActive(this) )
      {
        *((_DWORD *)this + 13248) = 8;
        if ( v2 )
        {
          *((_DWORD *)this + 13249) = *((_DWORD *)this + 13249) % 0xFFFFFFFF + 1;
          v56 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 96LL))(v2);
          v59 = v56;
          if ( (unsigned int)CallbackContext > 5 )
          {
            v94 = (char *)v56;
            v95 = "Frame: pipeManager spUT->GetFrameTimeStamp()";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
              (_DWORD)CallbackContext,
              (unsigned int)qword_180278088,
              v57,
              v58,
              (__int64)&v95,
              (__int64)&v94);
          }
          v60 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 104LL))(v2);
          v63 = v60;
          if ( (unsigned int)CallbackContext > 5 )
          {
            v94 = (char *)v60;
            v95 = "Frame: pipeManager spUT->GetFrameLastTimeStamp()";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
              (_DWORD)CallbackContext,
              (unsigned int)&unk_180278050,
              v61,
              v62,
              (__int64)&v95,
              (__int64)&v94);
          }
          v64 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 112LL))(v2);
          v67 = v64;
          if ( (unsigned int)CallbackContext > 5 )
          {
            LODWORD(v94) = v64;
            v95 = "Frame: pipeManager spUT->GetNumberOfTimeStamps()";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (_DWORD)CallbackContext,
              (unsigned int)word_18027801A,
              v65,
              v66,
              (__int64)&v95,
              (__int64)&v94);
          }
          PerfCounterSetNewFrameDetails(
            *((struct IRDPPerfCounterGeneric **)this + 6619),
            *((_DWORD *)this + 13249),
            v67,
            v59,
            v63);
          PerfCounterSetRdpIntervalMarker(
            *((struct IRDPPerfCounterGeneric **)this + 6614),
            *((_DWORD *)this + 13250),
            *((_DWORD *)this + 13249));
          if ( v9 )
            (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v9 + 288LL))(
              v9,
              *((unsigned int *)this + 13249),
              *((_QWORD *)this + 6649) / 10000LL,
              *((unsigned int *)this + 13259));
        }
      }
      else
      {
        *((_DWORD *)this + 13248) = 16;
      }
      goto LABEL_123;
    }
    v10 = v76;
    *(_QWORD *)&v92 = 0;
    v93[0] = 0;
    v11 = *((_DWORD *)v76 + 18);
    HIDWORD(v92) = *((_DWORD *)v76 + 19);
    v12 = v11 * HIDWORD(v92);
    DWORD2(v92) = v11;
    *((_DWORD *)this + 13352) += v11 * HIDWORD(v92);
    v90 = *((_QWORD *)v10 + 19);
    if ( !v90 )
    {
      v3 = -2147467261;
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesGetBAsFail",
        (char *)0x160A,
        0x80004003,
        v69);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_123;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v51 = 130;
      v52 = "pEncodingBA";
      goto LABEL_103;
    }
    v13 = *((_QWORD *)v10 + 33);
    if ( !v13 )
    {
      v3 = -2147467261;
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesGetBAsFail",
        (char *)0x160E,
        0x80004003,
        v69);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_123;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v51 = 131;
      v52 = "pUpdateBA";
      goto LABEL_103;
    }
    v73[0] = *((_QWORD *)v10 + 34);
    if ( !v73[0] )
    {
      v3 = -2147467261;
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesGetBAsFail",
        (char *)0x1612,
        0x80004003,
        v69);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_123;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v51 = 132;
      v52 = "pPrimitiveBA";
      goto LABEL_103;
    }
    v14 = (__int64 *)*((_QWORD *)v10 + 35);
    if ( !v14 )
    {
      v3 = -2147467261;
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesGetBAsFail",
        (char *)0x1616,
        0x80004003,
        v69);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_123;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v51 = 133;
      v52 = "pFrameDirtyBA";
      goto LABEL_103;
    }
    v75 = (const char *)*((_QWORD *)v10 + 23);
    if ( !v75 )
    {
      v3 = -2147467261;
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesGetBAsFail",
        (char *)0x161A,
        0x80004003,
        v69);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_123;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v51 = 134;
      v52 = "pDeferredBA";
      goto LABEL_103;
    }
    if ( (unsigned int)CallbackContext > 5 )
    {
      LOWORD(v94) = *((_WORD *)v10 + 28);
      v96 = "Frame: Encode: Processing updates for surface.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>>(
        v12,
        (unsigned int)byte_1802784D9,
        v7,
        v8,
        (__int64)&v96,
        (__int64)&v94);
    }
    updated = RdpSurface::UpdateFrameContext(v10);
    v3 = updated;
    if ( updated < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesUpdateFrameCtxFail",
        (char *)0x1623,
        updated,
        v69);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_123;
      v48 = "UpdateFrameContext failed";
      LODWORD(v94) = 5668;
      v49 = (__int16 *)byte_18027848B;
      goto LABEL_81;
    }
    if ( v83 )
    {
      if ( !*((_QWORD *)v10 + 47) )
      {
        v77 = v84;
        v78 = v85;
        *(_OWORD *)v74 = v92;
        v79 = v86;
        v80 = v87;
        v16 = *((_DWORD *)v10 + 96);
        v17 = *((_DWORD *)v10 + 97);
        v74[2] = v16 + DWORD2(v92);
        v74[1] = v17 + DWORD1(v92);
        v74[3] = v17 + HIDWORD(v92);
        v74[0] = v16;
        RdpRect::Intersect((RdpRect *)&v77, (const struct RdpRect *)v74);
        if ( !RdpRect::IsEmpty((RdpRect *)&v77) )
        {
          v23 = *((_QWORD *)v10 + 20);
          if ( v23 )
          {
            v24 = -v21;
            v78 += v24;
            v25 = -v22;
            v77 += v25;
            v79 += v25;
            v80 += v24;
            if ( (unsigned int)CallbackContext > 5 )
            {
              LODWORD(v96) = v80;
              LODWORD(v97) = v79;
              v88 = v78;
              v89 = v77;
              LOWORD(v95) = *((_WORD *)v10 + 28);
              *(_QWORD *)v74 = "Frame: Encode: Adding redraw rect to the spoiled and Update BA";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v18,
                (unsigned int)qword_180278440,
                v19,
                v20,
                (__int64)v74,
                (__int64)&v95,
                (__int64)&v89,
                (__int64)&v88,
                (__int64)&v97,
                (__int64)&v96);
            }
            v26 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 40LL))(v23, &v77);
            v3 = v26;
            if ( v26 < 0 )
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
                "PipeManagerError_ProcessGfxSrcUpdatesRedrawRectFail",
                (char *)0x1655,
                v26,
                v69);
              if ( (unsigned int)CallbackContext <= 2 )
                goto LABEL_123;
              v48 = "AddBA(SpoiledBA) from PrimarySurfaceRedrawPending failed";
              LODWORD(v94) = 5718;
              v49 = word_1802783F2;
              goto LABEL_81;
            }
            v27 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 40LL))(v13, &v77);
            v3 = v27;
            if ( v27 < 0 )
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
                "PipeManagerError_ProcessGfxSrcUpdatesRedrawRectFail",
                (char *)0x1659,
                v27,
                v69);
              if ( (unsigned int)CallbackContext <= 2 )
                goto LABEL_123;
              v48 = "AddBA(spUpdateBA) from PrimarySurfaceRedrawPending failed";
              LODWORD(v94) = 5722;
              v49 = (__int16 *)&dword_1802783A4;
              goto LABEL_81;
            }
            goto LABEL_24;
          }
          v3 = -2147467261;
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
            "PipeManagerError_ProcessGfxSrcUpdatesGetBAsFail",
            (char *)0x1644,
            0x80004003,
            v69);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_123;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v51 = 136;
          v52 = "pSpoiledBA";
LABEL_103:
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v51,
            (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)v52);
          goto LABEL_123;
        }
      }
    }
LABEL_24:
    v28 = (*(__int64 (__fastcall **)(__int64 *))(*v14 + 24))(v14);
    v3 = v28;
    if ( v28 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail",
        (char *)0x1662,
        v28,
        v69);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_123;
      v48 = "pFrameDirtyBA->Clear failed";
      LODWORD(v94) = 5731;
      v49 = &word_180278356;
LABEL_81:
      v96 = v48;
      v97 = "ProcessGfxSourceUpdates";
      *(_QWORD *)v74 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v73[0] = "Error HResult failed";
      v72 = &v96;
      v71 = (int *)&v97;
      v70 = v74;
      v53 = (const char **)v73;
LABEL_82:
      LODWORD(v95) = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v45,
        (_DWORD)v49,
        v46,
        v47,
        (__int64)v53,
        (__int64)&v95,
        (__int64)v70,
        (__int64)&v94,
        (__int64)v71,
        (__int64)v72);
      goto LABEL_123;
    }
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v13 + 136LL))(v13)
      && (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v73[0] + 136LL))(v73[0])
      && (*(unsigned int (__fastcall **)(const char *))(*(_QWORD *)v75 + 136LL))(v75) )
    {
      if ( (unsigned int)CallbackContext > 5 )
      {
        v96 = "Frame: Encode: Primitive and update BAs are empty";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v29,
          (unsigned int)qword_180278160,
          v30,
          v31,
          (__int64)&v96);
      }
      goto LABEL_46;
    }
    LODWORD(v96) = 0;
    *((_DWORD *)this + 13259) = 1;
    if ( v9 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 32LL))(v9, v13);
    v32 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v90 + 48LL))(v90, v13);
    v3 = v32;
    if ( v32 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail",
        (char *)0x1670,
        v32,
        v69);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_123;
      LODWORD(v94) = 5745;
      v97 = "spEncodingBA->AddBA failed";
      v49 = (__int16 *)qword_180278308;
      *(_QWORD *)v74 = "ProcessGfxSourceUpdates";
      v73[0] = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v75 = "Error HResult failed";
      v72 = &v97;
      v71 = v74;
      v70 = (int *)v73;
      v53 = &v75;
      goto LABEL_82;
    }
    v33 = (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)v90 + 48LL))(v90, v75);
    v3 = v33;
    if ( v33 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail",
        (char *)0x1674,
        v33,
        v69);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_123;
      LODWORD(v94) = 5749;
      v97 = "spEncodingBA->AddBA failed";
      v49 = word_1802782BA;
      *(_QWORD *)v74 = "ProcessGfxSourceUpdates";
      v73[0] = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v75 = "Error HResult failed";
      v72 = &v97;
      v71 = v74;
      v70 = (int *)v73;
      v53 = &v75;
      goto LABEL_82;
    }
    v34 = (*(__int64 (__fastcall **)(__int64, const char **))(*(_QWORD *)v13 + 144LL))(v13, &v96);
    v3 = v34;
    if ( v34 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail",
        (char *)0x1678,
        v34,
        v69);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_123;
      LODWORD(v94) = 5753;
      v97 = "pUpdateBA->GetPixelCount failed";
      v49 = (__int16 *)&dword_18027826C;
      *(_QWORD *)v74 = "ProcessGfxSourceUpdates";
      v73[0] = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v75 = "Error HResult failed";
      v72 = &v97;
      v71 = v74;
      v70 = (int *)v73;
      v53 = &v75;
      goto LABEL_82;
    }
    v35 = v90;
    *((_DWORD *)this + 13348) += (4 * (_DWORD)v96) & 0x1FFFFFFF;
    v36 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v14 + 48))(v14, v35);
    v3 = v36;
    if ( v36 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail",
        (char *)0x1683,
        v36,
        v69);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_123;
      LODWORD(v94) = 5764;
      v97 = "pFrameDirtyBA->AddBA failed";
      v49 = &word_18027821E;
      *(_QWORD *)v74 = "ProcessGfxSourceUpdates";
      v73[0] = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v75 = "Error HResult failed";
      v72 = &v97;
      v71 = v74;
      v70 = (int *)v73;
      v53 = &v75;
      goto LABEL_82;
    }
    v37 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v14 + 48))(v14, v73[0]);
    v3 = v37;
    if ( v37 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail",
        (char *)0x1687,
        v37,
        v69);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_123;
      LODWORD(v94) = 5768;
      v97 = "pFrameDirtyBA->AddBA failed";
      v49 = (__int16 *)qword_1802781D0;
      *(_QWORD *)v74 = "ProcessGfxSourceUpdates";
      v73[0] = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v75 = "Error HResult failed";
      v72 = &v97;
      v71 = v74;
      v70 = (int *)v73;
      v53 = &v75;
      goto LABEL_82;
    }
    if ( v9 )
    {
      v38 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v9 + 272LL))(
              v9,
              *((unsigned __int16 *)v10 + 28),
              *((unsigned int *)this + 13249),
              v14);
      v39 = v38;
      if ( v38 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v40 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          145,
          (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
          v40,
          (__int64)"spPipeEvents->OnGfxSourceDirtyRectsAdded failed.",
          v39);
      }
    }
    *((_DWORD *)v10 + 60) = 0;
    v41 = *v14;
    LODWORD(v97) = 0;
    if ( (*(int (__fastcall **)(__int64 *, const char **))(v41 + 144))(v14, &v97) >= 0 )
      *((_DWORD *)v10 + 80) += (_DWORD)v97;
    v42 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v10 + 39) + 48LL))(*((_QWORD *)v10 + 39), v14);
    v3 = v42;
    if ( v42 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesAddUpdateAndPrimitivesBAFail",
        (char *)0x1693,
        v42,
        v69);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_123;
      LODWORD(v94) = 5780;
      v97 = "InvalidateAdaptiveGrid failed";
      v49 = word_180278182;
      *(_QWORD *)v74 = "ProcessGfxSourceUpdates";
      v73[0] = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v75 = "Error HResult failed";
      v72 = &v97;
      v71 = v74;
      v70 = (int *)v73;
      v53 = &v75;
      goto LABEL_82;
    }
LABEL_46:
    v43 = (*(__int64 (__fastcall **)(__int64 *, _OWORD *))(*v14 + 152))(v14, v93);
    v3 = v43;
    if ( v43 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ProcessGfxSrcUpdatesOutOfSurfBounds",
        (char *)0x169E,
        v43,
        v69);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_123;
      v48 = "GetBoundingBox failed";
      LODWORD(v94) = 5791;
      v49 = word_180278112;
      goto LABEL_81;
    }
    if ( !RdpRect::Contains((RdpRect *)&v92, (const struct RdpRect *)v93) )
      break;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
    TCntPtr<RdpSurface>::operator=(&v76, 0);
    Next = CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::GetNext(v44, &v81, &v76);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids);
  }
  v3 = -2147024809;
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
    "PipeManagerError_ProcessGfxSrcUpdatesOutOfSurfBounds",
    (char *)0x16A5,
    0x80070057,
    v69);
  if ( (unsigned int)CallbackContext > 2 )
  {
    v48 = "Update coordinates outside of the surface";
    LODWORD(v94) = 5798;
    v49 = (__int16 *)&dword_1802780C4;
    goto LABEL_81;
  }
LABEL_123:
  PerfCounterSetRdpIntervalMarker(*((struct IRDPPerfCounterGeneric **)this + 6599), *((_DWORD *)this + 13250), 1u);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v82);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v91);
  TCntPtr<ClearCompressor>::SafeRelease(&v76);
  return v3;
}

```

## disassembly

```asm
0x1800594a4  push    rbp
0x1800594a6  push    rbx
0x1800594a7  push    rsi
0x1800594a8  push    rdi
0x1800594a9  push    r12
0x1800594ab  push    r13
0x1800594ad  push    r14
0x1800594af  push    r15
0x1800594b1  lea     rbp, [rsp-1Fh]
0x1800594b6  sub     rsp, 0F8h
0x1800594bd  xor     r13d, r13d
0x1800594c0  mov     r14, rcx
0x1800594c3  add     rcx, 0BF00h; this
0x1800594ca  mov     [rbp+57h+var_B8], r13
0x1800594ce  mov     ebx, r13d
0x1800594d1  mov     [rbp+57h+var_68], r13
0x1800594d5  mov     [rbp+57h+var_98], rbx
0x1800594d9  mov     esi, r13d
0x1800594dc  mov     [rbp+57h+arg_0], rcx
0x1800594e0  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800594e5  lea     rdx, [r14+32F0h]
0x1800594ec  lea     rcx, [rbp+57h+var_68]
0x1800594f0  call    ??4?$TCntPtr@VIRdpPipeEvents@@@@QEAAPEAVIRdpPipeEvents@@AEBV0@@Z; TCntPtr<IRdpPipeEvents>::operator=(TCntPtr<IRdpPipeEvents> const &)
0x1800594f5  cmp     [r14+32C8h], r13
0x1800594fc  jz      short loc_18005951B
0x1800594fe  lea     rcx, [rbp+57h+var_98]
0x180059502  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x180059507  mov     rbx, [r14+32C8h]
0x18005950e  lea     rcx, [rbp+57h+var_98]
0x180059512  mov     [rbp+57h+var_98], rbx
0x180059516  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18005951b  mov     eax, [r14+0CF30h]
0x180059522  lea     rcx, [rbp+57h+arg_0]; this
0x180059526  mov     [rbp+57h+var_90], eax
0x180059529  mov     eax, [r14+0CF34h]
0x180059530  mov     [rbp+57h+var_8C], eax
0x180059533  mov     eax, [r14+0CF38h]
0x18005953a  mov     [rbp+57h+var_88], eax
0x18005953d  mov     eax, [r14+0CF3Ch]
0x180059544  mov     [rbp+57h+var_84], eax
0x180059547  mov     eax, [r14+0CF40h]
0x18005954e  mov     [rbp+57h+var_80], eax
0x180059551  mov     [r14+0CF30h], r13d
0x180059558  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18005955d  mov     edx, [r14+0CF08h]; unsigned int
0x180059564  xor     r8d, r8d; unsigned int
0x180059567  mov     rcx, [r14+0CE30h]; struct IRDPPerfCounterGeneric *
0x18005956e  call    ?PerfCounterSetRdpIntervalMarker@@YAJPEAUIRDPPerfCounterGeneric@@II@Z; PerfCounterSetRdpIntervalMarker(IRDPPerfCounterGeneric *,uint,uint)
0x180059573  mov     rax, [r14+0C2E8h]
0x18005957a  mov     [rbp+57h+var_A0], rax
0x18005957e  jmp     short loc_18005959B
0x180059580  mov     rdx, [rbp+57h+var_B8]
0x180059584  lea     rcx, [r14+0BF80h]
0x18005958b  call    ?AddTail@?$CComPtrList@VRdpSurface@@V?$ComPlainSmartPtr@VRdpSurface@@@@@@QEAAPEAXPEAVRdpSurface@@@Z; CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::AddTail(RdpSurface *)
0x180059590  xor     edx, edx
0x180059592  lea     rcx, [rbp+57h+var_B8]
0x180059596  call    ??4?$TCntPtr@VRdpSurface@@@@QEAAPEAVRdpSurface@@PEAV1@@Z; TCntPtr<RdpSurface>::operator=(RdpSurface *)
0x18005959b  lea     r8, [rbp+57h+var_B8]
0x18005959f  lea     rdx, [rbp+57h+var_A0]
0x1800595a3  call    ?GetNext@?$CComPtrList@VRdpSurface@@V?$ComPlainSmartPtr@VRdpSurface@@@@@@QEBAHAEAPEAXPEAPEAVRdpSurface@@@Z; CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::GetNext(void * &,RdpSurface * *)
0x1800595a8  test    eax, eax
0x1800595aa  jnz     short loc_180059580
0x1800595ac  mov     rax, [r14+0C128h]
0x1800595b3  lea     r8, [rbp+57h+var_B8]
0x1800595b7  lea     rdx, [rbp+57h+var_A0]
0x1800595bb  mov     [rbp+57h+var_A0], rax
0x1800595bf  call    ?GetNext@?$CComPtrList@VRdpSurface@@V?$ComPlainSmartPtr@VRdpSurface@@@@@@QEBAHAEAPEAXPEAPEAVRdpSurface@@@Z; CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::GetNext(void * &,RdpSurface * *)
0x1800595c4  mov     rdi, [rbp+57h+var_68]
0x1800595c8  test    eax, eax
0x1800595ca  jz      loc_18005A2EA
0x1800595d0  mov     r15, [rbp+57h+var_B8]
0x1800595d4  lea     rax, [rbp+57h+var_50]
0x1800595d8  xorps   xmm0, xmm0
0x1800595db  mov     qword ptr [rbp+57h+var_60], 0
0x1800595e3  movups  xmmword ptr [rax], xmm0
0x1800595e6  mov     eax, [r15+48h]
0x1800595ea  mov     ecx, [r15+4Ch]
0x1800595ee  mov     dword ptr [rbp+57h+var_60+0Ch], ecx
0x1800595f1  imul    ecx, eax
0x1800595f4  mov     dword ptr [rbp+57h+var_60+8], eax
0x1800595f7  add     [r14+0D0A0h], ecx
0x1800595fe  mov     rax, [r15+98h]
0x180059605  mov     [rbp+57h+var_70], rax
0x180059609  test    rax, rax
0x18005960c  jz      loc_18005A269
0x180059612  mov     r13, [r15+108h]
0x180059619  test    r13, r13
0x18005961c  jz      loc_18005A20A
0x180059622  mov     rax, [r15+110h]
0x180059629  mov     [rsp+130h+var_E0], rax
0x18005962e  test    rax, rax
0x180059631  jz      loc_18005A1A8
0x180059637  mov     r12, [r15+118h]
0x18005963e  test    r12, r12
0x180059641  jz      loc_18005A146
0x180059647  mov     rax, [r15+0B8h]
0x18005964e  mov     [rbp+57h+var_C0], rax
0x180059652  test    rax, rax
0x180059655  jz      loc_18005A0E4
0x18005965b  mov     eax, cs:CallbackContext
0x180059661  cmp     eax, 5
0x180059664  jbe     short loc_180059698
0x180059666  movzx   eax, word ptr [r15+38h]
0x18005966b  lea     rdx, byte_1802784D9
0x180059672  mov     word ptr [rbp+57h+arg_0], ax
0x180059676  lea     rax, aFrameEncodePro; "Frame: Encode: Processing updates for s"...
0x18005967d  mov     [rbp+57h+arg_10], rax
0x180059681  lea     rax, [rbp+57h+arg_0]
0x180059685  mov     [rsp+130h+var_108], rax
0x18005968a  lea     rax, [rbp+57h+arg_10]
0x18005968e  mov     qword ptr [rsp+130h+var_110], rax; int
0x180059693  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &)
0x180059698  mov     rcx, r15; this
0x18005969b  call    ?UpdateFrameContext@RdpSurface@@QEAAJXZ; RdpSurface::UpdateFrameContext(void)
0x1800596a0  mov     esi, eax
0x1800596a2  test    eax, eax
0x1800596a4  js      loc_18005A03A
0x1800596aa  cmp     [rbp+57h+var_90], 0
0x1800596ae  jz      loc_1800597F9
0x1800596b4  cmp     qword ptr [r15+178h], 0
0x1800596bc  jnz     loc_1800597F9
0x1800596c2  mov     eax, [rbp+57h+var_8C]
0x1800596c5  lea     rdx, [rbp+57h+var_D0]; struct RdpRect *
0x1800596c9  movaps  xmm0, [rbp+57h+var_60]
0x1800596cd  lea     rcx, [rbp+57h+var_B0]; this
0x1800596d1  mov     [rbp+57h+var_B0], eax
0x1800596d4  mov     eax, [rbp+57h+var_88]
0x1800596d7  mov     [rbp+57h+var_AC], eax
0x1800596da  mov     eax, [rbp+57h+var_84]
0x1800596dd  movdqa  xmmword ptr [rbp+57h+var_D0], xmm0
0x1800596e2  mov     [rbp+57h+var_A8], eax
0x1800596e5  mov     eax, [rbp+57h+var_80]
0x1800596e8  mov     [rbp+57h+var_A4], eax
0x1800596eb  mov     r11d, [r15+180h]
0x1800596f2  mov     r10d, [r15+184h]
0x1800596f9  add     [rbp+57h+var_D0+8], r11d
0x1800596fd  add     [rbp+57h+var_D0+4], r10d
0x180059701  add     [rbp+57h+var_D0+0Ch], r10d
0x180059705  mov     [rbp+57h+var_D0], r11d
0x180059709  call    ?Intersect@RdpRect@@QEAA_NAEBU1@@Z; RdpRect::Intersect(RdpRect const &)
0x18005970e  lea     rcx, [rbp+57h+var_B0]; this
0x180059712  call    ?IsEmpty@RdpRect@@QEBA_NXZ; RdpRect::IsEmpty(void)
0x180059717  test    al, al
0x180059719  jnz     loc_1800597F9
0x18005971f  mov     rsi, [r15+0A0h]
0x180059726  test    rsi, rsi
0x180059729  jz      loc_180059B25
0x18005972f  mov     eax, cs:CallbackContext
0x180059735  neg     r10d
0x180059738  add     [rbp+57h+var_AC], r10d
0x18005973c  neg     r11d
0x18005973f  add     [rbp+57h+var_B0], r11d
0x180059743  add     [rbp+57h+var_A8], r11d
0x180059747  add     [rbp+57h+var_A4], r10d
0x18005974b  cmp     eax, 5
0x18005974e  jbe     short loc_1800597BE
0x180059750  mov     eax, [rbp+57h+var_A4]
0x180059753  lea     rdx, qword_180278440
0x18005975a  mov     dword ptr [rbp+57h+arg_10], eax
0x18005975d  mov     eax, [rbp+57h+var_A8]
0x180059760  mov     dword ptr [rbp+57h+arg_18], eax
0x180059763  mov     eax, [rbp+57h+var_AC]
0x180059766  mov     [rbp+57h+var_7C], eax
0x180059769  mov     eax, [rbp+57h+var_B0]
0x18005976c  mov     [rbp+57h+var_78], eax
0x18005976f  movzx   eax, word ptr [r15+38h]
0x180059774  mov     word ptr [rbp+57h+arg_8], ax
0x180059778  lea     rax, aFrameEncodeAdd; "Frame: Encode: Adding redraw rect to th"...
0x18005977f  mov     qword ptr [rbp+57h+var_D0], rax
0x180059783  lea     rax, [rbp+57h+arg_10]
0x180059787  mov     [rsp+130h+var_E8], rax
0x18005978c  lea     rax, [rbp+57h+arg_18]
0x180059790  mov     [rsp+130h+var_F0], rax
0x180059795  lea     rax, [rbp+57h+var_7C]
0x180059799  mov     [rsp+130h+var_F8], rax
0x18005979e  lea     rax, [rbp+57h+var_78]
0x1800597a2  mov     [rsp+130h+var_100], rax
0x1800597a7  lea     rax, [rbp+57h+arg_8]
0x1800597ab  mov     [rsp+130h+var_108], rax
0x1800597b0  lea     rax, [rbp+57h+var_D0]
0x1800597b4  mov     qword ptr [rsp+130h+var_110], rax; int
0x1800597b9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800597be  mov     rax, [rsi]
0x1800597c1  lea     rdx, [rbp+57h+var_B0]
0x1800597c5  mov     rcx, rsi
0x1800597c8  mov     rax, [rax+28h]
0x1800597cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597d1  mov     esi, eax
0x1800597d3  test    eax, eax
0x1800597d5  js      loc_180059AE0
0x1800597db  mov     rax, [r13+0]
0x1800597df  lea     rdx, [rbp+57h+var_B0]
0x1800597e3  mov     rcx, r13
0x1800597e6  mov     rax, [rax+28h]
0x1800597ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597ef  mov     esi, eax
0x1800597f1  test    eax, eax
0x1800597f3  js      loc_180059A9B
0x1800597f9  mov     rax, [r12]
0x1800597fd  mov     rcx, r12
0x180059800  mov     rax, [rax+18h]
0x180059804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059809  mov     esi, eax
0x18005980b  test    eax, eax
0x18005980d  js      loc_180059FF8
0x180059813  mov     rax, [r13+0]
0x180059817  mov     rcx, r13
0x18005981a  mov     rax, [rax+88h]
0x180059821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059826  test    eax, eax
0x180059828  jz      short loc_18005988D
0x18005982a  mov     rcx, [rsp+130h+var_E0]
0x18005982f  mov     rax, [rcx]
0x180059832  mov     rax, [rax+88h]
0x180059839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005983e  test    eax, eax
0x180059840  jz      short loc_18005988D
0x180059842  mov     rcx, [rbp+57h+var_C0]
0x180059846  mov     rax, [rcx]
0x180059849  mov     rax, [rax+88h]
0x180059850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059855  test    eax, eax
0x180059857  jz      short loc_18005988D
0x180059859  mov     eax, cs:CallbackContext
0x18005985f  cmp     eax, 5
0x180059862  jbe     loc_180059A35
0x180059868  lea     rax, aFrameEncodePri; "Frame: Encode: Primitive and update BAs"...
0x18005986f  mov     [rbp+57h+arg_10], rax
0x180059873  lea     rdx, qword_180278160
0x18005987a  lea     rax, [rbp+57h+arg_10]
0x18005987e  mov     qword ptr [rsp+130h+var_110], rax
0x180059883  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180059888  jmp     loc_180059A35
0x18005988d  mov     dword ptr [rbp+57h+arg_10], 0
0x180059894  mov     dword ptr [r14+0CF2Ch], 1
0x18005989f  test    rdi, rdi
0x1800598a2  jz      short loc_1800598B6
0x1800598a4  mov     rax, [rdi]
0x1800598a7  mov     rdx, r13
0x1800598aa  mov     rcx, rdi
0x1800598ad  mov     rax, [rax+20h]
0x1800598b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800598b6  mov     rcx, [rbp+57h+var_70]
0x1800598ba  mov     rdx, r13
0x1800598bd  mov     rax, [rcx]
0x1800598c0  mov     rax, [rax+30h]
0x1800598c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800598c9  mov     esi, eax
0x1800598cb  test    eax, eax
0x1800598cd  js      loc_180059F5B
0x1800598d3  mov     rcx, [rbp+57h+var_70]
0x1800598d7  mov     rdx, [rbp+57h+var_C0]
0x1800598db  mov     rax, [rcx]
0x1800598de  mov     rax, [rax+30h]
0x1800598e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800598e7  mov     esi, eax
0x1800598e9  test    eax, eax
0x1800598eb  js      loc_180059EBE
0x1800598f1  mov     rax, [r13+0]
0x1800598f5  lea     rdx, [rbp+57h+arg_10]
0x1800598f9  mov     rcx, r13
0x1800598fc  mov     rax, [rax+90h]
0x180059903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059908  mov     esi, eax
0x18005990a  test    eax, eax
0x18005990c  js      loc_180059E21
0x180059912  mov     eax, dword ptr [rbp+57h+arg_10]
0x180059915  mov     rcx, r12
0x180059918  mov     rdx, [rbp+57h+var_70]
0x18005991c  shl     eax, 5
0x18005991f  shr     eax, 3
0x180059922  add     [r14+0D090h], eax
0x180059929  mov     rax, [r12]
0x18005992d  mov     rax, [rax+30h]
0x180059931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059936  mov     esi, eax
0x180059938  test    eax, eax
0x18005993a  js      loc_180059D84
0x180059940  mov     rax, [r12]
0x180059944  mov     rcx, r12
0x180059947  mov     rdx, [rsp+130h+var_E0]
0x18005994c  mov     rax, [rax+30h]
0x180059950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059955  mov     esi, eax
0x180059957  test    eax, eax
0x180059959  js      loc_180059CE7
0x18005995f  test    rdi, rdi
0x180059962  jz      short loc_1800599DE
0x180059964  mov     rax, [rdi]
0x180059967  mov     r9, r12
0x18005996a  movzx   edx, word ptr [r15+38h]
0x18005996f  mov     rcx, rdi
0x180059972  mov     r8d, [r14+0CF04h]
0x180059979  mov     rax, [rax+110h]
0x180059980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059985  mov     esi, eax
0x180059987  test    eax, eax
0x180059989  jns     short loc_1800599DE
0x18005998b  mov     rcx, cs:WPP_GLOBAL_Control
0x180059992  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
