# CPipeManager::FlushSurfaceCommands(void)

- ea: `0x180056be0`
- end: `0x1800581c1`
- name: `?FlushSurfaceCommands@CPipeManager@@IEAAJXZ`
- size: `5601`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18005a85c`

## callees

- `0x1800019f0`
- `0x180001ab0`
- `0x180001b90`
- `0x180001c70`
- `0x180001eb4`
- `0x18000202c`
- `0x1800023e4`
- `0x180002568`
- `0x18000ce04`
- `0x18000ce34`
- `0x18001053c`
- `0x180010cd8`
- `0x180010d14`
- `0x180028a30`
- `0x18002aafc`
- `0x180039b28`
- `0x18003bf64`
- `0x18004f5bc`
- `0x180056be0`
- `0x18007e9e0`
- `0x18007f42c`
- `0x180098190`
- `0x180158180`
- `0x18019c010`

## string_xrefs

- `0x180056d06`: `PipeManagerError_FlushSrfCmdsNullProtocol`
- `0x180056d31`: `Protocol is null, can't flush surface commands`
- `0x180056d4b`: `FlushSurfaceCommands`
- `0x180056e08`: `FlushSurfaceCommands`
- `0x180056ec9`: `FlushSurfaceCommands`
- `0x180057143`: `FlushSurfaceCommands`
- `0x1800571cf`: `FlushSurfaceCommands`
- `0x1800572c0`: `FlushSurfaceCommands`
- `0x180057458`: `FlushSurfaceCommands`
- `0x18005781e`: `FlushSurfaceCommands`
- `0x1800578bf`: `FlushSurfaceCommands`
- `0x180057960`: `FlushSurfaceCommands`
- `0x180057a01`: `FlushSurfaceCommands`
- `0x180057b6d`: `FlushSurfaceCommands`
- `0x180057cdc`: `FlushSurfaceCommands`
- `0x180057f7f`: `FlushSurfaceCommands`
- `0x18005801c`: `FlushSurfaceCommands`
- `0x180058164`: `FlushSurfaceCommands`
- `0x180056dee`: `Failed to get Protocol Encoder`
- `0x18005727e`: `PipeManagerError_FlushSrfCmdsUTResetProtocolFail`
- `0x1800572a6`: `Failed to reset protocol`
- `0x180057416`: `PipeManagerError_FlushSrfCmdsCreateSrfEncoderFail`
- `0x18005743e`: `Failed to send create surface`
- `0x180057382`: `Surface: Sent create surface command`
- `0x180057549`: `Surface: Sent associate to scaled output window command.`
- `0x1800575c4`: `Surface: Sent associate to output window command. surf.`
- `0x180057703`: `Surface: Sent associate to output surface2 command. surf.`
- `0x1800577a0`: `Surface: Sent associate to output surface command.`
- `0x180057b2c`: `PipeManagerError_FlushSrfCmdsDeleteSurfaceFail`
- `0x180057b54`: `Failed to send delete surface`
- `0x180057ab7`: `Surface: Sent delete surface command.`
- `0x180057c9b`: `PipeManagerError_FlushSrfCmdsUpdateSurfaceProtectionFail`
- `0x180057c22`: `Surface: Sent protect surface command.`
- `0x180058123`: `PipeManagerError_FlushSrfCmdsUpdateSurfaceStartWatermarkingFail`
- `0x180057f66`: `qrEncoder->Copy failed!`
- `0x180057fdf`: `PipeManagerError_FlushSrfCmdsUpdateSurfaceCommitWatermarkingFail`
- `0x180057ec8`: `Surface: Sent watermark surface command.`

## pseudocode

```c
__int64 __fastcall CPipeManager::FlushSurfaceCommands(CPipeManager *this)
{
  unsigned int v1; // edx
  CPipeManager *v2; // r15
  __int64 v3; // rdi
  struct IRDPPerfCounterGeneric *v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // r12
  __int64 v8; // rcx
  int v9; // r14d
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  const char *v13; // rax
  char *v14; // rdx
  const char *v15; // rax
  signed int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int64 *v20; // rbx
  int v21; // r8d
  int v22; // r9d
  unsigned int v23; // r12d
  unsigned int v24; // r14d
  __int64 v25; // rbx
  __int64 v26; // rdx
  signed int v27; // eax
  signed int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // edx
  const char *v31; // r12
  signed int v32; // eax
  __int64 v33; // rbx
  int v34; // edi
  signed int v35; // eax
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  __int64 v39; // rcx
  __int64 v40; // rbx
  const char *v41; // rdi
  int v42; // r9d
  int v43; // r8d
  int v44; // r12d
  int v45; // r13d
  int v46; // eax
  __int64 v47; // r9
  bool v48; // zf
  __int64 v49; // rax
  __int64 v50; // r8
  signed int v51; // eax
  int v52; // ecx
  int v53; // r8d
  int v54; // r9d
  signed int v55; // eax
  int v56; // r12d
  __int64 v57; // rcx
  const char *v58; // rdi
  signed int v59; // eax
  int v60; // ecx
  int v61; // r8d
  int v62; // r9d
  signed int v63; // eax
  int v64; // ecx
  int v65; // r8d
  int v66; // r9d
  int v67; // ecx
  int v68; // r8d
  int v69; // r9d
  int v70; // ecx
  int v71; // r8d
  int v72; // r9d
  int v73; // ecx
  int v74; // r8d
  int v75; // r9d
  int v76; // ecx
  int v77; // r8d
  int v78; // r9d
  __int64 v79; // rbx
  signed int v80; // eax
  int v81; // ecx
  int v82; // r8d
  int v83; // r9d
  __int64 v84; // rcx
  const char *v85; // rdi
  int v86; // ecx
  int v87; // r8d
  int v88; // r9d
  __int64 v89; // rbx
  signed int v90; // eax
  int v91; // ecx
  int v92; // r8d
  int v93; // r9d
  __int64 v94; // rcx
  const char *v95; // rbx
  int v96; // ecx
  int v97; // r8d
  int v98; // r9d
  __int64 v99; // rbx
  __int64 v100; // r12
  __int64 (__fastcall *v101)(__int64); // rdi
  int v102; // esi
  int v103; // eax
  __int64 v104; // rdx
  unsigned int v105; // esi
  __int64 (__fastcall *v106)(__int64 *, __int64, _QWORD, int *); // rax
  signed int v107; // eax
  int v108; // ecx
  int v109; // r8d
  int v110; // r9d
  unsigned __int16 v111; // r14
  unsigned int v112; // eax
  signed int v113; // eax
  int v114; // ecx
  int v115; // r8d
  int v116; // r9d
  int v117; // ecx
  int v118; // r8d
  int v119; // r9d
  __int64 *v120; // rcx
  int v122; // ecx
  int v123; // r8d
  int v124; // r9d
  int v125; // [rsp+20h] [rbp-E0h]
  int v126; // [rsp+70h] [rbp-90h] BYREF
  int v127; // [rsp+74h] [rbp-8Ch] BYREF
  const char *v128; // [rsp+78h] [rbp-88h] BYREF
  int v129[2]; // [rsp+80h] [rbp-80h] BYREF
  const char *v130; // [rsp+88h] [rbp-78h] BYREF
  const char *v131; // [rsp+90h] [rbp-70h] BYREF
  int v132[2]; // [rsp+98h] [rbp-68h] BYREF
  const char *v133; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v134; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v135; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v136; // [rsp+B8h] [rbp-48h] BYREF
  const char *v137; // [rsp+C0h] [rbp-40h] BYREF
  const char *v138; // [rsp+C8h] [rbp-38h] BYREF
  __int64 (__fastcall *v139)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+D0h] [rbp-30h] BYREF
  const char *v140; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v141; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v142; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v143; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v144; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v145[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v146[1072]; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v147; // [rsp+540h] [rbp+440h]
  int v148; // [rsp+544h] [rbp+444h]
  int v149; // [rsp+548h] [rbp+448h]
  int v150[129]; // [rsp+54Ch] [rbp+44Ch]
  int v151; // [rsp+750h] [rbp+650h] BYREF
  _DWORD v152[79]; // [rsp+754h] [rbp+654h] BYREF

  v1 = *((_DWORD *)this + 13249);
  v2 = this;
  v131 = (const char *)this;
  v3 = 0;
  v4 = (struct IRDPPerfCounterGeneric *)*((_QWORD *)this + 6600);
  v5 = 0;
  v6 = 0;
  v143 = 0;
  v136 = 0;
  v142 = 0;
  v145[0] = 0;
  v144 = 0;
  v134 = 0;
  PerfCounterSetRdpIntervalMarker(v4, v1, 0);
  *(_QWORD *)v129 = (char *)v2 + 48896;
  CTSCriticalSection::Lock((CPipeManager *)((char *)v2 + 48896));
  v7 = 0;
  if ( *((_QWORD *)v2 + 1624) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v143);
    v143 = *((_QWORD *)v2 + 1624);
    v3 = v143;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v143);
    v7 = v3;
  }
  if ( *((_QWORD *)v2 + 1625) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v142);
    v5 = *((_QWORD *)v2 + 1625);
    v142 = v5;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v142);
  }
  if ( *((_QWORD *)v2 + 1638) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(v145);
    v6 = *((_QWORD *)v2 + 1638);
    v145[0] = v6;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  }
  TCntPtr<IRdpPipeEvents>::operator=(&v144, (char *)v2 + 13040);
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)v129);
  if ( !v7 )
  {
    v9 = -2147418113;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
      "PipeManagerError_FlushSrfCmdsNullProtocol",
      (char *)0x13C7,
      0x8000FFFF,
      v125);
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_125;
    v13 = "Protocol is null, can't flush surface commands";
    v126 = 5064;
    v14 = byte_180278CA3;
LABEL_11:
    *(_QWORD *)v129 = v13;
    v131 = "FlushSurfaceCommands";
    v128 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v15 = "Error condition failed";
LABEL_12:
    v130 = v15;
    v127 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v10,
      (_DWORD)v14,
      v11,
      v12,
      (__int64)&v130,
      (__int64)&v127,
      (__int64)&v128,
      (__int64)&v126,
      (__int64)&v131,
      (__int64)v129);
    goto LABEL_125;
  }
  v9 = 0;
  if ( *((_DWORD *)v2 + 13256) )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v7 + 136LL))(v7, &v136);
    if ( v9 < 0 )
    {
      v10 = (int)CallbackContext;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_125;
      v126 = 5070;
      *(_QWORD *)v129 = "Failed to get Protocol Encoder";
      v14 = byte_180278C55;
      v131 = "FlushSurfaceCommands";
      v128 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v15 = "Error HResult failed";
      goto LABEL_12;
    }
  }
  v126 = 0;
  if ( v5 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 176LL))(v5) )
  {
    memset_0(v146, 0, 0x640u);
    v16 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v5 + 168LL))(v5, v146);
    v9 = v16;
    if ( v16 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_FlushSrfCmdsUTGetMonitorLayoutFail",
        (char *)0x13DB,
        v16,
        v125);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_125;
      v126 = 5084;
      *(_QWORD *)v129 = "Failed to get the desktop layout";
      v14 = &byte_180278C07;
      v131 = "FlushSurfaceCommands";
      v128 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v15 = "Error HResult failed";
      goto LABEL_12;
    }
    *((_DWORD *)v2 + 13275) = v149;
    *((_DWORD *)v2 + 13276) = v148;
    if ( (unsigned int)CallbackContext > 4 )
    {
      v127 = *((_DWORD *)v2 + 13276);
      LODWORD(v137) = v127;
      *(_QWORD *)v129 = "Surface: Resetting output size and layout";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v17,
        (unsigned int)&word_180278BCE,
        v18,
        v19,
        (__int64)v129,
        (__int64)&v137,
        (__int64)&v127);
    }
    v20 = v136;
    if ( v136 )
    {
      v151 = 0;
      memset_0(v152, 0, sizeof(v152));
      v23 = v147;
      if ( v147 > 0x10 )
      {
        v9 = -2147467259;
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_FlushSrfCmdsUTMaxNumMonitorsExceeded",
          (char *)0x13EE,
          0x80004005,
          v125);
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_125;
        v13 = "Number of monitors greater than max supported";
        v126 = 5103;
        v14 = (char *)qword_180278B80;
        goto LABEL_11;
      }
      v24 = 0;
      if ( v147 )
      {
        v25 = 0;
        do
        {
          v26 = 5 * v25;
          v152[v26 - 1] = v150[8 * v25];
          v152[v26] = v150[8 * v25 + 1];
          v152[v26 + 1] = v150[8 * v25 + 2];
          v152[v26 + 2] = v150[8 * v25 + 3];
          v152[v26 + 3] = v150[8 * v25 + 7] != 0;
          if ( (unsigned int)CallbackContext > 4 )
          {
            v126 = v152[5 * v25 + 2];
            v127 = v152[5 * v25 + 1];
            LODWORD(v137) = v152[5 * v25];
            LODWORD(v139) = v152[5 * v25 - 1];
            *(_QWORD *)v129 = "Capability: Surface";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              32 * v25,
              (unsigned int)&word_180278B36,
              v21,
              v22,
              (__int64)v129,
              (__int64)&v139,
              (__int64)&v137,
              (__int64)&v127,
              (__int64)&v126);
          }
          ++v24;
          ++v25;
        }
        while ( v24 < v23 );
        v20 = v136;
      }
      v27 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(*v20 + 192))(
              v20,
              *((unsigned int *)v2 + 13276),
              *((unsigned int *)v2 + 13275),
              v23);
      v9 = v27;
      if ( v27 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_FlushSrfCmdsUTSetDesktopSizeFail",
          (char *)0x1405,
          v27,
          (int)&v151);
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_125;
        v126 = 5126;
        *(_QWORD *)v129 = "Failed to encode the desktop size";
        v14 = (char *)qword_180278AE8;
        v131 = "FlushSurfaceCommands";
        v128 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v15 = "Error HResult failed";
        goto LABEL_12;
      }
      v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 112LL))(
              v3,
              *((unsigned int *)v2 + 13276),
              *((unsigned int *)v2 + 13275));
      v9 = v28;
      if ( v28 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_FlushSrfCmdsUTResetInputParamsFail",
          (char *)0x1409,
          v28,
          (int)&v151);
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_125;
        v126 = 5130;
        *(_QWORD *)v129 = "Failed to reset input";
        v14 = (char *)word_180278A9A;
        v131 = "FlushSurfaceCommands";
        v128 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v15 = "Error HResult failed";
        goto LABEL_12;
      }
      v29 = *((_DWORD *)v2 + 13275);
      v30 = *((_DWORD *)v2 + 13276);
      v126 = 1;
      CPipeManager::LogMonitorInfo(v2, v30, v29, v23, (struct tagTS_MONITOR_DEF *const)&v151);
    }
    else
    {
      v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _BYTE *))(*(_QWORD *)v3 + 104LL))(
              v3,
              *((unsigned int *)v2 + 13276),
              *((unsigned int *)v2 + 13275),
              v146);
      v9 = v32;
      if ( v32 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_FlushSrfCmdsUTResetProtocolFail",
          (char *)0x1415,
          v32,
          v125);
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_125;
        v126 = 5142;
        *(_QWORD *)v129 = "Failed to reset protocol";
        v14 = (char *)&dword_180278A4C;
        v131 = "FlushSurfaceCommands";
        v128 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v15 = "Error HResult failed";
        goto LABEL_12;
      }
    }
    v8 = v144;
    if ( v144 )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v144 + 64LL))(
        v144,
        *((unsigned int *)v2 + 13276),
        *((unsigned int *)v2 + 13275));
  }
  v31 = (const char *)*((_QWORD *)v2 + 6237);
  v128 = v31;
  while ( (unsigned int)CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::GetNext(v8, &v128, &v134) )
  {
    if ( v136 )
    {
      v33 = v134;
      v34 = ((*(_DWORD *)(v134 + 432) & 0xC) != 8) + 32;
      v125 = v34;
      v35 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(*v136 + 136))(
              v136,
              *(unsigned __int16 *)(v134 + 56),
              *(unsigned int *)(v134 + 72),
              *(unsigned int *)(v134 + 76));
      v9 = v35;
      if ( v35 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_FlushSrfCmdsCreateSrfEncoderFail",
          (char *)0x144A,
          v35,
          v34);
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_125;
        v126 = 5195;
        *(_QWORD *)v129 = "Failed to send create surface";
        v14 = (char *)&word_1802789FE;
        v131 = "FlushSurfaceCommands";
        v128 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v15 = "Error HResult failed";
        goto LABEL_12;
      }
      v126 = 1;
      if ( (unsigned int)CallbackContext > 4 )
      {
        *(_QWORD *)v129 = *(_QWORD *)(v33 + 624);
        v127 = v34;
        LODWORD(v137) = *(_DWORD *)(v33 + 76);
        LODWORD(v139) = *(_DWORD *)(v33 + 72);
        v135 = *(_WORD *)(v33 + 56);
        v130 = "Surface: Sent create surface command";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v36,
          (unsigned int)&word_1802789AE,
          v37,
          v38,
          (__int64)&v130,
          (__int64)&v135,
          (__int64)&v139,
          (__int64)&v137,
          (__int64)&v127,
          (__int64)v129);
      }
    }
    CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::RemoveAt((char *)v2 + 49472, v31);
    v31 = v128;
    TCntPtr<RdpSurface>::operator=(&v134, 0);
  }
  *(_QWORD *)v129 = *((_QWORD *)v2 + 6349);
  v128 = *(const char **)v129;
  while ( 1 )
  {
    if ( !(unsigned int)CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::GetNext(v39, &v128, &v134) )
    {
      v58 = (const char *)*((_QWORD *)v2 + 6293);
      v128 = v58;
      while ( 1 )
      {
        if ( !(unsigned int)CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::GetNext(v57, &v128, &v134) )
        {
          v85 = (const char *)*((_QWORD *)v2 + 6517);
          v128 = v85;
          while ( 1 )
          {
            if ( !(unsigned int)CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::GetNext(v84, &v128, &v134) )
            {
              v95 = (const char *)*((_QWORD *)v2 + 6573);
              v137 = v95;
              v128 = v95;
              while ( 1 )
              {
                if ( !(unsigned int)CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::GetNext(v94, &v128, &v134) )
                {
                  *((_DWORD *)v2 + 13257) = 0;
                  *((_DWORD *)v2 + 13258) |= v126;
                  *((_DWORD *)v2 + 13248) = 9;
                  goto LABEL_125;
                }
                if ( v136 )
                {
                  v99 = v134;
                  v141 = *(_QWORD *)(v134 + 408);
                  v100 = v141;
                  v101 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v141 + 40LL);
                  v102 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v100 + 32LL))(v100);
                  v103 = v101(v100);
                  *(_QWORD *)v129 = 0;
                  v104 = *(unsigned __int16 *)(v99 + 56);
                  v105 = (4 * v103 * v102) & 0x1FFFFFFF;
                  v106 = *(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, int *))(*v136 + 232);
                  LODWORD(v130) = v105;
                  v107 = v106(v136, v104, v105, v129);
                  v9 = v107;
                  if ( v107 < 0 )
                  {
                    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
                      "PipeManagerError_FlushSrfCmdsUpdateSurfaceStartWatermarkingFail",
                      (char *)0x1540,
                      v107,
                      v125);
                    if ( (unsigned int)CallbackContext > 2 )
                    {
                      LODWORD(v130) = 5441;
                      v140 = "StartWatermarkingBitmap failed!";
                      LODWORD(v133) = v9;
                      *(_QWORD *)v132 = "FlushSurfaceCommands";
                      v131 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
                      v128 = "Error HResult failed";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                        v122,
                        (unsigned int)byte_180278609,
                        v123,
                        v124,
                        (__int64)&v128,
                        (__int64)&v133,
                        (__int64)&v131,
                        (__int64)&v130,
                        (__int64)v132,
                        (__int64)&v140);
                    }
                    goto LABEL_125;
                  }
                  if ( v105 )
                  {
                    v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v100 + 48LL))(
                           v100,
                           32,
                           *(_QWORD *)v129,
                           v105);
                    if ( v9 < 0 )
                    {
                      if ( (unsigned int)CallbackContext > 2 )
                      {
                        LODWORD(v130) = 5453;
                        v140 = "qrEncoder->Copy failed!";
                        LODWORD(v133) = v9;
                        *(_QWORD *)v132 = "FlushSurfaceCommands";
                        v131 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
                        v128 = "Error HResult failed";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                          v108,
                          (unsigned int)byte_1802785BB,
                          v109,
                          v110,
                          (__int64)&v128,
                          (__int64)&v133,
                          (__int64)&v131,
                          (__int64)&v130,
                          (__int64)v132,
                          (__int64)&v140);
                      }
                      goto LABEL_125;
                    }
                  }
                  *(_QWORD *)v132 = v136;
                  v139 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*v136 + 240);
                  LODWORD(v133) = *(_DWORD *)(v99 + 416);
                  LODWORD(v138) = *((_DWORD *)v131 + 13447);
                  v111 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v141 + 40LL))(v141);
                  v112 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v141 + 32LL))(v141);
                  v125 = 0;
                  v113 = v139(*(_QWORD *)v132, v112, v111, 0);
                  v9 = v113;
                  if ( v113 < 0 )
                  {
                    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
                      "PipeManagerError_FlushSrfCmdsUpdateSurfaceCommitWatermarkingFail",
                      (char *)0x155E,
                      v113,
                      0);
                    if ( (unsigned int)CallbackContext > 2 )
                    {
                      LODWORD(v130) = 5471;
                      v140 = "Failed to send watermarking bitmap to output";
                      LODWORD(v133) = v9;
                      *(_QWORD *)v132 = "FlushSurfaceCommands";
                      v128 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
                      v138 = "Error HResult failed";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                        v117,
                        (unsigned int)byte_18027856D,
                        v118,
                        v119,
                        (__int64)&v138,
                        (__int64)&v133,
                        (__int64)&v128,
                        (__int64)&v130,
                        (__int64)v132,
                        (__int64)&v140);
                    }
                    v2 = (CPipeManager *)v131;
                    goto LABEL_125;
                  }
                  if ( (unsigned int)CallbackContext > 4 )
                  {
                    v140 = *(const char **)(v99 + 624);
                    LOWORD(v127) = *(_WORD *)(v99 + 56);
                    *(_QWORD *)v132 = "Surface: Sent watermark surface command.";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>>(
                      v114,
                      (unsigned int)byte_180278539,
                      v115,
                      v116,
                      (__int64)v132,
                      (__int64)&v127,
                      (__int64)&v140);
                  }
                  v2 = (CPipeManager *)v131;
                  v95 = v137;
                }
                CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::RemoveAt((char *)v2 + 52160, v95);
                v95 = v128;
                v137 = v128;
                TCntPtr<RdpSurface>::operator=(&v134, 0);
              }
            }
            if ( v136 )
            {
              v89 = v134;
              v90 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(*v136 + 184))(
                      v136,
                      *(unsigned __int16 *)(v134 + 56),
                      *(unsigned int *)(v134 + 1652));
              v9 = v90;
              if ( v90 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
                  "PipeManagerError_FlushSrfCmdsUpdateSurfaceProtectionFail",
                  (char *)0x151B,
                  v90,
                  v125);
                if ( (unsigned int)CallbackContext > 2 )
                {
                  LODWORD(v130) = 5404;
                  *(_QWORD *)v132 = "Failed to send ProtectSurface surface";
                  LODWORD(v133) = v9;
                  *(_QWORD *)v129 = "FlushSurfaceCommands";
                  v131 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
                  v128 = "Error HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v96,
                    (unsigned int)byte_18027868B,
                    v97,
                    v98,
                    (__int64)&v128,
                    (__int64)&v133,
                    (__int64)&v131,
                    (__int64)&v130,
                    (__int64)v129,
                    (__int64)v132);
                }
                goto LABEL_125;
              }
              if ( (unsigned int)CallbackContext > 4 )
              {
                *(_QWORD *)v132 = *(_QWORD *)(v89 + 624);
                LOWORD(v127) = *(_WORD *)(v89 + 56);
                *(_QWORD *)v129 = "Surface: Sent protect surface command.";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>>(
                  v91,
                  (unsigned int)&byte_180278657,
                  v92,
                  v93,
                  (__int64)v129,
                  (__int64)&v127,
                  (__int64)v132);
              }
            }
            CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::RemoveAt((char *)v2 + 51712, v85);
            v85 = v128;
            TCntPtr<RdpSurface>::operator=(&v134, 0);
          }
        }
        if ( v136 )
        {
          v79 = v134;
          v80 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v136 + 144))(v136, *(unsigned __int16 *)(v134 + 56));
          v9 = v80;
          if ( v80 < 0 )
          {
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
              "PipeManagerError_FlushSrfCmdsDeleteSurfaceFail",
              (char *)0x14FB,
              v80,
              v125);
            if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(v130) = 5372;
              *(_QWORD *)v132 = "Failed to send delete surface";
              LODWORD(v133) = v9;
              *(_QWORD *)v129 = "FlushSurfaceCommands";
              v131 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
              v128 = "Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v86,
                (unsigned int)byte_18027870D,
                v87,
                v88,
                (__int64)&v128,
                (__int64)&v133,
                (__int64)&v131,
                (__int64)&v130,
                (__int64)v129,
                (__int64)v132);
            }
            goto LABEL_125;
          }
          v126 = 1;
          if ( (unsigned int)CallbackContext > 4 )
          {
            *(_QWORD *)v132 = *(_QWORD *)(v79 + 624);
            LOWORD(v127) = *(_WORD *)(v79 + 56);
            *(_QWORD *)v129 = "Surface: Sent delete surface command.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>>(
              v81,
              (unsigned int)byte_1802786D9,
              v82,
              v83,
              (__int64)v129,
              (__int64)&v127,
              (__int64)v132);
          }
        }
        CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::RemoveAt((char *)v2 + 49920, v58);
        v58 = v128;
        TCntPtr<RdpSurface>::operator=(&v134, 0);
      }
    }
    if ( v136 )
      break;
LABEL_70:
    CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::RemoveAt((char *)v2 + 50368, *(_QWORD *)v129);
    *(_QWORD *)v129 = v128;
    TCntPtr<RdpSurface>::operator=(&v134, 0);
  }
  v40 = v134;
  v41 = *(const char **)(v134 + 376);
  v42 = *(_DWORD *)(v134 + 384);
  v43 = *(_DWORD *)(v134 + 388);
  v44 = *(_DWORD *)(v134 + 400);
  v45 = *(_DWORD *)(v134 + 404);
  v126 = v42;
  LODWORD(v130) = v43;
  v46 = *((_DWORD *)v2 + 13437);
  if ( (unsigned __int64)(v41 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v47 = *(unsigned int *)(v134 + 392);
    v48 = v46 == 0;
    v49 = *v136;
    v50 = *(unsigned __int16 *)(v134 + 56);
    if ( v48 )
    {
      v125 = *(_DWORD *)(v134 + 396);
      v55 = (*(__int64 (__fastcall **)(__int64 *, const char *, __int64, __int64))(v49 + 168))(v136, v41, v50, v47);
      v9 = v55;
      if ( v55 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_FlushSrfCmdsAssociateSurfaceToWindowFail",
          (char *)0x14A2,
          v55,
          v125);
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v130) = 5283;
          *(_QWORD *)v132 = "Failed to send associate surface to window";
          LODWORD(v133) = v9;
          *(_QWORD *)v129 = "FlushSurfaceCommands";
          v131 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
          v128 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v70,
            (unsigned int)&byte_1802788BF,
            v71,
            v72,
            (__int64)&v128,
            (__int64)&v133,
            (__int64)&v131,
            (__int64)&v130,
            (__int64)v129,
            (__int64)v132);
        }
        goto LABEL_125;
      }
    }
    else
    {
      v125 = *(_DWORD *)(v134 + 396);
      v51 = (*(__int64 (__fastcall **)(__int64 *, const char *, __int64, __int64))(v49 + 176))(v136, v41, v50, v47);
      v9 = v51;
      if ( v51 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_FlushSrfCmdsAssociateSurfaceToWindowFail",
          (char *)0x148F,
          v51,
          v125);
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v130) = 5264;
          *(_QWORD *)v132 = "Failed to send associate surface to window";
          LODWORD(v133) = v9;
          *(_QWORD *)v129 = "FlushSurfaceCommands";
          v131 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
          v128 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v67,
            (unsigned int)qword_180278960,
            v68,
            v69,
            (__int64)&v128,
            (__int64)&v133,
            (__int64)&v131,
            (__int64)&v130,
            (__int64)v129,
            (__int64)v132);
        }
        goto LABEL_125;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(v141) = v45;
        LODWORD(v138) = v44;
        v133 = v41;
        v135 = *(_WORD *)(v40 + 56);
        *(_QWORD *)v132 = "Surface: Sent associate to scaled output window command.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v52,
          (unsigned int)byte_18027890D,
          v53,
          v54,
          (__int64)v132,
          (__int64)&v135,
          (__int64)&v133,
          (__int64)&v138,
          (__int64)&v141);
      }
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      *(_QWORD *)v132 = v41;
      LOWORD(v139) = *(_WORD *)(v40 + 56);
      v133 = "Surface: Sent associate to output window command. surf.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>>(
        v52,
        (unsigned int)&byte_180278887,
        v53,
        v54,
        (__int64)&v133,
        (__int64)&v139,
        (__int64)v132);
    }
    goto LABEL_66;
  }
  if ( v46 )
  {
    if ( !v44 || !v45 )
    {
      v44 = *(_DWORD *)(v134 + 72);
      v45 = *(_DWORD *)(v134 + 76);
    }
    v125 = v43;
    v59 = (*(__int64 (__fastcall **)(__int64 *, bool, _QWORD))(*v136 + 160))(
            v136,
            v41 == 0,
            *(unsigned __int16 *)(v134 + 56));
    v9 = v59;
    if ( v59 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_FlushSrfCmdsAssociateSurfaceFail",
        (char *)0x14BB,
        v59,
        v125);
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v130) = 5308;
        *(_QWORD *)v132 = "Failed to send associate surface2 to output";
        LODWORD(v133) = v9;
        *(_QWORD *)v129 = "FlushSurfaceCommands";
        v131 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v128 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v73,
          (unsigned int)byte_180278839,
          v74,
          v75,
          (__int64)&v128,
          (__int64)&v133,
          (__int64)&v131,
          (__int64)&v130,
          (__int64)v129,
          (__int64)v132);
      }
      goto LABEL_125;
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v141) = v44;
      v56 = v126;
      LODWORD(v133) = v126;
      LODWORD(v138) = v45;
      LOWORD(v137) = *(_WORD *)(v40 + 56);
      *(_QWORD *)v132 = "Surface: Sent associate to output surface2 command. surf.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v60,
        (unsigned int)byte_1802787E5,
        v61,
        v62,
        (__int64)v132,
        (__int64)&v137,
        (__int64)&v133,
        (__int64)&v126,
        (__int64)&v141,
        (__int64)&v138);
      goto LABEL_67;
    }
LABEL_66:
    v56 = v126;
LABEL_67:
    v126 = 1;
    if ( v6 && !v41 )
    {
      v125 = v56;
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v6 + 112LL))(
        v6,
        *(unsigned __int16 *)(v40 + 56),
        *(unsigned int *)(v40 + 72),
        *(unsigned int *)(v40 + 76));
    }
    goto LABEL_70;
  }
  v125 = v43;
  v56 = v42;
  v63 = (*(__int64 (__fastcall **)(__int64 *, bool, _QWORD))(*v136 + 152))(
          v136,
          v41 == 0,
          *(unsigned __int16 *)(v134 + 56));
  v9 = v63;
  if ( v63 >= 0 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v133) = v56;
      LODWORD(v138) = v56;
      LOWORD(v127) = *(_WORD *)(v40 + 56);
      *(_QWORD *)v132 = "Surface: Sent associate to output surface command.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v64,
        (unsigned int)byte_18027875B,
        v65,
        v66,
        (__int64)v132,
        (__int64)&v127,
        (__int64)&v138,
        (__int64)&v133);
    }
    goto LABEL_67;
  }
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
    "PipeManagerError_FlushSrfCmdsAssociateSurfaceFail",
    (char *)0x14D0,
    v63,
    v125);
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v130) = 5329;
    *(_QWORD *)v132 = "Failed to send associate surface to output";
    LODWORD(v133) = v9;
    *(_QWORD *)v129 = "FlushSurfaceCommands";
    v131 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v128 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v76,
      (unsigned int)&byte_180278797,
      v77,
      v78,
      (__int64)&v128,
      (__int64)&v133,
      (__int64)&v131,
      (__int64)&v130,
      (__int64)v129,
      (__int64)v132);
  }
LABEL_125:
  if ( v136 )
    (*(void (__fastcall **)(__int64 *))(*v136 + 32))(v136);
  PerfCounterSetRdpIntervalMarker(*((struct IRDPPerfCounterGeneric **)v2 + 6601), *((_DWORD *)v2 + 13249), 1u);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v144);
  TCntPtr<IRdpVCMgr>::SafeRelease(v145);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v142);
  v120 = v136;
  if ( v136 )
  {
    v136 = 0;
    (*(void (__fastcall **)(__int64 *))(*v120 + 16))(v120);
  }
  TCntPtr<IRdpVCMgr>::SafeRelease(&v143);
  TCntPtr<ClearCompressor>::SafeRelease(&v134);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180056be0  push    rbp
0x180056be2  push    rbx
0x180056be3  push    rsi
0x180056be4  push    rdi
0x180056be5  push    r12
0x180056be7  push    r13
0x180056be9  push    r14
0x180056beb  push    r15
0x180056bed  lea     rbp, [rsp-7A8h]
0x180056bf5  sub     rsp, 8A8h
0x180056bfc  mov     rax, cs:__security_cookie
0x180056c03  xor     rax, rsp
0x180056c06  mov     [rbp+7E0h+var_50], rax
0x180056c0d  mov     edx, [rcx+0CF04h]; unsigned int
0x180056c13  mov     r15, rcx
0x180056c16  mov     [rbp+7E0h+var_850], rcx
0x180056c1a  xor     edi, edi
0x180056c1c  mov     rcx, [rcx+0CE40h]; struct IRDPPerfCounterGeneric *
0x180056c23  xor     ebx, ebx
0x180056c25  xor     esi, esi
0x180056c27  mov     [rbp+7E0h+var_7F0], rdi
0x180056c2b  xor     r8d, r8d; unsigned int
0x180056c2e  mov     [rbp+7E0h+var_828], rdi
0x180056c32  mov     [rbp+7E0h+var_7F8], rbx
0x180056c36  mov     [rbp+7E0h+var_7E0], rsi
0x180056c3a  mov     [rbp+7E0h+var_7E8], rbx
0x180056c3e  mov     [rbp+7E0h+var_838], 0
0x180056c46  call    ?PerfCounterSetRdpIntervalMarker@@YAJPEAUIRDPPerfCounterGeneric@@II@Z; PerfCounterSetRdpIntervalMarker(IRDPPerfCounterGeneric *,uint,uint)
0x180056c4b  lea     rcx, [r15+0BF00h]; this
0x180056c52  mov     qword ptr [rbp+7E0h+var_860], rcx
0x180056c56  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180056c5b  xor     r12d, r12d
0x180056c5e  cmp     [r15+32C0h], rbx
0x180056c65  jz      short loc_180056C87
0x180056c67  lea     rcx, [rbp+7E0h+var_7F0]
0x180056c6b  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x180056c70  mov     rdi, [r15+32C0h]
0x180056c77  lea     rcx, [rbp+7E0h+var_7F0]
0x180056c7b  mov     [rbp+7E0h+var_7F0], rdi
0x180056c7f  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180056c84  mov     r12, rdi
0x180056c87  cmp     [r15+32C8h], rbx
0x180056c8e  jz      short loc_180056CAD
0x180056c90  lea     rcx, [rbp+7E0h+var_7F8]
0x180056c94  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x180056c99  mov     rbx, [r15+32C8h]
0x180056ca0  lea     rcx, [rbp+7E0h+var_7F8]
0x180056ca4  mov     [rbp+7E0h+var_7F8], rbx
0x180056ca8  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180056cad  cmp     [r15+3330h], rsi
0x180056cb4  jz      short loc_180056CDE
0x180056cb6  lea     rcx, [rbp+7E0h+var_7E0]
0x180056cba  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x180056cbf  mov     rsi, [r15+3330h]
0x180056cc6  mov     [rbp+7E0h+var_7E0], rsi
0x180056cca  test    rsi, rsi
0x180056ccd  jz      short loc_180056CDE
0x180056ccf  mov     rax, [rsi]
0x180056cd2  mov     rcx, rsi
0x180056cd5  mov     rax, [rax+8]
0x180056cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cde  lea     rdx, [r15+32F0h]
0x180056ce5  lea     rcx, [rbp+7E0h+var_7E8]
0x180056ce9  call    ??4?$TCntPtr@VIRdpPipeEvents@@@@QEAAPEAVIRdpPipeEvents@@AEBV0@@Z; TCntPtr<IRdpPipeEvents>::operator=(TCntPtr<IRdpPipeEvents> const &)
0x180056cee  lea     rcx, [rbp+7E0h+var_860]; this
0x180056cf2  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180056cf7  test    r12, r12
0x180056cfa  jnz     loc_180056DB5
0x180056d00  mov     r14d, 8000FFFFh
0x180056d06  lea     rdx, aPipemanagererr_85; "PipeManagerError_FlushSrfCmdsNullProtoc"...
0x180056d0d  mov     r9d, r14d; unsigned int
0x180056d10  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x180056d17  mov     r8d, 13C7h; char *
0x180056d1d  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180056d22  mov     eax, cs:CallbackContext
0x180056d28  cmp     eax, 2
0x180056d2b  jbe     loc_180058082
0x180056d31  lea     rax, aProtocolIsNull; "Protocol is null, can't flush surface c"...
0x180056d38  mov     [rsp+8E0h+var_870], 13C8h
0x180056d40  lea     rdx, byte_180278CA3
0x180056d47  mov     qword ptr [rbp+7E0h+var_860], rax
0x180056d4b  lea     rax, aFlushsurfaceco; "FlushSurfaceCommands"
0x180056d52  mov     [rbp+7E0h+var_850], rax
0x180056d56  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180056d5d  mov     [rsp+8E0h+var_868], rax
0x180056d62  lea     rax, aErrorCondition; "Error condition failed"
0x180056d69  mov     [rbp+7E0h+var_858], rax
0x180056d6d  lea     rax, [rbp+7E0h+var_860]
0x180056d71  mov     [rsp+8E0h+var_898], rax
0x180056d76  lea     rax, [rbp+7E0h+var_850]
0x180056d7a  mov     [rsp+8E0h+var_8A0], rax
0x180056d7f  lea     rax, [rsp+8E0h+var_870]
0x180056d84  mov     [rsp+8E0h+var_8A8], rax
0x180056d89  lea     rax, [rsp+8E0h+var_868]
0x180056d8e  mov     [rsp+8E0h+var_8B0], rax
0x180056d93  lea     rax, [rsp+8E0h+var_86C]
0x180056d98  mov     [rsp+8E0h+var_8B8], rax
0x180056d9d  lea     rax, [rbp+7E0h+var_858]
0x180056da1  mov     [rsp+8E0h+var_86C], r14d
0x180056da6  mov     [rsp+8E0h+var_8C0], rax
0x180056dab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180056db0  jmp     loc_180058082
0x180056db5  xor     r14d, r14d
0x180056db8  cmp     [r15+0CF20h], r14d
0x180056dbf  jz      short loc_180056E2B
0x180056dc1  mov     rax, [r12]
0x180056dc5  lea     rdx, [rbp+7E0h+var_828]
0x180056dc9  mov     rcx, r12
0x180056dcc  mov     rax, [rax+88h]
0x180056dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056dd8  mov     r14d, eax
0x180056ddb  test    eax, eax
0x180056ddd  jns     short loc_180056E2B
0x180056ddf  mov     ecx, cs:CallbackContext
0x180056de5  cmp     ecx, 2
0x180056de8  jbe     loc_180058082
0x180056dee  lea     rax, aFailedToGetPro_2; "Failed to get Protocol Encoder"
0x180056df5  mov     [rsp+8E0h+var_870], 13CEh
0x180056dfd  mov     qword ptr [rbp+7E0h+var_860], rax
0x180056e01  lea     rdx, byte_180278C55
0x180056e08  lea     rax, aFlushsurfaceco; "FlushSurfaceCommands"
0x180056e0f  mov     [rbp+7E0h+var_850], rax
0x180056e13  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180056e1a  mov     [rsp+8E0h+var_868], rax
0x180056e1f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180056e26  jmp     loc_180056D69
0x180056e2b  mov     [rsp+8E0h+var_870], 0
0x180056e33  test    rbx, rbx
0x180056e36  jz      loc_180057242
0x180056e3c  mov     rax, [rbx]
0x180056e3f  mov     rcx, rbx
0x180056e42  mov     rax, [rax+0B0h]
0x180056e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e4e  test    eax, eax
0x180056e50  jz      loc_180057242
0x180056e56  xor     edx, edx; Val
0x180056e58  lea     rcx, [rbp+7E0h+var_7D0]; void *
0x180056e5c  mov     r8d, 640h; Size
0x180056e62  call    memset_0
0x180056e67  mov     rax, [rbx]
0x180056e6a  lea     rdx, [rbp+7E0h+var_7D0]
0x180056e6e  mov     rcx, rbx
0x180056e71  mov     rax, [rax+0A8h]
0x180056e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e7d  mov     r14d, eax
0x180056e80  test    eax, eax
0x180056e82  jns     short loc_180056EEC
0x180056e84  mov     r9d, eax; unsigned int
0x180056e87  lea     rdx, aPipemanagererr_106; "PipeManagerError_FlushSrfCmdsUTGetMonit"...
0x180056e8e  mov     r8d, 13DBh; char *
0x180056e94  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x180056e9b  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180056ea0  mov     eax, cs:CallbackContext
0x180056ea6  cmp     eax, 2
0x180056ea9  jbe     loc_180058082
0x180056eaf  lea     rax, aFailedToGetThe_5; "Failed to get the desktop layout"
0x180056eb6  mov     [rsp+8E0h+var_870], 13DCh
0x180056ebe  mov     qword ptr [rbp+7E0h+var_860], rax
0x180056ec2  lea     rdx, byte_180278C07
0x180056ec9  lea     rax, aFlushsurfaceco; "FlushSurfaceCommands"
0x180056ed0  mov     [rbp+7E0h+var_850], rax
0x180056ed4  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180056edb  mov     [rsp+8E0h+var_868], rax
0x180056ee0  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180056ee7  jmp     loc_180056D69
0x180056eec  mov     eax, [rbp+7E0h+var_398]
0x180056ef2  mov     [r15+0CF6Ch], eax
0x180056ef9  mov     eax, [rbp+7E0h+var_39C]
0x180056eff  mov     [r15+0CF70h], eax
0x180056f06  mov     eax, cs:CallbackContext
0x180056f0c  cmp     eax, 4
0x180056f0f  jbe     short loc_180056F52
0x180056f11  mov     eax, [r15+0CF70h]
0x180056f18  lea     rdx, word_180278BCE
0x180056f1f  mov     [rsp+8E0h+var_86C], eax
0x180056f23  mov     dword ptr [rbp+7E0h+var_820], eax
0x180056f26  lea     rax, aSurfaceResetti; "Surface: Resetting output size and layo"...
0x180056f2d  mov     qword ptr [rbp+7E0h+var_860], rax
0x180056f31  lea     rax, [rsp+8E0h+var_86C]
0x180056f36  mov     [rsp+8E0h+var_8B0], rax
0x180056f3b  lea     rax, [rbp+7E0h+var_820]
0x180056f3f  mov     [rsp+8E0h+var_8B8], rax
0x180056f44  lea     rax, [rbp+7E0h+var_860]
0x180056f48  mov     [rsp+8E0h+var_8C0], rax; int
0x180056f4d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180056f52  mov     rbx, [rbp+7E0h+var_828]
0x180056f56  test    rbx, rbx
0x180056f59  jz      loc_180057253
0x180056f5f  xor     edx, edx; Val
0x180056f61  mov     [rbp+7E0h+var_190], 0
0x180056f6b  mov     r8d, 13Ch; Size
0x180056f71  lea     rcx, [rbp+7E0h+var_18C]; void *
0x180056f78  call    memset_0
0x180056f7d  mov     r12d, [rbp+7E0h+var_3A0]
0x180056f84  cmp     r12d, 10h
0x180056f88  jbe     short loc_180056FD6
0x180056f8a  mov     r14d, 80004005h
0x180056f90  lea     rdx, aPipemanagererr_81; "PipeManagerError_FlushSrfCmdsUTMaxNumMo"...
0x180056f97  mov     r9d, r14d; unsigned int
0x180056f9a  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x180056fa1  mov     r8d, 13EEh; char *
0x180056fa7  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180056fac  mov     eax, cs:CallbackContext
0x180056fb2  cmp     eax, 2
0x180056fb5  jbe     loc_180058082
0x180056fbb  lea     rax, aNumberOfMonito; "Number of monitors greater than max sup"...
0x180056fc2  mov     [rsp+8E0h+var_870], 13EFh
0x180056fca  lea     rdx, qword_180278B80
0x180056fd1  jmp     loc_180056D47
0x180056fd6  xor     r14d, r14d
0x180056fd9  test    r12d, r12d
0x180056fdc  jz      loc_1800570C8
0x180056fe2  xor     ebx, ebx
0x180056fe4  lea     rdx, [rbx+rbx*4]
0x180056fe8  mov     rcx, rbx
0x180056feb  shl     rcx, 5
0x180056fef  mov     eax, [rbp+rcx+7E0h+var_394]
0x180056ff6  mov     [rbp+rdx*4+7E0h+var_190], eax
0x180056ffd  mov     eax, [rbp+rcx+7E0h+var_390]
0x180057004  mov     [rbp+rdx*4+7E0h+var_18C], eax
0x18005700b  mov     eax, [rbp+rcx+7E0h+var_38C]
0x180057012  mov     [rbp+rdx*4+7E0h+var_188], eax
0x180057019  mov     eax, [rbp+rcx+7E0h+var_388]
0x180057020  mov     [rbp+rdx*4+7E0h+var_184], eax
0x180057027  xor     eax, eax
0x180057029  cmp     [rbp+rcx+7E0h+var_378], eax
0x180057030  setnz   al
0x180057033  mov     [rbp+rdx*4+7E0h+var_180], eax
0x18005703a  mov     eax, cs:CallbackContext
0x180057040  cmp     eax, 4
0x180057043  jbe     short loc_1800570B5
0x180057045  mov     eax, [rbp+rdx*4+7E0h+var_184]
0x18005704c  mov     [rsp+8E0h+var_870], eax
0x180057050  mov     eax, [rbp+rdx*4+7E0h+var_188]
0x180057057  mov     [rsp+8E0h+var_86C], eax
0x18005705b  mov     eax, [rbp+rdx*4+7E0h+var_18C]
0x180057062  mov     dword ptr [rbp+7E0h+var_820], eax
0x180057065  mov     eax, [rbp+rdx*4+7E0h+var_190]
0x18005706c  lea     rdx, word_180278B36
0x180057073  mov     dword ptr [rbp+7E0h+var_810], eax
0x180057076  lea     rax, aCapabilitySurf; "Capability: Surface"
0x18005707d  mov     qword ptr [rbp+7E0h+var_860], rax
0x180057081  lea     rax, [rsp+8E0h+var_870]
0x180057086  mov     [rsp+8E0h+var_8A0], rax
0x18005708b  lea     rax, [rsp+8E0h+var_86C]
0x180057090  mov     [rsp+8E0h+var_8A8], rax
0x180057095  lea     rax, [rbp+7E0h+var_820]
0x180057099  mov     [rsp+8E0h+var_8B0], rax
0x18005709e  lea     rax, [rbp+7E0h+var_810]
0x1800570a2  mov     [rsp+8E0h+var_8B8], rax
0x1800570a7  lea     rax, [rbp+7E0h+var_860]
0x1800570ab  mov     [rsp+8E0h+var_8C0], rax
0x1800570b0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800570b5  inc     r14d
0x1800570b8  inc     rbx
0x1800570bb  cmp     r14d, r12d
0x1800570be  jb      loc_180056FE4
0x1800570c4  mov     rbx, [rbp+7E0h+var_828]
0x1800570c8  mov     rax, [rbx]
0x1800570cb  lea     rcx, [rbp+7E0h+var_190]
0x1800570d2  mov     r8d, [r15+0CF6Ch]
0x1800570d9  mov     r9d, r12d
0x1800570dc  mov     edx, [r15+0CF70h]
0x1800570e3  mov     [rsp+8E0h+var_8C0], rcx; int
0x1800570e8  mov     rcx, rbx
0x1800570eb  mov     rax, [rax+0C0h]
0x1800570f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570f7  mov     r14d, eax
0x1800570fa  test    eax, eax
0x1800570fc  jns     short loc_180057166
0x1800570fe  mov     r9d, eax; unsigned int
0x180057101  lea     rdx, aPipemanagererr_94; "PipeManagerError_FlushSrfCmdsUTSetDeskt"...
0x180057108  mov     r8d, 1405h; char *
0x18005710e  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x180057115  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18005711a  mov     eax, cs:CallbackContext
0x180057120  cmp     eax, 2
0x180057123  jbe     loc_180058082
0x180057129  lea     rax, aFailedToEncode_0; "Failed to encode the desktop size"
0x180057130  mov     [rsp+8E0h+var_870], 1406h
0x180057138  mov     qword ptr [rbp+7E0h+var_860], rax
0x18005713c  lea     rdx, qword_180278AE8
0x180057143  lea     rax, aFlushsurfaceco; "FlushSurfaceCommands"
0x18005714a  mov     [rbp+7E0h+var_850], rax
0x18005714e  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180057155  mov     [rsp+8E0h+var_868], rax
0x18005715a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180057161  jmp     loc_180056D69
0x180057166  mov     rax, [rdi]
0x180057169  mov     rcx, rdi
0x18005716c  mov     r8d, [r15+0CF6Ch]
0x180057173  mov     edx, [r15+0CF70h]
0x18005717a  mov     rax, [rax+70h]
0x18005717e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057183  mov     r14d, eax
0x180057186  test    eax, eax
0x180057188  jns     short loc_1800571F2
0x18005718a  mov     r9d, eax; unsigned int
0x18005718d  lea     rdx, aPipemanagererr_49; "PipeManagerError_FlushSrfCmdsUTResetInp"...
0x180057194  mov     r8d, 1409h; char *
  ... truncated ...
```
