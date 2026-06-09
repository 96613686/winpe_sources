# OlsGetRunCharWidths(COls *,CLsrun *,lsdevice,ushort const *,ulong,long,ulong,int *,long *,long *)

- ea: `0x18000a0b0`
- end: `0x18000aef1`
- name: `?OlsGetRunCharWidths@@YAJPEAUCOls@@PEAUCLsrun@@W4lsdevice@@PEBGKJKPEAHPEAJ5@Z`
- size: `3649`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x1800064d0`
- `0x180008f04`
- `0x18000a0b0`
- `0x18000af64`
- `0x18000b440`
- `0x180033af0`
- `0x180034060`
- `0x18003b4e0`
- `0x1800475c4`
- `0x18006ea80`
- `0x18008d830`
- `0x18009110a`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18000a97d`
- `KERNEL32!MulDiv` at `0x18000a97d`
- `KERNEL32!WideCharToMultiByte` at `0x18000acbd`
- `KERNEL32!WideCharToMultiByte` at `0x18000acbd`
- `USP10!ScriptGetProperties` at `0x18000ae36`
- `USP10!ScriptGetProperties` at `0x18000ae36`
- `GDI32!GetDeviceCaps` at `0x18000ae71`
- `GDI32!GetDeviceCaps` at `0x18000ae71`
- `GDI32!DeleteObject` at `0x18000a778`
- `GDI32!DeleteObject` at `0x18000a778`
- `GDI32!GetStockObject` at `0x18000ad0a`
- `GDI32!GetStockObject` at `0x18000ad0a`
- `GDI32!SelectObject` at `0x18000a5fc`
- `GDI32!SelectObject` at `0x18000a6a6`
- `GDI32!SelectObject` at `0x18000a76e`
- `GDI32!SelectObject` at `0x18000ad18`
- `GDI32!SelectObject` at `0x18000ad6d`
- `GDI32!SelectObject` at `0x18000a5fc`
- `GDI32!SelectObject` at `0x18000a6a6`
- `GDI32!SelectObject` at `0x18000a76e`
- `GDI32!SelectObject` at `0x18000ad18`
- `GDI32!SelectObject` at `0x18000ad6d`
- `GDI32!GetCharWidthW` at `0x18000a747`
- `GDI32!GetCharWidthW` at `0x18000ac61`
- `GDI32!GetCharWidthW` at `0x18000a747`
- `GDI32!GetCharWidthW` at `0x18000ac61`
- `GDI32!GetCharWidthA` at `0x18000a66e`
- `GDI32!GetCharWidthA` at `0x18000ace5`
- `GDI32!GetCharWidthA` at `0x18000a66e`
- `GDI32!GetCharWidthA` at `0x18000ace5`

## pseudocode

```c
__int64 __fastcall OlsGetRunCharWidths(
        __int64 *a1,
        int *a2,
        int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        __int64 a7,
        int *a8,
        _DWORD *a9,
        unsigned int *a10)
{
  __int64 v10; // rbx
  int *v13; // r13
  int v15; // ecx
  int v16; // esi
  int v17; // r11d
  __int64 v18; // r8
  int v19; // r9d
  int v20; // ecx
  int v21; // r10d
  int *v22; // r9
  int v23; // eax
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  __int64 v27; // r9
  int v28; // eax
  int v29; // edx
  int v30; // r11d
  int *v31; // r10
  int v32; // esi
  int v33; // eax
  int v34; // edx
  __int64 v35; // r8
  int v36; // eax
  int v37; // r10d
  int *v38; // r9
  int v39; // eax
  int v40; // ecx
  unsigned __int8 v41; // dl
  int v42; // r8d
  BOOL v43; // ecx
  __int64 v44; // rcx
  int v45; // edx
  int v46; // eax
  __int64 v47; // rdx
  __int16 v48; // dx
  HDC v49; // rdi
  __int64 v50; // r8
  __int16 v51; // r9
  __int64 v52; // rcx
  int v53; // edx
  int v54; // eax
  __int64 v55; // rcx
  __int16 v56; // ax
  struct CCcs *CcsBullet; // r14
  __int64 v58; // rax
  int v59; // esi
  unsigned int v60; // edi
  bool v61; // zf
  int *v62; // rdx
  int v63; // ecx
  int v64; // edx
  unsigned __int64 v65; // rbx
  CWidthCache *v66; // rdx
  _WORD *v67; // r8
  BOOL v68; // r14d
  UINT v69; // r13d
  int v70; // edx
  __int16 *v71; // rax
  struct CCcs *v72; // r14
  __int16 v73; // cx
  HDC v74; // r10
  __int64 v75; // rax
  __int64 v76; // rcx
  _WORD *v77; // r14
  WCHAR v78; // cx
  HDC v80; // r13
  __int16 v81; // r9
  __int64 v82; // rcx
  int v83; // edx
  int v84; // eax
  __int64 v85; // r9
  __int16 v86; // ax
  char v87; // dl
  HDC v88; // r9
  __int64 v89; // rax
  BOOL v90; // eax
  int *v91; // r8
  struct CCcs *Ccs; // rax
  void *v93; // rax
  int v94; // r8d
  int v95; // eax
  int v96; // eax
  int v97; // r8d
  _DWORD *v98; // rax
  int v99; // edx
  int v100; // eax
  int v101; // eax
  int v102; // edx
  _DWORD *v103; // rax
  int v104; // eax
  int v105; // edx
  int v106; // eax
  int v107; // eax
  int v108; // edx
  _DWORD *v109; // rax
  __int64 v110; // rax
  struct CUniscribe *Uniscribe; // rax
  __int16 v112; // r13
  void *v113; // rcx
  __int64 *v114; // rax
  unsigned __int16 v115; // r13
  __int64 *v116; // rcx
  __int64 v117; // rax
  int v118; // edx
  int v119; // eax
  unsigned __int16 v120; // cx
  HGDIOBJ StockObject; // rax
  __int16 v122; // ax
  __int16 v123; // ax
  __int64 v124; // r9
  __int64 v125; // rcx
  int cbMultiByte; // [rsp+28h] [rbp-D8h]
  WCHAR WideCharStr; // [rsp+40h] [rbp-C0h] BYREF
  int Buffer; // [rsp+48h] [rbp-B8h] BYREF
  HDC hdc; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 MultiByteStr[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v131; // [rsp+5Ch] [rbp-A4h]
  HGDIOBJ v132; // [rsp+60h] [rbp-A0h]
  BOOL v133; // [rsp+68h] [rbp-98h]
  int v134; // [rsp+6Ch] [rbp-94h]
  int v135; // [rsp+70h] [rbp-90h]
  struct CCcs *v136; // [rsp+78h] [rbp-88h]
  HGDIOBJ ho; // [rsp+80h] [rbp-80h]
  BOOL UsedDefaultChar; // [rsp+88h] [rbp-78h] BYREF
  HGDIOBJ h; // [rsp+90h] [rbp-70h]
  unsigned int *v140; // [rsp+98h] [rbp-68h]
  _DWORD *v141; // [rsp+A0h] [rbp-60h]
  struct tagLOGFONTW v142; // [rsp+B0h] [rbp-50h] BYREF

  v10 = *a1;
  v13 = a2;
  v15 = *a2 & 0x7FFFFFFF;
  v16 = *(_DWORD *)(v10 + 32);
  v141 = a9;
  ho = a2;
  v140 = a10;
  v17 = v15 - v16;
  if ( v15 == v16 )
    goto LABEL_47;
  v18 = *(_QWORD *)(v10 + 16);
  if ( !v18 )
    goto LABEL_47;
  v19 = *(_DWORD *)(v18 + 8);
  if ( !v19 )
    goto LABEL_47;
  if ( v15 < v16 / 2 )
  {
    *(_QWORD *)(v10 + 24) = 0;
    v118 = 0;
    if ( v15 )
      v118 = v15;
    v25 = CRunPtrBase::AdvanceCp((CRunPtrBase *)(v10 + 16), v118);
  }
  else
  {
    v20 = v15 - v16;
    if ( v17 < 0 )
    {
      while ( v20 < 0 )
      {
        v104 = *(_DWORD *)(v10 + 28);
        v105 = v104 + v20;
        if ( -v20 <= v104 )
        {
          *(_DWORD *)(v10 + 28) = v105;
LABEL_16:
          v20 = 0;
          break;
        }
        v106 = *(_DWORD *)(v10 + 24);
        v20 = v105;
        if ( v106 <= 0 )
        {
          *(_QWORD *)(v10 + 24) = 0;
          break;
        }
        v107 = v106 - 1;
        *(_DWORD *)(v10 + 24) = v107;
        v108 = *(_DWORD *)(v18 + 8);
        if ( v108 > 0 && v107 < v108 && *(_QWORD *)v18 && v107 >= 0 )
          v109 = (_DWORD *)(*(_QWORD *)v18 + *(_DWORD *)(v18 + 16) * v107);
        else
          v109 = 0;
        *(_DWORD *)(v10 + 28) = *v109;
      }
    }
    else
    {
      v21 = *(_DWORD *)(v10 + 24);
      if ( v19 > 0 && v21 < v19 && *(_QWORD *)v18 && v21 >= 0 )
        v22 = (int *)(*(_QWORD *)v18 + *(_DWORD *)(v18 + 16) * v21);
      else
        v22 = 0;
      while ( v20 > 0 )
      {
        v23 = *v22;
        *(_DWORD *)(v10 + 28) += v20;
        v24 = *(_DWORD *)(v10 + 28);
        if ( v24 < v23 )
          goto LABEL_16;
        v20 = v24 - v23;
        *(_DWORD *)(v10 + 24) = v21 + 1;
        if ( v21 + 1 >= *(_DWORD *)(v18 + 8) )
        {
          *(_DWORD *)(v10 + 24) = v21;
          *(_DWORD *)(v10 + 28) = v23;
          break;
        }
        *(_DWORD *)(v10 + 28) = 0;
        ++v21;
        v22 = (int *)((char *)v22 + *(int *)(v18 + 16));
      }
    }
    v25 = v16 + v17 - v20;
  }
  *(_DWORD *)(v10 + 32) = v25;
  v26 = v25 - v16;
  if ( !v26 )
  {
    v32 = 0;
LABEL_33:
    if ( !v32 )
      goto LABEL_47;
    v26 = v32;
    goto LABEL_35;
  }
  v27 = *(_QWORD *)(v10 + 48);
  if ( v27 && (v28 = *(_DWORD *)(v27 + 8)) != 0 )
  {
    v29 = v26;
    if ( v26 >= 0 )
    {
      v30 = *(_DWORD *)(v10 + 56);
      if ( v28 > 0 && v30 < v28 && *(_QWORD *)v27 && v30 >= 0 )
        v31 = (int *)(*(_QWORD *)v27 + *(_DWORD *)(v27 + 16) * v30);
      else
        v31 = 0;
      v32 = v26;
      while ( v29 > 0 )
      {
        v33 = *v31;
        *(_DWORD *)(v10 + 60) += v29;
        v34 = *(_DWORD *)(v10 + 60);
        if ( v34 < v33 )
          goto LABEL_35;
        *(_DWORD *)(v10 + 56) = v30 + 1;
        if ( v30 + 1 >= *(_DWORD *)(v27 + 8) )
        {
          *(_DWORD *)(v10 + 56) = v30;
          *(_DWORD *)(v10 + 60) = v33;
          goto LABEL_35;
        }
        v29 = v34 - v33;
        *(_DWORD *)(v10 + 60) = 0;
        ++v30;
        v31 = (int *)((char *)v31 + *(int *)(v27 + 16));
      }
      goto LABEL_33;
    }
    v32 = v26;
    while ( v29 < 0 )
    {
      v94 = *(_DWORD *)(v10 + 60);
      if ( -v29 <= v94 )
      {
        *(_DWORD *)(v10 + 60) = v94 + v29;
        break;
      }
      v95 = *(_DWORD *)(v10 + 56);
      if ( v95 <= 0 )
      {
        *(_QWORD *)(v10 + 56) = 0;
        break;
      }
      v29 += v94;
      v96 = v95 - 1;
      *(_DWORD *)(v10 + 56) = v96;
      v97 = *(_DWORD *)(v27 + 8);
      if ( v97 > 0 && v96 < v97 && *(_QWORD *)v27 && v96 >= 0 )
        v98 = (_DWORD *)(*(_QWORD *)v27 + *(_DWORD *)(v27 + 16) * v96);
      else
        v98 = 0;
      *(_DWORD *)(v10 + 60) = *v98;
    }
  }
  else
  {
    v32 = v26;
  }
LABEL_35:
  v35 = *(_QWORD *)(v10 + 64);
  if ( v35 )
  {
    v36 = *(_DWORD *)(v35 + 8);
    if ( v36 )
    {
      if ( v32 < 0 )
      {
        while ( v26 < 0 )
        {
          v99 = *(_DWORD *)(v10 + 76);
          if ( -v26 <= v99 )
          {
            *(_DWORD *)(v10 + 76) = v99 + v26;
            break;
          }
          v100 = *(_DWORD *)(v10 + 72);
          if ( v100 <= 0 )
          {
            *(_QWORD *)(v10 + 72) = 0;
            break;
          }
          v26 += v99;
          v101 = v100 - 1;
          *(_DWORD *)(v10 + 72) = v101;
          v102 = *(_DWORD *)(v35 + 8);
          if ( v102 > 0 && v101 < v102 && *(_QWORD *)v35 && v101 >= 0 )
            v103 = (_DWORD *)(*(_QWORD *)v35 + *(_DWORD *)(v35 + 16) * v101);
          else
            v103 = 0;
          *(_DWORD *)(v10 + 76) = *v103;
        }
      }
      else
      {
        v37 = *(_DWORD *)(v10 + 72);
        if ( v36 > 0 && v37 < v36 && *(_QWORD *)v35 && v37 >= 0 )
          v38 = (int *)(*(_QWORD *)v35 + *(_DWORD *)(v35 + 16) * v37);
        else
          v38 = 0;
        while ( v26 > 0 )
        {
          v39 = *v38;
          *(_DWORD *)(v10 + 76) += v26;
          v40 = *(_DWORD *)(v10 + 76);
          if ( v40 < v39 )
            break;
          *(_DWORD *)(v10 + 72) = v37 + 1;
          if ( v37 + 1 >= *(_DWORD *)(v35 + 8) )
          {
            *(_DWORD *)(v10 + 72) = v37;
            *(_DWORD *)(v10 + 76) = v39;
            break;
          }
          v26 = v40 - v39;
          *(_DWORD *)(v10 + 76) = 0;
          ++v37;
          v38 = (int *)((char *)v38 + *(int *)(v35 + 16));
        }
      }
    }
  }
LABEL_47:
  v41 = *(_BYTE *)(v10 + 162);
  v42 = *v13;
  v43 = a3 == 1;
  if ( v43 != ((v41 >> 1) & 1) )
  {
    if ( *(_DWORD *)(v10 + 128) != *(_DWORD *)(v10 + 112) && *(_DWORD *)(v10 + 132) != *(_DWORD *)(v10 + 116) )
    {
      v124 = *(_QWORD *)(v10 + 136);
      if ( v124 )
      {
        v122 = *(_WORD *)(v124 + 10);
        if ( v122 )
        {
          *(_WORD *)(v124 + 10) = v122 - 1;
          v41 = *(_BYTE *)(v10 + 162);
        }
      }
      *(_QWORD *)(v10 + 136) = 0;
    }
    *(_BYTE *)(v10 + 162) = v41 & 0xFD | (2 * v43);
  }
  if ( v42 < 0 )
  {
    v125 = *(_QWORD *)(v10 + 136);
    if ( v125 )
    {
      v123 = *(_WORD *)(v125 + 10);
      if ( v123 )
        *(_WORD *)(v125 + 10) = v123 - 1;
    }
    CcsBullet = CMeasurer::GetCcsBullet((CMeasurer *)v10, 0);
    *(_QWORD *)(v10 + 136) = CcsBullet;
    *(_WORD *)(v10 + 158) = -10;
    goto LABEL_74;
  }
  v44 = *(_QWORD *)(v10 + 48);
  if ( v44 && (v45 = *(_DWORD *)(v44 + 8)) != 0 )
  {
    if ( v45 > 0 && (v46 = *(_DWORD *)(v10 + 56), v46 < v45) && *(_QWORD *)v44 && v46 >= 0 )
      v47 = *(_QWORD *)v44 + *(_DWORD *)(v44 + 16) * v46;
    else
      v47 = 0;
    v48 = *(_WORD *)(v47 + 4);
    hdc = 0;
    if ( v48 >= 0 )
      goto LABEL_58;
  }
  else
  {
    hdc = 0;
  }
  v48 = *(_WORD *)(*(_QWORD *)(v10 + 16) + 28LL);
LABEL_58:
  if ( (*(int (__fastcall **)(struct IFormatCache *, _QWORD, HDC *))(*(_QWORD *)qword_1800A41F0 + 32LL))(
         qword_1800A41F0,
         (unsigned int)v48,
         &hdc) >= 0 )
  {
    v49 = hdc;
  }
  else
  {
    v49 = (HDC)g_defaultCF;
    hdc = (HDC)g_defaultCF;
  }
  v50 = *(_QWORD *)(v10 + 136);
  v51 = -1;
  if ( !v50
    || ((v52 = *(_QWORD *)(v10 + 48)) == 0 || (v53 = *(_DWORD *)(v52 + 8)) == 0
      ? (v56 = -1)
      : (v53 <= 0 || (v54 = *(_DWORD *)(v10 + 56), v54 >= v53) || !*(_QWORD *)v52 || v54 < 0
       ? (v55 = 0)
       : (v55 = *(_QWORD *)v52 + *(_DWORD *)(v52 + 16) * v54),
         v56 = *(_WORD *)(v55 + 4)),
        *(_WORD *)(v10 + 158) != v56 || (*(_BYTE *)(v10 + 162) & 8) != 0) )
  {
    v82 = *(_QWORD *)(v10 + 48);
    if ( v82 )
    {
      v83 = *(_DWORD *)(v82 + 8);
      if ( v83 )
      {
        if ( v83 > 0 && (v84 = *(_DWORD *)(v10 + 56), v84 < v83) && *(_QWORD *)v82 && v84 >= 0 )
          v85 = *(_QWORD *)v82 + *(_DWORD *)(v82 + 16) * v84;
        else
          v85 = 0;
        v51 = *(_WORD *)(v85 + 4);
      }
    }
    *(_WORD *)(v10 + 158) = v51;
    if ( v50 )
    {
      v86 = *(_WORD *)(v50 + 10);
      if ( v86 )
        *(_WORD *)(v50 + 10) = v86 - 1;
    }
    v87 = *(_BYTE *)(v10 + 162);
    v88 = 0;
    if ( (v87 & 2) != 0 )
    {
      v89 = *(_QWORD *)(v10 + 104);
      if ( *(_QWORD *)(v89 + 8) && *(_BYTE *)(v10 + 160) == 2 )
        v88 = *(HDC *)(v89 + 8);
    }
    else
    {
      v110 = *(_QWORD *)(v10 + 120);
      if ( *(_QWORD *)(v110 + 24) && *(_BYTE *)(v10 + 161) == 2 )
        v88 = *(HDC *)(v110 + 24);
    }
    v90 = (v87 & 0x10) != 0 && *(_BYTE *)(v10 + 160) == 2;
    v91 = (int *)(v10 + 112);
    if ( (v87 & 2) == 0 )
      v91 = (int *)(v10 + 128);
    Ccs = CFontCache::GetCcs(qword_1800A3EE0, (const struct CCharFormat *const)v49, *v91, v88, v90);
    *(_BYTE *)(v10 + 162) &= ~8u;
    *(_QWORD *)(v10 + 136) = Ccs;
    if ( !Ccs )
      return 4294967294LL;
  }
  if ( *((_BYTE *)v49 + 32) == 4 )
    *(_BYTE *)(v10 + 101) |= 0x20u;
  CcsBullet = *(struct CCcs **)(v10 + 136);
  *(_WORD *)(v10 + 96) = *((_WORD *)CcsBullet + 49);
LABEL_74:
  v136 = CcsBullet;
  if ( CcsBullet )
  {
    v58 = *(_QWORD *)(v10 + 40);
    v59 = 0;
    v60 = 0;
    v133 = 0;
    if ( (*(_DWORD *)(v58 + 192) & 0x61086013) == 0 || (v13[6] & 0x3FF) == 0 || *v13 < 0 )
      goto LABEL_77;
    Uniscribe = GetUniscribe();
    v112 = *((_WORD *)v13 + 12);
    v113 = (char *)Uniscribe + 56;
    v114 = (__int64 *)*((_QWORD *)Uniscribe + 7);
    v132 = v113;
    if ( v114 || ScriptGetProperties((const SCRIPT_PROPERTIES ***)v113, 0) >= 0 && (v114 = *(__int64 **)v132) != 0 )
    {
      if ( v114 == &off_1800A3010 )
      {
        v116 = v114;
      }
      else
      {
        v115 = v112 & 0x3FF;
        v116 = v114;
        if ( v115 < (unsigned __int16)g_cMaxScript )
        {
LABEL_203:
          v117 = v115;
          v13 = (int *)ho;
          v133 = (*(_DWORD *)v116[v117] & 0x20000) != 0;
LABEL_77:
          v61 = (*(_BYTE *)(v10 + 162) & 2) == 0;
          v62 = (int *)(v10 + 116);
          v63 = *(__int16 *)(*((_QWORD *)v13 + 1) + 18LL);
          v135 = v63;
          if ( v61 )
            v62 = (int *)(v10 + 132);
          v64 = *v62;
          if ( v64 != 1440 && v63 )
            v135 = MulDiv(v63, v64, 1440);
          while ( 1 )
          {
            if ( v60 >= a5 )
            {
LABEL_112:
              *v140 = v60;
              *v141 = v59;
              return 0;
            }
            v65 = *a4;
            if ( !v133 )
              break;
            if ( (unsigned int)(v65 - 768) > 0xB50
              || (v70 = 0, (unsigned int)(v65 - 768) > 0x6F)
              && !(unsigned int)CW32System::IsDiacritic(v65)
              && (_WORD)v65 != v81 )
            {
              v70 = *((__int16 *)CcsBullet + 47);
            }
LABEL_93:
            v59 += v70;
            *a8 = v70;
            ++v60;
            if ( v59 + v70 > a6 )
              goto LABEL_112;
            ++a8;
            ++a4;
          }
          if ( (unsigned int)(v65 - 8203) <= 4 )
          {
            v70 = 0;
            goto LABEL_93;
          }
          v66 = (struct CCcs *)((char *)CcsBullet + 16);
          if ( (unsigned __int16)v65 < 0x4E00u
            || (unsigned int)(v65 - 19968) > 0x51FF && (unsigned int)(v65 - 63744) > 0x1FF )
          {
            v67 = (_WORD *)(*((_QWORD *)CcsBullet + 6) + 4 * (*(int *)v66 & v65));
            if ( (_WORD)v65 == *v67 && v67[1] )
            {
              v68 = 1;
              v69 = (__int16)v67[1];
            }
            else
            {
              v68 = 0;
              v69 = 0;
            }
            if ( !*((_DWORD *)v66 + 4) )
            {
              ++*((_DWORD *)v66 + 3);
              if ( v68 )
                goto LABEL_91;
              if ( v67[1] )
                ++*((_DWORD *)v66 + 2);
              else
                ++*((_DWORD *)v66 + 1);
              if ( *((int *)v66 + 3) >= 64 )
                CWidthCache::CheckPerformance(v66);
            }
          }
          else
          {
            if ( (unsigned int)(v65 - 44032) <= 0x2BFF )
              v71 = (__int16 *)((char *)CcsBullet + 36);
            else
              v71 = (__int16 *)((char *)CcsBullet + 38);
            v69 = *v71;
            v68 = (_WORD)v69 != 0;
          }
          if ( v68 )
            goto LABEL_91;
          v72 = v136;
          h = SelectObject(*((HDC *)v136 + 8), *((HGDIOBJ *)v136 + 9));
          if ( !h )
            goto LABEL_91;
          v73 = *((_WORD *)v72 + 48);
          v74 = (HDC)*((_QWORD *)v72 + 8);
          v69 = *((unsigned __int16 *)v72 + 58);
          v131 = v73;
          hdc = v74;
          if ( (unsigned __int16)v65 < 0x4E00u )
          {
LABEL_107:
            v75 = *((_QWORD *)v72 + 6);
            v76 = v65 & *((int *)v72 + 4);
            *(_WORD *)(v75 + 4 * v76 + 2) = 0;
            WideCharStr = v65;
            Buffer = 0;
            v77 = (_WORD *)(v75 + 4 * v76);
            v78 = v65;
            if ( v69 == 42 || (unsigned int)v65 <= 0x7F )
            {
              if ( GetCharWidthA(v74, v65, v65, &Buffer) )
                goto LABEL_109;
              v78 = WideCharStr;
              v74 = hdc;
            }
            v134 = 0;
            ho = 0;
            v132 = 0;
            if ( v78 == 8364 )
            {
              if ( GetDeviceCaps(v74, 2) != 1 || (unsigned int)CW32System::IsEnhancedMetafileDC(hdc) )
              {
                v134 = 1;
                StockObject = GetStockObject(12);
                v132 = SelectObject(hdc, StockObject);
                memset_0(&v142, 0, sizeof(v142));
                CW32System::GetObjectW(v132, 92, &v142);
                if ( CW32System::_dwPlatformId == 1 )
                  v142.lfOutPrecision = 7;
                else
                  v142.lfOutPrecision = 9;
                ho = CW32System::CreateFontIndirect(&v142);
                SelectObject(hdc, ho);
              }
              v78 = WideCharStr;
            }
            if ( CW32System::_dwPlatformId != 1
              || CW32System::_dwMajorVersion != 4
              || CW32System::_dwMinorVersion
              || (unsigned int)v78 - 128 <= 0x7F
              || v69 != 950 && v69 != 936 )
            {
              goto LABEL_117;
            }
            GetCharWidthW(hdc, 0x4E00u, 0x4E00u, &Buffer);
            v77[1] = Buffer;
            if ( (unsigned int)WideCharStr - 19968 <= 0x51FF )
            {
LABEL_110:
              v77[1] -= v131;
              LOWORD(v69) = v77[1];
              *v77 = v65;
              v72 = v136;
LABEL_111:
              SelectObject(*((HDC *)v72 + 8), h);
              v69 = (__int16)v69;
LABEL_91:
              v70 = 1;
              CcsBullet = v136;
              if ( (int)(v69 + v135) > 1 )
                v70 = v69 + v135;
              goto LABEL_93;
            }
            UsedDefaultChar = 0;
            v119 = WideCharToMultiByte(v69, 0, &WideCharStr, 1, (LPSTR)MultiByteStr, 2, 0, &UsedDefaultChar);
            v120 = LOBYTE(MultiByteStr[0]);
            if ( v119 == 2 )
            {
              v120 = _byteswap_ushort(MultiByteStr[0]);
            }
            else if ( v119 <= 0 )
            {
LABEL_229:
              v78 = WideCharStr;
LABEL_117:
              if ( v78 == 0xFFFF )
              {
                v78 = -2;
                WideCharStr = -2;
              }
              v80 = hdc;
              if ( GetCharWidthW(hdc, v78, v78, &Buffer) )
                v77[1] = Buffer;
              if ( v134 )
              {
                SelectObject(v80, v132);
                DeleteObject(ho);
              }
              goto LABEL_110;
            }
            if ( !GetCharWidthA(hdc, v120, v120, &Buffer) )
              goto LABEL_229;
LABEL_109:
            v77[1] = Buffer;
            goto LABEL_110;
          }
          if ( (unsigned int)(v65 - 19968) > 0x51FF )
          {
            if ( (unsigned int)(v65 - 63744) > 0x1FF )
              goto LABEL_107;
            v73 = v131;
          }
          v93 = (char *)v72 + 36;
          if ( (unsigned int)(v65 - 44032) > 0x2B9F )
            v93 = (char *)v72 + 38;
          v132 = v93;
          CW32System::REGetCharWidth(v74, v65, (__int16 *)v93, v69, v73, cbMultiByte);
          LOWORD(v69) = *(_WORD *)v132;
          goto LABEL_111;
        }
      }
    }
    else
    {
      v116 = &off_1800A3010;
      *(_QWORD *)v132 = &off_1800A3010;
    }
    v115 = 0;
    goto LABEL_203;
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x18000a0b0  mov     [rsp-8+arg_10], rbx
0x18000a0b5  push    rbp
0x18000a0b6  push    rsi
0x18000a0b7  push    rdi
0x18000a0b8  push    r12
0x18000a0ba  push    r13
0x18000a0bc  push    r14
0x18000a0be  push    r15
0x18000a0c0  lea     rbp, [rsp-20h]
0x18000a0c5  sub     rsp, 120h
0x18000a0cc  mov     rax, cs:__security_cookie
0x18000a0d3  xor     rax, rsp
0x18000a0d6  mov     [rbp+50h+var_40], rax
0x18000a0da  mov     rbx, [rcx]
0x18000a0dd  mov     r15, r9
0x18000a0e0  mov     rax, [rbp+50h+arg_40]
0x18000a0e7  mov     r14d, r8d
0x18000a0ea  mov     ecx, [rdx]
0x18000a0ec  mov     r13, rdx
0x18000a0ef  mov     r12, [rbp+50h+arg_38]
0x18000a0f6  btr     ecx, 1Fh
0x18000a0fa  mov     esi, [rbx+20h]
0x18000a0fd  mov     r11d, ecx
0x18000a100  mov     [rbp+50h+var_B0], rax
0x18000a104  mov     rax, [rbp+50h+arg_48]
0x18000a10b  mov     [rbp+50h+ho], rdx
0x18000a10f  mov     [rbp+50h+var_B8], rax
0x18000a113  sub     r11d, esi
0x18000a116  jz      loc_18000A30C
0x18000a11c  mov     r8, [rbx+10h]
0x18000a120  test    r8, r8
0x18000a123  jz      loc_18000A30C
0x18000a129  mov     r9d, [r8+8]
0x18000a12d  test    r9d, r9d
0x18000a130  jz      loc_18000A30C
0x18000a136  mov     eax, esi
0x18000a138  cdq
0x18000a139  sub     eax, edx
0x18000a13b  sar     eax, 1
0x18000a13d  cmp     ecx, eax
0x18000a13f  jl      loc_18000AB97
0x18000a145  mov     ecx, r11d
0x18000a148  test    r11d, r11d
0x18000a14b  js      loc_18000AA70
0x18000a151  mov     r10d, [rbx+18h]
0x18000a155  test    r9d, r9d
0x18000a158  jle     loc_18000AC0F
0x18000a15e  cmp     r10d, r9d
0x18000a161  jge     loc_18000AC0F
0x18000a167  mov     rdx, [r8]
0x18000a16a  test    rdx, rdx
0x18000a16d  jz      loc_18000AC0F
0x18000a173  test    r10d, r10d
0x18000a176  js      loc_18000AC0F
0x18000a17c  mov     eax, r10d
0x18000a17f  imul    eax, [r8+10h]
0x18000a184  movsxd  r9, eax
0x18000a187  add     r9, rdx
0x18000a18a  nop     word ptr [rax+rax+00h]
0x18000a190  test    ecx, ecx
0x18000a192  jle     short loc_18000A1CC
0x18000a194  mov     eax, [r9]
0x18000a197  add     [rbx+1Ch], ecx
0x18000a19a  mov     ecx, [rbx+1Ch]
0x18000a19d  cmp     ecx, eax
0x18000a19f  jl      short loc_18000A1CA
0x18000a1a1  lea     edx, [r10+1]
0x18000a1a5  sub     ecx, eax
0x18000a1a7  mov     [rbx+18h], edx
0x18000a1aa  cmp     edx, [r8+8]
0x18000a1ae  jge     loc_18000A900
0x18000a1b4  mov     dword ptr [rbx+1Ch], 0
0x18000a1bb  mov     r10d, edx
0x18000a1be  movsxd  rax, dword ptr [r8+10h]
0x18000a1c2  add     r9, rax
0x18000a1c5  jmp     short loc_18000A190
0x18000a1c7  mov     [rbx+1Ch], edx
0x18000a1ca  xor     ecx, ecx
0x18000a1cc  sub     r11d, ecx
0x18000a1cf  lea     ecx, [rsi+r11]
0x18000a1d3  mov     [rbx+20h], ecx
0x18000a1d6  sub     ecx, esi
0x18000a1d8  jz      loc_18000A278
0x18000a1de  mov     r9, [rbx+30h]
0x18000a1e2  test    r9, r9
0x18000a1e5  jz      loc_18000A8E1
0x18000a1eb  mov     eax, [r9+8]
0x18000a1ef  test    eax, eax
0x18000a1f1  jz      loc_18000A8E1
0x18000a1f7  mov     edx, ecx
0x18000a1f9  test    ecx, ecx
0x18000a1fb  js      loc_18000A98C
0x18000a201  mov     r11d, [rbx+38h]
0x18000a205  test    eax, eax
0x18000a207  jle     loc_18000ABFC
0x18000a20d  cmp     r11d, eax
0x18000a210  jge     loc_18000ABFC
0x18000a216  mov     r8, [r9]
0x18000a219  test    r8, r8
0x18000a21c  jz      loc_18000ABFC
0x18000a222  test    r11d, r11d
0x18000a225  js      loc_18000ABFC
0x18000a22b  mov     eax, r11d
0x18000a22e  imul    eax, [r9+10h]
0x18000a233  movsxd  r10, eax
0x18000a236  add     r10, r8
0x18000a239  mov     esi, ecx
0x18000a23b  nop     dword ptr [rax+rax+00h]
0x18000a240  test    edx, edx
0x18000a242  jle     short loc_18000A27A
0x18000a244  mov     eax, [r10]
0x18000a247  add     [rbx+3Ch], edx
0x18000a24a  mov     edx, [rbx+3Ch]
0x18000a24d  cmp     edx, eax
0x18000a24f  jl      short loc_18000A284
0x18000a251  lea     r8d, [r11+1]
0x18000a255  mov     [rbx+38h], r8d
0x18000a259  cmp     r8d, [r9+8]
0x18000a25d  jge     loc_18000A8F4
0x18000a263  sub     edx, eax
0x18000a265  mov     dword ptr [rbx+3Ch], 0
0x18000a26c  movsxd  rax, dword ptr [r9+10h]
0x18000a270  mov     r11d, r8d
0x18000a273  add     r10, rax
0x18000a276  jmp     short loc_18000A240
0x18000a278  mov     esi, ecx
0x18000a27a  test    esi, esi
0x18000a27c  jz      loc_18000A30C
0x18000a282  mov     ecx, esi
0x18000a284  mov     r8, [rbx+40h]
0x18000a288  test    r8, r8
0x18000a28b  jz      short loc_18000A30C
0x18000a28d  mov     eax, [r8+8]
0x18000a291  test    eax, eax
0x18000a293  jz      short loc_18000A30C
0x18000a295  test    esi, esi
0x18000a297  js      loc_18000A9F7
0x18000a29d  mov     r10d, [rbx+48h]
0x18000a2a1  test    eax, eax
0x18000a2a3  jle     loc_18000AC04
0x18000a2a9  cmp     r10d, eax
0x18000a2ac  jge     loc_18000AC04
0x18000a2b2  mov     rdx, [r8]
0x18000a2b5  test    rdx, rdx
0x18000a2b8  jz      loc_18000AC04
0x18000a2be  test    r10d, r10d
0x18000a2c1  js      loc_18000AC04
0x18000a2c7  mov     eax, r10d
0x18000a2ca  imul    eax, [r8+10h]
0x18000a2cf  movsxd  r9, eax
0x18000a2d2  add     r9, rdx
0x18000a2d5  xor     r11d, r11d
0x18000a2d8  test    ecx, ecx
0x18000a2da  jle     short loc_18000A30C
0x18000a2dc  mov     eax, [r9]
0x18000a2df  add     [rbx+4Ch], ecx
0x18000a2e2  mov     ecx, [rbx+4Ch]
0x18000a2e5  cmp     ecx, eax
0x18000a2e7  jl      short loc_18000A30C
0x18000a2e9  lea     edx, [r10+1]
0x18000a2ed  mov     [rbx+48h], edx
0x18000a2f0  cmp     edx, [r8+8]
0x18000a2f4  jge     loc_18000A8E8
0x18000a2fa  sub     ecx, eax
0x18000a2fc  mov     [rbx+4Ch], r11d
0x18000a300  movsxd  rax, dword ptr [r8+10h]
0x18000a304  mov     r10d, edx
0x18000a307  add     r9, rax
0x18000a30a  jmp     short loc_18000A2D8
0x18000a30c  movzx   edx, byte ptr [rbx+0A2h]
0x18000a313  xor     ecx, ecx
0x18000a315  mov     r8d, [r13+0]
0x18000a319  cmp     r14d, 1
0x18000a31d  mov     eax, edx
0x18000a31f  setz    cl
0x18000a322  shr     eax, 1
0x18000a324  and     eax, 1
0x18000a327  cmp     ecx, eax
0x18000a329  jnz     loc_18000A8AF
0x18000a32f  test    r8d, r8d
0x18000a332  js      loc_18000AE1A
0x18000a338  mov     rcx, [rbx+30h]
0x18000a33c  test    rcx, rcx
0x18000a33f  jz      loc_18000A8A1
0x18000a345  mov     edx, [rcx+8]
0x18000a348  test    edx, edx
0x18000a34a  jz      loc_18000A8A1
0x18000a350  jle     loc_18000ABF5
0x18000a356  mov     eax, [rbx+38h]
0x18000a359  cmp     eax, edx
0x18000a35b  jge     loc_18000ABF5
0x18000a361  mov     r8, [rcx]
0x18000a364  test    r8, r8
0x18000a367  jz      loc_18000ABF5
0x18000a36d  test    eax, eax
0x18000a36f  js      loc_18000ABF5
0x18000a375  imul    eax, [rcx+10h]
0x18000a379  movsxd  rdx, eax
0x18000a37c  add     rdx, r8
0x18000a37f  movzx   edx, word ptr [rdx+4]
0x18000a383  mov     [rsp+150h+hdc], 0
0x18000a38c  test    dx, dx
0x18000a38f  jns     short loc_18000A399
0x18000a391  mov     rax, [rbx+10h]
0x18000a395  movzx   edx, word ptr [rax+1Ch]
0x18000a399  mov     rcx, cs:qword_1800A41F0
0x18000a3a0  lea     r8, [rsp+150h+hdc]
0x18000a3a5  movsx   edx, dx
0x18000a3a8  mov     rax, [rcx]
0x18000a3ab  mov     rax, [rax+20h]
0x18000a3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3b4  test    eax, eax
0x18000a3b6  jns     loc_18000A7BF
0x18000a3bc  lea     rdi, ?g_defaultCF@@3VCCharFormat@@A; CCharFormat g_defaultCF
0x18000a3c3  mov     [rsp+150h+hdc], rdi
0x18000a3c8  mov     r8, [rbx+88h]
0x18000a3cf  mov     r9d, 0FFFFFFFFh
0x18000a3d5  test    r8, r8
0x18000a3d8  jz      loc_18000A7C9
0x18000a3de  mov     rcx, [rbx+30h]
0x18000a3e2  test    rcx, rcx
0x18000a3e5  jz      loc_18000A90C
0x18000a3eb  mov     edx, [rcx+8]
0x18000a3ee  test    edx, edx
0x18000a3f0  jz      loc_18000A90C
0x18000a3f6  jle     loc_18000AC17
0x18000a3fc  mov     eax, [rbx+38h]
0x18000a3ff  cmp     eax, edx
0x18000a401  jge     loc_18000AC17
0x18000a407  mov     rdx, [rcx]
0x18000a40a  test    rdx, rdx
0x18000a40d  jz      loc_18000AC17
0x18000a413  test    eax, eax
0x18000a415  js      loc_18000AC17
0x18000a41b  imul    eax, [rcx+10h]
0x18000a41f  movsxd  rcx, eax
0x18000a422  add     rcx, rdx
0x18000a425  movzx   eax, word ptr [rcx+4]
0x18000a429  cmp     [rbx+9Eh], ax
0x18000a430  jnz     loc_18000A7C9
0x18000a436  test    byte ptr [rbx+0A2h], 8
0x18000a43d  jnz     loc_18000A7C9
0x18000a443  cmp     byte ptr [rdi+20h], 4
0x18000a447  jz      loc_18000AE2B
0x18000a44d  mov     r14, [rbx+88h]
0x18000a454  movzx   eax, word ptr [r14+62h]
0x18000a459  mov     [rbx+60h], ax
0x18000a45d  mov     [rsp+150h+var_D8], r14
0x18000a462  test    r14, r14
0x18000a465  jz      loc_18000A897
0x18000a46b  mov     rax, [rbx+28h]
0x18000a46f  xor     esi, esi
0x18000a471  xor     edi, edi
0x18000a473  mov     [rsp+150h+var_E8], esi
0x18000a477  test    dword ptr [rax+0C0h], 61086013h
0x18000a481  jz      short loc_18000A493
0x18000a483  mov     eax, 3FFh
0x18000a488  test    [r13+18h], ax
0x18000a48d  jnz     loc_18000AB16
0x18000a493  test    byte ptr [rbx+0A2h], 2
0x18000a49a  lea     rdx, [rbx+74h]
0x18000a49e  mov     rax, [r13+8]
0x18000a4a2  movsx   ecx, word ptr [rax+12h]; nNumber
0x18000a4a6  mov     [rsp+150h+var_E0], ecx
0x18000a4aa  jnz     short loc_18000A4B3
0x18000a4ac  lea     rdx, [rbx+84h]
0x18000a4b3  mov     edx, [rdx]; nNumerator
0x18000a4b5  cmp     edx, 5A0h
0x18000a4bb  jz      short loc_18000A4C5
0x18000a4bd  test    ecx, ecx
0x18000a4bf  jnz     loc_18000A977
0x18000a4c5  mov     r9d, 640h
0x18000a4cb  mov     ecx, 4E00h
0x18000a4d0  cmp     edi, [rbp+50h+arg_20]
0x18000a4d6  jnb     loc_18000A6B5
0x18000a4dc  cmp     [rsp+150h+var_E8], 0
0x18000a4e1  movzx   ebx, word ptr [r15]
0x18000a4e5  jnz     loc_18000A783
0x18000a4eb  lea     eax, [rbx-200Bh]
0x18000a4f1  cmp     eax, 4
0x18000a4f4  jbe     loc_18000A58B
0x18000a4fa  lea     rdx, [r14+10h]
0x18000a4fe  cmp     bx, cx
0x18000a501  jnb     loc_18000A5AF
0x18000a507  movsxd  rax, dword ptr [rdx]
0x18000a50a  mov     rcx, rbx
0x18000a50d  and     rcx, rax
0x18000a510  mov     rax, [rdx+20h]
0x18000a514  lea     r8, [rax+rcx*4]
0x18000a518  cmp     bx, [rax+rcx*4]
0x18000a51c  jnz     loc_18000A6EA
0x18000a522  movsx   eax, word ptr [r8+2]
0x18000a527  test    ax, ax
0x18000a52a  jz      loc_18000A6EA
0x18000a530  mov     r14d, 1
0x18000a536  mov     r13d, eax
0x18000a539  cmp     dword ptr [rdx+10h], 0
0x18000a53d  jnz     loc_18000A5E6
0x18000a543  inc     dword ptr [rdx+0Ch]
0x18000a546  test    r14d, r14d
  ... truncated ...
```
