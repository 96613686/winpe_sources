# CWMArtistProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x18004b900`
- end: `0x18004c274`
- name: `?SetNativeValue@CWMArtistProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `2420`
- prototype: `int(CWMArtistProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800085a0`
- `0x18000faf4`
- `0x180011f08`
- `0x18001a330`
- `0x18001c280`
- `0x18004b900`
- `0x18004f410`
- `0x180057904`
- `0x180057fe4`
- `0x180058310`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004c03d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004c18b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004c03d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004c18b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b99d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bad5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bc04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bc8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bd18`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bda2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bede`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bfae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c05d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c0ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c1a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b99d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bad5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bc04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bc8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bd18`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bda2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bede`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bfae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c05d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c0ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c1a7`

## pseudocode

```c
__int64 __fastcall CWMArtistProperty::SetNativeValue(PROPVARIANT *this, struct tagPROPVARIANT *a2)
{
  __int64 *v4; // rcx
  HRESULT Element; // edi
  CallStackTracing *v6; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rdx
  int v9; // r15d
  unsigned int i; // r12d
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // ecx
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  int v19; // ecx
  __int64 v20; // rdx
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  PROPVARIANT *p_pvar; // rcx
  __int64 v36; // rdx
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  __int64 v48; // rdx
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  PROPVARIANT pvar; // [rsp+30h] [rbp-29h] BYREF
  PROPVARIANT pvarSrc; // [rsp+48h] [rbp-11h] BYREF
  PROPVARIANT v60; // [rsp+60h] [rbp+7h] BYREF
  PROPVARIANT pvarDest; // [rsp+78h] [rbp+1Fh] BYREF
  char v62; // [rsp+D0h] [rbp+77h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v62, "CWMArtistProperty::SetNativeValue", 902);
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  memset(&pvarDest, 0, sizeof(pvarDest));
  CMFPropVariant::Clear(&pvarDest);
  CMFPropVariant::Copy(&pvarDest, a2);
  if ( (pvarDest.vt & 0xFFF) != 0x1F )
  {
    v4 = (__int64 *)CallStackTracing::s_wpInstance;
    Element = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 4095);
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v4 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMArtistProperty::SetNativeValue", 912, -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v8 = 91;
LABEL_148:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, Element);
      goto LABEL_149;
    }
    goto LABEL_149;
  }
  if ( (pvarDest.vt & 0x1000) != 0 )
  {
    v9 = 0;
    for ( i = 0; i < CMFPropVariant::GetElementCount((CMFPropVariant *)&pvarDest); ++i )
    {
      memset(&pvar, 0, sizeof(pvar));
      memset(&v60, 0, sizeof(v60));
      Element = CMFPropVariant::GetElement((CMFPropVariant *)&pvarDest, i, &pvar);
      if ( Element < 0 )
      {
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
          if ( *((_DWORD *)v34 + 499) != Element )
            CallStackContext::TraceFailure(v34, "CWMArtistProperty::SetNativeValue", 921, Element);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v22 = 92;
LABEL_83:
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v22,
            WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
            this,
            Element);
        }
LABEL_84:
        CMFPropVariant::Clear(&v60);
        p_pvar = &pvar;
LABEL_85:
        CMFPropVariant::Clear(p_pvar);
        goto LABEL_149;
      }
      v12 = *pvar.bstrVal;
      if ( v9 )
      {
        v13 = v12 - 68;
        if ( !v13 )
        {
          v13 = *(unsigned __int16 *)(pvar.hVal.QuadPart + 2) - 67;
          if ( *(_WORD *)(pvar.hVal.QuadPart + 2) == 67 )
            v13 = *(unsigned __int16 *)(pvar.hVal.QuadPart + 4);
        }
        if ( v13 )
        {
          Element = CMFPropVariant::CreateString((CMFPropVariant *)&v60, 0x1Fu, L"AC");
          if ( Element < 0 )
          {
            v26 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
              CallStackTracing::s_wpInstance = v27;
              if ( v27
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
              {
                v26 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v26 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v26 + 8) )
            {
              v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
              if ( *((_DWORD *)v28 + 499) != Element )
                CallStackContext::TraceFailure(v28, "CWMArtistProperty::SetNativeValue", 941, Element);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v22 = 94;
              goto LABEL_83;
            }
            goto LABEL_84;
          }
          CMFPropVariant::AppendElement((CMFPropVariant *)&pvarSrc, &v60);
        }
        else
        {
          CMFPropVariant::Clear(&pvar);
          Element = CMFPropVariant::CreateString((CMFPropVariant *)&pvar, 0x1Fu, L"AC/DC");
          if ( Element < 0 )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
              CallStackTracing::s_wpInstance = v16;
              if ( v16
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
              {
                v15 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v15 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v15 + 8) )
            {
              v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
              if ( *((_DWORD *)v21 + 499) != Element )
                CallStackContext::TraceFailure(v21, "CWMArtistProperty::SetNativeValue", 934, Element);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v22 = 93;
              goto LABEL_83;
            }
            goto LABEL_84;
          }
        }
        Element = CMFPropVariant::AppendElement((CMFPropVariant *)&pvarSrc, &pvar);
        if ( Element < 0 )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v23 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v23 + 8) )
          {
            v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v25 + 499) != Element )
              CallStackContext::TraceFailure(v25, "CWMArtistProperty::SetNativeValue", 944, Element);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v22 = 95;
            goto LABEL_83;
          }
          goto LABEL_84;
        }
        v9 = 0;
      }
      else
      {
        v19 = v12 - 65;
        if ( !v19 )
        {
          v19 = *(unsigned __int16 *)(pvar.hVal.QuadPart + 2) - 67;
          if ( *(_WORD *)(pvar.hVal.QuadPart + 2) == 67 )
            v19 = *(unsigned __int16 *)(pvar.hVal.QuadPart + 4);
        }
        if ( v19 )
        {
          Element = CMFPropVariant::AppendElement((CMFPropVariant *)&pvarSrc, &pvar);
          if ( Element < 0 )
          {
            v29 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
              CallStackTracing::s_wpInstance = v30;
              if ( v30
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
              {
                v29 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v29 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v29 + 8) )
            {
              v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
              if ( *((_DWORD *)v31 + 499) != Element )
                CallStackContext::TraceFailure(v31, "CWMArtistProperty::SetNativeValue", 959, Element);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v22 = 96;
              goto LABEL_83;
            }
            goto LABEL_84;
          }
        }
        else
        {
          v9 = 1;
        }
      }
      CMFPropVariant::Clear(&v60);
      CMFPropVariant::Clear(&pvar);
    }
    if ( v9 )
    {
      memset(&v60, 0, sizeof(v60));
      CMFPropVariant::CreateString((CMFPropVariant *)&v60, 0x1Fu, L"AC");
      CMFPropVariant::AppendElement((CMFPropVariant *)&pvarSrc, &v60);
      CMFPropVariant::Clear(&v60);
    }
    if ( (pvarSrc.vt & 0x1000) != 0 && CMFPropVariant::GetElementCount((CMFPropVariant *)&pvarSrc) == 1 )
    {
      memset(&v60, 0, sizeof(v60));
      Element = CMFPropVariant::Copy(&v60, &pvarSrc);
      if ( Element < 0 )
      {
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
          CallStackTracing::s_wpInstance = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
          {
            v37 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v37 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
          if ( *((_DWORD *)v39 + 499) != Element )
            CallStackContext::TraceFailure(v39, "CWMArtistProperty::SetNativeValue", 981, Element);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_102;
        v40 = 97;
LABEL_101:
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v40,
          WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
          this,
          Element);
LABEL_102:
        p_pvar = &v60;
        goto LABEL_85;
      }
      CMFPropVariant::Clear(&pvarSrc);
      Element = CMFPropVariant::CreateString((CMFPropVariant *)&pvarSrc, 0x1Fu, *(const void **)v60.bstrblobVal.pData);
      if ( Element < 0 )
      {
        v42 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
          if ( *((_DWORD *)v44 + 499) != Element )
            CallStackContext::TraceFailure(v44, "CWMArtistProperty::SetNativeValue", 984, Element);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_102;
        v40 = 98;
        goto LABEL_101;
      }
      CMFPropVariant::Clear(&v60);
    }
LABEL_115:
    Element = PropVariantCopy(this + 5, &pvarSrc);
    if ( Element >= 0 )
    {
      Element = PropVariantCopy(this + 4, &pvarSrc);
      if ( Element < 0 )
      {
        v54 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53);
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v54 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v54 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v54 + 8) )
        {
          v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)v56 + 499) != Element )
            CallStackContext::TraceFailure(v56, "CWMArtistProperty::SetNativeValue", 996, Element);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v8 = 101;
          goto LABEL_148;
        }
      }
    }
    else
    {
      v46 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45);
        CallStackTracing::s_wpInstance = v47;
        if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
        {
          v46 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v46 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v46 + 8) )
      {
        v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
        if ( *((_DWORD *)v52 + 499) != Element )
          CallStackContext::TraceFailure(v52, "CWMArtistProperty::SetNativeValue", 995, Element);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = 100;
        goto LABEL_148;
      }
    }
    goto LABEL_149;
  }
  Element = CMFPropVariant::Copy(&pvarSrc, &pvarDest);
  if ( Element >= 0 )
    goto LABEL_115;
  v49 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
    CallStackTracing::s_wpInstance = v50;
    if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
    {
      v49 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v49 = &qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v49 + 8) )
  {
    v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
    if ( *((_DWORD *)v51 + 499) != Element )
      CallStackContext::TraceFailure(v51, "CWMArtistProperty::SetNativeValue", 992, Element);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v8 = 99;
    goto LABEL_148;
  }
LABEL_149:
  CMFPropVariant::Clear(&pvarDest);
  CMFPropVariant::Clear(&pvarSrc);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v62);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x18004b900  mov     [rsp-8+arg_0], rbx
0x18004b905  mov     [rsp-8+arg_8], rdi
0x18004b90a  push    rbp
0x18004b90b  push    r12
0x18004b90d  push    r13
0x18004b90f  push    r14
0x18004b911  push    r15
0x18004b913  lea     rbp, [rsp-37h]
0x18004b918  sub     rsp, 90h
0x18004b91f  mov     rbx, rdx
0x18004b922  lea     r13, aCwmartistprope; "CWMArtistProperty::SetNativeValue"
0x18004b929  mov     r14, rcx
0x18004b92c  mov     rdx, r13; char *
0x18004b92f  mov     r8d, 386h; int
0x18004b935  lea     rcx, [rbp+57h+arg_10]; this
0x18004b939  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004b93e  xor     eax, eax
0x18004b940  lea     rcx, [rbp+57h+pvarDest]; pvar
0x18004b944  xorps   xmm0, xmm0
0x18004b947  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x18004b94b  xorps   xmm1, xmm1
0x18004b94e  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x18004b952  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x18004b956  movups  xmmword ptr [rbp+57h+pvarDest], xmm1
0x18004b95a  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18004b95f  mov     rdx, rbx; pvarSrc
0x18004b962  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x18004b966  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x18004b96b  movzx   ecx, word ptr [rbp+57h+pvarDest]
0x18004b96f  mov     edx, 0FFFh
0x18004b974  movzx   eax, cx
0x18004b977  mov     r8d, 1Fh
0x18004b97d  and     ax, dx
0x18004b980  xor     ebx, ebx
0x18004b982  cmp     ax, r8w
0x18004b986  jz      loc_18004BA1B
0x18004b98c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b993  mov     edi, 8000FFFFh
0x18004b998  test    rcx, rcx
0x18004b99b  jnz     short loc_18004B9DE
0x18004b99d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b9a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b9aa  mov     rcx, rax
0x18004b9ad  test    rax, rax
0x18004b9b0  jz      short loc_18004B9D0
0x18004b9b2  mov     rax, [rax]
0x18004b9b5  mov     edx, 7F0h
0x18004b9ba  mov     rax, [rax+8]
0x18004b9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9c3  test    eax, eax
0x18004b9c5  jz      short loc_18004B9D0
0x18004b9c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b9ce  jmp     short loc_18004B9DE
0x18004b9d0  lea     rcx, qword_180069A90; this
0x18004b9d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b9de  cmp     [rcx+8], bl
0x18004b9e1  jz      short loc_18004BA04
0x18004b9e3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b9e8  cmp     [rax+7CCh], edi
0x18004b9ee  jz      short loc_18004BA04
0x18004b9f0  mov     r9d, edi; int
0x18004b9f3  mov     r8d, 390h; int
0x18004b9f9  mov     rdx, r13; char *
0x18004b9fc  mov     rcx, rax; this
0x18004b9ff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ba04  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004ba09  cmp     al, 1
0x18004ba0b  jb      loc_18004C23A
0x18004ba11  mov     edx, 5Bh ; '['
0x18004ba16  jmp     loc_18004C21C
0x18004ba1b  mov     edi, 1000h
0x18004ba20  and     cx, di
0x18004ba23  cmp     bx, cx
0x18004ba26  jz      loc_18004C09B
0x18004ba2c  mov     r15d, ebx
0x18004ba2f  mov     r12d, ebx
0x18004ba32  lea     rcx, [rbp+57h+pvarDest]; this
0x18004ba36  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x18004ba3b  cmp     r12d, eax
0x18004ba3e  jnb     loc_18004BE4C
0x18004ba44  xor     eax, eax
0x18004ba46  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18004ba4a  xorps   xmm0, xmm0
0x18004ba4d  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18004ba51  xorps   xmm1, xmm1
0x18004ba54  mov     qword ptr [rbp+57h+var_50+10h], rax
0x18004ba58  mov     edx, r12d; unsigned int
0x18004ba5b  lea     rcx, [rbp+57h+pvarDest]; this
0x18004ba5f  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18004ba63  movups  xmmword ptr [rbp+57h+var_50], xmm1
0x18004ba67  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x18004ba6c  mov     edi, eax
0x18004ba6e  test    eax, eax
0x18004ba70  js      loc_18004BD96
0x18004ba76  mov     rdx, qword ptr [rbp+57h+pvar+8]
0x18004ba7a  movzx   ecx, word ptr [rdx]
0x18004ba7d  test    r15d, r15d
0x18004ba80  jz      loc_18004BB5B
0x18004ba86  sub     ecx, 44h ; 'D'
0x18004ba89  jnz     short loc_18004BA9D
0x18004ba8b  movzx   ecx, word ptr [rdx+2]
0x18004ba8f  sub     ecx, 43h ; 'C'
0x18004ba92  jnz     short loc_18004BA9D
0x18004ba94  movzx   ecx, word ptr [rdx+4]
0x18004ba98  movzx   eax, bx
0x18004ba9b  sub     ecx, eax
0x18004ba9d  test    ecx, ecx
0x18004ba9f  jnz     short loc_18004BB13
0x18004baa1  lea     rcx, [rbp+57h+pvar]; pvar
0x18004baa5  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18004baaa  mov     edx, 1Fh; unsigned __int16
0x18004baaf  lea     r8, aAcDc; "AC/DC"
0x18004bab6  lea     rcx, [rbp+57h+pvar]; this
0x18004baba  call    ?CreateString@CMFPropVariant@@QEAAJGPEBX@Z; CMFPropVariant::CreateString(ushort,void const *)
0x18004babf  mov     edi, eax
0x18004bac1  test    eax, eax
0x18004bac3  jns     short loc_18004BB3F
0x18004bac5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bacc  test    rcx, rcx
0x18004bacf  jnz     loc_18004BBBB
0x18004bad5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004badb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bae2  mov     rcx, rax
0x18004bae5  test    rax, rax
0x18004bae8  jz      loc_18004BBAD
0x18004baee  mov     rax, [rax]
0x18004baf1  mov     edx, 7F0h
0x18004baf6  mov     rax, [rax+8]
0x18004bafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004baff  test    eax, eax
0x18004bb01  jz      loc_18004BBAD
0x18004bb07  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bb0e  jmp     loc_18004BBBB
0x18004bb13  mov     edx, 1Fh; unsigned __int16
0x18004bb18  lea     r8, aAc; "AC"
0x18004bb1f  lea     rcx, [rbp+57h+var_50]; this
0x18004bb23  call    ?CreateString@CMFPropVariant@@QEAAJGPEBX@Z; CMFPropVariant::CreateString(ushort,void const *)
0x18004bb28  mov     edi, eax
0x18004bb2a  test    eax, eax
0x18004bb2c  js      loc_18004BC82
0x18004bb32  lea     rdx, [rbp+57h+var_50]; struct tagPROPVARIANT *
0x18004bb36  lea     rcx, [rbp+57h+pvarSrc]; this
0x18004bb3a  call    ?AppendElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendElement(tagPROPVARIANT const *)
0x18004bb3f  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18004bb43  lea     rcx, [rbp+57h+pvarSrc]; this
0x18004bb47  call    ?AppendElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendElement(tagPROPVARIANT const *)
0x18004bb4c  mov     edi, eax
0x18004bb4e  test    eax, eax
0x18004bb50  js      loc_18004BBF8
0x18004bb56  mov     r15d, ebx
0x18004bb59  jmp     short loc_18004BB93
0x18004bb5b  sub     ecx, 41h ; 'A'
0x18004bb5e  jnz     short loc_18004BB72
0x18004bb60  movzx   ecx, word ptr [rdx+2]
0x18004bb64  sub     ecx, 43h ; 'C'
0x18004bb67  jnz     short loc_18004BB72
0x18004bb69  movzx   ecx, word ptr [rdx+4]
0x18004bb6d  movzx   eax, bx
0x18004bb70  sub     ecx, eax
0x18004bb72  test    ecx, ecx
0x18004bb74  jnz     short loc_18004BB7C
0x18004bb76  lea     r15d, [rcx+1]
0x18004bb7a  jmp     short loc_18004BB93
0x18004bb7c  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18004bb80  lea     rcx, [rbp+57h+pvarSrc]; this
0x18004bb84  call    ?AppendElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendElement(tagPROPVARIANT const *)
0x18004bb89  mov     edi, eax
0x18004bb8b  test    eax, eax
0x18004bb8d  js      loc_18004BD0C
0x18004bb93  lea     rcx, [rbp+57h+var_50]; pvar
0x18004bb97  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18004bb9c  lea     rcx, [rbp+57h+pvar]; pvar
0x18004bba0  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18004bba5  inc     r12d
0x18004bba8  jmp     loc_18004BA32
0x18004bbad  lea     rcx, qword_180069A90; this
0x18004bbb4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bbbb  cmp     [rcx+8], bl
0x18004bbbe  jz      short loc_18004BBE1
0x18004bbc0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004bbc5  cmp     [rax+7CCh], edi
0x18004bbcb  jz      short loc_18004BBE1
0x18004bbcd  mov     r9d, edi; int
0x18004bbd0  mov     r8d, 3A6h; int
0x18004bbd6  mov     rdx, r13; char *
0x18004bbd9  mov     rcx, rax; this
0x18004bbdc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004bbe1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004bbe6  cmp     al, 1
0x18004bbe8  jb      loc_18004BE35
0x18004bbee  mov     edx, 5Dh ; ']'
0x18004bbf3  jmp     loc_18004BE17
0x18004bbf8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bbff  test    rcx, rcx
0x18004bc02  jnz     short loc_18004BC45
0x18004bc04  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004bc0a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bc11  mov     rcx, rax
0x18004bc14  test    rax, rax
0x18004bc17  jz      short loc_18004BC37
0x18004bc19  mov     rax, [rax]
0x18004bc1c  mov     edx, 7F0h
0x18004bc21  mov     rax, [rax+8]
0x18004bc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc2a  test    eax, eax
0x18004bc2c  jz      short loc_18004BC37
0x18004bc2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bc35  jmp     short loc_18004BC45
0x18004bc37  lea     rcx, qword_180069A90; this
0x18004bc3e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bc45  cmp     [rcx+8], bl
0x18004bc48  jz      short loc_18004BC6B
0x18004bc4a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004bc4f  cmp     [rax+7CCh], edi
0x18004bc55  jz      short loc_18004BC6B
0x18004bc57  mov     r9d, edi; int
0x18004bc5a  mov     r8d, 3B0h; int
0x18004bc60  mov     rdx, r13; char *
0x18004bc63  mov     rcx, rax; this
0x18004bc66  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004bc6b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004bc70  cmp     al, 1
0x18004bc72  jb      loc_18004BE35
0x18004bc78  mov     edx, 5Fh ; '_'
0x18004bc7d  jmp     loc_18004BE17
0x18004bc82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bc89  test    rcx, rcx
0x18004bc8c  jnz     short loc_18004BCCF
0x18004bc8e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004bc94  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bc9b  mov     rcx, rax
0x18004bc9e  test    rax, rax
0x18004bca1  jz      short loc_18004BCC1
0x18004bca3  mov     rax, [rax]
0x18004bca6  mov     edx, 7F0h
0x18004bcab  mov     rax, [rax+8]
0x18004bcaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcb4  test    eax, eax
0x18004bcb6  jz      short loc_18004BCC1
0x18004bcb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bcbf  jmp     short loc_18004BCCF
0x18004bcc1  lea     rcx, qword_180069A90; this
0x18004bcc8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bccf  cmp     [rcx+8], bl
0x18004bcd2  jz      short loc_18004BCF5
0x18004bcd4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004bcd9  cmp     [rax+7CCh], edi
0x18004bcdf  jz      short loc_18004BCF5
0x18004bce1  mov     r9d, edi; int
0x18004bce4  mov     r8d, 3ADh; int
0x18004bcea  mov     rdx, r13; char *
0x18004bced  mov     rcx, rax; this
0x18004bcf0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004bcf5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004bcfa  cmp     al, 1
0x18004bcfc  jb      loc_18004BE35
0x18004bd02  mov     edx, 5Eh ; '^'
0x18004bd07  jmp     loc_18004BE17
0x18004bd0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bd13  test    rcx, rcx
0x18004bd16  jnz     short loc_18004BD59
0x18004bd18  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004bd1e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bd25  mov     rcx, rax
0x18004bd28  test    rax, rax
0x18004bd2b  jz      short loc_18004BD4B
0x18004bd2d  mov     rax, [rax]
0x18004bd30  mov     edx, 7F0h
0x18004bd35  mov     rax, [rax+8]
0x18004bd39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd3e  test    eax, eax
0x18004bd40  jz      short loc_18004BD4B
0x18004bd42  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bd49  jmp     short loc_18004BD59
0x18004bd4b  lea     rcx, qword_180069A90; this
0x18004bd52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bd59  cmp     [rcx+8], bl
0x18004bd5c  jz      short loc_18004BD7F
0x18004bd5e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004bd63  cmp     [rax+7CCh], edi
0x18004bd69  jz      short loc_18004BD7F
0x18004bd6b  mov     r9d, edi; int
0x18004bd6e  mov     r8d, 3BFh; int
0x18004bd74  mov     rdx, r13; char *
0x18004bd77  mov     rcx, rax; this
0x18004bd7a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004bd7f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004bd84  cmp     al, 1
0x18004bd86  jb      loc_18004BE35
0x18004bd8c  mov     edx, 60h ; '`'
0x18004bd91  jmp     loc_18004BE17
0x18004bd96  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bd9d  test    rcx, rcx
0x18004bda0  jnz     short loc_18004BDE3
0x18004bda2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004bda8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bdaf  mov     rcx, rax
0x18004bdb2  test    rax, rax
0x18004bdb5  jz      short loc_18004BDD5
0x18004bdb7  mov     rax, [rax]
  ... truncated ...
```
