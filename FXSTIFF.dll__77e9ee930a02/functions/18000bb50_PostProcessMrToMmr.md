# PostProcessMrToMmr

- ea: `0x18000bb50`
- end: `0x18000c74a`
- name: `PostProcessMrToMmr`
- size: `3066`
- prototype: `__int64 __fastcall(WCHAR *, unsigned int *, WCHAR *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x1800094c0`
- `0x18000d8c0`

## callees

- `0x1800053b8`
- `0x180007fd0`
- `0x180008070`
- `0x1800083a0`
- `0x180009600`
- `0x180009cd0`
- `0x180009ea0`
- `0x180009f04`
- `0x180009f34`
- `0x18000a0c4`
- `0x18000aa20`
- `0x18000ad58`
- `0x18000bb50`
- `0x18000c750`
- `0x18001899e`
- `0x1800189d0`
- `0x180018a60`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18000bd4a`
- `KERNEL32!DeleteFileW` at `0x18000c6e4`
- `KERNEL32!DeleteFileW` at `0x18000c711`
- `KERNEL32!DeleteFileW` at `0x18000bd4a`
- `KERNEL32!DeleteFileW` at `0x18000c6e4`
- `KERNEL32!DeleteFileW` at `0x18000c711`
- `KERNEL32!SetLastError` at `0x18000bd31`
- `KERNEL32!SetLastError` at `0x18000bdf4`
- `KERNEL32!SetLastError` at `0x18000bd31`
- `KERNEL32!SetLastError` at `0x18000bdf4`
- `KERNEL32!VirtualAlloc` at `0x18000be83`
- `KERNEL32!VirtualAlloc` at `0x18000beaa`
- `KERNEL32!VirtualAlloc` at `0x18000bfb0`
- `KERNEL32!VirtualAlloc` at `0x18000bfdb`
- `KERNEL32!VirtualAlloc` at `0x18000be83`
- `KERNEL32!VirtualAlloc` at `0x18000beaa`
- `KERNEL32!VirtualAlloc` at `0x18000bfb0`
- `KERNEL32!VirtualAlloc` at `0x18000bfdb`
- `KERNEL32!VirtualFree` at `0x18000bf64`
- `KERNEL32!VirtualFree` at `0x18000bf7d`
- `KERNEL32!VirtualFree` at `0x18000c680`
- `KERNEL32!VirtualFree` at `0x18000c69c`
- `KERNEL32!VirtualFree` at `0x18000bf64`
- `KERNEL32!VirtualFree` at `0x18000bf7d`
- `KERNEL32!VirtualFree` at `0x18000c680`
- `KERNEL32!VirtualFree` at `0x18000c69c`
- `KERNEL32!MoveFileW` at `0x18000c6fb`
- `KERNEL32!MoveFileW` at `0x18000c6fb`
- `KERNEL32!GetTempPath2W` at `0x18000bc56`
- `KERNEL32!GetTempPath2W` at `0x18000bc56`
- `KERNEL32!GetTempFileNameW` at `0x18000bc7f`
- `KERNEL32!GetTempFileNameW` at `0x18000bc7f`

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
    if ( !(unsigned int)TiffSeekToPage((__int64)v29, v28 + 1, 2) )
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
    if ( !(unsigned int)GetTiffBits(
                          (__int64)lpMem,
                          (unsigned __int8 *)((unsigned __int64)lpAddress & 0xFFFFFFFFFFFFFFFCuLL),
                          &dwSize) )
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
      if ( !(unsigned int)GetTiffBits((__int64)lpMem, (unsigned __int8 *)(v32 & 0xFFFFFFFFFFFFFFFCuLL), &dwSize) )
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
0x18000bb50  mov     [rsp-8+arg_10], rbx
0x18000bb55  push    rbp
0x18000bb56  push    rsi
0x18000bb57  push    rdi
0x18000bb58  push    r12
0x18000bb5a  push    r13
0x18000bb5c  push    r14
0x18000bb5e  push    r15
0x18000bb60  lea     rbp, [rsp-2130h]
0x18000bb68  mov     eax, 2230h
0x18000bb6d  call    _alloca_probe
0x18000bb72  sub     rsp, rax
0x18000bb75  mov     rax, cs:__security_cookie
0x18000bb7c  xor     rax, rsp
0x18000bb7f  mov     [rbp+2160h+var_40], rax
0x18000bb86  mov     r15, r8
0x18000bb89  mov     [rbp+2160h+var_21C0], r8
0x18000bb8d  mov     r14, rdx
0x18000bb90  mov     [rbp+2160h+lpMem], rcx
0x18000bb94  mov     r13, rcx
0x18000bb97  mov     ebx, 208h
0x18000bb9c  mov     r8d, ebx; Size
0x18000bb9f  lea     rcx, [rbp+2160h+TempFileName]; void *
0x18000bba3  xor     edx, edx; Val
0x18000bba5  call    memset_0
0x18000bbaa  mov     r8d, ebx; Size
0x18000bbad  lea     rcx, [rbp+2160h+PathName]; void *
0x18000bbb4  xor     edx, edx; Val
0x18000bbb6  call    memset_0
0x18000bbbb  mov     r8d, ebx; Size
0x18000bbbe  lea     rcx, [rbp+2160h+FileName]; void *
0x18000bbc5  xor     edx, edx; Val
0x18000bbc7  call    memset_0
0x18000bbcc  mov     ebx, 0D84h
0x18000bbd1  lea     rcx, [rbp+2160h+var_1B5E]; void *
0x18000bbd8  mov     r8d, ebx; Size
0x18000bbdb  xor     edx, edx; Val
0x18000bbdd  call    memset_0
0x18000bbe2  mov     r8d, ebx; Size
0x18000bbe5  lea     rcx, [rbp+2160h+var_DCE]; void *
0x18000bbec  xor     edx, edx; Val
0x18000bbee  call    memset_0
0x18000bbf3  mov     r10, cs:WPP_GLOBAL_Control
0x18000bbfa  lea     rax, WPP_GLOBAL_Control
0x18000bc01  cmp     r10, rax
0x18000bc04  jz      short loc_18000BC30
0x18000bc06  test    byte ptr [r10+1Ch], 2
0x18000bc0b  jz      short loc_18000BC30
0x18000bc0d  cmp     byte ptr [r10+19h], 5
0x18000bc12  jb      short loc_18000BC30
0x18000bc14  mov     rcx, [r10+10h]
0x18000bc18  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000bc1f  mov     edx, 25h ; '%'
0x18000bc24  call    WPP_SF_
0x18000bc29  mov     r10, cs:WPP_GLOBAL_Control
0x18000bc30  xor     r11d, r11d
0x18000bc33  mov     esi, 7FFFFFFEh
0x18000bc38  mov     edi, 104h
0x18000bc3d  mov     r12d, 1
0x18000bc43  test    r15, r15
0x18000bc46  jnz     loc_18000BD5B
0x18000bc4c  lea     rdx, [rbp+2160h+PathName]
0x18000bc53  lea     ecx, [rdi-1]
0x18000bc56  call    cs:__imp_GetTempPath2W
0x18000bc5d  nop     dword ptr [rax+rax+00h]
0x18000bc62  xor     r8d, r8d; uUnique
0x18000bc65  test    eax, eax
0x18000bc67  jz      loc_18000BE00
0x18000bc6d  lea     r9, [rbp+2160h+TempFileName]; lpTempFileName
0x18000bc71  lea     rdx, PrefixString; "Fxs"
0x18000bc78  lea     rcx, [rbp+2160h+PathName]; lpPathName
0x18000bc7f  call    cs:__imp_GetTempFileNameW
0x18000bc86  nop     dword ptr [rax+rax+00h]
0x18000bc8b  xor     r11d, r11d
0x18000bc8e  test    eax, eax
0x18000bc90  jz      loc_18000BE00
0x18000bc96  mov     r10, cs:WPP_GLOBAL_Control
0x18000bc9d  lea     rax, [r13+2Ch]
0x18000bca1  lea     rdx, [rbp+2160h+FileName]
0x18000bca8  test    rsi, rsi
0x18000bcab  jz      short loc_18000BCC8
0x18000bcad  movzx   ecx, word ptr [rax]
0x18000bcb0  test    cx, cx
0x18000bcb3  jz      short loc_18000BCC8
0x18000bcb5  mov     [rdx], cx
0x18000bcb8  add     rax, 2
0x18000bcbc  add     rdx, 2
0x18000bcc0  sub     rsi, r12
0x18000bcc3  sub     rdi, r12
0x18000bcc6  jnz     short loc_18000BCA8
0x18000bcc8  mov     rax, rdi
0x18000bccb  lea     rcx, [rdx-2]
0x18000bccf  neg     rax
0x18000bcd2  sbb     ebx, ebx
0x18000bcd4  not     ebx
0x18000bcd6  and     ebx, 8007007Ah
0x18000bcdc  test    rdi, rdi
0x18000bcdf  cmovnz  rcx, rdx
0x18000bce3  mov     [rcx], r11w
0x18000bce7  jnz     loc_18000BE07
0x18000bced  lea     rax, WPP_GLOBAL_Control
0x18000bcf4  cmp     r10, rax
0x18000bcf7  jz      short loc_18000BD1F
0x18000bcf9  test    byte ptr [r10+1Ch], 2
0x18000bcfe  jz      short loc_18000BD1F
0x18000bd00  cmp     byte ptr [r10+19h], 2
0x18000bd05  jb      short loc_18000BD1F
0x18000bd07  mov     rcx, [r10+10h]
0x18000bd0b  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000bd12  mov     edx, 27h ; '''
0x18000bd17  mov     r9d, ebx
0x18000bd1a  call    WPP_SF_d
0x18000bd1f  mov     eax, ebx
0x18000bd21  movzx   ecx, bx
0x18000bd24  and     eax, 1FFF0000h
0x18000bd29  cmp     eax, 70000h
0x18000bd2e  cmovnz  ecx, ebx; dwErrCode
0x18000bd31  call    cs:__imp_SetLastError
0x18000bd38  nop     dword ptr [rax+rax+00h]
0x18000bd3d  test    r15, r15
0x18000bd40  jnz     loc_18000BE00
0x18000bd46  lea     rcx, [rbp+2160h+TempFileName]; lpFileName
0x18000bd4a  call    cs:__imp_DeleteFileW
0x18000bd51  nop     dword ptr [rax+rax+00h]
0x18000bd56  jmp     loc_18000BE00
0x18000bd5b  mov     rax, rsi
0x18000bd5e  lea     r8, [rbp+2160h+TempFileName]
0x18000bd62  mov     rcx, r15
0x18000bd65  mov     rdx, rdi
0x18000bd68  test    rax, rax
0x18000bd6b  jz      short loc_18000BD8B
0x18000bd6d  movzx   r9d, word ptr [rcx]
0x18000bd71  test    r9w, r9w
0x18000bd75  jz      short loc_18000BD8B
0x18000bd77  mov     [r8], r9w
0x18000bd7b  add     rcx, 2
0x18000bd7f  add     r8, 2
0x18000bd83  sub     rax, r12
0x18000bd86  sub     rdx, r12
0x18000bd89  jnz     short loc_18000BD68
0x18000bd8b  mov     rax, rdx
0x18000bd8e  lea     rcx, [r8-2]
0x18000bd92  neg     rax
0x18000bd95  sbb     ebx, ebx
0x18000bd97  not     ebx
0x18000bd99  and     ebx, 8007007Ah
0x18000bd9f  test    rdx, rdx
0x18000bda2  cmovnz  rcx, r8
0x18000bda6  mov     [rcx], r11w
0x18000bdaa  jnz     loc_18000BC9D
0x18000bdb0  lea     rax, WPP_GLOBAL_Control
0x18000bdb7  cmp     r10, rax
0x18000bdba  jz      short loc_18000BDE2
0x18000bdbc  test    byte ptr [r10+1Ch], 2
0x18000bdc1  jz      short loc_18000BDE2
0x18000bdc3  cmp     byte ptr [r10+19h], 2
0x18000bdc8  jb      short loc_18000BDE2
0x18000bdca  mov     rcx, [r10+10h]
0x18000bdce  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000bdd5  mov     edx, 26h ; '&'
0x18000bdda  mov     r9d, ebx
0x18000bddd  call    WPP_SF_d
0x18000bde2  mov     eax, ebx
0x18000bde4  movzx   ecx, bx
0x18000bde7  and     eax, 1FFF0000h
0x18000bdec  cmp     eax, 70000h
0x18000bdf1  cmovnz  ecx, ebx; dwErrCode
0x18000bdf4  call    cs:__imp_SetLastError
0x18000bdfb  nop     dword ptr [rax+rax+00h]
0x18000be00  xor     eax, eax
0x18000be02  jmp     loc_18000C71F
0x18000be07  cmp     dword ptr [r14+1Ch], 0C4h
0x18000be0f  lea     rcx, [rbp+2160h+TempFileName]; lpFileName
0x18000be13  mov     r8d, [r14]
0x18000be16  mov     eax, r11d
0x18000be19  mov     r9d, 2
0x18000be1f  mov     ebx, r11d
0x18000be22  setz    al
0x18000be25  mov     [rbp+2160h+var_21E0], ebx
0x18000be28  mov     [rsp+2260h+var_2240], eax; int
0x18000be2c  lea     edx, [r9+2]
0x18000be30  call    TiffCreate
0x18000be35  mov     r13, rax
0x18000be38  test    rax, rax
0x18000be3b  jz      loc_18000C6B5
0x18000be41  mov     ecx, [r14]
0x18000be44  mov     eax, 0FFFFFFFFh
0x18000be49  shr     rcx, 3
0x18000be4d  imul    r15, rcx, 960h
0x18000be54  cmp     r15, rax
0x18000be57  ja      loc_18000C6B1
0x18000be5d  lea     edi, [r15+30D40h]
0x18000be64  mov     dword ptr [rbp+2160h+Size], edi
0x18000be67  cmp     edi, r15d
0x18000be6a  jb      loc_18000C6B1
0x18000be70  mov     esi, 1000h
0x18000be75  mov     edx, r15d; dwSize
0x18000be78  mov     r8d, esi; flAllocationType
0x18000be7b  mov     r9d, 4; flProtect
0x18000be81  xor     ecx, ecx; lpAddress
0x18000be83  call    cs:__imp_VirtualAlloc
0x18000be8a  nop     dword ptr [rax+rax+00h]
0x18000be8f  mov     [rsp+2260h+lpAddress], rax
0x18000be94  test    rax, rax
0x18000be97  jz      loc_18000C6B1
0x18000be9d  mov     edx, edi; dwSize
0x18000be9f  mov     r9d, 4; flProtect
0x18000bea5  mov     r8d, esi; flAllocationType
0x18000bea8  xor     ecx, ecx; lpAddress
0x18000beaa  call    cs:__imp_VirtualAlloc
0x18000beb1  nop     dword ptr [rax+rax+00h]
0x18000beb6  xor     r9d, r9d
0x18000beb9  mov     [rsp+2260h+var_2200], rax
0x18000bebe  mov     rbx, rax
0x18000bec1  test    rax, rax
0x18000bec4  jz      loc_18000C669
0x18000beca  mov     ecx, [r14+8]
0x18000bece  mov     eax, r9d
0x18000bed1  mov     [rbp+2160h+var_21AC], ecx
0x18000bed4  test    ecx, ecx
0x18000bed6  jz      loc_18000C3CF
0x18000bedc  mov     rdi, [rbp+2160h+lpMem]
0x18000bee0  inc     eax
0x18000bee2  mov     r8d, 2
0x18000bee8  mov     edx, eax
0x18000beea  mov     [rbp+2160h+var_21B0], eax
0x18000beed  mov     rcx, rdi
0x18000bef0  call    TiffSeekToPage
0x18000bef5  test    eax, eax
0x18000bef7  jz      loc_18000C3D6
0x18000befd  mov     esi, [rdi+61Ch]
0x18000bf03  mov     rcx, r13
0x18000bf06  mov     dword ptr [rsp+2260h+dwSize+4], esi
0x18000bf0a  call    TiffStartPage
0x18000bf0f  mov     r14, [rsp+2260h+lpAddress]
0x18000bf14  test    eax, eax
0x18000bf16  jz      loc_18000C662
0x18000bf1c  mov     rcx, [rbp+2160h+lpMem]
0x18000bf20  lea     r8, [rsp+2260h+dwSize]
0x18000bf25  mov     rbx, r14
0x18000bf28  mov     dword ptr [rsp+2260h+dwSize], r15d
0x18000bf2d  and     rbx, 0FFFFFFFFFFFFFFFCh
0x18000bf31  mov     rdx, rbx
0x18000bf34  mov     [rsp+2260h+var_21F0], rbx
0x18000bf39  mov     rdi, rbx
0x18000bf3c  call    GetTiffBits
0x18000bf41  xor     r9d, r9d
0x18000bf44  test    eax, eax
0x18000bf46  jnz     loc_18000C023
0x18000bf4c  cmp     dword ptr [rsp+2260h+dwSize], r15d
0x18000bf51  jbe     loc_18000C65D
0x18000bf57  mov     ebx, 8000h
0x18000bf5c  xor     edx, edx; dwSize
0x18000bf5e  mov     r8d, ebx; dwFreeType
0x18000bf61  mov     rcx, r14; lpAddress
0x18000bf64  call    cs:__imp_VirtualFree
0x18000bf6b  nop     dword ptr [rax+rax+00h]
0x18000bf70  mov     r8d, ebx; dwFreeType
0x18000bf73  xor     edx, edx; dwSize
0x18000bf75  mov     rbx, [rsp+2260h+var_2200]
0x18000bf7a  mov     rcx, rbx; lpAddress
0x18000bf7d  call    cs:__imp_VirtualFree
0x18000bf84  nop     dword ptr [rax+rax+00h]
0x18000bf89  mov     r15d, dword ptr [rsp+2260h+dwSize]
0x18000bf8e  lea     edi, [r15+30D40h]
0x18000bf95  mov     dword ptr [rbp+2160h+Size], edi
0x18000bf98  cmp     edi, r15d
0x18000bf9b  jb      loc_18000C662
0x18000bfa1  xor     ecx, ecx; lpAddress
0x18000bfa3  mov     edx, r15d; dwSize
0x18000bfa6  mov     r8d, 1000h; flAllocationType
0x18000bfac  lea     r9d, [rcx+4]; flProtect
0x18000bfb0  call    cs:__imp_VirtualAlloc
0x18000bfb7  nop     dword ptr [rax+rax+00h]
0x18000bfbc  mov     [rsp+2260h+lpAddress], rax
0x18000bfc1  mov     r14, rax
0x18000bfc4  test    rax, rax
0x18000bfc7  jz      loc_18000C68C
0x18000bfcd  xor     ecx, ecx; lpAddress
0x18000bfcf  mov     edx, edi; dwSize
0x18000bfd1  mov     r8d, 1000h; flAllocationType
0x18000bfd7  lea     r9d, [rcx+4]; flProtect
0x18000bfdb  call    cs:__imp_VirtualAlloc
0x18000bfe2  nop     dword ptr [rax+rax+00h]
0x18000bfe7  mov     [rsp+2260h+var_2200], rax
0x18000bfec  mov     rbx, rax
0x18000bfef  test    rax, rax
0x18000bff2  jz      loc_18000C675
0x18000bff8  mov     rcx, [rbp+2160h+lpMem]
0x18000bffc  lea     r8, [rsp+2260h+dwSize]
0x18000c001  mov     rbx, r14
0x18000c004  and     rbx, 0FFFFFFFFFFFFFFFCh
0x18000c008  mov     rdx, rbx
0x18000c00b  mov     [rsp+2260h+var_21F0], rbx
0x18000c010  mov     rdi, rbx
0x18000c013  call    GetTiffBits
0x18000c018  xor     r9d, r9d
0x18000c01b  test    eax, eax
0x18000c01d  jz      loc_18000C670
0x18000c023  mov     eax, dword ptr [rsp+2260h+dwSize]
  ... truncated ...
```
