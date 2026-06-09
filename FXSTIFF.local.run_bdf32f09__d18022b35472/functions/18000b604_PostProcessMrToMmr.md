# PostProcessMrToMmr

- ea: `0x18000b604`
- end: `0x18000c19d`
- name: `PostProcessMrToMmr`
- size: `2969`
- prototype: `__int64 __fastcall(WCHAR *, unsigned int *, WCHAR *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x180009070`
- `0x18000d310`

## callees

- `0x1800052e0`
- `0x180007cd0`
- `0x180007d60`
- `0x180008060`
- `0x1800091a0`
- `0x180009860`
- `0x180009a20`
- `0x180009a7c`
- `0x180009aa4`
- `0x180009c1c`
- `0x18000a560`
- `0x18000a88c`
- `0x18000b604`
- `0x18000c1a4`
- `0x180017bce`
- `0x180017c00`
- `0x180017c90`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18000b7ec`
- `KERNEL32!DeleteFileW` at `0x18000c14a`
- `KERNEL32!DeleteFileW` at `0x18000c16b`
- `KERNEL32!DeleteFileW` at `0x18000b7ec`
- `KERNEL32!DeleteFileW` at `0x18000c14a`
- `KERNEL32!DeleteFileW` at `0x18000c16b`
- `KERNEL32!SetLastError` at `0x18000b7d9`
- `KERNEL32!SetLastError` at `0x18000b890`
- `KERNEL32!SetLastError` at `0x18000b7d9`
- `KERNEL32!SetLastError` at `0x18000b890`
- `KERNEL32!VirtualAlloc` at `0x18000b919`
- `KERNEL32!VirtualAlloc` at `0x18000b93a`
- `KERNEL32!VirtualAlloc` at `0x18000ba2e`
- `KERNEL32!VirtualAlloc` at `0x18000ba53`
- `KERNEL32!VirtualAlloc` at `0x18000b919`
- `KERNEL32!VirtualAlloc` at `0x18000b93a`
- `KERNEL32!VirtualAlloc` at `0x18000ba2e`
- `KERNEL32!VirtualAlloc` at `0x18000ba53`
- `KERNEL32!VirtualFree` at `0x18000b9ee`
- `KERNEL32!VirtualFree` at `0x18000ba01`
- `KERNEL32!VirtualFree` at `0x18000c0f2`
- `KERNEL32!VirtualFree` at `0x18000c108`
- `KERNEL32!VirtualFree` at `0x18000b9ee`
- `KERNEL32!VirtualFree` at `0x18000ba01`
- `KERNEL32!VirtualFree` at `0x18000c0f2`
- `KERNEL32!VirtualFree` at `0x18000c108`
- `KERNEL32!MoveFileW` at `0x18000c15b`
- `KERNEL32!MoveFileW` at `0x18000c15b`
- `KERNEL32!GetTempPath2W` at `0x18000b70a`
- `KERNEL32!GetTempPath2W` at `0x18000b70a`
- `KERNEL32!GetTempFileNameW` at `0x18000b72d`
- `KERNEL32!GetTempFileNameW` at `0x18000b72d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PostProcessMrToMmr(WCHAR *a1, unsigned int *a2, WCHAR *a3)
{
  WCHAR *v3; // r15
  _QWORD *v6; // r10
  __int64 v7; // rsi
  __int64 v8; // rdi
  int v9; // r12d
  WCHAR *v10; // rax
  WCHAR *v11; // rdx
  WCHAR *v12; // rcx
  unsigned int v13; // ebx
  DWORD v14; // ecx
  __int64 v15; // rax
  WCHAR *v16; // r8
  WCHAR *v17; // rcx
  __int64 v18; // rdx
  WCHAR *v19; // rcx
  unsigned int v20; // ebx
  DWORD v21; // ecx
  unsigned int v23; // ebx
  BOOL v24; // eax
  _DWORD *v25; // r13
  unsigned __int64 v26; // r15
  void *v27; // rbx
  unsigned int v28; // eax
  _DWORD *v29; // rdi
  unsigned int v30; // esi
  int started; // eax
  unsigned __int64 v32; // r14
  unsigned __int64 v33; // rbx
  unsigned int v34; // edi
  unsigned int v35; // edi
  unsigned __int64 v36; // rax
  unsigned __int64 v37; // rbx
  _DWORD *v38; // rdi
  unsigned __int8 v39; // bl
  char *v40; // r10
  unsigned __int64 v41; // r8
  unsigned __int16 v42; // r14
  int v43; // edx
  int v44; // eax
  unsigned __int8 v45; // bl
  int MrLine; // eax
  __int64 *v47; // r9
  int v48; // eax
  int v49; // eax
  int v50; // esi
  unsigned __int8 v51; // bl
  int v52; // esi
  unsigned __int16 v53; // r11
  unsigned __int8 v54; // dl
  unsigned __int8 v55; // cl
  int v56; // edx
  char *v57; // rdx
  unsigned int v58; // ecx
  int v59; // ebx
  int v60; // eax
  char v61; // al
  char v62; // al
  int v63; // eax
  __int16 *v64; // rax
  int NextEol; // eax
  unsigned __int8 v66; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v67[3]; // [rsp+41h] [rbp-BFh] BYREF
  int v68; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int dwSize; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int dwSize_4; // [rsp+4Ch] [rbp-B4h]
  __int16 *v71; // [rsp+50h] [rbp-B0h]
  __int16 *v72; // [rsp+58h] [rbp-A8h]
  LPVOID v73; // [rsp+60h] [rbp-A0h]
  int v74; // [rsp+68h] [rbp-98h]
  unsigned __int64 v75; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpAddress; // [rsp+78h] [rbp-88h]
  int v77; // [rsp+80h] [rbp-80h]
  unsigned __int64 v78; // [rsp+88h] [rbp-78h] BYREF
  size_t Size; // [rsp+90h] [rbp-70h]
  unsigned __int64 v80; // [rsp+98h] [rbp-68h]
  WCHAR *v81; // [rsp+A0h] [rbp-60h]
  LPVOID lpMem; // [rsp+A8h] [rbp-58h]
  unsigned int v83; // [rsp+B0h] [rbp-50h]
  unsigned int v84; // [rsp+B4h] [rbp-4Ch]
  __int64 v85; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v86; // [rsp+C0h] [rbp-40h]
  WCHAR TempFileName[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR FileName[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR PathName[264]; // [rsp+4F0h] [rbp+3F0h] BYREF
  __int16 v90; // [rsp+700h] [rbp+600h] BYREF
  char v91[3470]; // [rsp+702h] [rbp+602h] BYREF
  __int16 v92; // [rsp+1490h] [rbp+1390h] BYREF
  char v93[3470]; // [rsp+1492h] [rbp+1392h] BYREF

  v3 = a3;
  v81 = a3;
  lpMem = a1;
  memset_0(TempFileName, 0, 0x208u);
  memset_0(PathName, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  memset_0(v91, 0, 0xD84u);
  memset_0(v93, 0, 0xD84u);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = 2147483646;
  v8 = 260;
  v9 = 1;
  if ( v3 )
  {
    v15 = 2147483646;
    v16 = TempFileName;
    v17 = v3;
    v18 = 260;
    do
    {
      if ( !v15 )
        break;
      if ( !*v17 )
        break;
      *v16++ = *v17++;
      --v15;
      --v18;
    }
    while ( v18 );
    v19 = v16 - 1;
    v20 = v18 == 0 ? 0x8007007A : 0;
    if ( v18 )
      v19 = v16;
    *v19 = 0;
    if ( !v18 )
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_d(v6[2], 38, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids, v20);
      v21 = (unsigned __int16)v20;
      if ( (v20 & 0x1FFF0000) != 0x70000 )
        v21 = v20;
      SetLastError(v21);
      return 0;
    }
  }
  else
  {
    if ( !(unsigned int)GetTempPath2W(259, PathName) || !GetTempFileNameW(PathName, L"Fxs", 0, TempFileName) )
      return 0;
    v6 = WPP_GLOBAL_Control;
  }
  v10 = a1 + 22;
  v11 = FileName;
  do
  {
    if ( !v7 )
      break;
    if ( !*v10 )
      break;
    *v11++ = *v10++;
    --v7;
    --v8;
  }
  while ( v8 );
  v12 = v11 - 1;
  v13 = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v12 = v11;
  *v12 = 0;
  if ( !v8 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_d(v6[2], 39, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids, v13);
    v14 = (unsigned __int16)v13;
    if ( (v8 == 0 ? 0x70000 : 0) != 0x70000 )
      v14 = v8 == 0 ? 0x8007007A : 0;
    SetLastError(v14);
    if ( !v3 )
      DeleteFileW(TempFileName);
    return 0;
  }
  v23 = 0;
  v24 = a2[7] == 196;
  v77 = 0;
  v25 = (_DWORD *)TiffCreate(TempFileName, v24);
  if ( !v25 )
    goto LABEL_145;
  v26 = 2400 * ((unsigned __int64)*a2 >> 3);
  if ( v26 > 0xFFFFFFFF )
    goto LABEL_144;
  LODWORD(Size) = v26 + 200000;
  if ( (int)v26 + 200000 < (unsigned int)v26 )
    goto LABEL_144;
  lpAddress = VirtualAlloc(0, (unsigned int)v26, 0x1000u, 4u);
  if ( !lpAddress )
    goto LABEL_144;
  v73 = VirtualAlloc(0, (unsigned int)(v26 + 200000), 0x1000u, 4u);
  v27 = v73;
  if ( !v73 )
  {
    v32 = (unsigned __int64)lpAddress;
    goto LABEL_140;
  }
  v28 = 0;
  v84 = a2[2];
  if ( !v84 )
    goto LABEL_98;
  v29 = lpMem;
  do
  {
    v83 = v28 + 1;
    if ( !(unsigned int)TiffSeekToPage(v29, v28 + 1, 2) )
      goto LABEL_99;
    v30 = v29[391];
    dwSize_4 = v30;
    started = TiffStartPage(v25);
    v32 = (unsigned __int64)lpAddress;
    if ( !started )
      goto LABEL_136;
    dwSize = v26;
    v33 = (unsigned __int64)lpAddress & 0xFFFFFFFFFFFFFFFCuLL;
    v75 = (unsigned __int64)lpAddress & 0xFFFFFFFFFFFFFFFCuLL;
    v34 = (unsigned int)lpAddress & 0xFFFFFFFC;
    if ( !(unsigned int)GetTiffBits(lpMem, (unsigned __int64)lpAddress & 0xFFFFFFFFFFFFFFFCuLL, &dwSize) )
    {
      if ( dwSize <= (unsigned int)v26 )
        goto LABEL_135;
      VirtualFree((LPVOID)v32, 0, 0x8000u);
      v27 = v73;
      VirtualFree(v73, 0, 0x8000u);
      LODWORD(v26) = dwSize;
      v35 = dwSize + 200000;
      LODWORD(Size) = dwSize + 200000;
      if ( dwSize + 200000 < dwSize )
        goto LABEL_136;
      lpAddress = VirtualAlloc(0, dwSize, 0x1000u, 4u);
      v32 = (unsigned __int64)lpAddress;
      if ( !lpAddress )
        goto LABEL_141;
      v73 = VirtualAlloc(0, v35, 0x1000u, 4u);
      v27 = v73;
      if ( !v73 )
        goto LABEL_140;
      v33 = v32 & 0xFFFFFFFFFFFFFFFCuLL;
      v75 = v32 & 0xFFFFFFFFFFFFFFFCuLL;
      v34 = v32 & 0xFFFFFFFC;
      if ( !(unsigned int)GetTiffBits(lpMem, v32 & 0xFFFFFFFFFFFFFFFCuLL, &dwSize) )
      {
        v27 = v73;
        goto LABEL_140;
      }
    }
    v66 = 0;
    v67[0] = 0;
    v36 = v33 + 4 * ((unsigned __int64)dwSize >> 2);
    v37 = (unsigned int)Size;
    v80 = v36;
    v86 = (unsigned __int64)v73 & 0xFFFFFFFFFFFFFFFCuLL;
    v78 = (unsigned __int64)v73 & 0xFFFFFFFFFFFFFFFCuLL;
    memset_0((void *)((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFFCuLL), 0, (unsigned int)Size);
    v90 = v30;
    if ( !(unsigned int)FindNextEol(v34, 0, v80, (unsigned int)&v75, (__int64)&v66, 0, (__int64)&v68) )
      goto LABEL_135;
    v92 = v30;
    v85 = v86 + 4 * (v37 >> 2);
    if ( !(unsigned int)OutputMmrLine(
                          v86,
                          0,
                          (unsigned int)&v92,
                          (unsigned int)&v90,
                          (__int64)&v78,
                          (__int64)v67,
                          v85,
                          v30) )
      goto LABEL_135;
    v38 = (_DWORD *)v75;
    v39 = v66;
    v40 = (char *)&v90;
    v41 = (unsigned __int64)&v92;
    v72 = &v90;
    v71 = &v92;
    v42 = 0;
    v74 = 1;
    v43 = 0;
    dwSize = 1;
    while ( 1 )
    {
      v44 = *v38 & (1 << v39);
      if ( v9 )
        break;
      if ( v44 )
        goto LABEL_72;
      v45 = v39 + 1;
      v66 = v45;
      if ( v45 > 0x1Fu )
      {
        v75 = (unsigned __int64)(v38 + 1);
        v66 = v45 - 32;
      }
      v68 = 0;
      MrLine = ReadMrLine((unsigned int)&v75, (unsigned int)&v66, (_DWORD)v40, v41, v80 - 4, 0, v30);
      v47 = 0;
      if ( MrLine )
      {
        v48 = MrLine - 1;
        if ( v48 )
        {
          v49 = v48 - 1;
          if ( !v49 )
            goto LABEL_95;
          if ( v49 != 1 )
            goto LABEL_134;
        }
        v9 = 1;
        v50 = 0;
        v42 = 0;
      }
      else
      {
        v42 = dwSize_4;
        ++dwSize;
        v50 = 1;
        v9 = 0;
      }
      LODWORD(v38) = v75;
      v51 = v66;
LABEL_123:
      v43 = v68;
LABEL_124:
      LODWORD(v40) = (_DWORD)v72;
      LODWORD(v41) = (_DWORD)v71;
LABEL_125:
      if ( v42 == dwSize_4 && !v43 )
      {
        if ( !(unsigned int)OutputMmrLine(v78, v67[0], v41, (_DWORD)v40, (__int64)&v78, (__int64)v67, v85, dwSize_4) )
          goto LABEL_134;
        v64 = v72;
        v72 = v71;
        v71 = v64;
      }
      LOBYTE(v43) = v51;
      NextEol = FindNextEol((_DWORD)v38, v43, v80, (unsigned int)&v75, (__int64)&v66, v50, (__int64)&v68);
      v30 = dwSize_4;
      v47 = 0;
      if ( !NextEol )
        goto LABEL_95;
      v38 = (_DWORD *)v75;
      v39 = v66;
      v42 = 0;
      v43 = 0;
LABEL_131:
      v41 = (unsigned __int64)v71;
      LODWORD(v40) = (_DWORD)v72;
LABEL_132:
      if ( (unsigned __int64)v38 > v80 )
        goto LABEL_95;
    }
    if ( !v44 )
    {
      v51 = v39 + 1;
      v66 = v51;
      if ( v51 > 0x1Fu )
      {
        ++v38;
        v51 -= 32;
        v75 = (unsigned __int64)v38;
        v66 = v51;
      }
      v50 = 0;
      v9 = 1;
      goto LABEL_125;
    }
LABEL_72:
    v51 = v39 + 1;
    v66 = v51;
    if ( v51 > 0x1Fu )
    {
      ++v38;
      v51 -= 32;
      v75 = (unsigned __int64)v38;
      v66 = v51;
    }
    v68 = 0;
    v42 = 0;
    v52 = 0;
    v53 = 0;
    v47 = gc_GlobTableWhite;
    v54 = v51;
    v55 = v51;
    while ( 2 )
    {
      if ( v55 > 0x11u )
        LOWORD(v56) = (*v38 >> v55) + (v38[1] << (32 - v54));
      else
        v56 = *v38 >> v55;
      v57 = (char *)v47 + 5 * (v56 & 0x7FFFu);
      v47 = 0;
      v41 = 0;
      v40 = v57 + 4;
LABEL_79:
      v58 = *v57 & 0x3F;
      if ( *v57 >= 0 )
      {
        v42 += v58;
        if ( v42 > dwSize_4 )
          goto LABEL_122;
        v71[v53++] = v42;
        if ( v53 >= 0x6C3u )
          goto LABEL_134;
        v47 = 0;
        v68 = 0;
        v52 = 1 - v52;
LABEL_86:
        ++v57;
        v41 = (unsigned int)(v41 + 1);
        if ( (unsigned int)v41 >= 4 )
        {
LABEL_89:
          v47 = GlobTableBlack;
          if ( !v52 )
            v47 = gc_GlobTableWhite;
          v51 += *v40 & 0xF;
          v66 = v51;
          v55 = v51;
          if ( v51 > 0x1Fu )
          {
            v51 -= 32;
            v75 = (unsigned __int64)++v38;
            v55 = v51;
            v66 = v51;
          }
          v54 = v51;
          if ( (unsigned __int64)v38 > v80 )
          {
            v30 = dwSize_4;
            goto LABEL_95;
          }
          continue;
        }
        goto LABEL_79;
      }
      break;
    }
    if ( v58 <= 0x28 )
    {
      v42 += (_WORD)v58 << 6;
      if ( v42 > dwSize_4 )
        goto LABEL_122;
      v74 = 0;
      v68 = 1;
      goto LABEL_86;
    }
    if ( v58 == 53 )
      goto LABEL_89;
    if ( v58 != 51 )
    {
      if ( v58 != 52 )
      {
        if ( v58 != 50 )
          goto LABEL_134;
LABEL_122:
        v50 = 0;
        v9 = 1;
        goto LABEL_123;
      }
      v39 = (*v40 & 0xF) + v51;
      if ( v39 > 0x1Fu )
      {
        v75 = (unsigned __int64)++v38;
        v39 -= 32;
      }
      v30 = dwSize_4;
      if ( v42 != dwSize_4 || v68 )
      {
        if ( v42 || (v41 = (unsigned int)(v74 + 1), v74 = v41, (unsigned int)v41 < 5) )
        {
          v43 = v68;
          v9 = 1;
          goto LABEL_131;
        }
        goto LABEL_95;
      }
      LOBYTE(v57) = v67[0];
      v63 = OutputMmrLine(v78, (_DWORD)v57, (_DWORD)v71, (_DWORD)v72, (__int64)&v78, (__int64)v67, v85, dwSize_4);
      v47 = 0;
      if ( !v63 )
        goto LABEL_134;
      LODWORD(v40) = (_DWORD)v71;
      v41 = (unsigned __int64)v72;
      ++dwSize;
      v9 = 0;
      v43 = v68;
      v72 = v71;
      v71 = (__int16 *)v41;
      v74 = 0;
      goto LABEL_132;
    }
    v30 = dwSize_4;
    v43 = v68;
    if ( v42 == dwSize_4 && !v68 )
    {
      v61 = *v40;
      ++dwSize;
      v51 += v61 & 0xF;
      v74 = 0;
      v66 = v51;
      v9 = 0;
      v50 = 1;
      if ( v51 > 0x1Fu )
      {
        ++v38;
        v51 -= 32;
        v75 = (unsigned __int64)v38;
        v66 = v51;
      }
      goto LABEL_124;
    }
    if ( v42 )
    {
      v9 = 1;
      v50 = 0;
      goto LABEL_124;
    }
    v41 = (unsigned int)(v74 + 1);
    v74 = v41;
    if ( (unsigned int)v41 < 5 )
    {
      LODWORD(v41) = (_DWORD)v71;
      v9 = 1;
      v50 = 1;
      v62 = *v40;
      LODWORD(v40) = (_DWORD)v72;
      v51 += v62 & 0xF;
      v66 = v51;
      if ( v51 > 0x1Fu )
      {
        ++v38;
        v51 -= 32;
        v75 = (unsigned __int64)v38;
        v66 = v51;
      }
      goto LABEL_125;
    }
LABEL_95:
    v59 = v78;
    CheckAndAddOutput(v78, v85, v41, v47);
    if ( !(unsigned int)TiffWriteRaw(v25, v86, (v59 - (_DWORD)v86) & 0xFFFFFFFC) )
    {
LABEL_134:
      v32 = (unsigned __int64)lpAddress;
LABEL_135:
      v27 = v73;
      goto LABEL_136;
    }
    v29 = lpMem;
    v25[212] = dwSize - 1;
    v25[391] = v30;
    v25[421] = v29[421];
    v60 = TiffEndPage(v25);
    v27 = v73;
    if ( !v60 )
      goto LABEL_99;
    v28 = v83;
  }
  while ( v83 < v84 );
LABEL_98:
  v77 = 1;
LABEL_99:
  v32 = (unsigned __int64)lpAddress;
LABEL_136:
  if ( v32 )
LABEL_140:
    VirtualFree((LPVOID)v32, 0, 0x8000u);
LABEL_141:
  if ( v27 )
    VirtualFree(v27, 0, 0x8000u);
  v23 = v77;
LABEL_144:
  v3 = v81;
LABEL_145:
  if ( lpMem )
    TiffClose(lpMem);
  if ( v25 )
    TiffClose(v25);
  if ( v23 == 1 )
  {
    if ( !v3 )
    {
      DeleteFileW(FileName);
      v23 = MoveFileW(TempFileName, FileName);
      goto LABEL_152;
    }
  }
  else
  {
LABEL_152:
    if ( !v23 )
      DeleteFileW(TempFileName);
  }
  return v23;
}

```

## disassembly

```asm
0x18000b604  mov     [rsp-8+arg_10], rbx
0x18000b609  push    rbp
0x18000b60a  push    rsi
0x18000b60b  push    rdi
0x18000b60c  push    r12
0x18000b60e  push    r13
0x18000b610  push    r14
0x18000b612  push    r15
0x18000b614  lea     rbp, [rsp-2130h]
0x18000b61c  mov     eax, 2230h
0x18000b621  call    _alloca_probe
0x18000b626  sub     rsp, rax
0x18000b629  mov     rax, cs:__security_cookie
0x18000b630  xor     rax, rsp
0x18000b633  mov     [rbp+2160h+var_40], rax
0x18000b63a  mov     r15, r8
0x18000b63d  mov     [rbp+2160h+var_21C0], r8
0x18000b641  mov     r14, rdx
0x18000b644  mov     [rbp+2160h+lpMem], rcx
0x18000b648  mov     r13, rcx
0x18000b64b  mov     ebx, 208h
0x18000b650  mov     r8d, ebx; Size
0x18000b653  lea     rcx, [rbp+2160h+TempFileName]; void *
0x18000b657  xor     edx, edx; Val
0x18000b659  call    memset_0
0x18000b65e  mov     r8d, ebx; Size
0x18000b661  lea     rcx, [rbp+2160h+PathName]; void *
0x18000b668  xor     edx, edx; Val
0x18000b66a  call    memset_0
0x18000b66f  mov     r8d, ebx; Size
0x18000b672  lea     rcx, [rbp+2160h+FileName]; void *
0x18000b679  xor     edx, edx; Val
0x18000b67b  call    memset_0
0x18000b680  mov     ebx, 0D84h
0x18000b685  lea     rcx, [rbp+2160h+var_1B5E]; void *
0x18000b68c  mov     r8d, ebx; Size
0x18000b68f  xor     edx, edx; Val
0x18000b691  call    memset_0
0x18000b696  mov     r8d, ebx; Size
0x18000b699  lea     rcx, [rbp+2160h+var_DCE]; void *
0x18000b6a0  xor     edx, edx; Val
0x18000b6a2  call    memset_0
0x18000b6a7  mov     r10, cs:WPP_GLOBAL_Control
0x18000b6ae  lea     rax, WPP_GLOBAL_Control
0x18000b6b5  cmp     r10, rax
0x18000b6b8  jz      short loc_18000B6E4
0x18000b6ba  test    byte ptr [r10+1Ch], 2
0x18000b6bf  jz      short loc_18000B6E4
0x18000b6c1  cmp     byte ptr [r10+19h], 5
0x18000b6c6  jb      short loc_18000B6E4
0x18000b6c8  mov     rcx, [r10+10h]
0x18000b6cc  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000b6d3  mov     edx, 25h ; '%'
0x18000b6d8  call    WPP_SF_
0x18000b6dd  mov     r10, cs:WPP_GLOBAL_Control
0x18000b6e4  xor     r11d, r11d
0x18000b6e7  mov     esi, 7FFFFFFEh
0x18000b6ec  mov     edi, 104h
0x18000b6f1  mov     r12d, 1
0x18000b6f7  test    r15, r15
0x18000b6fa  jnz     loc_18000B7F7
0x18000b700  lea     rdx, [rbp+2160h+PathName]
0x18000b707  lea     ecx, [rdi-1]
0x18000b70a  call    cs:__imp_GetTempPath2W
0x18000b710  xor     r8d, r8d; uUnique
0x18000b713  test    eax, eax
0x18000b715  jz      loc_18000B896
0x18000b71b  lea     r9, [rbp+2160h+TempFileName]; lpTempFileName
0x18000b71f  lea     rdx, PrefixString; "Fxs"
0x18000b726  lea     rcx, [rbp+2160h+PathName]; lpPathName
0x18000b72d  call    cs:__imp_GetTempFileNameW
0x18000b733  xor     r11d, r11d
0x18000b736  test    eax, eax
0x18000b738  jz      loc_18000B896
0x18000b73e  mov     r10, cs:WPP_GLOBAL_Control
0x18000b745  lea     rax, [r13+2Ch]
0x18000b749  lea     rdx, [rbp+2160h+FileName]
0x18000b750  test    rsi, rsi
0x18000b753  jz      short loc_18000B770
0x18000b755  movzx   ecx, word ptr [rax]
0x18000b758  test    cx, cx
0x18000b75b  jz      short loc_18000B770
0x18000b75d  mov     [rdx], cx
0x18000b760  add     rax, 2
0x18000b764  add     rdx, 2
0x18000b768  sub     rsi, r12
0x18000b76b  sub     rdi, r12
0x18000b76e  jnz     short loc_18000B750
0x18000b770  mov     rax, rdi
0x18000b773  lea     rcx, [rdx-2]
0x18000b777  neg     rax
0x18000b77a  sbb     ebx, ebx
0x18000b77c  not     ebx
0x18000b77e  and     ebx, 8007007Ah
0x18000b784  test    rdi, rdi
0x18000b787  cmovnz  rcx, rdx
0x18000b78b  mov     [rcx], r11w
0x18000b78f  jnz     loc_18000B89D
0x18000b795  lea     rax, WPP_GLOBAL_Control
0x18000b79c  cmp     r10, rax
0x18000b79f  jz      short loc_18000B7C7
0x18000b7a1  test    byte ptr [r10+1Ch], 2
0x18000b7a6  jz      short loc_18000B7C7
0x18000b7a8  cmp     byte ptr [r10+19h], 2
0x18000b7ad  jb      short loc_18000B7C7
0x18000b7af  mov     rcx, [r10+10h]
0x18000b7b3  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000b7ba  mov     edx, 27h ; '''
0x18000b7bf  mov     r9d, ebx
0x18000b7c2  call    WPP_SF_d
0x18000b7c7  mov     eax, ebx
0x18000b7c9  movzx   ecx, bx
0x18000b7cc  and     eax, 1FFF0000h
0x18000b7d1  cmp     eax, 70000h
0x18000b7d6  cmovnz  ecx, ebx; dwErrCode
0x18000b7d9  call    cs:__imp_SetLastError
0x18000b7df  test    r15, r15
0x18000b7e2  jnz     loc_18000B896
0x18000b7e8  lea     rcx, [rbp+2160h+TempFileName]; lpFileName
0x18000b7ec  call    cs:__imp_DeleteFileW
0x18000b7f2  jmp     loc_18000B896
0x18000b7f7  mov     rax, rsi
0x18000b7fa  lea     r8, [rbp+2160h+TempFileName]
0x18000b7fe  mov     rcx, r15
0x18000b801  mov     rdx, rdi
0x18000b804  test    rax, rax
0x18000b807  jz      short loc_18000B827
0x18000b809  movzx   r9d, word ptr [rcx]
0x18000b80d  test    r9w, r9w
0x18000b811  jz      short loc_18000B827
0x18000b813  mov     [r8], r9w
0x18000b817  add     rcx, 2
0x18000b81b  add     r8, 2
0x18000b81f  sub     rax, r12
0x18000b822  sub     rdx, r12
0x18000b825  jnz     short loc_18000B804
0x18000b827  mov     rax, rdx
0x18000b82a  lea     rcx, [r8-2]
0x18000b82e  neg     rax
0x18000b831  sbb     ebx, ebx
0x18000b833  not     ebx
0x18000b835  and     ebx, 8007007Ah
0x18000b83b  test    rdx, rdx
0x18000b83e  cmovnz  rcx, r8
0x18000b842  mov     [rcx], r11w
0x18000b846  jnz     loc_18000B745
0x18000b84c  lea     rax, WPP_GLOBAL_Control
0x18000b853  cmp     r10, rax
0x18000b856  jz      short loc_18000B87E
0x18000b858  test    byte ptr [r10+1Ch], 2
0x18000b85d  jz      short loc_18000B87E
0x18000b85f  cmp     byte ptr [r10+19h], 2
0x18000b864  jb      short loc_18000B87E
0x18000b866  mov     rcx, [r10+10h]
0x18000b86a  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000b871  mov     edx, 26h ; '&'
0x18000b876  mov     r9d, ebx
0x18000b879  call    WPP_SF_d
0x18000b87e  mov     eax, ebx
0x18000b880  movzx   ecx, bx
0x18000b883  and     eax, 1FFF0000h
0x18000b888  cmp     eax, 70000h
0x18000b88d  cmovnz  ecx, ebx; dwErrCode
0x18000b890  call    cs:__imp_SetLastError
0x18000b896  xor     eax, eax
0x18000b898  jmp     loc_18000C173
0x18000b89d  cmp     dword ptr [r14+1Ch], 0C4h
0x18000b8a5  lea     rcx, [rbp+2160h+TempFileName]; lpFileName
0x18000b8a9  mov     r8d, [r14]
0x18000b8ac  mov     eax, r11d
0x18000b8af  mov     r9d, 2
0x18000b8b5  mov     ebx, r11d
0x18000b8b8  setz    al
0x18000b8bb  mov     [rbp+2160h+var_21E0], ebx
0x18000b8be  mov     [rsp+2260h+var_2240], eax; int
0x18000b8c2  lea     edx, [r9+2]
0x18000b8c6  call    TiffCreate
0x18000b8cb  mov     r13, rax
0x18000b8ce  test    rax, rax
0x18000b8d1  jz      loc_18000C11B
0x18000b8d7  mov     ecx, [r14]
0x18000b8da  mov     eax, 0FFFFFFFFh
0x18000b8df  shr     rcx, 3
0x18000b8e3  imul    r15, rcx, 960h
0x18000b8ea  cmp     r15, rax
0x18000b8ed  ja      loc_18000C117
0x18000b8f3  lea     edi, [r15+30D40h]
0x18000b8fa  mov     dword ptr [rbp+2160h+Size], edi
0x18000b8fd  cmp     edi, r15d
0x18000b900  jb      loc_18000C117
0x18000b906  mov     esi, 1000h
0x18000b90b  mov     edx, r15d; dwSize
0x18000b90e  mov     r8d, esi; flAllocationType
0x18000b911  mov     r9d, 4; flProtect
0x18000b917  xor     ecx, ecx; lpAddress
0x18000b919  call    cs:__imp_VirtualAlloc
0x18000b91f  mov     [rsp+2260h+lpAddress], rax
0x18000b924  test    rax, rax
0x18000b927  jz      loc_18000C117
0x18000b92d  mov     edx, edi; dwSize
0x18000b92f  mov     r9d, 4; flProtect
0x18000b935  mov     r8d, esi; flAllocationType
0x18000b938  xor     ecx, ecx; lpAddress
0x18000b93a  call    cs:__imp_VirtualAlloc
0x18000b940  xor     r9d, r9d
0x18000b943  mov     [rsp+2260h+var_2200], rax
0x18000b948  mov     rbx, rax
0x18000b94b  test    rax, rax
0x18000b94e  jz      loc_18000C0DB
0x18000b954  mov     ecx, [r14+8]
0x18000b958  mov     eax, r9d
0x18000b95b  mov     [rbp+2160h+var_21AC], ecx
0x18000b95e  test    ecx, ecx
0x18000b960  jz      loc_18000BE41
0x18000b966  mov     rdi, [rbp+2160h+lpMem]
0x18000b96a  inc     eax
0x18000b96c  mov     r8d, 2
0x18000b972  mov     edx, eax
0x18000b974  mov     [rbp+2160h+var_21B0], eax
0x18000b977  mov     rcx, rdi
0x18000b97a  call    TiffSeekToPage
0x18000b97f  test    eax, eax
0x18000b981  jz      loc_18000BE48
0x18000b987  mov     esi, [rdi+61Ch]
0x18000b98d  mov     rcx, r13
0x18000b990  mov     dword ptr [rsp+2260h+dwSize+4], esi
0x18000b994  call    TiffStartPage
0x18000b999  mov     r14, [rsp+2260h+lpAddress]
0x18000b99e  test    eax, eax
0x18000b9a0  jz      loc_18000C0D4
0x18000b9a6  mov     rcx, [rbp+2160h+lpMem]
0x18000b9aa  lea     r8, [rsp+2260h+dwSize]
0x18000b9af  mov     rbx, r14
0x18000b9b2  mov     dword ptr [rsp+2260h+dwSize], r15d
0x18000b9b7  and     rbx, 0FFFFFFFFFFFFFFFCh
0x18000b9bb  mov     rdx, rbx
0x18000b9be  mov     [rsp+2260h+var_21F0], rbx
0x18000b9c3  mov     rdi, rbx
0x18000b9c6  call    GetTiffBits
0x18000b9cb  xor     r9d, r9d
0x18000b9ce  test    eax, eax
0x18000b9d0  jnz     loc_18000BA95
0x18000b9d6  cmp     dword ptr [rsp+2260h+dwSize], r15d
0x18000b9db  jbe     loc_18000C0CF
0x18000b9e1  mov     ebx, 8000h
0x18000b9e6  xor     edx, edx; dwSize
0x18000b9e8  mov     r8d, ebx; dwFreeType
0x18000b9eb  mov     rcx, r14; lpAddress
0x18000b9ee  call    cs:__imp_VirtualFree
0x18000b9f4  mov     r8d, ebx; dwFreeType
0x18000b9f7  xor     edx, edx; dwSize
0x18000b9f9  mov     rbx, [rsp+2260h+var_2200]
0x18000b9fe  mov     rcx, rbx; lpAddress
0x18000ba01  call    cs:__imp_VirtualFree
0x18000ba07  mov     r15d, dword ptr [rsp+2260h+dwSize]
0x18000ba0c  lea     edi, [r15+30D40h]
0x18000ba13  mov     dword ptr [rbp+2160h+Size], edi
0x18000ba16  cmp     edi, r15d
0x18000ba19  jb      loc_18000C0D4
0x18000ba1f  xor     ecx, ecx; lpAddress
0x18000ba21  mov     edx, r15d; dwSize
0x18000ba24  mov     r8d, 1000h; flAllocationType
0x18000ba2a  lea     r9d, [rcx+4]; flProtect
0x18000ba2e  call    cs:__imp_VirtualAlloc
0x18000ba34  mov     [rsp+2260h+lpAddress], rax
0x18000ba39  mov     r14, rax
0x18000ba3c  test    rax, rax
0x18000ba3f  jz      loc_18000C0F8
0x18000ba45  xor     ecx, ecx; lpAddress
0x18000ba47  mov     edx, edi; dwSize
0x18000ba49  mov     r8d, 1000h; flAllocationType
0x18000ba4f  lea     r9d, [rcx+4]; flProtect
0x18000ba53  call    cs:__imp_VirtualAlloc
0x18000ba59  mov     [rsp+2260h+var_2200], rax
0x18000ba5e  mov     rbx, rax
0x18000ba61  test    rax, rax
0x18000ba64  jz      loc_18000C0E7
0x18000ba6a  mov     rcx, [rbp+2160h+lpMem]
0x18000ba6e  lea     r8, [rsp+2260h+dwSize]
0x18000ba73  mov     rbx, r14
0x18000ba76  and     rbx, 0FFFFFFFFFFFFFFFCh
0x18000ba7a  mov     rdx, rbx
0x18000ba7d  mov     [rsp+2260h+var_21F0], rbx
0x18000ba82  mov     rdi, rbx
0x18000ba85  call    GetTiffBits
0x18000ba8a  xor     r9d, r9d
0x18000ba8d  test    eax, eax
0x18000ba8f  jz      loc_18000C0E2
0x18000ba95  mov     eax, dword ptr [rsp+2260h+dwSize]
0x18000ba99  xor     edx, edx; Val
0x18000ba9b  shr     rax, 2
0x18000ba9f  mov     [rsp+2260h+var_2220], r9b
0x18000baa4  mov     [rsp+2260h+var_221F], r9b
0x18000baa9  lea     rax, [rbx+rax*4]
0x18000baad  mov     ebx, dword ptr [rbp+2160h+Size]
0x18000bab0  mov     [rbp+2160h+var_21C8], rax
0x18000bab4  mov     r8d, ebx; Size
0x18000bab7  mov     rax, [rsp+2260h+var_2200]
0x18000babc  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000bac0  mov     rcx, rax; void *
  ... truncated ...
```
