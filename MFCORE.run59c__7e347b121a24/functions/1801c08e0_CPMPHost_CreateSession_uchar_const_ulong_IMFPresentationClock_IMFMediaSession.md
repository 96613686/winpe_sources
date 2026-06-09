# CPMPHost::CreateSession(uchar const *,ulong,IMFPresentationClock *,IMFMediaSession * *)

- ea: `0x1801c08e0`
- end: `0x1801c147a`
- name: `?CreateSession@CPMPHost@@UEAAJPEBEKPEAUIMFPresentationClock@@PEAPEAUIMFMediaSession@@@Z`
- size: `2970`
- prototype: `int(CPMPHost *__hidden this, const unsigned __int8 *, unsigned int, struct IMFPresentationClock *, struct IMFMediaSession **)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002fee0`
- `0x180033e20`
- `0x180034610`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004d118`
- `0x180050d6c`
- `0x18006b388`
- `0x1800ec0e0`
- `0x1801356cc`
- `0x1801c08e0`
- `0x1801c1ed4`
- `0x1801cce10`
- `0x1802122a4`
- `0x18024aa20`
- `0x1802583a8`
- `0x1802a3874`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801c1450`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801c1450`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801c090f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801c090f`
- `MFPlat!MFInitAttributesFromBlob` at `0x1801c105e`
- `MFPlat!MFInitAttributesFromBlob` at `0x1801c105e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0980`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0a48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0aed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0bd1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0c6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0d29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0e13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0ec8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0fb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c1080`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c112c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c1215`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c12d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0980`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0a48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0aed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0bd1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0c6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0d29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0e13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0ec8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c0fb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c1080`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c112c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c1215`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801c12d0`
- `MFPlat!MFCreateAttributes` at `0x1801c0f92`
- `MFPlat!MFCreateAttributes` at `0x1801c0f92`

## string_xrefs

- `0x1801c0947`: `CPMPHost::CreateSession`
- `0x1801c09de`: `CPMPHost::CreateSession`
- `0x1801c0aa6`: `CPMPHost::CreateSession`
- `0x1801c0e71`: `CPMPHost::CreateSession`
- `0x1801c0f26`: `CPMPHost::CreateSession`
- `0x1801c1012`: `CPMPHost::CreateSession`
- `0x1801c10de`: `CPMPHost::CreateSession`
- `0x1801c118a`: `CPMPHost::CreateSession`
- `0x1801c1273`: `CPMPHost::CreateSession`
- `0x1801c132e`: `CPMPHost::CreateSession`

## pseudocode

```c
__int64 __fastcall CPMPHost::CreateSession(
        CPMPHost *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        struct IMFPresentationClock *a4,
        struct IMFMediaSession **a5)
{
  int Instance; // esi
  __int64 v10; // rdx
  __int64 v11; // r8
  char *v12; // rdi
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  struct IMFMediaSession **v17; // r12
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  CPolicyEngine *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  CPolicyEngine *v27; // rax
  CPolicyEngine *v28; // rcx
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
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
  __int64 v57; // r8
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // rcx
  struct IMFMediaSession **v67; // r15
  struct IMFPresentationClock *v68; // rdx
  struct CPolicyEngine *v69; // r8
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 *v77; // rcx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  struct IMFMediaSession *v80; // rcx
  __int64 v81; // rdi
  struct IMFMediaSession *v82; // rbx
  __int64 v83; // rcx
  int v85; // [rsp+20h] [rbp-E0h]
  int v86; // [rsp+40h] [rbp-C0h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  void **v89; // [rsp+60h] [rbp-A0h] BYREF
  void **v90; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v91[2]; // [rsp+268h] [rbp+168h] BYREF
  int v92; // [rsp+278h] [rbp+178h]
  unsigned int v93; // [rsp+27Ch] [rbp+17Ch]
  char v94; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v95; // [rsp+2D8h] [rbp+1D8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  Instance = 0;
  v95 = 0;
  v86 = 0;
  ppv = 0;
  ppMFAttributes = 0;
  CBufferReader::CBufferReader((CBufferReader *)&v89, a2, a3);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v94, "CPMPHost::CreateSession", 753);
  v12 = (char *)this - 8;
  if ( !a4 )
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    Instance = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CPMPHost::CreateSession", 753, -2147024809);
    }
    if ( g_wppLevels )
    {
      v16 = 25;
LABEL_12:
      v85 = -2147024809;
LABEL_13:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
        (char *)this - 8,
        v85);
      goto LABEL_165;
    }
    goto LABEL_165;
  }
  v17 = a5;
  if ( a5 )
  {
    if ( *((_QWORD *)v12 + 13) )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
      Instance = -2147467259;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v23 + 499) != -2147467259 )
          CallStackContext::TraceFailure(v23, "CPMPHost::CreateSession", 758, -2147467259);
      }
      if ( !g_wppLevels )
        goto LABEL_165;
      v16 = 27;
      goto LABEL_37;
    }
    v24 = (CPolicyEngine *)operator new(0x88u);
    if ( v24 )
    {
      v27 = CPolicyEngine::CPolicyEngine(
              v24,
              (struct IMFComponentCreator *)((*((_QWORD *)this + 10) + 16LL) & -(__int64)(*((_QWORD *)this + 10) != 0)),
              &v95);
      Instance = v95;
      v28 = v27;
    }
    else
    {
      v28 = 0;
    }
    *((_QWORD *)this + 11) = v28;
    if ( !v28 )
    {
      v29 = (__int64 *)CallStackTracing::s_wpInstance;
      Instance = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)v31 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v31, "CPMPHost::CreateSession", 767, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_165;
      v16 = 28;
      goto LABEL_37;
    }
    if ( Instance < 0 )
    {
      v32 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26);
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
        if ( *((_DWORD *)v34 + 499) != Instance )
          CallStackContext::TraceFailure(v34, "CPMPHost::CreateSession", 769, Instance);
      }
      if ( !g_wppLevels )
        goto LABEL_165;
      v16 = 29;
      goto LABEL_37;
    }
    (*(void (__fastcall **)(CPolicyEngine *))(*(_QWORD *)v28 + 8LL))(v28);
    Instance = CBinaryReader::ReadInt32((CBinaryReader *)v91, &v86);
    if ( Instance < 0 )
    {
      v37 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36);
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
        if ( *((_DWORD *)v39 + 499) != Instance )
          CallStackContext::TraceFailure(v39, "CPMPHost::CreateSession", 776, Instance);
      }
      if ( !g_wppLevels )
        goto LABEL_165;
      v16 = 30;
LABEL_37:
      v85 = Instance;
      goto LABEL_13;
    }
    if ( v86 )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          31,
          &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
          (char *)this - 8);
      Instance = CDCOMInterfaceMashallerHelper::UnMarshalInterface(
                   (struct CBinaryReader *)v91,
                   &IID_IMFContentProtectionManager,
                   &ppv);
      if ( Instance < 0 )
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
          if ( *((_DWORD *)v44 + 499) != Instance )
            CallStackContext::TraceFailure(v44, "CPMPHost::CreateSession", 787, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_165;
        v45 = 32;
        goto LABEL_89;
      }
      Instance = CPolicyEngine::SetContentProtectionManager(
                   *((CPolicyEngine **)v12 + 12),
                   (struct IMFContentProtectionManager *)ppv);
      if ( Instance < 0 )
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
          if ( *((_DWORD *)v50 + 499) != Instance )
            CallStackContext::TraceFailure(v50, "CPMPHost::CreateSession", 790, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_165;
        v45 = 33;
        goto LABEL_89;
      }
    }
    if ( v92 == v93 )
      goto LABEL_126;
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        34,
        &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
        (char *)this - 8);
    Instance = MFCreateAttributes(&ppMFAttributes, 5u);
    if ( Instance < 0 )
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
        if ( *((_DWORD *)v55 + 499) != Instance )
          CallStackContext::TraceFailure(v55, "CPMPHost::CreateSession", 799, Instance);
      }
      if ( !g_wppLevels )
        goto LABEL_165;
      v45 = 35;
      goto LABEL_89;
    }
    Instance = MFInitAttributesFromBlob(ppMFAttributes, (const UINT8 *)(v91[1] + v93), v92 - v93);
    if ( Instance >= 0 )
    {
LABEL_126:
      Instance = CPMPPresentationClock::CreateInstance(a4, (struct IMFPresentationClock **)this + 14);
      if ( Instance >= 0 )
      {
        v66 = *((_QWORD *)this + 10);
        v67 = (struct IMFMediaSession **)((char *)this + 96);
        v68 = (struct IMFPresentationClock *)*((_QWORD *)v12 + 15);
        v69 = (struct CPolicyEngine *)*((_QWORD *)this + 11);
        *((_QWORD *)this + 12) = 0;
        Instance = CMediaSession::CreateInstance(
                     0,
                     0,
                     0,
                     (struct IMFComponentCreator *)((v66 + 16) & -(__int64)(v66 != 0)),
                     v69,
                     v68,
                     ppMFAttributes,
                     (struct IMFMediaSession **)this + 12);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)v12 + 13) + 32LL))(
                       *((_QWORD *)v12 + 13),
                       (char *)this + 240,
                       0);
          if ( Instance >= 0 )
          {
            if ( (unsigned __int8)byte_1803CECE9 >= 8u )
              WPP_SF_qq(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                40,
                &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
                (char *)this - 8,
                *v67);
            v80 = *v67;
            *v17 = *v67;
            ((void (__fastcall *)(struct IMFMediaSession *))v80->lpVtbl->AddRef)(v80);
            v81 = *((_QWORD *)this + 11);
            v82 = *v67;
            v83 = *(_QWORD *)(v81 + 96);
            if ( v83 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
            *(_QWORD *)(v81 + 96) = v82;
            if ( v82 )
              ((void (__fastcall *)(struct IMFMediaSession *))v82->lpVtbl->AddRef)(v82);
            goto LABEL_165;
          }
          v77 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v75, v76);
            CallStackTracing::s_wpInstance = v78;
            if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
            {
              v77 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v77 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v77 + 8) )
          {
            v79 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v77);
            if ( *((_DWORD *)v79 + 499) != Instance )
              CallStackContext::TraceFailure(v79, "CPMPHost::CreateSession", 826, Instance);
          }
          if ( !g_wppLevels )
            goto LABEL_165;
          v45 = 39;
        }
        else
        {
          v72 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70, v71);
            CallStackTracing::s_wpInstance = v73;
            if ( v73 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
            {
              v72 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v72 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v72 + 8) )
          {
            v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
            if ( *((_DWORD *)v74 + 499) != Instance )
              CallStackContext::TraceFailure(v74, "CPMPHost::CreateSession", 824, Instance);
          }
          if ( !g_wppLevels )
            goto LABEL_165;
          v45 = 38;
        }
      }
      else
      {
        v63 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v61, v62);
          CallStackTracing::s_wpInstance = v64;
          if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
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
          if ( *((_DWORD *)v65 + 499) != Instance )
            CallStackContext::TraceFailure(v65, "CPMPHost::CreateSession", 810, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_165;
        v45 = 37;
      }
    }
    else
    {
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
        if ( *((_DWORD *)v60 + 499) != Instance )
          CallStackContext::TraceFailure(v60, "CPMPHost::CreateSession", 802, Instance);
      }
      if ( !g_wppLevels )
        goto LABEL_165;
      v45 = 36;
    }
LABEL_89:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v45,
      &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
      (char *)this - 8,
      Instance);
    goto LABEL_165;
  }
  v18 = (__int64 *)CallStackTracing::s_wpInstance;
  Instance = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11);
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
    if ( *((_DWORD *)v20 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v20, "CPMPHost::CreateSession", 754, -2147024809);
  }
  if ( g_wppLevels )
  {
    v16 = 26;
    goto LABEL_12;
  }
LABEL_165:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( ppMFAttributes )
  {
    ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
    ppMFAttributes = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v94);
  v89 = &CBufferReader::`vftable'{for `CDefaultIStreamImpl'};
  v90 = &CBufferWriter::`vftable'{for `CPersistStreamMap'};
  v91[0] = &CBufferReaderWithReferenceStore::`vftable'{for `CBinaryReader'};
  CPersistStreamMap::~CPersistStreamMap((CPersistStreamMap *)&v90);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1801c08e0  mov     [rsp-8+arg_8], rbx
0x1801c08e5  push    rbp
0x1801c08e6  push    rsi
0x1801c08e7  push    rdi
0x1801c08e8  push    r12
0x1801c08ea  push    r13
0x1801c08ec  push    r14
0x1801c08ee  push    r15
0x1801c08f0  lea     rbp, [rsp-180h]
0x1801c08f8  sub     rsp, 280h
0x1801c08ff  mov     r14, rcx
0x1801c0902  mov     r15, r9
0x1801c0905  add     rcx, 10h; lpCriticalSection
0x1801c0909  mov     ebx, r8d
0x1801c090c  mov     rdi, rdx
0x1801c090f  call    cs:__imp_EnterCriticalSection
0x1801c0916  nop     dword ptr [rax+rax+00h]
0x1801c091b  xor     esi, esi
0x1801c091d  lea     rcx, [rsp+2B0h+var_250]; this
0x1801c0922  mov     r8d, ebx; unsigned int
0x1801c0925  mov     [rbp+1B0h+arg_18], esi
0x1801c092b  mov     rdx, rdi; unsigned __int8 *
0x1801c092e  mov     [rsp+2B0h+var_270], esi
0x1801c0932  mov     [rsp+2B0h+ppv], rsi
0x1801c0937  mov     [rsp+2B0h+ppMFAttributes], rsi
0x1801c093c  call    ??0CBufferReader@@QEAA@PEBEK@Z; CBufferReader::CBufferReader(uchar const *,ulong)
0x1801c0941  mov     r12d, 2F1h
0x1801c0947  lea     rbx, aCpmphostCreate_6; "CPMPHost::CreateSession"
0x1801c094e  mov     r8d, r12d; int
0x1801c0951  lea     rcx, [rbp+1B0h+arg_0]; this
0x1801c0958  mov     rdx, rbx; char *
0x1801c095b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801c0960  lea     rdi, [r14-8]
0x1801c0964  test    r15, r15
0x1801c0967  jnz     loc_1801C0A25
0x1801c096d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0974  mov     ebx, 80070057h
0x1801c0979  mov     esi, ebx
0x1801c097b  test    rcx, rcx
0x1801c097e  jnz     short loc_1801C09C8
0x1801c0980  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801c0987  nop     dword ptr [rax+rax+00h]
0x1801c098c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0993  mov     rcx, rax
0x1801c0996  test    rax, rax
0x1801c0999  jz      short loc_1801C09BA
0x1801c099b  mov     rax, [rax]
0x1801c099e  mov     edx, 7F0h
0x1801c09a3  mov     rax, [rax+8]
0x1801c09a7  call    cs:__guard_dispatch_icall_fptr
0x1801c09ad  test    eax, eax
0x1801c09af  jz      short loc_1801C09BA
0x1801c09b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c09b8  jmp     short loc_1801C09C8
0x1801c09ba  lea     rcx, qword_1803CE250; this
0x1801c09c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c09c8  cmp     byte ptr [rcx+8], 0
0x1801c09cc  jz      short loc_1801C09F0
0x1801c09ce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801c09d3  cmp     [rax+7CCh], ebx
0x1801c09d9  jz      short loc_1801C09F0
0x1801c09db  mov     r9d, ebx; int
0x1801c09de  lea     rdx, aCpmphostCreate_6; "CPMPHost::CreateSession"
0x1801c09e5  mov     r8d, r12d; int
0x1801c09e8  mov     rcx, rax; this
0x1801c09eb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801c09f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801c09f7  jb      loc_1801C13D0
0x1801c09fd  mov     edx, 19h
0x1801c0a02  mov     dword ptr [rsp+2B0h+var_290], ebx
0x1801c0a06  lea     r8, WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids
0x1801c0a0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c0a14  mov     r9, rdi
0x1801c0a17  mov     rcx, [rcx+10h]
0x1801c0a1b  call    WPP_SF_qD
0x1801c0a20  jmp     loc_1801C13D0
0x1801c0a25  mov     r12, [rbp+1B0h+arg_20]
0x1801c0a2c  test    r12, r12
0x1801c0a2f  jnz     loc_1801C0AD2
0x1801c0a35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0a3c  mov     ebx, 80070057h
0x1801c0a41  mov     esi, ebx
0x1801c0a43  test    rcx, rcx
0x1801c0a46  jnz     short loc_1801C0A90
0x1801c0a48  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801c0a4f  nop     dword ptr [rax+rax+00h]
0x1801c0a54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0a5b  mov     rcx, rax
0x1801c0a5e  test    rax, rax
0x1801c0a61  jz      short loc_1801C0A82
0x1801c0a63  mov     rax, [rax]
0x1801c0a66  mov     edx, 7F0h
0x1801c0a6b  mov     rax, [rax+8]
0x1801c0a6f  call    cs:__guard_dispatch_icall_fptr
0x1801c0a75  test    eax, eax
0x1801c0a77  jz      short loc_1801C0A82
0x1801c0a79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0a80  jmp     short loc_1801C0A90
0x1801c0a82  lea     rcx, qword_1803CE250; this
0x1801c0a89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0a90  cmp     byte ptr [rcx+8], 0
0x1801c0a94  jz      short loc_1801C0ABB
0x1801c0a96  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801c0a9b  cmp     [rax+7CCh], ebx
0x1801c0aa1  jz      short loc_1801C0ABB
0x1801c0aa3  mov     r9d, ebx; int
0x1801c0aa6  lea     rdx, aCpmphostCreate_6; "CPMPHost::CreateSession"
0x1801c0aad  mov     r8d, 2F2h; int
0x1801c0ab3  mov     rcx, rax; this
0x1801c0ab6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801c0abb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801c0ac2  jb      loc_1801C13D0
0x1801c0ac8  mov     edx, 1Ah
0x1801c0acd  jmp     loc_1801C0A02
0x1801c0ad2  cmp     [rdi+68h], rsi
0x1801c0ad6  jz      loc_1801C0B77
0x1801c0adc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0ae3  mov     esi, 80004005h
0x1801c0ae8  test    rcx, rcx
0x1801c0aeb  jnz     short loc_1801C0B35
0x1801c0aed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801c0af4  nop     dword ptr [rax+rax+00h]
0x1801c0af9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0b00  mov     rcx, rax
0x1801c0b03  test    rax, rax
0x1801c0b06  jz      short loc_1801C0B27
0x1801c0b08  mov     rax, [rax]
0x1801c0b0b  mov     edx, 7F0h
0x1801c0b10  mov     rax, [rax+8]
0x1801c0b14  call    cs:__guard_dispatch_icall_fptr
0x1801c0b1a  test    eax, eax
0x1801c0b1c  jz      short loc_1801C0B27
0x1801c0b1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0b25  jmp     short loc_1801C0B35
0x1801c0b27  lea     rcx, qword_1803CE250; this
0x1801c0b2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0b35  cmp     byte ptr [rcx+8], 0
0x1801c0b39  jz      short loc_1801C0B5C
0x1801c0b3b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801c0b40  cmp     [rax+7CCh], esi
0x1801c0b46  jz      short loc_1801C0B5C
0x1801c0b48  mov     r9d, esi; int
0x1801c0b4b  mov     r8d, 2F6h; int
0x1801c0b51  mov     rdx, rbx; char *
0x1801c0b54  mov     rcx, rax; this
0x1801c0b57  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801c0b5c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801c0b63  jb      loc_1801C13D0
0x1801c0b69  mov     edx, 1Bh
0x1801c0b6e  mov     dword ptr [rsp+2B0h+var_290], esi
0x1801c0b72  jmp     loc_1801C0A06
0x1801c0b77  mov     ecx, 88h; Size
0x1801c0b7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801c0b81  test    rax, rax
0x1801c0b84  jz      short loc_1801C0BB1
0x1801c0b86  mov     rcx, [r14+50h]
0x1801c0b8a  lea     r8, [rcx+10h]
0x1801c0b8e  neg     rcx
0x1801c0b91  mov     rcx, rax; this
0x1801c0b94  sbb     rdx, rdx
0x1801c0b97  and     rdx, r8; struct IMFComponentCreator *
0x1801c0b9a  lea     r8, [rbp+1B0h+arg_18]; int *
0x1801c0ba1  call    ??0CPolicyEngine@@QEAA@PEAUIMFComponentCreator@@PEAJ@Z; CPolicyEngine::CPolicyEngine(IMFComponentCreator *,long *)
0x1801c0ba6  mov     esi, [rbp+1B0h+arg_18]
0x1801c0bac  mov     rcx, rax
0x1801c0baf  jmp     short loc_1801C0BB3
0x1801c0bb1  xor     ecx, ecx
0x1801c0bb3  mov     [r14+58h], rcx
0x1801c0bb7  test    rcx, rcx
0x1801c0bba  jnz     loc_1801C0C57
0x1801c0bc0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0bc7  mov     esi, 8007000Eh
0x1801c0bcc  test    rcx, rcx
0x1801c0bcf  jnz     short loc_1801C0C19
0x1801c0bd1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801c0bd8  nop     dword ptr [rax+rax+00h]
0x1801c0bdd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0be4  mov     rcx, rax
0x1801c0be7  test    rax, rax
0x1801c0bea  jz      short loc_1801C0C0B
0x1801c0bec  mov     rax, [rax]
0x1801c0bef  mov     edx, 7F0h
0x1801c0bf4  mov     rax, [rax+8]
0x1801c0bf8  call    cs:__guard_dispatch_icall_fptr
0x1801c0bfe  test    eax, eax
0x1801c0c00  jz      short loc_1801C0C0B
0x1801c0c02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0c09  jmp     short loc_1801C0C19
0x1801c0c0b  lea     rcx, qword_1803CE250; this
0x1801c0c12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0c19  cmp     byte ptr [rcx+8], 0
0x1801c0c1d  jz      short loc_1801C0C40
0x1801c0c1f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801c0c24  cmp     [rax+7CCh], esi
0x1801c0c2a  jz      short loc_1801C0C40
0x1801c0c2c  mov     r9d, esi; int
0x1801c0c2f  mov     r8d, 2FFh; int
0x1801c0c35  mov     rdx, rbx; char *
0x1801c0c38  mov     rcx, rax; this
0x1801c0c3b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801c0c40  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801c0c47  jb      loc_1801C13D0
0x1801c0c4d  mov     edx, 1Ch
0x1801c0c52  jmp     loc_1801C0B6E
0x1801c0c57  test    esi, esi
0x1801c0c59  jns     loc_1801C0CF5
0x1801c0c5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0c66  test    rcx, rcx
0x1801c0c69  jnz     short loc_1801C0CB3
0x1801c0c6b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801c0c72  nop     dword ptr [rax+rax+00h]
0x1801c0c77  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0c7e  mov     rcx, rax
0x1801c0c81  test    rax, rax
0x1801c0c84  jz      short loc_1801C0CA5
0x1801c0c86  mov     rax, [rax]
0x1801c0c89  mov     edx, 7F0h
0x1801c0c8e  mov     rax, [rax+8]
0x1801c0c92  call    cs:__guard_dispatch_icall_fptr
0x1801c0c98  test    eax, eax
0x1801c0c9a  jz      short loc_1801C0CA5
0x1801c0c9c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0ca3  jmp     short loc_1801C0CB3
0x1801c0ca5  lea     rcx, qword_1803CE250; this
0x1801c0cac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0cb3  cmp     byte ptr [rcx+8], 0
0x1801c0cb7  jz      short loc_1801C0CDE
0x1801c0cb9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801c0cbe  test    esi, esi
0x1801c0cc0  jns     short loc_1801C0CDE
0x1801c0cc2  cmp     [rax+7CCh], esi
0x1801c0cc8  jz      short loc_1801C0CDE
0x1801c0cca  mov     r9d, esi; int
0x1801c0ccd  mov     r8d, 301h; int
0x1801c0cd3  mov     rdx, rbx; char *
0x1801c0cd6  mov     rcx, rax; this
0x1801c0cd9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801c0cde  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801c0ce5  jb      loc_1801C13D0
0x1801c0ceb  mov     edx, 1Dh
0x1801c0cf0  jmp     loc_1801C0B6E
0x1801c0cf5  mov     rax, [rcx]
0x1801c0cf8  mov     rax, [rax+8]
0x1801c0cfc  call    cs:__guard_dispatch_icall_fptr
0x1801c0d02  lea     rdx, [rsp+2B0h+var_270]; int *
0x1801c0d07  lea     rcx, [rbp+1B0h+var_48]; this
0x1801c0d0e  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x1801c0d13  mov     esi, eax
0x1801c0d15  test    eax, eax
0x1801c0d17  jns     loc_1801C0DAF
0x1801c0d1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0d24  test    rcx, rcx
0x1801c0d27  jnz     short loc_1801C0D71
0x1801c0d29  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801c0d30  nop     dword ptr [rax+rax+00h]
0x1801c0d35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0d3c  mov     rcx, rax
0x1801c0d3f  test    rax, rax
0x1801c0d42  jz      short loc_1801C0D63
0x1801c0d44  mov     rax, [rax]
0x1801c0d47  mov     edx, 7F0h
0x1801c0d4c  mov     rax, [rax+8]
0x1801c0d50  call    cs:__guard_dispatch_icall_fptr
0x1801c0d56  test    eax, eax
0x1801c0d58  jz      short loc_1801C0D63
0x1801c0d5a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0d61  jmp     short loc_1801C0D71
0x1801c0d63  lea     rcx, qword_1803CE250; this
0x1801c0d6a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801c0d71  cmp     byte ptr [rcx+8], 0
0x1801c0d75  jz      short loc_1801C0D98
0x1801c0d77  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801c0d7c  cmp     [rax+7CCh], esi
0x1801c0d82  jz      short loc_1801C0D98
0x1801c0d84  mov     r9d, esi; int
0x1801c0d87  mov     r8d, 308h; int
0x1801c0d8d  mov     rdx, rbx; char *
0x1801c0d90  mov     rcx, rax; this
0x1801c0d93  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801c0d98  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801c0d9f  jb      loc_1801C13D0
0x1801c0da5  mov     edx, 1Eh
0x1801c0daa  jmp     loc_1801C0B6E
0x1801c0daf  cmp     [rsp+2B0h+var_270], 0
0x1801c0db4  lea     rbx, WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids
0x1801c0dbb  jz      loc_1801C0F52
0x1801c0dc1  cmp     cs:byte_1803CECE9, 10h
0x1801c0dc8  jb      short loc_1801C0DE5
0x1801c0dca  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c0dd1  mov     edx, 1Fh
0x1801c0dd6  mov     r9, rdi
0x1801c0dd9  mov     r8, rbx
0x1801c0ddc  mov     rcx, [rcx+38h]
0x1801c0de0  call    WPP_SF_q
0x1801c0de5  lea     r8, [rsp+2B0h+ppv]; ppv
0x1801c0dea  lea     rdx, IID_IMFContentProtectionManager; riid
0x1801c0df1  lea     rcx, [rbp+1B0h+var_48]; this
0x1801c0df8  call    ?UnMarshalInterface@CDCOMInterfaceMashallerHelper@@SAJAEAVCBinaryReader@@AEBU_GUID@@PEAPEAX@Z; CDCOMInterfaceMashallerHelper::UnMarshalInterface(CBinaryReader &,_GUID const &,void * *)
0x1801c0dfd  mov     esi, eax
0x1801c0dff  test    eax, eax
  ... truncated ...
```
