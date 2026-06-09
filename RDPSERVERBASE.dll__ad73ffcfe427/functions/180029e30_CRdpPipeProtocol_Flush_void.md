# CRdpPipeProtocol::Flush(void)

- ea: `0x180029e30`
- end: `0x18002a8f4`
- name: `?Flush@CRdpPipeProtocol@@UEAAJXZ`
- size: `2756`
- prototype: `__int64 __fastcall(CRdpPipeProtocol *__hidden this)`
- caller_count: `6`
- callee_count: `22`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002ada0`
- `0x18003b218`
- `0x18003b6f0`
- `0x1800d4840`
- `0x1800d4a20`
- `0x1800d4c50`

## callees

- `0x18000ce04`
- `0x18000ce34`
- `0x1800121cc`
- `0x180028644`
- `0x180028a30`
- `0x180029e30`
- `0x18002aafc`
- `0x18002b14c`
- `0x180049b9c`
- `0x18004d47c`
- `0x18004f5bc`
- `0x180076090`
- `0x180077aa0`
- `0x180079724`
- `0x180079770`
- `0x18007a1d4`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x1800894e4`
- `0x1800e0e78`
- `0x180158180`
- `0x18019c010`

## string_xrefs

- `0x18002a336`: `IID_IRdpPipeProtocol`
- `0x18002a3c4`: `IID_IRdpPipeProtocol`
- `0x18002a41a`: `IID_IRdpPipeProtocol`
- `0x18002a477`: `IID_IRdpPipeProtocol`
- `0x18002a4cd`: `IID_IRdpPipeProtocol`
- `0x18002a523`: `IID_IRdpPipeProtocol`
- `0x18002a5e2`: `IID_IRdpPipeProtocol`
- `0x18002a6c4`: `IID_IRdpPipeProtocol`
- `0x18002a77d`: `IID_IRdpPipeProtocol`
- `0x18002a8a1`: `IID_IRdpPipeProtocol`
- `0x18002a40d`: `BaseProtocolError_FlushGetReadPtrFail`
- `0x18002a32c`: `BaseProtocolError_FlushNullPointer`
- `0x18002a46a`: `BaseProtocolError_FlushGetWritePtrFail`
- `0x18002a5d5`: `BaseProtocolError_FlushGetWritePtrFail`
- `0x18002a4c0`: `BaseProtocolError_FlushCommitFail`
- `0x18002a516`: `BaseProtocolError_FlushBulkCompressFail`
- `0x18002a45b`: `Failed GetReadPtr on encoder buffer`
- `0x18002a61c`: `Failed GetWritePtr`
- `0x18002a6b7`: `BaseProtocolError_FlushRdpEncodeFIFOBufferCreateInstanceFail`
- `0x18002a770`: `BaseProtocolError_FlushCompressorBufferQueryInterfaceFail`
- `0x18002a55d`: `Failed to compress data `
- `0x18002a507`: `Failed to commit bytes to buffer `
- `0x18002a3b7`: `BaseProtocolError_FlushDVCWriteFail`
- `0x18002a3fe`: `Write on Graphics DVC failed!`
- `0x18002a894`: `BaseProtocolError_FlushDiscardFail`

## pseudocode

```c
__int64 __fastcall CRdpPipeProtocol::Flush(CRdpPipeProtocol *this)
{
  CTSCriticalSection *v1; // rbx
  __int64 v3; // r14
  __int64 v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rcx
  struct IRdpFIFOBuffer *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  int v11; // r15d
  struct IRdpFIFOBuffer *v12; // rcx
  signed int v14; // eax
  signed int v15; // eax
  struct IRDPPerfCounterGeneric *v16; // rcx
  bool v17; // zf
  unsigned int *v18; // rdx
  __int64 v19; // r8
  int v20; // eax
  struct IRDPPerfCounterGeneric *v21; // rcx
  struct IRDPPerfCounterGeneric *v22; // rcx
  signed int v23; // eax
  _QWORD *v24; // r15
  __int64 v25; // rcx
  __int64 v26; // rax
  void *v27; // rdx
  _DWORD *v28; // rbx
  signed int v29; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v31; // edx
  const char *v32; // rcx
  signed int v33; // eax
  int v34; // edx
  unsigned int v35; // r15d
  signed int v36; // eax
  int v37; // r15d
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  int v41; // [rsp+20h] [rbp-49h]
  unsigned int v42; // [rsp+20h] [rbp-49h]
  unsigned __int8 v43; // [rsp+28h] [rbp-41h]
  int v44; // [rsp+50h] [rbp-19h]
  CTSCriticalSection *v45; // [rsp+58h] [rbp-11h] BYREF
  struct IRdpFIFOBuffer *v46; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int8 v47[8]; // [rsp+68h] [rbp-1h] BYREF
  __int64 v48; // [rsp+70h] [rbp+7h] BYREF
  _QWORD v49[9]; // [rsp+78h] [rbp+Fh] BYREF
  unsigned int v50; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int v51; // [rsp+E0h] [rbp+77h] BYREF
  void *Block; // [rsp+E8h] [rbp+7Fh] BYREF

  v1 = (CRdpPipeProtocol *)((char *)this + 712);
  *(_QWORD *)v47 = 0;
  v51 = 0;
  v3 = 0;
  v4 = 0;
  v49[0] = 0;
  v46 = 0;
  v5 = 0;
  v48 = 0;
  v50 = 0;
  CTSCriticalSection::Lock((CRdpPipeProtocol *)((char *)this + 712));
  v6 = *((_QWORD *)this + 18);
  if ( v6 )
  {
    v3 = *((_QWORD *)this + 18);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  }
  v7 = *((_QWORD *)this + 19);
  if ( v7 )
  {
    v4 = *((_QWORD *)this + 19);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  }
  v8 = v46;
  if ( *((struct IRdpFIFOBuffer **)this + 22) != v46 )
  {
    v8 = (struct IRdpFIFOBuffer *)*((_QWORD *)this + 22);
    v46 = v8;
    if ( v8 )
    {
      (*(void (__fastcall **)(struct IRdpFIFOBuffer *))(*(_QWORD *)v8 + 8LL))(v8);
      v8 = v46;
    }
  }
  v9 = *((_QWORD *)this + 21);
  LODWORD(v45) = *((_DWORD *)this + 184);
  LODWORD(Block) = *((_DWORD *)this + 185);
  if ( v9 )
  {
    v5 = v9;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    v8 = v46;
  }
  v44 = *((_DWORD *)this + 189);
  if ( v1 )
  {
    CTSCriticalSection::UnLock(v1);
    v8 = v46;
  }
  if ( !v3 || !v8 || !v5 )
  {
    v11 = -2147418113;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_FlushNullPointer",
      (char *)0x845,
      0x8000FFFF,
      v41);
    goto LABEL_18;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v5 + 24LL))(v5, &v48, &v50);
  v11 = v10;
  if ( v10 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_FlushGetReadPtrFail",
      (char *)0x84A,
      v10,
      v41);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_18;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v31 = 110;
    v32 = "Failed GetReadPtr on encoder buffer";
    goto LABEL_99;
  }
  if ( !v50 )
  {
    v11 = 0;
    goto LABEL_18;
  }
  v14 = (*(__int64 (__fastcall **)(struct IRdpFIFOBuffer *, unsigned __int8 *, unsigned int *))(*(_QWORD *)v46 + 32LL))(
          v46,
          v47,
          &v51);
  v11 = v14;
  if ( v14 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_FlushGetWritePtrFail",
      (char *)0x858,
      v14,
      v41);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_18;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v31 = 111;
    goto LABEL_98;
  }
  if ( v51 < v50 + 1024 )
  {
    v34 = (int)Block;
    v35 = (_DWORD)Block + (_DWORD)v45;
    LODWORD(Block) = v35;
    if ( v50 + 1024 > v35 )
    {
      v35 = v34 + v50 + 1024;
      LODWORD(Block) = v35;
    }
    if ( v46 )
    {
      TCntPtr<IRdpVCMgr>::SafeRelease(&v46);
      v46 = 0;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v46);
    }
    v36 = RdpEncodeFIFOBuffer::CreateInstance(v35, &v46);
    v11 = v36;
    if ( v36 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
        "BaseProtocolError_FlushRdpEncodeFIFOBufferCreateInstanceFail",
        (char *)0x86B,
        v36,
        v41);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_18;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v31 = 112;
      v32 = "Failed RdpEncodeFIFOBuffer::CreatInstance";
      goto LABEL_99;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v37 = *((_DWORD *)this + 184);
      v38 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        &WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids,
        v38,
        v37,
        (_DWORD)Block);
    }
    v45 = v1;
    CTSCriticalSection::Lock(v1);
    if ( v46 != *((struct IRdpFIFOBuffer **)this + 22) )
    {
      TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 176);
      *((_QWORD *)this + 22) = v46;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 176);
    }
    *((_DWORD *)this + 184) = (_DWORD)Block;
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v45);
    v33 = (*(__int64 (__fastcall **)(struct IRdpFIFOBuffer *, unsigned __int8 *, unsigned int *))(*(_QWORD *)v46 + 32LL))(
            v46,
            v47,
            &v51);
    v11 = v33;
    if ( v33 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
        "BaseProtocolError_FlushGetWritePtrFail",
        (char *)0x878,
        v33,
        v41);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_18;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v31 = 114;
LABEL_98:
      v32 = "Failed GetWritePtr";
      goto LABEL_99;
    }
  }
  v15 = (**(__int64 (__fastcall ***)(struct IRdpFIFOBuffer *, GUID *, _QWORD *))v46)(v46, &IID_IUnknown, v49);
  v11 = v15;
  if ( v15 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_FlushCompressorBufferQueryInterfaceFail",
      (char *)0x87D,
      v15,
      v41);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_18;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v31 = 115;
    v32 = "QueryInterface(IID_Iunknown) failed!";
    goto LABEL_99;
  }
  v16 = (struct IRDPPerfCounterGeneric *)*((_QWORD *)this + 97);
  if ( v16 )
    PerfCounterSetRdpIntervalMarker(v16, *((_DWORD *)this + 22), 0);
  v17 = *((_DWORD *)this + 957) == 0;
  v18 = (unsigned int *)((char *)this + 3824);
  v19 = v50;
  Block = (char *)this + 3824;
  if ( v17 )
  {
    Block = (char *)this + 3824;
  }
  else
  {
    *v18 = 1;
    *((_DWORD *)this + 206) = 0;
    *((_DWORD *)this + 207) = v19;
    *((_DWORD *)this + 208) = 0;
  }
  v43 = v47[0];
  v42 = *v18;
  v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, char *))(**((_QWORD **)this + 102) + 48LL))(
          *((_QWORD *)this + 102),
          v48,
          v19,
          (char *)this + 824);
  v21 = (struct IRDPPerfCounterGeneric *)*((_QWORD *)this + 99);
  v11 = v20;
  if ( v21 )
    PerfCounterSetFrameBuffer(v21, *((_DWORD *)this + 22), *(unsigned __int64 *)v47, v50, 0, v43);
  v22 = (struct IRDPPerfCounterGeneric *)*((_QWORD *)this + 98);
  if ( v22 )
    PerfCounterSetRdpIntervalMarker(v22, *((_DWORD *)this + 22), 1u);
  if ( v11 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_FlushBulkCompressFail",
      (char *)0x8B2,
      v11,
      v42);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_18;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v31 = 116;
    v32 = "Failed to compress data ";
    goto LABEL_99;
  }
  v23 = (*(__int64 (__fastcall **)(struct IRdpFIFOBuffer *, _QWORD))(*(_QWORD *)v46 + 40LL))(v46, 0);
  v11 = v23;
  if ( v23 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_FlushCommitFail",
      (char *)0x8B6,
      v23,
      v42);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_18;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v31 = 117;
    v32 = "Failed to commit bytes to buffer ";
    goto LABEL_99;
  }
  CTSCriticalSection::Lock(v1);
  *((_DWORD *)this + 182) = *((_DWORD *)this + 182);
  if ( v1 )
    CTSCriticalSection::UnLock(v1);
  QueueEstimator::OnDataQueued((CRdpPipeProtocol *)((char *)this + 648), 0);
  if ( *((_DWORD *)this + 26) && v44 != -1 )
  {
    v24 = operator new(0x10u);
    if ( !v24 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v39 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          118,
          (unsigned int)&WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids,
          v39,
          (__int64)"GFXPIPE_FRAME_DETAILS");
      }
      v11 = -2147024882;
      goto LABEL_18;
    }
    *(_DWORD *)v24 = *((_DWORD *)this + 22);
    v24[1] = QueueEstimator::GetTotalBytesQueued((CRdpPipeProtocol *)((char *)this + 648));
    CTSCriticalSection::Lock(v1);
    if ( *((_DWORD *)this + 27) )
    {
      if ( *((_DWORD *)this + 160) > 0xAu )
      {
        v25 = *((_QWORD *)this + 78);
        if ( v25 )
        {
          v26 = *(_QWORD *)(v25 + 8);
          v27 = *(void **)v25;
          *((_QWORD *)this + 78) = v26;
          if ( v26 )
            *(_QWORD *)(v26 + 16) = 0;
          else
            *((_QWORD *)this + 79) = 0;
          *(_QWORD *)(v25 + 8) = *((_QWORD *)this + 25);
          *((_QWORD *)this + 25) = v25;
          --*((_DWORD *)this + 160);
          if ( v27 )
            operator delete(v27);
        }
      }
    }
    CVPtrList::AddTail((CRdpPipeProtocol *)((char *)this + 200), v24);
    if ( v1 )
      CTSCriticalSection::UnLock(v1);
  }
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v3 + 24LL))(
          v3,
          0,
          *(_QWORD *)v47,
          v49[0]);
  if ( v11 < 0 )
  {
    Block = 0;
    CTSCriticalSection::Lock(v1);
    *((_DWORD *)this + 182) = *((_DWORD *)this + 182);
    if ( *((_DWORD *)this + 26) && v44 != -1 )
    {
      CVPtrList::RemoveTail((CRdpPipeProtocol *)((char *)this + 200), &Block);
      *((_DWORD *)this + 26) = 0;
    }
    if ( v1 )
      CTSCriticalSection::UnLock(v1);
    if ( Block )
      operator delete(Block);
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_FlushDVCWriteFail",
      (char *)0x8F4,
      v11,
      v42);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_18;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v31 = 119;
    v32 = "Write on Graphics DVC failed!";
LABEL_99:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v31,
      (unsigned int)&WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v32,
      v11);
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v40 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids, v40, 0);
  }
  v28 = Block;
  if ( v4 )
  {
    v42 = v50;
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v4 + 72LL))(v4, *(_QWORD *)v47, 0, v48);
  }
  *((_DWORD *)this + 190) = *((_DWORD *)this + 190);
  *((_DWORD *)this + 192) += v50;
  ++*((_DWORD *)this + 191);
  *(_QWORD *)v47 = 0;
  *((_DWORD *)this + 26) = 0;
  v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 48LL))(v5);
  v11 = v29;
  if ( v29 >= 0 )
  {
    *((_DWORD *)this + 187) = 0;
    *v28 = 0;
    goto LABEL_18;
  }
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
    "BaseProtocolError_FlushDiscardFail",
    (char *)0x909,
    v29,
    v42);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v31 = 121;
    v32 = "Failed encoder buffer Discard!";
    goto LABEL_99;
  }
LABEL_18:
  if ( *(_QWORD *)v47 && v49[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v49[0] + 16LL))(v49[0]);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v12 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(struct IRdpFIFOBuffer *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180029e30  push    rbp
0x180029e32  push    rbx
0x180029e33  push    rsi
0x180029e34  push    rdi
0x180029e35  push    r12
0x180029e37  push    r13
0x180029e39  push    r14
0x180029e3b  push    r15
0x180029e3d  lea     rbp, [rsp-1Fh]
0x180029e42  sub     rsp, 88h
0x180029e49  xor     r15d, r15d
0x180029e4c  lea     rbx, [rcx+2C8h]
0x180029e53  mov     r13, rcx
0x180029e56  mov     qword ptr [rbp+57h+var_58], r15
0x180029e5a  mov     rcx, rbx; this
0x180029e5d  mov     [rbp+57h+arg_10], r15d
0x180029e61  mov     r14d, r15d
0x180029e64  mov     dword ptr [rbp+57h+arg_0], r15d
0x180029e68  mov     esi, r15d
0x180029e6b  mov     [rbp+57h+var_48], r15
0x180029e6f  mov     [rbp+57h+var_60], r15
0x180029e73  mov     edi, r15d
0x180029e76  mov     [rbp+57h+var_50], r15
0x180029e7a  mov     [rbp+57h+arg_8], r15d
0x180029e7e  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180029e83  mov     rcx, [r13+90h]
0x180029e8a  test    rcx, rcx
0x180029e8d  jz      short loc_180029E9E
0x180029e8f  mov     rax, [rcx]
0x180029e92  mov     r14, rcx
0x180029e95  mov     rax, [rax+8]
0x180029e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e9e  mov     rcx, [r13+98h]
0x180029ea5  test    rcx, rcx
0x180029ea8  jz      short loc_180029EB9
0x180029eaa  mov     rax, [rcx]
0x180029ead  mov     rsi, rcx
0x180029eb0  mov     rax, [rax+8]
0x180029eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029eb9  mov     rcx, [rbp+57h+var_60]
0x180029ebd  lea     r15, [r13+0B0h]
0x180029ec4  cmp     [r15], rcx
0x180029ec7  jz      short loc_180029EFA
0x180029ec9  test    rcx, rcx
0x180029ecc  jz      short loc_180029EDE
0x180029ece  mov     [rbp+57h+var_60], rdi
0x180029ed2  mov     rax, [rcx]
0x180029ed5  mov     rax, [rax+10h]
0x180029ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ede  mov     rcx, [r15]
0x180029ee1  mov     [rbp+57h+var_60], rcx
0x180029ee5  test    rcx, rcx
0x180029ee8  jz      short loc_180029EFA
0x180029eea  mov     rax, [rcx]
0x180029eed  mov     rax, [rax+8]
0x180029ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ef6  mov     rcx, [rbp+57h+var_60]
0x180029efa  mov     eax, [r13+2E0h]
0x180029f01  mov     rdx, [r13+0A8h]
0x180029f08  mov     dword ptr [rbp+57h+var_68], eax
0x180029f0b  mov     eax, [r13+2E4h]
0x180029f12  mov     dword ptr [rbp+57h+Block], eax
0x180029f15  test    rdx, rdx
0x180029f18  jz      short loc_180029F30
0x180029f1a  mov     rax, [rdx]
0x180029f1d  mov     rcx, rdx
0x180029f20  mov     rdi, rdx
0x180029f23  mov     rax, [rax+8]
0x180029f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f2c  mov     rcx, [rbp+57h+var_60]
0x180029f30  mov     eax, [r13+2F4h]
0x180029f37  mov     [rbp+57h+var_70], eax
0x180029f3a  test    rbx, rbx
0x180029f3d  jz      short loc_180029F4B
0x180029f3f  mov     rcx, rbx; this
0x180029f42  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x180029f47  mov     rcx, [rbp+57h+var_60]
0x180029f4b  test    r14, r14
0x180029f4e  jz      loc_18002A326
0x180029f54  test    rcx, rcx
0x180029f57  jz      loc_18002A326
0x180029f5d  test    rdi, rdi
0x180029f60  jz      loc_18002A326
0x180029f66  mov     rax, [rdi]
0x180029f69  lea     r8, [rbp+57h+arg_8]
0x180029f6d  lea     rdx, [rbp+57h+var_50]
0x180029f71  mov     rcx, rdi
0x180029f74  mov     rax, [rax+18h]
0x180029f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f7d  mov     r15d, eax
0x180029f80  test    eax, eax
0x180029f82  js      loc_18002A40A
0x180029f88  cmp     [rbp+57h+arg_8], 0
0x180029f8c  jnz     short loc_18002A00C
0x180029f8e  xor     r15d, r15d
0x180029f91  cmp     qword ptr [rbp+57h+var_58], 0
0x180029f96  jnz     loc_18002A8D6
0x180029f9c  test    rdi, rdi
0x180029f9f  jz      short loc_180029FB0
0x180029fa1  mov     rax, [rdi]
0x180029fa4  mov     rcx, rdi
0x180029fa7  mov     rax, [rax+10h]
0x180029fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fb0  mov     rcx, [rbp+57h+var_60]
0x180029fb4  test    rcx, rcx
0x180029fb7  jz      short loc_180029FCD
0x180029fb9  mov     [rbp+57h+var_60], 0
0x180029fc1  mov     rax, [rcx]
0x180029fc4  mov     rax, [rax+10h]
0x180029fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fcd  test    rsi, rsi
0x180029fd0  jz      short loc_180029FE1
0x180029fd2  mov     rax, [rsi]
0x180029fd5  mov     rcx, rsi
0x180029fd8  mov     rax, [rax+10h]
0x180029fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fe1  test    r14, r14
0x180029fe4  jz      short loc_180029FF5
0x180029fe6  mov     rax, [r14]
0x180029fe9  mov     rcx, r14
0x180029fec  mov     rax, [rax+10h]
0x180029ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ff5  mov     eax, r15d
0x180029ff8  add     rsp, 88h
0x180029fff  pop     r15
0x18002a001  pop     r14
0x18002a003  pop     r13
0x18002a005  pop     r12
0x18002a007  pop     rdi
0x18002a008  pop     rsi
0x18002a009  pop     rbx
0x18002a00a  pop     rbp
0x18002a00b  retn
0x18002a00c  mov     rcx, [rbp+57h+var_60]
0x18002a010  lea     r8, [rbp+57h+arg_10]
0x18002a014  lea     rdx, [rbp+57h+var_58]
0x18002a018  mov     rax, [rcx]
0x18002a01b  mov     rax, [rax+20h]
0x18002a01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a024  mov     r15d, eax
0x18002a027  test    eax, eax
0x18002a029  js      loc_18002A467
0x18002a02f  mov     ecx, [rbp+57h+arg_8]
0x18002a032  lea     r12, WPP_GLOBAL_Control
0x18002a039  lea     eax, [rcx+400h]
0x18002a03f  cmp     [rbp+57h+arg_10], eax
0x18002a042  jb      loc_18002A65F
0x18002a048  mov     rcx, [rbp+57h+var_60]
0x18002a04c  lea     r8, [rbp+57h+var_48]
0x18002a050  lea     rdx, IID_IUnknown
0x18002a057  mov     rax, [rcx]
0x18002a05a  mov     rax, [rax]
0x18002a05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a062  mov     r15d, eax
0x18002a065  test    eax, eax
0x18002a067  js      loc_18002A76D
0x18002a06d  mov     rcx, [r13+308h]; struct IRDPPerfCounterGeneric *
0x18002a074  test    rcx, rcx
0x18002a077  jz      short loc_18002A085
0x18002a079  mov     edx, [r13+58h]; unsigned int
0x18002a07d  xor     r8d, r8d; unsigned int
0x18002a080  call    ?PerfCounterSetRdpIntervalMarker@@YAJPEAUIRDPPerfCounterGeneric@@II@Z; PerfCounterSetRdpIntervalMarker(IRDPPerfCounterGeneric *,uint,uint)
0x18002a085  cmp     dword ptr [r13+0EF4h], 0
0x18002a08d  lea     rdx, [r13+0EF0h]
0x18002a094  mov     r8d, [rbp+57h+arg_8]
0x18002a098  lea     r11, [r13+338h]
0x18002a09f  mov     [rbp+57h+Block], rdx
0x18002a0a3  jnz     loc_18002A7C3
0x18002a0a9  mov     [rbp+57h+Block], rdx
0x18002a0ad  mov     r9d, [rbp+57h+arg_10]
0x18002a0b1  lea     r15, [rbp+57h+arg_0]
0x18002a0b5  mov     rcx, [r13+330h]
0x18002a0bc  mov     r10, qword ptr [rbp+57h+var_58]
0x18002a0c0  mov     [rsp+0C0h+var_88], r15
0x18002a0c5  mov     [rsp+0C0h+var_90], r9d
0x18002a0ca  mov     r9d, [rdx]
0x18002a0cd  mov     rax, [rcx]
0x18002a0d0  mov     rdx, [rbp+57h+var_50]
0x18002a0d4  mov     qword ptr [rsp+0C0h+var_98], r10; unsigned __int8
0x18002a0d9  mov     dword ptr [rsp+0C0h+var_A0], r9d
0x18002a0de  mov     r9, r11
0x18002a0e1  mov     rax, [rax+30h]
0x18002a0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0ea  mov     rcx, [r13+318h]; struct IRDPPerfCounterGeneric *
0x18002a0f1  mov     r15d, eax
0x18002a0f4  test    rcx, rcx
0x18002a0f7  jz      short loc_18002A111
0x18002a0f9  mov     eax, dword ptr [rbp+57h+arg_0]
0x18002a0fc  mov     r9d, [rbp+57h+arg_8]; unsigned int
0x18002a100  mov     r8, qword ptr [rbp+57h+var_58]; unsigned __int64
0x18002a104  mov     edx, [r13+58h]; unsigned int
0x18002a108  mov     dword ptr [rsp+0C0h+var_A0], eax; int
0x18002a10c  call    ?PerfCounterSetFrameBuffer@@YAJPEAUIRDPPerfCounterGeneric@@I_KIIE@Z; PerfCounterSetFrameBuffer(IRDPPerfCounterGeneric *,uint,unsigned __int64,uint,uint,uchar)
0x18002a111  mov     rcx, [r13+310h]; struct IRDPPerfCounterGeneric *
0x18002a118  test    rcx, rcx
0x18002a11b  jnz     loc_18002A312
0x18002a121  test    r15d, r15d
0x18002a124  js      loc_18002A513
0x18002a12a  mov     rcx, [rbp+57h+var_60]
0x18002a12e  mov     edx, dword ptr [rbp+57h+arg_0]
0x18002a131  mov     rax, [rcx]
0x18002a134  mov     rax, [rax+28h]
0x18002a138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a13d  mov     r15d, eax
0x18002a140  test    eax, eax
0x18002a142  js      loc_18002A4BD
0x18002a148  mov     rcx, rbx; this
0x18002a14b  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18002a150  mov     edx, dword ptr [rbp+57h+arg_0]
0x18002a153  add     [r13+2D8h], edx
0x18002a15a  test    rbx, rbx
0x18002a15d  jz      short loc_18002A16A
0x18002a15f  mov     rcx, rbx; this
0x18002a162  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18002a167  mov     edx, dword ptr [rbp+57h+arg_0]; unsigned int
0x18002a16a  lea     rcx, [r13+288h]; this
0x18002a171  call    ?OnDataQueued@QueueEstimator@@QEAAXK@Z; QueueEstimator::OnDataQueued(ulong)
0x18002a176  cmp     dword ptr [r13+68h], 0
0x18002a17b  jz      loc_18002A23C
0x18002a181  cmp     [rbp+57h+var_70], 0FFFFFFFFh
0x18002a185  jz      loc_18002A23C
0x18002a18b  mov     ecx, 10h; Size
0x18002a190  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a195  mov     r15, rax
0x18002a198  test    rax, rax
0x18002a19b  jz      loc_18002A359
0x18002a1a1  mov     eax, [r13+58h]
0x18002a1a5  lea     rcx, [r13+288h]; this
0x18002a1ac  mov     [r15], eax
0x18002a1af  call    ?GetTotalBytesQueued@QueueEstimator@@QEAA_KXZ; QueueEstimator::GetTotalBytesQueued(void)
0x18002a1b4  mov     rcx, rbx; this
0x18002a1b7  mov     [r15+8], rax
0x18002a1bb  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18002a1c0  xor     r8d, r8d
0x18002a1c3  cmp     [r13+6Ch], r8d
0x18002a1c7  jz      short loc_18002A220
0x18002a1c9  cmp     dword ptr [r13+280h], 0Ah
0x18002a1d1  jbe     short loc_18002A220
0x18002a1d3  mov     rcx, [r13+270h]
0x18002a1da  test    rcx, rcx
0x18002a1dd  jz      short loc_18002A220
0x18002a1df  mov     rax, [rcx+8]
0x18002a1e3  mov     rdx, [rcx]
0x18002a1e6  mov     [r13+270h], rax
0x18002a1ed  test    rax, rax
0x18002a1f0  jz      loc_18002A34D
0x18002a1f6  mov     [rax+10h], r8
0x18002a1fa  mov     rax, [r13+0C8h]
0x18002a201  mov     [rcx+8], rax
0x18002a205  mov     [r13+0C8h], rcx
0x18002a20c  dec     dword ptr [r13+280h]
0x18002a213  test    rdx, rdx
0x18002a216  jz      short loc_18002A220
0x18002a218  mov     rcx, rdx; Block
0x18002a21b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a220  lea     rcx, [r13+0C8h]; this
0x18002a227  mov     rdx, r15; void *
0x18002a22a  call    ?AddTail@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddTail(void *)
0x18002a22f  test    rbx, rbx
0x18002a232  jz      short loc_18002A23C
0x18002a234  mov     rcx, rbx; this
0x18002a237  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18002a23c  mov     rax, [r14]
0x18002a23f  mov     rcx, r14
0x18002a242  mov     r9, [rbp+57h+var_48]
0x18002a246  mov     r8, qword ptr [rbp+57h+var_58]
0x18002a24a  mov     edx, dword ptr [rbp+57h+arg_0]
0x18002a24d  mov     rax, [rax+18h]
0x18002a251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a256  mov     r15d, eax
0x18002a259  test    eax, eax
0x18002a25b  js      loc_18002A374
0x18002a261  mov     rax, cs:WPP_GLOBAL_Control
0x18002a268  cmp     rax, r12
0x18002a26b  jz      short loc_18002A27A
0x18002a26d  test    dword ptr [rax+1Ch], 100h
0x18002a274  jnz     loc_18002A857
0x18002a27a  mov     rbx, [rbp+57h+Block]
0x18002a27e  test    rsi, rsi
0x18002a281  jz      short loc_18002A2B7
0x18002a283  mov     ecx, [rbx]
0x18002a285  mov     rax, [rsi]
0x18002a288  mov     r9, [rbp+57h+var_50]
0x18002a28c  mov     r8d, dword ptr [rbp+57h+arg_0]
0x18002a290  mov     rdx, qword ptr [rbp+57h+var_58]
0x18002a294  mov     rax, [rax+48h]
0x18002a298  mov     [rsp+0C0h+var_90], ecx
0x18002a29c  lea     rcx, [r13+338h]
0x18002a2a3  mov     qword ptr [rsp+0C0h+var_98], rcx
0x18002a2a8  mov     ecx, [rbp+57h+arg_8]
0x18002a2ab  mov     dword ptr [rsp+0C0h+var_A0], ecx; int
0x18002a2af  mov     rcx, rsi
0x18002a2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2b7  mov     eax, dword ptr [rbp+57h+arg_0]
0x18002a2ba  mov     rcx, rdi
0x18002a2bd  add     [r13+2F8h], eax
0x18002a2c4  mov     edx, [rbp+57h+arg_8]
0x18002a2c7  add     [r13+300h], edx
0x18002a2ce  inc     dword ptr [r13+2FCh]
0x18002a2d5  mov     qword ptr [rbp+57h+var_58], 0
  ... truncated ...
```
