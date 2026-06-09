# TiffOpen

- ea: `0x180008b70`
- end: `0x180009081`
- name: `TiffOpen`
- size: `1297`
- prototype: `char *__fastcall(LPCWSTR lpFileName, _DWORD *, int, unsigned int)`
- caller_count: `9`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180004540`
- `0x180005450`
- `0x180005c30`
- `0x180005ed0`
- `0x1800066d0`
- `0x180008620`
- `0x1800094c0`
- `0x18000d8c0`
- `0x18000eb70`

## callees

- `0x1800057f0`
- `0x180008b70`
- `0x180009600`
- `0x180009f04`
- `0x180009f34`
- `0x18000f128`
- `0x18000f1c8`
- `0x1800131b4`
- `0x18001899e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008bee`
- `KERNEL32!GetLastError` at `0x180008f7d`
- `KERNEL32!GetLastError` at `0x180008bee`
- `KERNEL32!GetLastError` at `0x180008f7d`
- `KERNEL32!UnmapViewOfFile` at `0x180008fe4`
- `KERNEL32!UnmapViewOfFile` at `0x180008fe4`
- `KERNEL32!SetLastError` at `0x180009062`
- `KERNEL32!SetLastError` at `0x180009062`
- `KERNEL32!MapViewOfFile` at `0x180008cc4`
- `KERNEL32!MapViewOfFile` at `0x180008cc4`
- `KERNEL32!CreateFileMappingW` at `0x180008c93`
- `KERNEL32!CreateFileMappingW` at `0x180008c93`
- `KERNEL32!GetFileSize` at `0x180008c49`
- `KERNEL32!GetFileSize` at `0x180008c49`
- `KERNEL32!CloseHandle` at `0x180008ffd`
- `KERNEL32!CloseHandle` at `0x180009010`
- `KERNEL32!CloseHandle` at `0x180008ffd`
- `KERNEL32!CloseHandle` at `0x180009010`

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
0x180008b70  push    rbp
0x180008b72  push    rbx
0x180008b73  push    rsi
0x180008b74  push    rdi
0x180008b75  push    r12
0x180008b77  push    r14
0x180008b79  push    r15
0x180008b7b  mov     rbp, rsp
0x180008b7e  sub     rsp, 50h
0x180008b82  xorps   xmm0, xmm0
0x180008b85  mov     r15d, r9d
0x180008b88  movups  xmmword ptr [rbp+lpMem], xmm0
0x180008b8c  mov     esi, r8d
0x180008b8f  mov     r14, rdx
0x180008b92  mov     rbx, rcx
0x180008b95  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b9c  lea     rax, WPP_GLOBAL_Control
0x180008ba3  cmp     rcx, rax
0x180008ba6  jz      short loc_180008BC9
0x180008ba8  test    byte ptr [rcx+1Ch], 2
0x180008bac  jz      short loc_180008BC9
0x180008bae  cmp     byte ptr [rcx+19h], 5
0x180008bb2  jb      short loc_180008BC9
0x180008bb4  mov     rcx, [rcx+10h]
0x180008bb8  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180008bbf  mov     edx, 0Dh
0x180008bc4  call    WPP_SF_
0x180008bc9  lea     rax, [rbp+lpMem]
0x180008bcd  mov     ecx, 6A0h; dwBytes
0x180008bd2  mov     [rbp+lpMem+8], rax
0x180008bd6  lea     rax, [rbp+lpMem]
0x180008bda  mov     [rbp+lpMem], rax
0x180008bde  call    pMemAlloc
0x180008be3  xor     r12d, r12d
0x180008be6  mov     rdi, rax
0x180008be9  test    rax, rax
0x180008bec  jnz     short loc_180008C01
0x180008bee  call    cs:__imp_GetLastError
0x180008bf5  nop     dword ptr [rax+rax+00h]
0x180008bfa  mov     ebx, eax
0x180008bfc  jmp     loc_180008FBF
0x180008c01  xor     edx, edx; Val
0x180008c03  mov     r8d, 6A0h; Size
0x180008c09  mov     rcx, rdi; void *
0x180008c0c  call    memset_0
0x180008c11  mov     eax, esi
0x180008c13  mov     dword ptr [rsp+50h+lpName], r12d; int
0x180008c18  neg     eax
0x180008c1a  mov     [rsp+50h+dwMaximumSizeLow], 3; DWORD
0x180008c22  mov     eax, 0C0000000h
0x180008c27  mov     r8d, 1; dwShareMode
0x180008c2d  sbb     edx, edx
0x180008c2f  mov     rcx, rbx; lpFileName
0x180008c32  and     edx, eax
0x180008c34  add     edx, eax; dwDesiredAccess
0x180008c36  call    InternalSafeCreateFile
0x180008c3b  mov     [rdi], rax
0x180008c3e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008c42  jz      short loc_180008BEE
0x180008c44  xor     edx, edx; lpFileSizeHigh
0x180008c46  mov     rcx, rax; hFile
0x180008c49  call    cs:__imp_GetFileSize
0x180008c50  nop     dword ptr [rax+rax+00h]
0x180008c55  mov     [rdi+680h], eax
0x180008c5b  cmp     eax, 0FFFFFFFFh
0x180008c5e  jz      short loc_180008BEE
0x180008c60  cmp     eax, 8
0x180008c63  ja      short loc_180008C6F
0x180008c65  mov     ebx, 57h ; 'W'
0x180008c6a  jmp     loc_180008FCF
0x180008c6f  mov     rcx, [rdi]; hFile
0x180008c72  mov     eax, esi
0x180008c74  neg     eax
0x180008c76  mov     [rsp+50h+lpName], r12; lpName
0x180008c7b  mov     [rsp+50h+dwMaximumSizeLow], r12d; dwMaximumSizeLow
0x180008c80  sbb     r8d, r8d
0x180008c83  xor     r9d, r9d; dwMaximumSizeHigh
0x180008c86  and     r8d, 0FFFFFFFEh
0x180008c8a  xor     edx, edx; lpFileMappingAttributes
0x180008c8c  add     r8d, 8000004h; flProtect
0x180008c93  call    cs:__imp_CreateFileMappingW
0x180008c9a  nop     dword ptr [rax+rax+00h]
0x180008c9f  mov     [rdi+8], rax
0x180008ca3  test    rax, rax
0x180008ca6  jz      loc_180008BEE
0x180008cac  neg     esi
0x180008cae  mov     qword ptr [rsp+50h+dwMaximumSizeLow], r12; dwNumberOfBytesToMap
0x180008cb3  mov     rcx, rax; hFileMappingObject
0x180008cb6  sbb     edx, edx
0x180008cb8  xor     r9d, r9d; dwFileOffsetLow
0x180008cbb  and     edx, 0FFFFFFFEh
0x180008cbe  xor     r8d, r8d; dwFileOffsetHigh
0x180008cc1  add     edx, 6; dwDesiredAccess
0x180008cc4  call    cs:__imp_MapViewOfFile
0x180008ccb  nop     dword ptr [rax+rax+00h]
0x180008cd0  mov     [rdi+10h], rax
0x180008cd4  test    rax, rax
0x180008cd7  jz      loc_180008BEE
0x180008cdd  mov     eax, 7FFFFFFEh
0x180008ce2  lea     r8, [rdi+2Ch]
0x180008ce6  mov     edx, 104h
0x180008ceb  test    rax, rax
0x180008cee  jz      short loc_180008D0D
0x180008cf0  movzx   ecx, word ptr [rbx]
0x180008cf3  test    cx, cx
0x180008cf6  jz      short loc_180008D0D
0x180008cf8  mov     [r8], cx
0x180008cfc  add     rbx, 2
0x180008d00  add     r8, 2
0x180008d04  dec     rax
0x180008d07  sub     rdx, 1
0x180008d0b  jnz     short loc_180008CEB
0x180008d0d  mov     rax, rdx
0x180008d10  lea     rcx, [r8-2]
0x180008d14  neg     rax
0x180008d17  sbb     ebx, ebx
0x180008d19  not     ebx
0x180008d1b  and     ebx, 8007007Ah
0x180008d21  test    rdx, rdx
0x180008d24  cmovnz  rcx, r8
0x180008d28  mov     [rcx], r12w
0x180008d2c  jnz     short loc_180008D7F
0x180008d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d35  lea     rax, WPP_GLOBAL_Control
0x180008d3c  cmp     rcx, rax
0x180008d3f  jz      short loc_180008D65
0x180008d41  test    byte ptr [rcx+1Ch], 2
0x180008d45  jz      short loc_180008D65
0x180008d47  cmp     byte ptr [rcx+19h], 2
0x180008d4b  jb      short loc_180008D65
0x180008d4d  mov     rcx, [rcx+10h]
0x180008d51  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180008d58  mov     edx, 0Eh
0x180008d5d  mov     r9d, ebx
0x180008d60  call    WPP_SF_d
0x180008d65  mov     eax, ebx
0x180008d67  and     eax, 1FFF0000h
0x180008d6c  cmp     eax, 70000h
0x180008d71  jnz     loc_180008FBF
0x180008d77  movzx   ebx, bx
0x180008d7a  jmp     loc_180008FBF
0x180008d7f  mov     rax, [rdi+10h]
0x180008d83  mov     rcx, [rax]
0x180008d86  mov     eax, 4949h
0x180008d8b  mov     [rdi+234h], rcx
0x180008d92  cmp     cx, ax
0x180008d95  jnz     loc_180008FCA
0x180008d9b  cmp     word ptr [rdi+236h], 2Ah ; '*'
0x180008da3  jnz     loc_180008FCA
0x180008da9  mov     ebx, [rdi+238h]
0x180008daf  test    ebx, ebx
0x180008db1  jz      loc_180008FCA
0x180008db7  mov     rdx, rdi
0x180008dba  mov     ecx, ebx
0x180008dbc  call    IsValidIFDOffset
0x180008dc1  test    eax, eax
0x180008dc3  jz      loc_180008FCA
0x180008dc9  mov     rax, [rbp+lpMem]
0x180008dcd  jmp     short loc_180008DDB
0x180008dcf  cmp     [rax+10h], ebx
0x180008dd2  jz      loc_180008EFA
0x180008dd8  mov     rax, [rax]
0x180008ddb  lea     rcx, [rbp+lpMem]
0x180008ddf  cmp     rax, rcx
0x180008de2  jnz     short loc_180008DCF
0x180008de4  mov     ecx, 18h; dwBytes
0x180008de9  call    pMemAlloc
0x180008dee  test    rax, rax
0x180008df1  jz      loc_180008F7D
0x180008df7  mov     [rax+10h], ebx
0x180008dfa  lea     rdx, [rbp+lpMem]
0x180008dfe  mov     rcx, [rbp+lpMem+8]
0x180008e02  mov     [rax+8], rcx
0x180008e06  mov     [rax], rdx
0x180008e09  mov     [rcx], rax
0x180008e0c  mov     [rbp+lpMem+8], rax
0x180008e10  mov     rdx, [rdi+10h]
0x180008e14  mov     eax, ebx
0x180008e16  movzx   ecx, word ptr [rax+rdx]
0x180008e1a  lea     eax, [rcx+rcx*2]
0x180008e1d  lea     ecx, ds:2[rax*4]
0x180008e24  add     ecx, ebx
0x180008e26  cmp     ecx, ebx
0x180008e28  jb      loc_180008F42
0x180008e2e  mov     ebx, [rcx+rdx]
0x180008e31  mov     rdx, rdi
0x180008e34  mov     ecx, ebx
0x180008e36  call    IsValidIFDOffset
0x180008e3b  test    eax, eax
0x180008e3d  jz      loc_180008FCA
0x180008e43  inc     dword ptr [rdi+344h]
0x180008e49  test    ebx, ebx
0x180008e4b  jnz     loc_180008DC9
0x180008e51  mov     eax, [rdi+238h]
0x180008e57  lea     edx, [rbx+1]
0x180008e5a  mov     r8d, r15d
0x180008e5d  mov     [rdi+34Ch], eax
0x180008e63  mov     rcx, rdi
0x180008e66  mov     [rdi+65Ch], r15d
0x180008e6d  call    TiffSeekToPage
0x180008e72  test    eax, eax
0x180008e74  jz      loc_180008FCA
0x180008e7a  mov     eax, [rdi+344h]
0x180008e80  lea     rcx, [rdi+35Ch]; void *
0x180008e87  mov     [r14+8], eax
0x180008e8b  xor     edx, edx; Val
0x180008e8d  mov     eax, [rdi+61Ch]
0x180008e93  mov     r8d, 288h; Size
0x180008e99  mov     [r14], eax
0x180008e9c  mov     ebx, r12d
0x180008e9f  mov     eax, [rdi+620h]
0x180008ea5  mov     [r14+4], eax
0x180008ea9  mov     eax, [rdi+658h]
0x180008eaf  mov     [r14+0Ch], eax
0x180008eb3  mov     eax, [rdi+65Ch]
0x180008eb9  mov     [r14+18h], eax
0x180008ebd  mov     eax, [rdi+694h]
0x180008ec3  mov     [r14+1Ch], eax
0x180008ec7  mov     eax, [rdi+354h]
0x180008ecd  mov     [r14+14h], eax
0x180008ed1  lea     rax, [rcx+0D8h]
0x180008ed8  mov     [rdi+5E8h], rax
0x180008edf  mov     [rdi+5F0h], rcx
0x180008ee6  mov     dword ptr [rdi+5F8h], 1
0x180008ef0  call    memset_0
0x180008ef5  jmp     loc_18000902A
0x180008efa  mov     ebx, 0Bh
0x180008eff  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f06  lea     rax, WPP_GLOBAL_Control
0x180008f0d  cmp     rcx, rax
0x180008f10  jz      loc_180008FCF
0x180008f16  test    byte ptr [rcx+1Ch], 2
0x180008f1a  jz      loc_180008FCF
0x180008f20  cmp     byte ptr [rcx+19h], 2
0x180008f24  jb      loc_180008FCF
0x180008f2a  mov     rcx, [rcx+10h]
0x180008f2e  lea     edx, [rbx+4]
0x180008f31  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180008f38  call    WPP_SF_
0x180008f3d  jmp     loc_180008FCF
0x180008f42  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f49  lea     rax, WPP_GLOBAL_Control
0x180008f50  cmp     rcx, rax
0x180008f53  jz      short loc_180008F76
0x180008f55  test    byte ptr [rcx+1Ch], 2
0x180008f59  jz      short loc_180008F76
0x180008f5b  cmp     byte ptr [rcx+19h], 2
0x180008f5f  jb      short loc_180008F76
0x180008f61  mov     rcx, [rcx+10h]
0x180008f65  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180008f6c  mov     edx, 11h
0x180008f71  call    WPP_SF_
0x180008f76  mov     ebx, 216h
0x180008f7b  jmp     short loc_180008FCF
0x180008f7d  call    cs:__imp_GetLastError
0x180008f84  nop     dword ptr [rax+rax+00h]
0x180008f89  mov     ebx, eax
0x180008f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f92  lea     rax, WPP_GLOBAL_Control
0x180008f99  cmp     rcx, rax
0x180008f9c  jz      short loc_180008FBF
0x180008f9e  test    byte ptr [rcx+1Ch], 2
0x180008fa2  jz      short loc_180008FBF
0x180008fa4  cmp     byte ptr [rcx+19h], 2
0x180008fa8  jb      short loc_180008FBF
0x180008faa  mov     rcx, [rcx+10h]
0x180008fae  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180008fb5  mov     edx, 10h
0x180008fba  call    WPP_SF_
0x180008fbf  test    ebx, ebx
0x180008fc1  jz      short loc_18000902A
0x180008fc3  test    rdi, rdi
0x180008fc6  jz      short loc_18000902A
0x180008fc8  jmp     short loc_180008FCF
0x180008fca  mov     ebx, 0Bh
0x180008fcf  mov     rax, [rdi]
0x180008fd2  dec     rax
0x180008fd5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008fd9  ja      short loc_18000901F
0x180008fdb  mov     rcx, [rdi+10h]; lpBaseAddress
0x180008fdf  test    rcx, rcx
0x180008fe2  jz      short loc_180008FF4
0x180008fe4  call    cs:__imp_UnmapViewOfFile
0x180008feb  nop     dword ptr [rax+rax+00h]
0x180008ff0  mov     [rdi+10h], r12
0x180008ff4  mov     rcx, [rdi+8]; hObject
0x180008ff8  test    rcx, rcx
0x180008ffb  jz      short loc_18000900D
0x180008ffd  call    cs:__imp_CloseHandle
0x180009004  nop     dword ptr [rax+rax+00h]
0x180009009  mov     [rdi+8], r12
0x18000900d  mov     rcx, [rdi]; hObject
0x180009010  call    cs:__imp_CloseHandle
0x180009017  nop     dword ptr [rax+rax+00h]
0x18000901c  mov     [rdi], r12
0x18000901f  mov     rcx, rdi; lpMem
0x180009022  call    pMemFree
0x180009027  mov     rdi, r12
0x18000902a  mov     rsi, [rbp+lpMem]
0x18000902e  jmp     short loc_180009053
  ... truncated ...
```
