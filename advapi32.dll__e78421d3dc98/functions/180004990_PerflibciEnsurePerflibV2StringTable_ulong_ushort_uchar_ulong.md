# PerflibciEnsurePerflibV2StringTable(ulong,ushort,uchar * *,ulong *)

- ea: `0x180004990`
- end: `0x180005508`
- name: `?PerflibciEnsurePerflibV2StringTable@@YAKKGPEAPEAEPEAK@Z`
- size: `2936`
- prototype: `unsigned int __fastcall(unsigned int, unsigned __int16, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting`

## callers

- `0x180038490`

## callees

- `0x180003730`
- `0x180003764`
- `0x180004990`
- `0x180005510`
- `0x1800055a0`
- `0x180006488`
- `0x180014e2c`
- `0x18001708c`
- `0x180017100`
- `0x1800297d0`
- `0x180029828`
- `0x18002bbd8`
- `0x18003b698`
- `0x18003b748`
- `0x18003d048`
- `0x18003d070`
- `0x180065042`
- `0x18006505a`

## import_xrefs

- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180004ad9`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180004b20`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180004ad9`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180004b20`
- `KERNEL32!LocalFree` at `0x180004fbb`
- `KERNEL32!LocalFree` at `0x180004fd2`
- `KERNEL32!LocalFree` at `0x1800050fd`
- `KERNEL32!LocalFree` at `0x180005106`
- `KERNEL32!LocalFree` at `0x180005470`
- `KERNEL32!LocalFree` at `0x180004fbb`
- `KERNEL32!LocalFree` at `0x180004fd2`
- `KERNEL32!LocalFree` at `0x1800050fd`
- `KERNEL32!LocalFree` at `0x180005106`
- `KERNEL32!LocalFree` at `0x180005470`

## pseudocode

```c
__int64 __fastcall PerflibciEnsurePerflibV2StringTable(
        unsigned int a1,
        __int16 a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  __int16 v4; // bx
  bool v6; // si
  unsigned int *v7; // r9
  unsigned __int16 *v8; // r12
  DWORD v9; // r15d
  unsigned __int8 *v10; // rdi
  __int64 v11; // r13
  _QWORD *v12; // r14
  char v13; // bl
  __int16 v14; // cx
  int ThreadPreferredUILanguages; // eax
  unsigned __int16 *v16; // rax
  __int64 v17; // r14
  unsigned int v18; // eax
  unsigned int v19; // ebx
  enum _PerfRegInfoType v20; // edi
  unsigned int LangIdFromSzLang; // r13d
  const struct _GUID *v22; // r15
  unsigned __int8 *v23; // r14
  unsigned int v24; // esi
  unsigned int v25; // eax
  unsigned int v26; // r12d
  __int64 v27; // r14
  bool v28; // zf
  int v29; // r12d
  char v30; // si
  _WORD *v31; // rdi
  __int64 v32; // rax
  unsigned int v33; // edx
  unsigned int v34; // ecx
  __int64 v35; // rax
  unsigned int v36; // r11d
  unsigned __int64 v37; // r9
  __int64 v38; // rcx
  _WORD *v39; // rdx
  unsigned __int8 *v40; // r8
  unsigned __int8 *v41; // rcx
  __int64 v42; // rax
  int v43; // r13d
  bool v44; // al
  enum _PerfRegInfoType v45; // ebx
  unsigned int v46; // edi
  unsigned int v47; // eax
  unsigned int v48; // edx
  unsigned int v49; // edx
  bool v50; // r8
  unsigned int v51; // r9d
  _DWORD *v52; // rsi
  int v53; // ecx
  __int64 v54; // r14
  __int64 v55; // r12
  __int64 v56; // rcx
  _WORD *v57; // rbx
  __int64 v58; // rax
  unsigned int v59; // ecx
  unsigned __int16 *v60; // rdi
  __int64 v61; // rax
  __int64 v62; // r10
  unsigned __int64 v63; // r8
  __int64 v64; // rcx
  unsigned __int8 *v65; // rdx
  unsigned __int8 *v66; // rcx
  __int64 v67; // rax
  unsigned __int64 v68; // rcx
  unsigned int v69; // esi
  unsigned __int8 *v70; // rax
  unsigned int v71; // ebx
  unsigned __int64 v72; // rcx
  unsigned __int16 *v74; // rbx
  unsigned int v75; // eax
  __int64 v76; // rax
  __int64 v77; // rax
  unsigned __int64 v78; // rdx
  unsigned __int64 v79; // rdx
  signed __int64 v80; // rbx
  signed __int64 v81; // rsi
  bool v82; // [rsp+48h] [rbp-59h]
  __int16 v83; // [rsp+4Ah] [rbp-57h]
  unsigned int v84; // [rsp+4Ch] [rbp-55h]
  int v85; // [rsp+50h] [rbp-51h]
  unsigned __int8 *Src; // [rsp+58h] [rbp-49h]
  unsigned int v87; // [rsp+60h] [rbp-41h] BYREF
  _DWORD Size[3]; // [rsp+64h] [rbp-3Dh]
  HLOCAL hMem; // [rsp+70h] [rbp-31h] BYREF
  void *v90; // [rsp+78h] [rbp-29h]
  _BYTE *v91; // [rsp+80h] [rbp-21h]
  unsigned int v92; // [rsp+88h] [rbp-19h] BYREF
  int v93; // [rsp+8Ch] [rbp-15h]
  unsigned __int16 *v94; // [rsp+90h] [rbp-11h]
  int v95; // [rsp+98h] [rbp-9h] BYREF
  int v96; // [rsp+9Ch] [rbp-5h]
  _QWORD *v97; // [rsp+A0h] [rbp-1h]
  __int64 v98; // [rsp+A8h] [rbp+7h]
  unsigned int v99; // [rsp+108h] [rbp+67h]
  char v100; // [rsp+110h] [rbp+6Fh]

  v99 = a1;
  v4 = a1;
  v6 = ((a2 - 72) & 0xFFDF) == 0;
  v82 = v6;
  utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>(&hMem);
  v87 = 0;
  v8 = 0;
  v95 = 0;
  v92 = 0;
  v94 = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_57908ebe3a6b3f9305bc9279d0bf0558_Traceguids);
    v7 = a4;
  }
  if ( !a3 || !v7 )
  {
    v9 = 87;
    goto LABEL_111;
  }
  *a3 = 0;
  *v7 = 0;
  v9 = PerflibciEnsureCounterSetList();
  if ( v9 )
    goto LABEL_111;
  v10 = 0;
  v9 = PerflibciLocalWaitForMutex(g_hGlobalMutex);
  if ( v9 )
    goto LABEL_110;
  Size[0] = 0;
  v93 = 0;
  v83 = v4 & 0x3FF;
  LODWORD(v11) = 0;
  v12 = g_ObjectList;
  *(_QWORD *)&Size[1] = 4096;
  v97 = g_ObjectList;
  Src = (unsigned __int8 *)operator new(4096);
  v10 = Src;
  if ( Src )
  {
    v100 = 1;
    if ( (unsigned __int64)(v91 - (_BYTE *)hMem) >= 0x1000 )
      goto LABEL_132;
    v79 = 7 * ((unsigned __int64)(v91 - (_BYTE *)hMem) >> 2) + 8;
    if ( v79 >= 0x1000 )
    {
      if ( v79 > 0x7FFFFFFFFFFFFFFFLL )
        v79 = 0x7FFFFFFFFFFFFFFFLL;
    }
    else
    {
      v79 = 4096;
    }
    if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::_SetCapacity(&hMem, v79) )
    {
LABEL_132:
      v13 = 1;
    }
    else
    {
      v13 = 0;
      v9 = 14;
      v100 = 0;
    }
    utl::vector<unsigned char,utl::allocator<unsigned char>>::_Resize<,0>(&hMem, v91 - (_BYTE *)hMem);
  }
  else
  {
    v13 = 0;
    v9 = 14;
    v100 = 0;
  }
  v14 = v83;
  if ( v83 == 9 )
  {
    ThreadPreferredUILanguages = RtlGetThreadPreferredUILanguages(36, &v95, 0, &v92);
    if ( ThreadPreferredUILanguages == -1073741789 || !ThreadPreferredUILanguages )
    {
      if ( v92 )
      {
        v16 = (unsigned __int16 *)operator new(saturated_mul(v92, 2u));
        v94 = v16;
        if ( v16 )
          RtlGetThreadPreferredUILanguages(36, &v95, v16, &v92);
      }
    }
    v14 = 9;
  }
  if ( !v13 )
    goto LABEL_108;
  while ( v12 )
  {
    v17 = v12[4];
    v98 = v17;
    if ( !v17 )
      goto LABEL_58;
    v18 = *(_DWORD *)(v17 + 92);
    v96 = v11;
    v19 = v18 + 1;
    if ( !v6 )
      v19 = v18;
    v84 = v19;
    if ( v14 == 9 )
    {
      v20 = PERF_REG_COUNTERSET_HELP_STRING;
      if ( !v6 )
        v20 = PERF_REG_COUNTERSET_ENGLISH_NAME;
    }
    else
    {
      v20 = v6 + 3;
    }
    LangIdFromSzLang = v99;
    v22 = (const struct _GUID *)(v17 + 24);
    v23 = (unsigned __int8 *)hMem;
    do
    {
      v24 = (_DWORD)v90 - (_DWORD)v23;
      v25 = PerflibciLocalQueryCounterSetRegInfoEx(0, v22, v20, LangIdFromSzLang, v23, (_DWORD)v90 - (_DWORD)v23, &v87);
      v85 = v25;
      v26 = v25;
      if ( (v25 == 15100 || v25 == 15105) && v83 == 9 )
      {
        if ( v94 )
        {
          v74 = v94;
          if ( *v94 )
          {
            do
            {
              LangIdFromSzLang = GetLangIdFromSzLang(v74);
              v75 = PerflibciLocalQueryCounterSetRegInfoEx(0, v22, v20, LangIdFromSzLang, v23, v24, &v87);
              v85 = v75;
              v26 = v75;
              if ( v75 != 15100 && v75 != 15105 )
                break;
              v76 = -1;
              do
                ++v76;
              while ( v74[v76] );
              v77 = (unsigned int)(v76 + 1);
              v28 = v74[v77] == 0;
              v74 += v77;
            }
            while ( !v28 );
          }
        }
      }
      if ( v26 )
      {
        if ( v26 == 8 )
          goto LABEL_153;
        if ( LangIdFromSzLang == (LangIdFromSzLang & 0x3FF) )
        {
          LangIdFromSzLang |= 0x400u;
          v26 = PerflibciLocalQueryCounterSetRegInfoEx(0, v22, v20, LangIdFromSzLang, v23, v24, &v87);
          v85 = v26;
        }
      }
      if ( v26 != 8 )
        break;
LABEL_153:
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               &hMem,
                               (v87 + 7) & 0xFFFFFFF8) )
      {
        v26 = 14;
        v100 = 0;
        v85 = 14;
      }
      v23 = (unsigned __int8 *)hMem;
      v80 = v91 - (_BYTE *)hMem;
      v81 = (_BYTE *)v90 - (_BYTE *)hMem;
      if ( v91 - (_BYTE *)hMem > (unsigned __int64)((_BYTE *)v90 - (_BYTE *)hMem) )
      {
        if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                                &hMem,
                                v91 - (_BYTE *)hMem) )
        {
          memset_0(v90, 0, v80 - v81);
          v23 = (unsigned __int8 *)hMem;
          v90 = (char *)hMem + v80;
        }
        else
        {
          v23 = (unsigned __int8 *)hMem;
        }
      }
      else
      {
        v90 = v91;
      }
    }
    while ( v26 == 8 );
    v27 = v98;
    v28 = v26 == 15100;
    v29 = v96;
    v99 = LangIdFromSzLang;
    v11 = Size[0];
    if ( v28 || v85 == 15105 )
    {
      if ( !v85 )
      {
        v44 = v82;
        v30 = v82;
        if ( v82 )
        {
          LODWORD(v31) = (_DWORD)hMem;
          goto LABEL_47;
        }
        v9 = v85;
        v13 = v100;
        goto LABEL_57;
      }
      v50 = v82;
      v49 = v84;
      v30 = v82;
      goto LABEL_54;
    }
    v30 = 1;
    if ( v85 )
    {
LABEL_51:
      v49 = v84;
      v50 = v82;
LABEL_54:
      v51 = v99;
LABEL_55:
      v9 = v85;
      v13 = v100;
      if ( v85 == 15100 )
        goto LABEL_56;
      v10 = Src;
      v99 = v51;
      Size[0] = v11;
      if ( v85 == 15105 )
      {
        Size[0] = v11;
        v99 = v51;
LABEL_56:
        if ( v50 )
          goto LABEL_61;
        goto LABEL_57;
      }
      if ( v85 )
      {
        Size[0] = v11;
        v99 = v51;
        goto LABEL_61;
      }
      if ( !v30 )
      {
        v99 = v51;
        goto LABEL_57;
      }
      v52 = hMem;
      v53 = *((_DWORD *)hMem + 1);
      if ( v53 != *(_DWORD *)(v27 + 128) )
      {
        v9 = 13;
        goto LABEL_58;
      }
      v54 = 0;
      v99 = v51;
      if ( !v53 )
      {
        ++v93;
        Size[0] = v11;
        goto LABEL_58;
      }
      v55 = *(_QWORD *)&Size[1];
      while ( 1 )
      {
        v56 = (unsigned int)v52[2 * v54 + 3];
        if ( (_DWORD)v56 != -1 )
        {
          v57 = (_WORD *)((char *)v52 + v56);
          v58 = -1;
          do
            v28 = v57[++v58] == 0;
          while ( !v28 );
          v59 = v11 + 2 * v58 + 20;
          v87 = v59;
          if ( v59 >= (unsigned int)v55 )
          {
            v68 = (v59 + 4103) & 0xFFFFFFF8;
            v55 = (unsigned int)v68;
            if ( (unsigned int)v11 > (unsigned int)v68 )
            {
              LocalFree(v10);
              v10 = 0;
              Src = 0;
              goto LABEL_165;
            }
            v69 = v68;
            v70 = (unsigned __int8 *)operator new(v68, (const struct std::nothrow_t *)&std::nothrow);
            v10 = v70;
            if ( !v70 )
            {
              LocalFree(Src);
              Src = 0;
              v52 = hMem;
LABEL_165:
              v49 = v84;
              v13 = 0;
              v100 = 0;
              v9 = 14;
              goto LABEL_91;
            }
            memset_0(v70, 0, v69);
            memcpy_0(v10, Src, (unsigned int)v11);
            LocalFree(Src);
            v52 = hMem;
            Src = v10;
          }
          if ( !v9 )
          {
            v60 = (unsigned __int16 *)&v10[(unsigned int)v11];
            StringCbPrintfW(v60, (unsigned int)(v55 - v11), L"%d", v84);
            v61 = -1;
            do
              v28 = v60[++v61] == 0;
            while ( !v28 );
            v10 = Src;
            v62 = (unsigned int)(v11 + 2 * v61 + 2);
            v63 = (unsigned __int64)(unsigned int)(v55 - v62) >> 1;
            if ( v63 )
            {
              v64 = 2147483646;
              v65 = &Src[v62];
              do
              {
                if ( !v64 )
                  break;
                if ( !*v57 )
                  break;
                *(_WORD *)v65 = *v57++;
                v65 += 2;
                --v64;
                --v63;
              }
              while ( v63 );
              v66 = v65 - 2;
              if ( v63 )
                v66 = v65;
              *(_WORD *)v66 = 0;
            }
            v67 = -1;
            do
              v28 = *(_WORD *)&Src[2 * v67++ + 2 + v62] == 0;
            while ( !v28 );
            LODWORD(v11) = v62 + 2 * (v67 + 1);
          }
          v49 = v84;
        }
        v13 = v100;
LABEL_91:
        v49 += 2;
        v54 = (unsigned int)(v54 + 1);
        v84 = v49;
        if ( (unsigned int)v54 >= v52[1] )
        {
          *(_QWORD *)&Size[1] = v55;
          Size[0] = v11;
          goto LABEL_63;
        }
      }
    }
    v31 = hMem;
    v32 = -1;
    do
      v28 = *((_WORD *)hMem + ++v32) == 0;
    while ( !v28 );
    v33 = Size[1];
    v34 = Size[0] + 20 + 2 * v32;
    v87 = v34;
    if ( v34 >= Size[1] )
    {
      v71 = (v34 + 4103) & 0xFFFFFFF8;
      Src = PerflibciExtendBuffer(Src, Size[0], v71);
      if ( !Src )
      {
        v9 = 14;
        v10 = 0;
        break;
      }
      Size[1] = v71;
      v33 = v71;
    }
    StringCbPrintfW((unsigned __int16 *)&Src[v11], v33 - (unsigned int)v11, L"%d", v84);
    v84 += 2;
    v35 = -1;
    do
      v28 = *(_WORD *)&Src[2 * v35++ + 2 + v11] == 0;
    while ( !v28 );
    v36 = v11 + 2 + 2 * v35;
    v37 = (unsigned __int64)(Size[1] - v36) >> 1;
    if ( v37 )
    {
      v38 = 2147483646;
      v39 = v31;
      v40 = &Src[v36];
      do
      {
        if ( !v38 )
          break;
        if ( !*v39 )
          break;
        *(_WORD *)v40 = *v39++;
        v40 += 2;
        --v38;
        --v37;
      }
      while ( v37 );
      v41 = v40 - 2;
      if ( v37 )
        v41 = v40;
      *(_WORD *)v41 = 0;
    }
    v42 = -1;
    do
      v28 = *(_WORD *)&Src[2 * v42++ + 2 + v36] == 0;
    while ( !v28 );
    v43 = v42 + 1;
    v44 = v82;
    LODWORD(v11) = v36 + 2 * v43;
    Size[0] = v11;
LABEL_47:
    if ( v83 == 9 )
      v45 = 4 * !v44 + 6;
    else
      v45 = v44 + 5;
    while ( 2 )
    {
      v46 = (_DWORD)v90 - (_DWORD)v31;
      v47 = PerflibciLocalQueryCounterSetRegInfoEx(0, v22, v45, v99, (unsigned __int8 *)hMem, v46, &v87);
      v85 = v47;
      v48 = v47;
      if ( v47 )
      {
        if ( v47 == 8 )
          goto LABEL_105;
        v51 = v99;
        if ( v99 == (v99 & 0x3FF) )
        {
          v99 |= 0x400u;
          v48 = PerflibciLocalQueryCounterSetRegInfoEx(0, v22, v45, v99, (unsigned __int8 *)hMem, v46, &v87);
          v85 = v48;
          goto LABEL_50;
        }
        v49 = v84;
        v50 = v82;
        goto LABEL_55;
      }
LABEL_50:
      if ( v48 != 8 )
        goto LABEL_51;
LABEL_105:
      v72 = (v87 + 7) & 0xFFFFFFF8;
      if ( v72 <= v91 - (_BYTE *)hMem )
      {
LABEL_106:
        v85 = v48;
        utl::vector<unsigned char,utl::allocator<unsigned char>>::_Resize<,0>(&hMem, v91 - (_BYTE *)hMem);
        if ( v85 != 8 )
          goto LABEL_51;
        LODWORD(v31) = (_DWORD)hMem;
        continue;
      }
      break;
    }
    v78 = (v87 + 7) & 0xFFFFFFF8;
    if ( 7 * ((unsigned __int64)(v91 - (_BYTE *)hMem) >> 2) + 8 >= v72 )
      v78 = 7 * ((unsigned __int64)(v91 - (_BYTE *)hMem) >> 2) + 8;
    if ( v78 > 0x7FFFFFFFFFFFFFFFLL )
      v78 = 0x7FFFFFFFFFFFFFFFLL;
    if ( v72 <= v78
      && (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::_SetCapacity(&hMem, v78) )
    {
      v48 = v85;
      goto LABEL_106;
    }
    v13 = 0;
    v9 = 14;
    v100 = 0;
    utl::vector<unsigned char,utl::allocator<unsigned char>>::_Resize<,0>(&hMem, v91 - (_BYTE *)hMem);
LABEL_61:
    if ( !v30 )
    {
LABEL_57:
      v10 = Src;
      LODWORD(v11) = v29;
      Size[0] = v29;
      goto LABEL_58;
    }
    v10 = Src;
LABEL_63:
    if ( !v9 )
      ++v93;
LABEL_58:
    v12 = (_QWORD *)v97[3];
    v97 = v12;
    if ( v13 )
    {
      v6 = v82;
      v14 = v83;
      continue;
    }
    break;
  }
LABEL_108:
  PerflibciLocalReleaseMutex(g_hGlobalMutex);
  if ( v93 && v10 )
  {
    v8 = v94;
    if ( (_DWORD)v11 )
    {
      v9 = 0;
      *a3 = v10;
      *a4 = v11 + 2;
      goto LABEL_111;
    }
  }
  else
  {
    v8 = v94;
  }
LABEL_110:
  LocalFree(v10);
LABEL_111:
  LocalFree(v8);
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_57908ebe3a6b3f9305bc9279d0bf0558_Traceguids);
  if ( hMem != (HLOCAL)-1LL )
    operator delete(hMem);
  return v9;
}

```

## disassembly

```asm
0x180004990  mov     rax, rsp
0x180004993  mov     [rax+20h], r9
0x180004997  mov     [rax+18h], r8
0x18000499b  mov     [rax+8], ecx
0x18000499e  push    rbp
0x18000499f  lea     rbp, [rax-5Fh]
0x1800049a3  sub     rsp, 0F0h
0x1800049aa  mov     [rax-10h], rbx
0x1800049ae  sub     dx, 48h ; 'H'
0x1800049b2  mov     [rax-18h], rsi
0x1800049b6  mov     ebx, ecx
0x1800049b8  mov     [rax-20h], rdi
0x1800049bc  mov     rdi, r8
0x1800049bf  mov     [rax-28h], r12
0x1800049c3  mov     [rax-38h], r14
0x1800049c7  mov     eax, 0FFDFh
0x1800049cc  test    ax, dx
0x1800049cf  jnz     loc_180005373
0x1800049d5  mov     sil, 1
0x1800049d8  lea     rcx, [rbp+57h+hMem]
0x1800049dc  mov     [rbp+57h+var_B0], sil
0x1800049e0  call    ??0?$vector@UEXT_OBJ_LIST@@V?$allocator@UEXT_OBJ_LIST@@@utl@@@utl@@QEAA@XZ; utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>(void)
0x1800049e5  xor     r14d, r14d
0x1800049e8  mov     [rbp+57h+var_98], r14d
0x1800049ec  mov     r12d, r14d
0x1800049ef  mov     [rbp+57h+var_60], r14d
0x1800049f3  mov     [rbp+57h+var_70], r14d
0x1800049f7  mov     [rbp+57h+var_68], r14
0x1800049fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a02  test    dword ptr [rcx+1Ch], 400h
0x180004a09  jnz     loc_18000537B
0x180004a0f  mov     [rsp+0F0h+var_28], r13
0x180004a17  mov     [rsp+0F0h+var_38], r15
0x180004a1f  test    rdi, rdi
0x180004a22  jz      loc_1800052C3
0x180004a28  test    r9, r9
0x180004a2b  jz      loc_1800052C3
0x180004a31  mov     [rdi], r14
0x180004a34  mov     [r9], r14d
0x180004a37  call    ?PerflibciEnsureCounterSetList@@YAKXZ; PerflibciEnsureCounterSetList(void)
0x180004a3c  mov     r15d, eax
0x180004a3f  test    eax, eax
0x180004a41  jnz     loc_180005103
0x180004a47  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x180004a4e  mov     rdi, r14
0x180004a51  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x180004a56  mov     r15d, eax
0x180004a59  test    eax, eax
0x180004a5b  jnz     loc_1800050FA
0x180004a61  mov     ecx, 3FFh
0x180004a66  mov     dword ptr [rbp+57h+Size], r14d
0x180004a6a  and     bx, cx
0x180004a6d  mov     [rbp+57h+var_6C], r14d
0x180004a71  mov     [rbp+57h+var_AE], bx
0x180004a75  mov     r13d, r14d
0x180004a78  mov     r14, cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x180004a7f  mov     ebx, 1000h
0x180004a84  mov     ecx, ebx
0x180004a86  mov     qword ptr [rbp+57h+Size+4], rbx
0x180004a8a  mov     [rbp+57h+var_58], r14
0x180004a8e  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180004a93  mov     [rbp+57h+Src], rax
0x180004a97  mov     rdi, rax
0x180004a9a  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180004aa4  test    rax, rax
0x180004aa7  jnz     loc_18000526B
0x180004aad  xor     bl, bl
0x180004aaf  mov     r15d, 0Eh
0x180004ab5  mov     [rbp+57h+arg_8], bl
0x180004ab8  movzx   ecx, [rbp+57h+var_AE]
0x180004abc  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180004ac3  cmp     cx, 9
0x180004ac7  jnz     short loc_180004B2A
0x180004ac9  lea     r9, [rbp+57h+var_70]
0x180004acd  xor     r8d, r8d
0x180004ad0  lea     rdx, [rbp+57h+var_60]
0x180004ad4  mov     ecx, 24h ; '$'
0x180004ad9  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180004adf  cmp     eax, 0C0000023h
0x180004ae4  jz      short loc_180004AEA
0x180004ae6  test    eax, eax
0x180004ae8  jnz     short loc_180004B26
0x180004aea  mov     eax, [rbp+57h+var_70]
0x180004aed  test    eax, eax
0x180004aef  jz      short loc_180004B26
0x180004af1  mov     edx, eax
0x180004af3  mov     eax, 2
0x180004af8  mul     rdx
0x180004afb  cmovb   rax, r12
0x180004aff  mov     rcx, rax
0x180004b02  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180004b07  mov     [rbp+57h+var_68], rax
0x180004b0b  test    rax, rax
0x180004b0e  jz      short loc_180004B26
0x180004b10  lea     r9, [rbp+57h+var_70]
0x180004b14  mov     r8, rax
0x180004b17  lea     rdx, [rbp+57h+var_60]
0x180004b1b  mov     ecx, 24h ; '$'
0x180004b20  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180004b26  movzx   ecx, [rbp+57h+var_AE]
0x180004b2a  test    bl, bl
0x180004b2c  jz      loc_1800050E0
0x180004b32  mov     edx, 9
0x180004b37  test    r14, r14
0x180004b3a  jz      loc_1800050E0
0x180004b40  mov     r14, [r14+20h]
0x180004b44  mov     [rbp+57h+var_50], r14
0x180004b48  test    r14, r14
0x180004b4b  jz      loc_180004DA4
0x180004b51  mov     eax, [r14+5Ch]
0x180004b55  test    sil, sil
0x180004b58  mov     [rbp+57h+var_5C], r13d
0x180004b5c  lea     ebx, [rax+1]
0x180004b5f  cmovz   ebx, eax
0x180004b62  mov     [rbp+57h+var_AC], ebx
0x180004b65  cmp     cx, 9
0x180004b69  jnz     loc_180004FEE
0x180004b6f  test    sil, sil
0x180004b72  mov     edi, 4
0x180004b77  cmovz   edi, edx
0x180004b7a  mov     r13d, [rbp+57h+arg_0]
0x180004b7e  lea     r15, [r14+18h]
0x180004b82  mov     r14, [rbp+57h+hMem]
0x180004b86  mov     esi, dword ptr [rbp+57h+var_80]
0x180004b89  lea     rax, [rbp+57h+var_98]
0x180004b8d  mov     [rsp+30h], rax; unsigned int *
0x180004b92  sub     esi, r14d
0x180004b95  mov     [rsp+0F0h+var_C8], esi; unsigned int
0x180004b99  mov     r9d, r13d; unsigned int
0x180004b9c  mov     r8d, edi; enum _PerfRegInfoType
0x180004b9f  mov     [rsp+0F0h+var_D0], r14; unsigned __int8 *
0x180004ba4  mov     rdx, r15; struct _GUID *
0x180004ba7  xor     ecx, ecx; unsigned __int8
0x180004ba9  call    ?PerflibciLocalQueryCounterSetRegInfoEx@@YAKEPEBU_GUID@@W4_PerfRegInfoType@@KPEAEKPEAK@Z; PerflibciLocalQueryCounterSetRegInfoEx(uchar,_GUID const *,_PerfRegInfoType,ulong,uchar *,ulong,ulong *)
0x180004bae  mov     [rbp+57h+var_A8], eax
0x180004bb1  mov     r12d, eax
0x180004bb4  cmp     eax, 3AFCh
0x180004bb9  jz      loc_18000517D
0x180004bbf  cmp     eax, 3B01h
0x180004bc4  jz      loc_18000517D
0x180004bca  test    r12d, r12d
0x180004bcd  jnz     loc_18000500E
0x180004bd3  cmp     r12d, 8
0x180004bd7  jz      loc_1800053A3
0x180004bdd  mov     r14, [rbp+57h+var_50]
0x180004be1  cmp     r12d, 3AFCh
0x180004be8  mov     r12d, [rbp+57h+var_5C]
0x180004bec  mov     eax, [rbp+57h+var_A8]
0x180004bef  mov     [rbp+57h+arg_0], r13d
0x180004bf3  mov     r13d, dword ptr [rbp+57h+Size]
0x180004bf7  jz      loc_180004D63
0x180004bfd  cmp     eax, 3B01h
0x180004c02  jz      loc_180004D63
0x180004c08  mov     sil, 1
0x180004c0b  test    eax, eax
0x180004c0d  jnz     loc_180004D59
0x180004c13  mov     rdi, [rbp+57h+hMem]
0x180004c17  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004c1e  xchg    ax, ax
0x180004c20  cmp     word ptr [rdi+rax*2+2], 0
0x180004c26  lea     rax, [rax+1]
0x180004c2a  jnz     short loc_180004C20
0x180004c2c  mov     rdx, qword ptr [rbp+57h+Size+4]
0x180004c30  lea     ecx, [r13+14h]
0x180004c34  lea     ecx, [rcx+rax*2]
0x180004c37  mov     [rbp+57h+var_98], ecx
0x180004c3a  cmp     ecx, edx
0x180004c3c  jnb     loc_18000505C
0x180004c42  mov     r9d, [rbp+57h+var_AC]
0x180004c46  lea     r8, aD; "%d"
0x180004c4d  mov     rbx, r13
0x180004c50  sub     edx, r13d; unsigned __int64
0x180004c53  add     rbx, [rbp+57h+Src]
0x180004c57  mov     rcx, rbx; unsigned __int16 *
0x180004c5a  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004c5f  add     [rbp+57h+var_AC], 2
0x180004c63  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004c6a  nop     word ptr [rax+rax+00h]
0x180004c70  cmp     word ptr [rbx+rax*2+2], 0
0x180004c76  lea     rax, [rax+1]
0x180004c7a  jnz     short loc_180004C70
0x180004c7c  mov     r9d, dword ptr [rbp+57h+Size+4]
0x180004c80  lea     r11d, [r13+2]
0x180004c84  mov     r10, [rbp+57h+Src]
0x180004c88  lea     r11d, [r11+rax*2]
0x180004c8c  mov     ecx, r11d
0x180004c8f  sub     r9d, r11d
0x180004c92  add     r10, rcx
0x180004c95  shr     r9, 1
0x180004c98  jz      short loc_180004CD7
0x180004c9a  mov     ecx, 7FFFFFFEh
0x180004c9f  mov     rdx, rdi
0x180004ca2  mov     r8, r10
0x180004ca5  test    rcx, rcx
0x180004ca8  jz      short loc_180004CC7
0x180004caa  movzx   eax, word ptr [rdx]
0x180004cad  test    ax, ax
0x180004cb0  jz      short loc_180004CC7
0x180004cb2  mov     [r8], ax
0x180004cb6  add     rdx, 2
0x180004cba  add     r8, 2
0x180004cbe  dec     rcx
0x180004cc1  sub     r9, 1
0x180004cc5  jnz     short loc_180004CA5
0x180004cc7  test    r9, r9
0x180004cca  lea     rcx, [r8-2]
0x180004cce  cmovnz  rcx, r8
0x180004cd2  xor     eax, eax
0x180004cd4  mov     [rcx], ax
0x180004cd7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004cde  xchg    ax, ax
0x180004ce0  cmp     word ptr [r10+rax*2+2], 0
0x180004ce7  lea     rax, [rax+1]
0x180004ceb  jnz     short loc_180004CE0
0x180004ced  lea     r13d, [rax+1]
0x180004cf1  movzx   eax, [rbp+57h+var_B0]
0x180004cf5  lea     r13d, [r11+r13*2]
0x180004cf9  mov     dword ptr [rbp+57h+Size], r13d
0x180004cfd  cmp     [rbp+57h+var_AE], 9
0x180004d02  jnz     loc_180004FFF
0x180004d08  movzx   eax, al
0x180004d0b  xor     eax, 1
0x180004d0e  lea     ebx, ds:6[rax*4]
0x180004d15  mov     eax, dword ptr [rbp+57h+var_80]
0x180004d18  mov     r8d, ebx; enum _PerfRegInfoType
0x180004d1b  mov     r9d, [rbp+57h+arg_0]; unsigned int
0x180004d1f  sub     eax, edi
0x180004d21  mov     edi, eax
0x180004d23  mov     rdx, r15; struct _GUID *
0x180004d26  lea     rax, [rbp+57h+var_98]
0x180004d2a  xor     ecx, ecx; unsigned __int8
0x180004d2c  mov     [rsp+30h], rax; unsigned int *
0x180004d31  mov     rax, [rbp+57h+hMem]
0x180004d35  mov     [rsp+0F0h+var_C8], edi; unsigned int
0x180004d39  mov     [rsp+0F0h+var_D0], rax; unsigned __int8 *
0x180004d3e  call    ?PerflibciLocalQueryCounterSetRegInfoEx@@YAKEPEBU_GUID@@W4_PerfRegInfoType@@KPEAEKPEAK@Z; PerflibciLocalQueryCounterSetRegInfoEx(uchar,_GUID const *,_PerfRegInfoType,ulong,uchar *,ulong,ulong *)
0x180004d43  mov     [rbp+57h+var_A8], eax
0x180004d46  mov     edx, eax
0x180004d48  test    eax, eax
0x180004d4a  jnz     loc_180005091
0x180004d50  cmp     edx, 8
0x180004d53  jz      loc_18000509A
0x180004d59  mov     edx, [rbp+57h+var_AC]
0x180004d5c  movzx   r8d, [rbp+57h+var_B0]
0x180004d61  jmp     short loc_180004D7A
0x180004d63  test    eax, eax
0x180004d65  jz      loc_18000540F
0x180004d6b  movzx   r8d, [rbp+57h+var_B0]
0x180004d70  mov     edx, [rbp+57h+var_AC]
0x180004d73  movzx   esi, r8b
0x180004d77  mov     [rbp+57h+var_AC], edx
0x180004d7a  mov     r9d, [rbp+57h+arg_0]
0x180004d7e  mov     r15d, [rbp+57h+var_A8]
0x180004d82  movzx   ebx, [rbp+57h+arg_8]
0x180004d86  cmp     r15d, 3AFCh
0x180004d8d  jnz     short loc_180004DEF
0x180004d8f  test    r8b, r8b
0x180004d92  jnz     short loc_180004DDC
0x180004d94  mov     rdi, [rbp+57h+Src]
0x180004d98  mov     r13d, r12d
0x180004d9b  mov     dword ptr [rbp+57h+Size], r12d
0x180004d9f  mov     edx, 9
0x180004da4  mov     r14, [rbp+57h+var_58]
0x180004da8  mov     r14, [r14+18h]
0x180004dac  mov     [rbp+57h+var_58], r14
0x180004db0  test    bl, bl
0x180004db2  jz      loc_1800050E0
0x180004db8  movzx   esi, [rbp+57h+var_B0]
0x180004dbc  movzx   ecx, [rbp+57h+var_AE]
0x180004dc0  jmp     loc_180004B37
0x180004dc5  mov     rcx, qword ptr [rbp+57h+Size+4]
0x180004dc9  mov     qword ptr [rbp+57h+Size+4], rcx
0x180004dcd  mov     [rbp+57h+Src], rdi
0x180004dd1  mov     dword ptr [rbp+57h+Size], r13d
0x180004dd5  mov     [rbp+57h+arg_0], r9d
0x180004dd9  mov     [rbp+57h+arg_8], bl
0x180004ddc  test    sil, sil
0x180004ddf  jz      short loc_180004D94
0x180004de1  mov     rdi, [rbp+57h+Src]
0x180004de5  test    r15d, r15d
0x180004de8  jnz     short loc_180004D9F
0x180004dea  inc     [rbp+57h+var_6C]
0x180004ded  jmp     short loc_180004D9F
0x180004def  mov     rdi, [rbp+57h+Src]
0x180004df3  mov     [rbp+57h+Src], rdi
0x180004df7  mov     [rbp+57h+arg_8], bl
0x180004dfa  mov     [rbp+57h+arg_0], r9d
0x180004dfe  mov     dword ptr [rbp+57h+Size], r13d
0x180004e02  cmp     r15d, 3B01h
0x180004e09  jz      loc_1800054AD
0x180004e0f  test    r15d, r15d
0x180004e12  jnz     short loc_180004DC5
0x180004e14  test    sil, sil
0x180004e17  jz      loc_180005495
0x180004e1d  mov     rsi, [rbp+57h+hMem]
0x180004e21  mov     ecx, [rsi+4]
0x180004e24  cmp     ecx, [r14+80h]
0x180004e2b  jnz     loc_180005319
0x180004e31  xor     r14d, r14d
0x180004e34  mov     [rbp+57h+Src], rdi
  ... truncated ...
```
