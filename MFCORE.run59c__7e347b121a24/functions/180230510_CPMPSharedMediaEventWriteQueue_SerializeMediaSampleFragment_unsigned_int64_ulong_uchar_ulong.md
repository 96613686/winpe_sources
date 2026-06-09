# CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment(unsigned __int64,ulong,uchar *,ulong)

- ea: `0x180230510`
- end: `0x180230e98`
- name: `?SerializeMediaSampleFragment@CPMPSharedMediaEventWriteQueue@@IEAAJ_KKPEAEK@Z`
- size: `2440`
- prototype: `__int64 __fastcall(CPMPSharedMediaEventWriteQueue *__hidden this, unsigned __int64, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1800dfc90`

## callees

- `0x18002fee0`
- `0x18003367c`
- `0x180033838`
- `0x1800338bc`
- `0x180033e20`
- `0x1800341dc`
- `0x180034a6c`
- `0x180034b34`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x18005a3d4`
- `0x180063f00`
- `0x1800ec0e0`
- `0x1801128dc`
- `0x180112910`
- `0x18012649c`
- `0x18012cfd0`
- `0x180230510`
- `0x180258480`
- `0x180344c60`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230608`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802306b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230766`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230810`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802308c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802309a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230a58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230b24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230c1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230ccf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230da7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230608`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802306b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230766`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230810`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802308c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802309a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230a58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230b24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230c1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230ccf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180230da7`
- `MFPlat!MFCreateMediaEvent` at `0x1802305e6`
- `MFPlat!MFCreateMediaEvent` at `0x1802305e6`

## string_xrefs

- `0x18023057d`: `CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment`
- `0x18023091e`: `CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment`
- `0x180230a07`: `CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment`
- `0x180230ab6`: `CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment`
- `0x180230b82`: `CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment`
- `0x180230c7b`: `CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment`
- `0x180230d2d`: `CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment`
- `0x180230e05`: `CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment`

## pseudocode

```c
__int64 __fastcall CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment(
        CPMPSharedMediaEventWriteQueue *this,
        __int64 a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5)
{
  __int64 v9; // rdx
  HRESULT v10; // ebx
  __int64 v11; // r8
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  unsigned int v26; // ecx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  unsigned int v31; // esi
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  unsigned int v35; // eax
  unsigned int v36; // eax
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  _BYTE v67[8]; // [rsp+30h] [rbp-D0h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 *v69; // [rsp+40h] [rbp-C0h] BYREF
  void **v70; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v71[64]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v72[3]; // [rsp+258h] [rbp+158h] BYREF
  _QWORD v73[65]; // [rsp+270h] [rbp+170h] BYREF
  _QWORD v74[2]; // [rsp+478h] [rbp+378h] BYREF
  unsigned int v75; // [rsp+48Ch] [rbp+38Ch]
  char *v76; // [rsp+490h] [rbp+390h] BYREF
  int v77; // [rsp+498h] [rbp+398h]
  char v78; // [rsp+4A0h] [rbp+3A0h] BYREF
  int v79; // [rsp+1CA0h] [rbp+1BA0h]

  ppEvent = 0;
  v69 = 0;
  CBufferWriter::CBufferWriter((CBufferWriter *)v73);
  v77 = 0;
  v73[0] = &CDynamicBufferWriter::`vftable'{for `CDefaultIStreamImpl'};
  v79 = 256;
  v73[1] = &CBufferWriter::`vftable'{for `CPersistStreamMap'};
  v74[0] = &CDynamicBufferWriterWithReferenceStore::`vftable'{for `CBinaryWriter'};
  v76 = &v78;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v67,
    "CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment",
    529);
  v10 = MFCreateMediaEvent(2u, &s_PMPMsgQueue_FragmentedSample_Buffer, 0, 0, &ppEvent);
  if ( v10 < 0 )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment",
          529,
          v10);
    }
    if ( g_wppLevels )
    {
      v15 = 47;
LABEL_130:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids, this, v10);
      goto LABEL_131;
    }
    goto LABEL_131;
  }
  v10 = CBinaryWriter::WriteInt64((CBinaryWriter *)v74, a2);
  if ( v10 >= 0 )
  {
    v10 = CEventBinaryWriter::Serialize(v73, ppEvent, 1);
    if ( v10 < 0 )
    {
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != v10 )
          CallStackContext::TraceFailure(v25, "CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment", 536, v10);
      }
      if ( g_wppLevels )
      {
        v15 = 49;
        goto LABEL_130;
      }
      goto LABEL_131;
    }
    v26 = v75 + 4;
    if ( v75 + 4 < v75 )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      v10 = -2147024362;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != -2147024362 )
          CallStackContext::TraceFailure(
            v29,
            "CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment",
            541,
            -2147024362);
      }
      if ( !g_wppLevels )
        goto LABEL_131;
      v30 = 50;
      goto LABEL_45;
    }
    v31 = v26 + a5;
    if ( v26 + a5 < v26 )
    {
      v32 = (__int64 *)CallStackTracing::s_wpInstance;
      v10 = -2147024362;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
        CallStackTracing::s_wpInstance = v33;
        if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v32 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
        if ( *((_DWORD *)v34 + 499) != -2147024362 )
          CallStackContext::TraceFailure(
            v34,
            "CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment",
            543,
            -2147024362);
      }
      if ( !g_wppLevels )
        goto LABEL_131;
      v30 = 51;
LABEL_45:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v30,
        &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids,
        this,
        -2147024362);
      goto LABEL_131;
    }
    v35 = *((_DWORD *)this + 4);
    if ( v35 <= 0x28 )
      v36 = 2097148;
    else
      v36 = v35 - 40;
    if ( v31 > v36 )
    {
      if ( byte_1803CECEC )
        WPP_SF_qDD(
          *((_QWORD *)WPP_GLOBAL_Control + 22),
          52,
          &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids,
          this,
          a3,
          v26 + a5);
      v37 = (__int64 *)CallStackTracing::s_wpInstance;
      v10 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
        CallStackTracing::s_wpInstance = v38;
        if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
        {
          v37 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v37 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
        if ( *((_DWORD *)v39 + 499) != -1072875845 )
          CallStackContext::TraceFailure(
            v39,
            "CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment",
            552,
            -1072875845);
      }
      if ( g_wppLevels )
      {
        v15 = 53;
        goto LABEL_130;
      }
      goto LABEL_131;
    }
    v10 = CSharedMsgWriteQueue::AllocData(this, v31, &v69);
    if ( v10 < 0 )
    {
      v42 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41);
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v42 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v42 + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
        if ( *((_DWORD *)v44 + 499) != v10 )
          CallStackContext::TraceFailure(v44, "CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment", 556, v10);
      }
      if ( g_wppLevels )
      {
        v15 = 54;
        goto LABEL_130;
      }
      goto LABEL_131;
    }
    CFixedBufferWriter::CFixedBufferWriter((CFixedBufferWriter *)&v70, v69, v31);
    v10 = CFixedBufferWriter::WriteBlock((CFixedBufferWriter *)v72, (const void *)v74[1], v75);
    if ( v10 >= 0 )
    {
      v10 = CBinaryWriter::WriteBool((CBinaryWriter *)v72, a3);
      if ( v10 >= 0 )
      {
        v10 = CFixedBufferWriter::WriteBlock((CFixedBufferWriter *)v72, a4, a5);
        if ( v10 >= 0 )
        {
          v70 = &CBufferWriter::`vftable'{for `CDefaultIStreamImpl'};
          v71[0] = &CBufferWriter::`vftable'{for `CPersistStreamMap'};
          v72[0] = &CBufferWriter::`vftable'{for `CBinaryWriter'};
          CPersistStreamMap::~CPersistStreamMap((CPersistStreamMap *)v71);
          v10 = CSharedMsgWriteQueue::WriteMsg(this);
          if ( v10 < 0 )
          {
            v63 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v61, v62);
              CallStackTracing::s_wpInstance = v64;
              if ( v64
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
              {
                v63 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v63 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v63 + 8) )
            {
              v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
              if ( *((_DWORD *)v65 + 499) != v10 )
                CallStackContext::TraceFailure(
                  v65,
                  "CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment",
                  567,
                  v10);
            }
            if ( g_wppLevels )
            {
              v15 = 58;
              goto LABEL_130;
            }
          }
          goto LABEL_131;
        }
        v58 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56, v57);
          CallStackTracing::s_wpInstance = v59;
          if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
          {
            v58 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v58 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v58 + 8) )
        {
          v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
          if ( *((_DWORD *)v60 + 499) != v10 )
            CallStackContext::TraceFailure(
              v60,
              "CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment",
              563,
              v10);
        }
        if ( !g_wppLevels )
        {
LABEL_96:
          v70 = &CBufferWriter::`vftable'{for `CDefaultIStreamImpl'};
          v71[0] = &CBufferWriter::`vftable'{for `CPersistStreamMap'};
          v72[0] = &CBufferWriter::`vftable'{for `CBinaryWriter'};
          CPersistStreamMap::~CPersistStreamMap((CPersistStreamMap *)v71);
          goto LABEL_131;
        }
        v50 = 57;
      }
      else
      {
        v53 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52);
          CallStackTracing::s_wpInstance = v54;
          if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
          {
            v53 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v53 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v53 + 8) )
        {
          v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
          if ( *((_DWORD *)v55 + 499) != v10 )
            CallStackContext::TraceFailure(
              v55,
              "CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment",
              562,
              v10);
        }
        if ( !g_wppLevels )
          goto LABEL_96;
        v50 = 56;
      }
    }
    else
    {
      v47 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46);
        CallStackTracing::s_wpInstance = v48;
        if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
        {
          v47 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v47 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v47 + 8) )
      {
        v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
        if ( *((_DWORD *)v49 + 499) != v10 )
          CallStackContext::TraceFailure(v49, "CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment", 561, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_96;
      v50 = 55;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v50, &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids, this, v10);
    goto LABEL_96;
  }
  v18 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
    CallStackTracing::s_wpInstance = v19;
    if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v18 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
    if ( *((_DWORD *)v20 + 499) != v10 )
      CallStackContext::TraceFailure(v20, "CPMPSharedMediaEventWriteQueue::SerializeMediaSampleFragment", 534, v10);
  }
  if ( g_wppLevels )
  {
    v15 = 48;
    goto LABEL_130;
  }
LABEL_131:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v67);
  CStackAllocT<CPMPSharedMediaEventWriteQueue::BufRef,256>::FreeHeapAllocation(&v76);
  CDynamicBufferWriter::~CDynamicBufferWriter((CDynamicBufferWriter *)v73);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppEvent);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180230510  push    rbp
0x180230512  push    rbx
0x180230513  push    rsi
0x180230514  push    rdi
0x180230515  push    r12
0x180230517  push    r13
0x180230519  push    r14
0x18023051b  push    r15
0x18023051d  lea     rbp, [rsp-1BC8h]
0x180230525  mov     eax, 1CC8h
0x18023052a  call    _alloca_probe
0x18023052f  sub     rsp, rax
0x180230532  mov     rax, cs:__security_cookie
0x180230539  xor     rax, rsp
0x18023053c  mov     [rbp+1C00h+var_50], rax
0x180230543  mov     rdi, rcx
0x180230546  xor     r13d, r13d
0x180230549  lea     rcx, [rbp+1C00h+var_1A90]; this
0x180230550  mov     [rsp+1D00h+var_1CC8], r13
0x180230555  mov     [rsp+1D00h+var_1CC0], r13
0x18023055a  mov     r12, r9
0x18023055d  mov     r15d, r8d
0x180230560  mov     rsi, rdx
0x180230563  call    ??0CBufferWriter@@QEAA@XZ; CBufferWriter::CBufferWriter(void)
0x180230568  lea     rax, ??_7CDynamicBufferWriter@@6BCDefaultIStreamImpl@@@; const CDynamicBufferWriter::`vftable'{for `CDefaultIStreamImpl'}
0x18023056f  mov     [rbp+1C00h+var_1868], r13d
0x180230576  mov     [rbp+1C00h+var_1A90], rax
0x18023057d  lea     r14, aCpmpsharedmedi; "CPMPSharedMediaEventWriteQueue::Seriali"...
0x180230584  lea     rax, ??_7CBufferWriter@@6BCPersistStreamMap@@@; const CBufferWriter::`vftable'{for `CPersistStreamMap'}
0x18023058b  mov     [rbp+1C00h+var_60], 100h
0x180230595  mov     [rbp+1C00h+var_1A88], rax
0x18023059c  lea     rcx, [rsp+1D00h+var_1CD0]; this
0x1802305a1  lea     rax, ??_7CDynamicBufferWriterWithReferenceStore@@6BCBinaryWriter@@@; const CDynamicBufferWriterWithReferenceStore::`vftable'{for `CBinaryWriter'}
0x1802305a8  mov     r8d, 211h; int
0x1802305ae  mov     [rbp+1C00h+var_1888], rax
0x1802305b5  mov     rdx, r14; char *
0x1802305b8  lea     rax, [rbp+1C00h+var_1860]
0x1802305bf  mov     [rbp+1C00h+var_1870], rax
0x1802305c6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802305cb  lea     rax, [rsp+1D00h+var_1CC8]
0x1802305d0  xor     r9d, r9d; pvValue
0x1802305d3  xor     r8d, r8d; hrStatus
0x1802305d6  mov     [rsp+1D00h+ppEvent], rax; ppEvent
0x1802305db  lea     rdx, s_PMPMsgQueue_FragmentedSample_Buffer; guidExtendedType
0x1802305e2  lea     ecx, [r13+2]; met
0x1802305e6  call    cs:__imp_MFCreateMediaEvent
0x1802305ed  nop     dword ptr [rax+rax+00h]
0x1802305f2  mov     ebx, eax
0x1802305f4  test    eax, eax
0x1802305f6  jns     loc_18023068E
0x1802305fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180230603  test    rcx, rcx
0x180230606  jnz     short loc_180230650
0x180230608  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18023060f  nop     dword ptr [rax+rax+00h]
0x180230614  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18023061b  mov     rcx, rax
0x18023061e  test    rax, rax
0x180230621  jz      short loc_180230642
0x180230623  mov     rax, [rax]
0x180230626  mov     edx, 7F0h
0x18023062b  mov     rax, [rax+8]
0x18023062f  call    cs:__guard_dispatch_icall_fptr
0x180230635  test    eax, eax
0x180230637  jz      short loc_180230642
0x180230639  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180230640  jmp     short loc_180230650
0x180230642  lea     rcx, qword_1803CE250; this
0x180230649  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180230650  cmp     [rcx+8], r13b
0x180230654  jz      short loc_180230677
0x180230656  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18023065b  cmp     [rax+7CCh], ebx
0x180230661  jz      short loc_180230677
0x180230663  mov     r9d, ebx; int
0x180230666  mov     r8d, 211h; int
0x18023066c  mov     rdx, r14; char *
0x18023066f  mov     rcx, rax; this
0x180230672  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180230677  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18023067e  jb      loc_180230E46
0x180230684  mov     edx, 2Fh ; '/'
0x180230689  jmp     loc_180230E28
0x18023068e  mov     rdx, rsi; __int64
0x180230691  lea     rcx, [rbp+1C00h+var_1888]; this
0x180230698  call    ?WriteInt64@CBinaryWriter@@QEAAJ_J@Z; CBinaryWriter::WriteInt64(__int64)
0x18023069d  mov     ebx, eax
0x18023069f  test    eax, eax
0x1802306a1  jns     loc_180230739
0x1802306a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802306ae  test    rcx, rcx
0x1802306b1  jnz     short loc_1802306FB
0x1802306b3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802306ba  nop     dword ptr [rax+rax+00h]
0x1802306bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802306c6  mov     rcx, rax
0x1802306c9  test    rax, rax
0x1802306cc  jz      short loc_1802306ED
0x1802306ce  mov     rax, [rax]
0x1802306d1  mov     edx, 7F0h
0x1802306d6  mov     rax, [rax+8]
0x1802306da  call    cs:__guard_dispatch_icall_fptr
0x1802306e0  test    eax, eax
0x1802306e2  jz      short loc_1802306ED
0x1802306e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802306eb  jmp     short loc_1802306FB
0x1802306ed  lea     rcx, qword_1803CE250; this
0x1802306f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802306fb  cmp     [rcx+8], r13b
0x1802306ff  jz      short loc_180230722
0x180230701  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180230706  cmp     [rax+7CCh], ebx
0x18023070c  jz      short loc_180230722
0x18023070e  mov     r9d, ebx; int
0x180230711  mov     r8d, 216h; int
0x180230717  mov     rdx, r14; char *
0x18023071a  mov     rcx, rax; this
0x18023071d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180230722  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180230729  jb      loc_180230E46
0x18023072f  mov     edx, 30h ; '0'
0x180230734  jmp     loc_180230E28
0x180230739  mov     rdx, [rsp+1D00h+var_1CC8]
0x18023073e  lea     rcx, [rbp+1C00h+var_1A90]
0x180230745  mov     r8d, 1
0x18023074b  call    ?Serialize@CEventBinaryWriter@@QEAAJPEAUIMFMediaEvent@@W4VALUE_SERIALIZATION_TYPE@CEventBinaryTypes@@@Z; CEventBinaryWriter::Serialize(IMFMediaEvent *,CEventBinaryTypes::VALUE_SERIALIZATION_TYPE)
0x180230750  mov     ebx, eax
0x180230752  test    eax, eax
0x180230754  jns     loc_1802307EC
0x18023075a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180230761  test    rcx, rcx
0x180230764  jnz     short loc_1802307AE
0x180230766  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18023076d  nop     dword ptr [rax+rax+00h]
0x180230772  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180230779  mov     rcx, rax
0x18023077c  test    rax, rax
0x18023077f  jz      short loc_1802307A0
0x180230781  mov     rax, [rax]
0x180230784  mov     edx, 7F0h
0x180230789  mov     rax, [rax+8]
0x18023078d  call    cs:__guard_dispatch_icall_fptr
0x180230793  test    eax, eax
0x180230795  jz      short loc_1802307A0
0x180230797  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18023079e  jmp     short loc_1802307AE
0x1802307a0  lea     rcx, qword_1803CE250; this
0x1802307a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802307ae  cmp     [rcx+8], r13b
0x1802307b2  jz      short loc_1802307D5
0x1802307b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802307b9  cmp     [rax+7CCh], ebx
0x1802307bf  jz      short loc_1802307D5
0x1802307c1  mov     r9d, ebx; int
0x1802307c4  mov     r8d, 218h; int
0x1802307ca  mov     rdx, r14; char *
0x1802307cd  mov     rcx, rax; this
0x1802307d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802307d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802307dc  jb      loc_180230E46
0x1802307e2  mov     edx, 31h ; '1'
0x1802307e7  jmp     loc_180230E28
0x1802307ec  mov     eax, [rbp+1C00h+var_1874]
0x1802307f2  lea     ecx, [rax+4]
0x1802307f5  cmp     ecx, eax
0x1802307f7  jnb     loc_18023089A
0x1802307fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180230804  mov     esi, 80070216h
0x180230809  mov     ebx, esi
0x18023080b  test    rcx, rcx
0x18023080e  jnz     short loc_180230858
0x180230810  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180230817  nop     dword ptr [rax+rax+00h]
0x18023081c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180230823  mov     rcx, rax
0x180230826  test    rax, rax
0x180230829  jz      short loc_18023084A
0x18023082b  mov     rax, [rax]
0x18023082e  mov     edx, 7F0h
0x180230833  mov     rax, [rax+8]
0x180230837  call    cs:__guard_dispatch_icall_fptr
0x18023083d  test    eax, eax
0x18023083f  jz      short loc_18023084A
0x180230841  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180230848  jmp     short loc_180230858
0x18023084a  lea     rcx, qword_1803CE250; this
0x180230851  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180230858  cmp     [rcx+8], r13b
0x18023085c  jz      short loc_18023087F
0x18023085e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180230863  cmp     [rax+7CCh], esi
0x180230869  jz      short loc_18023087F
0x18023086b  mov     r9d, esi; int
0x18023086e  mov     r8d, 21Dh; int
0x180230874  mov     rdx, r14; char *
0x180230877  mov     rcx, rax; this
0x18023087a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18023087f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180230886  jb      loc_180230E46
0x18023088c  mov     edx, 32h ; '2'
0x180230891  mov     dword ptr [rsp+1D00h+ppEvent], esi
0x180230895  jmp     loc_180230E2C
0x18023089a  mov     r14d, [rbp+1C00h+arg_20]
0x1802308a1  lea     esi, [rcx+r14]
0x1802308a5  cmp     esi, ecx
0x1802308a7  jnb     loc_18023094A
0x1802308ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802308b4  mov     esi, 80070216h
0x1802308b9  mov     ebx, esi
0x1802308bb  test    rcx, rcx
0x1802308be  jnz     short loc_180230908
0x1802308c0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802308c7  nop     dword ptr [rax+rax+00h]
0x1802308cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802308d3  mov     rcx, rax
0x1802308d6  test    rax, rax
0x1802308d9  jz      short loc_1802308FA
0x1802308db  mov     rax, [rax]
0x1802308de  mov     edx, 7F0h
0x1802308e3  mov     rax, [rax+8]
0x1802308e7  call    cs:__guard_dispatch_icall_fptr
0x1802308ed  test    eax, eax
0x1802308ef  jz      short loc_1802308FA
0x1802308f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802308f8  jmp     short loc_180230908
0x1802308fa  lea     rcx, qword_1803CE250; this
0x180230901  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180230908  cmp     [rcx+8], r13b
0x18023090c  jz      short loc_180230933
0x18023090e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180230913  cmp     [rax+7CCh], esi
0x180230919  jz      short loc_180230933
0x18023091b  mov     r9d, esi; int
0x18023091e  lea     rdx, aCpmpsharedmedi; "CPMPSharedMediaEventWriteQueue::Seriali"...
0x180230925  mov     r8d, 21Fh; int
0x18023092b  mov     rcx, rax; this
0x18023092e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180230933  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18023093a  jb      loc_180230E46
0x180230940  mov     edx, 33h ; '3'
0x180230945  jmp     loc_180230891
0x18023094a  mov     eax, [rdi+10h]
0x18023094d  cmp     eax, 28h ; '('
0x180230950  jbe     short loc_180230957
0x180230952  add     eax, 0FFFFFFD8h
0x180230955  jmp     short loc_18023095C
0x180230957  mov     eax, 1FFFFCh
0x18023095c  cmp     esi, eax
0x18023095e  jbe     loc_180230A33
0x180230964  cmp     cs:byte_1803CECEC, 1
0x18023096b  jb      short loc_180230998
0x18023096d  mov     rcx, cs:WPP_GLOBAL_Control
0x180230974  lea     r8, WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids
0x18023097b  mov     edx, 34h ; '4'
0x180230980  mov     [rsp+1D00h+var_1CD8], esi
0x180230984  mov     r9, rdi
0x180230987  mov     dword ptr [rsp+1D00h+ppEvent], r15d
0x18023098c  mov     rcx, [rcx+0B0h]
0x180230993  call    WPP_SF_qDD
0x180230998  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18023099f  mov     ebx, 0C00D36BBh
0x1802309a4  test    rcx, rcx
0x1802309a7  jnz     short loc_1802309F1
0x1802309a9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802309b0  nop     dword ptr [rax+rax+00h]
0x1802309b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802309bc  mov     rcx, rax
0x1802309bf  test    rax, rax
0x1802309c2  jz      short loc_1802309E3
0x1802309c4  mov     rax, [rax]
0x1802309c7  mov     edx, 7F0h
0x1802309cc  mov     rax, [rax+8]
0x1802309d0  call    cs:__guard_dispatch_icall_fptr
0x1802309d6  test    eax, eax
0x1802309d8  jz      short loc_1802309E3
0x1802309da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802309e1  jmp     short loc_1802309F1
0x1802309e3  lea     rcx, qword_1803CE250; this
0x1802309ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802309f1  cmp     [rcx+8], r13b
0x1802309f5  jz      short loc_180230A1C
0x1802309f7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802309fc  cmp     [rax+7CCh], ebx
0x180230a02  jz      short loc_180230A1C
0x180230a04  mov     r9d, ebx; int
0x180230a07  lea     rdx, aCpmpsharedmedi; "CPMPSharedMediaEventWriteQueue::Seriali"...
0x180230a0e  mov     r8d, 228h; int
0x180230a14  mov     rcx, rax; this
0x180230a17  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180230a1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180230a23  jb      loc_180230E46
0x180230a29  mov     edx, 35h ; '5'
0x180230a2e  jmp     loc_180230E28
0x180230a33  lea     r8, [rsp+1D00h+var_1CC0]; unsigned __int8 **
0x180230a38  mov     edx, esi; unsigned int
0x180230a3a  mov     rcx, rdi; this
0x180230a3d  call    ?AllocData@CSharedMsgWriteQueue@@QEAAJKPEAPEAE@Z; CSharedMsgWriteQueue::AllocData(ulong,uchar * *)
0x180230a42  mov     ebx, eax
0x180230a44  test    eax, eax
0x180230a46  jns     loc_180230AE2
  ... truncated ...
```
