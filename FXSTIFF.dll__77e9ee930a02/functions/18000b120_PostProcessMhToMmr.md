# PostProcessMhToMmr

- ea: `0x18000b120`
- end: `0x18000bb47`
- name: `PostProcessMhToMmr`
- size: `2599`
- prototype: `__int64 __fastcall(WCHAR *, unsigned int *, WCHAR *)`
- caller_count: `2`
- callee_count: `16`
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
- `0x18000b120`
- `0x18001899e`
- `0x1800189d0`
- `0x180018a60`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18000b3c0`
- `KERNEL32!DeleteFileW` at `0x18000bade`
- `KERNEL32!DeleteFileW` at `0x18000bb0d`
- `KERNEL32!DeleteFileW` at `0x18000b3c0`
- `KERNEL32!DeleteFileW` at `0x18000bade`
- `KERNEL32!DeleteFileW` at `0x18000bb0d`
- `KERNEL32!SetLastError` at `0x18000b2ff`
- `KERNEL32!SetLastError` at `0x18000b3a7`
- `KERNEL32!SetLastError` at `0x18000b2ff`
- `KERNEL32!SetLastError` at `0x18000b3a7`
- `KERNEL32!VirtualAlloc` at `0x18000b43e`
- `KERNEL32!VirtualAlloc` at `0x18000b469`
- `KERNEL32!VirtualAlloc` at `0x18000b560`
- `KERNEL32!VirtualAlloc` at `0x18000b58b`
- `KERNEL32!VirtualAlloc` at `0x18000b43e`
- `KERNEL32!VirtualAlloc` at `0x18000b469`
- `KERNEL32!VirtualAlloc` at `0x18000b560`
- `KERNEL32!VirtualAlloc` at `0x18000b58b`
- `KERNEL32!VirtualFree` at `0x18000b51d`
- `KERNEL32!VirtualFree` at `0x18000b531`
- `KERNEL32!VirtualFree` at `0x18000ba7e`
- `KERNEL32!VirtualFree` at `0x18000ba9e`
- `KERNEL32!VirtualFree` at `0x18000b51d`
- `KERNEL32!VirtualFree` at `0x18000b531`
- `KERNEL32!VirtualFree` at `0x18000ba7e`
- `KERNEL32!VirtualFree` at `0x18000ba9e`
- `KERNEL32!MoveFileW` at `0x18000baf5`
- `KERNEL32!MoveFileW` at `0x18000baf5`
- `KERNEL32!GetTempPath2W` at `0x18000b228`
- `KERNEL32!GetTempPath2W` at `0x18000b228`
- `KERNEL32!GetTempFileNameW` at `0x18000b251`
- `KERNEL32!GetTempFileNameW` at `0x18000b251`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PostProcessMhToMmr(WCHAR *a1, unsigned int *a2, WCHAR *a3)
{
  WCHAR *v3; // r13
  _QWORD *v6; // r10
  unsigned int v7; // r12d
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 v10; // rax
  WCHAR *v11; // r8
  WCHAR *v12; // rcx
  __int64 v13; // rdx
  WCHAR *v14; // rcx
  unsigned int v15; // ebx
  DWORD v16; // ecx
  WCHAR *v18; // rax
  WCHAR *v19; // rdx
  WCHAR *v20; // rcx
  unsigned int v21; // ebx
  DWORD v22; // ecx
  _DWORD *v23; // r15
  unsigned __int64 v24; // rsi
  void *v25; // rbx
  unsigned __int64 v26; // r13
  unsigned int v27; // eax
  _DWORD *v28; // rbx
  unsigned __int64 v29; // r14
  unsigned __int64 v30; // rbx
  unsigned int v31; // edi
  unsigned int v32; // ebx
  void *v33; // r13
  unsigned __int64 v34; // rax
  unsigned __int64 v35; // rbx
  unsigned int v36; // r14d
  _DWORD *v37; // r14
  unsigned __int8 v38; // bl
  __int64 v39; // r9
  unsigned __int16 v40; // r11
  unsigned __int16 v41; // r10
  int v42; // r13d
  int v43; // r8d
  char *v44; // rdi
  __int16 *v45; // r8
  unsigned int v46; // edx
  unsigned int v47; // ecx
  unsigned int v48; // r13d
  __int16 *v49; // r13
  int v50; // eax
  __int64 v51; // rax
  int v52; // ebx
  int v53; // edi
  __int16 *v54; // rax
  unsigned __int64 v55; // rdi
  int NextEol; // eax
  int v57; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v58; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v59[3]; // [rsp+41h] [rbp-BFh] BYREF
  unsigned int dwSize[3]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v61; // [rsp+50h] [rbp-B0h]
  int v62; // [rsp+54h] [rbp-ACh]
  int v63; // [rsp+58h] [rbp-A8h]
  __int16 *v64; // [rsp+60h] [rbp-A0h]
  unsigned int v65; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v66; // [rsp+70h] [rbp-90h] BYREF
  __int16 *v67; // [rsp+78h] [rbp-88h]
  void *v68; // [rsp+80h] [rbp-80h] BYREF
  size_t Size; // [rsp+88h] [rbp-78h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  unsigned int v71; // [rsp+98h] [rbp-68h]
  unsigned int v72; // [rsp+9Ch] [rbp-64h]
  unsigned __int64 v73; // [rsp+A0h] [rbp-60h]
  __int64 v74; // [rsp+A8h] [rbp-58h]
  LPVOID v75; // [rsp+B0h] [rbp-50h]
  _BYTE *v76; // [rsp+B8h] [rbp-48h]
  WCHAR *v77; // [rsp+C0h] [rbp-40h]
  void *v78; // [rsp+C8h] [rbp-38h]
  WCHAR TempFileName[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR FileName[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR PathName[264]; // [rsp+4F0h] [rbp+3F0h] BYREF
  __int16 v82; // [rsp+700h] [rbp+600h] BYREF
  char v83[3470]; // [rsp+702h] [rbp+602h] BYREF
  __int16 v84; // [rsp+1490h] [rbp+1390h] BYREF
  char v85[3470]; // [rsp+1492h] [rbp+1392h] BYREF

  v3 = a3;
  v77 = a3;
  lpMem = a1;
  memset_0(TempFileName, 0, 0x208u);
  memset_0(PathName, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  memset_0(v83, 0, 0xD84u);
  memset_0(v85, 0, 0xD84u);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = 0;
  v8 = 2147483646;
  v9 = 260;
  if ( v3 )
  {
    v10 = 2147483646;
    v11 = TempFileName;
    v12 = v3;
    v13 = 260;
    do
    {
      if ( !v10 )
        break;
      if ( !*v12 )
        break;
      *v11++ = *v12++;
      --v10;
      --v13;
    }
    while ( v13 );
    v14 = v11 - 1;
    v15 = v13 == 0 ? 0x8007007A : 0;
    if ( v13 )
      v14 = v11;
    *v14 = 0;
    if ( !v13 )
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 2u )
        WPP_SF_d(v6[2], 35, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids, v15);
      v16 = (unsigned __int16)v15;
      if ( (v15 & 0x1FFF0000) != 0x70000 )
        v16 = v15;
      SetLastError(v16);
      return 0;
    }
  }
  else
  {
    if ( !(unsigned int)GetTempPath2W(259, PathName) || !GetTempFileNameW(PathName, L"Fxs", 0, TempFileName) )
      return 0;
    v6 = WPP_GLOBAL_Control;
  }
  v18 = a1 + 22;
  v19 = FileName;
  do
  {
    if ( !v8 )
      break;
    if ( !*v18 )
      break;
    *v19++ = *v18++;
    --v8;
    --v9;
  }
  while ( v9 );
  v20 = v19 - 1;
  v21 = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v20 = v19;
  *v20 = 0;
  if ( !v9 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_d(v6[2], 36, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids, v21);
    v22 = (unsigned __int16)v21;
    if ( (v9 == 0 ? 0x70000 : 0) != 0x70000 )
      v22 = v9 == 0 ? 0x8007007A : 0;
    SetLastError(v22);
    if ( !v3 )
      DeleteFileW(TempFileName);
    return 0;
  }
  v23 = (_DWORD *)TiffCreate(TempFileName, a2[7] == 196);
  if ( !v23 )
    goto LABEL_113;
  v24 = 2400 * ((unsigned __int64)*a2 >> 3);
  if ( v24 > 0xFFFFFFFF )
    goto LABEL_113;
  LODWORD(Size) = v24 + 200000;
  if ( (int)v24 + 200000 < (unsigned int)v24 )
    goto LABEL_113;
  *(_QWORD *)&dwSize[1] = VirtualAlloc(0, (unsigned int)v24, 0x1000u, 4u);
  v25 = *(void **)&dwSize[1];
  if ( !*(_QWORD *)&dwSize[1] )
    goto LABEL_113;
  v75 = VirtualAlloc(0, (unsigned int)(v24 + 200000), 0x1000u, 4u);
  v26 = (unsigned __int64)v75;
  if ( !v75 )
    goto LABEL_109;
  v27 = 0;
  v72 = a2[2];
  if ( !v72 )
    goto LABEL_91;
  v28 = lpMem;
  while ( 2 )
  {
    v71 = v27 + 1;
    if ( !(unsigned int)TiffSeekToPage((__int64)v28, v27 + 1, 2) )
      goto LABEL_108;
    v61 = v28[391];
    if ( !(unsigned int)TiffStartPage(v23) )
      goto LABEL_108;
    v29 = *(_QWORD *)&dwSize[1];
    v30 = *(_QWORD *)&dwSize[1] & 0xFFFFFFFFFFFFFFFCuLL;
    dwSize[0] = v24;
    v66 = *(_QWORD *)&dwSize[1] & 0xFFFFFFFFFFFFFFFCuLL;
    v31 = dwSize[1] & 0xFFFFFFFC;
    if ( !(unsigned int)GetTiffBits(
                          (__int64)lpMem,
                          (unsigned __int8 *)(*(_QWORD *)&dwSize[1] & 0xFFFFFFFFFFFFFFFCuLL),
                          dwSize) )
    {
      if ( dwSize[0] <= (unsigned int)v24 )
        goto LABEL_107;
      VirtualFree((LPVOID)v29, 0, 0x8000u);
      VirtualFree((LPVOID)v26, 0, 0x8000u);
      LODWORD(v24) = dwSize[0];
      v32 = dwSize[0] + 200000;
      LODWORD(Size) = dwSize[0] + 200000;
      if ( dwSize[0] + 200000 < dwSize[0] )
        goto LABEL_107;
      *(_QWORD *)&dwSize[1] = VirtualAlloc(0, dwSize[0], 0x1000u, 4u);
      v29 = *(_QWORD *)&dwSize[1];
      if ( !*(_QWORD *)&dwSize[1] )
        goto LABEL_110;
      v75 = VirtualAlloc(0, v32, 0x1000u, 4u);
      v26 = (unsigned __int64)v75;
      v25 = (void *)v29;
      if ( !v75 )
        goto LABEL_109;
      v30 = v29 & 0xFFFFFFFFFFFFFFFCuLL;
      v66 = v29 & 0xFFFFFFFFFFFFFFFCuLL;
      v31 = v29 & 0xFFFFFFFC;
      if ( !(unsigned int)GetTiffBits((__int64)lpMem, (unsigned __int8 *)(v29 & 0xFFFFFFFFFFFFFFFCuLL), dwSize) )
      {
LABEL_107:
        v25 = (void *)v29;
        goto LABEL_109;
      }
    }
    v33 = (void *)(v26 & 0xFFFFFFFFFFFFFFFCuLL);
    v58 = 0;
    v59[0] = 0;
    v78 = v33;
    v34 = v30 + 4 * ((unsigned __int64)dwSize[0] >> 2);
    v68 = v33;
    v35 = (unsigned int)Size;
    v73 = v34;
    memset_0(v33, 0, (unsigned int)Size);
    v36 = v61;
    v82 = v61;
    if ( !(unsigned int)FindNextEol(v31, 0, v73, (unsigned int)&v66, (__int64)&v58, 0, (__int64)&v65) )
      goto LABEL_108;
    v84 = v36;
    v74 = (__int64)v33 + 4 * (v35 >> 2);
    if ( !(unsigned int)OutputMmrLine(
                          (_DWORD)v33,
                          0,
                          (unsigned int)&v84,
                          (unsigned int)&v82,
                          (__int64)&v68,
                          (__int64)v59,
                          v74,
                          v36) )
      goto LABEL_108;
    v37 = (_DWORD *)v66;
    v67 = &v82;
    dwSize[0] = 1;
    v64 = &v84;
    v63 = 1;
    do
    {
      v38 = v58;
      v39 = (__int64)gc_GlobTableWhite;
      v40 = 0;
      v62 = 0;
      v41 = 0;
      v42 = 0;
LABEL_58:
      if ( v38 > 0x11u )
        LOWORD(v43) = (*v37 >> v38) + (v37[1] << (32 - v38));
      else
        v43 = *v37 >> v38;
      v44 = (char *)(v39 + 5 * (v43 & 0x7FFFu));
      v76 = v44 + 4;
      v45 = 0;
      v46 = 0;
      v65 = 0;
      v39 = 1;
      while ( 1 )
      {
        v47 = *v44 & 0x3F;
        if ( *v44 >= 0 )
          break;
        if ( v47 <= 0x28 )
        {
          v41 += (_WORD)v47 << 6;
          if ( v41 > v61 )
            goto LABEL_93;
          v62 = 1;
          goto LABEL_79;
        }
        if ( v47 == 53 )
          goto LABEL_81;
        if ( v47 == 51 )
        {
          v53 = 1;
          v38 += *v76 & 0xF;
          v58 = v38;
          if ( v38 > 0x1Fu )
          {
            ++v37;
            v38 -= 32;
            v66 = (unsigned __int64)v37;
            v58 = v38;
          }
          goto LABEL_94;
        }
        if ( v47 != 52 )
        {
          if ( v47 != 50 )
            goto LABEL_108;
LABEL_93:
          v53 = 0;
LABEL_94:
          v45 = v64;
          goto LABEL_95;
        }
        v48 = v61;
        if ( v41 != v61 || v62 )
        {
          if ( !v41 && ++dwSize[0] >= 5 )
            goto LABEL_87;
        }
        else
        {
          LOBYTE(v46) = v59[0];
          v49 = v64;
          v50 = OutputMmrLine((_DWORD)v68, v46, (_DWORD)v64, (_DWORD)v67, (__int64)&v68, (__int64)v59, v74, v61);
          v45 = 0;
          if ( !v50 )
            goto LABEL_108;
          v39 = 1;
          ++v63;
          v46 = v65;
          v64 = v67;
          v67 = v49;
        }
        v40 = 0;
        v62 = 0;
        v41 = 0;
        v42 = 0;
LABEL_80:
        ++v46;
        ++v44;
        v65 = v46;
        if ( v46 >= 4 )
        {
LABEL_81:
          v39 = (__int64)GlobTableBlack;
          if ( !v42 )
            v39 = (__int64)gc_GlobTableWhite;
          v38 += *v76 & 0xF;
          v58 = v38;
          if ( v38 > 0x1Fu )
          {
            ++v37;
            v38 -= 32;
            v66 = (unsigned __int64)v37;
            v58 = v38;
          }
          if ( (unsigned __int64)v37 > v73 )
          {
            v48 = v61;
            goto LABEL_87;
          }
          goto LABEL_58;
        }
      }
      v41 += v47;
      if ( v41 > v61 )
        goto LABEL_93;
      v45 = v64;
      v51 = v40++;
      v64[v51] = v41;
      if ( v40 < 0x6C3u )
      {
        v45 = 0;
        v62 = 0;
        v42 = 1 - v42;
LABEL_79:
        dwSize[0] = 0;
        goto LABEL_80;
      }
      v53 = 0;
LABEL_95:
      v48 = v61;
      if ( v41 != v61 || v62 )
      {
        if ( v41 )
          goto LABEL_104;
        if ( ++dwSize[0] < 5 )
          goto LABEL_104;
        break;
      }
      LOBYTE(v46) = v59[0];
      if ( !(unsigned int)OutputMmrLine(
                            (_DWORD)v68,
                            v46,
                            (_DWORD)v45,
                            (_DWORD)v67,
                            (__int64)&v68,
                            (__int64)v59,
                            v74,
                            v61) )
        goto LABEL_108;
      v54 = v67;
      ++v63;
      v67 = v64;
      v64 = v54;
LABEL_104:
      LOBYTE(v46) = v38;
      v57 = v53;
      v55 = v73;
      NextEol = FindNextEol((_DWORD)v37, v46, v73, (unsigned int)&v66, (__int64)&v58, v57, (__int64)&v65);
      v45 = 0;
      if ( !NextEol )
        break;
      v37 = (_DWORD *)v66;
    }
    while ( v66 <= v55 );
LABEL_87:
    v52 = (int)v68;
    CheckAndAddOutput(v68, v74, v45, v39);
    if ( !(unsigned int)TiffWriteRaw(v23, v78, (v52 - (_DWORD)v78) & 0xFFFFFFFC)
      || (v28 = lpMem, v23[212] = v63 - 1, v23[391] = v48, v23[421] = v28[421], !(unsigned int)TiffEndPage(v23)) )
    {
LABEL_108:
      v25 = *(void **)&dwSize[1];
      goto LABEL_109;
    }
    v27 = v71;
    v26 = (unsigned __int64)v75;
    if ( v71 < v72 )
      continue;
    break;
  }
  v25 = *(void **)&dwSize[1];
LABEL_91:
  v7 = 1;
LABEL_109:
  VirtualFree(v25, 0, 0x8000u);
  v26 = (unsigned __int64)v75;
LABEL_110:
  if ( v26 )
    VirtualFree((LPVOID)v26, 0, 0x8000u);
  v3 = v77;
LABEL_113:
  if ( lpMem )
    TiffClose(lpMem);
  if ( v23 )
    TiffClose(v23);
  if ( v7 == 1 )
  {
    if ( !v3 )
    {
      DeleteFileW(FileName);
      v7 = MoveFileW(TempFileName, FileName);
      goto LABEL_120;
    }
  }
  else
  {
LABEL_120:
    if ( !v7 )
      DeleteFileW(TempFileName);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b120  mov     [rsp-8+arg_10], rbx
0x18000b125  push    rbp
0x18000b126  push    rsi
0x18000b127  push    rdi
0x18000b128  push    r12
0x18000b12a  push    r13
0x18000b12c  push    r14
0x18000b12e  push    r15
0x18000b130  lea     rbp, [rsp-2130h]
0x18000b138  mov     eax, 2230h
0x18000b13d  call    _alloca_probe
0x18000b142  sub     rsp, rax
0x18000b145  mov     rax, cs:__security_cookie
0x18000b14c  xor     rax, rsp
0x18000b14f  mov     [rbp+2160h+var_40], rax
0x18000b156  mov     r13, r8
0x18000b159  mov     [rbp+2160h+var_21A0], r8
0x18000b15d  mov     r14, rdx
0x18000b160  mov     [rbp+2160h+lpMem], rcx
0x18000b164  mov     r15, rcx
0x18000b167  mov     ebx, 208h
0x18000b16c  mov     r8d, ebx; Size
0x18000b16f  lea     rcx, [rbp+2160h+TempFileName]; void *
0x18000b173  xor     edx, edx; Val
0x18000b175  call    memset_0
0x18000b17a  mov     r8d, ebx; Size
0x18000b17d  lea     rcx, [rbp+2160h+PathName]; void *
0x18000b184  xor     edx, edx; Val
0x18000b186  call    memset_0
0x18000b18b  mov     r8d, ebx; Size
0x18000b18e  lea     rcx, [rbp+2160h+FileName]; void *
0x18000b195  xor     edx, edx; Val
0x18000b197  call    memset_0
0x18000b19c  mov     ebx, 0D84h
0x18000b1a1  lea     rcx, [rbp+2160h+var_1B5E]; void *
0x18000b1a8  mov     r8d, ebx; Size
0x18000b1ab  xor     edx, edx; Val
0x18000b1ad  call    memset_0
0x18000b1b2  mov     r8d, ebx; Size
0x18000b1b5  lea     rcx, [rbp+2160h+var_DCE]; void *
0x18000b1bc  xor     edx, edx; Val
0x18000b1be  call    memset_0
0x18000b1c3  mov     r10, cs:WPP_GLOBAL_Control
0x18000b1ca  lea     r11, WPP_GLOBAL_Control
0x18000b1d1  cmp     r10, r11
0x18000b1d4  jz      short loc_18000B207
0x18000b1d6  test    byte ptr [r10+1Ch], 2
0x18000b1db  jz      short loc_18000B207
0x18000b1dd  cmp     byte ptr [r10+19h], 5
0x18000b1e2  jb      short loc_18000B207
0x18000b1e4  mov     rcx, [r10+10h]
0x18000b1e8  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000b1ef  mov     edx, 22h ; '"'
0x18000b1f4  call    WPP_SF_
0x18000b1f9  mov     r10, cs:WPP_GLOBAL_Control
0x18000b200  lea     r11, WPP_GLOBAL_Control
0x18000b207  xor     r12d, r12d
0x18000b20a  mov     esi, 7FFFFFFEh
0x18000b20f  mov     edi, 104h
0x18000b214  mov     ebx, 1
0x18000b219  test    r13, r13
0x18000b21c  jnz     short loc_18000B271
0x18000b21e  lea     rdx, [rbp+2160h+PathName]
0x18000b225  lea     ecx, [rdi-1]
0x18000b228  call    cs:__imp_GetTempPath2W
0x18000b22f  nop     dword ptr [rax+rax+00h]
0x18000b234  test    eax, eax
0x18000b236  jz      loc_18000B30B
0x18000b23c  lea     r9, [rbp+2160h+TempFileName]; lpTempFileName
0x18000b240  xor     r8d, r8d; uUnique
0x18000b243  lea     rdx, PrefixString; "Fxs"
0x18000b24a  lea     rcx, [rbp+2160h+PathName]; lpPathName
0x18000b251  call    cs:__imp_GetTempFileNameW
0x18000b258  nop     dword ptr [rax+rax+00h]
0x18000b25d  test    eax, eax
0x18000b25f  jz      loc_18000B30B
0x18000b265  mov     r10, cs:WPP_GLOBAL_Control
0x18000b26c  jmp     loc_18000B317
0x18000b271  mov     rax, rsi
0x18000b274  lea     r8, [rbp+2160h+TempFileName]
0x18000b278  mov     rcx, r13
0x18000b27b  mov     rdx, rdi
0x18000b27e  test    rax, rax
0x18000b281  jz      short loc_18000B2A1
0x18000b283  movzx   r9d, word ptr [rcx]
0x18000b287  test    r9w, r9w
0x18000b28b  jz      short loc_18000B2A1
0x18000b28d  mov     [r8], r9w
0x18000b291  add     rcx, 2
0x18000b295  add     r8, 2
0x18000b299  sub     rax, rbx
0x18000b29c  sub     rdx, rbx
0x18000b29f  jnz     short loc_18000B27E
0x18000b2a1  mov     rax, rdx
0x18000b2a4  lea     rcx, [r8-2]
0x18000b2a8  neg     rax
0x18000b2ab  sbb     ebx, ebx
0x18000b2ad  not     ebx
0x18000b2af  and     ebx, 8007007Ah
0x18000b2b5  test    rdx, rdx
0x18000b2b8  cmovnz  rcx, r8
0x18000b2bc  mov     [rcx], r12w
0x18000b2c0  jnz     short loc_18000B312
0x18000b2c2  cmp     r10, r11
0x18000b2c5  jz      short loc_18000B2ED
0x18000b2c7  test    byte ptr [r10+1Ch], 2
0x18000b2cc  jz      short loc_18000B2ED
0x18000b2ce  cmp     byte ptr [r10+19h], 2
0x18000b2d3  jb      short loc_18000B2ED
0x18000b2d5  mov     rcx, [r10+10h]
0x18000b2d9  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000b2e0  mov     edx, 23h ; '#'
0x18000b2e5  mov     r9d, ebx
0x18000b2e8  call    WPP_SF_d
0x18000b2ed  mov     eax, ebx
0x18000b2ef  movzx   ecx, bx
0x18000b2f2  and     eax, 1FFF0000h
0x18000b2f7  cmp     eax, 70000h
0x18000b2fc  cmovnz  ecx, ebx; dwErrCode
0x18000b2ff  call    cs:__imp_SetLastError
0x18000b306  nop     dword ptr [rax+rax+00h]
0x18000b30b  xor     eax, eax
0x18000b30d  jmp     loc_18000BB1C
0x18000b312  mov     ebx, 1
0x18000b317  lea     rax, [r15+2Ch]
0x18000b31b  lea     rdx, [rbp+2160h+FileName]
0x18000b322  test    rsi, rsi
0x18000b325  jz      short loc_18000B342
0x18000b327  movzx   ecx, word ptr [rax]
0x18000b32a  test    cx, cx
0x18000b32d  jz      short loc_18000B342
0x18000b32f  mov     [rdx], cx
0x18000b332  add     rax, 2
0x18000b336  add     rdx, 2
0x18000b33a  sub     rsi, rbx
0x18000b33d  sub     rdi, rbx
0x18000b340  jnz     short loc_18000B322
0x18000b342  mov     rax, rdi
0x18000b345  lea     rcx, [rdx-2]
0x18000b349  neg     rax
0x18000b34c  sbb     ebx, ebx
0x18000b34e  not     ebx
0x18000b350  and     ebx, 8007007Ah
0x18000b356  test    rdi, rdi
0x18000b359  cmovnz  rcx, rdx
0x18000b35d  mov     [rcx], r12w
0x18000b361  jnz     short loc_18000B3D1
0x18000b363  lea     rax, WPP_GLOBAL_Control
0x18000b36a  cmp     r10, rax
0x18000b36d  jz      short loc_18000B395
0x18000b36f  test    byte ptr [r10+1Ch], 2
0x18000b374  jz      short loc_18000B395
0x18000b376  cmp     byte ptr [r10+19h], 2
0x18000b37b  jb      short loc_18000B395
0x18000b37d  mov     rcx, [r10+10h]
0x18000b381  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000b388  mov     edx, 24h ; '$'
0x18000b38d  mov     r9d, ebx
0x18000b390  call    WPP_SF_d
0x18000b395  mov     eax, ebx
0x18000b397  movzx   ecx, bx
0x18000b39a  and     eax, 1FFF0000h
0x18000b39f  cmp     eax, 70000h
0x18000b3a4  cmovnz  ecx, ebx; dwErrCode
0x18000b3a7  call    cs:__imp_SetLastError
0x18000b3ae  nop     dword ptr [rax+rax+00h]
0x18000b3b3  test    r13, r13
0x18000b3b6  jnz     loc_18000B30B
0x18000b3bc  lea     rcx, [rbp+2160h+TempFileName]; lpFileName
0x18000b3c0  call    cs:__imp_DeleteFileW
0x18000b3c7  nop     dword ptr [rax+rax+00h]
0x18000b3cc  jmp     loc_18000B30B
0x18000b3d1  mov     r8d, [r14]
0x18000b3d4  lea     rcx, [rbp+2160h+TempFileName]; lpFileName
0x18000b3d8  xor     edi, edi
0x18000b3da  cmp     dword ptr [r14+1Ch], 0C4h
0x18000b3e2  mov     eax, edi
0x18000b3e4  setz    al
0x18000b3e7  lea     r9d, [rdi+2]
0x18000b3eb  mov     [rsp+2260h+var_2240], eax; int
0x18000b3ef  lea     edx, [rdi+4]
0x18000b3f2  call    TiffCreate
0x18000b3f7  mov     r15, rax
0x18000b3fa  test    rax, rax
0x18000b3fd  jz      loc_18000BAAE
0x18000b403  mov     ecx, [r14]
0x18000b406  mov     eax, 0FFFFFFFFh
0x18000b40b  shr     rcx, 3
0x18000b40f  imul    rsi, rcx, 960h
0x18000b416  cmp     rsi, rax
0x18000b419  ja      loc_18000BAAE
0x18000b41f  lea     edi, [rsi+30D40h]
0x18000b425  mov     dword ptr [rbp+2160h+Size], edi
0x18000b428  cmp     edi, esi
0x18000b42a  jb      loc_18000BAAE
0x18000b430  xor     ecx, ecx; lpAddress
0x18000b432  mov     edx, esi; dwSize
0x18000b434  mov     r8d, 1000h; flAllocationType
0x18000b43a  lea     r9d, [rcx+4]; flProtect
0x18000b43e  call    cs:__imp_VirtualAlloc
0x18000b445  nop     dword ptr [rax+rax+00h]
0x18000b44a  mov     qword ptr [rsp+2260h+dwSize+4], rax
0x18000b44f  mov     rbx, rax
0x18000b452  test    rax, rax
0x18000b455  jz      loc_18000BAAE
0x18000b45b  xor     ecx, ecx; lpAddress
0x18000b45d  mov     edx, edi; dwSize
0x18000b45f  mov     r8d, 1000h; flAllocationType
0x18000b465  lea     r9d, [rcx+4]; flProtect
0x18000b469  call    cs:__imp_VirtualAlloc
0x18000b470  nop     dword ptr [rax+rax+00h]
0x18000b475  xor     edi, edi
0x18000b477  mov     [rbp+2160h+var_21B0], rax
0x18000b47b  mov     r13, rax
0x18000b47e  test    rax, rax
0x18000b481  jz      loc_18000BA73
0x18000b487  mov     ecx, [r14+8]
0x18000b48b  mov     eax, edi
0x18000b48d  mov     [rbp+2160h+var_21C4], ecx
0x18000b490  test    ecx, ecx
0x18000b492  jz      loc_18000B93D
0x18000b498  mov     rbx, [rbp+2160h+lpMem]
0x18000b49c  inc     eax
0x18000b49e  mov     r8d, 2
0x18000b4a4  mov     edx, eax
0x18000b4a6  mov     [rbp+2160h+var_21C8], eax
0x18000b4a9  mov     rcx, rbx
0x18000b4ac  call    TiffSeekToPage
0x18000b4b1  test    eax, eax
0x18000b4b3  jz      loc_18000BA6E
0x18000b4b9  mov     eax, [rbx+61Ch]
0x18000b4bf  mov     rcx, r15
0x18000b4c2  mov     [rsp+2260h+var_2210], eax
0x18000b4c6  call    TiffStartPage
0x18000b4cb  test    eax, eax
0x18000b4cd  jz      loc_18000BA6E
0x18000b4d3  mov     r14, qword ptr [rsp+2260h+dwSize+4]
0x18000b4d8  lea     r8, [rsp+2260h+dwSize]
0x18000b4dd  mov     rcx, [rbp+2160h+lpMem]
0x18000b4e1  mov     rbx, r14
0x18000b4e4  and     rbx, 0FFFFFFFFFFFFFFFCh
0x18000b4e8  mov     dword ptr [rsp+2260h+dwSize], esi
0x18000b4ec  mov     rdx, rbx
0x18000b4ef  mov     [rsp+2260h+var_21F0], rbx
0x18000b4f4  mov     rdi, rbx
0x18000b4f7  call    GetTiffBits
0x18000b4fc  xor     ecx, ecx
0x18000b4fe  test    eax, eax
0x18000b500  jnz     loc_18000B5D1
0x18000b506  cmp     dword ptr [rsp+2260h+dwSize], esi
0x18000b50a  jbe     loc_18000BA69
0x18000b510  mov     ebx, 8000h
0x18000b515  xor     edx, edx; dwSize
0x18000b517  mov     r8d, ebx; dwFreeType
0x18000b51a  mov     rcx, r14; lpAddress
0x18000b51d  call    cs:__imp_VirtualFree
0x18000b524  nop     dword ptr [rax+rax+00h]
0x18000b529  mov     r8d, ebx; dwFreeType
0x18000b52c  xor     edx, edx; dwSize
0x18000b52e  mov     rcx, r13; lpAddress
0x18000b531  call    cs:__imp_VirtualFree
0x18000b538  nop     dword ptr [rax+rax+00h]
0x18000b53d  mov     esi, dword ptr [rsp+2260h+dwSize]
0x18000b541  lea     ebx, [rsi+30D40h]
0x18000b547  mov     dword ptr [rbp+2160h+Size], ebx
0x18000b54a  cmp     ebx, esi
0x18000b54c  jb      loc_18000BA69
0x18000b552  xor     ecx, ecx; lpAddress
0x18000b554  mov     edx, esi; dwSize
0x18000b556  mov     r8d, 1000h; flAllocationType
0x18000b55c  lea     r9d, [rcx+4]; flProtect
0x18000b560  call    cs:__imp_VirtualAlloc
0x18000b567  nop     dword ptr [rax+rax+00h]
0x18000b56c  mov     qword ptr [rsp+2260h+dwSize+4], rax
0x18000b571  mov     r14, rax
0x18000b574  test    rax, rax
0x18000b577  jz      loc_18000BA8E
0x18000b57d  xor     ecx, ecx; lpAddress
0x18000b57f  mov     edx, ebx; dwSize
0x18000b581  mov     r8d, 1000h; flAllocationType
0x18000b587  lea     r9d, [rcx+4]; flProtect
0x18000b58b  call    cs:__imp_VirtualAlloc
0x18000b592  nop     dword ptr [rax+rax+00h]
0x18000b597  mov     [rbp+2160h+var_21B0], rax
0x18000b59b  mov     r13, rax
0x18000b59e  mov     rbx, r14
0x18000b5a1  test    rax, rax
0x18000b5a4  jz      loc_18000BA73
0x18000b5aa  mov     rcx, [rbp+2160h+lpMem]
0x18000b5ae  lea     r8, [rsp+2260h+dwSize]
0x18000b5b3  and     rbx, 0FFFFFFFFFFFFFFFCh
0x18000b5b7  mov     rdx, rbx
0x18000b5ba  mov     [rsp+2260h+var_21F0], rbx
0x18000b5bf  mov     rdi, rbx
0x18000b5c2  call    GetTiffBits
0x18000b5c7  xor     ecx, ecx
0x18000b5c9  test    eax, eax
0x18000b5cb  jz      loc_18000BA69
0x18000b5d1  mov     eax, dword ptr [rsp+2260h+dwSize]
0x18000b5d5  and     r13, 0FFFFFFFFFFFFFFFCh
  ... truncated ...
```
