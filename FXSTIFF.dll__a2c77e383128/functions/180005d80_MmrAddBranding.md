# MmrAddBranding

- ea: `0x180005d80`
- end: `0x18000651f`
- name: `MmrAddBranding`
- size: `1951`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, __int64, int)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops`

## callees

- `0x180003b00`
- `0x180004c48`
- `0x1800052e0`
- `0x180005d80`
- `0x1800068c0`
- `0x180006934`
- `0x180007cd0`
- `0x180007d60`
- `0x180008060`
- `0x1800087a0`
- `0x1800091a0`
- `0x180009860`
- `0x180009a20`
- `0x180009a7c`
- `0x180009aa4`
- `0x18000ea18`
- `0x18000eac0`
- `0x180017bc2`
- `0x180017bce`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180005f05`
- `msvcrt!wcsrchr` at `0x180005f05`
- `msvcrt!_wcsnset` at `0x180005f21`
- `msvcrt!_wcsnset` at `0x180005f21`
- `GDI32!DeleteObject` at `0x1800061ad`
- `GDI32!DeleteObject` at `0x1800061ad`
- `KERNEL32!DeleteFileW` at `0x180006476`
- `KERNEL32!DeleteFileW` at `0x180006492`
- `KERNEL32!DeleteFileW` at `0x180006476`
- `KERNEL32!DeleteFileW` at `0x180006492`
- `KERNEL32!GetLastError` at `0x1800063f7`
- `KERNEL32!GetLastError` at `0x1800063f7`
- `KERNEL32!SetLastError` at `0x1800063cc`
- `KERNEL32!SetLastError` at `0x18000641b`
- `KERNEL32!SetLastError` at `0x180006503`
- `KERNEL32!SetLastError` at `0x1800063cc`
- `KERNEL32!SetLastError` at `0x18000641b`
- `KERNEL32!SetLastError` at `0x180006503`
- `KERNEL32!VirtualAlloc` at `0x180005fd3`
- `KERNEL32!VirtualAlloc` at `0x180006222`
- `KERNEL32!VirtualAlloc` at `0x180005fd3`
- `KERNEL32!VirtualAlloc` at `0x180006222`
- `KERNEL32!VirtualFree` at `0x18000604f`
- `KERNEL32!VirtualFree` at `0x18000620c`
- `KERNEL32!VirtualFree` at `0x180006453`
- `KERNEL32!VirtualFree` at `0x18000604f`
- `KERNEL32!VirtualFree` at `0x18000620c`
- `KERNEL32!VirtualFree` at `0x180006453`
- `KERNEL32!MoveFileW` at `0x180006483`
- `KERNEL32!MoveFileW` at `0x180006483`

## pseudocode

```c
__int64 __fastcall MmrAddBranding(LPCWSTR lpFileName, const unsigned __int16 *a2, __int64 a3, int a4)
{
  __int64 v5; // r15
  unsigned int *v7; // rsi
  DWORD v8; // ecx
  __int64 v9; // rax
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
  int v13; // ebx
  __int64 v14; // rax
  wchar_t *v15; // rax
  unsigned int v16; // ebx
  __int64 v17; // r14
  unsigned __int16 *v18; // r13
  unsigned __int16 *v19; // rcx
  unsigned __int64 v20; // r12
  unsigned int *v21; // r14
  int v22; // eax
  unsigned int v23; // ecx
  __int64 v24; // rax
  unsigned int v25; // ebx
  unsigned __int16 *v26; // rax
  unsigned __int16 *v27; // r15
  int v28; // ebx
  LPVOID v29; // rbx
  __int64 v30; // rbx
  char v31; // bl
  unsigned __int64 v32; // rax
  unsigned int *v33; // rax
  int v34; // eax
  unsigned int *v35; // r9
  __int64 v36; // rax
  unsigned int *v37; // r11
  unsigned int v38; // edx
  DWORD v39; // ecx
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rbx
  DWORD LastError; // eax
  unsigned int v44; // esi
  __int64 v46; // [rsp+30h] [rbp-81h]
  __int64 v47; // [rsp+38h] [rbp-79h] BYREF
  int v48; // [rsp+40h] [rbp-71h] BYREF
  unsigned int *v49; // [rsp+48h] [rbp-69h] BYREF
  unsigned int v50; // [rsp+50h] [rbp-61h]
  int v51; // [rsp+54h] [rbp-5Dh]
  LPVOID v52; // [rsp+58h] [rbp-59h]
  int v53; // [rsp+60h] [rbp-51h]
  unsigned int v54; // [rsp+64h] [rbp-4Dh]
  unsigned __int64 v55; // [rsp+68h] [rbp-49h]
  __int128 v56; // [rsp+70h] [rbp-41h]
  __int128 v57; // [rsp+80h] [rbp-31h]
  void *Src; // [rsp+90h] [rbp-21h] BYREF
  HGDIOBJ ho; // [rsp+98h] [rbp-19h] BYREF
  __int64 v60; // [rsp+A0h] [rbp-11h]
  void *lpMem; // [rsp+A8h] [rbp-9h]
  size_t Size; // [rsp+B0h] [rbp-1h]
  size_t v63; // [rsp+B8h] [rbp+7h]

  LODWORD(v47) = -1;
  v56 = 0;
  v5 = -1;
  v57 = 0;
  do
    ++v5;
  while ( a2[v5] );
  v60 = v5;
  HIDWORD(v47) = 0;
  v48 = 0;
  ho = 0;
  Src = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
  }
  v7 = (unsigned int *)TiffOpen(lpFileName);
  if ( !v7 )
    goto LABEL_8;
  v9 = -1;
  do
    ++v9;
  while ( lpFileName[v9] );
  v10 = (unsigned int)(v9 + 1);
  v11 = (unsigned __int16 *)pMemAlloc(2 * v10);
  v12 = v11;
  if ( !v11 )
    goto LABEL_12;
  v13 = StringCchCopyW(v11, v10, lpFileName);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids,
        (unsigned int)v13);
    }
    TiffClose(v7);
    pMemFree(v12);
    if ( (v13 & 0x1FFF0000) == 0x70000 )
      v13 = (unsigned __int16)v13;
    v8 = v13;
    goto LABEL_94;
  }
  v14 = -1;
  do
    ++v14;
  while ( v12[v14] );
  if ( v14 )
  {
    v15 = wcsrchr(v12, 0);
    _wcsnset((wchar_t *)((unsigned __int64)(v15 - 1) & -(__int64)(v12 < v15)), 0x24u, 1u);
  }
  v16 = a4 + 1;
  v17 = (int)v56 / 8;
  v53 = (int)v56 / 8;
  Size = (unsigned int)((a4 + 1) * v17);
  v18 = (unsigned __int16 *)pMemAlloc(Size);
  if ( !v18 )
  {
    TiffClose(v7);
    v19 = v12;
LABEL_28:
    pMemFree(v19);
    goto LABEL_13;
  }
  v63 = 4 * v16 * v17;
  lpMem = (void *)pMemAlloc(v63);
  if ( !lpMem )
  {
    TiffClose(v7);
    pMemFree(v12);
    v19 = v18;
    goto LABEL_28;
  }
  v20 = DWORD1(v56) * ((unsigned __int64)(unsigned int)v56 >> 3);
  if ( v20 > 0xFFFFFFFF )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, 2147942934LL);
    }
    TiffClose(v7);
    pMemFree(v12);
    pMemFree(v18);
    pMemFree(lpMem);
    v8 = 534;
    goto LABEL_94;
  }
  v21 = (unsigned int *)VirtualAlloc(0, (unsigned int)v20 + 4LL, 0x1000u, 4u);
  v22 = 0;
  if ( !v21 )
  {
    pMemFree(v12);
    pMemFree(v18);
    pMemFree(lpMem);
LABEL_12:
    TiffClose(v7);
LABEL_13:
    v8 = 8;
    goto LABEL_94;
  }
  LOBYTE(v22) = HIDWORD(v57) == 196;
  v52 = (LPVOID)TiffCreate(v12, v22);
  if ( !v52 )
  {
    pMemFree(v12);
    pMemFree(v18);
    pMemFree(lpMem);
    VirtualFree(v21, 0, 0x8000u);
    TiffClose(v7);
LABEL_8:
    v8 = 1627;
LABEL_94:
    SetLastError(v8);
    return 0;
  }
  if ( !DWORD2(v56) )
  {
LABEL_82:
    v51 = 1;
    goto LABEL_83;
  }
  v51 = 0;
  v23 = 0;
  v55 = (unsigned __int64)lpMem & 0xFFFFFFFFFFFFFFFCuLL;
  while ( 1 )
  {
    v50 = v23 + 1;
    if ( !(unsigned int)TiffSeekToPage(v7, v23 + 1, 2) || !(unsigned int)TiffStartPage(v52) )
    {
      SetLastError(0x65Bu);
LABEL_83:
      v27 = 0;
      goto LABEL_84;
    }
    memset_0(v18, 0, Size);
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(a3 + 2 * v24) );
    LODWORD(v49) = v24 + v5 + 9;
    v25 = (unsigned int)v49;
    v26 = (unsigned __int16 *)pMemAlloc(2LL * (unsigned int)v49);
    v27 = v26;
    if ( !v26 )
      break;
    v28 = StringCchCopyW(v26, v25, a2);
    if ( v28 < 0 )
    {
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_73;
      }
      v41 = 25;
      goto LABEL_72;
    }
    LODWORD(v46) = DWORD2(v56);
    v28 = StringCchPrintfW(
            &v27[(unsigned int)v60],
            (unsigned int)((_DWORD)v49 - v60),
            L"%03d %s %03d",
            v50,
            a3,
            v46,
            v47);
    if ( v28 < 0 )
    {
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_73;
      }
      v41 = 26;
LABEL_72:
      WPP_SF_d(v40[2], v41, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, (unsigned int)v28);
LABEL_73:
      if ( (v28 & 0x1FFF0000) == 0x70000 )
        v28 = (unsigned __int16)v28;
      v39 = v28;
      goto LABEL_76;
    }
    if ( !(unsigned int)DrawBannerBitmap((_DWORD)v27, v56, a4, (unsigned int)&ho, (__int64)&Src) )
      goto LABEL_63;
    memcpy_0(v18, Src, (unsigned int)(a4 * v53));
    memset_0(lpMem, 0, v63);
    EncodeMmrBranding((_DWORD)v18, v55, a4 + 1, v56, (__int64)&v47 + 4, (__int64)&v48);
    DeleteObject(ho);
    v29 = v52;
    if ( !(unsigned int)TiffWriteRaw(v52, &v47, 4)
      || !(unsigned int)TiffWriteRaw(v29, v55, (unsigned int)(4 * HIDWORD(v47))) )
    {
      goto LABEL_63;
    }
    v30 = v7[388];
    v54 = v7[392];
    if ( (unsigned int)v30 > (unsigned int)v20 )
    {
      VirtualFree(v21, 0, 0x8000u);
      v21 = (unsigned int *)VirtualAlloc(0, v30 + 4, 0x1000u, 4u);
      if ( !v21 )
      {
        v39 = 8;
LABEL_76:
        SetLastError(v39);
        goto LABEL_84;
      }
      LODWORD(v20) = v30;
    }
    v31 = v48;
    LODWORD(v49) = v20;
    if ( v48 )
    {
      if ( !(unsigned int)GetTiffBits(v7, v21 + 1, &v49) )
        goto LABEL_63;
      v35 = v21;
      v36 = (v7[388] >> 2) + 1;
      v49 = v21;
      v37 = &v21[v36];
      *v21 = *(_DWORD *)(v55 + 4LL * HIDWORD(v47));
      if ( v21 < v37 )
      {
        do
        {
          v38 = v35[1];
          *v35++ += v38 << v31;
          *v35 = v38 >> (32 - v31);
        }
        while ( v35 < v37 );
      }
      v35[3] = 0x80000000;
      v34 = (_DWORD)v35 + 12 - (_DWORD)v21;
      v35[1] = 0x80000000;
      v35[2] = 0x80000000;
    }
    else
    {
      if ( !(unsigned int)GetTiffBits(v7, v21, &v49) )
        goto LABEL_63;
      v32 = (unsigned __int64)v7[388] >> 2;
      v21[v32 + 1] = 0x80000000;
      v21[v32 + 2] = 0x80000000;
      v33 = &v21[v32 + 3];
      *v33 = 0x80000000;
      v34 = (_DWORD)v33 - (_DWORD)v21;
    }
    if ( !(unsigned int)TiffWriteRaw(v52, v21, v34 & 0xFFFFFFFC)
      || (*((_DWORD *)v52 + 212) = a4 + 33 + v54, !(unsigned int)TiffEndPage()) )
    {
LABEL_63:
      v39 = 1627;
      goto LABEL_76;
    }
    pMemFree(v27);
    v23 = v50;
    if ( v50 >= DWORD2(v56) )
      goto LABEL_82;
    LODWORD(v5) = v60;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v42 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    WPP_SF_d(v42, 24, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, LastError);
  }
LABEL_84:
  pMemFree(v27);
  pMemFree(v18);
  pMemFree(lpMem);
  VirtualFree(v21, 0, 0x8000u);
  TiffClose(v7);
  TiffClose(v52);
  v44 = v51;
  if ( v51 == 1 )
  {
    DeleteFileW(lpFileName);
    v44 = MoveFileW(v12, lpFileName);
  }
  if ( !v44 )
    DeleteFileW(v12);
  pMemFree(v12);
  return v44;
}

```

## disassembly

```asm
0x180005d80  mov     rax, rsp
0x180005d83  mov     [rax+20h], r9d
0x180005d87  mov     [rax+18h], r8
0x180005d8b  mov     [rax+10h], rdx
0x180005d8f  mov     [rax+8], rcx
0x180005d93  push    rbp
0x180005d94  push    rbx
0x180005d95  push    rsi
0x180005d96  push    rdi
0x180005d97  push    r12
0x180005d99  push    r13
0x180005d9b  push    r14
0x180005d9d  push    r15
0x180005d9f  lea     rbp, [rax-5Fh]
0x180005da3  sub     rsp, 0C8h
0x180005daa  xorps   xmm0, xmm0
0x180005dad  mov     [rbp+57h+var_D0], 0FFFFFFFFh
0x180005db4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005db8  mov     r13d, r9d
0x180005dbb  movups  [rbp+57h+var_98], xmm0
0x180005dbf  mov     r15, rbx
0x180005dc2  xor     r12d, r12d
0x180005dc5  movups  [rbp+57h+var_88], xmm0
0x180005dc9  mov     r14, rcx
0x180005dcc  inc     r15
0x180005dcf  cmp     [rdx+r15*2], r12w
0x180005dd4  jnz     short loc_180005DCC
0x180005dd6  mov     [rbp+57h+var_68], r15
0x180005dda  mov     [rbp+57h+var_CC], r12d
0x180005dde  mov     [rbp+57h+var_C8], r12d
0x180005de2  mov     [rbp+57h+ho], r12
0x180005de6  mov     [rbp+57h+Src], r12
0x180005dea  mov     rcx, cs:WPP_GLOBAL_Control
0x180005df1  lea     rax, WPP_GLOBAL_Control
0x180005df8  cmp     rcx, rax
0x180005dfb  jz      short loc_180005E1E
0x180005dfd  test    byte ptr [rcx+1Ch], 2
0x180005e01  jz      short loc_180005E1E
0x180005e03  cmp     byte ptr [rcx+19h], 5
0x180005e07  jb      short loc_180005E1E
0x180005e09  mov     rcx, [rcx+10h]
0x180005e0d  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180005e14  mov     edx, 15h
0x180005e19  call    WPP_SF_
0x180005e1e  mov     r9d, 2
0x180005e24  lea     rdx, [rbp+57h+var_98]
0x180005e28  mov     rcx, r14; lpFileName
0x180005e2b  lea     r8d, [r9-1]
0x180005e2f  call    TiffOpen
0x180005e34  mov     rsi, rax
0x180005e37  test    rax, rax
0x180005e3a  jnz     short loc_180005E46
0x180005e3c  mov     ecx, 65Bh
0x180005e41  jmp     loc_180006503
0x180005e46  mov     rax, rbx
0x180005e49  inc     rax
0x180005e4c  cmp     [r14+rax*2], r12w
0x180005e51  jnz     short loc_180005E49
0x180005e53  inc     eax
0x180005e55  mov     ebx, eax
0x180005e57  lea     rcx, [rax+rax]; dwBytes
0x180005e5b  call    pMemAlloc
0x180005e60  mov     rdi, rax
0x180005e63  test    rax, rax
0x180005e66  jnz     short loc_180005E7A
0x180005e68  mov     rcx, rsi; lpMem
0x180005e6b  call    TiffClose
0x180005e70  mov     ecx, 8
0x180005e75  jmp     loc_180006503
0x180005e7a  mov     r8, r14; unsigned __int16 *
0x180005e7d  mov     rdx, rbx; unsigned __int64
0x180005e80  mov     rcx, rdi; unsigned __int16 *
0x180005e83  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005e88  mov     ebx, eax
0x180005e8a  test    eax, eax
0x180005e8c  jns     short loc_180005EED
0x180005e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e95  lea     rax, WPP_GLOBAL_Control
0x180005e9c  cmp     rcx, rax
0x180005e9f  jz      short loc_180005EC5
0x180005ea1  test    byte ptr [rcx+1Ch], 2
0x180005ea5  jz      short loc_180005EC5
0x180005ea7  cmp     byte ptr [rcx+19h], 2
0x180005eab  jb      short loc_180005EC5
0x180005ead  mov     rcx, [rcx+10h]
0x180005eb1  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180005eb8  mov     edx, 16h
0x180005ebd  mov     r9d, ebx
0x180005ec0  call    WPP_SF_d
0x180005ec5  mov     rcx, rsi; lpMem
0x180005ec8  call    TiffClose
0x180005ecd  mov     rcx, rdi; lpMem
0x180005ed0  call    pMemFree
0x180005ed5  mov     eax, ebx
0x180005ed7  and     eax, 1FFF0000h
0x180005edc  cmp     eax, 70000h
0x180005ee1  jnz     short loc_180005EE6
0x180005ee3  movzx   ebx, bx
0x180005ee6  mov     ecx, ebx
0x180005ee8  jmp     loc_180006503
0x180005eed  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005ef1  inc     rax
0x180005ef4  cmp     [rdi+rax*2], r12w
0x180005ef9  jnz     short loc_180005EF1
0x180005efb  test    rax, rax
0x180005efe  jz      short loc_180005F27
0x180005f00  xor     edx, edx; Ch
0x180005f02  mov     rcx, rdi; Str
0x180005f05  call    cs:__imp_wcsrchr
0x180005f0b  cmp     rdi, rax
0x180005f0e  mov     edx, 24h ; '$'; Value
0x180005f13  sbb     rcx, rcx
0x180005f16  lea     r8, [rax-2]
0x180005f1a  and     rcx, r8; String
0x180005f1d  lea     r8d, [rdx-23h]; MaxCount
0x180005f21  call    cs:__imp__wcsnset
0x180005f27  mov     eax, dword ptr [rbp+57h+var_98]
0x180005f2a  lea     ebx, [r13+1]
0x180005f2e  cdq
0x180005f2f  and     edx, 7
0x180005f32  add     eax, edx
0x180005f34  sar     eax, 3
0x180005f37  movsxd  r14, eax
0x180005f3a  mov     ecx, r14d
0x180005f3d  mov     [rbp+57h+var_A8], r14d
0x180005f41  imul    ecx, ebx; dwBytes
0x180005f44  mov     eax, ecx
0x180005f46  mov     [rbp+57h+Size], rax
0x180005f4a  call    pMemAlloc
0x180005f4f  mov     r13, rax
0x180005f52  test    rax, rax
0x180005f55  jnz     short loc_180005F6C
0x180005f57  mov     rcx, rsi; lpMem
0x180005f5a  call    TiffClose
0x180005f5f  mov     rcx, rdi; lpMem
0x180005f62  call    pMemFree
0x180005f67  jmp     loc_180005E70
0x180005f6c  mov     eax, ebx
0x180005f6e  mov     rcx, r14
0x180005f71  imul    rcx, rax
0x180005f75  shl     rcx, 2; dwBytes
0x180005f79  mov     [rbp+57h+var_50], rcx
0x180005f7d  call    pMemAlloc
0x180005f82  mov     [rbp+57h+lpMem], rax
0x180005f86  mov     rbx, rax
0x180005f89  test    rax, rax
0x180005f8c  jnz     short loc_180005FA3
0x180005f8e  mov     rcx, rsi; lpMem
0x180005f91  call    TiffClose
0x180005f96  mov     rcx, rdi; lpMem
0x180005f99  call    pMemFree
0x180005f9e  mov     rcx, r13
0x180005fa1  jmp     short loc_180005F62
0x180005fa3  mov     eax, dword ptr [rbp+57h+var_98+4]
0x180005fa6  mov     r12d, dword ptr [rbp+57h+var_98]
0x180005faa  shr     r12, 3
0x180005fae  imul    r12, rax
0x180005fb2  mov     eax, 0FFFFFFFFh
0x180005fb7  cmp     r12, rax
0x180005fba  ja      loc_1800064A4
0x180005fc0  xor     ecx, ecx; lpAddress
0x180005fc2  mov     edx, r12d
0x180005fc5  add     rdx, 4; dwSize
0x180005fc9  mov     r8d, 1000h; flAllocationType
0x180005fcf  lea     r9d, [rcx+4]; flProtect
0x180005fd3  call    cs:__imp_VirtualAlloc
0x180005fd9  mov     r14, rax
0x180005fdc  mov     rcx, rdi; lpFileName
0x180005fdf  xor     eax, eax
0x180005fe1  test    r14, r14
0x180005fe4  jnz     short loc_180006000
0x180005fe6  call    pMemFree
0x180005feb  mov     rcx, r13; lpMem
0x180005fee  call    pMemFree
0x180005ff3  mov     rcx, rbx; lpMem
0x180005ff6  call    pMemFree
0x180005ffb  jmp     loc_180005E68
0x180006000  cmp     dword ptr [rbp+57h+var_88+0Ch], 0C4h
0x180006007  mov     r9d, 2
0x18000600d  mov     r8d, dword ptr [rbp+57h+var_98]
0x180006011  setz    al
0x180006014  mov     [rsp+100h+var_E0], eax; int
0x180006018  lea     edx, [r9+2]
0x18000601c  call    TiffCreate
0x180006021  xor     edx, edx
0x180006023  mov     [rbp+57h+var_B0], rax
0x180006027  test    rax, rax
0x18000602a  jnz     short loc_180006062
0x18000602c  mov     rcx, rdi; lpMem
0x18000602f  call    pMemFree
0x180006034  mov     rcx, r13; lpMem
0x180006037  call    pMemFree
0x18000603c  mov     rcx, rbx; lpMem
0x18000603f  call    pMemFree
0x180006044  xor     edx, edx; dwSize
0x180006046  mov     r8d, 8000h; dwFreeType
0x18000604c  mov     rcx, r14; lpAddress
0x18000604f  call    cs:__imp_VirtualFree
0x180006055  mov     rcx, rsi; lpMem
0x180006058  call    TiffClose
0x18000605d  jmp     loc_180005E3C
0x180006062  cmp     dword ptr [rbp+57h+var_98+8], edx
0x180006065  jbe     loc_180006423
0x18000606b  mov     rax, rbx
0x18000606e  mov     [rbp+57h+var_B4], edx
0x180006071  and     rax, 0FFFFFFFFFFFFFFFCh
0x180006075  mov     ecx, edx
0x180006077  mov     [rbp+57h+var_A0], rax
0x18000607b  xor     ebx, ebx
0x18000607d  inc     ecx
0x18000607f  mov     r8d, 2
0x180006085  mov     [rbp+57h+var_B8], ecx
0x180006088  mov     edx, ecx
0x18000608a  mov     rcx, rsi
0x18000608d  call    TiffSeekToPage
0x180006092  test    eax, eax
0x180006094  jz      loc_180006416
0x18000609a  mov     rcx, [rbp+57h+var_B0]
0x18000609e  call    TiffStartPage
0x1800060a3  test    eax, eax
0x1800060a5  jz      loc_180006416
0x1800060ab  mov     r8, [rbp+57h+Size]; Size
0x1800060af  xor     edx, edx; Val
0x1800060b1  mov     rcx, r13; void *
0x1800060b4  call    memset_0
0x1800060b9  mov     rcx, [rbp+57h+arg_10]
0x1800060bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800060c1  inc     rax
0x1800060c4  cmp     [rcx+rax*2], bx
0x1800060c8  jnz     short loc_1800060C1
0x1800060ca  lea     ecx, [r15+9]
0x1800060ce  add     ecx, eax
0x1800060d0  mov     dword ptr [rbp+57h+var_C0], ecx
0x1800060d3  mov     ebx, ecx
0x1800060d5  add     rcx, rcx; dwBytes
0x1800060d8  call    pMemAlloc
0x1800060dd  mov     r15, rax
0x1800060e0  test    rax, rax
0x1800060e3  jz      loc_1800063D4
0x1800060e9  mov     r8, [rbp+57h+arg_8]; unsigned __int16 *
0x1800060ed  mov     edx, ebx; unsigned __int64
0x1800060ef  mov     rcx, rax; unsigned __int16 *
0x1800060f2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800060f7  mov     ebx, eax
0x1800060f9  test    eax, eax
0x1800060fb  js      loc_180006382
0x180006101  mov     rcx, [rbp+57h+var_68]
0x180006105  lea     r8, a03dS03d; "%03d %s %03d"
0x18000610c  mov     edx, dword ptr [rbp+57h+var_C0]
0x18000610f  mov     r9d, [rbp+57h+var_B8]
0x180006113  sub     edx, ecx; unsigned __int64
0x180006115  mov     eax, ecx
0x180006117  lea     rcx, [r15+rax*2]; unsigned __int16 *
0x18000611b  mov     eax, dword ptr [rbp+57h+var_98+8]
0x18000611e  mov     [rsp+28h], eax
0x180006122  mov     rax, [rbp+57h+arg_10]
0x180006126  mov     qword ptr [rsp+100h+var_E0], rax
0x18000612b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006130  mov     ebx, eax
0x180006132  test    eax, eax
0x180006134  js      loc_18000635C
0x18000613a  mov     ebx, [rbp+57h+arg_18]
0x18000613d  lea     rax, [rbp+57h+Src]
0x180006141  mov     edx, dword ptr [rbp+57h+var_98]
0x180006144  lea     r9, [rbp+57h+ho]
0x180006148  mov     r8d, ebx
0x18000614b  mov     qword ptr [rsp+100h+var_E0], rax
0x180006150  mov     rcx, r15
0x180006153  call    DrawBannerBitmap
0x180006158  test    eax, eax
0x18000615a  jz      loc_180006355
0x180006160  mov     r8d, [rbp+57h+var_A8]
0x180006164  mov     rcx, r13; void *
0x180006167  mov     rdx, [rbp+57h+Src]; Src
0x18000616b  imul    r8d, ebx; Size
0x18000616f  call    memcpy_0
0x180006174  mov     r8, [rbp+57h+var_50]; Size
0x180006178  xor     edx, edx; Val
0x18000617a  mov     rcx, [rbp+57h+lpMem]; void *
0x18000617e  call    memset_0
0x180006183  mov     r9d, dword ptr [rbp+57h+var_98]
0x180006187  lea     rax, [rbp+57h+var_C8]
0x18000618b  mov     rdx, [rbp+57h+var_A0]
0x18000618f  lea     r8d, [rbx+1]
0x180006193  mov     [rsp+28h], rax
0x180006198  mov     rcx, r13
0x18000619b  lea     rax, [rbp+57h+var_CC]
0x18000619f  mov     qword ptr [rsp+100h+var_E0], rax
0x1800061a4  call    EncodeMmrBranding
0x1800061a9  mov     rcx, [rbp+57h+ho]; ho
0x1800061ad  call    cs:__imp_DeleteObject
0x1800061b3  mov     rbx, [rbp+57h+var_B0]
0x1800061b7  lea     rdx, [rbp+57h+var_D0]
0x1800061bb  mov     rcx, rbx
0x1800061be  mov     r8d, 4
0x1800061c4  call    TiffWriteRaw
0x1800061c9  test    eax, eax
0x1800061cb  jz      loc_180006355
0x1800061d1  mov     r8d, [rbp+57h+var_CC]
0x1800061d5  mov     rcx, rbx
  ... truncated ...
```
