# TiffOpen

- ea: `0x1800087a0`
- end: `0x180008c7a`
- name: `TiffOpen`
- size: `1242`
- prototype: `char *__fastcall(LPCWSTR lpFileName, _DWORD *, int, unsigned int)`
- caller_count: `9`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800044f0`
- `0x180005380`
- `0x180005b00`
- `0x180005d80`
- `0x180006530`
- `0x1800082c0`
- `0x180009070`
- `0x18000d310`
- `0x18000e530`

## callees

- `0x1800056fc`
- `0x1800087a0`
- `0x1800091a0`
- `0x180009a7c`
- `0x180009aa4`
- `0x18000ea18`
- `0x18000eac0`
- `0x180012ad4`
- `0x180017bce`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000881e`
- `KERNEL32!GetLastError` at `0x180008b95`
- `KERNEL32!GetLastError` at `0x18000881e`
- `KERNEL32!GetLastError` at `0x180008b95`
- `KERNEL32!UnmapViewOfFile` at `0x180008bf6`
- `KERNEL32!UnmapViewOfFile` at `0x180008bf6`
- `KERNEL32!SetLastError` at `0x180008c62`
- `KERNEL32!SetLastError` at `0x180008c62`
- `KERNEL32!MapViewOfFile` at `0x1800088e2`
- `KERNEL32!MapViewOfFile` at `0x1800088e2`
- `KERNEL32!CreateFileMappingW` at `0x1800088b7`
- `KERNEL32!CreateFileMappingW` at `0x1800088b7`
- `KERNEL32!GetFileSize` at `0x180008873`
- `KERNEL32!GetFileSize` at `0x180008873`
- `KERNEL32!CloseHandle` at `0x180008c09`
- `KERNEL32!CloseHandle` at `0x180008c16`
- `KERNEL32!CloseHandle` at `0x180008c09`
- `KERNEL32!CloseHandle` at `0x180008c16`

## pseudocode

```c
char *__fastcall TiffOpen(LPCWSTR lpFileName, _DWORD *a2, int a3, unsigned int a4)
{
  char *v8; // rax
  char *v9; // rdi
  unsigned int LastError; // ebx
  void *File; // rax
  DWORD FileSize; // eax
  HANDLE FileMappingW; // rax
  LPVOID v14; // rax
  __int64 v15; // rax
  _WORD *v16; // r8
  __int64 v17; // rdx
  _WORD *v18; // rcx
  __int64 v19; // rcx
  unsigned int v20; // ebx
  LPVOID *i; // rax
  LPVOID *v22; // rax
  LPVOID **v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  const void *v26; // rcx
  void *v27; // rcx
  LPVOID *v28; // rsi
  LPVOID *v29; // rcx
  LPVOID **v30; // rax
  LPVOID lpMem[2]; // [rsp+40h] [rbp-10h] BYREF

  *(_OWORD *)lpMem = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
  }
  lpMem[1] = lpMem;
  lpMem[0] = lpMem;
  v8 = (char *)pMemAlloc(0x6A0u);
  v9 = v8;
  if ( !v8 )
    goto LABEL_6;
  memset_0(v8, 0, 0x6A0u);
  File = (void *)InternalSafeCreateFile(lpFileName, a3 != 0 ? 0x80000000 : -1073741824, 1u, 3u, 0);
  *(_QWORD *)v9 = File;
  if ( File == (void *)-1LL )
    goto LABEL_6;
  FileSize = GetFileSize(File, 0);
  *((_DWORD *)v9 + 416) = FileSize;
  if ( FileSize == -1 )
    goto LABEL_6;
  if ( FileSize <= 8 )
  {
    LastError = 87;
LABEL_57:
    if ( (unsigned __int64)(*(_QWORD *)v9 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v26 = (const void *)*((_QWORD *)v9 + 2);
      if ( v26 )
      {
        UnmapViewOfFile(v26);
        *((_QWORD *)v9 + 2) = 0;
      }
      v27 = (void *)*((_QWORD *)v9 + 1);
      if ( v27 )
      {
        CloseHandle(v27);
        *((_QWORD *)v9 + 1) = 0;
      }
      CloseHandle(*(HANDLE *)v9);
      *(_QWORD *)v9 = 0;
    }
    pMemFree(v9);
    v9 = 0;
    goto LABEL_64;
  }
  FileMappingW = CreateFileMappingW(*(HANDLE *)v9, 0, a3 != 0 ? 134217730 : 134217732, 0, 0, 0);
  *((_QWORD *)v9 + 1) = FileMappingW;
  if ( !FileMappingW || (v14 = MapViewOfFile(FileMappingW, a3 != 0 ? 4 : 6, 0, 0, 0), (*((_QWORD *)v9 + 2) = v14) == 0) )
  {
LABEL_6:
    LastError = GetLastError();
    goto LABEL_53;
  }
  v15 = 2147483646;
  v16 = v9 + 44;
  v17 = 260;
  do
  {
    if ( !v15 )
      break;
    if ( !*lpFileName )
      break;
    *v16++ = *lpFileName++;
    --v15;
    --v17;
  }
  while ( v17 );
  v18 = v16 - 1;
  LastError = v17 == 0 ? 0x8007007A : 0;
  if ( v17 )
    v18 = v16;
  *v18 = 0;
  if ( !v17 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, LastError);
    }
    if ( (LastError & 0x1FFF0000) == 0x70000 )
      LastError = (unsigned __int16)LastError;
LABEL_53:
    if ( !LastError || !v9 )
      goto LABEL_64;
    goto LABEL_57;
  }
  v19 = **((_QWORD **)v9 + 2);
  *(_QWORD *)(v9 + 564) = v19;
  if ( (_WORD)v19 != 18761
    || *((_WORD *)v9 + 283) != 42
    || (v20 = *((_DWORD *)v9 + 142)) == 0
    || !(unsigned int)IsValidIFDOffset(v20, v9) )
  {
LABEL_56:
    LastError = 11;
    goto LABEL_57;
  }
  do
  {
    for ( i = (LPVOID *)lpMem[0]; i != lpMem; i = (LPVOID *)*i )
    {
      if ( *((_DWORD *)i + 4) == v20 )
      {
        LastError = 11;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
        }
        goto LABEL_57;
      }
    }
    v22 = (LPVOID *)pMemAlloc(0x18u);
    if ( !v22 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
      }
      goto LABEL_53;
    }
    *((_DWORD *)v22 + 4) = v20;
    v23 = (LPVOID **)lpMem[1];
    v22[1] = lpMem[1];
    *v22 = lpMem;
    *v23 = v22;
    lpMem[1] = v22;
    v24 = *((_QWORD *)v9 + 2);
    v25 = v20 + 12 * *(unsigned __int16 *)(v20 + v24) + 2;
    if ( (unsigned int)v25 < v20 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
      }
      LastError = 534;
      goto LABEL_57;
    }
    v20 = *(_DWORD *)(v25 + v24);
    if ( !(unsigned int)IsValidIFDOffset(v20, v9) )
      goto LABEL_56;
    ++*((_DWORD *)v9 + 209);
  }
  while ( v20 );
  *((_DWORD *)v9 + 211) = *((_DWORD *)v9 + 142);
  *((_DWORD *)v9 + 407) = a4;
  if ( !(unsigned int)TiffSeekToPage(v9, 1, a4) )
    goto LABEL_56;
  a2[2] = *((_DWORD *)v9 + 209);
  *a2 = *((_DWORD *)v9 + 391);
  LastError = 0;
  a2[1] = *((_DWORD *)v9 + 392);
  a2[3] = *((_DWORD *)v9 + 406);
  a2[6] = *((_DWORD *)v9 + 407);
  a2[7] = *((_DWORD *)v9 + 421);
  a2[5] = *((_DWORD *)v9 + 213);
  *((_QWORD *)v9 + 189) = v9 + 1076;
  *((_QWORD *)v9 + 190) = v9 + 860;
  *((_DWORD *)v9 + 382) = 1;
  memset_0(v9 + 860, 0, 0x288u);
LABEL_64:
  v28 = (LPVOID *)lpMem[0];
  while ( v28 != lpMem )
  {
    v29 = v28;
    v28 = (LPVOID *)*v28;
    v30 = (LPVOID **)v29[1];
    *v30 = v28;
    v28[1] = v30;
    *v29 = 0;
    v29[1] = 0;
    pMemFree(v29);
  }
  if ( LastError )
    SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x1800087a0  push    rbp
0x1800087a2  push    rbx
0x1800087a3  push    rsi
0x1800087a4  push    rdi
0x1800087a5  push    r12
0x1800087a7  push    r14
0x1800087a9  push    r15
0x1800087ab  mov     rbp, rsp
0x1800087ae  sub     rsp, 50h
0x1800087b2  xorps   xmm0, xmm0
0x1800087b5  mov     r15d, r9d
0x1800087b8  movups  xmmword ptr [rbp+lpMem], xmm0
0x1800087bc  mov     esi, r8d
0x1800087bf  mov     r14, rdx
0x1800087c2  mov     rbx, rcx
0x1800087c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087cc  lea     rax, WPP_GLOBAL_Control
0x1800087d3  cmp     rcx, rax
0x1800087d6  jz      short loc_1800087F9
0x1800087d8  test    byte ptr [rcx+1Ch], 2
0x1800087dc  jz      short loc_1800087F9
0x1800087de  cmp     byte ptr [rcx+19h], 5
0x1800087e2  jb      short loc_1800087F9
0x1800087e4  mov     rcx, [rcx+10h]
0x1800087e8  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x1800087ef  mov     edx, 0Dh
0x1800087f4  call    WPP_SF_
0x1800087f9  lea     rax, [rbp+lpMem]
0x1800087fd  mov     ecx, 6A0h; dwBytes
0x180008802  mov     [rbp+lpMem+8], rax
0x180008806  lea     rax, [rbp+lpMem]
0x18000880a  mov     [rbp+lpMem], rax
0x18000880e  call    pMemAlloc
0x180008813  xor     r12d, r12d
0x180008816  mov     rdi, rax
0x180008819  test    rax, rax
0x18000881c  jnz     short loc_18000882B
0x18000881e  call    cs:__imp_GetLastError
0x180008824  mov     ebx, eax
0x180008826  jmp     loc_180008BD1
0x18000882b  xor     edx, edx; Val
0x18000882d  mov     r8d, 6A0h; Size
0x180008833  mov     rcx, rdi; void *
0x180008836  call    memset_0
0x18000883b  mov     eax, esi
0x18000883d  mov     dword ptr [rsp+50h+lpName], r12d; int
0x180008842  neg     eax
0x180008844  mov     [rsp+50h+dwMaximumSizeLow], 3; DWORD
0x18000884c  mov     eax, 0C0000000h
0x180008851  mov     r8d, 1; dwShareMode
0x180008857  sbb     edx, edx
0x180008859  mov     rcx, rbx; lpFileName
0x18000885c  and     edx, eax
0x18000885e  add     edx, eax; dwDesiredAccess
0x180008860  call    InternalSafeCreateFile
0x180008865  mov     [rdi], rax
0x180008868  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000886c  jz      short loc_18000881E
0x18000886e  xor     edx, edx; lpFileSizeHigh
0x180008870  mov     rcx, rax; hFile
0x180008873  call    cs:__imp_GetFileSize
0x180008879  mov     [rdi+680h], eax
0x18000887f  cmp     eax, 0FFFFFFFFh
0x180008882  jz      short loc_18000881E
0x180008884  cmp     eax, 8
0x180008887  ja      short loc_180008893
0x180008889  mov     ebx, 57h ; 'W'
0x18000888e  jmp     loc_180008BE1
0x180008893  mov     rcx, [rdi]; hFile
0x180008896  mov     eax, esi
0x180008898  neg     eax
0x18000889a  mov     [rsp+50h+lpName], r12; lpName
0x18000889f  mov     [rsp+50h+dwMaximumSizeLow], r12d; dwMaximumSizeLow
0x1800088a4  sbb     r8d, r8d
0x1800088a7  xor     r9d, r9d; dwMaximumSizeHigh
0x1800088aa  and     r8d, 0FFFFFFFEh
0x1800088ae  xor     edx, edx; lpFileMappingAttributes
0x1800088b0  add     r8d, 8000004h; flProtect
0x1800088b7  call    cs:__imp_CreateFileMappingW
0x1800088bd  mov     [rdi+8], rax
0x1800088c1  test    rax, rax
0x1800088c4  jz      loc_18000881E
0x1800088ca  neg     esi
0x1800088cc  mov     qword ptr [rsp+50h+dwMaximumSizeLow], r12; dwNumberOfBytesToMap
0x1800088d1  mov     rcx, rax; hFileMappingObject
0x1800088d4  sbb     edx, edx
0x1800088d6  xor     r9d, r9d; dwFileOffsetLow
0x1800088d9  and     edx, 0FFFFFFFEh
0x1800088dc  xor     r8d, r8d; dwFileOffsetHigh
0x1800088df  add     edx, 6; dwDesiredAccess
0x1800088e2  call    cs:__imp_MapViewOfFile
0x1800088e8  mov     [rdi+10h], rax
0x1800088ec  test    rax, rax
0x1800088ef  jz      loc_18000881E
0x1800088f5  mov     eax, 7FFFFFFEh
0x1800088fa  lea     r8, [rdi+2Ch]
0x1800088fe  mov     edx, 104h
0x180008903  test    rax, rax
0x180008906  jz      short loc_180008925
0x180008908  movzx   ecx, word ptr [rbx]
0x18000890b  test    cx, cx
0x18000890e  jz      short loc_180008925
0x180008910  mov     [r8], cx
0x180008914  add     rbx, 2
0x180008918  add     r8, 2
0x18000891c  dec     rax
0x18000891f  sub     rdx, 1
0x180008923  jnz     short loc_180008903
0x180008925  mov     rax, rdx
0x180008928  lea     rcx, [r8-2]
0x18000892c  neg     rax
0x18000892f  sbb     ebx, ebx
0x180008931  not     ebx
0x180008933  and     ebx, 8007007Ah
0x180008939  test    rdx, rdx
0x18000893c  cmovnz  rcx, r8
0x180008940  mov     [rcx], r12w
0x180008944  jnz     short loc_180008997
0x180008946  mov     rcx, cs:WPP_GLOBAL_Control
0x18000894d  lea     rax, WPP_GLOBAL_Control
0x180008954  cmp     rcx, rax
0x180008957  jz      short loc_18000897D
0x180008959  test    byte ptr [rcx+1Ch], 2
0x18000895d  jz      short loc_18000897D
0x18000895f  cmp     byte ptr [rcx+19h], 2
0x180008963  jb      short loc_18000897D
0x180008965  mov     rcx, [rcx+10h]
0x180008969  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180008970  mov     edx, 0Eh
0x180008975  mov     r9d, ebx
0x180008978  call    WPP_SF_d
0x18000897d  mov     eax, ebx
0x18000897f  and     eax, 1FFF0000h
0x180008984  cmp     eax, 70000h
0x180008989  jnz     loc_180008BD1
0x18000898f  movzx   ebx, bx
0x180008992  jmp     loc_180008BD1
0x180008997  mov     rax, [rdi+10h]
0x18000899b  mov     rcx, [rax]
0x18000899e  mov     eax, 4949h
0x1800089a3  mov     [rdi+234h], rcx
0x1800089aa  cmp     cx, ax
0x1800089ad  jnz     loc_180008BDC
0x1800089b3  cmp     word ptr [rdi+236h], 2Ah ; '*'
0x1800089bb  jnz     loc_180008BDC
0x1800089c1  mov     ebx, [rdi+238h]
0x1800089c7  test    ebx, ebx
0x1800089c9  jz      loc_180008BDC
0x1800089cf  mov     rdx, rdi
0x1800089d2  mov     ecx, ebx
0x1800089d4  call    IsValidIFDOffset
0x1800089d9  test    eax, eax
0x1800089db  jz      loc_180008BDC
0x1800089e1  mov     rax, [rbp+lpMem]
0x1800089e5  jmp     short loc_1800089F3
0x1800089e7  cmp     [rax+10h], ebx
0x1800089ea  jz      loc_180008B12
0x1800089f0  mov     rax, [rax]
0x1800089f3  lea     rcx, [rbp+lpMem]
0x1800089f7  cmp     rax, rcx
0x1800089fa  jnz     short loc_1800089E7
0x1800089fc  mov     ecx, 18h; dwBytes
0x180008a01  call    pMemAlloc
0x180008a06  test    rax, rax
0x180008a09  jz      loc_180008B95
0x180008a0f  mov     [rax+10h], ebx
0x180008a12  lea     rdx, [rbp+lpMem]
0x180008a16  mov     rcx, [rbp+lpMem+8]
0x180008a1a  mov     [rax+8], rcx
0x180008a1e  mov     [rax], rdx
0x180008a21  mov     [rcx], rax
0x180008a24  mov     [rbp+lpMem+8], rax
0x180008a28  mov     rdx, [rdi+10h]
0x180008a2c  mov     eax, ebx
0x180008a2e  movzx   ecx, word ptr [rax+rdx]
0x180008a32  lea     eax, [rcx+rcx*2]
0x180008a35  lea     ecx, ds:2[rax*4]
0x180008a3c  add     ecx, ebx
0x180008a3e  cmp     ecx, ebx
0x180008a40  jb      loc_180008B5A
0x180008a46  mov     ebx, [rcx+rdx]
0x180008a49  mov     rdx, rdi
0x180008a4c  mov     ecx, ebx
0x180008a4e  call    IsValidIFDOffset
0x180008a53  test    eax, eax
0x180008a55  jz      loc_180008BDC
0x180008a5b  inc     dword ptr [rdi+344h]
0x180008a61  test    ebx, ebx
0x180008a63  jnz     loc_1800089E1
0x180008a69  mov     eax, [rdi+238h]
0x180008a6f  lea     edx, [rbx+1]
0x180008a72  mov     r8d, r15d
0x180008a75  mov     [rdi+34Ch], eax
0x180008a7b  mov     rcx, rdi
0x180008a7e  mov     [rdi+65Ch], r15d
0x180008a85  call    TiffSeekToPage
0x180008a8a  test    eax, eax
0x180008a8c  jz      loc_180008BDC
0x180008a92  mov     eax, [rdi+344h]
0x180008a98  lea     rcx, [rdi+35Ch]; void *
0x180008a9f  mov     [r14+8], eax
0x180008aa3  xor     edx, edx; Val
0x180008aa5  mov     eax, [rdi+61Ch]
0x180008aab  mov     r8d, 288h; Size
0x180008ab1  mov     [r14], eax
0x180008ab4  mov     ebx, r12d
0x180008ab7  mov     eax, [rdi+620h]
0x180008abd  mov     [r14+4], eax
0x180008ac1  mov     eax, [rdi+658h]
0x180008ac7  mov     [r14+0Ch], eax
0x180008acb  mov     eax, [rdi+65Ch]
0x180008ad1  mov     [r14+18h], eax
0x180008ad5  mov     eax, [rdi+694h]
0x180008adb  mov     [r14+1Ch], eax
0x180008adf  mov     eax, [rdi+354h]
0x180008ae5  mov     [r14+14h], eax
0x180008ae9  lea     rax, [rcx+0D8h]
0x180008af0  mov     [rdi+5E8h], rax
0x180008af7  mov     [rdi+5F0h], rcx
0x180008afe  mov     dword ptr [rdi+5F8h], 1
0x180008b08  call    memset_0
0x180008b0d  jmp     loc_180008C2A
0x180008b12  mov     ebx, 0Bh
0x180008b17  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b1e  lea     rax, WPP_GLOBAL_Control
0x180008b25  cmp     rcx, rax
0x180008b28  jz      loc_180008BE1
0x180008b2e  test    byte ptr [rcx+1Ch], 2
0x180008b32  jz      loc_180008BE1
0x180008b38  cmp     byte ptr [rcx+19h], 2
0x180008b3c  jb      loc_180008BE1
0x180008b42  mov     rcx, [rcx+10h]
0x180008b46  lea     edx, [rbx+4]
0x180008b49  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180008b50  call    WPP_SF_
0x180008b55  jmp     loc_180008BE1
0x180008b5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b61  lea     rax, WPP_GLOBAL_Control
0x180008b68  cmp     rcx, rax
0x180008b6b  jz      short loc_180008B8E
0x180008b6d  test    byte ptr [rcx+1Ch], 2
0x180008b71  jz      short loc_180008B8E
0x180008b73  cmp     byte ptr [rcx+19h], 2
0x180008b77  jb      short loc_180008B8E
0x180008b79  mov     rcx, [rcx+10h]
0x180008b7d  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180008b84  mov     edx, 11h
0x180008b89  call    WPP_SF_
0x180008b8e  mov     ebx, 216h
0x180008b93  jmp     short loc_180008BE1
0x180008b95  call    cs:__imp_GetLastError
0x180008b9b  mov     ebx, eax
0x180008b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ba4  lea     rax, WPP_GLOBAL_Control
0x180008bab  cmp     rcx, rax
0x180008bae  jz      short loc_180008BD1
0x180008bb0  test    byte ptr [rcx+1Ch], 2
0x180008bb4  jz      short loc_180008BD1
0x180008bb6  cmp     byte ptr [rcx+19h], 2
0x180008bba  jb      short loc_180008BD1
0x180008bbc  mov     rcx, [rcx+10h]
0x180008bc0  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180008bc7  mov     edx, 10h
0x180008bcc  call    WPP_SF_
0x180008bd1  test    ebx, ebx
0x180008bd3  jz      short loc_180008C2A
0x180008bd5  test    rdi, rdi
0x180008bd8  jz      short loc_180008C2A
0x180008bda  jmp     short loc_180008BE1
0x180008bdc  mov     ebx, 0Bh
0x180008be1  mov     rax, [rdi]
0x180008be4  dec     rax
0x180008be7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008beb  ja      short loc_180008C1F
0x180008bed  mov     rcx, [rdi+10h]; lpBaseAddress
0x180008bf1  test    rcx, rcx
0x180008bf4  jz      short loc_180008C00
0x180008bf6  call    cs:__imp_UnmapViewOfFile
0x180008bfc  mov     [rdi+10h], r12
0x180008c00  mov     rcx, [rdi+8]; hObject
0x180008c04  test    rcx, rcx
0x180008c07  jz      short loc_180008C13
0x180008c09  call    cs:__imp_CloseHandle
0x180008c0f  mov     [rdi+8], r12
0x180008c13  mov     rcx, [rdi]; hObject
0x180008c16  call    cs:__imp_CloseHandle
0x180008c1c  mov     [rdi], r12
0x180008c1f  mov     rcx, rdi; lpMem
0x180008c22  call    pMemFree
0x180008c27  mov     rdi, r12
0x180008c2a  mov     rsi, [rbp+lpMem]
0x180008c2e  jmp     short loc_180008C53
0x180008c30  mov     rdx, [rsi]
0x180008c33  mov     rcx, rsi; lpMem
0x180008c36  mov     r8, rsi
0x180008c39  mov     rsi, rdx
0x180008c3c  mov     rax, [rcx+8]
0x180008c40  mov     [rax], rdx
0x180008c43  mov     [rdx+8], rax
0x180008c47  mov     [rcx], r12
  ... truncated ...
```
