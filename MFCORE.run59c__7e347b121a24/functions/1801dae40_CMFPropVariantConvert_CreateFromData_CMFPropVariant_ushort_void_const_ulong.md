# CMFPropVariantConvert::CreateFromData(CMFPropVariant *,ushort,void const *,ulong)

- ea: `0x1801dae40`
- end: `0x1801db8cc`
- name: `?CreateFromData@CMFPropVariantConvert@@SAJPEAVCMFPropVariant@@GPEBXK@Z`
- size: `2700`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar, unsigned __int16, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18021cf40`

## callees

- `0x18002c9ac`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x18017d0d8`
- `0x1801dae40`
- `0x180344ce4`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801db663`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801db64f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801db64f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801db1d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801db29f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801db37c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801db581`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801db1d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801db29f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801db37c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801db581`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801daeaf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dafe9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db12a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db208`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db2cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db3ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db45c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db4f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db5b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db692`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db722`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db810`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801daeaf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dafe9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db12a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db208`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db2cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db3ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db45c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db4f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db5b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db692`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db722`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801db810`

## string_xrefs

- `0x1801dae5c`: `CMFPropVariantConvert::CreateFromData`
- `0x1801db329`: `CMFPropVariantConvert::CreateFromData`

## pseudocode

```c
__int64 __fastcall CMFPropVariantConvert::CreateFromData(
        PROPVARIANT *pvar,
        unsigned __int16 a2,
        _BYTE *a3,
        unsigned int a4)
{
  SIZE_T cchWideChar; // rsi
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 *v10; // rcx
  signed int v11; // ebx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rcx
  unsigned __int16 **v29; // rdi
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  __int64 *v38; // rcx
  int v39; // edi
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  _OWORD *v43; // rax
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  void *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  PROPVARIANT *v53; // rcx
  _WORD *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 v63; // rdx
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  void *lpWideCharStr; // rax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  signed int LastError; // eax
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 *v76; // rcx
  CallStackTracing *v77; // rax
  struct CallStackContext *v78; // rax
  CallStackTracing *v79; // rax
  struct CallStackContext *v80; // rax
  __int16 v81; // r14
  __int64 *v82; // rcx
  CallStackTracing *v83; // rax
  struct CallStackContext *v84; // rax
  char v86; // [rsp+80h] [rbp+8h] BYREF

  cchWideChar = a4;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v86, "CMFPropVariantConvert::CreateFromData", 799);
  if ( !*(_WORD *)pvar )
  {
    v9 = a2;
    *(_WORD *)pvar = a2;
    if ( (a2 & 0x1000) != 0 )
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      v11 = -1072875797;
      if ( !CallStackTracing::s_wpInstance )
      {
        LOWORD(v9) = a2 & 0x1000;
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v8);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875797 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMFPropVariantConvert::CreateFromData",
            825,
            -1072875797);
      }
      if ( g_wppLevels )
      {
        v14 = 56;
LABEL_182:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, 0, v11);
        goto LABEL_183;
      }
      goto LABEL_183;
    }
    v15 = 8;
    if ( (_DWORD)cchWideChar )
    {
      v16 = 0;
      if ( a2 == 11 )
      {
        LODWORD(v28) = cchWideChar;
        while ( (_DWORD)v28 )
        {
          v28 = (unsigned int)(v28 - 1);
          if ( a3[v28] )
          {
            v16 = 0xFFFFFFFFLL;
            break;
          }
        }
LABEL_18:
        v17 = a2 & 0xFFF;
        v11 = 0;
        if ( v17 <= 0x13 )
        {
          if ( v17 == 19 )
            goto LABEL_28;
          v18 = v17 - 2;
          if ( !v18 )
            goto LABEL_28;
          v19 = v18 - 1;
          if ( !v19 )
            goto LABEL_28;
          v20 = v19 - 6;
          if ( !v20 )
            goto LABEL_28;
          v21 = v20 - 2;
          if ( !v21 )
          {
            v29 = (unsigned __int16 **)(pvar + 1);
            *((_WORD *)pvar + 4) = v16;
            goto LABEL_168;
          }
          v22 = v21 - 2;
          if ( !v22 )
            goto LABEL_28;
          v23 = v22 - 1;
          if ( !v23 )
          {
            if ( (_DWORD)cchWideChar != 16 )
              goto LABEL_29;
            v29 = (unsigned __int16 **)(pvar + 1);
            *(_OWORD *)pvar = *(_OWORD *)a3;
LABEL_168:
            v81 = *(_WORD *)pvar & 0xFFF;
            if ( (v81 == 9 || v81 == 13) && *v29 )
              (*(void (__fastcall **)(unsigned __int16 *, __int64, __int64))(*(_QWORD *)*v29 + 8LL))(*v29, v16, v15);
            goto LABEL_183;
          }
          v24 = v23 - 2;
          if ( !v24 || v24 - 1 <= 1 )
            goto LABEL_28;
          goto LABEL_59;
        }
        v30 = v17 - 20;
        if ( !v30 )
          goto LABEL_28;
        v31 = v30 - 1;
        if ( !v31 )
          goto LABEL_28;
        v32 = v31 - 1;
        if ( !v32 )
          goto LABEL_28;
        v33 = v32 - 1;
        if ( !v33 )
          goto LABEL_28;
        v34 = v33 - 7;
        if ( v34 )
        {
          v35 = v34 - 1;
          if ( v35 )
          {
            v36 = v35 - 33;
            if ( v36 )
            {
              v37 = v36 - 1;
              if ( v37 )
              {
                if ( v37 != 7 )
                {
LABEL_59:
                  v38 = (__int64 *)CallStackTracing::s_wpInstance;
                  v39 = -2147024809;
                  v11 = -2147024809;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, 8);
                    CallStackTracing::s_wpInstance = v40;
                    if ( v40
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
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
                    v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
                    if ( *((_DWORD *)v41 + 499) != -2147024809 )
                      CallStackContext::TraceFailure(v41, "CMFPropVariantConvert::CreateFromData", 970, -2147024809);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_30;
                  v42 = 66;
                  goto LABEL_69;
                }
                if ( (_DWORD)cchWideChar != 16 )
                  goto LABEL_29;
                v43 = CoTaskMemAlloc(0x10u);
                v29 = (unsigned __int16 **)(pvar + 1);
                pvar[1] = v43;
                if ( v43 )
                {
                  *v43 = *(_OWORD *)a3;
                  goto LABEL_168;
                }
                v44 = (__int64 *)CallStackTracing::s_wpInstance;
                v39 = -2147024882;
                v11 = -2147024882;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v15);
                  CallStackTracing::s_wpInstance = v45;
                  if ( v45
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
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
                  if ( *((_DWORD *)v46 + 499) != -2147024882 )
                    CallStackContext::TraceFailure(v46, "CMFPropVariantConvert::CreateFromData", 927, -2147024882);
                }
                if ( !g_wppLevels )
                  goto LABEL_30;
                v42 = 65;
              }
              else
              {
                v47 = CoTaskMemAlloc(cchWideChar);
                pvar[2] = v47;
                if ( v47 )
                {
                  v29 = (unsigned __int16 **)(pvar + 1);
                  v53 = (PROPVARIANT *)v47;
                  *((_DWORD *)pvar + 2) = cchWideChar;
LABEL_167:
                  memcpy_0(v53, a3, cchWideChar);
                  goto LABEL_168;
                }
                v50 = (__int64 *)CallStackTracing::s_wpInstance;
                v39 = -2147024882;
                v11 = -2147024882;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48, v49);
                  CallStackTracing::s_wpInstance = v51;
                  if ( v51
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
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
                  if ( *((_DWORD *)v52 + 499) != -2147024882 )
                    CallStackContext::TraceFailure(v52, "CMFPropVariantConvert::CreateFromData", 914, -2147024882);
                }
                if ( !g_wppLevels )
                  goto LABEL_30;
                v42 = 64;
              }
LABEL_69:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v42,
                &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                0,
                v39);
              goto LABEL_30;
            }
LABEL_28:
            if ( (unsigned int)cchWideChar > 8 )
            {
LABEL_29:
              v11 = -2147024809;
LABEL_30:
              CMFPropVariant::Clear(pvar);
              goto LABEL_183;
            }
            v29 = (unsigned __int16 **)(pvar + 1);
            v53 = pvar + 1;
            goto LABEL_167;
          }
          if ( (cchWideChar & 1) != 0 || (unsigned int)cchWideChar < 2 )
          {
            v64 = (__int64 *)CallStackTracing::s_wpInstance;
            v39 = -2147024809;
            v11 = -2147024809;
            if ( !CallStackTracing::s_wpInstance )
            {
              v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, 8);
              CallStackTracing::s_wpInstance = v65;
              if ( v65
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
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
              if ( *((_DWORD *)v66 + 499) != -2147024809 )
                CallStackContext::TraceFailure(v66, "CMFPropVariantConvert::CreateFromData", 901, -2147024809);
            }
            if ( !g_wppLevels )
              goto LABEL_30;
            v42 = 61;
            goto LABEL_69;
          }
          v54 = CoTaskMemAlloc(cchWideChar);
          v29 = (unsigned __int16 **)(pvar + 1);
          pvar[1] = v54;
          if ( !v54 )
          {
            v57 = (__int64 *)CallStackTracing::s_wpInstance;
            v39 = -2147024882;
            v11 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56);
              CallStackTracing::s_wpInstance = v58;
              if ( v58
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
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
              if ( *((_DWORD *)v59 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v59, "CMFPropVariantConvert::CreateFromData", 905, -2147024882);
            }
            if ( !g_wppLevels )
              goto LABEL_30;
            v42 = 62;
            goto LABEL_69;
          }
          *v54 = 0;
          v11 = StringCchCopyW(*v29, cchWideChar >> 1, (const unsigned __int16 *)a3);
          if ( v11 >= 0 )
            goto LABEL_168;
          v60 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v15);
            CallStackTracing::s_wpInstance = v61;
            if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
            {
              v60 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v60 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v60 + 8) )
          {
            v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
            if ( *((_DWORD *)v62 + 499) != v11 )
              CallStackContext::TraceFailure(v62, "CMFPropVariantConvert::CreateFromData", 909, v11);
          }
          if ( !g_wppLevels )
            goto LABEL_30;
          v63 = 63;
        }
        else
        {
          lpWideCharStr = CoTaskMemAlloc(2 * cchWideChar);
          v29 = (unsigned __int16 **)(pvar + 1);
          pvar[1] = lpWideCharStr;
          if ( !lpWideCharStr )
          {
            v70 = (__int64 *)CallStackTracing::s_wpInstance;
            v39 = -2147024882;
            v11 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v68, v69);
              CallStackTracing::s_wpInstance = v71;
              if ( v71
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
              {
                v70 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v70 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v70 + 8) )
            {
              v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
              if ( *((_DWORD *)v72 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v72, "CMFPropVariantConvert::CreateFromData", 876, -2147024882);
            }
            if ( !g_wppLevels )
              goto LABEL_30;
            v42 = 58;
            goto LABEL_69;
          }
          *(_WORD *)pvar = 31;
          if ( MultiByteToWideChar(0, 0, a3, cchWideChar, (LPWSTR)lpWideCharStr, cchWideChar) )
          {
            (*v29)[(unsigned int)(cchWideChar - 1)] = 0;
            goto LABEL_168;
          }
          LastError = GetLastError();
          v11 = LastError;
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
          v76 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( v11 >= 0 )
          {
            v11 = -2147418113;
            if ( !CallStackTracing::s_wpInstance )
            {
              v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v74, v75);
              CallStackTracing::s_wpInstance = v79;
              if ( v79
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
              {
                v76 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v76 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v76 + 8) )
            {
              v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v76);
              if ( *((_DWORD *)v80 + 499) != -2147418113 )
                CallStackContext::TraceFailure(v80, "CMFPropVariantConvert::CreateFromData", 890, -2147418113);
            }
            if ( !g_wppLevels )
              goto LABEL_30;
            v63 = 60;
          }
          else
          {
            if ( !CallStackTracing::s_wpInstance )
            {
              v77 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v74, v75);
              CallStackTracing::s_wpInstance = v77;
              if ( v77
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v77 + 8LL))(v77, 2032) )
              {
                v76 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v76 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v76 + 8) )
            {
              v78 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v76);
              if ( *((_DWORD *)v78 + 499) != v11 )
                CallStackContext::TraceFailure(v78, "CMFPropVariantConvert::CreateFromData", 889, v11);
            }
            if ( !g_wppLevels )
              goto LABEL_30;
            v63 = 59;
          }
        }
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v63, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, 0, v11);
        goto LABEL_30;
      }
    }
    else
    {
      if ( a2 && a2 != 65 )
      {
        v25 = (__int64 *)CallStackTracing::s_wpInstance;
        v11 = -2147024809;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 65, 8);
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
          if ( *((_DWORD *)v27 + 499) != -2147024809 )
            CallStackContext::TraceFailure(v27, "CMFPropVariantConvert::CreateFromData", 834, -2147024809);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
            0,
            -2147024809);
        goto LABEL_183;
      }
      v16 = 0;
    }
    if ( a2 == 8 )
    {
      *(_WORD *)pvar = 31;
      a2 = 31;
    }
    goto LABEL_18;
  }
  v82 = (__int64 *)CallStackTracing::s_wpInstance;
  v11 = -1072875798;
  if ( !CallStackTracing::s_wpInstance )
  {
    v83 = (CallStackTracing *)((__int64 (*)(void))MFGetCallStackTracingWeakReference)();
    CallStackTracing::s_wpInstance = v83;
    if ( v83 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v83 + 8LL))(v83, 2032) )
    {
      v82 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v82 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v82 + 8) )
  {
    v84 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v82);
    if ( *((_DWORD *)v84 + 499) != -1072875798 )
      CallStackContext::TraceFailure(v84, "CMFPropVariantConvert::CreateFromData", 812, -1072875798);
  }
  if ( g_wppLevels )
  {
    v14 = 55;
    goto LABEL_182;
  }
LABEL_183:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v86);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1801dae40  mov     rax, rsp
0x1801dae43  push    rbx
0x1801dae44  push    rbp
0x1801dae45  push    rsi
0x1801dae46  push    rdi
0x1801dae47  push    r12
0x1801dae49  push    r13
0x1801dae4b  push    r14
0x1801dae4d  push    r15
0x1801dae4f  sub     rsp, 38h
0x1801dae53  mov     r12, r8
0x1801dae56  mov     esi, r9d
0x1801dae59  movzx   edi, dx
0x1801dae5c  lea     rbp, aCmfpropvariant_9; "CMFPropVariantConvert::CreateFromData"
0x1801dae63  mov     r15, rcx
0x1801dae66  mov     rdx, rbp; char *
0x1801dae69  mov     r8d, 31Fh; int
0x1801dae6f  lea     rcx, [rax+8]; this
0x1801dae73  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801dae78  xor     r13d, r13d
0x1801dae7b  cmp     r13w, [r15]
0x1801dae7f  jnz     loc_1801DB7FF
0x1801dae85  movzx   edx, di
0x1801dae88  mov     [r15], di
0x1801dae8c  mov     eax, 1000h
0x1801dae91  and     dx, ax
0x1801dae94  cmp     r13w, dx
0x1801dae98  jz      loc_1801DAF35
0x1801dae9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801daea5  mov     ebx, 0C00D36EBh
0x1801daeaa  test    rcx, rcx
0x1801daead  jnz     short loc_1801DAEF7
0x1801daeaf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801daeb6  nop     dword ptr [rax+rax+00h]
0x1801daebb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801daec2  mov     rcx, rax
0x1801daec5  test    rax, rax
0x1801daec8  jz      short loc_1801DAEE9
0x1801daeca  mov     rax, [rax]
0x1801daecd  mov     edx, 7F0h
0x1801daed2  mov     rax, [rax+8]
0x1801daed6  call    cs:__guard_dispatch_icall_fptr
0x1801daedc  test    eax, eax
0x1801daede  jz      short loc_1801DAEE9
0x1801daee0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801daee7  jmp     short loc_1801DAEF7
0x1801daee9  lea     rcx, qword_1803CE250; this
0x1801daef0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801daef7  cmp     [rcx+8], r13b
0x1801daefb  jz      short loc_1801DAF1E
0x1801daefd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801daf02  cmp     [rax+7CCh], ebx
0x1801daf08  jz      short loc_1801DAF1E
0x1801daf0a  mov     r9d, ebx; int
0x1801daf0d  mov     r8d, 339h; int
0x1801daf13  mov     rdx, rbp; char *
0x1801daf16  mov     rcx, rax; this
0x1801daf19  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801daf1e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801daf25  jb      loc_1801DB8AB
0x1801daf2b  mov     edx, 38h ; '8'
0x1801daf30  jmp     loc_1801DB88D
0x1801daf35  mov     ecx, 1Fh
0x1801daf3a  lea     edx, [rcx+22h]
0x1801daf3d  lea     r8d, [rcx-17h]
0x1801daf41  test    esi, esi
0x1801daf43  jnz     loc_1801DB073
0x1801daf49  cmp     r13w, di
0x1801daf4d  jnz     short loc_1801DAFCD
0x1801daf4f  mov     edx, r13d
0x1801daf52  cmp     r8w, di
0x1801daf56  jnz     short loc_1801DAF5F
0x1801daf58  mov     [r15], cx
0x1801daf5c  movzx   edi, cx
0x1801daf5f  movzx   ecx, di
0x1801daf62  mov     r14d, 0FFFh
0x1801daf68  and     ecx, r14d
0x1801daf6b  mov     ebx, r13d
0x1801daf6e  cmp     ecx, 13h
0x1801daf71  ja      loc_1801DB0C6
0x1801daf77  jz      short loc_1801DAFB2
0x1801daf79  sub     ecx, 2
0x1801daf7c  jz      short loc_1801DAFB2
0x1801daf7e  sub     ecx, 1
0x1801daf81  jz      short loc_1801DAFB2
0x1801daf83  sub     ecx, 6
0x1801daf86  jz      short loc_1801DAFB2
0x1801daf88  sub     ecx, 2
0x1801daf8b  jz      loc_1801DB0BA
0x1801daf91  sub     ecx, 2
0x1801daf94  jz      short loc_1801DAFB2
0x1801daf96  sub     ecx, 1
0x1801daf99  jz      loc_1801DB09E
0x1801daf9f  sub     ecx, 2
0x1801dafa2  jz      short loc_1801DAFB2
0x1801dafa4  sub     ecx, 1
0x1801dafa7  jz      short loc_1801DAFB2
0x1801dafa9  cmp     ecx, 1
0x1801dafac  jnz     loc_1801DB117
0x1801dafb2  cmp     esi, r8d
0x1801dafb5  jbe     loc_1801DB7B9
0x1801dafbb  mov     ebx, 80070057h
0x1801dafc0  mov     rcx, r15; pvar
0x1801dafc3  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1801dafc8  jmp     loc_1801DB8AB
0x1801dafcd  cmp     dx, di
0x1801dafd0  jz      loc_1801DAF4F
0x1801dafd6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dafdd  mov     edi, 80070057h
0x1801dafe2  mov     ebx, edi
0x1801dafe4  test    rcx, rcx
0x1801dafe7  jnz     short loc_1801DB031
0x1801dafe9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801daff0  nop     dword ptr [rax+rax+00h]
0x1801daff5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801daffc  mov     rcx, rax
0x1801dafff  test    rax, rax
0x1801db002  jz      short loc_1801DB023
0x1801db004  mov     rax, [rax]
0x1801db007  mov     edx, 7F0h
0x1801db00c  mov     rax, [rax+8]
0x1801db010  call    cs:__guard_dispatch_icall_fptr
0x1801db016  test    eax, eax
0x1801db018  jz      short loc_1801DB023
0x1801db01a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db021  jmp     short loc_1801DB031
0x1801db023  lea     rcx, qword_1803CE250; this
0x1801db02a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db031  cmp     [rcx+8], r13b
0x1801db035  jz      short loc_1801DB058
0x1801db037  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801db03c  cmp     [rax+7CCh], edi
0x1801db042  jz      short loc_1801DB058
0x1801db044  mov     r9d, edi; int
0x1801db047  mov     r8d, 342h; int
0x1801db04d  mov     rdx, rbp; char *
0x1801db050  mov     rcx, rax; this
0x1801db053  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801db058  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801db05f  jb      loc_1801DB8AB
0x1801db065  mov     edx, 39h ; '9'
0x1801db06a  mov     dword ptr [rsp+78h+lpWideCharStr], edi
0x1801db06e  jmp     loc_1801DB891
0x1801db073  mov     eax, 0Bh
0x1801db078  mov     edx, r13d
0x1801db07b  cmp     ax, di
0x1801db07e  jnz     loc_1801DAF52
0x1801db084  mov     ecx, esi
0x1801db086  test    ecx, ecx
0x1801db088  jz      loc_1801DAF5F
0x1801db08e  dec     ecx
0x1801db090  cmp     [rcx+r12], r13b
0x1801db094  jz      short loc_1801DB086
0x1801db096  or      edx, 0FFFFFFFFh
0x1801db099  jmp     loc_1801DAF5F
0x1801db09e  cmp     esi, 10h
0x1801db0a1  jnz     loc_1801DAFBB
0x1801db0a7  movups  xmm0, xmmword ptr [r12]
0x1801db0ac  lea     rdi, [r15+8]
0x1801db0b0  movdqu  xmmword ptr [r15], xmm0
0x1801db0b5  jmp     loc_1801DB7CB
0x1801db0ba  lea     rdi, [r15+8]
0x1801db0be  mov     [rdi], dx
0x1801db0c1  jmp     loc_1801DB7CB
0x1801db0c6  sub     ecx, 14h
0x1801db0c9  jz      loc_1801DAFB2
0x1801db0cf  sub     ecx, 1
0x1801db0d2  jz      loc_1801DAFB2
0x1801db0d8  sub     ecx, 1
0x1801db0db  jz      loc_1801DAFB2
0x1801db0e1  sub     ecx, 1
0x1801db0e4  jz      loc_1801DAFB2
0x1801db0ea  sub     ecx, 7
0x1801db0ed  jz      loc_1801DB57B
0x1801db0f3  sub     ecx, 1
0x1801db0f6  jz      loc_1801DB363
0x1801db0fc  sub     ecx, 21h ; '!'
0x1801db0ff  jz      loc_1801DAFB2
0x1801db105  sub     ecx, 1
0x1801db108  jz      loc_1801DB29C
0x1801db10e  cmp     ecx, 7
0x1801db111  jz      loc_1801DB1CE
0x1801db117  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db11e  mov     edi, 80070057h
0x1801db123  mov     ebx, edi
0x1801db125  test    rcx, rcx
0x1801db128  jnz     short loc_1801DB172
0x1801db12a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801db131  nop     dword ptr [rax+rax+00h]
0x1801db136  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db13d  mov     rcx, rax
0x1801db140  test    rax, rax
0x1801db143  jz      short loc_1801DB164
0x1801db145  mov     rax, [rax]
0x1801db148  mov     edx, 7F0h
0x1801db14d  mov     rax, [rax+8]
0x1801db151  call    cs:__guard_dispatch_icall_fptr
0x1801db157  test    eax, eax
0x1801db159  jz      short loc_1801DB164
0x1801db15b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db162  jmp     short loc_1801DB172
0x1801db164  lea     rcx, qword_1803CE250; this
0x1801db16b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db172  cmp     [rcx+8], r13b
0x1801db176  jz      short loc_1801DB199
0x1801db178  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801db17d  cmp     [rax+7CCh], edi
0x1801db183  jz      short loc_1801DB199
0x1801db185  mov     r9d, edi; int
0x1801db188  mov     r8d, 3CAh; int
0x1801db18e  mov     rdx, rbp; char *
0x1801db191  mov     rcx, rax; this
0x1801db194  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801db199  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801db1a0  jb      loc_1801DAFC0
0x1801db1a6  mov     edx, 42h ; 'B'
0x1801db1ab  mov     dword ptr [rsp+78h+lpWideCharStr], edi
0x1801db1af  mov     rcx, cs:WPP_GLOBAL_Control
0x1801db1b6  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1801db1bd  xor     r9d, r9d
0x1801db1c0  mov     rcx, [rcx+10h]
0x1801db1c4  call    WPP_SF_qD
0x1801db1c9  jmp     loc_1801DAFC0
0x1801db1ce  cmp     esi, 10h
0x1801db1d1  jnz     loc_1801DAFBB
0x1801db1d7  mov     ecx, esi; cb
0x1801db1d9  call    cs:__imp_CoTaskMemAlloc
0x1801db1e0  nop     dword ptr [rax+rax+00h]
0x1801db1e5  lea     rdi, [r15+8]
0x1801db1e9  mov     [rdi], rax
0x1801db1ec  test    rax, rax
0x1801db1ef  jnz     loc_1801DB28E
0x1801db1f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db1fc  mov     edi, 8007000Eh
0x1801db201  mov     ebx, edi
0x1801db203  test    rcx, rcx
0x1801db206  jnz     short loc_1801DB250
0x1801db208  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801db20f  nop     dword ptr [rax+rax+00h]
0x1801db214  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db21b  mov     rcx, rax
0x1801db21e  test    rax, rax
0x1801db221  jz      short loc_1801DB242
0x1801db223  mov     rax, [rax]
0x1801db226  mov     edx, 7F0h
0x1801db22b  mov     rax, [rax+8]
0x1801db22f  call    cs:__guard_dispatch_icall_fptr
0x1801db235  test    eax, eax
0x1801db237  jz      short loc_1801DB242
0x1801db239  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db240  jmp     short loc_1801DB250
0x1801db242  lea     rcx, qword_1803CE250; this
0x1801db249  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db250  cmp     [rcx+8], r13b
0x1801db254  jz      short loc_1801DB277
0x1801db256  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801db25b  cmp     [rax+7CCh], edi
0x1801db261  jz      short loc_1801DB277
0x1801db263  mov     r9d, edi; int
0x1801db266  mov     r8d, 39Fh; int
0x1801db26c  mov     rdx, rbp; char *
0x1801db26f  mov     rcx, rax; this
0x1801db272  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801db277  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801db27e  jb      loc_1801DAFC0
0x1801db284  mov     edx, 41h ; 'A'
0x1801db289  jmp     loc_1801DB1AB
0x1801db28e  movups  xmm0, xmmword ptr [r12]
0x1801db293  movdqu  xmmword ptr [rax], xmm0
0x1801db297  jmp     loc_1801DB7CB
0x1801db29c  mov     rcx, rsi; cb
0x1801db29f  call    cs:__imp_CoTaskMemAlloc
0x1801db2a6  nop     dword ptr [rax+rax+00h]
0x1801db2ab  mov     [r15+10h], rax
0x1801db2af  test    rax, rax
0x1801db2b2  jnz     loc_1801DB355
0x1801db2b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db2bf  mov     edi, 8007000Eh
0x1801db2c4  mov     ebx, edi
0x1801db2c6  test    rcx, rcx
0x1801db2c9  jnz     short loc_1801DB313
0x1801db2cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801db2d2  nop     dword ptr [rax+rax+00h]
0x1801db2d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db2de  mov     rcx, rax
0x1801db2e1  test    rax, rax
0x1801db2e4  jz      short loc_1801DB305
0x1801db2e6  mov     rax, [rax]
0x1801db2e9  mov     edx, 7F0h
0x1801db2ee  mov     rax, [rax+8]
0x1801db2f2  call    cs:__guard_dispatch_icall_fptr
0x1801db2f8  test    eax, eax
0x1801db2fa  jz      short loc_1801DB305
0x1801db2fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db303  jmp     short loc_1801DB313
0x1801db305  lea     rcx, qword_1803CE250; this
0x1801db30c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801db313  cmp     [rcx+8], r13b
0x1801db317  jz      short loc_1801DB33E
0x1801db319  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
  ... truncated ...
```
