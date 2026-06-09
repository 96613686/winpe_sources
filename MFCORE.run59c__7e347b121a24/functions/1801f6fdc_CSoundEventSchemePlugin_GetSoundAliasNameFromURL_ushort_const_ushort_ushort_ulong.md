# CSoundEventSchemePlugin::GetSoundAliasNameFromURL(ushort const *,ushort * *,ushort * *,ulong *)

- ea: `0x1801f6fdc`
- end: `0x1801f7a6c`
- name: `?GetSoundAliasNameFromURL@CSoundEventSchemePlugin@@QEAAJPEBGPEAPEAG1PEAK@Z`
- size: `2704`
- prototype: `int(CSoundEventSchemePlugin *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802bf500`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180093088`
- `0x1800ec0e0`
- `0x180111d68`
- `0x18017d0d8`
- `0x1801f6fdc`
- `0x18020b77c`
- `0x180258480`
- `0x180259174`
- `0x18025918c`
- `0x180259198`
- `0x1802591d4`
- `0x1802591e0`
- `0x180259270`
- `0x1802592a0`
- `0x180273258`
- `0x18027a218`
- `0x1802c00c0`
- `0x1802c0284`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801f7885`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801f7885`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801f7867`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801f7867`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f7624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f796c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f7624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f796c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f7089`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f712f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f71d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f727b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f7331`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f73ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f74b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f763c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f7994`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f7089`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f712f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f71d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f727b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f7331`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f73ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f74b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f763c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f7994`

## string_xrefs

- `0x1801f7057`: `CSoundEventSchemePlugin::GetSoundAliasNameFromURL`
- `0x1801f70e7`: `CSoundEventSchemePlugin::GetSoundAliasNameFromURL`
- `0x1801f718d`: `CSoundEventSchemePlugin::GetSoundAliasNameFromURL`
- `0x1801f7233`: `CSoundEventSchemePlugin::GetSoundAliasNameFromURL`
- `0x1801f72d9`: `CSoundEventSchemePlugin::GetSoundAliasNameFromURL`
- `0x1801f738f`: `CSoundEventSchemePlugin::GetSoundAliasNameFromURL`
- `0x1801f744c`: `CSoundEventSchemePlugin::GetSoundAliasNameFromURL`
- `0x1801f7510`: `CSoundEventSchemePlugin::GetSoundAliasNameFromURL`
- `0x1801f769a`: `CSoundEventSchemePlugin::GetSoundAliasNameFromURL`
- `0x1801f79f2`: `CSoundEventSchemePlugin::GetSoundAliasNameFromURL`

## pseudocode

```c
__int64 __fastcall CSoundEventSchemePlugin::GetSoundAliasNameFromURL(
        CSoundEventSchemePlugin *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        unsigned int *a5)
{
  unsigned int v5; // r12d
  unsigned __int16 **v9; // r15
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 *v12; // rcx
  int v13; // edi
  int v14; // ebx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  int v43; // eax
  void *v44; // r11
  __int64 v45; // rax
  unsigned int v46; // r14d
  unsigned __int16 *v47; // rdi
  unsigned int v48; // ebx
  unsigned __int16 *v49; // rsi
  int v50; // r15d
  unsigned int v51; // r9d
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  int v57; // r9d
  int v58; // ecx
  unsigned __int16 *v59; // rbx
  unsigned int v60; // edi
  int v61; // r15d
  unsigned int v62; // r9d
  int v63; // eax
  int v64; // r9d
  int v65; // ecx
  HMODULE ModuleHandleW; // rax
  void *v67; // rcx
  int v68; // esi
  __int64 v69; // rdi
  wchar_t *v70; // r8
  void *v71; // r11
  __int64 *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  _BYTE v76[8]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v77; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v78; // [rsp+60h] [rbp-A0h] BYREF
  int v79; // [rsp+70h] [rbp-90h] BYREF
  int v80; // [rsp+78h] [rbp-88h]
  __int128 v81; // [rsp+80h] [rbp-80h]
  int v82; // [rsp+90h] [rbp-70h]
  __int64 v83; // [rsp+98h] [rbp-68h]
  __int64 v84; // [rsp+A0h] [rbp-60h]
  int v85; // [rsp+A8h] [rbp-58h]
  __int64 v86; // [rsp+B0h] [rbp-50h]
  __int64 v87; // [rsp+B8h] [rbp-48h]
  __int16 v88; // [rsp+C0h] [rbp-40h]
  int v89; // [rsp+C4h] [rbp-3Ch]
  unsigned __int16 **v90; // [rsp+D0h] [rbp-30h]
  int v91; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v92; // [rsp+E4h] [rbp-1Ch]
  int v93; // [rsp+ECh] [rbp-14h]
  __int64 v94; // [rsp+F0h] [rbp-10h]
  wchar_t *String1; // [rsp+F8h] [rbp-8h] BYREF
  size_t MaxCount; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v97; // [rsp+108h] [rbp+8h]
  void *v98; // [rsp+110h] [rbp+10h]
  __int64 v99; // [rsp+128h] [rbp+28h]
  unsigned int v100; // [rsp+130h] [rbp+30h]
  int v101; // [rsp+138h] [rbp+38h]
  wchar_t v102[264]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR Filename[264]; // [rsp+350h] [rbp+250h] BYREF

  v5 = 0;
  v91 &= 0xFFFFFFF8;
  v90 = a4;
  v92 = 0;
  v94 = 0;
  v101 = 1;
  v93 = 0;
  v9 = a4;
  memset_0(&String1, 0, 0x40u);
  v77 = 0;
  v78 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v76,
    "CSoundEventSchemePlugin::GetSoundAliasNameFromURL",
    323);
  if ( !a2 )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    v13 = -2147467261;
    v14 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CSoundEventSchemePlugin::GetSoundAliasNameFromURL",
          323,
          -2147467261);
    }
    if ( g_wppLevels )
    {
      v17 = 25;
LABEL_157:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_e14fdb8ad75d33abc5719e2865154777_Traceguids, this, v13);
      goto LABEL_158;
    }
    goto LABEL_158;
  }
  if ( a3 )
  {
    if ( !v9 )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
      v13 = -2147467261;
      v14 = -2147467261;
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
        if ( *((_DWORD *)v23 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v23, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 325, -2147467261);
      }
      if ( g_wppLevels )
      {
        v17 = 27;
        goto LABEL_157;
      }
      goto LABEL_158;
    }
    if ( !a5 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      v13 = -2147467261;
      v14 = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v26, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 326, -2147467261);
      }
      if ( g_wppLevels )
      {
        v17 = 28;
        goto LABEL_157;
      }
      goto LABEL_158;
    }
    *a3 = 0;
    *v9 = 0;
    *a5 = 0;
    v14 = CUri::Parse((CUri *)&v91, a2, v11);
    if ( v14 < 0 )
    {
      v29 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
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
        if ( *((_DWORD *)v31 + 499) != v14 )
          CallStackContext::TraceFailure(v31, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 334, v14);
      }
      if ( !g_wppLevels )
        goto LABEL_158;
      v32 = 29;
      goto LABEL_56;
    }
    if ( wcsnicmp(String1, L"ms-winsoundevent", (unsigned int)MaxCount) )
    {
      v35 = (__int64 *)CallStackTracing::s_wpInstance;
      v13 = -2147024809;
      v14 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
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
        if ( *((_DWORD *)v37 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v37, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 339, -2147024809);
      }
      if ( g_wppLevels )
      {
        v17 = 30;
        goto LABEL_157;
      }
      goto LABEL_158;
    }
    if ( (unsigned int)((_DWORD)v98 - 1) > 0x102 )
    {
      v72 = (__int64 *)CallStackTracing::s_wpInstance;
      v13 = -2147024809;
      v14 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
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
        if ( *((_DWORD *)v74 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v74, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 344, -2147024809);
      }
      if ( g_wppLevels )
      {
        v17 = 31;
        goto LABEL_157;
      }
      goto LABEL_158;
    }
    v14 = CTCoAllocPolicy::Alloc((void *)(unsigned int)v98, 0, 2LL * (unsigned int)((_DWORD)v98 + 1), (void **)&v77);
    if ( v14 < 0 )
    {
      v40 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39);
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v40 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
        if ( *((_DWORD *)v42 + 499) != v14 )
          CallStackContext::TraceFailure(v42, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 348, v14);
      }
      if ( !g_wppLevels )
        goto LABEL_158;
      v32 = 32;
      goto LABEL_56;
    }
    v43 = StringCchCopyW(v77, (unsigned int)((_DWORD)v98 + 1), v97);
    v14 = v43;
    if ( v43 < 0 )
    {
      if ( v43 != -2147024774 )
      {
        CoTaskMemFree(v44);
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
          v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)v56 + 499) != v14 )
            CallStackContext::TraceFailure(v56, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 361, v14);
        }
        if ( !g_wppLevels )
          goto LABEL_158;
        v32 = 33;
LABEL_56:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, &WPP_e14fdb8ad75d33abc5719e2865154777_Traceguids, this, v14);
        goto LABEL_158;
      }
      v14 = 0;
    }
    v45 = v100;
    v46 = 2;
    *a3 = (unsigned __int16 *)v44;
    if ( (_DWORD)v45 )
    {
      v86 = v99;
      v79 = 0;
      v81 = 0;
      v80 = 0;
      v87 = v99 + 2 * v45;
      v83 = 0;
      v84 = 0;
      v82 = 0;
      v85 = 0;
      v88 = 0;
      v89 = 1;
      if ( (int)CTokenReaderT<unsigned short,CUriExtraInfoSeparator>::ReadNextToken(&v79) >= 0 )
      {
        do
        {
          if ( (unsigned int)CTokenT<unsigned short>::FastCompareName(&v79, &off_180357BC8) )
          {
            v47 = (unsigned __int16 *)v81;
            v48 = 0;
            v49 = (unsigned __int16 *)v81;
            v80 = 0;
            while ( 1 )
            {
              LODWORD(v77) = v48;
              if ( (unsigned __int64)v47 >= *((_QWORD *)&v81 + 1) )
                break;
              v50 = *v47;
              if ( (unsigned int)o_iswdigit_0((unsigned __int16)v50) )
              {
                v51 = v50 - 48;
              }
              else
              {
                if ( !iswalpha(v50) )
                  break;
                v51 = towupper(v50) - 55;
              }
              if ( v51 >= 0xA )
                break;
              v5 = 0;
              if ( (int)ULongLongToULong(10LL * v48, (unsigned int *)&v77) < 0 )
                goto LABEL_123;
              v48 = (_DWORD)v77 + v57;
              if ( (int)v77 + v57 < (unsigned int)v77 )
                goto LABEL_123;
              ++v47;
              v5 = (_DWORD)v77 + v57;
              *(_QWORD *)&v81 = v47;
            }
            if ( v49 == v47 )
            {
              v80 = -2147467259;
            }
            else
            {
              v58 = 128;
              if ( v5 != 1 )
                v58 = 0;
              v46 |= v58;
            }
            v5 = 0;
          }
          else if ( (unsigned int)CTokenT<unsigned short>::FastCompareName(&v79, &off_180357BB8) )
          {
            v59 = (unsigned __int16 *)v81;
            v60 = 0;
            v49 = (unsigned __int16 *)v81;
            LODWORD(v77) = 0;
            v80 = 0;
            while ( (unsigned __int64)v59 < *((_QWORD *)&v81 + 1) )
            {
              v61 = *v59;
              if ( (unsigned int)o_iswdigit_0((unsigned __int16)v61) )
              {
                v62 = v61 - 48;
              }
              else
              {
                if ( !iswalpha(v61) )
                  break;
                v62 = towupper(v61) - 55;
              }
              if ( v62 >= 0xA )
                break;
              v63 = ULongLongToULong(10LL * v5, (unsigned int *)&v77);
              v5 = 0;
              if ( v63 < 0 || (v60 = (_DWORD)v77 + v64, (int)v77 + v64 < (unsigned int)v77) )
              {
LABEL_123:
                v80 = -2147024362;
                *(_QWORD *)&v81 = v49;
                goto LABEL_129;
              }
              ++v59;
              LODWORD(v77) = (_DWORD)v77 + v64;
              *(_QWORD *)&v81 = v59;
              v5 = v60;
            }
            v5 = 0;
            if ( v49 == v59 )
            {
              v80 = -2147467259;
            }
            else
            {
              v65 = 0x80000;
              if ( v60 != 1 )
                v65 = 0;
              v46 |= v65;
            }
          }
LABEL_129:
          ;
        }
        while ( (int)CTokenReaderT<unsigned short,CUriExtraInfoSeparator>::ReadNextToken(&v79) >= 0 );
        v9 = v90;
      }
      v14 = 0;
      if ( (v46 & 0x80u) != 0 )
      {
        v77 = 0;
        Filename[0] = 0;
        v46 &= ~0x80u;
        v102[0] = 0;
        ModuleHandleW = GetModuleHandleW(0);
        if ( GetModuleFileNameW(ModuleHandleW, Filename, 0x104u) )
          wsplitpath_s(Filename, 0, 0, 0, 0, v102, 0x104u, 0, 0);
        if ( v102[0] && !(unsigned int)StringCchLengthW(v102, 0x104u, (unsigned __int64 *)&v77) )
        {
          if ( wcsicmp(v102, L"iexplore") && (v68 = 0, wcsicmp(v102, L"miexplore")) )
          {
            v69 = (__int64)v77;
          }
          else
          {
            v69 = 8;
            v68 = 1;
          }
          v14 = CTCoAllocPolicy::Alloc(v67, 0, 2 * v69 + 2, (void **)&v78);
          if ( v14 >= 0 )
          {
            v70 = v102;
            if ( v68 )
              v70 = (wchar_t *)L"Explorer";
            if ( StringCchCopyW(v78, v69 + 1, v70) )
              CoTaskMemFree(v71);
            else
              *v9 = (unsigned __int16 *)v71;
          }
        }
      }
    }
    *a5 = v46;
    goto LABEL_158;
  }
  v18 = (__int64 *)CallStackTracing::s_wpInstance;
  v13 = -2147467261;
  v14 = -2147467261;
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
    if ( *((_DWORD *)v20 + 499) != -2147467261 )
      CallStackContext::TraceFailure(v20, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 324, -2147467261);
  }
  if ( g_wppLevels )
  {
    v17 = 26;
    goto LABEL_157;
  }
LABEL_158:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v76);
  CMFBaseStringT<char>::~CMFBaseStringT<char>(&v91);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1801f6fdc  push    rbp
0x1801f6fde  push    rbx
0x1801f6fdf  push    rsi
0x1801f6fe0  push    rdi
0x1801f6fe1  push    r12
0x1801f6fe3  push    r13
0x1801f6fe5  push    r14
0x1801f6fe7  push    r15
0x1801f6fe9  lea     rbp, [rsp-478h]
0x1801f6ff1  sub     rsp, 578h
0x1801f6ff8  mov     rax, cs:__security_cookie
0x1801f6fff  xor     rax, rsp
0x1801f7002  mov     [rbp+4B0h+var_50], rax
0x1801f7009  mov     r13, [rbp+4B0h+arg_20]
0x1801f7010  xor     r12d, r12d
0x1801f7013  and     [rbp+4B0h+var_4D0], 0FFFFFFF8h
0x1801f7017  mov     rdi, r8
0x1801f701a  mov     rbx, rdx
0x1801f701d  mov     [rbp+4B0h+var_4E0], r9
0x1801f7021  mov     rsi, rcx
0x1801f7024  mov     [rbp+4B0h+var_4CC], r12
0x1801f7028  lea     r14d, [r12+1]
0x1801f702d  mov     [rbp+4B0h+var_4C0], r12
0x1801f7031  xor     edx, edx; Val
0x1801f7033  mov     [rbp+4B0h+var_478], r14d
0x1801f7037  lea     r8d, [r12+40h]; Size
0x1801f703c  mov     [rbp+4B0h+var_4C4], r12d
0x1801f7040  lea     rcx, [rbp+4B0h+String1]; void *
0x1801f7044  mov     r15, r9
0x1801f7047  call    memset_0
0x1801f704c  mov     r8d, 143h; int
0x1801f7052  mov     [rsp+5B0h+var_558], r12
0x1801f7057  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f705e  mov     [rsp+5B0h+var_550], r12
0x1801f7063  lea     rcx, [rsp+5B0h+var_560]; this
0x1801f7068  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801f706d  test    rbx, rbx
0x1801f7070  jnz     loc_1801F7113
0x1801f7076  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f707d  mov     edi, 80004003h
0x1801f7082  mov     ebx, edi
0x1801f7084  test    rcx, rcx
0x1801f7087  jnz     short loc_1801F70D1
0x1801f7089  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f7090  nop     dword ptr [rax+rax+00h]
0x1801f7095  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f709c  mov     rcx, rax
0x1801f709f  test    rax, rax
0x1801f70a2  jz      short loc_1801F70C3
0x1801f70a4  mov     rax, [rax]
0x1801f70a7  mov     edx, 7F0h
0x1801f70ac  mov     rax, [rax+8]
0x1801f70b0  call    cs:__guard_dispatch_icall_fptr
0x1801f70b6  test    eax, eax
0x1801f70b8  jz      short loc_1801F70C3
0x1801f70ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f70c1  jmp     short loc_1801F70D1
0x1801f70c3  lea     rcx, qword_1803CE250; this
0x1801f70ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f70d1  cmp     [rcx+8], r12b
0x1801f70d5  jz      short loc_1801F70FC
0x1801f70d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f70dc  cmp     [rax+7CCh], edi
0x1801f70e2  jz      short loc_1801F70FC
0x1801f70e4  mov     r9d, edi; int
0x1801f70e7  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f70ee  mov     r8d, 143h; int
0x1801f70f4  mov     rcx, rax; this
0x1801f70f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f70fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1801f7103  jb      loc_1801F7A33
0x1801f7109  mov     edx, 19h
0x1801f710e  jmp     loc_1801F7A15
0x1801f7113  test    rdi, rdi
0x1801f7116  jnz     loc_1801F71B9
0x1801f711c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f7123  mov     edi, 80004003h
0x1801f7128  mov     ebx, edi
0x1801f712a  test    rcx, rcx
0x1801f712d  jnz     short loc_1801F7177
0x1801f712f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f7136  nop     dword ptr [rax+rax+00h]
0x1801f713b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f7142  mov     rcx, rax
0x1801f7145  test    rax, rax
0x1801f7148  jz      short loc_1801F7169
0x1801f714a  mov     rax, [rax]
0x1801f714d  mov     edx, 7F0h
0x1801f7152  mov     rax, [rax+8]
0x1801f7156  call    cs:__guard_dispatch_icall_fptr
0x1801f715c  test    eax, eax
0x1801f715e  jz      short loc_1801F7169
0x1801f7160  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f7167  jmp     short loc_1801F7177
0x1801f7169  lea     rcx, qword_1803CE250; this
0x1801f7170  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f7177  cmp     [rcx+8], r12b
0x1801f717b  jz      short loc_1801F71A2
0x1801f717d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f7182  cmp     [rax+7CCh], edi
0x1801f7188  jz      short loc_1801F71A2
0x1801f718a  mov     r9d, edi; int
0x1801f718d  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f7194  mov     r8d, 144h; int
0x1801f719a  mov     rcx, rax; this
0x1801f719d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f71a2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1801f71a9  jb      loc_1801F7A33
0x1801f71af  mov     edx, 1Ah
0x1801f71b4  jmp     loc_1801F7A15
0x1801f71b9  test    r15, r15
0x1801f71bc  jnz     loc_1801F725F
0x1801f71c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f71c9  mov     edi, 80004003h
0x1801f71ce  mov     ebx, edi
0x1801f71d0  test    rcx, rcx
0x1801f71d3  jnz     short loc_1801F721D
0x1801f71d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f71dc  nop     dword ptr [rax+rax+00h]
0x1801f71e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f71e8  mov     rcx, rax
0x1801f71eb  test    rax, rax
0x1801f71ee  jz      short loc_1801F720F
0x1801f71f0  mov     rax, [rax]
0x1801f71f3  mov     edx, 7F0h
0x1801f71f8  mov     rax, [rax+8]
0x1801f71fc  call    cs:__guard_dispatch_icall_fptr
0x1801f7202  test    eax, eax
0x1801f7204  jz      short loc_1801F720F
0x1801f7206  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f720d  jmp     short loc_1801F721D
0x1801f720f  lea     rcx, qword_1803CE250; this
0x1801f7216  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f721d  cmp     [rcx+8], r12b
0x1801f7221  jz      short loc_1801F7248
0x1801f7223  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f7228  cmp     [rax+7CCh], edi
0x1801f722e  jz      short loc_1801F7248
0x1801f7230  mov     r9d, edi; int
0x1801f7233  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f723a  mov     r8d, 145h; int
0x1801f7240  mov     rcx, rax; this
0x1801f7243  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f7248  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1801f724f  jb      loc_1801F7A33
0x1801f7255  mov     edx, 1Bh
0x1801f725a  jmp     loc_1801F7A15
0x1801f725f  test    r13, r13
0x1801f7262  jnz     loc_1801F7305
0x1801f7268  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f726f  mov     edi, 80004003h
0x1801f7274  mov     ebx, edi
0x1801f7276  test    rcx, rcx
0x1801f7279  jnz     short loc_1801F72C3
0x1801f727b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f7282  nop     dword ptr [rax+rax+00h]
0x1801f7287  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f728e  mov     rcx, rax
0x1801f7291  test    rax, rax
0x1801f7294  jz      short loc_1801F72B5
0x1801f7296  mov     rax, [rax]
0x1801f7299  mov     edx, 7F0h
0x1801f729e  mov     rax, [rax+8]
0x1801f72a2  call    cs:__guard_dispatch_icall_fptr
0x1801f72a8  test    eax, eax
0x1801f72aa  jz      short loc_1801F72B5
0x1801f72ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f72b3  jmp     short loc_1801F72C3
0x1801f72b5  lea     rcx, qword_1803CE250; this
0x1801f72bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f72c3  cmp     [rcx+8], r12b
0x1801f72c7  jz      short loc_1801F72EE
0x1801f72c9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f72ce  cmp     [rax+7CCh], edi
0x1801f72d4  jz      short loc_1801F72EE
0x1801f72d6  mov     r9d, edi; int
0x1801f72d9  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f72e0  mov     r8d, 146h; int
0x1801f72e6  mov     rcx, rax; this
0x1801f72e9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f72ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1801f72f5  jb      loc_1801F7A33
0x1801f72fb  mov     edx, 1Ch
0x1801f7300  jmp     loc_1801F7A15
0x1801f7305  mov     [rdi], r12
0x1801f7308  lea     rcx, [rbp+4B0h+var_4D0]; this
0x1801f730c  mov     [r15], r12
0x1801f730f  mov     rdx, rbx; unsigned __int16 *
0x1801f7312  mov     [r13+0], r12d
0x1801f7316  call    ?Parse@CUri@@QEAAJPEBGJ@Z; CUri::Parse(ushort const *,long)
0x1801f731b  mov     ebx, eax
0x1801f731d  test    eax, eax
0x1801f731f  jns     loc_1801F73BF
0x1801f7325  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f732c  test    rcx, rcx
0x1801f732f  jnz     short loc_1801F7379
0x1801f7331  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f7338  nop     dword ptr [rax+rax+00h]
0x1801f733d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f7344  mov     rcx, rax
0x1801f7347  test    rax, rax
0x1801f734a  jz      short loc_1801F736B
0x1801f734c  mov     rax, [rax]
0x1801f734f  mov     edx, 7F0h
0x1801f7354  mov     rax, [rax+8]
0x1801f7358  call    cs:__guard_dispatch_icall_fptr
0x1801f735e  test    eax, eax
0x1801f7360  jz      short loc_1801F736B
0x1801f7362  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f7369  jmp     short loc_1801F7379
0x1801f736b  lea     rcx, qword_1803CE250; this
0x1801f7372  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f7379  cmp     [rcx+8], r12b
0x1801f737d  jz      short loc_1801F73A4
0x1801f737f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f7384  cmp     [rax+7CCh], ebx
0x1801f738a  jz      short loc_1801F73A4
0x1801f738c  mov     r9d, ebx; int
0x1801f738f  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f7396  mov     r8d, 14Eh; int
0x1801f739c  mov     rcx, rax; this
0x1801f739f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f73a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1801f73ab  jb      loc_1801F7A33
0x1801f73b1  mov     edx, 1Dh
0x1801f73b6  mov     dword ptr [rsp+5B0h+DirCount], ebx
0x1801f73ba  jmp     loc_1801F7A19
0x1801f73bf  mov     r8d, dword ptr [rbp+4B0h+MaxCount]; MaxCount
0x1801f73c3  lea     rdx, aMsWinsoundeven; "ms-winsoundevent"
0x1801f73ca  mov     rcx, [rbp+4B0h+String1]; String1
0x1801f73ce  call    _wcsnicmp
0x1801f73d3  test    eax, eax
0x1801f73d5  jz      loc_1801F7478
0x1801f73db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f73e2  mov     edi, 80070057h
0x1801f73e7  mov     ebx, edi
0x1801f73e9  test    rcx, rcx
0x1801f73ec  jnz     short loc_1801F7436
0x1801f73ee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f73f5  nop     dword ptr [rax+rax+00h]
0x1801f73fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f7401  mov     rcx, rax
0x1801f7404  test    rax, rax
0x1801f7407  jz      short loc_1801F7428
0x1801f7409  mov     rax, [rax]
0x1801f740c  mov     edx, 7F0h
0x1801f7411  mov     rax, [rax+8]
0x1801f7415  call    cs:__guard_dispatch_icall_fptr
0x1801f741b  test    eax, eax
0x1801f741d  jz      short loc_1801F7428
0x1801f741f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f7426  jmp     short loc_1801F7436
0x1801f7428  lea     rcx, qword_1803CE250; this
0x1801f742f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f7436  cmp     [rcx+8], r12b
0x1801f743a  jz      short loc_1801F7461
0x1801f743c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f7441  cmp     [rax+7CCh], edi
0x1801f7447  jz      short loc_1801F7461
0x1801f7449  mov     r9d, edi; int
0x1801f744c  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f7453  mov     r8d, 153h; int
0x1801f7459  mov     rcx, rax; this
0x1801f745c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f7461  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1801f7468  jb      loc_1801F7A33
0x1801f746e  mov     edx, 1Eh
0x1801f7473  jmp     loc_1801F7A15
0x1801f7478  mov     ecx, dword ptr [rbp+4B0h+var_4A0]; void *
0x1801f747b  lea     eax, [rcx-1]
0x1801f747e  cmp     eax, 102h
0x1801f7483  ja      loc_1801F7981
0x1801f7489  lea     r8d, [rcx+1]
0x1801f748d  xor     edx, edx; unsigned int
0x1801f748f  add     r8, r8; unsigned __int64
0x1801f7492  lea     r9, [rsp+5B0h+var_558]; void **
0x1801f7497  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1801f749c  mov     ebx, eax
0x1801f749e  test    eax, eax
0x1801f74a0  jns     loc_1801F753C
0x1801f74a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f74ad  test    rcx, rcx
0x1801f74b0  jnz     short loc_1801F74FA
0x1801f74b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f74b9  nop     dword ptr [rax+rax+00h]
0x1801f74be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f74c5  mov     rcx, rax
0x1801f74c8  test    rax, rax
0x1801f74cb  jz      short loc_1801F74EC
0x1801f74cd  mov     rax, [rax]
0x1801f74d0  mov     edx, 7F0h
0x1801f74d5  mov     rax, [rax+8]
0x1801f74d9  call    cs:__guard_dispatch_icall_fptr
0x1801f74df  test    eax, eax
0x1801f74e1  jz      short loc_1801F74EC
0x1801f74e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f74ea  jmp     short loc_1801F74FA
0x1801f74ec  lea     rcx, qword_1803CE250; this
0x1801f74f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f74fa  cmp     [rcx+8], r12b
  ... truncated ...
```
