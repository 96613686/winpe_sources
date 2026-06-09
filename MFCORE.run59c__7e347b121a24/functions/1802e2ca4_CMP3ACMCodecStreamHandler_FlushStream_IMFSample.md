# CMP3ACMCodecStreamHandler::FlushStream(IMFSample *)

- ea: `0x1802e2ca4`
- end: `0x1802e386b`
- name: `?FlushStream@CMP3ACMCodecStreamHandler@@QEAAJPEAUIMFSample@@@Z`
- size: `3015`
- prototype: `__int64 __fastcall(CMP3ACMCodecStreamHandler *__hidden this, struct IMFSample *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800ea5c0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x1800ec0e0`
- `0x18018566c`
- `0x180258480`
- `0x1802592a0`
- `0x1802e0db8`
- `0x1802e2ca4`
- `0x1802e4294`
- `0x1802e43cc`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreateMemoryBuffer` at `0x1802e3063`
- `MFPlat!MFCreateMemoryBuffer` at `0x1802e3063`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e2d93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e2e45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e2ef7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e2fc0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e3085`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e313d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e31fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e32b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e3361`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e3414`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e3534`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e35df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e368a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e3746`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e2d93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e2e45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e2ef7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e2fc0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e3085`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e313d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e31fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e32b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e3361`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e3414`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e3534`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e35df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e368a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e3746`
- `ext-ms-win-mm-msacm-l1-1-0!acmStreamMessage` at `0x1802e34cf`
- `ext-ms-win-mm-msacm-l1-1-0!acmStreamMessage` at `0x1802e34cf`
- `ext-ms-win-mm-msacm-l1-1-0!acmStreamSize` at `0x1802e2d2a`
- `ext-ms-win-mm-msacm-l1-1-0!acmStreamSize` at `0x1802e2d2a`

## pseudocode

```c
__int64 __fastcall CMP3ACMCodecStreamHandler::FlushStream(CMP3ACMCodecStreamHandler *this, struct IMFSample *a2)
{
  HACMSTREAM v4; // rcx
  MMRESULT v5; // eax
  HRESULT updated; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  unsigned __int8 *v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  struct IMFSampleVtbl *lpVtbl; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 v56; // rdx
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  MMRESULT v60; // eax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 *v73; // rcx
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 *v78; // rcx
  CallStackTracing *v79; // rax
  struct CallStackContext *v80; // rax
  unsigned __int8 v82; // [rsp+30h] [rbp-89h] BYREF
  _BYTE v83[7]; // [rsp+31h] [rbp-88h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-81h] BYREF
  int v85; // [rsp+40h] [rbp-79h] BYREF
  DWORD pdwOutputBytes; // [rsp+44h] [rbp-75h] BYREF
  DWORD v87; // [rsp+48h] [rbp-71h] BYREF
  unsigned __int8 *v88; // [rsp+50h] [rbp-69h] BYREF
  __int64 v89; // [rsp+58h] [rbp-61h] BYREF
  struct tACMSTREAMHEADER lParam2; // [rsp+60h] [rbp-59h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v83, "CMP3ACMCodecStreamHandler::FlushStream", 1719);
  ppBuffer = 0;
  v89 = 0;
  v88 = 0;
  v82 = 0;
  pdwOutputBytes = 0;
  memset_0(&lParam2, 0, sizeof(lParam2));
  v4 = (HACMSTREAM)*((_QWORD *)this + 2);
  v85 = 0;
  v87 = 0;
  v5 = acmStreamSize(v4, 0x2400u, &pdwOutputBytes, 0);
  if ( (int)HRESULTFromMMRESULT(v5) < 0 )
  {
    updated = -1072861838;
    if ( g_wppLevels >= 8u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        139,
        &WPP_a3216b5dee8234e6df5ca2fe73b99a91_Traceguids,
        this,
        -1072861838);
    goto LABEL_169;
  }
  updated = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD, IMFMediaBuffer **))a2->lpVtbl->GetBufferByIndex)(
              a2,
              0,
              &ppBuffer);
  if ( updated < 0 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMP3ACMCodecStreamHandler::FlushStream", 1742, updated);
    }
    if ( g_wppLevels )
    {
      v12 = 140;
LABEL_164:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_a3216b5dee8234e6df5ca2fe73b99a91_Traceguids,
        this,
        updated);
      goto LABEL_169;
    }
    goto LABEL_169;
  }
  updated = ((__int64 (__fastcall *)(IMFMediaBuffer *, int *))ppBuffer->lpVtbl->GetCurrentLength)(ppBuffer, &v85);
  if ( updated >= 0 )
  {
    updated = ((__int64 (__fastcall *)(IMFMediaBuffer *, DWORD *))ppBuffer->lpVtbl->GetMaxLength)(ppBuffer, &v87);
    if ( updated < 0 )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != updated )
          CallStackContext::TraceFailure(v22, "CMP3ACMCodecStreamHandler::FlushStream", 1744, updated);
      }
      if ( g_wppLevels )
      {
        v12 = 142;
        goto LABEL_164;
      }
      goto LABEL_169;
    }
    if ( pdwOutputBytes <= v87 - v85 )
    {
      updated = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned __int8 **, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
                  ppBuffer,
                  &v88,
                  0,
                  0);
      if ( updated < 0 )
      {
        v25 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)v27 + 499) != updated )
            CallStackContext::TraceFailure(v27, "CMP3ACMCodecStreamHandler::FlushStream", 1749, updated);
        }
        if ( g_wppLevels )
        {
          v12 = 143;
          goto LABEL_164;
        }
        goto LABEL_169;
      }
      v28 = &v88[v85];
      v88 = v28;
      goto LABEL_118;
    }
    ppBuffer = 0;
    updated = MFCreateMemoryBuffer(pdwOutputBytes, &ppBuffer);
    if ( updated < 0 )
    {
      v31 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)v33 + 499) != updated )
          CallStackContext::TraceFailure(v33, "CMP3ACMCodecStreamHandler::FlushStream", 1756, updated);
      }
      if ( g_wppLevels )
      {
        v12 = 144;
        goto LABEL_164;
      }
      goto LABEL_169;
    }
    updated = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned __int8 **, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
                ppBuffer,
                &v88,
                0,
                0);
    if ( updated < 0 )
    {
      v36 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v36 + 8) )
      {
        v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)v38 + 499) != updated )
          CallStackContext::TraceFailure(v38, "CMP3ACMCodecStreamHandler::FlushStream", 1757, updated);
      }
      if ( g_wppLevels )
      {
        v12 = 145;
        goto LABEL_164;
      }
      goto LABEL_169;
    }
    v87 = pdwOutputBytes;
    lpVtbl = a2->lpVtbl;
    v85 = 0;
    updated = ((__int64 (__fastcall *)(struct IMFSample *, IMFMediaBuffer *))lpVtbl->AddBuffer)(a2, ppBuffer);
    if ( updated >= 0 )
    {
      updated = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))a2->lpVtbl->ConvertToContiguousBuffer)(a2, &v89);
      if ( updated >= 0 )
      {
        updated = ((__int64 (__fastcall *)(struct IMFSample *))a2->lpVtbl->RemoveAllBuffers)(a2);
        if ( updated >= 0 )
        {
          updated = ((__int64 (__fastcall *)(struct IMFSample *, __int64))a2->lpVtbl->AddBuffer)(a2, v89);
          if ( updated >= 0 )
          {
            v28 = v88;
LABEL_118:
            CMP3ACMCodecStreamHandler::PrepareDummyHeader(this, &v82, v24, v28, pdwOutputBytes, &lParam2);
            v60 = acmStreamMessage(*((HACMSTREAM *)this + 2), 0x4100u, *((_QWORD *)this + 28), (LPARAM)&lParam2);
            if ( (int)HRESULTFromMMRESULT(v60) >= 0 && lParam2.cbDstLengthUsed )
            {
              ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
              updated = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
                          ppBuffer,
                          lParam2.cbDstLengthUsed + v85);
              if ( updated >= 0 )
              {
                updated = CMP3ACMCodecStreamHandler::UpdateGaplessMetadata(this, &lParam2, a2);
                if ( updated >= 0 )
                {
                  updated = CMP3ACMCodecStreamHandler::AddPaddingTimeToOutputSampleTime(this, a2, &lParam2);
                  if ( updated >= 0 )
                  {
                    updated = ((__int64 (__fastcall *)(struct IMFSample *, const GUID *, __int64))a2->lpVtbl->SetUINT32)(
                                a2,
                                &MFSampleExtension_CleanPoint,
                                1);
                    if ( updated < 0 )
                    {
                      v78 = (__int64 *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76, v77);
                        CallStackTracing::s_wpInstance = v79;
                        if ( v79
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(
                               v79,
                               2032) )
                        {
                          v78 = (__int64 *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v78 = &qword_1803CE250;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                        }
                      }
                      if ( *((_BYTE *)v78 + 8) )
                      {
                        v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v78);
                        if ( *((_DWORD *)v80 + 499) != updated )
                          CallStackContext::TraceFailure(v80, "CMP3ACMCodecStreamHandler::FlushStream", 1790, updated);
                      }
                      if ( g_wppLevels )
                      {
                        v12 = 154;
                        goto LABEL_164;
                      }
                    }
                  }
                  else
                  {
                    v73 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v71, v72);
                      CallStackTracing::s_wpInstance = v74;
                      if ( v74
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(
                             v74,
                             2032) )
                      {
                        v73 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v73 = &qword_1803CE250;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                      }
                    }
                    if ( *((_BYTE *)v73 + 8) )
                    {
                      v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
                      if ( *((_DWORD *)v75 + 499) != updated )
                        CallStackContext::TraceFailure(v75, "CMP3ACMCodecStreamHandler::FlushStream", 1789, updated);
                    }
                    if ( g_wppLevels )
                    {
                      v12 = 153;
                      goto LABEL_164;
                    }
                  }
                }
                else
                {
                  v68 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v67);
                    CallStackTracing::s_wpInstance = v69;
                    if ( v69
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
                    {
                      v68 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v68 = &qword_1803CE250;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v68 + 8) )
                  {
                    v70 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
                    if ( *((_DWORD *)v70 + 499) != updated )
                      CallStackContext::TraceFailure(v70, "CMP3ACMCodecStreamHandler::FlushStream", 1786, updated);
                  }
                  if ( g_wppLevels )
                  {
                    v12 = 152;
                    goto LABEL_164;
                  }
                }
              }
              else
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
                  if ( *((_DWORD *)v65 + 499) != updated )
                    CallStackContext::TraceFailure(v65, "CMP3ACMCodecStreamHandler::FlushStream", 1783, updated);
                }
                if ( g_wppLevels )
                {
                  v12 = 151;
                  goto LABEL_164;
                }
              }
              goto LABEL_169;
            }
            updated = -1072861838;
            if ( g_wppLevels >= 8u )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                150,
                &WPP_a3216b5dee8234e6df5ca2fe73b99a91_Traceguids,
                this,
                -1072861838);
LABEL_168:
            ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
            goto LABEL_169;
          }
          v57 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56, v24);
            CallStackTracing::s_wpInstance = v58;
            if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
            {
              v57 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v57 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v57 + 8) )
          {
            v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
            if ( *((_DWORD *)v59 + 499) != updated )
              CallStackContext::TraceFailure(v59, "CMP3ACMCodecStreamHandler::FlushStream", 1766, updated);
          }
          if ( !g_wppLevels )
            goto LABEL_168;
          v45 = 149;
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
            if ( *((_DWORD *)v55 + 499) != updated )
              CallStackContext::TraceFailure(v55, "CMP3ACMCodecStreamHandler::FlushStream", 1765, updated);
          }
          if ( !g_wppLevels )
            goto LABEL_168;
          v45 = 148;
        }
      }
      else
      {
        v48 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47);
          CallStackTracing::s_wpInstance = v49;
          if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
          {
            v48 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v48 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v48 + 8) )
        {
          v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
          if ( *((_DWORD *)v50 + 499) != updated )
            CallStackContext::TraceFailure(v50, "CMP3ACMCodecStreamHandler::FlushStream", 1764, updated);
        }
        if ( !g_wppLevels )
          goto LABEL_168;
        v45 = 147;
      }
    }
    else
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
        if ( *((_DWORD *)v44 + 499) != updated )
          CallStackContext::TraceFailure(v44, "CMP3ACMCodecStreamHandler::FlushStream", 1763, updated);
      }
      if ( !g_wppLevels )
        goto LABEL_168;
      v45 = 146;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v45, &WPP_a3216b5dee8234e6df5ca2fe73b99a91_Traceguids, this, updated);
    goto LABEL_168;
  }
  v15 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14);
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v15 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
    if ( *((_DWORD *)v17 + 499) != updated )
      CallStackContext::TraceFailure(v17, "CMP3ACMCodecStreamHandler::FlushStream", 1743, updated);
  }
  if ( g_wppLevels )
  {
    v12 = 141;
    goto LABEL_164;
  }
LABEL_169:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v89);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppBuffer);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v83);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1802e2ca4  mov     [rsp-8+arg_10], rbx
0x1802e2ca9  push    rbp
0x1802e2caa  push    rsi
0x1802e2cab  push    rdi
0x1802e2cac  push    r14
0x1802e2cae  push    r15
0x1802e2cb0  lea     rbp, [rsp-37h]
0x1802e2cb5  sub     rsp, 0F0h
0x1802e2cbc  mov     rax, cs:__security_cookie
0x1802e2cc3  xor     rax, rsp
0x1802e2cc6  mov     [rbp+57h+var_30], rax
0x1802e2cca  mov     rsi, rdx
0x1802e2ccd  lea     r15, aCmp3acmcodecst_2; "CMP3ACMCodecStreamHandler::FlushStream"
0x1802e2cd4  mov     rdi, rcx
0x1802e2cd7  mov     rdx, r15; char *
0x1802e2cda  mov     r8d, 6B7h; int
0x1802e2ce0  lea     rcx, [rsp+110h+var_DF]; this
0x1802e2ce5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802e2cea  xor     r14d, r14d
0x1802e2ced  lea     rcx, [rbp+57h+lParam2]; void *
0x1802e2cf1  xor     edx, edx; Val
0x1802e2cf3  mov     [rsp+110h+ppBuffer], r14
0x1802e2cf8  mov     [rbp+57h+var_B8], r14
0x1802e2cfc  mov     [rbp+57h+var_C0], r14
0x1802e2d00  lea     r8d, [r14+7Ch]; Size
0x1802e2d04  mov     [rsp+110h+var_E0], r14b
0x1802e2d09  mov     [rbp+57h+pdwOutputBytes], r14d
0x1802e2d0d  call    memset_0
0x1802e2d12  mov     rcx, [rdi+10h]; has
0x1802e2d16  lea     r8, [rbp+57h+pdwOutputBytes]; pdwOutputBytes
0x1802e2d1a  xor     r9d, r9d; fdwSize
0x1802e2d1d  mov     [rbp+57h+var_D0], r14d
0x1802e2d21  mov     edx, 2400h; cbInput
0x1802e2d26  mov     [rbp+57h+var_C8], r14d
0x1802e2d2a  call    cs:__imp_acmStreamSize
0x1802e2d31  nop     dword ptr [rax+rax+00h]
0x1802e2d36  mov     ecx, eax; unsigned int
0x1802e2d38  call    ?HRESULTFromMMRESULT@@YAJI@Z; HRESULTFromMMRESULT(uint)
0x1802e2d3d  test    eax, eax
0x1802e2d3f  jns     short loc_1802E2D63
0x1802e2d41  mov     eax, 0C00D6D72h
0x1802e2d46  mov     ebx, eax
0x1802e2d48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1802e2d4f  jb      loc_1802E3828
0x1802e2d55  mov     edx, 8Bh
0x1802e2d5a  mov     [rsp+110h+var_F0], eax
0x1802e2d5e  jmp     loc_1802E37C7
0x1802e2d63  mov     rax, [rsi]
0x1802e2d66  lea     r8, [rsp+110h+ppBuffer]
0x1802e2d6b  xor     edx, edx
0x1802e2d6d  mov     rcx, rsi
0x1802e2d70  mov     rax, [rax+140h]
0x1802e2d77  call    cs:__guard_dispatch_icall_fptr
0x1802e2d7d  mov     ebx, eax
0x1802e2d7f  test    eax, eax
0x1802e2d81  jns     loc_1802E2E19
0x1802e2d87  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2d8e  test    rcx, rcx
0x1802e2d91  jnz     short loc_1802E2DDB
0x1802e2d93  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e2d9a  nop     dword ptr [rax+rax+00h]
0x1802e2d9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2da6  mov     rcx, rax
0x1802e2da9  test    rax, rax
0x1802e2dac  jz      short loc_1802E2DCD
0x1802e2dae  mov     rax, [rax]
0x1802e2db1  mov     edx, 7F0h
0x1802e2db6  mov     rax, [rax+8]
0x1802e2dba  call    cs:__guard_dispatch_icall_fptr
0x1802e2dc0  test    eax, eax
0x1802e2dc2  jz      short loc_1802E2DCD
0x1802e2dc4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2dcb  jmp     short loc_1802E2DDB
0x1802e2dcd  lea     rcx, qword_1803CE250; this
0x1802e2dd4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2ddb  cmp     [rcx+8], r14b
0x1802e2ddf  jz      short loc_1802E2E02
0x1802e2de1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e2de6  cmp     [rax+7CCh], ebx
0x1802e2dec  jz      short loc_1802E2E02
0x1802e2dee  mov     r9d, ebx; int
0x1802e2df1  mov     r8d, 6CEh; int
0x1802e2df7  mov     rdx, r15; char *
0x1802e2dfa  mov     rcx, rax; this
0x1802e2dfd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e2e02  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e2e09  jb      loc_1802E3828
0x1802e2e0f  mov     edx, 8Ch
0x1802e2e14  jmp     loc_1802E37C3
0x1802e2e19  mov     rcx, [rsp+110h+ppBuffer]
0x1802e2e1e  lea     rdx, [rbp+57h+var_D0]
0x1802e2e22  mov     rax, [rcx]
0x1802e2e25  mov     rax, [rax+28h]
0x1802e2e29  call    cs:__guard_dispatch_icall_fptr
0x1802e2e2f  mov     ebx, eax
0x1802e2e31  test    eax, eax
0x1802e2e33  jns     loc_1802E2ECB
0x1802e2e39  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2e40  test    rcx, rcx
0x1802e2e43  jnz     short loc_1802E2E8D
0x1802e2e45  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e2e4c  nop     dword ptr [rax+rax+00h]
0x1802e2e51  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2e58  mov     rcx, rax
0x1802e2e5b  test    rax, rax
0x1802e2e5e  jz      short loc_1802E2E7F
0x1802e2e60  mov     rax, [rax]
0x1802e2e63  mov     edx, 7F0h
0x1802e2e68  mov     rax, [rax+8]
0x1802e2e6c  call    cs:__guard_dispatch_icall_fptr
0x1802e2e72  test    eax, eax
0x1802e2e74  jz      short loc_1802E2E7F
0x1802e2e76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2e7d  jmp     short loc_1802E2E8D
0x1802e2e7f  lea     rcx, qword_1803CE250; this
0x1802e2e86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2e8d  cmp     [rcx+8], r14b
0x1802e2e91  jz      short loc_1802E2EB4
0x1802e2e93  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e2e98  cmp     [rax+7CCh], ebx
0x1802e2e9e  jz      short loc_1802E2EB4
0x1802e2ea0  mov     r9d, ebx; int
0x1802e2ea3  mov     r8d, 6CFh; int
0x1802e2ea9  mov     rdx, r15; char *
0x1802e2eac  mov     rcx, rax; this
0x1802e2eaf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e2eb4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e2ebb  jb      loc_1802E3828
0x1802e2ec1  mov     edx, 8Dh
0x1802e2ec6  jmp     loc_1802E37C3
0x1802e2ecb  mov     rcx, [rsp+110h+ppBuffer]
0x1802e2ed0  lea     rdx, [rbp+57h+var_C8]
0x1802e2ed4  mov     rax, [rcx]
0x1802e2ed7  mov     rax, [rax+38h]
0x1802e2edb  call    cs:__guard_dispatch_icall_fptr
0x1802e2ee1  mov     ebx, eax
0x1802e2ee3  test    eax, eax
0x1802e2ee5  jns     loc_1802E2F7D
0x1802e2eeb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2ef2  test    rcx, rcx
0x1802e2ef5  jnz     short loc_1802E2F3F
0x1802e2ef7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e2efe  nop     dword ptr [rax+rax+00h]
0x1802e2f03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2f0a  mov     rcx, rax
0x1802e2f0d  test    rax, rax
0x1802e2f10  jz      short loc_1802E2F31
0x1802e2f12  mov     rax, [rax]
0x1802e2f15  mov     edx, 7F0h
0x1802e2f1a  mov     rax, [rax+8]
0x1802e2f1e  call    cs:__guard_dispatch_icall_fptr
0x1802e2f24  test    eax, eax
0x1802e2f26  jz      short loc_1802E2F31
0x1802e2f28  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2f2f  jmp     short loc_1802E2F3F
0x1802e2f31  lea     rcx, qword_1803CE250; this
0x1802e2f38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2f3f  cmp     [rcx+8], r14b
0x1802e2f43  jz      short loc_1802E2F66
0x1802e2f45  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e2f4a  cmp     [rax+7CCh], ebx
0x1802e2f50  jz      short loc_1802E2F66
0x1802e2f52  mov     r9d, ebx; int
0x1802e2f55  mov     r8d, 6D0h; int
0x1802e2f5b  mov     rdx, r15; char *
0x1802e2f5e  mov     rcx, rax; this
0x1802e2f61  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e2f66  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e2f6d  jb      loc_1802E3828
0x1802e2f73  mov     edx, 8Eh
0x1802e2f78  jmp     loc_1802E37C3
0x1802e2f7d  mov     eax, [rbp+57h+var_C8]
0x1802e2f80  sub     eax, [rbp+57h+var_D0]
0x1802e2f83  mov     ecx, [rbp+57h+pdwOutputBytes]; cbMaxLength
0x1802e2f86  cmp     ecx, eax
0x1802e2f88  ja      loc_1802E3059
0x1802e2f8e  mov     rcx, [rsp+110h+ppBuffer]
0x1802e2f93  lea     rdx, [rbp+57h+var_C0]
0x1802e2f97  xor     r9d, r9d
0x1802e2f9a  xor     r8d, r8d
0x1802e2f9d  mov     rax, [rcx]
0x1802e2fa0  mov     rax, [rax+18h]
0x1802e2fa4  call    cs:__guard_dispatch_icall_fptr
0x1802e2faa  mov     ebx, eax
0x1802e2fac  test    eax, eax
0x1802e2fae  jns     loc_1802E3046
0x1802e2fb4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2fbb  test    rcx, rcx
0x1802e2fbe  jnz     short loc_1802E3008
0x1802e2fc0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e2fc7  nop     dword ptr [rax+rax+00h]
0x1802e2fcc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2fd3  mov     rcx, rax
0x1802e2fd6  test    rax, rax
0x1802e2fd9  jz      short loc_1802E2FFA
0x1802e2fdb  mov     rax, [rax]
0x1802e2fde  mov     edx, 7F0h
0x1802e2fe3  mov     rax, [rax+8]
0x1802e2fe7  call    cs:__guard_dispatch_icall_fptr
0x1802e2fed  test    eax, eax
0x1802e2fef  jz      short loc_1802E2FFA
0x1802e2ff1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e2ff8  jmp     short loc_1802E3008
0x1802e2ffa  lea     rcx, qword_1803CE250; this
0x1802e3001  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e3008  cmp     [rcx+8], r14b
0x1802e300c  jz      short loc_1802E302F
0x1802e300e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e3013  cmp     [rax+7CCh], ebx
0x1802e3019  jz      short loc_1802E302F
0x1802e301b  mov     r9d, ebx; int
0x1802e301e  mov     r8d, 6D5h; int
0x1802e3024  mov     rdx, r15; char *
0x1802e3027  mov     rcx, rax; this
0x1802e302a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e302f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e3036  jb      loc_1802E3828
0x1802e303c  mov     edx, 8Fh
0x1802e3041  jmp     loc_1802E37C3
0x1802e3046  mov     r9, [rbp+57h+var_C0]
0x1802e304a  mov     eax, [rbp+57h+var_D0]
0x1802e304d  add     r9, rax
0x1802e3050  mov     [rbp+57h+var_C0], r9
0x1802e3054  jmp     loc_1802E349E
0x1802e3059  lea     rdx, [rsp+110h+ppBuffer]; ppBuffer
0x1802e305e  mov     [rsp+110h+ppBuffer], r14
0x1802e3063  call    cs:__imp_MFCreateMemoryBuffer
0x1802e306a  nop     dword ptr [rax+rax+00h]
0x1802e306f  mov     ebx, eax
0x1802e3071  test    eax, eax
0x1802e3073  jns     loc_1802E310B
0x1802e3079  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e3080  test    rcx, rcx
0x1802e3083  jnz     short loc_1802E30CD
0x1802e3085  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e308c  nop     dword ptr [rax+rax+00h]
0x1802e3091  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e3098  mov     rcx, rax
0x1802e309b  test    rax, rax
0x1802e309e  jz      short loc_1802E30BF
0x1802e30a0  mov     rax, [rax]
0x1802e30a3  mov     edx, 7F0h
0x1802e30a8  mov     rax, [rax+8]
0x1802e30ac  call    cs:__guard_dispatch_icall_fptr
0x1802e30b2  test    eax, eax
0x1802e30b4  jz      short loc_1802E30BF
0x1802e30b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e30bd  jmp     short loc_1802E30CD
0x1802e30bf  lea     rcx, qword_1803CE250; this
0x1802e30c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e30cd  cmp     [rcx+8], r14b
0x1802e30d1  jz      short loc_1802E30F4
0x1802e30d3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e30d8  cmp     [rax+7CCh], ebx
0x1802e30de  jz      short loc_1802E30F4
0x1802e30e0  mov     r9d, ebx; int
0x1802e30e3  mov     r8d, 6DCh; int
0x1802e30e9  mov     rdx, r15; char *
0x1802e30ec  mov     rcx, rax; this
0x1802e30ef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e30f4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e30fb  jb      loc_1802E3828
0x1802e3101  mov     edx, 90h
0x1802e3106  jmp     loc_1802E37C3
0x1802e310b  mov     rcx, [rsp+110h+ppBuffer]
0x1802e3110  lea     rdx, [rbp+57h+var_C0]
0x1802e3114  xor     r9d, r9d
0x1802e3117  xor     r8d, r8d
0x1802e311a  mov     rax, [rcx]
0x1802e311d  mov     rax, [rax+18h]
0x1802e3121  call    cs:__guard_dispatch_icall_fptr
0x1802e3127  mov     ebx, eax
0x1802e3129  test    eax, eax
0x1802e312b  jns     loc_1802E31C3
0x1802e3131  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e3138  test    rcx, rcx
0x1802e313b  jnz     short loc_1802E3185
0x1802e313d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e3144  nop     dword ptr [rax+rax+00h]
0x1802e3149  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e3150  mov     rcx, rax
0x1802e3153  test    rax, rax
0x1802e3156  jz      short loc_1802E3177
0x1802e3158  mov     rax, [rax]
0x1802e315b  mov     edx, 7F0h
0x1802e3160  mov     rax, [rax+8]
0x1802e3164  call    cs:__guard_dispatch_icall_fptr
0x1802e316a  test    eax, eax
0x1802e316c  jz      short loc_1802E3177
0x1802e316e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e3175  jmp     short loc_1802E3185
0x1802e3177  lea     rcx, qword_1803CE250; this
0x1802e317e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e3185  cmp     [rcx+8], r14b
0x1802e3189  jz      short loc_1802E31AC
0x1802e318b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e3190  cmp     [rax+7CCh], ebx
0x1802e3196  jz      short loc_1802E31AC
0x1802e3198  mov     r9d, ebx; int
0x1802e319b  mov     r8d, 6DDh; int
  ... truncated ...
```
