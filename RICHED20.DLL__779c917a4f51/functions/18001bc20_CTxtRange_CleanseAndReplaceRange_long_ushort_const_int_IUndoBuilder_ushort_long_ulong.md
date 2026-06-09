# CTxtRange::CleanseAndReplaceRange(long,ushort const *,int,IUndoBuilder *,ushort *,long *,ulong)

- ea: `0x18001bc20`
- end: `0x18001c920`
- name: `?CleanseAndReplaceRange@CTxtRange@@QEAAJJPEBGHPEAVIUndoBuilder@@PEAGPEAJK@Z`
- size: `3328`
- prototype: `__int64 __usercall@<rax>(CTxtRange *__hidden this@<rcx>, int@<edx>, const unsigned __int16 *@<r8>, int@<r9d>, struct IUndoBuilder *, unsigned __int16 *, int *, unsigned int)`
- caller_count: `8`
- callee_count: `26`
- tags: ``

## callers

- `0x1800049f0`
- `0x18001cc3c`
- `0x1800323d8`
- `0x180043514`
- `0x18006cacc`
- `0x180072728`
- `0x180073604`
- `0x1800893e0`

## callees

- `0x180004fe0`
- `0x180005480`
- `0x1800064d0`
- `0x180006610`
- `0x18001ab58`
- `0x18001bc20`
- `0x18001c928`
- `0x18001c968`
- `0x18001c988`
- `0x18001cb00`
- `0x18001cbf0`
- `0x18001d040`
- `0x18001d0b8`
- `0x18001d8b0`
- `0x18001db20`
- `0x1800202a0`
- `0x1800227dc`
- `0x180022a54`
- `0x180023010`
- `0x18002c900`
- `0x180032db0`
- `0x18003e0c4`
- `0x180044044`
- `0x180048ed8`
- `0x180091140`
- `0x180092010`

## pseudocode

```c
__int64 __fastcall CTxtRange::CleanseAndReplaceRange(
        CTxtRange *this,
        int a2,
        unsigned __int16 *a3,
        int a4,
        struct IUndoBuilder *a5,
        unsigned __int16 *a6,
        int *a7,
        char a8)
{
  CTxtRange *v8; // r15
  __int64 v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 *v14; // rbx
  unsigned __int16 *v15; // rax
  int v16; // ecx
  int v17; // esi
  int v18; // eax
  __int64 v19; // rdx
  unsigned int v20; // eax
  int v21; // r14d
  int v22; // r14d
  unsigned int v23; // eax
  int v24; // ebx
  CRchTxtPtr *v25; // rcx
  unsigned int v26; // r9d
  int v27; // r11d
  unsigned int v28; // eax
  int v29; // r8d
  int v30; // eax
  const struct CCharFormat *CharFormat; // rax
  __int64 v32; // xmm0_8
  unsigned int CharSetMask; // eax
  unsigned int v34; // ecx
  BOOL v35; // edx
  bool v36; // zf
  unsigned __int16 *Buf; // rax
  int v39; // edx
  __int64 *PF; // rax
  int v41; // edx
  __int64 v42; // rdx
  __int16 v43; // dx
  unsigned int v44; // r11d
  int v45; // edx
  int v46; // r10d
  unsigned int v47; // ecx
  unsigned int v48; // esi
  unsigned __int16 v49; // ax
  unsigned __int16 *v50; // rcx
  unsigned __int16 *v51; // rax
  int v52; // ebx
  unsigned int CharFlags; // eax
  unsigned int v54; // ebx
  int v55; // r15d
  CTxtRange *v56; // r14
  __int64 v57; // rax
  unsigned int v58; // eax
  int v59; // r14d
  const unsigned __int16 *v60; // r15
  unsigned int v61; // ecx
  int v62; // eax
  int v63; // r14d
  __int128 v64; // xmm1
  int v65; // eax
  int v66; // edx
  unsigned __int16 Char; // ax
  int i; // r14d
  unsigned int CharFlags125x; // ebx
  const struct CCharFormat *v70; // rax
  unsigned int v71; // eax
  unsigned __int16 *v72; // rcx
  int v73; // eax
  unsigned __int16 *v74; // rax
  struct IUndoBuilder *v75; // r14
  int v76; // eax
  int v77; // r8d
  unsigned int v78; // ebx
  unsigned int v79; // [rsp+48h] [rbp-B8h]
  unsigned __int8 v80; // [rsp+50h] [rbp-B0h]
  int v81; // [rsp+54h] [rbp-ACh]
  bool v82; // [rsp+58h] [rbp-A8h]
  int v83; // [rsp+5Ch] [rbp-A4h]
  int v84; // [rsp+60h] [rbp-A0h]
  unsigned int v85; // [rsp+64h] [rbp-9Ch]
  int v86; // [rsp+68h] [rbp-98h]
  unsigned int v87; // [rsp+6Ch] [rbp-94h]
  unsigned int v88; // [rsp+70h] [rbp-90h]
  int v89; // [rsp+70h] [rbp-90h]
  int v90; // [rsp+74h] [rbp-8Ch] BYREF
  int v91; // [rsp+78h] [rbp-88h]
  int v92; // [rsp+7Ch] [rbp-84h]
  CTxtRange *v93; // [rsp+80h] [rbp-80h]
  int v94; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v95; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v96; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v97; // [rsp+A0h] [rbp-60h]
  struct IUndoBuilder *v98; // [rsp+A8h] [rbp-58h]
  __int128 v99; // [rsp+B0h] [rbp-50h] BYREF
  int v100; // [rsp+C0h] [rbp-40h]
  unsigned int v101; // [rsp+C4h] [rbp-3Ch]
  BOOL v102; // [rsp+C8h] [rbp-38h]
  __int64 *v103; // [rsp+D0h] [rbp-30h] BYREF
  CDisplay *v104; // [rsp+D8h] [rbp-28h]
  __int128 v105; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v106; // [rsp+F0h] [rbp-10h]
  __int64 v107; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v108; // [rsp+108h] [rbp+8h]
  __int64 v109; // [rsp+110h] [rbp+10h]
  int *v110; // [rsp+118h] [rbp+18h]
  _OWORD v111[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v112; // [rsp+140h] [rbp+40h]
  _BYTE v113[256]; // [rsp+150h] [rbp+50h] BYREF
  void *lpMem; // [rsp+250h] [rbp+150h]
  int v115; // [rsp+258h] [rbp+158h]

  v8 = this;
  v98 = a5;
  v93 = this;
  v11 = *((_QWORD *)this + 6);
  v110 = a7;
  v108 = a6;
  v97 = a6;
  v12 = (unsigned int)*(__int16 *)(v11 + 276);
  v92 = a4;
  v109 = v11;
  v13 = *(_QWORD *)qword_1800A41F0;
  v95 = 0;
  v14 = g_defaultCF;
  if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, unsigned __int16 **))(v13 + 32))(
         qword_1800A41F0,
         v12,
         &v95) >= 0 )
  {
    v15 = v95;
  }
  else
  {
    v15 = (unsigned __int16 *)g_defaultCF;
    v95 = (unsigned __int16 *)g_defaultCF;
  }
  v16 = *((_DWORD *)v8 + 22);
  v17 = *((_DWORD *)v8 + 10);
  v80 = *((_BYTE *)v15 + 4);
  v90 = 0;
  if ( v16 > 0 )
    v17 -= v16;
  v91 = v17;
  v18 = CTxtRange::GetiFormat(v8);
  v103 = 0;
  v19 = (unsigned int)v18;
  if ( v18 < 0 )
    v19 = (unsigned int)*(__int16 *)(*((_QWORD *)v8 + 6) + 276LL);
  if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, __int64 **))(*(_QWORD *)qword_1800A41F0 + 32LL))(
         qword_1800A41F0,
         v19,
         &v103) >= 0 )
    v14 = v103;
  else
    v103 = g_defaultCF;
  v20 = CW32System::GetFontSig(*((unsigned __int8 *)v14 + 4)) << 8;
  if ( (v20 & 0x400000) != 0 )
  {
    v22 = v20;
  }
  else
  {
    v21 = 3145728;
    if ( (v20 | 0x200000) >= 0x20000000 )
      v21 = 0x200000;
    v22 = v20 | v21;
    if ( (v22 & 0x1E000000) != 0 && ((v23 = CW32System::_syslcid & 0x3FF, v23 == 18) || v23 == 4 || v23 == 17) )
    {
      v22 |= 0x800000u;
    }
    else if ( (v22 & 0x19300) != 0 )
    {
      v22 |= 0x80000u;
    }
  }
  LODWORD(v103) = *(_DWORD *)(v11 + 180);
  v84 = 0;
  v104 = *(CDisplay **)(v11 + 64);
  CDisplay::Freeze(v104);
  v24 = (*(_DWORD *)(*(_QWORD *)(v11 + 64) + 56LL) >> 17) & 1;
  v94 = v24;
  v102 = v80 == 128 || v80 == 129 || v80 == 130 || v80 == 134 || v80 == 136;
  LODWORD(v99) = 0;
  v82 = CRchTxtPtr::fUseUIFont((CTxtRange *)((char *)v8 + 8));
  v28 = *(_DWORD *)(v11 + 180);
  v29 = v26;
  lpMem = v113;
  LOBYTE(v29) = v22 == 0x400000;
  v115 = 256;
  BYTE4(v111[0]) = 0;
  v36 = (*(_BYTE *)(v11 + 180) & 1) == 0;
  v81 = v29;
  v88 = v28;
  v95 = a3;
  if ( !v36 || (v36 = *((_DWORD *)v8 + 22) == 0, v100 = 1, v36) )
    v100 = v26;
  if ( (*(_WORD *)(v11 + 184) & 0x4000) != 0 )
  {
    v84 = 503316480;
    v30 = CTxtRange::GetiFormat(v8);
    CharFormat = CTxtArray::GetCharFormat((CTxtArray *)(v11 + 248), v30);
    v29 = v81;
    v25 = (CTxtRange *)((char *)v8 + 8);
    v27 = v99;
    v26 = 0;
    v111[0] = *(_OWORD *)CharFormat;
    v111[1] = *((_OWORD *)CharFormat + 1);
    v32 = *((_QWORD *)CharFormat + 4);
    v28 = v88;
    v112 = v32;
  }
  if ( v82 )
  {
    CharSetMask = CTxtRange::GetCharSetMask(v8, 1);
    v27 = v99;
    v34 = CharSetMask;
    v26 = 0;
    v36 = (CharSetMask & 0x300000) == 3145728;
    v28 = v88;
    v35 = v36;
    v36 = v34 == 0x400000;
    v101 = v35;
    v25 = (CTxtRange *)((char *)v8 + 8);
    if ( v36 )
    {
      v29 = 1;
      v81 = 1;
    }
    else
    {
      v29 = 0;
      v81 = 0;
      v101 = v35;
    }
  }
  else
  {
    v101 = v26;
  }
  if ( !a3 )
  {
    a2 = v26;
    goto LABEL_71;
  }
  if ( v24 )
  {
    v36 = a2 == 0;
    if ( a2 < 0 )
    {
      a2 = CW32System::wcslen(a3);
      v25 = (CTxtRange *)((char *)v8 + 8);
      v36 = a2 == 0;
    }
    Buf = v97;
    if ( !v36 && !v97 )
    {
      Buf = CTempWcharBuf::GetBuf((CTempWcharBuf *)v113, a2);
      v97 = Buf;
      if ( !Buf )
      {
        if ( lpMem != v113 )
          CW32System::FreePv(lpMem);
        CDisplay::Thaw(v104);
        return 0;
      }
      v25 = (CTxtRange *)((char *)v8 + 8);
    }
    v39 = *((_DWORD *)v8 + 22);
    v95 = Buf;
    if ( v39 <= 0 )
    {
      PF = (__int64 *)CRchTxtPtr::GetPF(v25);
LABEL_68:
      v44 = *((unsigned __int16 *)PF + 1);
      v29 = v81;
      v28 = v88;
      v27 = (v44 >> 14) & 1;
      LODWORD(v99) = v27;
      v26 = 0;
      goto LABEL_71;
    }
    v99 = *(_OWORD *)((char *)v8 + 72);
    CRunPtrBase::AdvanceCp((CRunPtrBase *)&v99, -v39);
    if ( (_QWORD)v99 && *(_DWORD *)(v99 + 8) )
    {
      v41 = *(_DWORD *)(v99 + 8);
      if ( v41 > 0 && SDWORD2(v99) < v41 && *(_QWORD *)v99 && (SDWORD2(v99) & 0x80000000) == 0 )
        v42 = *(_QWORD *)v99 + *(_DWORD *)(v99 + 16) * DWORD2(v99);
      else
        v42 = 0;
      v43 = *(_WORD *)(v42 + 4);
      *(_QWORD *)&v99 = 0;
      if ( v43 >= 0 )
        goto LABEL_65;
    }
    else
    {
      *(_QWORD *)&v99 = 0;
    }
    v43 = *(_WORD *)(v11 + 278);
LABEL_65:
    if ( (*(int (__fastcall **)(struct IFormatCache *, _QWORD, __int128 *))(*(_QWORD *)qword_1800A41E8 + 32LL))(
           qword_1800A41E8,
           (unsigned int)v43,
           &v99) >= 0 )
    {
      PF = (__int64 *)v99;
    }
    else
    {
      PF = g_defaultPF;
      *(_QWORD *)&v99 = g_defaultPF;
    }
    goto LABEL_68;
  }
  if ( a2 < 0 )
    a2 = 0x3FFFFFFF;
LABEL_71:
  v45 = 0;
  v86 = v26;
  v85 = v26;
  v46 = v26;
  v87 = v26;
  v89 = (v28 >> 19) & 1;
  v83 = 0;
  if ( !a2 )
    goto LABEL_193;
  do
  {
    v47 = *a3;
    if ( !(_WORD)v47 && (!v24 || !v108) )
      break;
    v48 = *a3;
    if ( v47 - 9 > 4 )
    {
      if ( (v47 | 1) == 0x2029 )
      {
        if ( !v24 )
          break;
        v48 = 11;
        if ( v47 == 8233 )
          v48 = 13;
      }
    }
    else
    {
      if ( !v24 && v47 >= 0xA )
        break;
      if ( v47 != 13 || ((unsigned int)v103 & 0x80000) != 0 )
      {
        if ( v89 || v47 != 10 )
        {
          if ( v47 == 9 && v27 )
            v48 = 32;
        }
        else
        {
          v48 = 13;
        }
      }
      else
      {
        if ( a2 > 1 )
        {
          v49 = a3[1];
          if ( v49 == 13 && a2 > 2 )
          {
            if ( a3[2] == 10 )
            {
              if ( v89 )
              {
                v50 = v97;
                v48 = 10;
                *(_DWORD *)v97 = 851981;
                v45 += 2;
                v97 = v50 + 2;
                v83 = v45;
              }
              else
              {
                v48 = 32;
                if ( (*(_WORD *)(v11 + 186) & 0x4000) != 0 )
                  v48 = 13;
              }
              a3 += 2;
              a2 -= 2;
            }
          }
          else if ( v49 == 10 )
          {
            if ( v89 && !v27 )
            {
              v51 = v97;
              v48 = 10;
              *v97 = 13;
              ++v45;
              v97 = v51 + 1;
              v83 = v45;
            }
            ++a3;
            --a2;
          }
        }
        if ( v27 && v48 == 13 )
          v48 = 32;
      }
    }
    v52 = 0x400000;
    if ( !v29 )
    {
      CharFlags = GetCharFlags(v48, v80);
      v45 = v83;
      v52 = CharFlags;
      v29 = v81;
      v26 = v87;
      v46 = v86;
    }
    v26 |= v52;
    v54 = v52 & 0xFFFFFF00;
    v87 = v26;
    if ( (*(_DWORD *)(v11 + 180) & 0x200000) == 0 || v29 )
      goto LABEL_186;
    v55 = 0;
    if ( v100 )
    {
      v56 = v93;
      v57 = *(_QWORD *)v93;
      v100 = 0;
      (*(void (__fastcall **)(CTxtRange *, _QWORD, _QWORD, struct IUndoBuilder *, int, _QWORD, int))(v57 + 560))(
        v93,
        0,
        0,
        v98,
        1,
        0,
        2);
      CTxtRange::Set_iCF(v56, -1);
      v58 = CTxtRange::GetCharSetMask(v56, 1);
      v45 = v83;
      v22 = v58;
      v29 = v81;
      v26 = v87;
      v46 = v86;
    }
    if ( (*(_WORD *)(v11 + 184) & 0x4000) != 0 )
    {
      if ( v48 > 0x7F )
        goto LABEL_173;
      if ( v82 )
      {
LABEL_165:
        if ( v84 != 3145728 )
        {
          v85 += CTxtRange::CheckLimitReplaceRange(v93, v45, v95, v92, v98, 0, &v90, v91, 0, v79);
          v70 = CTxtArray::GetCharFormat((CTxtArray *)(v11 + 248), -1);
          v105 = *(_OWORD *)v70;
          v106 = *((_OWORD *)v70 + 1);
          v107 = *((_QWORD *)v70 + 4);
          CTxtRange::SetCharFormat(v93, (const struct CCharFormat *)&v105, 0, v98, 0xA8000000, 0x9000u);
          v45 = v83;
          v55 = 1;
          v29 = v81;
          v26 = v87;
          v46 = v86;
        }
        v84 = 3145728;
        goto LABEL_176;
      }
      if ( (*(_BYTE *)(v11 + 188) & 2) != 0 && (*((_BYTE *)&rgbCharClass + (unsigned __int8)v48) & 3) != 0 )
      {
        if ( v84 != 1 )
        {
          v85 += CTxtRange::CheckLimitReplaceRange(v93, v45, v95, v92, v98, v54, &v90, v91, 0, v79);
          v55 = 1;
          v45 = v83;
          v29 = v81;
          v26 = v87;
          v46 = v86;
        }
        v84 = 1;
      }
      else
      {
LABEL_173:
        if ( v84 != 503316480 )
        {
          v85 += CTxtRange::CheckLimitReplaceRange(v93, v45, v95, v92, v98, 0, &v90, v91, 0, v79);
          CTxtRange::SetCharFormat(v93, (const struct CCharFormat *)v111, 0, v98, 0xA8000000, 0x9000u);
          v45 = v83;
          v55 = 1;
          v29 = v81;
          v26 = v87;
          v46 = v86;
        }
        v84 = 503316480;
      }
LABEL_176:
      v36 = v55 == 0;
      v8 = v93;
      if ( !v36 )
        goto LABEL_177;
      goto LABEL_186;
    }
    if ( v82 )
    {
      if ( v54 != 512 && v48 - 592 > 0xAF && v48 - 65104 > 0x1F || CW32System::_ACP != 936 && CW32System::_ACP != 950 )
        goto LABEL_123;
      v96 = v48;
      if ( (unsigned int)CW32System::VerifyFEString(936, &v96, 1, 1) == 936
        || (unsigned int)CW32System::VerifyFEString(950, &v96, 1, 1) == 950 )
      {
        v45 = v83;
        v54 = 0x4000000;
        v29 = v81;
        v26 = v87;
        v46 = v86;
      }
      else
      {
        v45 = v83;
        v29 = v81;
        v26 = v87;
        v46 = v86;
LABEL_123:
        if ( v54 == 256 && v102 )
        {
          if ( v84 != 256 )
          {
            v55 = 1;
            v85 += CTxtRange::CheckLimitReplaceRange(v93, v45, v95, v92, v98, 0x100u, &v90, v91, 0, v79);
            v45 = v83;
            v29 = v81;
            v26 = v87;
            v46 = v86;
          }
          v84 = 256;
          goto LABEL_176;
        }
      }
      if ( v101 && ((v54 & 0x300000) != 0 || v48 - 8216 <= 5) )
        goto LABEL_165;
    }
    if ( v54 && (v22 & v54) == 0 || v84 )
    {
      v84 = 0;
      if ( (v54 & 0x14000000) != 0 )
      {
        v59 = a2 - 1;
        v60 = a3 + 1;
        if ( a2 - 1 <= 10 )
        {
          if ( a2 != 1 )
            goto LABEL_139;
        }
        else
        {
          v59 = 10;
          do
          {
LABEL_139:
            if ( !*v60 )
              break;
            v61 = *v60++;
            v54 |= GetCharFlags(v61, v80);
            --v59;
          }
          while ( v59 );
          v11 = v109;
        }
        v8 = v93;
        v62 = CTxtRange::CalcTextLenNotInRange(v93);
        if ( a2 < 6 && v62 )
        {
          v63 = 6;
          v64 = *(_OWORD *)((char *)v8 + 40);
          v105 = *(_OWORD *)((char *)v8 + 24);
          if ( v62 < 6 )
            v63 = v62;
          v65 = *((_DWORD *)v8 + 22);
          v106 = v64;
          if ( !v65 )
          {
            v66 = v63 / -2;
            goto LABEL_150;
          }
          if ( v65 < 0 )
          {
            v66 = -v63;
LABEL_150:
            CTxtPtr::AdvanceCp((CTxtPtr *)&v105, v66);
          }
          do
          {
            Char = CTxtPtr::GetChar((CTxtPtr *)&v105);
            v54 |= GetCharFlags(Char, v80);
            CTxtPtr::AdvanceCp((CTxtPtr *)&v105, 1);
            --v63;
          }
          while ( v63 );
          v8 = v93;
        }
        v45 = v83;
        v54 &= 0x1E000000u;
      }
      else
      {
        if ( (v54 & 0x300) != 0 )
        {
          i = v22 & 0x19300;
          if ( i )
          {
            CharFlags125x = CW32System::GetCharFlags125x(v48);
            if ( (CharFlags125x & i) == 0 )
            {
              for ( i = 256; i < 0x20000; i *= 2 )
              {
                if ( (i & CharFlags125x & 0x19300) != 0 )
                  break;
              }
            }
            v45 = v83;
            v54 = i & CharFlags125x & 0x19300;
          }
        }
        v8 = v93;
      }
      v85 += CTxtRange::CheckLimitReplaceRange(v8, v45, v95, v92, v98, v54, &v90, v91, 2, v79);
      v29 = v81;
      v26 = v87;
      v46 = v86;
LABEL_177:
      if ( (v54 & 0x400000) != 0 )
      {
        v22 = 0x400000;
      }
      else
      {
        v71 = CTxtRange::GetCharSetMask(v8, 0);
        v29 = v81;
        v22 = v71;
        v26 = v87;
        v46 = v86;
      }
      v72 = a3;
      if ( v90 )
        v46 = v90;
      v73 = v94;
      v86 = v46;
      if ( v94 )
        v72 = v97;
      v45 = 0;
      v95 = v72;
      goto LABEL_187;
    }
    v8 = v93;
LABEL_186:
    v73 = v94;
LABEL_187:
    if ( v73 )
    {
      if ( (v54 & 0x400000) != 0 )
        LOWORD(v48) = (unsigned __int8)v48;
      v74 = v97;
      *v97 = v48;
      v97 = v74 + 1;
    }
    v24 = v94;
    ++v45;
    v27 = v99;
    ++a3;
    v83 = v45;
    --a2;
  }
  while ( a2 );
  v17 = v91;
LABEL_193:
  v75 = v98;
  CTxtEdit::OrCharFlags((CTxtEdit *)v11, v26, v98);
  v76 = CTxtRange::CheckLimitReplaceRange(v8, v83, v95, v92, v75, 0, &v90, v17, 0, v79);
  v77 = v86;
  v78 = v76 + v85;
  if ( v90 )
    v77 = v90;
  if ( v110 )
    *v110 = v77;
  if ( (*(_DWORD *)(v11 + 192) & 0x61086013) != 0 )
  {
    if ( (*(_DWORD *)(v11 + 180) & 0x10000) == 0 && (a8 & 2) == 0 )
      CRchTxtPtr::ItemizeReplaceRange((CTxtRange *)((char *)v8 + 8), v78, v77, v75, a8 & 1);
    else
      *(_WORD *)(v11 + 188) |= 8u;
  }
  if ( lpMem != v113 )
    CW32System::FreePv(lpMem);
  CDisplay::Thaw(v104);
  return v78;
}

```

## disassembly

```asm
0x18001bc20  push    rbp
0x18001bc22  push    rbx
0x18001bc23  push    rsi
0x18001bc24  push    rdi
0x18001bc25  push    r12
0x18001bc27  push    r13
0x18001bc29  push    r14
0x18001bc2b  push    r15
0x18001bc2d  lea     rbp, [rsp-178h]
0x18001bc35  sub     rsp, 278h
0x18001bc3c  mov     rax, cs:__security_cookie
0x18001bc43  xor     rax, rsp
0x18001bc46  mov     [rbp+1B0h+var_50], rax
0x18001bc4d  mov     rax, [rbp+1B0h+arg_20]
0x18001bc54  mov     r15, rcx
0x18001bc57  mov     [rbp+1B0h+var_208], rax
0x18001bc5b  mov     r12, r8
0x18001bc5e  mov     rax, [rbp+1B0h+arg_30]
0x18001bc65  lea     r8, [rbp+1B0h+var_220]
0x18001bc69  mov     [rbp+1B0h+var_230], rcx
0x18001bc6d  mov     r13d, edx
0x18001bc70  mov     rcx, [rbp+1B0h+arg_28]
0x18001bc77  xor     r14d, r14d
0x18001bc7a  mov     rdi, [r15+30h]
0x18001bc7e  mov     [rbp+1B0h+var_198], rax
0x18001bc82  mov     [rbp+1B0h+var_1A8], rcx
0x18001bc86  mov     [rbp+1B0h+var_210], rcx
0x18001bc8a  mov     rcx, cs:qword_1800A41F0
0x18001bc91  movsx   edx, word ptr [rdi+114h]
0x18001bc98  mov     [rsp+2B0h+var_234], r9d
0x18001bc9d  mov     [rbp+1B0h+var_1A0], rdi
0x18001bca1  mov     rax, [rcx]
0x18001bca4  mov     [rbp+1B0h+var_220], r14
0x18001bca8  mov     rax, [rax+20h]
0x18001bcac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcb1  lea     rbx, ?g_defaultCF@@3VCCharFormat@@A; CCharFormat g_defaultCF
0x18001bcb8  test    eax, eax
0x18001bcba  jns     short loc_18001BCC5
0x18001bcbc  mov     rax, rbx
0x18001bcbf  mov     [rbp+1B0h+var_220], rbx
0x18001bcc3  jmp     short loc_18001BCC9
0x18001bcc5  mov     rax, [rbp+1B0h+var_220]
0x18001bcc9  movzx   eax, byte ptr [rax+4]
0x18001bccd  mov     ecx, [r15+58h]
0x18001bcd1  mov     esi, [r15+28h]
0x18001bcd5  mov     [rsp+2B0h+var_260], al
0x18001bcd9  mov     eax, esi
0x18001bcdb  sub     eax, ecx
0x18001bcdd  mov     [rsp+2B0h+var_23C], r14d
0x18001bce2  test    ecx, ecx
0x18001bce4  mov     rcx, r15; this
0x18001bce7  cmovg   esi, eax
0x18001bcea  mov     [rsp+2B0h+var_238], esi
0x18001bcee  call    ?GetiFormat@CTxtRange@@QEBAJXZ; CTxtRange::GetiFormat(void)
0x18001bcf3  mov     [rbp+1B0h+var_1E0], r14
0x18001bcf7  mov     edx, eax
0x18001bcf9  test    eax, eax
0x18001bcfb  jns     short loc_18001BD08
0x18001bcfd  mov     rax, [r15+30h]
0x18001bd01  movsx   edx, word ptr [rax+114h]
0x18001bd08  mov     rcx, cs:qword_1800A41F0
0x18001bd0f  lea     r8, [rbp+1B0h+var_1E0]
0x18001bd13  mov     rax, [rcx]
0x18001bd16  mov     rax, [rax+20h]
0x18001bd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd1f  test    eax, eax
0x18001bd21  jns     short loc_18001BD29
0x18001bd23  mov     [rbp+1B0h+var_1E0], rbx
0x18001bd27  jmp     short loc_18001BD2D
0x18001bd29  mov     rbx, [rbp+1B0h+var_1E0]
0x18001bd2d  movzx   ecx, byte ptr [rbx+4]; unsigned __int16
0x18001bd31  call    ?GetFontSig@CW32System@@SAKG@Z; CW32System::GetFontSig(ushort)
0x18001bd36  shl     eax, 8
0x18001bd39  mov     edx, 200000h
0x18001bd3e  bt      eax, 16h
0x18001bd42  jb      short loc_18001BD96
0x18001bd44  mov     ecx, eax
0x18001bd46  mov     r14d, 300000h
0x18001bd4c  or      ecx, edx
0x18001bd4e  cmp     ecx, 20000000h
0x18001bd54  cmovnb  r14d, edx
0x18001bd58  or      r14d, eax
0x18001bd5b  test    r14d, 1E000000h
0x18001bd62  jz      short loc_18001BD86
0x18001bd64  movzx   eax, word ptr cs:?_syslcid@CW32System@@0KA; ulong CW32System::_syslcid
0x18001bd6b  and     eax, 3FFh
0x18001bd70  cmp     eax, 12h
0x18001bd73  jz      short loc_18001BD7F
0x18001bd75  cmp     eax, 4
0x18001bd78  jz      short loc_18001BD7F
0x18001bd7a  cmp     eax, 11h
0x18001bd7d  jnz     short loc_18001BD86
0x18001bd7f  bts     r14d, 17h
0x18001bd84  jmp     short loc_18001BD99
0x18001bd86  test    r14d, 19300h
0x18001bd8d  jz      short loc_18001BD99
0x18001bd8f  bts     r14d, 13h
0x18001bd94  jmp     short loc_18001BD99
0x18001bd96  mov     r14d, eax
0x18001bd99  mov     eax, [rdi+0B4h]
0x18001bd9f  mov     dword ptr [rbp+1B0h+var_1E0], eax
0x18001bda2  mov     rax, [rdi+40h]
0x18001bda6  mov     rcx, rax; this
0x18001bda9  mov     [rsp+2B0h+var_250], 0
0x18001bdb1  mov     [rbp+1B0h+var_1D8], rax
0x18001bdb5  call    ?Freeze@CDisplay@@QEAAXXZ; CDisplay::Freeze(void)
0x18001bdba  mov     rax, [rdi+40h]
0x18001bdbe  mov     ebx, [rax+38h]
0x18001bdc1  movzx   eax, [rsp+2B0h+var_260]
0x18001bdc6  shr     ebx, 11h
0x18001bdc9  and     ebx, 1
0x18001bdcc  mov     [rbp+1B0h+var_228], ebx
0x18001bdcf  sub     eax, 80h
0x18001bdd4  jz      short loc_18001BDF3
0x18001bdd6  sub     eax, 1
0x18001bdd9  jz      short loc_18001BDF3
0x18001bddb  sub     eax, 1
0x18001bdde  jz      short loc_18001BDF3
0x18001bde0  sub     eax, 4
0x18001bde3  jz      short loc_18001BDF3
0x18001bde5  cmp     eax, 2
0x18001bde8  jz      short loc_18001BDF3
0x18001bdea  xor     r9d, r9d
0x18001bded  mov     [rbp+1B0h+var_1E8], r9d
0x18001bdf1  jmp     short loc_18001BDFD
0x18001bdf3  mov     [rbp+1B0h+var_1E8], 1
0x18001bdfa  xor     r9d, r9d
0x18001bdfd  lea     rcx, [r15+8]; this
0x18001be01  mov     dword ptr [rbp+1B0h+var_200], r9d
0x18001be05  mov     r11d, r9d
0x18001be08  call    ?fUseUIFont@CRchTxtPtr@@IEBA_NXZ; CRchTxtPtr::fUseUIFont(void)
0x18001be0d  cmp     r14d, 400000h
0x18001be14  mov     [rsp+2B0h+var_258], al
0x18001be18  mov     eax, [rdi+0B4h]
0x18001be1e  lea     rdx, [rbp+1B0h+var_160]
0x18001be22  mov     r8d, r9d
0x18001be25  mov     [rbp+1B0h+lpMem], rdx
0x18001be2c  setz    r8b
0x18001be30  mov     [rbp+1B0h+var_58], 100h
0x18001be3a  mov     [rbp+1B0h+var_18C], 0
0x18001be3e  test    byte ptr [rdi+0B4h], 1
0x18001be45  mov     [rsp+2B0h+var_25C], r8d
0x18001be4a  mov     [rsp+2B0h+var_240], eax
0x18001be4e  mov     [rbp+1B0h+var_220], r12
0x18001be52  jnz     short loc_18001BE62
0x18001be54  cmp     dword ptr [r15+58h], 0
0x18001be59  mov     [rbp+1B0h+var_1F0], 1
0x18001be60  jnz     short loc_18001BE66
0x18001be62  mov     [rbp+1B0h+var_1F0], r9d
0x18001be66  mov     edx, 4000h
0x18001be6b  test    [rdi+0B8h], dx
0x18001be72  jz      short loc_18001BEBF
0x18001be74  mov     rcx, r15; this
0x18001be77  mov     [rsp+2B0h+var_250], 1E000000h
0x18001be7f  call    ?GetiFormat@CTxtRange@@QEBAJXZ; CTxtRange::GetiFormat(void)
0x18001be84  lea     rcx, [rdi+0F8h]; this
0x18001be8b  mov     edx, eax; int
0x18001be8d  call    ?GetCharFormat@CTxtArray@@QEAAPEBVCCharFormat@@J@Z; CTxtArray::GetCharFormat(long)
0x18001be92  mov     r8d, [rsp+2B0h+var_25C]
0x18001be97  lea     rcx, [r15+8]
0x18001be9b  mov     r11d, dword ptr [rbp+1B0h+var_200]
0x18001be9f  xor     r9d, r9d
0x18001bea2  movups  xmm0, xmmword ptr [rax]
0x18001bea5  movups  xmmword ptr [rbp+20h], xmm0
0x18001bea9  movups  xmm1, xmmword ptr [rax+10h]
0x18001bead  movups  [rbp+1B0h+var_180], xmm1
0x18001beb1  movsd   xmm0, qword ptr [rax+20h]
0x18001beb6  mov     eax, [rsp+2B0h+var_240]
0x18001beba  movsd   [rbp+1B0h+var_170], xmm0
0x18001bebf  cmp     [rsp+2B0h+var_258], 0
0x18001bec4  jz      short loc_18001BF19
0x18001bec6  mov     edx, 1; int
0x18001becb  mov     rcx, r15; this
0x18001bece  call    ?GetCharSetMask@CTxtRange@@QEAAKH@Z; CTxtRange::GetCharSetMask(int)
0x18001bed3  mov     r11d, dword ptr [rbp+1B0h+var_200]
0x18001bed7  mov     ecx, eax
0x18001bed9  and     eax, 300000h
0x18001bede  xor     r9d, r9d
0x18001bee1  cmp     eax, 300000h
0x18001bee6  mov     edx, r9d
0x18001bee9  mov     eax, [rsp+2B0h+var_240]
0x18001beed  setz    dl
0x18001bef0  cmp     ecx, 400000h
0x18001bef6  mov     [rbp+1B0h+var_1EC], edx
0x18001bef9  lea     rcx, [r15+8]
0x18001befd  jnz     short loc_18001BF0C
0x18001beff  mov     r8d, 1
0x18001bf05  mov     [rsp+2B0h+var_25C], r8d
0x18001bf0a  jmp     short loc_18001BF1D
0x18001bf0c  mov     r8d, r9d
0x18001bf0f  mov     [rsp+2B0h+var_25C], r9d
0x18001bf14  mov     [rbp+1B0h+var_1EC], edx
0x18001bf17  jmp     short loc_18001BF1D
0x18001bf19  mov     [rbp+1B0h+var_1EC], r9d
0x18001bf1d  test    r12, r12
0x18001bf20  jnz     short loc_18001BF2A
0x18001bf22  mov     r13d, r9d
0x18001bf25  jmp     loc_18001C06E
0x18001bf2a  test    ebx, ebx
0x18001bf2c  jz      loc_18001C063
0x18001bf32  test    r13d, r13d
0x18001bf35  jns     short loc_18001BF49
0x18001bf37  mov     rcx, r12; unsigned __int16 *
0x18001bf3a  call    ?wcslen@CW32System@@SA_KPEBG@Z; CW32System::wcslen(ushort const *)
0x18001bf3f  mov     r13, rax
0x18001bf42  lea     rcx, [r15+8]
0x18001bf46  test    r13d, r13d
0x18001bf49  mov     rax, [rbp+1B0h+var_210]
0x18001bf4d  jz      short loc_18001BF92
0x18001bf4f  test    rax, rax
0x18001bf52  jnz     short loc_18001BF92
0x18001bf54  mov     edx, r13d; int
0x18001bf57  lea     rcx, [rbp+1B0h+var_160]; this
0x18001bf5b  call    ?GetBuf@CTempWcharBuf@@QEAAPEAGJ@Z; CTempWcharBuf::GetBuf(long)
0x18001bf60  mov     [rbp+1B0h+var_210], rax
0x18001bf64  test    rax, rax
0x18001bf67  jnz     short loc_18001BF8E
0x18001bf69  mov     rcx, [rbp+1B0h+lpMem]; lpMem
0x18001bf70  lea     rax, [rbp+1B0h+var_160]
0x18001bf74  cmp     rcx, rax
0x18001bf77  jz      short loc_18001BF7E
0x18001bf79  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x18001bf7e  mov     rcx, [rbp+1B0h+var_1D8]; this
0x18001bf82  call    ?Thaw@CDisplay@@QEAAXXZ; CDisplay::Thaw(void)
0x18001bf87  xor     eax, eax
0x18001bf89  jmp     loc_18001C8FD
0x18001bf8e  lea     rcx, [r15+8]; this
0x18001bf92  mov     edx, [r15+58h]
0x18001bf96  mov     [rbp+1B0h+var_220], rax
0x18001bf9a  test    edx, edx
0x18001bf9c  jg      short loc_18001BFA8
0x18001bf9e  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x18001bfa3  jmp     loc_18001C044
0x18001bfa8  movups  xmm0, xmmword ptr [r15+48h]
0x18001bfad  neg     edx; int
0x18001bfaf  lea     rcx, [rbp+1B0h+var_200]; this
0x18001bfb3  movups  [rbp+1B0h+var_200], xmm0
0x18001bfb7  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18001bfbc  mov     rcx, qword ptr [rbp+1B0h+var_200]
0x18001bfc0  test    rcx, rcx
0x18001bfc3  jz      short loc_18001C006
0x18001bfc5  cmp     dword ptr [rcx+8], 0
0x18001bfc9  jz      short loc_18001C006
0x18001bfcb  mov     edx, [rcx+8]
0x18001bfce  test    edx, edx
0x18001bfd0  jle     short loc_18001BFF1
0x18001bfd2  mov     eax, dword ptr [rbp+1B0h+var_200+8]
0x18001bfd5  cmp     eax, edx
0x18001bfd7  jge     short loc_18001BFF1
0x18001bfd9  mov     r8, [rcx]
0x18001bfdc  test    r8, r8
0x18001bfdf  jz      short loc_18001BFF1
0x18001bfe1  test    eax, eax
0x18001bfe3  js      short loc_18001BFF1
0x18001bfe5  imul    eax, [rcx+10h]
0x18001bfe9  movsxd  rdx, eax
0x18001bfec  add     rdx, r8
0x18001bfef  jmp     short loc_18001BFF3
0x18001bff1  xor     edx, edx
0x18001bff3  movzx   edx, word ptr [rdx+4]
0x18001bff7  mov     qword ptr [rbp+1B0h+var_200], 0
0x18001bfff  test    dx, dx
0x18001c002  jns     short loc_18001C015
0x18001c004  jmp     short loc_18001C00E
0x18001c006  mov     qword ptr [rbp+1B0h+var_200], 0
0x18001c00e  movzx   edx, word ptr [rdi+116h]
0x18001c015  mov     rcx, cs:qword_1800A41E8
0x18001c01c  lea     r8, [rbp+1B0h+var_200]
0x18001c020  movsx   edx, dx
0x18001c023  mov     rax, [rcx]
0x18001c026  mov     rax, [rax+20h]
0x18001c02a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c02f  test    eax, eax
0x18001c031  jns     short loc_18001C040
0x18001c033  lea     rax, ?g_defaultPF@@3VCParaFormat@@A; CParaFormat g_defaultPF
0x18001c03a  mov     qword ptr [rbp+1B0h+var_200], rax
0x18001c03e  jmp     short loc_18001C044
0x18001c040  mov     rax, qword ptr [rbp+1B0h+var_200]
0x18001c044  movzx   r11d, word ptr [rax+2]
0x18001c049  mov     r8d, [rsp+2B0h+var_25C]
0x18001c04e  mov     eax, [rsp+2B0h+var_240]
0x18001c052  shr     r11d, 0Eh
0x18001c056  and     r11d, 1
0x18001c05a  mov     dword ptr [rbp+1B0h+var_200], r11d
0x18001c05e  xor     r9d, r9d
0x18001c061  jmp     short loc_18001C06E
0x18001c063  test    r13d, r13d
0x18001c066  jns     short loc_18001C06E
0x18001c068  mov     r13d, 3FFFFFFFh
0x18001c06e  shr     eax, 13h
0x18001c071  xor     edx, edx
0x18001c073  and     eax, 1
0x18001c076  mov     [rsp+2B0h+var_248], r9d
0x18001c07b  mov     [rsp+2B0h+var_24C], r9d
0x18001c080  mov     r10d, r9d
0x18001c083  mov     [rsp+2B0h+var_244], r9d
0x18001c088  mov     [rsp+2B0h+var_240], eax
0x18001c08c  mov     [rsp+2B0h+var_254], edx
0x18001c090  test    r13d, r13d
0x18001c093  jz      loc_18001C82C
  ... truncated ...
```
