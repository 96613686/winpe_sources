# CWMPropTranslator::CreateNamePropMapping(void)

- ea: `0x18023636c`
- end: `0x180236cd1`
- name: `?CreateNamePropMapping@CWMPropTranslator@@AEAAJXZ`
- size: `2405`
- prototype: `__int64 __fastcall(CWMPropTranslator *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x1801ceb30`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180093088`
- `0x1800ec0e0`
- `0x18012add8`
- `0x18023636c`
- `0x1802583a8`
- `0x18029e10c`
- `0x1802d6a98`
- `0x1802d7414`
- `0x1802d7520`
- `0x1802d764c`
- `0x1802d76f8`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236624`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802366ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236750`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802367e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18023687c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236912`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802369a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236a3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236ad4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236b6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236c05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236624`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802366ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236750`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802367e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18023687c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236912`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802369a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236a3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236ad4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236b6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180236c05`

## string_xrefs

- `0x1802363ff`: `CWMPropTranslator::CreateNamePropMapping`
- `0x180236682`: `CWMPropTranslator::CreateNamePropMapping`
- `0x180236718`: `CWMPropTranslator::CreateNamePropMapping`
- `0x1802367ae`: `CWMPropTranslator::CreateNamePropMapping`
- `0x180236844`: `CWMPropTranslator::CreateNamePropMapping`
- `0x1802368da`: `CWMPropTranslator::CreateNamePropMapping`
- `0x180236970`: `CWMPropTranslator::CreateNamePropMapping`
- `0x180236a06`: `CWMPropTranslator::CreateNamePropMapping`
- `0x180236a9c`: `CWMPropTranslator::CreateNamePropMapping`
- `0x180236b32`: `CWMPropTranslator::CreateNamePropMapping`
- `0x180236bc8`: `CWMPropTranslator::CreateNamePropMapping`
- `0x180236c63`: `CWMPropTranslator::CreateNamePropMapping`

## pseudocode

```c
__int64 __fastcall CWMPropTranslator::CreateNamePropMapping(CWMPropTranslator *this)
{
  int v2; // ebx
  unsigned int i; // r15d
  CMFProperty *v4; // rax
  CMFProperty *v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v66[32]; // [rsp+30h] [rbp-20h] BYREF
  char v67; // [rsp+90h] [rbp+40h] BYREF
  CMFProperty *v68; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  CTBucketHash<CMFBaseStringT<unsigned short>,CMFProperty *>::Initialize((char *)this + 24, 64);
  CTBucketHash<_tagpropertykey,CMFProperty *>::Initialize((char *)this + 400, 64);
  for ( i = 0; i < 0x7C; ++i )
  {
    CMFBaseStringT<unsigned short>::CMFBaseStringT<unsigned short>(v66, *((_QWORD *)&krgPKeyWMMap + 5 * i + 2));
    v4 = (CMFProperty *)operator new(0x78u);
    if ( v4 )
      v5 = CMFProperty::CMFProperty(v4, *((const struct _tagpropertykey **)&krgPKeyWMMap + 5 * i));
    else
      v5 = 0;
    v68 = v5;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v67,
      "CWMPropTranslator::CreateNamePropMapping",
      607);
    if ( !v5 )
    {
      v62 = (__int64 *)CallStackTracing::s_wpInstance;
      v2 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7);
        CallStackTracing::s_wpInstance = v63;
        if ( v63 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
        {
          v62 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v62 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v62 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CWMPropTranslator::CreateNamePropMapping",
            607,
            -2147024882);
      }
      if ( g_wppLevels )
      {
        v34 = 33;
LABEL_128:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, &WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids, this, v2);
      }
LABEL_129:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v67);
      CMFBaseStringT<char>::~CMFBaseStringT<char>(v66);
      return (unsigned int)v2;
    }
    v2 = (*(__int64 (__fastcall **)(CMFProperty *, __int128 *, _QWORD))(*(_QWORD *)v5 + 168LL))(
           v5,
           &MF_MD_SHELLMULTI,
           *((unsigned __int8 *)&krgPKeyWMMap + 40 * i + 10));
    if ( v2 < 0 )
    {
      v59 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9);
        CallStackTracing::s_wpInstance = v60;
        if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
        {
          v59 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v59 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v59 + 8) )
      {
        v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
        if ( *((_DWORD *)v61 + 499) != v2 )
          CallStackContext::TraceFailure(v61, "CWMPropTranslator::CreateNamePropMapping", 609, v2);
      }
      if ( g_wppLevels )
      {
        v34 = 34;
        goto LABEL_128;
      }
      goto LABEL_129;
    }
    v2 = (*(__int64 (__fastcall **)(CMFProperty *, __int128 *, _QWORD))(*(_QWORD *)v5 + 168LL))(
           v5,
           &MF_MD_FSDKMULTI,
           *((unsigned __int8 *)&krgPKeyWMMap + 40 * i + 26));
    if ( v2 < 0 )
    {
      v56 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11);
        CallStackTracing::s_wpInstance = v57;
        if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
        {
          v56 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v56 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v56 + 8) )
      {
        v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
        if ( *((_DWORD *)v58 + 499) != v2 )
          CallStackContext::TraceFailure(v58, "CWMPropTranslator::CreateNamePropMapping", 610, v2);
      }
      if ( g_wppLevels )
      {
        v34 = 35;
        goto LABEL_128;
      }
      goto LABEL_129;
    }
    v2 = (*(__int64 (__fastcall **)(CMFProperty *, __int128 *, _QWORD))(*(_QWORD *)v5 + 168LL))(
           v5,
           &MF_MD_SHELLTYPE,
           *((unsigned __int16 *)&krgPKeyWMMap + 20 * i + 4));
    if ( v2 < 0 )
    {
      v53 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13);
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
        if ( *((_DWORD *)v55 + 499) != v2 )
          CallStackContext::TraceFailure(v55, "CWMPropTranslator::CreateNamePropMapping", 611, v2);
      }
      if ( g_wppLevels )
      {
        v34 = 36;
        goto LABEL_128;
      }
      goto LABEL_129;
    }
    v2 = (*(__int64 (__fastcall **)(CMFProperty *, __int128 *, _QWORD))(*(_QWORD *)v5 + 168LL))(
           v5,
           &MF_MD_FSDKTYPE,
           *((unsigned __int16 *)&krgPKeyWMMap + 20 * i + 12));
    if ( v2 < 0 )
    {
      v50 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15);
        CallStackTracing::s_wpInstance = v51;
        if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
        {
          v50 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v50 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v50 + 8) )
      {
        v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
        if ( *((_DWORD *)v52 + 499) != v2 )
          CallStackContext::TraceFailure(v52, "CWMPropTranslator::CreateNamePropMapping", 612, v2);
      }
      if ( g_wppLevels )
      {
        v34 = 37;
        goto LABEL_128;
      }
      goto LABEL_129;
    }
    v2 = (*(__int64 (__fastcall **)(CMFProperty *, void *, _QWORD))(*(_QWORD *)v5 + 168LL))(
           v5,
           &MF_MD_ACCESSTYPE,
           *((unsigned int *)&krgPKeyWMMap + 10 * i + 7));
    if ( v2 < 0 )
    {
      v47 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
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
        if ( *((_DWORD *)v49 + 499) != v2 )
          CallStackContext::TraceFailure(v49, "CWMPropTranslator::CreateNamePropMapping", 613, v2);
      }
      if ( g_wppLevels )
      {
        v34 = 38;
        goto LABEL_128;
      }
      goto LABEL_129;
    }
    v2 = (*(__int64 (__fastcall **)(CMFProperty *, void *, _QWORD))(*(_QWORD *)v5 + 168LL))(
           v5,
           &MF_MD_PKEY_EXCEPTIONAL,
           *((unsigned __int8 *)&krgPKeyWMMap + 40 * i + 32));
    if ( v2 < 0 )
    {
      v44 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19);
        CallStackTracing::s_wpInstance = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
        {
          v44 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v44 + 8) )
      {
        v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
        if ( *((_DWORD *)v46 + 499) != v2 )
          CallStackContext::TraceFailure(v46, "CWMPropTranslator::CreateNamePropMapping", 614, v2);
      }
      if ( g_wppLevels )
      {
        v34 = 39;
        goto LABEL_128;
      }
      goto LABEL_129;
    }
    v2 = (*(__int64 (__fastcall **)(CMFProperty *, void *, _QWORD))(*(_QWORD *)v5 + 168LL))(
           v5,
           &MF_MD_TRANSFERRABLE,
           *((unsigned __int8 *)&krgPKeyWMMap + 40 * i + 33));
    if ( v2 < 0 )
    {
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21);
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)v43 + 499) != v2 )
          CallStackContext::TraceFailure(v43, "CWMPropTranslator::CreateNamePropMapping", 615, v2);
      }
      if ( g_wppLevels )
      {
        v34 = 40;
        goto LABEL_128;
      }
      goto LABEL_129;
    }
    v22 = *((_QWORD *)&krgPKeyWMMap + 5 * i);
    *(_OWORD *)((char *)v5 + 76) = *(_OWORD *)v22;
    *((_DWORD *)v5 + 23) = *(_DWORD *)(v22 + 16);
    v23 = CMFBaseStringT<unsigned short>::PContents(v66);
    v2 = (*(__int64 (__fastcall **)(CMFProperty *, void *, __int64))(v24 + 200))(v5, &MF_MD_NAME, v23);
    if ( v2 < 0 )
    {
      v38 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26);
        CallStackTracing::s_wpInstance = v39;
        if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
        {
          v38 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
        if ( *((_DWORD *)v40 + 499) != v2 )
          CallStackContext::TraceFailure(v40, "CWMPropTranslator::CreateNamePropMapping", 623, v2);
      }
      if ( g_wppLevels )
      {
        v34 = 41;
        goto LABEL_128;
      }
      goto LABEL_129;
    }
    v2 = CTBucketHash<CMFBaseStringT<unsigned short>,CMFProperty *>::Insert((char *)this + 24, v66, &v68);
    if ( v2 < 0 )
    {
      v35 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != v2 )
          CallStackContext::TraceFailure(v37, "CWMPropTranslator::CreateNamePropMapping", 625, v2);
      }
      if ( g_wppLevels )
      {
        v34 = 42;
        goto LABEL_128;
      }
      goto LABEL_129;
    }
    v2 = CTBucketHash<_tagpropertykey,CMFProperty *>::Insert((char *)this + 400, (char *)v5 + 76, &v68);
    if ( v2 < 0 )
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
        if ( *((_DWORD *)v33 + 499) != v2 )
          CallStackContext::TraceFailure(v33, "CWMPropTranslator::CreateNamePropMapping", 626, v2);
      }
      if ( g_wppLevels )
      {
        v34 = 43;
        goto LABEL_128;
      }
      goto LABEL_129;
    }
    (*(void (__fastcall **)(CMFProperty *))(*(_QWORD *)v5 + 8LL))(v5);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v67);
    CMFBaseStringT<char>::~CMFBaseStringT<char>(v66);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18023636c  mov     [rsp-38h+arg_10], rbx
0x180236371  push    rbp
0x180236372  push    rsi
0x180236373  push    rdi
0x180236374  push    r12
0x180236376  push    r13
0x180236378  push    r14
0x18023637a  push    r15
0x18023637c  mov     rbp, rsp
0x18023637f  sub     rsp, 50h
0x180236383  xor     r13d, r13d
0x180236386  mov     rsi, rcx
0x180236389  add     rcx, 18h
0x18023638d  mov     ebx, r13d
0x180236390  lea     edi, [r13+40h]
0x180236394  mov     edx, edi
0x180236396  call    ?Initialize@?$CTBucketHash@V?$CMFBaseStringT@G@@PEAVCMFProperty@@@@QEAAJKK@Z; CTBucketHash<CMFBaseStringT<ushort>,CMFProperty *>::Initialize(ulong,ulong)
0x18023639b  lea     rcx, [rsi+190h]
0x1802363a2  mov     edx, edi
0x1802363a4  call    ?Initialize@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAJKK@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Initialize(ulong,ulong)
0x1802363a9  mov     r15d, r13d
0x1802363ac  lea     rdi, ?krgPKeyWMMap@@3QBUPKEY_TO_WM_MAP@@B; PKEY_TO_WM_MAP const near * const krgPKeyWMMap
0x1802363b3  cmp     r15d, 7Ch ; '|'
0x1802363b7  jnb     loc_180236CB6
0x1802363bd  mov     eax, r15d
0x1802363c0  lea     rcx, [rbp+var_20]
0x1802363c4  lea     r14, [rax+rax*4]
0x1802363c8  mov     rdx, [rdi+r14*8+10h]
0x1802363cd  call    ??0?$CMFBaseStringT@G@@QEAA@PEBGJ@Z; CMFBaseStringT<ushort>::CMFBaseStringT<ushort>(ushort const *,long)
0x1802363d2  mov     ecx, 78h ; 'x'; Size
0x1802363d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802363dc  test    rax, rax
0x1802363df  jz      short loc_1802363F2
0x1802363e1  mov     rdx, [rdi+r14*8]; struct _tagpropertykey *
0x1802363e5  mov     rcx, rax; this
0x1802363e8  call    ??0CMFProperty@@QEAA@AEBU_tagpropertykey@@@Z; CMFProperty::CMFProperty(_tagpropertykey const &)
0x1802363ed  mov     rdi, rax
0x1802363f0  jmp     short loc_1802363F5
0x1802363f2  mov     rdi, r13
0x1802363f5  mov     r8d, 25Fh; int
0x1802363fb  mov     [rbp+arg_8], rdi
0x1802363ff  lea     rdx, aCwmproptransla_2; "CWMPropTranslator::CreateNamePropMappin"...
0x180236406  lea     rcx, [rbp+arg_0]; this
0x18023640a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18023640f  test    rdi, rdi
0x180236412  jz      loc_180236BF4
0x180236418  mov     rax, [rdi]
0x18023641b  lea     rcx, ?krgPKeyWMMap@@3QBUPKEY_TO_WM_MAP@@B; PKEY_TO_WM_MAP const near * const krgPKeyWMMap
0x180236422  movzx   r8d, byte ptr [rcx+r14*8+0Ah]
0x180236428  lea     rdx, MF_MD_SHELLMULTI
0x18023642f  mov     rcx, rdi
0x180236432  mov     rax, [rax+0A8h]
0x180236439  call    cs:__guard_dispatch_icall_fptr
0x18023643f  mov     ebx, eax
0x180236441  test    eax, eax
0x180236443  js      loc_180236B5E
0x180236449  mov     rax, [rdi]
0x18023644c  lea     rcx, ?krgPKeyWMMap@@3QBUPKEY_TO_WM_MAP@@B; PKEY_TO_WM_MAP const near * const krgPKeyWMMap
0x180236453  movzx   r8d, byte ptr [rcx+r14*8+1Ah]
0x180236459  lea     rdx, MF_MD_FSDKMULTI
0x180236460  mov     rcx, rdi
0x180236463  mov     rax, [rax+0A8h]
0x18023646a  call    cs:__guard_dispatch_icall_fptr
0x180236470  mov     ebx, eax
0x180236472  test    eax, eax
0x180236474  js      loc_180236AC8
0x18023647a  mov     rax, [rdi]
0x18023647d  lea     rcx, ?krgPKeyWMMap@@3QBUPKEY_TO_WM_MAP@@B; PKEY_TO_WM_MAP const near * const krgPKeyWMMap
0x180236484  movzx   r8d, word ptr [rcx+r14*8+8]
0x18023648a  lea     rdx, MF_MD_SHELLTYPE
0x180236491  mov     rcx, rdi
0x180236494  mov     rax, [rax+0A8h]
0x18023649b  call    cs:__guard_dispatch_icall_fptr
0x1802364a1  mov     ebx, eax
0x1802364a3  test    eax, eax
0x1802364a5  js      loc_180236A32
0x1802364ab  mov     rax, [rdi]
0x1802364ae  lea     rcx, ?krgPKeyWMMap@@3QBUPKEY_TO_WM_MAP@@B; PKEY_TO_WM_MAP const near * const krgPKeyWMMap
0x1802364b5  movzx   r8d, word ptr [rcx+r14*8+18h]
0x1802364bb  lea     rdx, MF_MD_FSDKTYPE
0x1802364c2  mov     rcx, rdi
0x1802364c5  mov     rax, [rax+0A8h]
0x1802364cc  call    cs:__guard_dispatch_icall_fptr
0x1802364d2  mov     ebx, eax
0x1802364d4  test    eax, eax
0x1802364d6  js      loc_18023699C
0x1802364dc  mov     rax, [rdi]
0x1802364df  lea     rcx, ?krgPKeyWMMap@@3QBUPKEY_TO_WM_MAP@@B; PKEY_TO_WM_MAP const near * const krgPKeyWMMap
0x1802364e6  mov     r8d, [rcx+r14*8+1Ch]
0x1802364eb  lea     rdx, MF_MD_ACCESSTYPE
0x1802364f2  mov     rcx, rdi
0x1802364f5  mov     rax, [rax+0A8h]
0x1802364fc  call    cs:__guard_dispatch_icall_fptr
0x180236502  mov     ebx, eax
0x180236504  test    eax, eax
0x180236506  js      loc_180236906
0x18023650c  mov     rax, [rdi]
0x18023650f  lea     rcx, ?krgPKeyWMMap@@3QBUPKEY_TO_WM_MAP@@B; PKEY_TO_WM_MAP const near * const krgPKeyWMMap
0x180236516  movzx   r8d, byte ptr [rcx+r14*8+20h]
0x18023651c  lea     rdx, MF_MD_PKEY_EXCEPTIONAL
0x180236523  mov     rcx, rdi
0x180236526  mov     rax, [rax+0A8h]
0x18023652d  call    cs:__guard_dispatch_icall_fptr
0x180236533  mov     ebx, eax
0x180236535  test    eax, eax
0x180236537  js      loc_180236870
0x18023653d  mov     rax, [rdi]
0x180236540  lea     rcx, ?krgPKeyWMMap@@3QBUPKEY_TO_WM_MAP@@B; PKEY_TO_WM_MAP const near * const krgPKeyWMMap
0x180236547  movzx   r8d, byte ptr [rcx+r14*8+21h]
0x18023654d  lea     rdx, MF_MD_TRANSFERRABLE
0x180236554  mov     rcx, rdi
0x180236557  mov     rax, [rax+0A8h]
0x18023655e  call    cs:__guard_dispatch_icall_fptr
0x180236564  mov     ebx, eax
0x180236566  test    eax, eax
0x180236568  js      loc_1802367DA
0x18023656e  lea     rax, ?krgPKeyWMMap@@3QBUPKEY_TO_WM_MAP@@B; PKEY_TO_WM_MAP const near * const krgPKeyWMMap
0x180236575  mov     rax, [rax+r14*8]
0x180236579  lea     rcx, [rbp+var_20]
0x18023657d  movups  xmm0, xmmword ptr [rax]
0x180236580  movups  xmmword ptr [rdi+4Ch], xmm0
0x180236584  mov     eax, [rax+10h]
0x180236587  mov     [rdi+5Ch], eax
0x18023658a  mov     r9, [rdi]
0x18023658d  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x180236592  mov     r8, rax
0x180236595  lea     rdx, MF_MD_NAME
0x18023659c  mov     rax, [r9+0C8h]
0x1802365a3  mov     rcx, rdi
0x1802365a6  call    cs:__guard_dispatch_icall_fptr
0x1802365ac  mov     ebx, eax
0x1802365ae  test    eax, eax
0x1802365b0  js      loc_180236744
0x1802365b6  lea     r8, [rbp+arg_8]
0x1802365ba  lea     rdx, [rbp+var_20]
0x1802365be  lea     rcx, [rsi+18h]
0x1802365c2  call    ?Insert@?$CTBucketHash@V?$CMFBaseStringT@G@@PEAVCMFProperty@@@@QEAAJAEBV?$CMFBaseStringT@G@@AEBQEAVCMFProperty@@@Z; CTBucketHash<CMFBaseStringT<ushort>,CMFProperty *>::Insert(CMFBaseStringT<ushort> const &,CMFProperty * const &)
0x1802365c7  mov     ebx, eax
0x1802365c9  test    eax, eax
0x1802365cb  js      loc_1802366AE
0x1802365d1  lea     r8, [rbp+arg_8]
0x1802365d5  lea     rdx, [rdi+4Ch]
0x1802365d9  lea     rcx, [rsi+190h]
0x1802365e0  call    ?Insert@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAJAEBU_tagpropertykey@@AEBQEAVCMFProperty@@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Insert(_tagpropertykey const &,CMFProperty * const &)
0x1802365e5  xor     r13d, r13d
0x1802365e8  mov     ebx, eax
0x1802365ea  test    eax, eax
0x1802365ec  js      short loc_180236618
0x1802365ee  mov     rax, [rdi]
0x1802365f1  mov     rcx, rdi
0x1802365f4  mov     rax, [rax+8]
0x1802365f8  call    cs:__guard_dispatch_icall_fptr
0x1802365fe  lea     rcx, [rbp+arg_0]; this
0x180236602  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180236607  lea     rcx, [rbp+var_20]
0x18023660b  call    ??1?$CMFBaseStringT@D@@QEAA@XZ; CMFBaseStringT<char>::~CMFBaseStringT<char>(void)
0x180236610  inc     r15d
0x180236613  jmp     loc_1802363AC
0x180236618  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18023661f  test    rcx, rcx
0x180236622  jnz     short loc_18023666C
0x180236624  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18023662b  nop     dword ptr [rax+rax+00h]
0x180236630  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180236637  mov     rcx, rax
0x18023663a  test    rax, rax
0x18023663d  jz      short loc_18023665E
0x18023663f  mov     rax, [rax]
0x180236642  mov     edx, 7F0h
0x180236647  mov     rax, [rax+8]
0x18023664b  call    cs:__guard_dispatch_icall_fptr
0x180236651  test    eax, eax
0x180236653  jz      short loc_18023665E
0x180236655  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18023665c  jmp     short loc_18023666C
0x18023665e  lea     rcx, qword_1803CE250; this
0x180236665  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18023666c  cmp     [rcx+8], r13b
0x180236670  jz      short loc_180236697
0x180236672  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180236677  cmp     [rax+7CCh], ebx
0x18023667d  jz      short loc_180236697
0x18023667f  mov     r9d, ebx; int
0x180236682  lea     rdx, aCwmproptransla_2; "CWMPropTranslator::CreateNamePropMappin"...
0x180236689  mov     r8d, 272h; int
0x18023668f  mov     rcx, rax; this
0x180236692  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180236697  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18023669e  jb      loc_180236CA4
0x1802366a4  mov     edx, 2Bh ; '+'
0x1802366a9  jmp     loc_180236C86
0x1802366ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802366b5  test    rcx, rcx
0x1802366b8  jnz     short loc_180236702
0x1802366ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802366c1  nop     dword ptr [rax+rax+00h]
0x1802366c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802366cd  mov     rcx, rax
0x1802366d0  test    rax, rax
0x1802366d3  jz      short loc_1802366F4
0x1802366d5  mov     rax, [rax]
0x1802366d8  mov     edx, 7F0h
0x1802366dd  mov     rax, [rax+8]
0x1802366e1  call    cs:__guard_dispatch_icall_fptr
0x1802366e7  test    eax, eax
0x1802366e9  jz      short loc_1802366F4
0x1802366eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802366f2  jmp     short loc_180236702
0x1802366f4  lea     rcx, qword_1803CE250; this
0x1802366fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180236702  cmp     byte ptr [rcx+8], 0
0x180236706  jz      short loc_18023672D
0x180236708  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18023670d  cmp     [rax+7CCh], ebx
0x180236713  jz      short loc_18023672D
0x180236715  mov     r9d, ebx; int
0x180236718  lea     rdx, aCwmproptransla_2; "CWMPropTranslator::CreateNamePropMappin"...
0x18023671f  mov     r8d, 271h; int
0x180236725  mov     rcx, rax; this
0x180236728  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18023672d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180236734  jb      loc_180236CA4
0x18023673a  mov     edx, 2Ah ; '*'
0x18023673f  jmp     loc_180236C86
0x180236744  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18023674b  test    rcx, rcx
0x18023674e  jnz     short loc_180236798
0x180236750  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180236757  nop     dword ptr [rax+rax+00h]
0x18023675c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180236763  mov     rcx, rax
0x180236766  test    rax, rax
0x180236769  jz      short loc_18023678A
0x18023676b  mov     rax, [rax]
0x18023676e  mov     edx, 7F0h
0x180236773  mov     rax, [rax+8]
0x180236777  call    cs:__guard_dispatch_icall_fptr
0x18023677d  test    eax, eax
0x18023677f  jz      short loc_18023678A
0x180236781  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180236788  jmp     short loc_180236798
0x18023678a  lea     rcx, qword_1803CE250; this
0x180236791  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180236798  cmp     byte ptr [rcx+8], 0
0x18023679c  jz      short loc_1802367C3
0x18023679e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802367a3  cmp     [rax+7CCh], ebx
0x1802367a9  jz      short loc_1802367C3
0x1802367ab  mov     r9d, ebx; int
0x1802367ae  lea     rdx, aCwmproptransla_2; "CWMPropTranslator::CreateNamePropMappin"...
0x1802367b5  mov     r8d, 26Fh; int
0x1802367bb  mov     rcx, rax; this
0x1802367be  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802367c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802367ca  jb      loc_180236CA4
0x1802367d0  mov     edx, 29h ; ')'
0x1802367d5  jmp     loc_180236C86
0x1802367da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802367e1  test    rcx, rcx
0x1802367e4  jnz     short loc_18023682E
0x1802367e6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802367ed  nop     dword ptr [rax+rax+00h]
0x1802367f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802367f9  mov     rcx, rax
0x1802367fc  test    rax, rax
0x1802367ff  jz      short loc_180236820
0x180236801  mov     rax, [rax]
0x180236804  mov     edx, 7F0h
0x180236809  mov     rax, [rax+8]
0x18023680d  call    cs:__guard_dispatch_icall_fptr
0x180236813  test    eax, eax
0x180236815  jz      short loc_180236820
0x180236817  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18023681e  jmp     short loc_18023682E
0x180236820  lea     rcx, qword_1803CE250; this
0x180236827  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18023682e  cmp     [rcx+8], r13b
0x180236832  jz      short loc_180236859
0x180236834  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180236839  cmp     [rax+7CCh], ebx
0x18023683f  jz      short loc_180236859
0x180236841  mov     r9d, ebx; int
0x180236844  lea     rdx, aCwmproptransla_2; "CWMPropTranslator::CreateNamePropMappin"...
0x18023684b  mov     r8d, 267h; int
0x180236851  mov     rcx, rax; this
0x180236854  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180236859  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180236860  jb      loc_180236CA4
0x180236866  mov     edx, 28h ; '('
0x18023686b  jmp     loc_180236C86
0x180236870  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180236877  test    rcx, rcx
0x18023687a  jnz     short loc_1802368C4
0x18023687c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180236883  nop     dword ptr [rax+rax+00h]
0x180236888  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18023688f  mov     rcx, rax
0x180236892  test    rax, rax
0x180236895  jz      short loc_1802368B6
0x180236897  mov     rax, [rax]
  ... truncated ...
```
