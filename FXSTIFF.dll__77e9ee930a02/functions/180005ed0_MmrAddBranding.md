# MmrAddBranding

- ea: `0x180005ed0`
- end: `0x1800066ca`
- name: `MmrAddBranding`
- size: `2042`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, __int64, int)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops`

## callees

- `0x180003b38`
- `0x180004cbc`
- `0x1800053b8`
- `0x180005ed0`
- `0x180006aa4`
- `0x180006b18`
- `0x180007fd0`
- `0x180008070`
- `0x1800083a0`
- `0x180008b70`
- `0x180009600`
- `0x180009cd0`
- `0x180009ea0`
- `0x180009f04`
- `0x180009f34`
- `0x18000f128`
- `0x18000f1c8`
- `0x180018992`
- `0x18001899e`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180006055`
- `msvcrt!wcsrchr` at `0x180006055`
- `msvcrt!_wcsnset` at `0x180006077`
- `msvcrt!_wcsnset` at `0x180006077`
- `GDI32!DeleteObject` at `0x180006315`
- `GDI32!DeleteObject` at `0x180006315`
- `KERNEL32!DeleteFileW` at `0x180006608`
- `KERNEL32!DeleteFileW` at `0x180006630`
- `KERNEL32!DeleteFileW` at `0x180006608`
- `KERNEL32!DeleteFileW` at `0x180006630`
- `KERNEL32!GetLastError` at `0x180006577`
- `KERNEL32!GetLastError` at `0x180006577`
- `KERNEL32!SetLastError` at `0x180006546`
- `KERNEL32!SetLastError` at `0x1800065a1`
- `KERNEL32!SetLastError` at `0x1800066a7`
- `KERNEL32!SetLastError` at `0x180006546`
- `KERNEL32!SetLastError` at `0x1800065a1`
- `KERNEL32!SetLastError` at `0x1800066a7`
- `KERNEL32!VirtualAlloc` at `0x18000612f`
- `KERNEL32!VirtualAlloc` at `0x180006396`
- `KERNEL32!VirtualAlloc` at `0x18000612f`
- `KERNEL32!VirtualAlloc` at `0x180006396`
- `KERNEL32!VirtualFree` at `0x1800061b1`
- `KERNEL32!VirtualFree` at `0x18000637a`
- `KERNEL32!VirtualFree` at `0x1800065df`
- `KERNEL32!VirtualFree` at `0x1800061b1`
- `KERNEL32!VirtualFree` at `0x18000637a`
- `KERNEL32!VirtualFree` at `0x1800065df`
- `KERNEL32!MoveFileW` at `0x18000661b`
- `KERNEL32!MoveFileW` at `0x18000661b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // r12
  unsigned __int8 *v22; // r14
  int v23; // eax
  unsigned int v24; // ecx
  __int64 v25; // rax
  unsigned int v26; // ebx
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // r15
  int v29; // ebx
  LPVOID v30; // rbx
  __int64 v31; // rbx
  char v32; // bl
  unsigned __int64 v33; // rax
  unsigned __int8 *v34; // rax
  int v35; // eax
  unsigned __int8 *v36; // r9
  __int64 v37; // rax
  unsigned __int8 *v38; // r11
  unsigned int v39; // edx
  DWORD v40; // ecx
  _QWORD *v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rbx
  DWORD LastError; // eax
  unsigned int v45; // esi
  __int64 v47; // [rsp+30h] [rbp-81h]
  __int64 v48; // [rsp+38h] [rbp-79h] BYREF
  int v49; // [rsp+40h] [rbp-71h] BYREF
  unsigned __int8 *v50; // [rsp+48h] [rbp-69h] BYREF
  unsigned int v51; // [rsp+50h] [rbp-61h]
  int v52; // [rsp+54h] [rbp-5Dh]
  LPVOID v53; // [rsp+58h] [rbp-59h]
  int v54; // [rsp+60h] [rbp-51h]
  unsigned int v55; // [rsp+64h] [rbp-4Dh]
  unsigned __int64 v56; // [rsp+68h] [rbp-49h]
  __int128 v57; // [rsp+70h] [rbp-41h] BYREF
  __int128 v58; // [rsp+80h] [rbp-31h]
  void *Src; // [rsp+90h] [rbp-21h] BYREF
  HGDIOBJ ho; // [rsp+98h] [rbp-19h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-11h]
  void *lpMem; // [rsp+A8h] [rbp-9h]
  size_t Size; // [rsp+B0h] [rbp-1h]
  size_t v64; // [rsp+B8h] [rbp+7h]

  LODWORD(v48) = -1;
  v57 = 0;
  v5 = -1;
  v58 = 0;
  do
    ++v5;
  while ( a2[v5] );
  v61 = v5;
  HIDWORD(v48) = 0;
  v49 = 0;
  ho = 0;
  Src = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
  }
  v7 = (unsigned int *)TiffOpen(lpFileName, &v57, 1, 2u);
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
  v17 = (int)v57 / 8;
  v54 = (int)v57 / 8;
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
  v64 = 4 * v16 * v17;
  lpMem = (void *)pMemAlloc(v64);
  v20 = (unsigned __int64)lpMem;
  if ( !lpMem )
  {
    TiffClose(v7);
    pMemFree(v12);
    v19 = v18;
    goto LABEL_28;
  }
  v21 = DWORD1(v57) * ((unsigned __int64)(unsigned int)v57 >> 3);
  if ( v21 > 0xFFFFFFFF )
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
    pMemFree((LPVOID)v20);
    v8 = 534;
    goto LABEL_94;
  }
  v22 = (unsigned __int8 *)VirtualAlloc(0, (unsigned int)v21 + 4LL, 0x1000u, 4u);
  v23 = 0;
  if ( !v22 )
  {
    pMemFree(v12);
    pMemFree(v18);
    pMemFree((LPVOID)v20);
LABEL_12:
    TiffClose(v7);
LABEL_13:
    v8 = 8;
    goto LABEL_94;
  }
  LOBYTE(v23) = HIDWORD(v58) == 196;
  v53 = (LPVOID)TiffCreate(v12, v23);
  if ( !v53 )
  {
    pMemFree(v12);
    pMemFree(v18);
    pMemFree((LPVOID)v20);
    VirtualFree(v22, 0, 0x8000u);
    TiffClose(v7);
LABEL_8:
    v8 = 1627;
LABEL_94:
    SetLastError(v8);
    return 0;
  }
  if ( !DWORD2(v57) )
  {
LABEL_82:
    v52 = 1;
    goto LABEL_83;
  }
  v52 = 0;
  v24 = 0;
  v56 = v20 & 0xFFFFFFFFFFFFFFFCuLL;
  while ( 1 )
  {
    v51 = v24 + 1;
    if ( !(unsigned int)TiffSeekToPage((__int64)v7, v24 + 1, 2) || !(unsigned int)TiffStartPage(v53) )
    {
      SetLastError(0x65Bu);
LABEL_83:
      v28 = 0;
      goto LABEL_84;
    }
    memset_0(v18, 0, Size);
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)(a3 + 2 * v25) );
    LODWORD(v50) = v25 + v5 + 9;
    v26 = (unsigned int)v50;
    v27 = (unsigned __int16 *)pMemAlloc(2LL * (unsigned int)v50);
    v28 = v27;
    if ( !v27 )
      break;
    v29 = StringCchCopyW(v27, v26, a2);
    if ( v29 < 0 )
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_73;
      }
      v42 = 25;
      goto LABEL_72;
    }
    LODWORD(v47) = DWORD2(v57);
    v29 = StringCchPrintfW(
            &v28[(unsigned int)v61],
            (unsigned int)((_DWORD)v50 - v61),
            L"%03d %s %03d",
            v51,
            a3,
            v47,
            v48);
    if ( v29 < 0 )
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_73;
      }
      v42 = 26;
LABEL_72:
      WPP_SF_d(v41[2], v42, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, (unsigned int)v29);
LABEL_73:
      if ( (v29 & 0x1FFF0000) == 0x70000 )
        v29 = (unsigned __int16)v29;
      v40 = v29;
      goto LABEL_76;
    }
    if ( !(unsigned int)DrawBannerBitmap((_DWORD)v28, v57, a4, (unsigned int)&ho, (__int64)&Src) )
      goto LABEL_63;
    memcpy_0(v18, Src, (unsigned int)(a4 * v54));
    memset_0(lpMem, 0, v64);
    EncodeMmrBranding((_DWORD)v18, v56, a4 + 1, v57, (__int64)&v48 + 4, (__int64)&v49);
    DeleteObject(ho);
    v30 = v53;
    if ( !(unsigned int)TiffWriteRaw(v53, &v48, 4)
      || !(unsigned int)TiffWriteRaw(v30, v56, (unsigned int)(4 * HIDWORD(v48))) )
    {
      goto LABEL_63;
    }
    v31 = v7[388];
    v55 = v7[392];
    if ( (unsigned int)v31 > (unsigned int)v21 )
    {
      VirtualFree(v22, 0, 0x8000u);
      v22 = (unsigned __int8 *)VirtualAlloc(0, v31 + 4, 0x1000u, 4u);
      if ( !v22 )
      {
        v40 = 8;
LABEL_76:
        SetLastError(v40);
        goto LABEL_84;
      }
      LODWORD(v21) = v31;
    }
    v32 = v49;
    LODWORD(v50) = v21;
    if ( v49 )
    {
      if ( !(unsigned int)GetTiffBits((__int64)v7, v22 + 4, (unsigned int *)&v50) )
        goto LABEL_63;
      v36 = v22;
      v37 = (v7[388] >> 2) + 1;
      v50 = v22;
      v38 = &v22[4 * v37];
      *(_DWORD *)v22 = *(_DWORD *)(v56 + 4LL * HIDWORD(v48));
      if ( v22 < v38 )
      {
        do
        {
          v39 = *((_DWORD *)v36 + 1);
          *(_DWORD *)v36 += v39 << v32;
          v36 += 4;
          *(_DWORD *)v36 = v39 >> (32 - v32);
        }
        while ( v36 < v38 );
      }
      *((_DWORD *)v36 + 3) = 0x80000000;
      v35 = (_DWORD)v36 + 12 - (_DWORD)v22;
      *((_DWORD *)v36 + 1) = 0x80000000;
      *((_DWORD *)v36 + 2) = 0x80000000;
    }
    else
    {
      if ( !(unsigned int)GetTiffBits((__int64)v7, v22, (unsigned int *)&v50) )
        goto LABEL_63;
      v33 = (unsigned __int64)v7[388] >> 2;
      *(_DWORD *)&v22[4 * v33 + 4] = 0x80000000;
      *(_DWORD *)&v22[4 * v33 + 8] = 0x80000000;
      v34 = &v22[4 * v33 + 12];
      *(_DWORD *)v34 = 0x80000000;
      v35 = (_DWORD)v34 - (_DWORD)v22;
    }
    if ( !(unsigned int)TiffWriteRaw(v53, v22, v35 & 0xFFFFFFFC)
      || (*((_DWORD *)v53 + 212) = a4 + 33 + v55, !(unsigned int)TiffEndPage()) )
    {
LABEL_63:
      v40 = 1627;
      goto LABEL_76;
    }
    pMemFree(v28);
    v24 = v51;
    if ( v51 >= DWORD2(v57) )
      goto LABEL_82;
    LODWORD(v5) = v61;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v43 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    WPP_SF_d(v43, 24, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, LastError);
  }
LABEL_84:
  pMemFree(v28);
  pMemFree(v18);
  pMemFree(lpMem);
  VirtualFree(v22, 0, 0x8000u);
  TiffClose(v7);
  TiffClose(v53);
  v45 = v52;
  if ( v52 == 1 )
  {
    DeleteFileW(lpFileName);
    v45 = MoveFileW(v12, lpFileName);
  }
  if ( !v45 )
    DeleteFileW(v12);
  pMemFree(v12);
  return v45;
}

```

## disassembly

```asm
0x180005ed0  mov     rax, rsp
0x180005ed3  mov     [rax+20h], r9d
0x180005ed7  mov     [rax+18h], r8
0x180005edb  mov     [rax+10h], rdx
0x180005edf  mov     [rax+8], rcx
0x180005ee3  push    rbp
0x180005ee4  push    rbx
0x180005ee5  push    rsi
0x180005ee6  push    rdi
0x180005ee7  push    r12
0x180005ee9  push    r13
0x180005eeb  push    r14
0x180005eed  push    r15
0x180005eef  lea     rbp, [rax-5Fh]
0x180005ef3  sub     rsp, 0C8h
0x180005efa  xorps   xmm0, xmm0
0x180005efd  mov     [rbp+57h+var_D0], 0FFFFFFFFh
0x180005f04  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005f08  mov     r13d, r9d
0x180005f0b  movups  [rbp+57h+var_98], xmm0
0x180005f0f  mov     r15, rbx
0x180005f12  xor     r12d, r12d
0x180005f15  movups  [rbp+57h+var_88], xmm0
0x180005f19  mov     r14, rcx
0x180005f1c  inc     r15
0x180005f1f  cmp     [rdx+r15*2], r12w
0x180005f24  jnz     short loc_180005F1C
0x180005f26  mov     [rbp+57h+var_68], r15
0x180005f2a  mov     [rbp+57h+var_CC], r12d
0x180005f2e  mov     [rbp+57h+var_C8], r12d
0x180005f32  mov     [rbp+57h+ho], r12
0x180005f36  mov     [rbp+57h+Src], r12
0x180005f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f41  lea     rax, WPP_GLOBAL_Control
0x180005f48  cmp     rcx, rax
0x180005f4b  jz      short loc_180005F6E
0x180005f4d  test    byte ptr [rcx+1Ch], 2
0x180005f51  jz      short loc_180005F6E
0x180005f53  cmp     byte ptr [rcx+19h], 5
0x180005f57  jb      short loc_180005F6E
0x180005f59  mov     rcx, [rcx+10h]
0x180005f5d  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180005f64  mov     edx, 15h
0x180005f69  call    WPP_SF_
0x180005f6e  mov     r9d, 2
0x180005f74  lea     rdx, [rbp+57h+var_98]
0x180005f78  mov     rcx, r14; lpFileName
0x180005f7b  lea     r8d, [r9-1]
0x180005f7f  call    TiffOpen
0x180005f84  mov     rsi, rax
0x180005f87  test    rax, rax
0x180005f8a  jnz     short loc_180005F96
0x180005f8c  mov     ecx, 65Bh
0x180005f91  jmp     loc_1800066A7
0x180005f96  mov     rax, rbx
0x180005f99  inc     rax
0x180005f9c  cmp     [r14+rax*2], r12w
0x180005fa1  jnz     short loc_180005F99
0x180005fa3  inc     eax
0x180005fa5  mov     ebx, eax
0x180005fa7  lea     rcx, [rax+rax]; dwBytes
0x180005fab  call    pMemAlloc
0x180005fb0  mov     rdi, rax
0x180005fb3  test    rax, rax
0x180005fb6  jnz     short loc_180005FCA
0x180005fb8  mov     rcx, rsi; lpMem
0x180005fbb  call    TiffClose
0x180005fc0  mov     ecx, 8
0x180005fc5  jmp     loc_1800066A7
0x180005fca  mov     r8, r14; unsigned __int16 *
0x180005fcd  mov     rdx, rbx; unsigned __int64
0x180005fd0  mov     rcx, rdi; unsigned __int16 *
0x180005fd3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005fd8  mov     ebx, eax
0x180005fda  test    eax, eax
0x180005fdc  jns     short loc_18000603D
0x180005fde  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fe5  lea     rax, WPP_GLOBAL_Control
0x180005fec  cmp     rcx, rax
0x180005fef  jz      short loc_180006015
0x180005ff1  test    byte ptr [rcx+1Ch], 2
0x180005ff5  jz      short loc_180006015
0x180005ff7  cmp     byte ptr [rcx+19h], 2
0x180005ffb  jb      short loc_180006015
0x180005ffd  mov     rcx, [rcx+10h]
0x180006001  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180006008  mov     edx, 16h
0x18000600d  mov     r9d, ebx
0x180006010  call    WPP_SF_d
0x180006015  mov     rcx, rsi; lpMem
0x180006018  call    TiffClose
0x18000601d  mov     rcx, rdi; lpMem
0x180006020  call    pMemFree
0x180006025  mov     eax, ebx
0x180006027  and     eax, 1FFF0000h
0x18000602c  cmp     eax, 70000h
0x180006031  jnz     short loc_180006036
0x180006033  movzx   ebx, bx
0x180006036  mov     ecx, ebx
0x180006038  jmp     loc_1800066A7
0x18000603d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006041  inc     rax
0x180006044  cmp     [rdi+rax*2], r12w
0x180006049  jnz     short loc_180006041
0x18000604b  test    rax, rax
0x18000604e  jz      short loc_180006083
0x180006050  xor     edx, edx; Ch
0x180006052  mov     rcx, rdi; Str
0x180006055  call    cs:__imp_wcsrchr
0x18000605c  nop     dword ptr [rax+rax+00h]
0x180006061  cmp     rdi, rax
0x180006064  mov     edx, 24h ; '$'; Value
0x180006069  sbb     rcx, rcx
0x18000606c  lea     r8, [rax-2]
0x180006070  and     rcx, r8; String
0x180006073  lea     r8d, [rdx-23h]; MaxCount
0x180006077  call    cs:__imp__wcsnset
0x18000607e  nop     dword ptr [rax+rax+00h]
0x180006083  mov     eax, dword ptr [rbp+57h+var_98]
0x180006086  lea     ebx, [r13+1]
0x18000608a  cdq
0x18000608b  and     edx, 7
0x18000608e  add     eax, edx
0x180006090  sar     eax, 3
0x180006093  movsxd  r14, eax
0x180006096  mov     ecx, r14d
0x180006099  mov     [rbp+57h+var_A8], r14d
0x18000609d  imul    ecx, ebx; dwBytes
0x1800060a0  mov     eax, ecx
0x1800060a2  mov     [rbp+57h+Size], rax
0x1800060a6  call    pMemAlloc
0x1800060ab  mov     r13, rax
0x1800060ae  test    rax, rax
0x1800060b1  jnz     short loc_1800060C8
0x1800060b3  mov     rcx, rsi; lpMem
0x1800060b6  call    TiffClose
0x1800060bb  mov     rcx, rdi; lpMem
0x1800060be  call    pMemFree
0x1800060c3  jmp     loc_180005FC0
0x1800060c8  mov     eax, ebx
0x1800060ca  mov     rcx, r14
0x1800060cd  imul    rcx, rax
0x1800060d1  shl     rcx, 2; dwBytes
0x1800060d5  mov     [rbp+57h+var_50], rcx
0x1800060d9  call    pMemAlloc
0x1800060de  mov     [rbp+57h+lpMem], rax
0x1800060e2  mov     rbx, rax
0x1800060e5  test    rax, rax
0x1800060e8  jnz     short loc_1800060FF
0x1800060ea  mov     rcx, rsi; lpMem
0x1800060ed  call    TiffClose
0x1800060f2  mov     rcx, rdi; lpMem
0x1800060f5  call    pMemFree
0x1800060fa  mov     rcx, r13
0x1800060fd  jmp     short loc_1800060BE
0x1800060ff  mov     eax, dword ptr [rbp+57h+var_98+4]
0x180006102  mov     r12d, dword ptr [rbp+57h+var_98]
0x180006106  shr     r12, 3
0x18000610a  imul    r12, rax
0x18000610e  mov     eax, 0FFFFFFFFh
0x180006113  cmp     r12, rax
0x180006116  ja      loc_180006648
0x18000611c  xor     ecx, ecx; lpAddress
0x18000611e  mov     edx, r12d
0x180006121  add     rdx, 4; dwSize
0x180006125  mov     r8d, 1000h; flAllocationType
0x18000612b  lea     r9d, [rcx+4]; flProtect
0x18000612f  call    cs:__imp_VirtualAlloc
0x180006136  nop     dword ptr [rax+rax+00h]
0x18000613b  mov     r14, rax
0x18000613e  mov     rcx, rdi; lpFileName
0x180006141  xor     eax, eax
0x180006143  test    r14, r14
0x180006146  jnz     short loc_180006162
0x180006148  call    pMemFree
0x18000614d  mov     rcx, r13; lpMem
0x180006150  call    pMemFree
0x180006155  mov     rcx, rbx; lpMem
0x180006158  call    pMemFree
0x18000615d  jmp     loc_180005FB8
0x180006162  cmp     dword ptr [rbp+57h+var_88+0Ch], 0C4h
0x180006169  mov     r9d, 2
0x18000616f  mov     r8d, dword ptr [rbp+57h+var_98]
0x180006173  setz    al
0x180006176  mov     [rsp+100h+var_E0], eax; int
0x18000617a  lea     edx, [r9+2]
0x18000617e  call    TiffCreate
0x180006183  xor     edx, edx
0x180006185  mov     [rbp+57h+var_B0], rax
0x180006189  test    rax, rax
0x18000618c  jnz     short loc_1800061CA
0x18000618e  mov     rcx, rdi; lpMem
0x180006191  call    pMemFree
0x180006196  mov     rcx, r13; lpMem
0x180006199  call    pMemFree
0x18000619e  mov     rcx, rbx; lpMem
0x1800061a1  call    pMemFree
0x1800061a6  xor     edx, edx; dwSize
0x1800061a8  mov     r8d, 8000h; dwFreeType
0x1800061ae  mov     rcx, r14; lpAddress
0x1800061b1  call    cs:__imp_VirtualFree
0x1800061b8  nop     dword ptr [rax+rax+00h]
0x1800061bd  mov     rcx, rsi; lpMem
0x1800061c0  call    TiffClose
0x1800061c5  jmp     loc_180005F8C
0x1800061ca  cmp     dword ptr [rbp+57h+var_98+8], edx
0x1800061cd  jbe     loc_1800065AF
0x1800061d3  mov     rax, rbx
0x1800061d6  mov     [rbp+57h+var_B4], edx
0x1800061d9  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800061dd  mov     ecx, edx
0x1800061df  mov     [rbp+57h+var_A0], rax
0x1800061e3  xor     ebx, ebx
0x1800061e5  inc     ecx
0x1800061e7  mov     r8d, 2
0x1800061ed  mov     [rbp+57h+var_B8], ecx
0x1800061f0  mov     edx, ecx
0x1800061f2  mov     rcx, rsi
0x1800061f5  call    TiffSeekToPage
0x1800061fa  test    eax, eax
0x1800061fc  jz      loc_18000659C
0x180006202  mov     rcx, [rbp+57h+var_B0]
0x180006206  call    TiffStartPage
0x18000620b  test    eax, eax
0x18000620d  jz      loc_18000659C
0x180006213  mov     r8, [rbp+57h+Size]; Size
0x180006217  xor     edx, edx; Val
0x180006219  mov     rcx, r13; void *
0x18000621c  call    memset_0
0x180006221  mov     rcx, [rbp+57h+arg_10]
0x180006225  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006229  inc     rax
0x18000622c  cmp     [rcx+rax*2], bx
0x180006230  jnz     short loc_180006229
0x180006232  lea     ecx, [r15+9]
0x180006236  add     ecx, eax
0x180006238  mov     dword ptr [rbp+57h+var_C0], ecx
0x18000623b  mov     ebx, ecx
0x18000623d  add     rcx, rcx; dwBytes
0x180006240  call    pMemAlloc
0x180006245  mov     r15, rax
0x180006248  test    rax, rax
0x18000624b  jz      loc_180006554
0x180006251  mov     r8, [rbp+57h+arg_8]; unsigned __int16 *
0x180006255  mov     edx, ebx; unsigned __int64
0x180006257  mov     rcx, rax; unsigned __int16 *
0x18000625a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000625f  mov     ebx, eax
0x180006261  test    eax, eax
0x180006263  js      loc_1800064FC
0x180006269  mov     rcx, [rbp+57h+var_68]
0x18000626d  lea     r8, a03dS03d; "%03d %s %03d"
0x180006274  mov     edx, dword ptr [rbp+57h+var_C0]
0x180006277  mov     r9d, [rbp+57h+var_B8]
0x18000627b  sub     edx, ecx; unsigned __int64
0x18000627d  mov     eax, ecx
0x18000627f  lea     rcx, [r15+rax*2]; unsigned __int16 *
0x180006283  mov     eax, dword ptr [rbp+57h+var_98+8]
0x180006286  mov     [rsp+28h], eax
0x18000628a  mov     rax, [rbp+57h+arg_10]
0x18000628e  mov     qword ptr [rsp+100h+var_E0], rax
0x180006293  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006298  mov     ebx, eax
0x18000629a  test    eax, eax
0x18000629c  js      loc_1800064D6
0x1800062a2  mov     ebx, [rbp+57h+arg_18]
0x1800062a5  lea     rax, [rbp+57h+Src]
0x1800062a9  mov     edx, dword ptr [rbp+57h+var_98]
0x1800062ac  lea     r9, [rbp+57h+ho]
0x1800062b0  mov     r8d, ebx
0x1800062b3  mov     qword ptr [rsp+100h+var_E0], rax
0x1800062b8  mov     rcx, r15
0x1800062bb  call    DrawBannerBitmap
0x1800062c0  test    eax, eax
0x1800062c2  jz      loc_1800064CF
0x1800062c8  mov     r8d, [rbp+57h+var_A8]
0x1800062cc  mov     rcx, r13; void *
0x1800062cf  mov     rdx, [rbp+57h+Src]; Src
0x1800062d3  imul    r8d, ebx; Size
0x1800062d7  call    memcpy_0
0x1800062dc  mov     r8, [rbp+57h+var_50]; Size
0x1800062e0  xor     edx, edx; Val
0x1800062e2  mov     rcx, [rbp+57h+lpMem]; void *
0x1800062e6  call    memset_0
0x1800062eb  mov     r9d, dword ptr [rbp+57h+var_98]
0x1800062ef  lea     rax, [rbp+57h+var_C8]
0x1800062f3  mov     rdx, [rbp+57h+var_A0]
0x1800062f7  lea     r8d, [rbx+1]
0x1800062fb  mov     [rsp+28h], rax
0x180006300  mov     rcx, r13
0x180006303  lea     rax, [rbp+57h+var_CC]
0x180006307  mov     qword ptr [rsp+100h+var_E0], rax
0x18000630c  call    EncodeMmrBranding
0x180006311  mov     rcx, [rbp+57h+ho]; ho
0x180006315  call    cs:__imp_DeleteObject
0x18000631c  nop     dword ptr [rax+rax+00h]
0x180006321  mov     rbx, [rbp+57h+var_B0]
0x180006325  lea     rdx, [rbp+57h+var_D0]
0x180006329  mov     rcx, rbx
0x18000632c  mov     r8d, 4
  ... truncated ...
```
