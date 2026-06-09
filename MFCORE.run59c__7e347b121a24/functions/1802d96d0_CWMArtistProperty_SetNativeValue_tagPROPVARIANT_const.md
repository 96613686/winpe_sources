# CWMArtistProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x1802d96d0`
- end: `0x1802da09d`
- name: `?SetNativeValue@CWMArtistProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `2509`
- prototype: `int(CWMArtistProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002c9ac`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x18019d300`
- `0x1801a7850`
- `0x1801cd57c`
- `0x180279370`
- `0x1802796b8`
- `0x18029e6a4`
- `0x1802d96d0`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1802d9e40`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1802d9fa6`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1802d9e40`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1802d9fa6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9764`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d98a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d99dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9a6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9aff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9b90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9cd3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9daa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9e66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9ece`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9fc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9764`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d98a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d99dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9a6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9aff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9b90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9cd3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9daa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9e66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9ece`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802d9fc8`

## pseudocode

```c
__int64 __fastcall CWMArtistProperty::SetNativeValue(PROPVARIANT *this, PROPVARIANT *a2)
{
  __int64 *v4; // rcx
  HRESULT Element; // edi
  CallStackTracing *v6; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rdx
  int v9; // r15d
  unsigned int i; // r12d
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // ecx
  int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // r8
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  struct tagPROPVARIANT *p_pvar; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  struct tagPROPVARIANT pvar; // [rsp+30h] [rbp-29h] BYREF
  PROPVARIANT pvarSrc[2]; // [rsp+48h] [rbp-11h] BYREF
  __int64 v70; // [rsp+58h] [rbp-1h]
  struct tagPROPVARIANT pvarDest; // [rsp+60h] [rbp+7h] BYREF
  PROPVARIANT v72[2]; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v73; // [rsp+88h] [rbp+2Fh]
  char v74; // [rsp+D0h] [rbp+77h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v74, "CWMArtistProperty::SetNativeValue", 902);
  v70 = 0;
  v73 = 0;
  *(_OWORD *)pvarSrc = 0;
  *(_OWORD *)v72 = 0;
  CMFPropVariant::operator=(v72, a2);
  if ( ((__int64)v72[0] & 0xFFF) != 0x1F )
  {
    v4 = (__int64 *)CallStackTracing::s_wpInstance;
    Element = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 4095, 31);
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v4 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMArtistProperty::SetNativeValue", 912, -2147418113);
    }
    if ( g_wppLevels )
    {
      v8 = 91;
LABEL_148:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        Element);
      goto LABEL_149;
    }
    goto LABEL_149;
  }
  if ( ((__int64)v72[0] & 0x1000) != 0 )
  {
    v9 = 0;
    for ( i = 0; i < CMFPropVariant::GetElementCount((CMFPropVariant *)v72); ++i )
    {
      memset(&pvar, 0, sizeof(pvar));
      memset(&pvarDest, 0, sizeof(pvarDest));
      Element = CMFPropVariant::GetElement((CMFPropVariant *)v72, i, (PROPVARIANT *)&pvar);
      if ( Element < 0 )
      {
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12);
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
          if ( *((_DWORD *)v39 + 499) != Element )
            CallStackContext::TraceFailure(v39, "CWMArtistProperty::SetNativeValue", 921, Element);
        }
        if ( g_wppLevels )
        {
          v27 = 92;
LABEL_83:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v27,
            &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
            this,
            Element);
        }
LABEL_84:
        CMFPropVariant::Clear((PROPVARIANT *)&pvarDest);
        p_pvar = &pvar;
LABEL_85:
        CMFPropVariant::Clear((PROPVARIANT *)p_pvar);
        goto LABEL_149;
      }
      v13 = *pvar.bstrVal;
      if ( v9 )
      {
        v14 = v13 - 68;
        if ( !v14 )
        {
          v14 = *(unsigned __int16 *)(pvar.hVal.QuadPart + 2) - 67;
          if ( *(_WORD *)(pvar.hVal.QuadPart + 2) == 67 )
            v14 = *(unsigned __int16 *)(pvar.hVal.QuadPart + 4);
        }
        if ( v14 )
        {
          Element = CMFPropVariant::CreateString((CMFPropVariant *)&pvarDest, 0x1Fu, L"AC");
          if ( Element < 0 )
          {
            v31 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20);
              CallStackTracing::s_wpInstance = v32;
              if ( v32
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
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
              if ( *((_DWORD *)v33 + 499) != Element )
                CallStackContext::TraceFailure(v33, "CWMArtistProperty::SetNativeValue", 941, Element);
            }
            if ( g_wppLevels )
            {
              v27 = 94;
              goto LABEL_83;
            }
            goto LABEL_84;
          }
          CMFPropVariant::AppendElement((CMFPropVariant *)pvarSrc, &pvarDest);
        }
        else
        {
          CMFPropVariant::Clear((PROPVARIANT *)&pvar);
          Element = CMFPropVariant::CreateString((CMFPropVariant *)&pvar, 0x1Fu, L"AC/DC");
          if ( Element < 0 )
          {
            v17 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16);
              CallStackTracing::s_wpInstance = v18;
              if ( v18
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
              {
                v17 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v17 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v17 + 8) )
            {
              v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
              if ( *((_DWORD *)v26 + 499) != Element )
                CallStackContext::TraceFailure(v26, "CWMArtistProperty::SetNativeValue", 934, Element);
            }
            if ( g_wppLevels )
            {
              v27 = 93;
              goto LABEL_83;
            }
            goto LABEL_84;
          }
        }
        Element = CMFPropVariant::AppendElement((CMFPropVariant *)pvarSrc, &pvar);
        if ( Element < 0 )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v28 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
            if ( *((_DWORD *)v30 + 499) != Element )
              CallStackContext::TraceFailure(v30, "CWMArtistProperty::SetNativeValue", 944, Element);
          }
          if ( g_wppLevels )
          {
            v27 = 95;
            goto LABEL_83;
          }
          goto LABEL_84;
        }
        v9 = 0;
      }
      else
      {
        v23 = v13 - 65;
        if ( !v23 )
        {
          v23 = *(unsigned __int16 *)(pvar.hVal.QuadPart + 2) - 67;
          if ( *(_WORD *)(pvar.hVal.QuadPart + 2) == 67 )
            v23 = *(unsigned __int16 *)(pvar.hVal.QuadPart + 4);
        }
        if ( v23 )
        {
          Element = CMFPropVariant::AppendElement((CMFPropVariant *)pvarSrc, &pvar);
          if ( Element < 0 )
          {
            v34 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
              CallStackTracing::s_wpInstance = v35;
              if ( v35
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
              {
                v34 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v34 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v34 + 8) )
            {
              v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
              if ( *((_DWORD *)v36 + 499) != Element )
                CallStackContext::TraceFailure(v36, "CWMArtistProperty::SetNativeValue", 959, Element);
            }
            if ( g_wppLevels )
            {
              v27 = 96;
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
      CMFPropVariant::Clear((PROPVARIANT *)&pvarDest);
      CMFPropVariant::Clear((PROPVARIANT *)&pvar);
    }
    if ( v9 )
    {
      memset(&pvarDest, 0, sizeof(pvarDest));
      CMFPropVariant::CreateString((CMFPropVariant *)&pvarDest, 0x1Fu, L"AC");
      CMFPropVariant::AppendElement((CMFPropVariant *)pvarSrc, &pvarDest);
      CMFPropVariant::Clear((PROPVARIANT *)&pvarDest);
    }
    if ( ((__int64)pvarSrc[0] & 0x1000) != 0 && CMFPropVariant::GetElementCount((CMFPropVariant *)pvarSrc) == 1 )
    {
      memset(&pvarDest, 0, sizeof(pvarDest));
      Element = CMFPropVariant::Copy((PROPVARIANT *)&pvarDest, pvarSrc);
      if ( Element < 0 )
      {
        v43 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42);
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v43 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v43 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
          if ( *((_DWORD *)v45 + 499) != Element )
            CallStackContext::TraceFailure(v45, "CWMArtistProperty::SetNativeValue", 981, Element);
        }
        if ( !g_wppLevels )
          goto LABEL_102;
        v46 = 97;
LABEL_101:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v46,
          &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
          this,
          Element);
LABEL_102:
        p_pvar = &pvarDest;
        goto LABEL_85;
      }
      CMFPropVariant::Clear(pvarSrc);
      Element = CMFPropVariant::CreateString(
                  (CMFPropVariant *)pvarSrc,
                  0x1Fu,
                  *(const void **)pvarDest.bstrblobVal.pData);
      if ( Element < 0 )
      {
        v49 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48);
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v49 + 8) )
        {
          v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
          if ( *((_DWORD *)v51 + 499) != Element )
            CallStackContext::TraceFailure(v51, "CWMArtistProperty::SetNativeValue", 984, Element);
        }
        if ( !g_wppLevels )
          goto LABEL_102;
        v46 = 98;
        goto LABEL_101;
      }
      CMFPropVariant::Clear((PROPVARIANT *)&pvarDest);
    }
LABEL_115:
    Element = PropVariantCopy(this + 15, pvarSrc);
    if ( Element >= 0 )
    {
      Element = PropVariantCopy(this + 12, pvarSrc);
      if ( Element < 0 )
      {
        v64 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62, v63);
          CallStackTracing::s_wpInstance = v65;
          if ( v65 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
          {
            v64 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v64 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v64 + 8) )
        {
          v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
          if ( *((_DWORD *)v66 + 499) != Element )
            CallStackContext::TraceFailure(v66, "CWMArtistProperty::SetNativeValue", 996, Element);
        }
        if ( g_wppLevels )
        {
          v8 = 101;
          goto LABEL_148;
        }
      }
    }
    else
    {
      v54 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53);
        CallStackTracing::s_wpInstance = v55;
        if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
        {
          v54 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v54 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v54 + 8) )
      {
        v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
        if ( *((_DWORD *)v61 + 499) != Element )
          CallStackContext::TraceFailure(v61, "CWMArtistProperty::SetNativeValue", 995, Element);
      }
      if ( g_wppLevels )
      {
        v8 = 100;
        goto LABEL_148;
      }
    }
    goto LABEL_149;
  }
  Element = CMFPropVariant::Copy(pvarSrc, v72);
  if ( Element >= 0 )
    goto LABEL_115;
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
    if ( *((_DWORD *)v60 + 499) != Element )
      CallStackContext::TraceFailure(v60, "CWMArtistProperty::SetNativeValue", 992, Element);
  }
  if ( g_wppLevels )
  {
    v8 = 99;
    goto LABEL_148;
  }
LABEL_149:
  CMFPropVariant::Clear(v72);
  CMFPropVariant::Clear(pvarSrc);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v74);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x1802d96d0  mov     [rsp-8+arg_0], rbx
0x1802d96d5  mov     [rsp-8+arg_8], rdi
0x1802d96da  push    rbp
0x1802d96db  push    r12
0x1802d96dd  push    r13
0x1802d96df  push    r14
0x1802d96e1  push    r15
0x1802d96e3  lea     rbp, [rsp-37h]
0x1802d96e8  sub     rsp, 90h
0x1802d96ef  mov     rbx, rdx
0x1802d96f2  lea     r13, aCwmartistprope; "CWMArtistProperty::SetNativeValue"
0x1802d96f9  mov     r14, rcx
0x1802d96fc  mov     rdx, r13; char *
0x1802d96ff  mov     r8d, 386h; int
0x1802d9705  lea     rcx, [rbp+57h+arg_10]; this
0x1802d9709  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802d970e  xor     eax, eax
0x1802d9710  lea     rcx, [rbp+57h+var_38]; pvarDest
0x1802d9714  xorps   xmm0, xmm0
0x1802d9717  mov     [rbp+57h+var_58], rax
0x1802d971b  xorps   xmm1, xmm1
0x1802d971e  mov     [rbp+57h+var_28], rax
0x1802d9722  mov     rdx, rbx; pvarSrc
0x1802d9725  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x1802d9729  movups  xmmword ptr [rbp+57h+var_38], xmm1
0x1802d972d  call    ??4CMFPropVariant@@QEAAAEAV0@AEBV0@@Z; CMFPropVariant::operator=(CMFPropVariant const &)
0x1802d9732  movzx   ecx, word ptr [rbp+57h+var_38]
0x1802d9736  mov     edx, 0FFFh
0x1802d973b  movzx   eax, cx
0x1802d973e  mov     r8d, 1Fh
0x1802d9744  and     ax, dx
0x1802d9747  xor     ebx, ebx
0x1802d9749  cmp     ax, r8w
0x1802d974d  jz      loc_1802D97E9
0x1802d9753  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d975a  mov     edi, 8000FFFFh
0x1802d975f  test    rcx, rcx
0x1802d9762  jnz     short loc_1802D97AC
0x1802d9764  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802d976b  nop     dword ptr [rax+rax+00h]
0x1802d9770  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9777  mov     rcx, rax
0x1802d977a  test    rax, rax
0x1802d977d  jz      short loc_1802D979E
0x1802d977f  mov     rax, [rax]
0x1802d9782  mov     edx, 7F0h
0x1802d9787  mov     rax, [rax+8]
0x1802d978b  call    cs:__guard_dispatch_icall_fptr
0x1802d9791  test    eax, eax
0x1802d9793  jz      short loc_1802D979E
0x1802d9795  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d979c  jmp     short loc_1802D97AC
0x1802d979e  lea     rcx, qword_1803CE250; this
0x1802d97a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d97ac  cmp     [rcx+8], bl
0x1802d97af  jz      short loc_1802D97D2
0x1802d97b1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802d97b6  cmp     [rax+7CCh], edi
0x1802d97bc  jz      short loc_1802D97D2
0x1802d97be  mov     r9d, edi; int
0x1802d97c1  mov     r8d, 390h; int
0x1802d97c7  mov     rdx, r13; char *
0x1802d97ca  mov     rcx, rax; this
0x1802d97cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802d97d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802d97d9  jb      loc_1802DA062
0x1802d97df  mov     edx, 5Bh ; '['
0x1802d97e4  jmp     loc_1802DA044
0x1802d97e9  mov     edi, 1000h
0x1802d97ee  and     cx, di
0x1802d97f1  cmp     bx, cx
0x1802d97f4  jz      loc_1802D9EAB
0x1802d97fa  mov     r15d, ebx
0x1802d97fd  mov     r12d, ebx
0x1802d9800  lea     rcx, [rbp+57h+var_38]; this
0x1802d9804  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x1802d9809  cmp     r12d, eax
0x1802d980c  jnb     loc_1802D9C41
0x1802d9812  xor     eax, eax
0x1802d9814  lea     r8, [rbp+57h+pvar]; pvarDest
0x1802d9818  xorps   xmm0, xmm0
0x1802d981b  mov     [rbp+57h+var_70], rax
0x1802d981f  xorps   xmm1, xmm1
0x1802d9822  mov     [rbp+57h+var_40], rax
0x1802d9826  mov     edx, r12d; unsigned int
0x1802d9829  lea     rcx, [rbp+57h+var_38]; this
0x1802d982d  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1802d9831  movups  xmmword ptr [rbp+57h+pvarDest], xmm1
0x1802d9835  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x1802d983a  mov     edi, eax
0x1802d983c  test    eax, eax
0x1802d983e  js      loc_1802D9B84
0x1802d9844  mov     rdx, [rbp+57h+pvar+8]
0x1802d9848  movzx   ecx, word ptr [rdx]
0x1802d984b  test    r15d, r15d
0x1802d984e  jz      loc_1802D9934
0x1802d9854  sub     ecx, 44h ; 'D'
0x1802d9857  jnz     short loc_1802D986B
0x1802d9859  movzx   ecx, word ptr [rdx+2]
0x1802d985d  sub     ecx, 43h ; 'C'
0x1802d9860  jnz     short loc_1802D986B
0x1802d9862  movzx   ecx, word ptr [rdx+4]
0x1802d9866  movzx   eax, bx
0x1802d9869  sub     ecx, eax
0x1802d986b  test    ecx, ecx
0x1802d986d  jnz     short loc_1802D98EC
0x1802d986f  lea     rcx, [rbp+57h+pvar]; pvar
0x1802d9873  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1802d9878  mov     edx, 1Fh; unsigned __int16
0x1802d987d  lea     r8, aAcDc; "AC/DC"
0x1802d9884  lea     rcx, [rbp+57h+pvar]; this
0x1802d9888  call    ?CreateString@CMFPropVariant@@QEAAJGPEBX@Z; CMFPropVariant::CreateString(ushort,void const *)
0x1802d988d  mov     edi, eax
0x1802d988f  test    eax, eax
0x1802d9891  jns     loc_1802D9918
0x1802d9897  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d989e  test    rcx, rcx
0x1802d98a1  jnz     loc_1802D9994
0x1802d98a7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802d98ae  nop     dword ptr [rax+rax+00h]
0x1802d98b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d98ba  mov     rcx, rax
0x1802d98bd  test    rax, rax
0x1802d98c0  jz      loc_1802D9986
0x1802d98c6  mov     rax, [rax]
0x1802d98c9  mov     edx, 7F0h
0x1802d98ce  mov     rax, [rax+8]
0x1802d98d2  call    cs:__guard_dispatch_icall_fptr
0x1802d98d8  test    eax, eax
0x1802d98da  jz      loc_1802D9986
0x1802d98e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d98e7  jmp     loc_1802D9994
0x1802d98ec  mov     edx, 1Fh; unsigned __int16
0x1802d98f1  lea     r8, aAc; "AC"
0x1802d98f8  lea     rcx, [rbp+57h+pvarDest]; this
0x1802d98fc  call    ?CreateString@CMFPropVariant@@QEAAJGPEBX@Z; CMFPropVariant::CreateString(ushort,void const *)
0x1802d9901  mov     edi, eax
0x1802d9903  test    eax, eax
0x1802d9905  js      loc_1802D9A62
0x1802d990b  lea     rdx, [rbp+57h+pvarDest]; struct tagPROPVARIANT *
0x1802d990f  lea     rcx, [rbp+57h+pvarSrc]; this
0x1802d9913  call    ?AppendElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendElement(tagPROPVARIANT const *)
0x1802d9918  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x1802d991c  lea     rcx, [rbp+57h+pvarSrc]; this
0x1802d9920  call    ?AppendElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendElement(tagPROPVARIANT const *)
0x1802d9925  mov     edi, eax
0x1802d9927  test    eax, eax
0x1802d9929  js      loc_1802D99D1
0x1802d992f  mov     r15d, ebx
0x1802d9932  jmp     short loc_1802D996C
0x1802d9934  sub     ecx, 41h ; 'A'
0x1802d9937  jnz     short loc_1802D994B
0x1802d9939  movzx   ecx, word ptr [rdx+2]
0x1802d993d  sub     ecx, 43h ; 'C'
0x1802d9940  jnz     short loc_1802D994B
0x1802d9942  movzx   ecx, word ptr [rdx+4]
0x1802d9946  movzx   eax, bx
0x1802d9949  sub     ecx, eax
0x1802d994b  test    ecx, ecx
0x1802d994d  jnz     short loc_1802D9955
0x1802d994f  lea     r15d, [rcx+1]
0x1802d9953  jmp     short loc_1802D996C
0x1802d9955  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x1802d9959  lea     rcx, [rbp+57h+pvarSrc]; this
0x1802d995d  call    ?AppendElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendElement(tagPROPVARIANT const *)
0x1802d9962  mov     edi, eax
0x1802d9964  test    eax, eax
0x1802d9966  js      loc_1802D9AF3
0x1802d996c  lea     rcx, [rbp+57h+pvarDest]; pvar
0x1802d9970  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1802d9975  lea     rcx, [rbp+57h+pvar]; pvar
0x1802d9979  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1802d997e  inc     r12d
0x1802d9981  jmp     loc_1802D9800
0x1802d9986  lea     rcx, qword_1803CE250; this
0x1802d998d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9994  cmp     [rcx+8], bl
0x1802d9997  jz      short loc_1802D99BA
0x1802d9999  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802d999e  cmp     [rax+7CCh], edi
0x1802d99a4  jz      short loc_1802D99BA
0x1802d99a6  mov     r9d, edi; int
0x1802d99a9  mov     r8d, 3A6h; int
0x1802d99af  mov     rdx, r13; char *
0x1802d99b2  mov     rcx, rax; this
0x1802d99b5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802d99ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802d99c1  jb      loc_1802D9C2A
0x1802d99c7  mov     edx, 5Dh ; ']'
0x1802d99cc  jmp     loc_1802D9C0C
0x1802d99d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d99d8  test    rcx, rcx
0x1802d99db  jnz     short loc_1802D9A25
0x1802d99dd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802d99e4  nop     dword ptr [rax+rax+00h]
0x1802d99e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d99f0  mov     rcx, rax
0x1802d99f3  test    rax, rax
0x1802d99f6  jz      short loc_1802D9A17
0x1802d99f8  mov     rax, [rax]
0x1802d99fb  mov     edx, 7F0h
0x1802d9a00  mov     rax, [rax+8]
0x1802d9a04  call    cs:__guard_dispatch_icall_fptr
0x1802d9a0a  test    eax, eax
0x1802d9a0c  jz      short loc_1802D9A17
0x1802d9a0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9a15  jmp     short loc_1802D9A25
0x1802d9a17  lea     rcx, qword_1803CE250; this
0x1802d9a1e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9a25  cmp     [rcx+8], bl
0x1802d9a28  jz      short loc_1802D9A4B
0x1802d9a2a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802d9a2f  cmp     [rax+7CCh], edi
0x1802d9a35  jz      short loc_1802D9A4B
0x1802d9a37  mov     r9d, edi; int
0x1802d9a3a  mov     r8d, 3B0h; int
0x1802d9a40  mov     rdx, r13; char *
0x1802d9a43  mov     rcx, rax; this
0x1802d9a46  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802d9a4b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802d9a52  jb      loc_1802D9C2A
0x1802d9a58  mov     edx, 5Fh ; '_'
0x1802d9a5d  jmp     loc_1802D9C0C
0x1802d9a62  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9a69  test    rcx, rcx
0x1802d9a6c  jnz     short loc_1802D9AB6
0x1802d9a6e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802d9a75  nop     dword ptr [rax+rax+00h]
0x1802d9a7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9a81  mov     rcx, rax
0x1802d9a84  test    rax, rax
0x1802d9a87  jz      short loc_1802D9AA8
0x1802d9a89  mov     rax, [rax]
0x1802d9a8c  mov     edx, 7F0h
0x1802d9a91  mov     rax, [rax+8]
0x1802d9a95  call    cs:__guard_dispatch_icall_fptr
0x1802d9a9b  test    eax, eax
0x1802d9a9d  jz      short loc_1802D9AA8
0x1802d9a9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9aa6  jmp     short loc_1802D9AB6
0x1802d9aa8  lea     rcx, qword_1803CE250; this
0x1802d9aaf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9ab6  cmp     [rcx+8], bl
0x1802d9ab9  jz      short loc_1802D9ADC
0x1802d9abb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802d9ac0  cmp     [rax+7CCh], edi
0x1802d9ac6  jz      short loc_1802D9ADC
0x1802d9ac8  mov     r9d, edi; int
0x1802d9acb  mov     r8d, 3ADh; int
0x1802d9ad1  mov     rdx, r13; char *
0x1802d9ad4  mov     rcx, rax; this
0x1802d9ad7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802d9adc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802d9ae3  jb      loc_1802D9C2A
0x1802d9ae9  mov     edx, 5Eh ; '^'
0x1802d9aee  jmp     loc_1802D9C0C
0x1802d9af3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9afa  test    rcx, rcx
0x1802d9afd  jnz     short loc_1802D9B47
0x1802d9aff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802d9b06  nop     dword ptr [rax+rax+00h]
0x1802d9b0b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9b12  mov     rcx, rax
0x1802d9b15  test    rax, rax
0x1802d9b18  jz      short loc_1802D9B39
0x1802d9b1a  mov     rax, [rax]
0x1802d9b1d  mov     edx, 7F0h
0x1802d9b22  mov     rax, [rax+8]
0x1802d9b26  call    cs:__guard_dispatch_icall_fptr
0x1802d9b2c  test    eax, eax
0x1802d9b2e  jz      short loc_1802D9B39
0x1802d9b30  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9b37  jmp     short loc_1802D9B47
0x1802d9b39  lea     rcx, qword_1803CE250; this
0x1802d9b40  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9b47  cmp     [rcx+8], bl
0x1802d9b4a  jz      short loc_1802D9B6D
0x1802d9b4c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802d9b51  cmp     [rax+7CCh], edi
0x1802d9b57  jz      short loc_1802D9B6D
0x1802d9b59  mov     r9d, edi; int
0x1802d9b5c  mov     r8d, 3BFh; int
0x1802d9b62  mov     rdx, r13; char *
0x1802d9b65  mov     rcx, rax; this
0x1802d9b68  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802d9b6d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802d9b74  jb      loc_1802D9C2A
0x1802d9b7a  mov     edx, 60h ; '`'
0x1802d9b7f  jmp     loc_1802D9C0C
0x1802d9b84  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9b8b  test    rcx, rcx
0x1802d9b8e  jnz     short loc_1802D9BD8
0x1802d9b90  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802d9b97  nop     dword ptr [rax+rax+00h]
0x1802d9b9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802d9ba3  mov     rcx, rax
0x1802d9ba6  test    rax, rax
0x1802d9ba9  jz      short loc_1802D9BCA
0x1802d9bab  mov     rax, [rax]
0x1802d9bae  mov     edx, 7F0h
  ... truncated ...
```
