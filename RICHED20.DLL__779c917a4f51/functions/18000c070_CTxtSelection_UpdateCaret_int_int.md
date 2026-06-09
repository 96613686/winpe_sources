# CTxtSelection::UpdateCaret(int,int)

- ea: `0x18000c070`
- end: `0x18000cf4a`
- name: `?UpdateCaret@CTxtSelection@@QEAAHHH@Z`
- size: `3802`
- prototype: `__int64 __fastcall(CTxtSelection *__hidden this, int, int)`
- caller_count: `17`
- callee_count: `26`
- tags: `installer_update`

## callers

- `0x180006610`
- `0x18000b920`
- `0x18002bfc0`
- `0x18002cc44`
- `0x1800323d8`
- `0x180032e18`
- `0x1800385d0`
- `0x18003a300`
- `0x18003f9c0`
- `0x1800492b0`
- `0x180058e50`
- `0x18005d2f4`
- `0x18005d340`
- `0x18005d520`
- `0x18007ef48`
- `0x1800809e0`
- `0x180080e14`

## callees

- `0x180008f80`
- `0x18000b440`
- `0x18000c070`
- `0x18000cf50`
- `0x18000d4a0`
- `0x18000d670`
- `0x180010510`
- `0x1800110b0`
- `0x1800114d0`
- `0x1800165c0`
- `0x18001dfd0`
- `0x1800202a0`
- `0x180020eb0`
- `0x180026e20`
- `0x1800275a8`
- `0x180027d38`
- `0x180038bd0`
- `0x180039500`
- `0x18003be28`
- `0x18003d108`
- `0x18003dadc`
- `0x18004222c`
- `0x180043f80`
- `0x180045f24`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18000c941`
- `KERNEL32!MulDiv` at `0x18000ca5e`
- `KERNEL32!MulDiv` at `0x18000c941`
- `KERNEL32!MulDiv` at `0x18000ca5e`
- `KERNEL32!EnterCriticalSection` at `0x18000c3f2`
- `KERNEL32!EnterCriticalSection` at `0x18000c3f2`
- `KERNEL32!LeaveCriticalSection` at `0x18000c5b5`
- `KERNEL32!LeaveCriticalSection` at `0x18000ca14`
- `KERNEL32!LeaveCriticalSection` at `0x18000c5b5`
- `KERNEL32!LeaveCriticalSection` at `0x18000ca14`
- `GDI32!GetDeviceCaps` at `0x18000c4b8`
- `GDI32!GetDeviceCaps` at `0x18000c4b8`

## pseudocode

```c
__int64 __fastcall CTxtSelection::UpdateCaret(CTxtSelection *this, int a2, int a3)
{
  __int64 v6; // r9
  __int64 v7; // r15
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // r8
  int v12; // r14d
  _DWORD *v13; // rcx
  unsigned int v14; // eax
  bool v15; // zf
  int v16; // edx
  __int16 v17; // ax
  int v18; // edx
  LONG top; // r14d
  LONG bottom; // esi
  __int128 v21; // xmm0
  __int64 v22; // r8
  CRunPtrBase *v23; // r11
  __int64 v24; // r10
  int v25; // ecx
  int v26; // edi
  int v27; // edx
  int v28; // r12d
  int v29; // eax
  int v30; // eax
  int v31; // r9d
  _DWORD *v32; // r8
  int v33; // ecx
  _DWORD *v34; // r8
  __int64 v35; // rax
  int v36; // r12d
  int v37; // edi
  int v38; // r13d
  __int64 v39; // rax
  int v40; // eax
  int v41; // r9d
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rcx
  _QWORD *v45; // rdx
  __int64 v46; // rax
  CDisplay *v47; // rcx
  HDC v48; // rdi
  int ZoomDenominator; // eax
  __int64 v50; // rdx
  __int64 v51; // rcx
  int v52; // r12d
  int DeviceCaps; // edi
  struct CCcs *Ccs; // r12
  struct CCharFormat *v55; // r13
  int v56; // edx
  int v57; // edi
  __int64 v58; // rax
  int v59; // ecx
  __int16 v60; // ax
  int v61; // edx
  int v62; // r10d
  int v63; // r9d
  int v64; // eax
  int v65; // r8d
  __int64 *v66; // r11
  __int64 *v67; // rdi
  __int64 *v68; // r12
  __int64 *v69; // rax
  int v70; // eax
  __int64 *v71; // r9
  __int64 *v72; // rax
  int v73; // eax
  int v74; // edi
  int v75; // r12d
  int v76; // r13d
  LONG v77; // r9d
  LONG v78; // r11d
  LONG v79; // eax
  LONG v80; // eax
  int v81; // eax
  int v82; // r11d
  BOOL v84; // eax
  int v85; // r14d
  int IsBiDiLcid; // eax
  int v87; // ecx
  int v88; // edx
  int IsHScrollEnabled; // eax
  LONG v90; // eax
  __int16 v91; // ax
  int v92; // eax
  int v93; // eax
  int v94; // eax
  unsigned __int8 v95; // r11
  unsigned __int8 Level; // r12
  unsigned __int8 v97; // r11
  int v98; // ecx
  int v99; // eax
  CTxtPtr *v100; // rcx
  const struct CParaFormat *PF; // rax
  LONG left; // r9d
  char v103; // cl
  struct CLine *Line; // rax
  unsigned int v105; // esi
  struct CLine *v106; // rax
  struct CLine *v107; // rax
  __int64 v108; // r9
  int v109; // r11d
  __int64 v110; // r10
  unsigned int v111; // eax
  int v112; // edi
  LONG v113; // eax
  bool v114; // sf
  int v115; // edi
  int v116; // eax
  BOOL v117; // [rsp+50h] [rbp-B0h]
  int v118; // [rsp+54h] [rbp-ACh] BYREF
  int nDenominator; // [rsp+58h] [rbp-A8h]
  BOOL v120; // [rsp+5Ch] [rbp-A4h]
  int v121; // [rsp+60h] [rbp-A0h]
  int v122; // [rsp+64h] [rbp-9Ch]
  unsigned int v123; // [rsp+68h] [rbp-98h]
  int v124; // [rsp+6Ch] [rbp-94h]
  int v125; // [rsp+70h] [rbp-90h] BYREF
  __int64 v126; // [rsp+78h] [rbp-88h] BYREF
  __int64 v127; // [rsp+80h] [rbp-80h]
  struct CCharFormat *v128; // [rsp+88h] [rbp-78h] BYREF
  int v129; // [rsp+90h] [rbp-70h]
  int v130; // [rsp+94h] [rbp-6Ch]
  int v131; // [rsp+98h] [rbp-68h]
  __int64 v132; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v133; // [rsp+A8h] [rbp-58h]
  __int64 v134; // [rsp+B0h] [rbp-50h]
  __int64 *v135; // [rsp+B8h] [rbp-48h]
  _QWORD v136[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v137; // [rsp+D0h] [rbp-30h] BYREF
  int v138; // [rsp+E0h] [rbp-20h]
  __int64 v139; // [rsp+E4h] [rbp-1Ch]
  int v140; // [rsp+ECh] [rbp-14h]
  __int64 v141; // [rsp+F0h] [rbp-10h] BYREF
  int v142; // [rsp+F8h] [rbp-8h]
  int v143; // [rsp+FCh] [rbp-4h]
  __int64 v144; // [rsp+100h] [rbp+0h]
  int v145; // [rsp+108h] [rbp+8h]
  int v146; // [rsp+10Ch] [rbp+Ch]
  __int64 v147; // [rsp+110h] [rbp+10h]
  _QWORD *v148; // [rsp+118h] [rbp+18h]
  struct tagRECT v149; // [rsp+120h] [rbp+20h] BYREF
  struct tagRECT v150; // [rsp+130h] [rbp+30h] BYREF

  v6 = *(_QWORD *)(*((_QWORD *)this + 13) + 48LL);
  if ( v6 )
  {
    *(_DWORD *)(v6 + 16) |= 1u;
    v88 = *(_DWORD *)(v6 + 16);
    if ( (v88 & 2) == 0 )
      *(_DWORD *)(v6 + 16) = (2 * a2) ^ (v88 ^ (2 * a2)) & 0xFFFFFFFD;
    return 0;
  }
  v7 = *((_QWORD *)this + 6);
  v8 = *(_DWORD *)(v7 + 180);
  if ( (v8 & 0x10000) != 0 )
    return 0;
  if ( (v8 & 8) == 0 )
  {
    if ( a2 )
      *(_DWORD *)(v7 + 180) = v8 | 0x8000;
    return 0;
  }
  v9 = *(_QWORD *)(v7 + 48);
  v125 = 0;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 248LL))(v9, &v125);
  v117 = 0;
  v120 = 0;
  v10 = CTxtPtr::IsAfterEOP((CTxtSelection *)((char *)this + 24));
  v11 = *((_QWORD *)this + 13);
  v12 = v10;
  nDenominator = v10;
  v134 = v11;
  v126 = 0;
  v132 = 0;
  v133 = 0;
  v135 = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 24LL))(v11, &v132);
  v13 = (_DWORD *)*((_QWORD *)this + 13);
  v150 = 0;
  v149 = 0;
  v121 = v13[18];
  v14 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v13 + 288LL))(v13);
  v15 = *(_BYTE *)(v7 + 180) >= 0;
  v123 = v14;
  if ( !v15 )
  {
    v16 = *((_DWORD *)this + 34);
    if ( (v16 & 8) != 0 || a3 )
    {
      v17 = *((_WORD *)this + 49);
      v18 = v16 | 8;
      *((_DWORD *)this + 34) = v18;
      if ( (v18 & 0xA20) == 0 && (v17 & 0x10) == 0 )
      {
        *((_DWORD *)this + 34) = v18 | 0x200;
        CTxtSelection::CheckChangeKeyboardLayout(this);
        if ( !v12
          && (*(_BYTE *)(v7 + 192) & 1) != 0
          && (unsigned int)CRunPtrBase::IsValid((CTxtSelection *)((char *)this + 56))
          && (!*((_DWORD *)this + 17) || !(unsigned int)CRunPtrBase::GetCchLeft((CTxtSelection *)((char *)this + 56))) )
        {
          CRunPtrBase::AdjustBackward((CTxtSelection *)((char *)this + 56));
          v85 = (unsigned int)*((unsigned __int8 *)CRchTxtPtr::GetCF((CTxtSelection *)((char *)this + 8)) + 4) - 177 <= 1;
          CRunPtrBase::AdjustForward((CTxtSelection *)((char *)this + 56));
          if ( v85 != (unsigned int)*((unsigned __int8 *)CRchTxtPtr::GetCF((CTxtSelection *)((char *)this + 8)) + 4)
                    - 177 <= 1 )
          {
            IsBiDiLcid = CW32System::IsBiDiLcid((unsigned __int16)CW32System::_hklCurrent);
            v87 = nDenominator;
            if ( v85 != IsBiDiLcid )
              v87 = 1;
            nDenominator = v87;
          }
        }
        *((_DWORD *)this + 34) &= ~0x200u;
      }
    }
  }
  (*(void (__fastcall **)(_QWORD, struct tagRECT *))(**(_QWORD **)(v7 + 48) + 192LL))(*(_QWORD *)(v7 + 48), &v150);
  CDisplay::GetViewRect(*((CDisplay **)this + 13), &v149, &v150);
  top = v150.top;
  bottom = v150.bottom;
  if ( v149.top > v150.top )
    top = v149.top;
  if ( v149.bottom < v150.bottom )
    bottom = v149.bottom;
  v130 = v149.right - v149.left;
  if ( a2 )
  {
    v92 = *(_DWORD *)(v7 + 180);
    v117 = (v125 & 0x40) != 0;
    v120 = (v125 & 0x80) != 0;
    if ( (v92 & 0x80000) == 0 || (*((_DWORD *)this + 34) & 0x2000) == 0 )
    {
      if ( (v92 & 0x80u) == 0 && (v92 & 0x20) != 0 )
      {
        v117 = (v125 & 0x40) != 0;
        v120 = (v125 & 0x80) != 0;
        if ( (v125 & 0x40) != 0 || (v125 & 0x80) != 0 )
        {
          v93 = v92 | 0x8000;
          *(_DWORD *)(v7 + 180) = v93;
          if ( (v93 & 0x80000) == 0 || (*((_DWORD *)this + 34) & 0x1000) == 0 )
          {
            v120 = 0;
            v117 = 0;
          }
        }
      }
      else
      {
        v117 = (v125 & 0x40) != 0;
        v120 = (v125 & 0x80) != 0;
      }
    }
  }
  *((_DWORD *)this + 34) &= ~0x1000u;
  if ( !*((_DWORD *)this + 22)
    && (*(_WORD *)(*((_QWORD *)this + 6) + 184LL) & 0x2000) != 0
    && (*((_WORD *)CRchTxtPtr::GetPF((CTxtSelection *)((char *)this + 8)) + 1) & 0x100) != 0 )
  {
    goto LABEL_119;
  }
  v21 = *(_OWORD *)((char *)this + 24);
  v22 = *((_QWORD *)this + 7);
  v23 = (CTxtSelection *)((char *)this + 56);
  v24 = *((_QWORD *)this + 9);
  v25 = *((_DWORD *)this + 16);
  v26 = *((_DWORD *)this + 17);
  v27 = *((_DWORD *)this + 20);
  v28 = *((_DWORD *)this + 21);
  v136[0] = &CRchTxtPtr::`vftable';
  v29 = *((_DWORD *)this + 10);
  v137 = v21;
  *(_QWORD *)&v21 = *(_QWORD *)((char *)this + 44);
  v124 = v29;
  v138 = v29;
  v30 = *((_DWORD *)this + 13);
  v139 = v21;
  v128 = 0;
  v140 = v30;
  v141 = v22;
  v142 = v25;
  v143 = v26;
  v144 = v24;
  v145 = v27;
  v146 = v28;
  if ( v22 )
  {
    v31 = *(_DWORD *)(v22 + 8);
    if ( v31 )
    {
      v32 = v31 > 0 && v25 < v31 && *(_QWORD *)v22 && v25 >= 0
          ? (_DWORD *)(*(_QWORD *)v22 + *(_DWORD *)(v22 + 16) * v25)
          : 0LL;
      v23 = (CTxtSelection *)((char *)this + 56);
      if ( *v32 == v26 && v25 < v31 - 1 )
      {
        v143 = 0;
        v142 = v25 + 1;
      }
    }
  }
  if ( v24 )
  {
    v33 = *(_DWORD *)(v24 + 8);
    if ( v33 )
    {
      v34 = v33 > 0 && v27 < v33 && *(_QWORD *)v24 && v27 >= 0
          ? (_DWORD *)(*(_QWORD *)v24 + *(_DWORD *)(v24 + 16) * v27)
          : 0LL;
      if ( *v34 == v28 && v27 < v33 - 1 )
      {
        v146 = 0;
        v145 = v27 + 1;
      }
    }
  }
  v35 = *((_QWORD *)this + 6);
  v36 = -1;
  v37 = 8216;
  v122 = -1;
  if ( (*(_BYTE *)(v35 + 192) & 1) != 0 && (unsigned int)CRunPtrBase::IsValid(v23) )
  {
    v94 = *((_DWORD *)this + 34);
    if ( (v94 & 0x800) != 0 )
    {
      v37 = ((((v94 & 1) == 0) + 1) << 14) | 0x2018;
    }
    else if ( !(unsigned int)CRchTxtPtr::GetIchRunCF((CTxtSelection *)((char *)this + 8))
           || !(unsigned int)CRchTxtPtr::GetCchLeftRunCF((CTxtSelection *)((char *)this + 8)) )
    {
      LOWORD(v118) = 0;
      CRchTxtPtr::IsParaRTL((CRchTxtPtr *)v136);
      CRunPtrBase::AdjustBackward((CRunPtrBase *)&v141);
      if ( v124 )
        Level = CFormatRunPtr::GetLevel((CFormatRunPtr *)&v141, 0);
      else
        Level = v95;
      CRunPtrBase::AdjustForward((CRunPtrBase *)&v141);
      if ( v124 == (unsigned int)CTxtPtr::GetTextLength((CTxtPtr *)&v137) )
      {
        v98 = 0;
      }
      else
      {
        v97 = CFormatRunPtr::GetLevel((CFormatRunPtr *)&v141, (struct CBiDiLevel *)&v118);
        v98 = BYTE1(v118) & 1;
      }
      if ( Level != v97 || v98 )
      {
        v36 = -1;
        if ( !nDenominator && (unsigned int)CRchTxtPtr::Advance((CRchTxtPtr *)v136, -1) )
        {
          v37 = 8218;
          v99 = CTxtPtr::IsAfterEOP((CTxtPtr *)&v137);
          *((_DWORD *)this + 34) &= ~1u;
          *((_DWORD *)this + 34) |= v99 == 0;
        }
      }
      else
      {
        v36 = -1;
      }
    }
  }
  if ( (*(int (__fastcall **)(_QWORD, _QWORD *, struct tagRECT *, _QWORD, __int64 *, __int64 *, int, struct CCharFormat **))(**((_QWORD **)this + 13) + 240LL))(
         *((_QWORD *)this + 13),
         v136,
         &v150,
         *((_DWORD *)this + 34) & 1,
         &v126,
         &v132,
         v37,
         &v128) < 0 )
    goto LABEL_119;
  v118 = 0;
  v124 = bottom - top;
  v38 = 0;
  v39 = *((_QWORD *)this + 6);
  v131 = 0;
  if ( (*(_BYTE *)(v39 + 180) & 1) == 0
    && (*(_DWORD *)(*((_QWORD *)this + 13) + 56LL) & 0x20000) != 0
    && (*((_BYTE *)this + 136) & 1) == 0
    && *((_DWORD *)this + 10) == (unsigned int)CTxtPtr::GetTextLength((CTxtSelection *)((char *)this + 24))
    && (unsigned int)CTxtPtr::IsAfterEOP(v100) )
  {
    PF = CTxtSelection::GetPF(this);
    left = v149.left;
    v103 = *((_BYTE *)PF + 16);
    if ( v103 == 3 )
    {
      left = (v149.left + v149.right) / 2;
    }
    else if ( v103 == 2 )
    {
      left = v149.right;
    }
    LODWORD(v126) = left - v121;
    Line = CLinePtr::GetLine((CLinePtr *)&v132);
    v40 = *((__int16 *)Line + 6) + HIDWORD(v126);
    HIDWORD(v126) = v40;
  }
  else
  {
    v40 = HIDWORD(v126);
    v41 = v126;
  }
  v129 = v40;
  *((_DWORD *)this + 30) = v41;
  EnterCriticalSection(&g_CriticalSection);
  v42 = (unsigned int)*((__int16 *)this + 48);
  v43 = *((_QWORD *)this + 6);
  v147 = v43;
  v128 = 0;
  if ( (int)v42 < 0 )
    v42 = (unsigned int)*(__int16 *)(v43 + 276);
  if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, struct CCharFormat **))(*(_QWORD *)qword_1800A41F0 + 32LL))(
         qword_1800A41F0,
         v42,
         &v128) < 0 )
    v128 = (struct CCharFormat *)g_defaultCF;
  v44 = *((_QWORD *)this + 13);
  v45 = (_QWORD *)(v44 + 16);
  if ( !v44 )
    v45 = 0;
  v148 = v45;
  v46 = v45[1];
  v127 = v46;
  if ( v46
    || (v46 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*v45 + 48LL) + 24LL))(*(_QWORD *)(*v45 + 48LL)),
        (v127 = v46) != 0) )
  {
    v47 = (CDisplay *)*((_QWORD *)this + 13);
    v48 = (HDC)v46;
    v122 = -1;
    ZoomDenominator = CDisplay::GetZoomDenominator(v47);
    v50 = *((_QWORD *)this + 13);
    nDenominator = ZoomDenominator;
    v51 = *(_QWORD *)(v50 + 16);
    v52 = *(unsigned __int16 *)(v51 + 202);
    if ( !*(_WORD *)(v51 + 202) )
    {
      v52 = *(_DWORD *)(v50 + 68);
      if ( v52 <= 0 )
        v52 = 1;
    }
    DeviceCaps = GetDeviceCaps(v48, 90);
    if ( v52 != nDenominator && (!nDenominator || DeviceCaps) )
      DeviceCaps = MulDiv(DeviceCaps, v52, nDenominator);
    Ccs = CFontCache::GetCcs(qword_1800A3EE0, v128, DeviceCaps, 0, 0);
    if ( Ccs )
    {
      v55 = v128;
      v56 = 0;
      nDenominator = 0;
      if ( *((_WORD *)v128 + 5) )
      {
        v56 = CW32System::MulDiv(*((__int16 *)v128 + 5), DeviceCaps, 1440);
        nDenominator = v56;
      }
      if ( (*(_DWORD *)v55 & 0x20000) != 0 )
      {
        v57 = *((__int16 *)Ccs + 55);
      }
      else
      {
        v57 = 0;
        if ( (*(_DWORD *)v55 & 0x10000) != 0 )
          v57 = *((__int16 *)Ccs + 56);
      }
      v58 = *((_QWORD *)this + 6);
      if ( (*(_BYTE *)(v58 + 180) & 1) != 0
        && (*(_BYTE *)(v58 + 188) & 4) == 0
        && (*(_DWORD *)(*(_QWORD *)(v147 + 64) + 56LL) & 0x20000) != 0
        && (*((_BYTE *)Ccs + 123) & 8) != 0 )
      {
        v59 = *((__int16 *)Ccs + 45);
        if ( *((_WORD *)Ccs + 45) )
        {
          v91 = MulDiv(v59, 15, 100);
          v56 = nDenominator;
          LOWORD(v59) = v91;
        }
      }
      else
      {
        LOWORD(v59) = 0;
      }
      v38 = (__int16)v59 + *((__int16 *)Ccs + 46) - v57 - v56;
      v60 = *((_WORD *)Ccs + 5);
      v122 = *((__int16 *)Ccs + 45) + 2 * (__int16)v59;
      if ( v60 )
        *((_WORD *)Ccs + 5) = v60 - 1;
    }
    if ( !v148[1] )
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*v148 + 48LL) + 32LL))(*(_QWORD *)(*v148 + 48LL), v127);
    LeaveCriticalSection(&g_CriticalSection);
    v36 = v122;
  }
  else
  {
    LeaveCriticalSection(&g_CriticalSection);
  }
  v61 = v36 - v38;
  v62 = v38;
  v63 = v36 - v38;
  if ( v132 )
  {
    if ( !*(_DWORD *)(v132 + 8) )
      goto LABEL_96;
    v64 = *(_DWORD *)(v132 + 8);
    v65 = v133;
    if ( v64 > 0 && (int)v133 < v64 && *(_QWORD *)v132 && (int)v133 >= 0 )
      v66 = (__int64 *)(*(_QWORD *)v132 + *(_DWORD *)(v132 + 16) * (int)v133);
    else
      v66 = 0;
    v67 = v135;
  }
  else
  {
    v67 = v135;
    if ( !v135 )
      goto LABEL_96;
    v65 = v133;
    v66 = v135;
  }
  v68 = g_defaultLi;
  v69 = g_defaultLi;
  if ( v66 )
    v69 = v66;
  if ( *((_WORD *)v69 + 7) != 0xFFFF )
  {
    if ( v132 )
    {
      v70 = *(_DWORD *)(v132 + 8);
      if ( v70 > 0 && v65 < v70 && *(_QWORD *)v132 && v65 >= 0 )
        v71 = (__int64 *)(*(_QWORD *)v132 + *(_DWORD *)(v132 + 16) * v65);
      else
        v71 = 0;
    }
    else
    {
      v71 = v67;
    }
    v72 = g_defaultLi;
    if ( v71 )
      v72 = v71;
    v62 = *((__int16 *)v72 + 7);
    if ( v132 )
    {
      v73 = *(_DWORD *)(v132 + 8);
      if ( v73 > 0 && v65 < v73 && *(_QWORD *)v132 && v65 >= 0 )
        v67 = (__int64 *)(*(_QWORD *)v132 + *(_DWORD *)(v132 + 16) * v65);
      else
        v67 = 0;
    }
    if ( v67 )
      v68 = v67;
    v63 = *((__int16 *)v68 + 6) - v62;
  }
  v36 = v122;
LABEL_96:
  v15 = v36 == 0;
  v74 = v63;
  v75 = v62;
  if ( !v15 )
  {
    if ( v61 < v63 )
      v74 = v61;
    if ( v38 < v62 )
      v75 = v38;
  }
  if ( v117 )
  {
    if ( v74 > v124 )
    {
      v75 = 0;
      v118 = 0;
      v76 = 0;
      v74 = v124;
    }
    else if ( v75 + v74 > v124 )
    {
      v75 = v124 - v74;
      v118 = 0;
      v76 = 0;
    }
    else if ( v63 + v75 > v124 )
    {
      v118 = v124 + -v74 - v75;
      v76 = 0;
    }
    else
    {
      v118 = v63 - v74;
      v76 = v62 - v75;
      if ( v63 + v62 > v124 )
        v76 = v124 - (v63 + v75);
    }
  }
  else
  {
    v76 = v131;
  }
  v77 = v149.left;
  v15 = (v125 & 0x80u) == 0;
  *((_DWORD *)this + 32) = *((_DWORD *)this + 30) + v121 - v149.left;
  if ( v15 )
  {
    IsHScrollEnabled = CDisplay::IsHScrollEnabled(*((CDisplay **)this + 13));
    v77 = v149.left;
    if ( !IsHScrollEnabled )
    {
      v90 = *((_DWORD *)this + 30);
      if ( v90 < v149.left )
      {
        *((_DWORD *)this + 30) = v149.left;
      }
      else if ( v90 > v149.right )
      {
        *((_DWORD *)this + 30) = v149.right - 1;
      }
    }
  }
  *((_DWORD *)this + 34) &= ~0x100u;
  if ( *(char *)(v7 + 180) < 0 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v7 + 48) + 96LL))(*(_QWORD *)(v7 + 48), 0);
    v77 = v149.left;
  }
  v78 = v129;
  if ( v129 + v75 + v76 <= top || (v79 = v129 - v74 - v118, v79 >= bottom) )
  {
    v84 = v117;
    if ( v120 || v117 )
      goto LABEL_213;
    goto LABEL_119;
  }
  if ( v79 < top )
  {
    if ( v117 )
      goto LABEL_212;
    v74 = v129 - top;
    if ( v129 < top )
    {
      v75 += v74;
      v78 = top;
      v74 = 0;
    }
  }
  if ( v78 + v75 + v76 <= bottom )
  {
LABEL_110:
    if ( v74 > 0 || v75 > 0 )
    {
      v80 = *((_DWORD *)this + 30);
      if ( v80 >= v77 && v80 <= v149.right )
      {
        v81 = v75 + v74;
        v82 = v78 - v74;
        goto LABEL_114;
      }
      if ( v120 )
        goto LABEL_212;
    }
LABEL_119:
    v82 = -32000;
    v81 = 1;
    *((_DWORD *)this + 30) = -32000;
LABEL_114:
    *((_DWORD *)this + 31) = v82;
    *((_DWORD *)this + 33) = v81;
    if ( *(char *)(v7 + 180) < 0 && (*((_BYTE *)this + 136) & 8) != 0 )
    {
LABEL_115:
      CTxtSelection::CreateCaret(this);
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v7 + 48) + 96LL))(*(_QWORD *)(v7 + 48), 1);
    }
    return 0;
  }
  if ( !v117 )
  {
    v75 = bottom - v78;
    if ( v78 > bottom )
    {
      v74 += v75;
      v78 = bottom;
      v75 = 0;
    }
    goto LABEL_110;
  }
LABEL_212:
  v84 = v117;
LABEL_213:
  if ( !v84 )
    goto LABEL_221;
  if ( !*((_DWORD *)this + 10) )
  {
    v105 = 0;
    goto LABEL_222;
  }
  if ( v78 - v74 - v118 < top )
  {
    v105 = v78 - top - v74 - v118 + v123;
    goto LABEL_222;
  }
  if ( v78 + v75 + v76 > bottom )
  {
    v105 = v78 + v76 + v75 - bottom + v123;
    v106 = CLinePtr::GetLine((CLinePtr *)&v132);
    if ( *((__int16 *)v106 + 6) < v124 )
    {
      v107 = CLinePtr::GetLine((CLinePtr *)&v132);
      v111 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(v108 + 344))(
               v110,
               (unsigned int)(v109 + *((__int16 *)v107 + 6)),
               v105);
      v77 = v149.left;
      v105 = v111;
    }
  }
  else
  {
LABEL_221:
    v105 = v123;
  }
LABEL_222:
  v112 = v121;
  if ( v120 )
  {
    v113 = *((_DWORD *)this + 30);
    if ( v113 >= v77 )
    {
      if ( v113 > v149.right )
        v112 = v113 - v130 - v77 + v121 + 1;
    }
    else
    {
      v112 = v113 + v121 - v77;
      if ( v112 > 0 )
      {
        v115 = v112 - v130 / 3;
        v114 = v115 < 0;
        v116 = v115;
        v112 = 0;
        if ( !v114 )
          v112 = v116;
      }
    }
  }
  if ( v105 == (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 288LL))(*((_QWORD *)this + 13))
    && v112 == *(_DWORD *)(*((_QWORD *)this + 13) + 72LL) )
  {
    return 0;
  }
  if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(**((_QWORD **)this + 13) + 336LL))(
          *((_QWORD *)this + 13),
          (unsigned int)v112,
          v105,
          0,
          0) )
  {
    if ( *(char *)(v7 + 180) >= 0 || (*((_BYTE *)this + 136) & 8) == 0 )
      return 0;
    goto LABEL_115;
  }
  return 1;
}

```

## disassembly

```asm
0x18000c070  push    rbp
0x18000c072  push    rbx
0x18000c073  push    rsi
0x18000c074  push    rdi
0x18000c075  push    r12
0x18000c077  push    r13
0x18000c079  push    r14
0x18000c07b  push    r15
0x18000c07d  lea     rbp, [rsp-58h]
0x18000c082  sub     rsp, 158h
0x18000c089  mov     rax, cs:__security_cookie
0x18000c090  xor     rax, rsp
0x18000c093  mov     [rbp+90h+var_50], rax
0x18000c097  mov     rax, [rcx+68h]
0x18000c09b  mov     esi, r8d
0x18000c09e  mov     edi, edx
0x18000c0a0  mov     rbx, rcx
0x18000c0a3  mov     r9, [rax+30h]
0x18000c0a7  test    r9, r9
0x18000c0aa  jnz     loc_18000C912
0x18000c0b0  mov     r15, [rcx+30h]
0x18000c0b4  mov     eax, [r15+0B4h]
0x18000c0bb  bt      eax, 10h
0x18000c0bf  jb      loc_18000C7F0
0x18000c0c5  test    al, 8
0x18000c0c7  jz      loc_18000CACC
0x18000c0cd  mov     rcx, [r15+30h]
0x18000c0d1  lea     rdx, [rsp+190h+var_120]
0x18000c0d6  xor     r14d, r14d
0x18000c0d9  mov     [rsp+190h+var_120], r14d
0x18000c0de  mov     rax, [rcx]
0x18000c0e1  mov     rax, [rax+0F8h]
0x18000c0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0ed  lea     rcx, [rbx+18h]; this
0x18000c0f1  mov     [rsp+190h+var_140], r14d
0x18000c0f6  mov     [rsp+190h+var_134], r14d
0x18000c0fb  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x18000c100  mov     r8, [rbx+68h]
0x18000c104  lea     rdx, [rbp+90h+var_F0]
0x18000c108  mov     r14d, eax
0x18000c10b  mov     [rsp+190h+nDenominator], eax
0x18000c10f  xor     eax, eax
0x18000c111  mov     [rbp+90h+var_E0], r8
0x18000c115  mov     [rsp+190h+var_118], rax
0x18000c11a  mov     [rbp+90h+var_F0], rax
0x18000c11e  mov     [rbp+90h+var_E8], rax
0x18000c122  mov     [rbp+90h+var_D8], rax
0x18000c126  mov     rcx, [r8]
0x18000c129  mov     rax, [rcx+18h]
0x18000c12d  mov     rcx, r8
0x18000c130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c135  mov     rcx, [rbx+68h]
0x18000c139  xorps   xmm0, xmm0
0x18000c13c  movups  xmmword ptr [rbp+90h+var_60.left], xmm0
0x18000c140  xorps   xmm1, xmm1
0x18000c143  movups  xmmword ptr [rbp+90h+var_70.left], xmm1
0x18000c147  mov     eax, [rcx+48h]
0x18000c14a  mov     [rsp+190h+var_130], eax
0x18000c14e  mov     rax, [rcx]
0x18000c151  mov     rax, [rax+120h]
0x18000c158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c15d  test    byte ptr [r15+0B4h], 80h
0x18000c165  mov     [rsp+190h+var_128], eax
0x18000c169  jz      short loc_18000C1C7
0x18000c16b  mov     edx, [rbx+88h]
0x18000c171  test    dl, 8
0x18000c174  jz      loc_18000CAE4
0x18000c17a  movzx   eax, word ptr [rbx+62h]
0x18000c17e  or      edx, 8
0x18000c181  test    edx, 0A20h
0x18000c187  mov     [rbx+88h], edx
0x18000c18d  mov     r8d, 4
0x18000c193  setz    cl
0x18000c196  bt      ax, r8w
0x18000c19b  setnb   al
0x18000c19e  test    al, cl
0x18000c1a0  jz      short loc_18000C1C7
0x18000c1a2  bts     edx, 9
0x18000c1a6  mov     rcx, rbx; this
0x18000c1a9  mov     [rbx+88h], edx
0x18000c1af  call    ?CheckChangeKeyboardLayout@CTxtSelection@@QEAAXXZ; CTxtSelection::CheckChangeKeyboardLayout(void)
0x18000c1b4  test    r14d, r14d
0x18000c1b7  jz      loc_18000C872
0x18000c1bd  and     dword ptr [rbx+88h], 0FFFFFDFFh
0x18000c1c7  mov     rcx, [r15+30h]
0x18000c1cb  lea     rdx, [rbp+90h+var_60]
0x18000c1cf  mov     rax, [rcx]
0x18000c1d2  mov     rax, [rax+0C0h]
0x18000c1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1de  mov     rcx, [rbx+68h]; this
0x18000c1e2  lea     r8, [rbp+90h+var_60]; struct tagRECT *
0x18000c1e6  lea     rdx, [rbp+90h+var_70]; struct tagRECT *
0x18000c1ea  call    ?GetViewRect@CDisplay@@QEAAXAEAUtagRECT@@PEBU2@@Z; CDisplay::GetViewRect(tagRECT &,tagRECT const *)
0x18000c1ef  mov     r14d, [rbp+90h+var_60.top]
0x18000c1f3  mov     ecx, 2000h
0x18000c1f8  cmp     [rbp+90h+var_70.top], r14d
0x18000c1fc  mov     esi, [rbp+90h+var_60.bottom]
0x18000c1ff  cmovg   r14d, [rbp+90h+var_70.top]
0x18000c204  cmp     [rbp+90h+var_70.bottom], esi
0x18000c207  mov     eax, [rbp+90h+var_70.right]
0x18000c20a  cmovl   esi, [rbp+90h+var_70.bottom]
0x18000c20e  sub     eax, [rbp+90h+var_70.left]
0x18000c211  mov     [rbp+90h+var_FC], eax
0x18000c214  test    edi, edi
0x18000c216  jnz     loc_18000CA6F
0x18000c21c  and     dword ptr [rbx+88h], 0FFFFEFFFh
0x18000c226  cmp     dword ptr [rbx+58h], 0
0x18000c22a  jz      loc_18000C848
0x18000c230  movups  xmm0, xmmword ptr [rbx+18h]
0x18000c234  mov     r8, [rbx+38h]
0x18000c238  lea     r11, [rbx+38h]
0x18000c23c  mov     r10, [rbx+48h]
0x18000c240  lea     rax, ??_7CRchTxtPtr@@6B@; const CRchTxtPtr::`vftable'
0x18000c247  mov     ecx, [r11+8]
0x18000c24b  mov     edi, [r11+0Ch]
0x18000c24f  mov     edx, [rbx+50h]
0x18000c252  mov     r12d, [rbx+54h]
0x18000c256  mov     [rbp+90h+var_D0], rax
0x18000c25a  mov     eax, [rbx+28h]
0x18000c25d  movaps  [rbp+90h+var_C0], xmm0
0x18000c261  movsd   xmm0, qword ptr [rbx+2Ch]
0x18000c266  mov     [rsp+190h+var_124], eax
0x18000c26a  mov     [rbp+90h+var_B0], eax
0x18000c26d  mov     eax, [rbx+34h]
0x18000c270  movsd   [rbp+90h+var_AC], xmm0
0x18000c275  mov     [rbp+90h+var_108], 0
0x18000c27d  mov     [rbp+90h+var_A4], eax
0x18000c280  mov     [rbp+90h+var_A0], r8
0x18000c284  mov     [rbp+90h+var_98], ecx
0x18000c287  mov     [rbp+90h+var_94], edi
0x18000c28a  mov     [rbp+90h+var_90], r10
0x18000c28e  mov     [rbp+90h+var_88], edx
0x18000c291  mov     [rbp+90h+var_84], r12d
0x18000c295  test    r8, r8
0x18000c298  jz      short loc_18000C2F1
0x18000c29a  mov     r9d, [r8+8]
0x18000c29e  test    r9d, r9d
0x18000c2a1  jz      short loc_18000C2F1
0x18000c2a3  jle     loc_18000C9FD
0x18000c2a9  cmp     ecx, r9d
0x18000c2ac  jge     loc_18000C9FD
0x18000c2b2  mov     r11, [r8]
0x18000c2b5  test    r11, r11
0x18000c2b8  jz      loc_18000C9FD
0x18000c2be  test    ecx, ecx
0x18000c2c0  js      loc_18000C9FD
0x18000c2c6  mov     eax, ecx
0x18000c2c8  imul    eax, [r8+10h]
0x18000c2cd  movsxd  r8, eax
0x18000c2d0  add     r8, r11
0x18000c2d3  lea     r11, [rbx+38h]
0x18000c2d7  cmp     [r8], edi
0x18000c2da  jnz     short loc_18000C2F1
0x18000c2dc  lea     eax, [r9-1]
0x18000c2e0  cmp     ecx, eax
0x18000c2e2  jge     short loc_18000C2F1
0x18000c2e4  lea     eax, [rcx+1]
0x18000c2e7  mov     [rbp+90h+var_94], 0
0x18000c2ee  mov     [rbp+90h+var_98], eax
0x18000c2f1  test    r10, r10
0x18000c2f4  jz      short loc_18000C346
0x18000c2f6  mov     ecx, [r10+8]
0x18000c2fa  test    ecx, ecx
0x18000c2fc  jz      short loc_18000C346
0x18000c2fe  jle     loc_18000CA05
0x18000c304  cmp     edx, ecx
0x18000c306  jge     loc_18000CA05
0x18000c30c  mov     r9, [r10]
0x18000c30f  test    r9, r9
0x18000c312  jz      loc_18000CA05
0x18000c318  test    edx, edx
0x18000c31a  js      loc_18000CA05
0x18000c320  mov     eax, edx
0x18000c322  imul    eax, [r10+10h]
0x18000c327  movsxd  r8, eax
0x18000c32a  add     r8, r9
0x18000c32d  cmp     [r8], r12d
0x18000c330  jnz     short loc_18000C346
0x18000c332  lea     eax, [rcx-1]
0x18000c335  cmp     edx, eax
0x18000c337  jge     short loc_18000C346
0x18000c339  lea     eax, [rdx+1]
0x18000c33c  mov     [rbp+90h+var_84], 0
0x18000c343  mov     [rbp+90h+var_88], eax
0x18000c346  mov     rax, [rbx+30h]
0x18000c34a  mov     r12d, 0FFFFFFFFh
0x18000c350  mov     edi, 2018h
0x18000c355  mov     [rsp+190h+var_12C], r12d
0x18000c35a  test    byte ptr [rax+0C0h], 1
0x18000c361  jnz     loc_18000CB58
0x18000c367  mov     rcx, [rbx+68h]
0x18000c36b  lea     rdx, [rbp+90h+var_108]
0x18000c36f  mov     r9d, [rbx+88h]
0x18000c376  lea     r8, [rbp+90h+var_60]
0x18000c37a  mov     [rsp+190h+var_158], rdx
0x18000c37f  and     r9d, 1
0x18000c383  lea     rdx, [rbp+90h+var_F0]
0x18000c387  mov     [rsp+190h+var_160], edi
0x18000c38b  mov     rax, [rcx]
0x18000c38e  mov     [rsp+190h+var_168], rdx
0x18000c393  lea     rdx, [rsp+190h+var_118]
0x18000c398  mov     qword ptr [rsp+190h+var_170], rdx
0x18000c39d  lea     rdx, [rbp+90h+var_D0]
0x18000c3a1  mov     rax, [rax+0F0h]
0x18000c3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3ad  test    eax, eax
0x18000c3af  js      loc_18000C829
0x18000c3b5  xor     edi, edi
0x18000c3b7  mov     eax, esi
0x18000c3b9  sub     eax, r14d
0x18000c3bc  mov     [rsp+190h+var_13C], edi
0x18000c3c0  mov     [rsp+190h+var_124], eax
0x18000c3c4  mov     r13d, edi
0x18000c3c7  mov     rax, [rbx+30h]
0x18000c3cb  mov     [rbp+90h+var_F8], edi
0x18000c3ce  test    byte ptr [rax+0B4h], 1
0x18000c3d5  jz      loc_18000CC76
0x18000c3db  mov     eax, dword ptr [rsp+190h+var_118+4]
0x18000c3df  mov     r9d, dword ptr [rsp+190h+var_118]
0x18000c3e4  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c3eb  mov     [rbp+90h+var_100], eax
0x18000c3ee  mov     [rbx+78h], r9d
0x18000c3f2  call    cs:__imp_EnterCriticalSection
0x18000c3f8  movsx   edx, word ptr [rbx+60h]
0x18000c3fc  mov     rax, [rbx+30h]
0x18000c400  mov     [rbp+90h+var_80], rax
0x18000c404  mov     [rbp+90h+var_108], rdi
0x18000c408  test    edx, edx
0x18000c40a  jns     short loc_18000C413
0x18000c40c  movsx   edx, word ptr [rax+114h]
0x18000c413  mov     rcx, cs:qword_1800A41F0
0x18000c41a  lea     r8, [rbp+90h+var_108]
0x18000c41e  mov     rax, [rcx]
0x18000c421  mov     rax, [rax+20h]
0x18000c425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c42a  test    eax, eax
0x18000c42c  jns     short loc_18000C439
0x18000c42e  lea     rax, ?g_defaultCF@@3VCCharFormat@@A; CCharFormat g_defaultCF
0x18000c435  mov     [rbp+90h+var_108], rax
0x18000c439  mov     rcx, [rbx+68h]
0x18000c43d  test    rcx, rcx
0x18000c440  lea     rdx, [rcx+10h]
0x18000c444  cmovz   rdx, rdi
0x18000c448  mov     [rbp+90h+var_78], rdx
0x18000c44c  mov     rax, [rdx+8]
0x18000c450  mov     [rbp+90h+var_110], rax
0x18000c454  test    rax, rax
0x18000c457  jnz     short loc_18000C479
0x18000c459  mov     rax, [rdx]
0x18000c45c  mov     rcx, [rax+30h]
0x18000c460  mov     rax, [rcx]
0x18000c463  mov     rax, [rax+18h]
0x18000c467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c46c  mov     [rbp+90h+var_110], rax
0x18000c470  test    rax, rax
0x18000c473  jz      loc_18000CA0D
0x18000c479  mov     rcx, [rbx+68h]; this
0x18000c47d  mov     rdi, rax
0x18000c480  mov     [rsp+190h+var_12C], r12d
0x18000c485  call    ?GetZoomDenominator@CDisplay@@QEBAJXZ; CDisplay::GetZoomDenominator(void)
0x18000c48a  mov     rdx, [rbx+68h]
0x18000c48e  mov     [rsp+190h+nDenominator], eax
0x18000c492  mov     rcx, [rdx+10h]
0x18000c496  movzx   r12d, word ptr [rcx+0CAh]
0x18000c49e  test    r12d, r12d
0x18000c4a1  jnz     short loc_18000C4B0
0x18000c4a3  mov     r12d, [rdx+44h]
0x18000c4a7  test    r12d, r12d
0x18000c4aa  jle     loc_18000C83D
0x18000c4b0  mov     edx, 5Ah ; 'Z'; index
0x18000c4b5  mov     rcx, rdi; hdc
0x18000c4b8  call    cs:__imp_GetDeviceCaps
0x18000c4be  mov     edi, eax
0x18000c4c0  mov     eax, [rsp+190h+nDenominator]
0x18000c4c4  cmp     r12d, eax
0x18000c4c7  jz      short loc_18000C4E1
0x18000c4c9  mov     rcx, [rbp+90h+var_110]
0x18000c4cd  mov     [rbp+90h+var_110], rcx
0x18000c4d1  test    eax, eax
0x18000c4d3  jz      loc_18000C939
0x18000c4d9  test    edi, edi
0x18000c4db  jnz     loc_18000C939
0x18000c4e1  mov     rdx, [rbp+90h+var_108]; struct CCharFormat *
0x18000c4e5  xor     r9d, r9d; HDC
0x18000c4e8  mov     rcx, cs:qword_1800A3EE0; this
0x18000c4ef  mov     r8d, edi; int
0x18000c4f2  mov     [rsp+190h+var_170], r13d; int
0x18000c4f7  call    ?GetCcs@CFontCache@@QEAAPEAVCCcs@@QEBVCCharFormat@@JPEAUHDC__@@H@Z; CFontCache::GetCcs(CCharFormat const * const,long,HDC__ *,int)
0x18000c4fc  mov     r12, rax
0x18000c4ff  test    rax, rax
0x18000c502  jz      loc_18000C58C
0x18000c508  mov     r13, [rbp+90h+var_108]
0x18000c50c  xor     edx, edx
0x18000c50e  mov     [rsp+190h+nDenominator], edx
0x18000c512  movsx   eax, word ptr [r13+0Ah]
0x18000c517  test    ax, ax
0x18000c51a  jnz     loc_18000CD08
0x18000c520  mov     ecx, [r13+0]
0x18000c524  bt      ecx, 11h
0x18000c528  jb      loc_18000CD22
  ... truncated ...
```
