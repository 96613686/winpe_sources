# PostProcessMhToMmr

- ea: `0x18000ac38`
- end: `0x18000b5fe`
- name: `PostProcessMhToMmr`
- size: `2502`
- prototype: `__int64 __fastcall(WCHAR *, unsigned int *, WCHAR *)`
- caller_count: `2`
- callee_count: `16`
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
- `0x18000ac38`
- `0x180017bce`
- `0x180017c00`
- `0x180017c90`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18000aec0`
- `KERNEL32!DeleteFileW` at `0x18000b5a8`
- `KERNEL32!DeleteFileW` at `0x18000b5cb`
- `KERNEL32!DeleteFileW` at `0x18000aec0`
- `KERNEL32!DeleteFileW` at `0x18000b5a8`
- `KERNEL32!DeleteFileW` at `0x18000b5cb`
- `KERNEL32!SetLastError` at `0x18000ae0b`
- `KERNEL32!SetLastError` at `0x18000aead`
- `KERNEL32!SetLastError` at `0x18000ae0b`
- `KERNEL32!SetLastError` at `0x18000aead`
- `KERNEL32!VirtualAlloc` at `0x18000af38`
- `KERNEL32!VirtualAlloc` at `0x18000af5d`
- `KERNEL32!VirtualAlloc` at `0x18000b042`
- `KERNEL32!VirtualAlloc` at `0x18000b067`
- `KERNEL32!VirtualAlloc` at `0x18000af38`
- `KERNEL32!VirtualAlloc` at `0x18000af5d`
- `KERNEL32!VirtualAlloc` at `0x18000b042`
- `KERNEL32!VirtualAlloc` at `0x18000b067`
- `KERNEL32!VirtualFree` at `0x18000b00b`
- `KERNEL32!VirtualFree` at `0x18000b019`
- `KERNEL32!VirtualFree` at `0x18000b554`
- `KERNEL32!VirtualFree` at `0x18000b56e`
- `KERNEL32!VirtualFree` at `0x18000b00b`
- `KERNEL32!VirtualFree` at `0x18000b019`
- `KERNEL32!VirtualFree` at `0x18000b554`
- `KERNEL32!VirtualFree` at `0x18000b56e`
- `KERNEL32!MoveFileW` at `0x18000b5b9`
- `KERNEL32!MoveFileW` at `0x18000b5b9`
- `KERNEL32!GetTempPath2W` at `0x18000ad40`
- `KERNEL32!GetTempPath2W` at `0x18000ad40`
- `KERNEL32!GetTempFileNameW` at `0x18000ad63`
- `KERNEL32!GetTempFileNameW` at `0x18000ad63`

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
  _DWORD dwSize[3]; // [rsp+44h] [rbp-BCh] BYREF
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
    if ( !(unsigned int)TiffSeekToPage(v28, v27 + 1, 2) )
      goto LABEL_108;
    v61 = v28[391];
    if ( !(unsigned int)TiffStartPage(v23) )
      goto LABEL_108;
    v29 = *(_QWORD *)&dwSize[1];
    v30 = *(_QWORD *)&dwSize[1] & 0xFFFFFFFFFFFFFFFCuLL;
    dwSize[0] = v24;
    v66 = *(_QWORD *)&dwSize[1] & 0xFFFFFFFFFFFFFFFCuLL;
    v31 = dwSize[1] & 0xFFFFFFFC;
    if ( !(unsigned int)GetTiffBits(lpMem, *(_QWORD *)&dwSize[1] & 0xFFFFFFFFFFFFFFFCuLL, dwSize) )
    {
      if ( dwSize[0] <= (unsigned int)v24 )
        goto LABEL_107;
      VirtualFree((LPVOID)v29, 0, 0x8000u);
      VirtualFree((LPVOID)v26, 0, 0x8000u);
      LODWORD(v24) = dwSize[0];
      v32 = dwSize[0] + 200000;
      LODWORD(Size) = dwSize[0] + 200000;
      if ( (unsigned int)(dwSize[0] + 200000) < dwSize[0] )
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
      if ( !(unsigned int)GetTiffBits(lpMem, v29 & 0xFFFFFFFFFFFFFFFCuLL, dwSize) )
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
          if ( !v41 && ++dwSize[0] >= 5u )
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
        if ( ++dwSize[0] < 5u )
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
0x18000ac38  mov     [rsp-8+arg_10], rbx
0x18000ac3d  push    rbp
0x18000ac3e  push    rsi
0x18000ac3f  push    rdi
0x18000ac40  push    r12
0x18000ac42  push    r13
0x18000ac44  push    r14
0x18000ac46  push    r15
0x18000ac48  lea     rbp, [rsp-2130h]
0x18000ac50  mov     eax, 2230h
0x18000ac55  call    _alloca_probe
0x18000ac5a  sub     rsp, rax
0x18000ac5d  mov     rax, cs:__security_cookie
0x18000ac64  xor     rax, rsp
0x18000ac67  mov     [rbp+2160h+var_40], rax
0x18000ac6e  mov     r13, r8
0x18000ac71  mov     [rbp+2160h+var_21A0], r8
0x18000ac75  mov     r14, rdx
0x18000ac78  mov     [rbp+2160h+lpMem], rcx
0x18000ac7c  mov     r15, rcx
0x18000ac7f  mov     ebx, 208h
0x18000ac84  mov     r8d, ebx; Size
0x18000ac87  lea     rcx, [rbp+2160h+TempFileName]; void *
0x18000ac8b  xor     edx, edx; Val
0x18000ac8d  call    memset_0
0x18000ac92  mov     r8d, ebx; Size
0x18000ac95  lea     rcx, [rbp+2160h+PathName]; void *
0x18000ac9c  xor     edx, edx; Val
0x18000ac9e  call    memset_0
0x18000aca3  mov     r8d, ebx; Size
0x18000aca6  lea     rcx, [rbp+2160h+FileName]; void *
0x18000acad  xor     edx, edx; Val
0x18000acaf  call    memset_0
0x18000acb4  mov     ebx, 0D84h
0x18000acb9  lea     rcx, [rbp+2160h+var_1B5E]; void *
0x18000acc0  mov     r8d, ebx; Size
0x18000acc3  xor     edx, edx; Val
0x18000acc5  call    memset_0
0x18000acca  mov     r8d, ebx; Size
0x18000accd  lea     rcx, [rbp+2160h+var_DCE]; void *
0x18000acd4  xor     edx, edx; Val
0x18000acd6  call    memset_0
0x18000acdb  mov     r10, cs:WPP_GLOBAL_Control
0x18000ace2  lea     r11, WPP_GLOBAL_Control
0x18000ace9  cmp     r10, r11
0x18000acec  jz      short loc_18000AD1F
0x18000acee  test    byte ptr [r10+1Ch], 2
0x18000acf3  jz      short loc_18000AD1F
0x18000acf5  cmp     byte ptr [r10+19h], 5
0x18000acfa  jb      short loc_18000AD1F
0x18000acfc  mov     rcx, [r10+10h]
0x18000ad00  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000ad07  mov     edx, 22h ; '"'
0x18000ad0c  call    WPP_SF_
0x18000ad11  mov     r10, cs:WPP_GLOBAL_Control
0x18000ad18  lea     r11, WPP_GLOBAL_Control
0x18000ad1f  xor     r12d, r12d
0x18000ad22  mov     esi, 7FFFFFFEh
0x18000ad27  mov     edi, 104h
0x18000ad2c  mov     ebx, 1
0x18000ad31  test    r13, r13
0x18000ad34  jnz     short loc_18000AD7D
0x18000ad36  lea     rdx, [rbp+2160h+PathName]
0x18000ad3d  lea     ecx, [rdi-1]
0x18000ad40  call    cs:__imp_GetTempPath2W
0x18000ad46  test    eax, eax
0x18000ad48  jz      loc_18000AE11
0x18000ad4e  lea     r9, [rbp+2160h+TempFileName]; lpTempFileName
0x18000ad52  xor     r8d, r8d; uUnique
0x18000ad55  lea     rdx, PrefixString; "Fxs"
0x18000ad5c  lea     rcx, [rbp+2160h+PathName]; lpPathName
0x18000ad63  call    cs:__imp_GetTempFileNameW
0x18000ad69  test    eax, eax
0x18000ad6b  jz      loc_18000AE11
0x18000ad71  mov     r10, cs:WPP_GLOBAL_Control
0x18000ad78  jmp     loc_18000AE1D
0x18000ad7d  mov     rax, rsi
0x18000ad80  lea     r8, [rbp+2160h+TempFileName]
0x18000ad84  mov     rcx, r13
0x18000ad87  mov     rdx, rdi
0x18000ad8a  test    rax, rax
0x18000ad8d  jz      short loc_18000ADAD
0x18000ad8f  movzx   r9d, word ptr [rcx]
0x18000ad93  test    r9w, r9w
0x18000ad97  jz      short loc_18000ADAD
0x18000ad99  mov     [r8], r9w
0x18000ad9d  add     rcx, 2
0x18000ada1  add     r8, 2
0x18000ada5  sub     rax, rbx
0x18000ada8  sub     rdx, rbx
0x18000adab  jnz     short loc_18000AD8A
0x18000adad  mov     rax, rdx
0x18000adb0  lea     rcx, [r8-2]
0x18000adb4  neg     rax
0x18000adb7  sbb     ebx, ebx
0x18000adb9  not     ebx
0x18000adbb  and     ebx, 8007007Ah
0x18000adc1  test    rdx, rdx
0x18000adc4  cmovnz  rcx, r8
0x18000adc8  mov     [rcx], r12w
0x18000adcc  jnz     short loc_18000AE18
0x18000adce  cmp     r10, r11
0x18000add1  jz      short loc_18000ADF9
0x18000add3  test    byte ptr [r10+1Ch], 2
0x18000add8  jz      short loc_18000ADF9
0x18000adda  cmp     byte ptr [r10+19h], 2
0x18000addf  jb      short loc_18000ADF9
0x18000ade1  mov     rcx, [r10+10h]
0x18000ade5  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000adec  mov     edx, 23h ; '#'
0x18000adf1  mov     r9d, ebx
0x18000adf4  call    WPP_SF_d
0x18000adf9  mov     eax, ebx
0x18000adfb  movzx   ecx, bx
0x18000adfe  and     eax, 1FFF0000h
0x18000ae03  cmp     eax, 70000h
0x18000ae08  cmovnz  ecx, ebx; dwErrCode
0x18000ae0b  call    cs:__imp_SetLastError
0x18000ae11  xor     eax, eax
0x18000ae13  jmp     loc_18000B5D4
0x18000ae18  mov     ebx, 1
0x18000ae1d  lea     rax, [r15+2Ch]
0x18000ae21  lea     rdx, [rbp+2160h+FileName]
0x18000ae28  test    rsi, rsi
0x18000ae2b  jz      short loc_18000AE48
0x18000ae2d  movzx   ecx, word ptr [rax]
0x18000ae30  test    cx, cx
0x18000ae33  jz      short loc_18000AE48
0x18000ae35  mov     [rdx], cx
0x18000ae38  add     rax, 2
0x18000ae3c  add     rdx, 2
0x18000ae40  sub     rsi, rbx
0x18000ae43  sub     rdi, rbx
0x18000ae46  jnz     short loc_18000AE28
0x18000ae48  mov     rax, rdi
0x18000ae4b  lea     rcx, [rdx-2]
0x18000ae4f  neg     rax
0x18000ae52  sbb     ebx, ebx
0x18000ae54  not     ebx
0x18000ae56  and     ebx, 8007007Ah
0x18000ae5c  test    rdi, rdi
0x18000ae5f  cmovnz  rcx, rdx
0x18000ae63  mov     [rcx], r12w
0x18000ae67  jnz     short loc_18000AECB
0x18000ae69  lea     rax, WPP_GLOBAL_Control
0x18000ae70  cmp     r10, rax
0x18000ae73  jz      short loc_18000AE9B
0x18000ae75  test    byte ptr [r10+1Ch], 2
0x18000ae7a  jz      short loc_18000AE9B
0x18000ae7c  cmp     byte ptr [r10+19h], 2
0x18000ae81  jb      short loc_18000AE9B
0x18000ae83  mov     rcx, [r10+10h]
0x18000ae87  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000ae8e  mov     edx, 24h ; '$'
0x18000ae93  mov     r9d, ebx
0x18000ae96  call    WPP_SF_d
0x18000ae9b  mov     eax, ebx
0x18000ae9d  movzx   ecx, bx
0x18000aea0  and     eax, 1FFF0000h
0x18000aea5  cmp     eax, 70000h
0x18000aeaa  cmovnz  ecx, ebx; dwErrCode
0x18000aead  call    cs:__imp_SetLastError
0x18000aeb3  test    r13, r13
0x18000aeb6  jnz     loc_18000AE11
0x18000aebc  lea     rcx, [rbp+2160h+TempFileName]; lpFileName
0x18000aec0  call    cs:__imp_DeleteFileW
0x18000aec6  jmp     loc_18000AE11
0x18000aecb  mov     r8d, [r14]
0x18000aece  lea     rcx, [rbp+2160h+TempFileName]; lpFileName
0x18000aed2  xor     edi, edi
0x18000aed4  cmp     dword ptr [r14+1Ch], 0C4h
0x18000aedc  mov     eax, edi
0x18000aede  setz    al
0x18000aee1  lea     r9d, [rdi+2]
0x18000aee5  mov     [rsp+2260h+var_2240], eax; int
0x18000aee9  lea     edx, [rdi+4]
0x18000aeec  call    TiffCreate
0x18000aef1  mov     r15, rax
0x18000aef4  test    rax, rax
0x18000aef7  jz      loc_18000B578
0x18000aefd  mov     ecx, [r14]
0x18000af00  mov     eax, 0FFFFFFFFh
0x18000af05  shr     rcx, 3
0x18000af09  imul    rsi, rcx, 960h
0x18000af10  cmp     rsi, rax
0x18000af13  ja      loc_18000B578
0x18000af19  lea     edi, [rsi+30D40h]
0x18000af1f  mov     dword ptr [rbp+2160h+Size], edi
0x18000af22  cmp     edi, esi
0x18000af24  jb      loc_18000B578
0x18000af2a  xor     ecx, ecx; lpAddress
0x18000af2c  mov     edx, esi; dwSize
0x18000af2e  mov     r8d, 1000h; flAllocationType
0x18000af34  lea     r9d, [rcx+4]; flProtect
0x18000af38  call    cs:__imp_VirtualAlloc
0x18000af3e  mov     qword ptr [rsp+2260h+dwSize+4], rax
0x18000af43  mov     rbx, rax
0x18000af46  test    rax, rax
0x18000af49  jz      loc_18000B578
0x18000af4f  xor     ecx, ecx; lpAddress
0x18000af51  mov     edx, edi; dwSize
0x18000af53  mov     r8d, 1000h; flAllocationType
0x18000af59  lea     r9d, [rcx+4]; flProtect
0x18000af5d  call    cs:__imp_VirtualAlloc
0x18000af63  xor     edi, edi
0x18000af65  mov     [rbp+2160h+var_21B0], rax
0x18000af69  mov     r13, rax
0x18000af6c  test    rax, rax
0x18000af6f  jz      loc_18000B549
0x18000af75  mov     ecx, [r14+8]
0x18000af79  mov     eax, edi
0x18000af7b  mov     [rbp+2160h+var_21C4], ecx
0x18000af7e  test    ecx, ecx
0x18000af80  jz      loc_18000B413
0x18000af86  mov     rbx, [rbp+2160h+lpMem]
0x18000af8a  inc     eax
0x18000af8c  mov     r8d, 2
0x18000af92  mov     edx, eax
0x18000af94  mov     [rbp+2160h+var_21C8], eax
0x18000af97  mov     rcx, rbx
0x18000af9a  call    TiffSeekToPage
0x18000af9f  test    eax, eax
0x18000afa1  jz      loc_18000B544
0x18000afa7  mov     eax, [rbx+61Ch]
0x18000afad  mov     rcx, r15
0x18000afb0  mov     [rsp+2260h+var_2210], eax
0x18000afb4  call    TiffStartPage
0x18000afb9  test    eax, eax
0x18000afbb  jz      loc_18000B544
0x18000afc1  mov     r14, qword ptr [rsp+2260h+dwSize+4]
0x18000afc6  lea     r8, [rsp+2260h+dwSize]
0x18000afcb  mov     rcx, [rbp+2160h+lpMem]
0x18000afcf  mov     rbx, r14
0x18000afd2  and     rbx, 0FFFFFFFFFFFFFFFCh
0x18000afd6  mov     dword ptr [rsp+2260h+dwSize], esi
0x18000afda  mov     rdx, rbx
0x18000afdd  mov     [rsp+2260h+var_21F0], rbx
0x18000afe2  mov     rdi, rbx
0x18000afe5  call    GetTiffBits
0x18000afea  xor     ecx, ecx
0x18000afec  test    eax, eax
0x18000afee  jnz     loc_18000B0A7
0x18000aff4  cmp     dword ptr [rsp+2260h+dwSize], esi
0x18000aff8  jbe     loc_18000B53F
0x18000affe  mov     ebx, 8000h
0x18000b003  xor     edx, edx; dwSize
0x18000b005  mov     r8d, ebx; dwFreeType
0x18000b008  mov     rcx, r14; lpAddress
0x18000b00b  call    cs:__imp_VirtualFree
0x18000b011  mov     r8d, ebx; dwFreeType
0x18000b014  xor     edx, edx; dwSize
0x18000b016  mov     rcx, r13; lpAddress
0x18000b019  call    cs:__imp_VirtualFree
0x18000b01f  mov     esi, dword ptr [rsp+2260h+dwSize]
0x18000b023  lea     ebx, [rsi+30D40h]
0x18000b029  mov     dword ptr [rbp+2160h+Size], ebx
0x18000b02c  cmp     ebx, esi
0x18000b02e  jb      loc_18000B53F
0x18000b034  xor     ecx, ecx; lpAddress
0x18000b036  mov     edx, esi; dwSize
0x18000b038  mov     r8d, 1000h; flAllocationType
0x18000b03e  lea     r9d, [rcx+4]; flProtect
0x18000b042  call    cs:__imp_VirtualAlloc
0x18000b048  mov     qword ptr [rsp+2260h+dwSize+4], rax
0x18000b04d  mov     r14, rax
0x18000b050  test    rax, rax
0x18000b053  jz      loc_18000B55E
0x18000b059  xor     ecx, ecx; lpAddress
0x18000b05b  mov     edx, ebx; dwSize
0x18000b05d  mov     r8d, 1000h; flAllocationType
0x18000b063  lea     r9d, [rcx+4]; flProtect
0x18000b067  call    cs:__imp_VirtualAlloc
0x18000b06d  mov     [rbp+2160h+var_21B0], rax
0x18000b071  mov     r13, rax
0x18000b074  mov     rbx, r14
0x18000b077  test    rax, rax
0x18000b07a  jz      loc_18000B549
0x18000b080  mov     rcx, [rbp+2160h+lpMem]
0x18000b084  lea     r8, [rsp+2260h+dwSize]
0x18000b089  and     rbx, 0FFFFFFFFFFFFFFFCh
0x18000b08d  mov     rdx, rbx
0x18000b090  mov     [rsp+2260h+var_21F0], rbx
0x18000b095  mov     rdi, rbx
0x18000b098  call    GetTiffBits
0x18000b09d  xor     ecx, ecx
0x18000b09f  test    eax, eax
0x18000b0a1  jz      loc_18000B53F
0x18000b0a7  mov     eax, dword ptr [rsp+2260h+dwSize]
0x18000b0ab  and     r13, 0FFFFFFFFFFFFFFFCh
0x18000b0af  shr     rax, 2
0x18000b0b3  xor     edx, edx; Val
0x18000b0b5  mov     [rsp+2260h+var_2220], cl
0x18000b0b9  mov     [rsp+2260h+var_221F], cl
0x18000b0bd  mov     rcx, r13; void *
0x18000b0c0  mov     [rbp+2160h+var_2198], r13
0x18000b0c4  lea     rax, [rbx+rax*4]
0x18000b0c8  mov     [rbp+2160h+var_21E0], r13
0x18000b0cc  mov     ebx, dword ptr [rbp+2160h+Size]
0x18000b0cf  mov     r8d, ebx; Size
0x18000b0d2  mov     [rbp+2160h+var_21C0], rax
  ... truncated ...
```
