# CPipeManager::ConfigureProfile(void)

- ea: `0x18008d5a4`
- end: `0x18008dc35`
- name: `?ConfigureProfile@CPipeManager@@IEAAJXZ`
- size: `1681`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this)`
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180099b80`
- `0x18009c0e0`
- `0x18009df30`

## callees

- `0x180001f84`
- `0x18000202c`
- `0x18000ce04`
- `0x18000ce34`
- `0x180010cd8`
- `0x180010d14`
- `0x18001dcf4`
- `0x18002aafc`
- `0x1800396e4`
- `0x18003bf64`
- `0x18004f5bc`
- `0x1800868e0`
- `0x18008be64`
- `0x18008c840`
- `0x18008d5a4`
- `0x180096c80`
- `0x18009b938`
- `0x180158180`
- `0x18019c010`

## string_xrefs

- `0x18008d5e1`: `PipeManagerError_ConfigProfilFrameInProgressFail`
- `0x18008d615`: `ConfigureProfile called while frame is in progress`
- `0x18008d62e`: `ConfigureProfile`
- `0x18008d718`: `ConfigureProfile`
- `0x18008d950`: `ConfigureProfile`
- `0x18008d9eb`: `ConfigureProfile`
- `0x18008da50`: `ConfigureProfile`
- `0x18008db9e`: `ConfigureProfile`
- `0x18008d6d7`: `PipeManagerError_ConfigProfileGetProcessorConfigFail`
- `0x18008d6ff`: `GetProcessorConfig failed`
- `0x18008d7a1`: `Processor selected for configuring profile`
- `0x18008da10`: `PipeManagerError_ConfigProfileInconsistentProfileState`
- `0x18008d9aa`: `PipeManagerError_ConfigProfileSetConfigFail`
- `0x18008d9d2`: `SetConfig failed`
- `0x18008d90f`: `PipeManagerError_ConfigProfileAddProcessorFail`
- `0x18008db85`: `CheckDownsampleReady failed`

## pseudocode

```c
__int64 __fastcall CPipeManager::ConfigureProfile(CPipeManager *this, __int64 a2, int a3, int a4)
{
  CPipeManager *v4; // rsi
  __int64 v5; // rbx
  int v6; // r14d
  char *v7; // rdx
  const char **v8; // rax
  __int64 v9; // rcx
  signed int v10; // eax
  unsigned int v11; // r15d
  int v12; // r12d
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  const char *v16; // rdi
  signed int v17; // eax
  signed int v18; // eax
  __int64 v19; // rcx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  char *v23; // rdx
  const char **v24; // rax
  const char *v25; // rax
  char *v26; // rdi
  PixelMap *v27; // rcx
  unsigned int v28; // edx
  int v30; // [rsp+20h] [rbp-49h]
  const char **v31; // [rsp+30h] [rbp-39h]
  const char **v32; // [rsp+30h] [rbp-39h]
  const char **v33; // [rsp+40h] [rbp-29h]
  const char **v34; // [rsp+40h] [rbp-29h]
  const char **v35; // [rsp+48h] [rbp-21h]
  __int64 v36; // [rsp+50h] [rbp-19h] BYREF
  const char *v37; // [rsp+58h] [rbp-11h] BYREF
  const char *v38; // [rsp+60h] [rbp-9h] BYREF
  const char *v39; // [rsp+68h] [rbp-1h] BYREF
  const char *v40; // [rsp+70h] [rbp+7h] BYREF
  __int64 v41[9]; // [rsp+78h] [rbp+Fh] BYREF
  char *i; // [rsp+D0h] [rbp+67h] BYREF
  const char *v43; // [rsp+D8h] [rbp+6Fh] BYREF
  const char *v44; // [rsp+E0h] [rbp+77h] BYREF
  struct IRDPKeyCollection *v45; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = this;
  v5 = 0;
  v45 = 0;
  v6 = -2147467259;
  v36 = 0;
  v41[0] = 0;
  if ( *((_DWORD *)this + 13244) )
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
      "PipeManagerError_ConfigProfilFrameInProgressFail",
      (char *)0x11D3,
      0x80004005,
      v30);
  if ( *((_DWORD *)v4 + 13244) )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(i) = 4564;
      v44 = "ConfigureProfile called while frame is in progress";
      v7 = byte_1802794D3;
      v37 = "ConfigureProfile";
      v38 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v39 = "Error condition failed";
      v33 = &v37;
      v31 = &v38;
      v8 = &v39;
LABEL_6:
      LODWORD(v43) = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (_DWORD)v7,
        a3,
        a4,
        (__int64)v8,
        (__int64)&v43,
        (__int64)v31,
        (__int64)&i,
        (__int64)v33,
        (__int64)&v44);
    }
  }
  else
  {
    CTSSimpleKeyComPtrArray<enum PipelineProcessor,IRdpProcessor>::RemoveAll((char *)v4 + 48976);
    v9 = *((_QWORD *)v4 + 1631);
    *((_QWORD *)v4 + 6115) = 0;
    *((_DWORD *)v4 + 12232) = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, struct IRDPKeyCollection **))(*(_QWORD *)v9 + 136LL))(v9, &v45);
    v6 = v10;
    if ( v10 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_ConfigProfileGetProcessorConfigFail",
        (char *)0x11E2,
        v10,
        v30);
      LODWORD(this) = (_DWORD)CallbackContext;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_56;
      LODWORD(i) = 4579;
      v44 = "GetProcessorConfig failed";
      v7 = byte_180279485;
      v39 = "ConfigureProfile";
      v38 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v37 = "Error HResult failed";
      v33 = &v39;
      v31 = &v38;
      v8 = &v37;
      goto LABEL_6;
    }
    v11 = 0;
    v12 = 1;
    do
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v4 + 1631) + 112LL))(
             *((_QWORD *)v4 + 1631),
             v11) )
      {
        if ( (unsigned int)CallbackContext > 5 )
        {
          LODWORD(i) = v11;
          v43 = "Processor selected for configuring profile";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v13,
            (unsigned int)byte_180279421,
            v14,
            v15,
            (__int64)&v43,
            (__int64)&i);
        }
        v44 = 0;
        if ( !(unsigned int)CTSSimpleKeyComPtrArray<enum PipelineProcessor,IRdpProcessor>::Find(
                              (char *)v4 + 48944,
                              v11,
                              &v44) )
        {
          v6 = -2147418113;
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
            "PipeManagerError_ConfigProfileInconsistentProfileState",
            (char *)0x11EE,
            0x8000FFFF,
            v30);
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(i) = 4591;
            v40 = "Inconsistent profile state";
            v23 = byte_1802793D3;
            v39 = "ConfigureProfile";
            v38 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
            v25 = "Error condition failed";
LABEL_40:
            v37 = v25;
            v35 = &v40;
            v34 = &v39;
            v32 = &v38;
            v24 = &v37;
LABEL_41:
            LODWORD(v43) = v6;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v20,
              (_DWORD)v23,
              v21,
              v22,
              (__int64)v24,
              (__int64)&v43,
              (__int64)v32,
              (__int64)&i,
              (__int64)v34,
              (__int64)v35);
          }
LABEL_42:
          TCntPtr<IRdpVCMgr>::SafeRelease(&v44);
          goto LABEL_56;
        }
        v16 = v44;
        v17 = (*(__int64 (__fastcall **)(const char *, struct IRDPKeyCollection *))(*(_QWORD *)v44 + 72LL))(v44, v45);
        v6 = v17;
        if ( v17 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
            "PipeManagerError_ConfigProfileSetConfigFail",
            (char *)0x11F2,
            v17,
            v30);
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(i) = 4595;
            v40 = "SetConfig failed";
            v23 = byte_180279385;
            v39 = "ConfigureProfile";
            v38 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
            v25 = "Error HResult failed";
            goto LABEL_40;
          }
          goto LABEL_42;
        }
        v18 = CTSSimpleKeyComPtrArray<enum PipelineProcessor,IRdpProcessor>::Add((char *)v4 + 48976, v11, v16);
        v6 = v18;
        if ( v18 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
            "PipeManagerError_ConfigProfileAddProcessorFail",
            (char *)0x11F6,
            v18,
            v30);
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(i) = 4599;
            v39 = "m_selectedProcessor.Add failed";
            v23 = &byte_180279337;
            v38 = "ConfigureProfile";
            v37 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
            v40 = "Error HResult failed";
            v35 = &v39;
            v34 = &v38;
            v32 = &v37;
            v24 = &v40;
            goto LABEL_41;
          }
          goto LABEL_42;
        }
        if ( !*((_DWORD *)v4 + 12230) && v11 == 7 )
          *((_DWORD *)v4 + 12230) = 1;
        if ( !*((_DWORD *)v4 + 12231) && v11 == 5 )
          *((_DWORD *)v4 + 12231) = 1;
        if ( !*((_DWORD *)v4 + 12232) && v11 == 4 )
          *((_DWORD *)v4 + 12232) = 1;
        TCntPtr<IRdpVCMgr>::SafeRelease(&v44);
      }
      ++v11;
    }
    while ( (int)v11 <= 9 );
    if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v4 + 1631) + 112LL))(
            *((_QWORD *)v4 + 1631),
            2)
      || !(*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v4 + 1631) + 112LL))(
            *((_QWORD *)v4 + 1631),
            3)
      || !(*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v4 + 1631) + 112LL))(
            *((_QWORD *)v4 + 1631),
            7) )
    {
      v12 = 0;
    }
    *((_DWORD *)v4 + 13359) = v12;
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1631) + 72LL))(*((_QWORD *)v4 + 1631)) )
    {
      v43 = (const char *)*((_QWORD *)v4 + 6181);
      for ( i = 0;
            (unsigned int)CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::GetNext(v19, &v43, &i);
            TCntPtr<RdpSurface>::operator=(&i, 0) )
      {
        v26 = i;
        v27 = (PixelMap *)*((_QWORD *)i + 18);
        if ( v27 )
          PixelMap::`scalar deleting destructor'(v27, v28);
        *((_QWORD *)v26 + 18) = 0;
        TCntPtr<MotionDetectionContext>::operator=(v26 + 248, 0);
      }
      TCntPtr<ClearCompressor>::SafeRelease(&i);
    }
    i = (char *)v4 + 48896;
    CTSCriticalSection::Lock((CPipeManager *)((char *)v4 + 48896));
    if ( *((_QWORD *)v4 + 1624) )
    {
      TCntPtr<IRdpVCMgr>::SafeRelease(&v36);
      v5 = *((_QWORD *)v4 + 1624);
      v36 = v5;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v36);
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&i);
    if ( v5 )
      (*(void (__fastcall **)(__int64, struct IRDPKeyCollection *))(*(_QWORD *)v5 + 248LL))(v5, v45);
    v6 = CPipeManager::CheckDownsampleReady(v4, v45);
    if ( v6 >= 0 )
    {
      *((_DWORD *)v4 + 13436) = CPipeManager::IsEarlyGfxSourceUpdatesEnabled(v4);
      goto LABEL_56;
    }
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(i) = 4658;
      v44 = "CheckDownsampleReady failed";
      v7 = byte_1802792E9;
      v40 = "ConfigureProfile";
      v39 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v38 = "Error HResult failed";
      v33 = &v40;
      v31 = &v39;
      v8 = &v38;
      goto LABEL_6;
    }
  }
LABEL_56:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v36);
  TCntPtr<IRdpVCMgr>::SafeRelease(v41);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v45);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18008d5a4  push    rbp
0x18008d5a6  push    rbx
0x18008d5a7  push    rsi
0x18008d5a8  push    rdi
0x18008d5a9  push    r12
0x18008d5ab  push    r13
0x18008d5ad  push    r14
0x18008d5af  push    r15
0x18008d5b1  lea     rbp, [rsp-1Fh]
0x18008d5b6  sub     rsp, 88h
0x18008d5bd  xor     edi, edi
0x18008d5bf  mov     rsi, rcx
0x18008d5c2  mov     ebx, edi
0x18008d5c4  mov     [rbp+57h+arg_18], rdi
0x18008d5c8  mov     r14d, 80004005h
0x18008d5ce  mov     [rbp+57h+var_70], rbx
0x18008d5d2  mov     [rbp+57h+var_48], rdi
0x18008d5d6  cmp     [rcx+0CEF0h], edi
0x18008d5dc  jz      short loc_18008D5FA
0x18008d5de  mov     r9d, r14d; unsigned int
0x18008d5e1  lea     rdx, aPipemanagererr_19; "PipeManagerError_ConfigProfilFrameInPro"...
0x18008d5e8  mov     r8d, 11D3h; char *
0x18008d5ee  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18008d5f5  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008d5fa  cmp     [rsi+0CEF0h], edi
0x18008d600  jz      loc_18008D693
0x18008d606  mov     eax, cs:CallbackContext
0x18008d60c  cmp     eax, 2
0x18008d60f  jbe     loc_18008DC03
0x18008d615  lea     rax, aConfigureprofi; "ConfigureProfile called while frame is "...
0x18008d61c  mov     dword ptr [rbp+57h+arg_0], 11D4h
0x18008d623  mov     [rbp+57h+arg_10], rax
0x18008d627  lea     rdx, byte_1802794D3
0x18008d62e  lea     rax, aConfigureprofi_1; "ConfigureProfile"
0x18008d635  mov     [rbp+57h+var_68], rax
0x18008d639  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008d640  mov     [rbp+57h+var_60], rax
0x18008d644  lea     rax, aErrorCondition; "Error condition failed"
0x18008d64b  mov     [rbp+57h+var_58], rax
0x18008d64f  lea     rax, [rbp+57h+arg_10]
0x18008d653  mov     [rsp+0C0h+var_78], rax
0x18008d658  lea     rax, [rbp+57h+var_68]
0x18008d65c  mov     [rsp+0C0h+var_80], rax
0x18008d661  lea     rax, [rbp+57h+arg_0]
0x18008d665  mov     [rsp+0C0h+var_88], rax
0x18008d66a  lea     rax, [rbp+57h+var_60]
0x18008d66e  mov     [rsp+0C0h+var_90], rax
0x18008d673  lea     rax, [rbp+57h+arg_8]
0x18008d677  mov     [rsp+0C0h+var_98], rax
0x18008d67c  lea     rax, [rbp+57h+var_58]
0x18008d680  mov     dword ptr [rbp+57h+arg_8], r14d
0x18008d684  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18008d689  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008d68e  jmp     loc_18008DC03
0x18008d693  lea     r13, [rsi+0BF50h]
0x18008d69a  mov     rcx, r13
0x18008d69d  call    ?RemoveAll@?$CTSSimpleKeyComPtrArray@W4PipelineProcessor@@VIRdpProcessor@@@@QEAAXXZ; CTSSimpleKeyComPtrArray<PipelineProcessor,IRdpProcessor>::RemoveAll(void)
0x18008d6a2  mov     rcx, [rsi+32F8h]
0x18008d6a9  lea     rdx, [rbp+57h+arg_18]
0x18008d6ad  mov     [rsi+0BF18h], rdi
0x18008d6b4  mov     [rsi+0BF20h], edi
0x18008d6ba  mov     rax, [rcx]
0x18008d6bd  mov     rax, [rax+88h]
0x18008d6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d6c9  mov     r14d, eax
0x18008d6cc  test    eax, eax
0x18008d6ce  jns     loc_18008D76F
0x18008d6d4  mov     r9d, eax; unsigned int
0x18008d6d7  lea     rdx, aPipemanagererr_57; "PipeManagerError_ConfigProfileGetProces"...
0x18008d6de  mov     r8d, 11E2h; char *
0x18008d6e4  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18008d6eb  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008d6f0  mov     ecx, cs:CallbackContext
0x18008d6f6  cmp     ecx, 2
0x18008d6f9  jbe     loc_18008DC03
0x18008d6ff  lea     rax, aGetprocessorco; "GetProcessorConfig failed"
0x18008d706  mov     dword ptr [rbp+57h+arg_0], 11E3h
0x18008d70d  mov     [rbp+57h+arg_10], rax
0x18008d711  lea     rdx, byte_180279485
0x18008d718  lea     rax, aConfigureprofi_1; "ConfigureProfile"
0x18008d71f  mov     [rbp+57h+var_58], rax
0x18008d723  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008d72a  mov     [rbp+57h+var_60], rax
0x18008d72e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008d735  mov     [rbp+57h+var_68], rax
0x18008d739  lea     rax, [rbp+57h+arg_10]
0x18008d73d  mov     [rsp+0C0h+var_78], rax
0x18008d742  lea     rax, [rbp+57h+var_58]
0x18008d746  mov     [rsp+0C0h+var_80], rax
0x18008d74b  lea     rax, [rbp+57h+arg_0]
0x18008d74f  mov     [rsp+0C0h+var_88], rax
0x18008d754  lea     rax, [rbp+57h+var_60]
0x18008d758  mov     [rsp+0C0h+var_90], rax
0x18008d75d  lea     rax, [rbp+57h+arg_8]
0x18008d761  mov     [rsp+0C0h+var_98], rax
0x18008d766  lea     rax, [rbp+57h+var_68]
0x18008d76a  jmp     loc_18008D680
0x18008d76f  mov     r15d, edi
0x18008d772  mov     r12d, 1
0x18008d778  mov     rcx, [rsi+32F8h]
0x18008d77f  mov     edx, r15d
0x18008d782  mov     rax, [rcx]
0x18008d785  mov     rax, [rax+70h]
0x18008d789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d78e  test    eax, eax
0x18008d790  jz      loc_18008D872
0x18008d796  mov     eax, cs:CallbackContext
0x18008d79c  cmp     eax, 5
0x18008d79f  jbe     short loc_18008D7CE
0x18008d7a1  lea     rax, aProcessorSelec; "Processor selected for configuring prof"...
0x18008d7a8  mov     dword ptr [rbp+57h+arg_0], r15d
0x18008d7ac  mov     [rbp+57h+arg_8], rax
0x18008d7b0  lea     rdx, byte_180279421
0x18008d7b7  lea     rax, [rbp+57h+arg_0]
0x18008d7bb  mov     [rsp+0C0h+var_98], rax
0x18008d7c0  lea     rax, [rbp+57h+arg_8]
0x18008d7c4  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18008d7c9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008d7ce  lea     rcx, [rsi+0BF30h]
0x18008d7d5  mov     [rbp+57h+arg_10], rdi
0x18008d7d9  lea     r8, [rbp+57h+arg_10]
0x18008d7dd  mov     edx, r15d
0x18008d7e0  call    ?Find@?$CTSSimpleKeyComPtrArray@W4PipelineProcessor@@VIRdpProcessor@@@@QEAAHW4PipelineProcessor@@PEAPEAVIRdpProcessor@@@Z; CTSSimpleKeyComPtrArray<PipelineProcessor,IRdpProcessor>::Find(PipelineProcessor,IRdpProcessor * *)
0x18008d7e5  test    eax, eax
0x18008d7e7  jz      loc_18008DA0A
0x18008d7ed  mov     rdi, [rbp+57h+arg_10]
0x18008d7f1  mov     rdx, [rbp+57h+arg_18]
0x18008d7f5  mov     rcx, rdi
0x18008d7f8  mov     rax, [rdi]
0x18008d7fb  mov     rax, [rax+48h]
0x18008d7ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d804  mov     r14d, eax
0x18008d807  test    eax, eax
0x18008d809  js      loc_18008D9A7
0x18008d80f  mov     r8, rdi
0x18008d812  mov     edx, r15d
0x18008d815  mov     rcx, r13
0x18008d818  call    ?Add@?$CTSSimpleKeyComPtrArray@W4PipelineProcessor@@VIRdpProcessor@@@@QEAAJW4PipelineProcessor@@PEAVIRdpProcessor@@@Z; CTSSimpleKeyComPtrArray<PipelineProcessor,IRdpProcessor>::Add(PipelineProcessor,IRdpProcessor *)
0x18008d81d  xor     edi, edi
0x18008d81f  mov     r14d, eax
0x18008d822  test    eax, eax
0x18008d824  js      loc_18008D90C
0x18008d82a  cmp     [rsi+0BF18h], edi
0x18008d830  jnz     short loc_18008D83F
0x18008d832  cmp     r15d, 7
0x18008d836  jnz     short loc_18008D83F
0x18008d838  mov     [rsi+0BF18h], r12d
0x18008d83f  cmp     [rsi+0BF1Ch], edi
0x18008d845  jnz     short loc_18008D854
0x18008d847  cmp     r15d, 5
0x18008d84b  jnz     short loc_18008D854
0x18008d84d  mov     [rsi+0BF1Ch], r12d
0x18008d854  cmp     [rsi+0BF20h], edi
0x18008d85a  jnz     short loc_18008D869
0x18008d85c  cmp     r15d, 4
0x18008d860  jnz     short loc_18008D869
0x18008d862  mov     [rsi+0BF20h], r12d
0x18008d869  lea     rcx, [rbp+57h+arg_10]
0x18008d86d  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18008d872  add     r15d, r12d
0x18008d875  cmp     r15d, 9
0x18008d879  jle     loc_18008D778
0x18008d87f  mov     rcx, [rsi+32F8h]
0x18008d886  mov     edx, 2
0x18008d88b  mov     rax, [rcx]
0x18008d88e  mov     rax, [rax+70h]
0x18008d892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d897  test    eax, eax
0x18008d899  jz      short loc_18008D8D3
0x18008d89b  mov     rcx, [rsi+32F8h]
0x18008d8a2  mov     edx, 3
0x18008d8a7  mov     rax, [rcx]
0x18008d8aa  mov     rax, [rax+70h]
0x18008d8ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d8b3  test    eax, eax
0x18008d8b5  jz      short loc_18008D8D3
0x18008d8b7  mov     rcx, [rsi+32F8h]
0x18008d8be  mov     edx, 7
0x18008d8c3  mov     rax, [rcx]
0x18008d8c6  mov     rax, [rax+70h]
0x18008d8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d8cf  test    eax, eax
0x18008d8d1  jnz     short loc_18008D8D6
0x18008d8d3  mov     r12d, edi
0x18008d8d6  mov     [rsi+0D0BCh], r12d
0x18008d8dd  mov     rcx, [rsi+32F8h]
0x18008d8e4  mov     rax, [rcx]
0x18008d8e7  mov     rax, [rax+48h]
0x18008d8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d8f0  test    eax, eax
0x18008d8f2  jz      loc_18008DB0D
0x18008d8f8  mov     rax, [rsi+0C128h]
0x18008d8ff  mov     [rbp+57h+arg_8], rax
0x18008d903  mov     [rbp+57h+arg_0], rdi
0x18008d907  jmp     loc_18008DAF3
0x18008d90c  mov     r9d, r14d; unsigned int
0x18008d90f  lea     rdx, aPipemanagererr_95; "PipeManagerError_ConfigProfileAddProces"...
0x18008d916  mov     r8d, 11F6h; char *
0x18008d91c  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18008d923  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008d928  mov     eax, cs:CallbackContext
0x18008d92e  cmp     eax, 2
0x18008d931  jbe     loc_18008DAB0
0x18008d937  lea     rax, aMSelectedproce; "m_selectedProcessor.Add failed"
0x18008d93e  mov     dword ptr [rbp+57h+arg_0], 11F7h
0x18008d945  mov     [rbp+57h+var_58], rax
0x18008d949  lea     rdx, byte_180279337
0x18008d950  lea     rax, aConfigureprofi_1; "ConfigureProfile"
0x18008d957  mov     [rbp+57h+var_60], rax
0x18008d95b  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008d962  mov     [rbp+57h+var_68], rax
0x18008d966  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008d96d  mov     [rbp+57h+var_50], rax
0x18008d971  lea     rax, [rbp+57h+var_58]
0x18008d975  mov     [rsp+0C0h+var_78], rax
0x18008d97a  lea     rax, [rbp+57h+var_60]
0x18008d97e  mov     [rsp+0C0h+var_80], rax
0x18008d983  lea     rax, [rbp+57h+arg_0]
0x18008d987  mov     [rsp+0C0h+var_88], rax
0x18008d98c  lea     rax, [rbp+57h+var_68]
0x18008d990  mov     [rsp+0C0h+var_90], rax
0x18008d995  lea     rax, [rbp+57h+arg_8]
0x18008d999  mov     [rsp+0C0h+var_98], rax
0x18008d99e  lea     rax, [rbp+57h+var_50]
0x18008d9a2  jmp     loc_18008DAA2
0x18008d9a7  mov     r9d, r14d; unsigned int
0x18008d9aa  lea     rdx, aPipemanagererr_70; "PipeManagerError_ConfigProfileSetConfig"...
0x18008d9b1  mov     r8d, 11F2h; char *
0x18008d9b7  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18008d9be  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008d9c3  mov     eax, cs:CallbackContext
0x18008d9c9  cmp     eax, 2
0x18008d9cc  jbe     loc_18008DAB0
0x18008d9d2  lea     rax, aSetconfigFaile; "SetConfig failed"
0x18008d9d9  mov     dword ptr [rbp+57h+arg_0], 11F3h
0x18008d9e0  mov     [rbp+57h+var_50], rax
0x18008d9e4  lea     rdx, byte_180279385
0x18008d9eb  lea     rax, aConfigureprofi_1; "ConfigureProfile"
0x18008d9f2  mov     [rbp+57h+var_58], rax
0x18008d9f6  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008d9fd  mov     [rbp+57h+var_60], rax
0x18008da01  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008da08  jmp     short loc_18008DA6D
0x18008da0a  mov     r14d, 8000FFFFh
0x18008da10  lea     rdx, aPipemanagererr_101; "PipeManagerError_ConfigProfileInconsist"...
0x18008da17  mov     r9d, r14d; unsigned int
0x18008da1a  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18008da21  mov     r8d, 11EEh; char *
0x18008da27  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008da2c  mov     eax, cs:CallbackContext
0x18008da32  cmp     eax, 2
0x18008da35  jbe     short loc_18008DAB0
0x18008da37  lea     rax, aInconsistentPr; "Inconsistent profile state"
0x18008da3e  mov     dword ptr [rbp+57h+arg_0], 11EFh
0x18008da45  mov     [rbp+57h+var_50], rax
0x18008da49  lea     rdx, byte_1802793D3
0x18008da50  lea     rax, aConfigureprofi_1; "ConfigureProfile"
0x18008da57  mov     [rbp+57h+var_58], rax
0x18008da5b  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008da62  mov     [rbp+57h+var_60], rax
0x18008da66  lea     rax, aErrorCondition; "Error condition failed"
0x18008da6d  mov     [rbp+57h+var_68], rax
0x18008da71  lea     rax, [rbp+57h+var_50]
0x18008da75  mov     [rsp+0C0h+var_78], rax
0x18008da7a  lea     rax, [rbp+57h+var_58]
0x18008da7e  mov     [rsp+0C0h+var_80], rax
0x18008da83  lea     rax, [rbp+57h+arg_0]
0x18008da87  mov     [rsp+0C0h+var_88], rax
0x18008da8c  lea     rax, [rbp+57h+var_60]
0x18008da90  mov     [rsp+0C0h+var_90], rax
0x18008da95  lea     rax, [rbp+57h+arg_8]
0x18008da99  mov     [rsp+0C0h+var_98], rax
0x18008da9e  lea     rax, [rbp+57h+var_68]
0x18008daa2  mov     dword ptr [rbp+57h+arg_8], r14d
0x18008daa6  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18008daab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008dab0  lea     rcx, [rbp+57h+arg_10]
0x18008dab4  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18008dab9  jmp     loc_18008DC03
0x18008dabe  mov     rdi, [rbp+57h+arg_0]
0x18008dac2  mov     rcx, [rdi+90h]; this
0x18008dac9  test    rcx, rcx
0x18008dacc  jz      short loc_18008DAD3
0x18008dace  call    ??_GPixelMap@@QEAAPEAXI@Z; PixelMap::`scalar deleting destructor'(uint)
0x18008dad3  lea     rcx, [rdi+0F8h]
0x18008dada  mov     [rdi+90h], rbx
0x18008dae1  xor     edx, edx
0x18008dae3  call    ??4?$TCntPtr@VMotionDetectionContext@@@@QEAAPEAVMotionDetectionContext@@PEAV1@@Z; TCntPtr<MotionDetectionContext>::operator=(MotionDetectionContext *)
0x18008dae8  xor     edx, edx
0x18008daea  lea     rcx, [rbp+57h+arg_0]
0x18008daee  call    ??4?$TCntPtr@VRdpSurface@@@@QEAAPEAVRdpSurface@@PEAV1@@Z; TCntPtr<RdpSurface>::operator=(RdpSurface *)
0x18008daf3  lea     r8, [rbp+57h+arg_0]
0x18008daf7  lea     rdx, [rbp+57h+arg_8]
0x18008dafb  call    ?GetNext@?$CComPtrList@VRdpSurface@@V?$ComPlainSmartPtr@VRdpSurface@@@@@@QEBAHAEAPEAXPEAPEAVRdpSurface@@@Z; CComPtrList<RdpSurface,ComPlainSmartPtr<RdpSurface>>::GetNext(void * &,RdpSurface * *)
0x18008db00  test    eax, eax
0x18008db02  jnz     short loc_18008DABE
0x18008db04  lea     rcx, [rbp+57h+arg_0]
0x18008db08  call    ?SafeRelease@?$TCntPtr@VClearCompressor@@@@AEAAXXZ; TCntPtr<ClearCompressor>::SafeRelease(void)
0x18008db0d  lea     rcx, [rsi+0BF00h]; this
0x18008db14  mov     [rbp+57h+arg_0], rcx
  ... truncated ...
```
