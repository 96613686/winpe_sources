# PerflibciEnsurePerflibV2StringTable(ulong,ushort,uchar * *,ulong *)

- ea: `0x180004ec0`
- end: `0x180005a6d`
- name: `?PerflibciEnsurePerflibV2StringTable@@YAKKGPEAPEAEPEAK@Z`
- size: `2989`
- prototype: `unsigned int __fastcall(unsigned int, unsigned __int16, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting`

## callers

- `0x18003c6c8`

## callees

- `0x180001978`
- `0x1800025fc`
- `0x180002e40`
- `0x180004ec0`
- `0x180005a80`
- `0x180005b20`
- `0x180006ad4`
- `0x180006fe0`
- `0x18000c2bc`
- `0x18000dc60`
- `0x18002cdc0`
- `0x18002ce18`
- `0x18003fc48`
- `0x18003fd04`
- `0x18004165c`
- `0x180041684`
- `0x180072042`
- `0x18007205a`

## import_xrefs

- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180005009`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180005056`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180005009`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180005056`
- `KERNEL32!LocalFree` at `0x1800054fb`
- `KERNEL32!LocalFree` at `0x180005518`
- `KERNEL32!LocalFree` at `0x180005649`
- `KERNEL32!LocalFree` at `0x180005658`
- `KERNEL32!LocalFree` at `0x1800059cf`
- `KERNEL32!LocalFree` at `0x1800054fb`
- `KERNEL32!LocalFree` at `0x180005518`
- `KERNEL32!LocalFree` at `0x180005649`
- `KERNEL32!LocalFree` at `0x180005658`
- `KERNEL32!LocalFree` at `0x1800059cf`

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
0x180004ec0  mov     rax, rsp
0x180004ec3  mov     [rax+20h], r9
0x180004ec7  mov     [rax+18h], r8
0x180004ecb  mov     [rax+8], ecx
0x180004ece  push    rbp
0x180004ecf  lea     rbp, [rax-5Fh]
0x180004ed3  sub     rsp, 0F0h
0x180004eda  mov     [rax-10h], rbx
0x180004ede  sub     dx, 48h ; 'H'
0x180004ee2  mov     [rax-18h], rsi
0x180004ee6  mov     ebx, ecx
0x180004ee8  mov     [rax-20h], rdi
0x180004eec  mov     rdi, r8
0x180004eef  mov     [rax-28h], r12
0x180004ef3  mov     [rax-38h], r14
0x180004ef7  mov     eax, 0FFDFh
0x180004efc  test    ax, dx
0x180004eff  jnz     loc_1800058D2
0x180004f05  mov     sil, 1
0x180004f08  lea     rcx, [rbp+57h+hMem]
0x180004f0c  mov     [rbp+57h+var_B0], sil
0x180004f10  call    ??0?$vector@UEXT_OBJ_LIST@@V?$allocator@UEXT_OBJ_LIST@@@utl@@@utl@@QEAA@XZ; utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>(void)
0x180004f15  xor     r14d, r14d
0x180004f18  mov     [rbp+57h+var_98], r14d
0x180004f1c  mov     r12d, r14d
0x180004f1f  mov     [rbp+57h+var_60], r14d
0x180004f23  mov     [rbp+57h+var_70], r14d
0x180004f27  mov     [rbp+57h+var_68], r14
0x180004f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f32  test    dword ptr [rcx+1Ch], 400h
0x180004f39  jnz     loc_1800058DA
0x180004f3f  mov     [rsp+0F0h+var_28], r13
0x180004f47  mov     [rsp+0F0h+var_38], r15
0x180004f4f  test    rdi, rdi
0x180004f52  jz      loc_180005822
0x180004f58  test    r9, r9
0x180004f5b  jz      loc_180005822
0x180004f61  mov     [rdi], r14
0x180004f64  mov     [r9], r14d
0x180004f67  call    ?PerflibciEnsureCounterSetList@@YAKXZ; PerflibciEnsureCounterSetList(void)
0x180004f6c  mov     r15d, eax
0x180004f6f  test    eax, eax
0x180004f71  jnz     loc_180005655
0x180004f77  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x180004f7e  mov     rdi, r14
0x180004f81  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x180004f86  mov     r15d, eax
0x180004f89  test    eax, eax
0x180004f8b  jnz     loc_180005646
0x180004f91  mov     ecx, 3FFh
0x180004f96  mov     dword ptr [rbp+57h+Size], r14d
0x180004f9a  and     bx, cx
0x180004f9d  mov     [rbp+57h+var_6C], r14d
0x180004fa1  mov     [rbp+57h+var_AE], bx
0x180004fa5  mov     r13d, r14d
0x180004fa8  mov     r14, cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x180004faf  mov     ebx, 1000h
0x180004fb4  mov     ecx, ebx
0x180004fb6  mov     qword ptr [rbp+57h+Size+4], rbx
0x180004fba  mov     [rbp+57h+var_58], r14
0x180004fbe  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180004fc3  mov     [rbp+57h+Src], rax
0x180004fc7  mov     rdi, rax
0x180004fca  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180004fd4  test    rax, rax
0x180004fd7  jnz     loc_1800057CA
0x180004fdd  xor     bl, bl
0x180004fdf  mov     r15d, 0Eh
0x180004fe5  mov     [rbp+57h+arg_8], bl
0x180004fe8  movzx   ecx, [rbp+57h+var_AE]
0x180004fec  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180004ff3  cmp     cx, 9
0x180004ff7  jnz     short loc_180005066
0x180004ff9  lea     r9, [rbp+57h+var_70]
0x180004ffd  xor     r8d, r8d
0x180005000  lea     rdx, [rbp+57h+var_60]
0x180005004  mov     ecx, 24h ; '$'
0x180005009  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180005010  nop     dword ptr [rax+rax+00h]
0x180005015  cmp     eax, 0C0000023h
0x18000501a  jz      short loc_180005020
0x18000501c  test    eax, eax
0x18000501e  jnz     short loc_180005062
0x180005020  mov     eax, [rbp+57h+var_70]
0x180005023  test    eax, eax
0x180005025  jz      short loc_180005062
0x180005027  mov     edx, eax
0x180005029  mov     eax, 2
0x18000502e  mul     rdx
0x180005031  cmovb   rax, r12
0x180005035  mov     rcx, rax
0x180005038  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000503d  mov     [rbp+57h+var_68], rax
0x180005041  test    rax, rax
0x180005044  jz      short loc_180005062
0x180005046  lea     r9, [rbp+57h+var_70]
0x18000504a  mov     r8, rax
0x18000504d  lea     rdx, [rbp+57h+var_60]
0x180005051  mov     ecx, 24h ; '$'
0x180005056  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x18000505d  nop     dword ptr [rax+rax+00h]
0x180005062  movzx   ecx, [rbp+57h+var_AE]
0x180005066  test    bl, bl
0x180005068  jz      loc_18000562C
0x18000506e  mov     edx, 9
0x180005073  test    r14, r14
0x180005076  jz      loc_18000562C
0x18000507c  mov     r14, [r14+20h]
0x180005080  mov     [rbp+57h+var_50], r14
0x180005084  test    r14, r14
0x180005087  jz      loc_1800052E4
0x18000508d  mov     eax, [r14+5Ch]
0x180005091  test    sil, sil
0x180005094  mov     [rbp+57h+var_5C], r13d
0x180005098  lea     ebx, [rax+1]
0x18000509b  cmovz   ebx, eax
0x18000509e  mov     [rbp+57h+var_AC], ebx
0x1800050a1  cmp     cx, 9
0x1800050a5  jnz     loc_18000553A
0x1800050ab  test    sil, sil
0x1800050ae  mov     edi, 4
0x1800050b3  cmovz   edi, edx
0x1800050b6  mov     r13d, [rbp+57h+arg_0]
0x1800050ba  lea     r15, [r14+18h]
0x1800050be  mov     r14, [rbp+57h+hMem]
0x1800050c2  mov     esi, dword ptr [rbp+57h+var_80]
0x1800050c5  lea     rax, [rbp+57h+var_98]
0x1800050c9  mov     [rsp+30h], rax; unsigned int *
0x1800050ce  sub     esi, r14d
0x1800050d1  mov     [rsp+0F0h+var_C8], esi; unsigned int
0x1800050d5  mov     r9d, r13d; unsigned int
0x1800050d8  mov     r8d, edi; enum _PerfRegInfoType
0x1800050db  mov     [rsp+0F0h+var_D0], r14; unsigned __int8 *
0x1800050e0  mov     rdx, r15; struct _GUID *
0x1800050e3  xor     ecx, ecx; unsigned __int8
0x1800050e5  call    ?PerflibciLocalQueryCounterSetRegInfoEx@@YAKEPEBU_GUID@@W4_PerfRegInfoType@@KPEAEKPEAK@Z; PerflibciLocalQueryCounterSetRegInfoEx(uchar,_GUID const *,_PerfRegInfoType,ulong,uchar *,ulong,ulong *)
0x1800050ea  mov     [rbp+57h+var_A8], eax
0x1800050ed  mov     r12d, eax
0x1800050f0  cmp     eax, 3AFCh
0x1800050f5  jz      loc_1800056D6
0x1800050fb  cmp     eax, 3B01h
0x180005100  jz      loc_1800056D6
0x180005106  test    r12d, r12d
0x180005109  jnz     loc_18000555A
0x18000510f  cmp     r12d, 8
0x180005113  jz      loc_180005902
0x180005119  mov     r14, [rbp+57h+var_50]
0x18000511d  cmp     r12d, 3AFCh
0x180005124  mov     r12d, [rbp+57h+var_5C]
0x180005128  mov     eax, [rbp+57h+var_A8]
0x18000512b  mov     [rbp+57h+arg_0], r13d
0x18000512f  mov     r13d, dword ptr [rbp+57h+Size]
0x180005133  jz      loc_1800052A3
0x180005139  cmp     eax, 3B01h
0x18000513e  jz      loc_1800052A3
0x180005144  mov     sil, 1
0x180005147  test    eax, eax
0x180005149  jnz     loc_180005299
0x18000514f  mov     rdi, [rbp+57h+hMem]
0x180005153  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000515a  nop     word ptr [rax+rax+00h]
0x180005160  cmp     word ptr [rdi+rax*2+2], 0
0x180005166  lea     rax, [rax+1]
0x18000516a  jnz     short loc_180005160
0x18000516c  mov     rdx, qword ptr [rbp+57h+Size+4]
0x180005170  lea     ecx, [r13+14h]
0x180005174  lea     ecx, [rcx+rax*2]
0x180005177  mov     [rbp+57h+var_98], ecx
0x18000517a  cmp     ecx, edx
0x18000517c  jnb     loc_1800055A8
0x180005182  mov     r9d, [rbp+57h+var_AC]
0x180005186  lea     r8, aD; "%d"
0x18000518d  mov     rbx, r13
0x180005190  sub     edx, r13d; unsigned __int64
0x180005193  add     rbx, [rbp+57h+Src]
0x180005197  mov     rcx, rbx; unsigned __int16 *
0x18000519a  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000519f  add     [rbp+57h+var_AC], 2
0x1800051a3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800051aa  nop     word ptr [rax+rax+00h]
0x1800051b0  cmp     word ptr [rbx+rax*2+2], 0
0x1800051b6  lea     rax, [rax+1]
0x1800051ba  jnz     short loc_1800051B0
0x1800051bc  mov     r9d, dword ptr [rbp+57h+Size+4]
0x1800051c0  lea     r11d, [r13+2]
0x1800051c4  mov     r10, [rbp+57h+Src]
0x1800051c8  lea     r11d, [r11+rax*2]
0x1800051cc  mov     ecx, r11d
0x1800051cf  sub     r9d, r11d
0x1800051d2  add     r10, rcx
0x1800051d5  shr     r9, 1
0x1800051d8  jz      short loc_180005217
0x1800051da  mov     ecx, 7FFFFFFEh
0x1800051df  mov     rdx, rdi
0x1800051e2  mov     r8, r10
0x1800051e5  test    rcx, rcx
0x1800051e8  jz      short loc_180005207
0x1800051ea  movzx   eax, word ptr [rdx]
0x1800051ed  test    ax, ax
0x1800051f0  jz      short loc_180005207
0x1800051f2  mov     [r8], ax
0x1800051f6  add     rdx, 2
0x1800051fa  add     r8, 2
0x1800051fe  dec     rcx
0x180005201  sub     r9, 1
0x180005205  jnz     short loc_1800051E5
0x180005207  test    r9, r9
0x18000520a  lea     rcx, [r8-2]
0x18000520e  cmovnz  rcx, r8
0x180005212  xor     eax, eax
0x180005214  mov     [rcx], ax
0x180005217  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000521e  xchg    ax, ax
0x180005220  cmp     word ptr [r10+rax*2+2], 0
0x180005227  lea     rax, [rax+1]
0x18000522b  jnz     short loc_180005220
0x18000522d  lea     r13d, [rax+1]
0x180005231  movzx   eax, [rbp+57h+var_B0]
0x180005235  lea     r13d, [r11+r13*2]
0x180005239  mov     dword ptr [rbp+57h+Size], r13d
0x18000523d  cmp     [rbp+57h+var_AE], 9
0x180005242  jnz     loc_18000554B
0x180005248  movzx   eax, al
0x18000524b  xor     eax, 1
0x18000524e  lea     ebx, ds:6[rax*4]
0x180005255  mov     eax, dword ptr [rbp+57h+var_80]
0x180005258  mov     r8d, ebx; enum _PerfRegInfoType
0x18000525b  mov     r9d, [rbp+57h+arg_0]; unsigned int
0x18000525f  sub     eax, edi
0x180005261  mov     edi, eax
0x180005263  mov     rdx, r15; struct _GUID *
0x180005266  lea     rax, [rbp+57h+var_98]
0x18000526a  xor     ecx, ecx; unsigned __int8
0x18000526c  mov     [rsp+30h], rax; unsigned int *
0x180005271  mov     rax, [rbp+57h+hMem]
0x180005275  mov     [rsp+0F0h+var_C8], edi; unsigned int
0x180005279  mov     [rsp+0F0h+var_D0], rax; unsigned __int8 *
0x18000527e  call    ?PerflibciLocalQueryCounterSetRegInfoEx@@YAKEPEBU_GUID@@W4_PerfRegInfoType@@KPEAEKPEAK@Z; PerflibciLocalQueryCounterSetRegInfoEx(uchar,_GUID const *,_PerfRegInfoType,ulong,uchar *,ulong,ulong *)
0x180005283  mov     [rbp+57h+var_A8], eax
0x180005286  mov     edx, eax
0x180005288  test    eax, eax
0x18000528a  jnz     loc_1800055DD
0x180005290  cmp     edx, 8
0x180005293  jz      loc_1800055E6
0x180005299  mov     edx, [rbp+57h+var_AC]
0x18000529c  movzx   r8d, [rbp+57h+var_B0]
0x1800052a1  jmp     short loc_1800052BA
0x1800052a3  test    eax, eax
0x1800052a5  jz      loc_18000596E
0x1800052ab  movzx   r8d, [rbp+57h+var_B0]
0x1800052b0  mov     edx, [rbp+57h+var_AC]
0x1800052b3  movzx   esi, r8b
0x1800052b7  mov     [rbp+57h+var_AC], edx
0x1800052ba  mov     r9d, [rbp+57h+arg_0]
0x1800052be  mov     r15d, [rbp+57h+var_A8]
0x1800052c2  movzx   ebx, [rbp+57h+arg_8]
0x1800052c6  cmp     r15d, 3AFCh
0x1800052cd  jnz     short loc_18000532F
0x1800052cf  test    r8b, r8b
0x1800052d2  jnz     short loc_18000531C
0x1800052d4  mov     rdi, [rbp+57h+Src]
0x1800052d8  mov     r13d, r12d
0x1800052db  mov     dword ptr [rbp+57h+Size], r12d
0x1800052df  mov     edx, 9
0x1800052e4  mov     r14, [rbp+57h+var_58]
0x1800052e8  mov     r14, [r14+18h]
0x1800052ec  mov     [rbp+57h+var_58], r14
0x1800052f0  test    bl, bl
0x1800052f2  jz      loc_18000562C
0x1800052f8  movzx   esi, [rbp+57h+var_B0]
0x1800052fc  movzx   ecx, [rbp+57h+var_AE]
0x180005300  jmp     loc_180005073
0x180005305  mov     rcx, qword ptr [rbp+57h+Size+4]
0x180005309  mov     qword ptr [rbp+57h+Size+4], rcx
0x18000530d  mov     [rbp+57h+Src], rdi
0x180005311  mov     dword ptr [rbp+57h+Size], r13d
0x180005315  mov     [rbp+57h+arg_0], r9d
0x180005319  mov     [rbp+57h+arg_8], bl
0x18000531c  test    sil, sil
0x18000531f  jz      short loc_1800052D4
0x180005321  mov     rdi, [rbp+57h+Src]
0x180005325  test    r15d, r15d
0x180005328  jnz     short loc_1800052DF
0x18000532a  inc     [rbp+57h+var_6C]
0x18000532d  jmp     short loc_1800052DF
0x18000532f  mov     rdi, [rbp+57h+Src]
0x180005333  mov     [rbp+57h+Src], rdi
0x180005337  mov     [rbp+57h+arg_8], bl
0x18000533a  mov     [rbp+57h+arg_0], r9d
0x18000533e  mov     dword ptr [rbp+57h+Size], r13d
0x180005342  cmp     r15d, 3B01h
0x180005349  jz      loc_180005A12
0x18000534f  test    r15d, r15d
0x180005352  jnz     short loc_180005305
0x180005354  test    sil, sil
0x180005357  jz      loc_1800059FA
0x18000535d  mov     rsi, [rbp+57h+hMem]
0x180005361  mov     ecx, [rsi+4]
0x180005364  cmp     ecx, [r14+80h]
0x18000536b  jnz     loc_180005878
  ... truncated ...
```
