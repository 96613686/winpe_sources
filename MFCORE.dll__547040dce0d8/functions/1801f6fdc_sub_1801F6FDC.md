# sub_1801F6FDC

- ea: `0x1801f6fdc`
- end: `0x1801f7a6c`
- name: `sub_1801F6FDC`
- size: `2704`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, service_task, broker_com_uri`

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
__int64 __fastcall sub_1801F6FDC(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4, int *a5)
{
  unsigned int v5; // r12d
  _QWORD *v9; // r15
  __int64 *v10; // rcx
  int v11; // edi
  int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  int v35; // eax
  void *v36; // r11
  __int64 v37; // rax
  int v38; // r14d
  unsigned __int16 *v39; // rdi
  unsigned int v40; // ebx
  unsigned __int16 *v41; // rsi
  int v42; // r15d
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 *v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rax
  int v48; // r9d
  int v49; // ecx
  unsigned __int16 *v50; // rbx
  unsigned int v51; // edi
  int v52; // r15d
  __int64 v53; // r8
  __int64 v54; // r9
  int v55; // eax
  int v56; // r9d
  int v57; // ecx
  HMODULE ModuleHandleW; // rax
  __int64 v59; // rcx
  int v60; // esi
  __int64 v61; // rdi
  const wchar_t *v62; // r8
  void *v63; // r11
  __int64 *v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rax
  _BYTE v68[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v69; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v70; // [rsp+60h] [rbp-A0h] BYREF
  int v71; // [rsp+70h] [rbp-90h] BYREF
  int v72; // [rsp+78h] [rbp-88h]
  __int128 v73; // [rsp+80h] [rbp-80h]
  int v74; // [rsp+90h] [rbp-70h]
  __int64 v75; // [rsp+98h] [rbp-68h]
  __int64 v76; // [rsp+A0h] [rbp-60h]
  int v77; // [rsp+A8h] [rbp-58h]
  __int64 v78; // [rsp+B0h] [rbp-50h]
  __int64 v79; // [rsp+B8h] [rbp-48h]
  __int16 v80; // [rsp+C0h] [rbp-40h]
  int v81; // [rsp+C4h] [rbp-3Ch]
  _QWORD *v82; // [rsp+D0h] [rbp-30h]
  int v83; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v84; // [rsp+E4h] [rbp-1Ch]
  int v85; // [rsp+ECh] [rbp-14h]
  __int64 v86; // [rsp+F0h] [rbp-10h]
  _QWORD v87[8]; // [rsp+F8h] [rbp-8h] BYREF
  int v88; // [rsp+138h] [rbp+38h]
  _WORD v89[264]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR Filename[264]; // [rsp+350h] [rbp+250h] BYREF

  v5 = 0;
  v83 &= 0xFFFFFFF8;
  v82 = a4;
  v84 = 0;
  v86 = 0;
  v88 = 1;
  v85 = 0;
  v9 = a4;
  memset(v87, 0, sizeof(v87));
  v69 = 0;
  v70 = 0;
  sub_18002FEE0(v68, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 323);
  if ( !a2 )
  {
    v10 = (__int64 *)qword_1803CEF18;
    v11 = -2147467261;
    v12 = -2147467261;
    if ( !qword_1803CEF18 )
    {
      v13 = MFGetCallStackTracingWeakReference(0);
      qword_1803CEF18 = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v10 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v10 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v14 = sub_1800402C0(v10);
      if ( *(_DWORD *)(v14 + 1996) != -2147467261 )
        sub_1800EC0E0(v14, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 323, 2147500035LL);
    }
    if ( byte_1803CECE8 )
    {
      v15 = 25;
LABEL_157:
      sub_180050D6C(*((_QWORD *)RequestContext + 2), v15, qword_1803822C8, a1, v11);
      goto LABEL_158;
    }
    goto LABEL_158;
  }
  if ( a3 )
  {
    if ( !v9 )
    {
      v19 = (__int64 *)qword_1803CEF18;
      v11 = -2147467261;
      v12 = -2147467261;
      if ( !qword_1803CEF18 )
      {
        v20 = MFGetCallStackTracingWeakReference(0);
        qword_1803CEF18 = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v19 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = sub_1800402C0(v19);
        if ( *(_DWORD *)(v21 + 1996) != -2147467261 )
          sub_1800EC0E0(v21, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 325, 2147500035LL);
      }
      if ( byte_1803CECE8 )
      {
        v15 = 27;
        goto LABEL_157;
      }
      goto LABEL_158;
    }
    if ( !a5 )
    {
      v22 = (__int64 *)qword_1803CEF18;
      v11 = -2147467261;
      v12 = -2147467261;
      if ( !qword_1803CEF18 )
      {
        v23 = MFGetCallStackTracingWeakReference(0);
        qword_1803CEF18 = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v22 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v24 = sub_1800402C0(v22);
        if ( *(_DWORD *)(v24 + 1996) != -2147467261 )
          sub_1800EC0E0(v24, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 326, 2147500035LL);
      }
      if ( byte_1803CECE8 )
      {
        v15 = 28;
        goto LABEL_157;
      }
      goto LABEL_158;
    }
    *a3 = 0;
    *v9 = 0;
    *a5 = 0;
    v12 = sub_18020B77C(&v83, a2);
    if ( v12 < 0 )
    {
      v25 = (__int64 *)qword_1803CEF18;
      if ( !qword_1803CEF18 )
      {
        v26 = MFGetCallStackTracingWeakReference(0);
        qword_1803CEF18 = v26;
        if ( v26 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        {
          v25 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v25 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        v27 = sub_1800402C0(v25);
        if ( *(_DWORD *)(v27 + 1996) != v12 )
          sub_1800EC0E0(v27, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 334, (unsigned int)v12);
      }
      if ( !byte_1803CECE8 )
        goto LABEL_158;
      v28 = 29;
      goto LABEL_56;
    }
    if ( (unsigned int)o__wcsnicmp(v87[0], L"ms-winsoundevent", LODWORD(v87[1])) )
    {
      v29 = (__int64 *)qword_1803CEF18;
      v11 = -2147024809;
      v12 = -2147024809;
      if ( !qword_1803CEF18 )
      {
        v30 = MFGetCallStackTracingWeakReference(0);
        qword_1803CEF18 = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v29 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = sub_1800402C0(v29);
        if ( *(_DWORD *)(v31 + 1996) != -2147024809 )
          sub_1800EC0E0(v31, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 339, 2147942487LL);
      }
      if ( byte_1803CECE8 )
      {
        v15 = 30;
        goto LABEL_157;
      }
      goto LABEL_158;
    }
    if ( (unsigned int)(LODWORD(v87[3]) - 1) > 0x102 )
    {
      v64 = (__int64 *)qword_1803CEF18;
      v11 = -2147024809;
      v12 = -2147024809;
      if ( !qword_1803CEF18 )
      {
        v65 = MFGetCallStackTracingWeakReference(0);
        qword_1803CEF18 = v65;
        if ( v65 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
        {
          v64 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v64 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v64 + 8) )
      {
        v66 = sub_1800402C0(v64);
        if ( *(_DWORD *)(v66 + 1996) != -2147024809 )
          sub_1800EC0E0(v66, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 344, 2147942487LL);
      }
      if ( byte_1803CECE8 )
      {
        v15 = 31;
        goto LABEL_157;
      }
      goto LABEL_158;
    }
    v12 = sub_18027A218(LODWORD(v87[3]), 0, 2LL * (unsigned int)(LODWORD(v87[3]) + 1), &v69);
    if ( v12 < 0 )
    {
      v32 = (__int64 *)qword_1803CEF18;
      if ( !qword_1803CEF18 )
      {
        v33 = MFGetCallStackTracingWeakReference(0);
        qword_1803CEF18 = v33;
        if ( v33 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        {
          v32 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v32 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v34 = sub_1800402C0(v32);
        if ( *(_DWORD *)(v34 + 1996) != v12 )
          sub_1800EC0E0(v34, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 348, (unsigned int)v12);
      }
      if ( !byte_1803CECE8 )
        goto LABEL_158;
      v28 = 32;
      goto LABEL_56;
    }
    v35 = sub_18017D0D8(v69, (unsigned int)(LODWORD(v87[3]) + 1), v87[2]);
    v12 = v35;
    if ( v35 < 0 )
    {
      if ( v35 != -2147024774 )
      {
        CoTaskMemFree(v36);
        v45 = (__int64 *)qword_1803CEF18;
        if ( !qword_1803CEF18 )
        {
          v46 = MFGetCallStackTracingWeakReference(0);
          qword_1803CEF18 = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = (__int64 *)qword_1803CEF18;
          }
          else
          {
            v45 = &qword_1803CE250;
            qword_1803CEF18 = (__int64)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          v47 = sub_1800402C0(v45);
          if ( *(_DWORD *)(v47 + 1996) != v12 )
            sub_1800EC0E0(v47, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 361, (unsigned int)v12);
        }
        if ( !byte_1803CECE8 )
          goto LABEL_158;
        v28 = 33;
LABEL_56:
        sub_180050D6C(*((_QWORD *)RequestContext + 2), v28, qword_1803822C8, a1, v12);
        goto LABEL_158;
      }
      v12 = 0;
    }
    v37 = LODWORD(v87[7]);
    v38 = 2;
    *a3 = v36;
    if ( (_DWORD)v37 )
    {
      v78 = v87[6];
      v71 = 0;
      v73 = 0;
      v72 = 0;
      v79 = v87[6] + 2 * v37;
      v75 = 0;
      v76 = 0;
      v74 = 0;
      v77 = 0;
      v80 = 0;
      v81 = 1;
      if ( (int)sub_1802C0284(&v71) >= 0 )
      {
        do
        {
          if ( (unsigned int)sub_1802C00C0(&v71, &off_180357BB8) )
          {
            v39 = (unsigned __int16 *)v73;
            v40 = 0;
            v41 = (unsigned __int16 *)v73;
            v72 = 0;
            while ( 1 )
            {
              LODWORD(v69) = v40;
              if ( (unsigned __int64)v39 >= *((_QWORD *)&v73 + 1) )
                break;
              v42 = *v39;
              if ( (unsigned int)o_iswdigit((unsigned __int16)v42) )
              {
                v44 = (unsigned int)(v42 - 48);
              }
              else
              {
                if ( !(unsigned int)o_iswalpha((unsigned __int16)v42) )
                  break;
                v44 = (unsigned int)(unsigned __int16)o_towupper((unsigned __int16)v42) - 55;
              }
              if ( (unsigned int)v44 >= 0xA )
                break;
              v5 = 0;
              if ( (int)sub_180111D68(10LL * v40, &v69, v43, v44) < 0 )
                goto LABEL_123;
              v40 = v69 + v48;
              if ( (int)v69 + v48 < (unsigned int)v69 )
                goto LABEL_123;
              ++v39;
              v5 = v69 + v48;
              *(_QWORD *)&v73 = v39;
            }
            if ( v41 == v39 )
            {
              v72 = -2147467259;
            }
            else
            {
              v49 = 128;
              if ( v5 != 1 )
                v49 = 0;
              v38 |= v49;
            }
            v5 = 0;
          }
          else if ( (unsigned int)sub_1802C00C0(&v71, &off_180357BC8) )
          {
            v50 = (unsigned __int16 *)v73;
            v51 = 0;
            v41 = (unsigned __int16 *)v73;
            LODWORD(v69) = 0;
            v72 = 0;
            while ( (unsigned __int64)v50 < *((_QWORD *)&v73 + 1) )
            {
              v52 = *v50;
              if ( (unsigned int)o_iswdigit((unsigned __int16)v52) )
              {
                v54 = (unsigned int)(v52 - 48);
              }
              else
              {
                if ( !(unsigned int)o_iswalpha((unsigned __int16)v52) )
                  break;
                v54 = (unsigned int)(unsigned __int16)o_towupper((unsigned __int16)v52) - 55;
              }
              if ( (unsigned int)v54 >= 0xA )
                break;
              v55 = sub_180111D68(10LL * v5, &v69, v53, v54);
              v5 = 0;
              if ( v55 < 0 || (v51 = v69 + v56, (int)v69 + v56 < (unsigned int)v69) )
              {
LABEL_123:
                v72 = -2147024362;
                *(_QWORD *)&v73 = v41;
                goto LABEL_129;
              }
              ++v50;
              LODWORD(v69) = v69 + v56;
              *(_QWORD *)&v73 = v50;
              v5 = v51;
            }
            v5 = 0;
            if ( v41 == v50 )
            {
              v72 = -2147467259;
            }
            else
            {
              v57 = 0x80000;
              if ( v51 != 1 )
                v57 = 0;
              v38 |= v57;
            }
          }
LABEL_129:
          ;
        }
        while ( (int)sub_1802C0284(&v71) >= 0 );
        v9 = v82;
      }
      v12 = 0;
      if ( (v38 & 0x80u) != 0 )
      {
        v69 = 0;
        Filename[0] = 0;
        v38 &= ~0x80u;
        v89[0] = 0;
        ModuleHandleW = GetModuleHandleW(0);
        if ( GetModuleFileNameW(ModuleHandleW, Filename, 0x104u) )
          o__wsplitpath_s(Filename, 0, 0, 0, 0, v89, 260, 0, 0);
        if ( v89[0] && !(unsigned int)sub_180273258(v89, 260, &v69) )
        {
          if ( (unsigned int)o__wcsicmp(v89) && (v60 = 0, (unsigned int)o__wcsicmp(v89)) )
          {
            v61 = v69;
          }
          else
          {
            v61 = 8;
            v60 = 1;
          }
          v12 = sub_18027A218(v59, 0, 2 * v61 + 2, &v70);
          if ( v12 >= 0 )
          {
            v62 = v89;
            if ( v60 )
              v62 = L"Explorer";
            if ( (unsigned int)sub_18017D0D8(v70, v61 + 1, v62) )
              CoTaskMemFree(v63);
            else
              *v9 = v63;
          }
        }
      }
    }
    *a5 = v38;
    goto LABEL_158;
  }
  v16 = (__int64 *)qword_1803CEF18;
  v11 = -2147467261;
  v12 = -2147467261;
  if ( !qword_1803CEF18 )
  {
    v17 = MFGetCallStackTracingWeakReference(0);
    qword_1803CEF18 = v17;
    if ( v17 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
    {
      v16 = (__int64 *)qword_1803CEF18;
    }
    else
    {
      v16 = &qword_1803CE250;
      qword_1803CEF18 = (__int64)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v16 + 8) )
  {
    v18 = sub_1800402C0(v16);
    if ( *(_DWORD *)(v18 + 1996) != -2147467261 )
      sub_1800EC0E0(v18, "CSoundEventSchemePlugin::GetSoundAliasNameFromURL", 324, 2147500035LL);
  }
  if ( byte_1803CECE8 )
  {
    v15 = 26;
    goto LABEL_157;
  }
LABEL_158:
  sub_18003ECB0(v68);
  sub_180093088(&v83);
  return (unsigned int)v12;
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
0x1801f7040  lea     rcx, [rbp+4B0h+var_4B8]; void *
0x1801f7044  mov     r15, r9
0x1801f7047  call    memset
0x1801f704c  mov     r8d, 143h
0x1801f7052  mov     [rsp+5B0h+var_558], r12
0x1801f7057  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f705e  mov     [rsp+5B0h+var_550], r12
0x1801f7063  lea     rcx, [rsp+5B0h+var_560]
0x1801f7068  call    sub_18002FEE0
0x1801f706d  test    rbx, rbx
0x1801f7070  jnz     loc_1801F7113
0x1801f7076  mov     rcx, cs:qword_1803CEF18
0x1801f707d  mov     edi, 80004003h
0x1801f7082  mov     ebx, edi
0x1801f7084  test    rcx, rcx
0x1801f7087  jnz     short loc_1801F70D1
0x1801f7089  call    cs:MFGetCallStackTracingWeakReference
0x1801f7090  nop     dword ptr [rax+rax+00h]
0x1801f7095  mov     cs:qword_1803CEF18, rax
0x1801f709c  mov     rcx, rax
0x1801f709f  test    rax, rax
0x1801f70a2  jz      short loc_1801F70C3
0x1801f70a4  mov     rax, [rax]
0x1801f70a7  mov     edx, 7F0h
0x1801f70ac  mov     rax, [rax+8]
0x1801f70b0  call    cs:__guard_dispatch_icall_fptr
0x1801f70b6  test    eax, eax
0x1801f70b8  jz      short loc_1801F70C3
0x1801f70ba  mov     rcx, cs:qword_1803CEF18
0x1801f70c1  jmp     short loc_1801F70D1
0x1801f70c3  lea     rcx, qword_1803CE250
0x1801f70ca  mov     cs:qword_1803CEF18, rcx
0x1801f70d1  cmp     [rcx+8], r12b
0x1801f70d5  jz      short loc_1801F70FC
0x1801f70d7  call    sub_1800402C0
0x1801f70dc  cmp     [rax+7CCh], edi
0x1801f70e2  jz      short loc_1801F70FC
0x1801f70e4  mov     r9d, edi
0x1801f70e7  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f70ee  mov     r8d, 143h
0x1801f70f4  mov     rcx, rax
0x1801f70f7  call    sub_1800EC0E0
0x1801f70fc  cmp     cs:byte_1803CECE8, r14b
0x1801f7103  jb      loc_1801F7A33
0x1801f7109  mov     edx, 19h
0x1801f710e  jmp     loc_1801F7A15
0x1801f7113  test    rdi, rdi
0x1801f7116  jnz     loc_1801F71B9
0x1801f711c  mov     rcx, cs:qword_1803CEF18
0x1801f7123  mov     edi, 80004003h
0x1801f7128  mov     ebx, edi
0x1801f712a  test    rcx, rcx
0x1801f712d  jnz     short loc_1801F7177
0x1801f712f  call    cs:MFGetCallStackTracingWeakReference
0x1801f7136  nop     dword ptr [rax+rax+00h]
0x1801f713b  mov     cs:qword_1803CEF18, rax
0x1801f7142  mov     rcx, rax
0x1801f7145  test    rax, rax
0x1801f7148  jz      short loc_1801F7169
0x1801f714a  mov     rax, [rax]
0x1801f714d  mov     edx, 7F0h
0x1801f7152  mov     rax, [rax+8]
0x1801f7156  call    cs:__guard_dispatch_icall_fptr
0x1801f715c  test    eax, eax
0x1801f715e  jz      short loc_1801F7169
0x1801f7160  mov     rcx, cs:qword_1803CEF18
0x1801f7167  jmp     short loc_1801F7177
0x1801f7169  lea     rcx, qword_1803CE250
0x1801f7170  mov     cs:qword_1803CEF18, rcx
0x1801f7177  cmp     [rcx+8], r12b
0x1801f717b  jz      short loc_1801F71A2
0x1801f717d  call    sub_1800402C0
0x1801f7182  cmp     [rax+7CCh], edi
0x1801f7188  jz      short loc_1801F71A2
0x1801f718a  mov     r9d, edi
0x1801f718d  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f7194  mov     r8d, 144h
0x1801f719a  mov     rcx, rax
0x1801f719d  call    sub_1800EC0E0
0x1801f71a2  cmp     cs:byte_1803CECE8, r14b
0x1801f71a9  jb      loc_1801F7A33
0x1801f71af  mov     edx, 1Ah
0x1801f71b4  jmp     loc_1801F7A15
0x1801f71b9  test    r15, r15
0x1801f71bc  jnz     loc_1801F725F
0x1801f71c2  mov     rcx, cs:qword_1803CEF18
0x1801f71c9  mov     edi, 80004003h
0x1801f71ce  mov     ebx, edi
0x1801f71d0  test    rcx, rcx
0x1801f71d3  jnz     short loc_1801F721D
0x1801f71d5  call    cs:MFGetCallStackTracingWeakReference
0x1801f71dc  nop     dword ptr [rax+rax+00h]
0x1801f71e1  mov     cs:qword_1803CEF18, rax
0x1801f71e8  mov     rcx, rax
0x1801f71eb  test    rax, rax
0x1801f71ee  jz      short loc_1801F720F
0x1801f71f0  mov     rax, [rax]
0x1801f71f3  mov     edx, 7F0h
0x1801f71f8  mov     rax, [rax+8]
0x1801f71fc  call    cs:__guard_dispatch_icall_fptr
0x1801f7202  test    eax, eax
0x1801f7204  jz      short loc_1801F720F
0x1801f7206  mov     rcx, cs:qword_1803CEF18
0x1801f720d  jmp     short loc_1801F721D
0x1801f720f  lea     rcx, qword_1803CE250
0x1801f7216  mov     cs:qword_1803CEF18, rcx
0x1801f721d  cmp     [rcx+8], r12b
0x1801f7221  jz      short loc_1801F7248
0x1801f7223  call    sub_1800402C0
0x1801f7228  cmp     [rax+7CCh], edi
0x1801f722e  jz      short loc_1801F7248
0x1801f7230  mov     r9d, edi
0x1801f7233  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f723a  mov     r8d, 145h
0x1801f7240  mov     rcx, rax
0x1801f7243  call    sub_1800EC0E0
0x1801f7248  cmp     cs:byte_1803CECE8, r14b
0x1801f724f  jb      loc_1801F7A33
0x1801f7255  mov     edx, 1Bh
0x1801f725a  jmp     loc_1801F7A15
0x1801f725f  test    r13, r13
0x1801f7262  jnz     loc_1801F7305
0x1801f7268  mov     rcx, cs:qword_1803CEF18
0x1801f726f  mov     edi, 80004003h
0x1801f7274  mov     ebx, edi
0x1801f7276  test    rcx, rcx
0x1801f7279  jnz     short loc_1801F72C3
0x1801f727b  call    cs:MFGetCallStackTracingWeakReference
0x1801f7282  nop     dword ptr [rax+rax+00h]
0x1801f7287  mov     cs:qword_1803CEF18, rax
0x1801f728e  mov     rcx, rax
0x1801f7291  test    rax, rax
0x1801f7294  jz      short loc_1801F72B5
0x1801f7296  mov     rax, [rax]
0x1801f7299  mov     edx, 7F0h
0x1801f729e  mov     rax, [rax+8]
0x1801f72a2  call    cs:__guard_dispatch_icall_fptr
0x1801f72a8  test    eax, eax
0x1801f72aa  jz      short loc_1801F72B5
0x1801f72ac  mov     rcx, cs:qword_1803CEF18
0x1801f72b3  jmp     short loc_1801F72C3
0x1801f72b5  lea     rcx, qword_1803CE250
0x1801f72bc  mov     cs:qword_1803CEF18, rcx
0x1801f72c3  cmp     [rcx+8], r12b
0x1801f72c7  jz      short loc_1801F72EE
0x1801f72c9  call    sub_1800402C0
0x1801f72ce  cmp     [rax+7CCh], edi
0x1801f72d4  jz      short loc_1801F72EE
0x1801f72d6  mov     r9d, edi
0x1801f72d9  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f72e0  mov     r8d, 146h
0x1801f72e6  mov     rcx, rax
0x1801f72e9  call    sub_1800EC0E0
0x1801f72ee  cmp     cs:byte_1803CECE8, r14b
0x1801f72f5  jb      loc_1801F7A33
0x1801f72fb  mov     edx, 1Ch
0x1801f7300  jmp     loc_1801F7A15
0x1801f7305  mov     [rdi], r12
0x1801f7308  lea     rcx, [rbp+4B0h+var_4D0]
0x1801f730c  mov     [r15], r12
0x1801f730f  mov     rdx, rbx
0x1801f7312  mov     [r13+0], r12d
0x1801f7316  call    sub_18020B77C
0x1801f731b  mov     ebx, eax
0x1801f731d  test    eax, eax
0x1801f731f  jns     loc_1801F73BF
0x1801f7325  mov     rcx, cs:qword_1803CEF18
0x1801f732c  test    rcx, rcx
0x1801f732f  jnz     short loc_1801F7379
0x1801f7331  call    cs:MFGetCallStackTracingWeakReference
0x1801f7338  nop     dword ptr [rax+rax+00h]
0x1801f733d  mov     cs:qword_1803CEF18, rax
0x1801f7344  mov     rcx, rax
0x1801f7347  test    rax, rax
0x1801f734a  jz      short loc_1801F736B
0x1801f734c  mov     rax, [rax]
0x1801f734f  mov     edx, 7F0h
0x1801f7354  mov     rax, [rax+8]
0x1801f7358  call    cs:__guard_dispatch_icall_fptr
0x1801f735e  test    eax, eax
0x1801f7360  jz      short loc_1801F736B
0x1801f7362  mov     rcx, cs:qword_1803CEF18
0x1801f7369  jmp     short loc_1801F7379
0x1801f736b  lea     rcx, qword_1803CE250
0x1801f7372  mov     cs:qword_1803CEF18, rcx
0x1801f7379  cmp     [rcx+8], r12b
0x1801f737d  jz      short loc_1801F73A4
0x1801f737f  call    sub_1800402C0
0x1801f7384  cmp     [rax+7CCh], ebx
0x1801f738a  jz      short loc_1801F73A4
0x1801f738c  mov     r9d, ebx
0x1801f738f  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f7396  mov     r8d, 14Eh
0x1801f739c  mov     rcx, rax
0x1801f739f  call    sub_1800EC0E0
0x1801f73a4  cmp     cs:byte_1803CECE8, r14b
0x1801f73ab  jb      loc_1801F7A33
0x1801f73b1  mov     edx, 1Dh
0x1801f73b6  mov     dword ptr [rsp+5B0h+var_590], ebx
0x1801f73ba  jmp     loc_1801F7A19
0x1801f73bf  mov     r8d, [rbp+4B0h+var_4B0]
0x1801f73c3  lea     rdx, aMsWinsoundeven; "ms-winsoundevent"
0x1801f73ca  mov     rcx, [rbp+4B0h+var_4B8]
0x1801f73ce  call    _o__wcsnicmp
0x1801f73d3  test    eax, eax
0x1801f73d5  jz      loc_1801F7478
0x1801f73db  mov     rcx, cs:qword_1803CEF18
0x1801f73e2  mov     edi, 80070057h
0x1801f73e7  mov     ebx, edi
0x1801f73e9  test    rcx, rcx
0x1801f73ec  jnz     short loc_1801F7436
0x1801f73ee  call    cs:MFGetCallStackTracingWeakReference
0x1801f73f5  nop     dword ptr [rax+rax+00h]
0x1801f73fa  mov     cs:qword_1803CEF18, rax
0x1801f7401  mov     rcx, rax
0x1801f7404  test    rax, rax
0x1801f7407  jz      short loc_1801F7428
0x1801f7409  mov     rax, [rax]
0x1801f740c  mov     edx, 7F0h
0x1801f7411  mov     rax, [rax+8]
0x1801f7415  call    cs:__guard_dispatch_icall_fptr
0x1801f741b  test    eax, eax
0x1801f741d  jz      short loc_1801F7428
0x1801f741f  mov     rcx, cs:qword_1803CEF18
0x1801f7426  jmp     short loc_1801F7436
0x1801f7428  lea     rcx, qword_1803CE250
0x1801f742f  mov     cs:qword_1803CEF18, rcx
0x1801f7436  cmp     [rcx+8], r12b
0x1801f743a  jz      short loc_1801F7461
0x1801f743c  call    sub_1800402C0
0x1801f7441  cmp     [rax+7CCh], edi
0x1801f7447  jz      short loc_1801F7461
0x1801f7449  mov     r9d, edi
0x1801f744c  lea     rdx, aCsoundeventsch; "CSoundEventSchemePlugin::GetSoundAliasN"...
0x1801f7453  mov     r8d, 153h
0x1801f7459  mov     rcx, rax
0x1801f745c  call    sub_1800EC0E0
0x1801f7461  cmp     cs:byte_1803CECE8, r14b
0x1801f7468  jb      loc_1801F7A33
0x1801f746e  mov     edx, 1Eh
0x1801f7473  jmp     loc_1801F7A15
0x1801f7478  mov     ecx, [rbp+4B0h+var_4A0]
0x1801f747b  lea     eax, [rcx-1]
0x1801f747e  cmp     eax, 102h
0x1801f7483  ja      loc_1801F7981
0x1801f7489  lea     r8d, [rcx+1]
0x1801f748d  xor     edx, edx
0x1801f748f  add     r8, r8
0x1801f7492  lea     r9, [rsp+5B0h+var_558]
0x1801f7497  call    sub_18027A218
0x1801f749c  mov     ebx, eax
0x1801f749e  test    eax, eax
0x1801f74a0  jns     loc_1801F753C
0x1801f74a6  mov     rcx, cs:qword_1803CEF18
0x1801f74ad  test    rcx, rcx
0x1801f74b0  jnz     short loc_1801F74FA
0x1801f74b2  call    cs:MFGetCallStackTracingWeakReference
0x1801f74b9  nop     dword ptr [rax+rax+00h]
0x1801f74be  mov     cs:qword_1803CEF18, rax
0x1801f74c5  mov     rcx, rax
0x1801f74c8  test    rax, rax
0x1801f74cb  jz      short loc_1801F74EC
0x1801f74cd  mov     rax, [rax]
0x1801f74d0  mov     edx, 7F0h
0x1801f74d5  mov     rax, [rax+8]
0x1801f74d9  call    cs:__guard_dispatch_icall_fptr
0x1801f74df  test    eax, eax
0x1801f74e1  jz      short loc_1801F74EC
0x1801f74e3  mov     rcx, cs:qword_1803CEF18
0x1801f74ea  jmp     short loc_1801F74FA
0x1801f74ec  lea     rcx, qword_1803CE250
0x1801f74f3  mov     cs:qword_1803CEF18, rcx
0x1801f74fa  cmp     [rcx+8], r12b
  ... truncated ...
```
