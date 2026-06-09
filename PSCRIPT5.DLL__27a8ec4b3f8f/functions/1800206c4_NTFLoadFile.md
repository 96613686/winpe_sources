# NTFLoadFile

- ea: `0x1800206c4`
- end: `0x180020a45`
- name: `NTFLoadFile`
- size: `897`
- prototype: `_DWORD *__fastcall(__int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001b8b0`

## callees

- `0x1800055fc`
- `0x1800206c4`
- `0x180020a4c`
- `0x180020acc`
- `0x180030424`
- `0x180031330`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002081c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002081c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800206ed`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180020709`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180020721`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800206ed`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180020709`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180020721`
- `KERNEL32!MapViewOfFile` at `0x180020901`
- `KERNEL32!MapViewOfFile` at `0x180020901`
- `KERNEL32!CreateFileMappingW` at `0x1800208db`
- `KERNEL32!CreateFileMappingW` at `0x1800208db`
- `KERNEL32!GetFileSize` at `0x1800208b1`
- `KERNEL32!GetFileSize` at `0x1800208b1`
- `KERNEL32!LeaveCriticalSection` at `0x180020a09`
- `KERNEL32!LeaveCriticalSection` at `0x180020a09`
- `KERNEL32!EnterCriticalSection` at `0x1800207f5`
- `KERNEL32!EnterCriticalSection` at `0x1800207f5`
- `KERNEL32!CreateFileW` at `0x18002088b`
- `KERNEL32!CreateFileW` at `0x18002088b`
- `KERNEL32!CloseHandle` at `0x180020913`
- `KERNEL32!CloseHandle` at `0x180020927`
- `KERNEL32!CloseHandle` at `0x180020982`
- `KERNEL32!CloseHandle` at `0x180020913`
- `KERNEL32!CloseHandle` at `0x180020927`
- `KERNEL32!CloseHandle` at `0x180020982`
- `KERNEL32!LocalFree` at `0x1800207c7`
- `KERNEL32!LocalFree` at `0x1800207d9`
- `KERNEL32!LocalFree` at `0x1800209f3`
- `KERNEL32!LocalFree` at `0x180020a22`
- `KERNEL32!LocalFree` at `0x1800207c7`
- `KERNEL32!LocalFree` at `0x1800207d9`
- `KERNEL32!LocalFree` at `0x1800209f3`
- `KERNEL32!LocalFree` at `0x180020a22`
- `KERNEL32!LocalAlloc` at `0x180020789`
- `KERNEL32!LocalAlloc` at `0x18002083f`
- `KERNEL32!LocalAlloc` at `0x180020789`
- `KERNEL32!LocalAlloc` at `0x18002083f`

## pseudocode

```c
_DWORD *__fastcall NTFLoadFile(__int64 a1, const wchar_t *a2)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rbx
  wchar_t *v6; // rax
  const wchar_t *v7; // rbx
  char *DriverDirectory; // rsi
  __int64 v9; // rax
  __int64 v10; // rcx
  SIZE_T v11; // rbp
  wchar_t *v12; // rax
  wchar_t *v13; // rdi
  size_t v14; // rbp
  int i; // ebx
  _QWORD *v16; // rcx
  _QWORD *v17; // rax
  _DWORD *v18; // rbx
  LPVOID *v19; // r14
  __int64 v20; // rsi
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  HANDLE FileMappingW; // rax
  void *v24; // rbp
  _DWORD *v25; // rcx
  int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // rsi
  _DWORD *v29; // rcx

  if ( !a2 )
    return 0;
  v4 = wcsrchr(a2, 0x5Cu);
  v5 = v4;
  if ( v4 )
  {
    v6 = wcsrchr(v4, 0x2Fu);
    if ( v6 )
      v5 = v6;
  }
  else
  {
    v5 = wcsrchr(a2, 0x2Fu);
    if ( !v5 )
    {
      v7 = a2;
      goto LABEL_9;
    }
  }
  v7 = v5 + 1;
LABEL_9:
  DriverDirectory = PtstrGetDriverDirectory(*(const wchar_t **)(*(_QWORD *)(a1 + 696) + 24LL));
  if ( !DriverDirectory )
    return 0;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)&DriverDirectory[2 * v9] );
  v10 = -1;
  do
    ++v10;
  while ( v7[v10] );
  v11 = (unsigned int)(2 * (v10 + v9) + 2);
  v12 = (wchar_t *)LocalAlloc(0, v11);
  v13 = v12;
  if ( v12 )
  {
    v14 = v11 >> 1;
    if ( StringCchCopyW(v12, v14, (STRSAFE_LPCWSTR)DriverDirectory) < 0 || StringCchCatW(v13, v14, v7) < 0 )
    {
      LocalFree(v13);
      v13 = 0;
    }
  }
  LocalFree(DriverDirectory);
  if ( !v13 )
    return 0;
  EnterCriticalSection(&gPSCritSection);
  for ( i = 0; i < 4; ++i )
  {
    v16 = (_QWORD *)*((_QWORD *)&gCachedNtfFiles + (unsigned int)i);
    if ( v16 && !(unsigned int)_o__wcsicmp(*v16, v13) )
    {
      v18 = (_DWORD *)*((_QWORD *)&gCachedNtfFiles + (unsigned int)i);
      ++v18[7];
      goto LABEL_51;
    }
  }
  v17 = LocalAlloc(0x40u, 0x20u);
  v18 = v17;
  if ( !v17 )
    goto LABEL_51;
  v19 = (LPVOID *)(v17 + 2);
  v20 = -1;
  if ( v17 != (_QWORD *)-16LL )
  {
    FileW = CreateFileW(v13, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
    v20 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
LABEL_31:
      *v19 = 0;
      goto LABEL_32;
    }
    if ( v18 != (_DWORD *)-24LL && (FileSize = GetFileSize(FileW, 0), v18[6] = FileSize, FileSize == -1)
      || (FileMappingW = CreateFileMappingW((HANDLE)v20, 0, 2u, 0, 0, 0), (v24 = FileMappingW) == 0)
      || (*v19 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0), CloseHandle(v24), !*v19) )
    {
      CloseHandle((HANDLE)v20);
      v20 = -1;
      goto LABEL_31;
    }
  }
LABEL_32:
  v25 = *v19;
  *((_QWORD *)v18 + 1) = *v19;
  if ( v25 )
  {
    if ( v18[6] >= 0x34u
      && *v25 == 1314145841
      && v25[1] == 1314148435
      && v25[2] == 0x10000
      && *(_DWORD *)((char *)v25 + (unsigned int)v18[6] - 4) == 625299270 )
    {
      CloseHandle((HANDLE)v20);
      v26 = 0;
      *(_QWORD *)v18 = v13;
      do
      {
        if ( !*((_QWORD *)&gCachedNtfFiles + (unsigned int)v26) )
        {
          *((_QWORD *)&gCachedNtfFiles + (unsigned int)v26) = v18;
          goto LABEL_47;
        }
        ++v26;
      }
      while ( v26 < 4 );
      v27 = 0;
      while ( 1 )
      {
        v28 = v27;
        v29 = (_DWORD *)*((_QWORD *)&gCachedNtfFiles + v27);
        if ( !v29[7] )
          break;
        if ( (int)++v27 >= 4 )
          goto LABEL_51;
      }
      NTFUnloadFile(v29);
      *((_QWORD *)&gCachedNtfFiles + v28) = v18;
LABEL_47:
      v18[7] = 1;
      goto LABEL_51;
    }
    UnmapFileFromMemory(v25, (void *)v20);
  }
  LocalFree(v18);
  v18 = 0;
LABEL_51:
  LeaveCriticalSection(&gPSCritSection);
  if ( !v18 || *(wchar_t **)v18 != v13 )
    LocalFree(v13);
  return v18;
}

```

## disassembly

```asm
0x1800206c4  push    rbx
0x1800206c6  push    rbp
0x1800206c7  push    rsi
0x1800206c8  push    rdi
0x1800206c9  push    r12
0x1800206cb  push    r14
0x1800206cd  push    r15
0x1800206cf  sub     rsp, 40h
0x1800206d3  xor     r12d, r12d
0x1800206d6  mov     rdi, rdx
0x1800206d9  mov     rsi, rcx
0x1800206dc  test    rdx, rdx
0x1800206df  jz      loc_180020A33
0x1800206e5  lea     edx, [r12+5Ch]; Ch
0x1800206ea  mov     rcx, rdi; Str
0x1800206ed  call    cs:__imp_wcsrchr
0x1800206f4  nop     dword ptr [rax+rax+00h]
0x1800206f9  lea     edx, [r12+2Fh]; Ch
0x1800206fe  mov     rbx, rax
0x180020701  test    rax, rax
0x180020704  jz      short loc_18002071E
0x180020706  mov     rcx, rax; Str
0x180020709  call    cs:__imp_wcsrchr
0x180020710  nop     dword ptr [rax+rax+00h]
0x180020715  test    rax, rax
0x180020718  cmovnz  rbx, rax
0x18002071c  jmp     short loc_180020735
0x18002071e  mov     rcx, rdi; Str
0x180020721  call    cs:__imp_wcsrchr
0x180020728  nop     dword ptr [rax+rax+00h]
0x18002072d  mov     rbx, rax
0x180020730  test    rax, rax
0x180020733  jz      short loc_18002073B
0x180020735  add     rbx, 2
0x180020739  jmp     short loc_18002073E
0x18002073b  mov     rbx, rdi
0x18002073e  mov     rcx, [rsi+2B8h]
0x180020745  mov     rcx, [rcx+18h]; Src
0x180020749  call    PtstrGetDriverDirectory
0x18002074e  mov     rsi, rax
0x180020751  test    rax, rax
0x180020754  jz      loc_180020A33
0x18002075a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002075e  mov     rax, r15
0x180020761  inc     rax
0x180020764  cmp     [rsi+rax*2], r12w
0x180020769  jnz     short loc_180020761
0x18002076b  mov     rcx, r15
0x18002076e  inc     rcx
0x180020771  cmp     [rbx+rcx*2], r12w
0x180020776  jnz     short loc_18002076E
0x180020778  add     rax, rcx
0x18002077b  xor     ecx, ecx; uFlags
0x18002077d  lea     rax, ds:2[rax*2]
0x180020785  mov     edx, eax; uBytes
0x180020787  mov     ebp, eax
0x180020789  call    cs:__imp_LocalAlloc
0x180020790  nop     dword ptr [rax+rax+00h]
0x180020795  mov     rdi, rax
0x180020798  test    rax, rax
0x18002079b  jz      short loc_1800207D6
0x18002079d  shr     rbp, 1
0x1800207a0  mov     r8, rsi; pszSrc
0x1800207a3  mov     rdx, rbp; cchDest
0x1800207a6  mov     rcx, rax; pszDest
0x1800207a9  call    StringCchCopyW
0x1800207ae  test    eax, eax
0x1800207b0  js      short loc_1800207C4
0x1800207b2  mov     r8, rbx; pszSrc
0x1800207b5  mov     rdx, rbp; cchDest
0x1800207b8  mov     rcx, rdi; pszDest
0x1800207bb  call    StringCchCatW
0x1800207c0  test    eax, eax
0x1800207c2  jns     short loc_1800207D6
0x1800207c4  mov     rcx, rdi; hMem
0x1800207c7  call    cs:__imp_LocalFree
0x1800207ce  nop     dword ptr [rax+rax+00h]
0x1800207d3  mov     rdi, r12
0x1800207d6  mov     rcx, rsi; hMem
0x1800207d9  call    cs:__imp_LocalFree
0x1800207e0  nop     dword ptr [rax+rax+00h]
0x1800207e5  test    rdi, rdi
0x1800207e8  jz      loc_180020A33
0x1800207ee  lea     rcx, gPSCritSection; lpCriticalSection
0x1800207f5  call    cs:__imp_EnterCriticalSection
0x1800207fc  nop     dword ptr [rax+rax+00h]
0x180020801  mov     ebx, r12d
0x180020804  lea     r14, gCachedNtfFiles
0x18002080b  mov     esi, ebx
0x18002080d  mov     rcx, [r14+rsi*8]
0x180020811  test    rcx, rcx
0x180020814  jz      short loc_180020830
0x180020816  mov     rcx, [rcx]
0x180020819  mov     rdx, rdi
0x18002081c  call    cs:__imp__o__wcsicmp
0x180020823  nop     dword ptr [rax+rax+00h]
0x180020828  test    eax, eax
0x18002082a  jz      loc_1800209C2
0x180020830  inc     ebx
0x180020832  cmp     ebx, 4
0x180020835  jl      short loc_18002080B
0x180020837  mov     edx, 20h ; ' '; uBytes
0x18002083c  lea     ecx, [rdx+20h]; uFlags
0x18002083f  call    cs:__imp_LocalAlloc
0x180020846  nop     dword ptr [rax+rax+00h]
0x18002084b  mov     rbx, rax
0x18002084e  test    rax, rax
0x180020851  jz      loc_180020A02
0x180020857  lea     r14, [rax+10h]
0x18002085b  mov     rsi, r15
0x18002085e  test    r14, r14
0x180020861  jz      loc_18002093A
0x180020867  xor     r9d, r9d; lpSecurityAttributes
0x18002086a  mov     [rsp+78h+hTemplateFile], r12; hTemplateFile
0x18002086f  mov     [rsp+78h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180020877  mov     edx, 80000000h; dwDesiredAccess
0x18002087c  mov     rcx, rdi; lpFileName
0x18002087f  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180020887  lea     r8d, [r9+1]; dwShareMode
0x18002088b  call    cs:__imp_CreateFileW
0x180020892  nop     dword ptr [rax+rax+00h]
0x180020897  mov     rsi, rax
0x18002089a  cmp     rax, r15
0x18002089d  jz      loc_180020937
0x1800208a3  lea     r15, [rbx+18h]
0x1800208a7  test    r15, r15
0x1800208aa  jz      short loc_1800208C5
0x1800208ac  xor     edx, edx; lpFileSizeHigh
0x1800208ae  mov     rcx, rax; hFile
0x1800208b1  call    cs:__imp_GetFileSize
0x1800208b8  nop     dword ptr [rax+rax+00h]
0x1800208bd  mov     [r15], eax
0x1800208c0  cmp     eax, 0FFFFFFFFh
0x1800208c3  jz      short loc_180020924
0x1800208c5  xor     r9d, r9d; dwMaximumSizeHigh
0x1800208c8  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r12; lpName
0x1800208cd  xor     edx, edx; lpFileMappingAttributes
0x1800208cf  mov     [rsp+78h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x1800208d4  mov     rcx, rsi; hFile
0x1800208d7  lea     r8d, [r9+2]; flProtect
0x1800208db  call    cs:__imp_CreateFileMappingW
0x1800208e2  nop     dword ptr [rax+rax+00h]
0x1800208e7  mov     rbp, rax
0x1800208ea  test    rax, rax
0x1800208ed  jz      short loc_180020924
0x1800208ef  xor     r9d, r9d; dwFileOffsetLow
0x1800208f2  mov     qword ptr [rsp+78h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x1800208f7  xor     r8d, r8d; dwFileOffsetHigh
0x1800208fa  mov     rcx, rax; hFileMappingObject
0x1800208fd  lea     edx, [r9+4]; dwDesiredAccess
0x180020901  call    cs:__imp_MapViewOfFile
0x180020908  nop     dword ptr [rax+rax+00h]
0x18002090d  mov     rcx, rbp; hObject
0x180020910  mov     [r14], rax
0x180020913  call    cs:__imp_CloseHandle
0x18002091a  nop     dword ptr [rax+rax+00h]
0x18002091f  cmp     [r14], r12
0x180020922  jnz     short loc_18002093A
0x180020924  mov     rcx, rsi; hObject
0x180020927  call    cs:__imp_CloseHandle
0x18002092e  nop     dword ptr [rax+rax+00h]
0x180020933  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180020937  mov     [r14], r12
0x18002093a  mov     rcx, [r14]
0x18002093d  mov     [rbx+8], rcx
0x180020941  test    rcx, rcx
0x180020944  jz      loc_1800209F0
0x18002094a  cmp     dword ptr [rbx+18h], 34h ; '4'
0x18002094e  jb      loc_1800209E3
0x180020954  cmp     dword ptr [rcx], 4E544631h
0x18002095a  jnz     loc_1800209E3
0x180020960  cmp     dword ptr [rcx+4], 4E545053h
0x180020967  jnz     short loc_1800209E3
0x180020969  cmp     dword ptr [rcx+8], 10000h
0x180020970  jnz     short loc_1800209E3
0x180020972  mov     eax, [rbx+18h]
0x180020975  cmp     dword ptr [rax+rcx-4], 25454F46h
0x18002097d  jnz     short loc_1800209E3
0x18002097f  mov     rcx, rsi; hObject
0x180020982  call    cs:__imp_CloseHandle
0x180020989  nop     dword ptr [rax+rax+00h]
0x18002098e  mov     eax, r12d
0x180020991  mov     [rbx], rdi
0x180020994  lea     r14, gCachedNtfFiles
0x18002099b  mov     ecx, eax
0x18002099d  cmp     [r14+rcx*8], r12
0x1800209a1  jz      short loc_1800209DD
0x1800209a3  inc     eax
0x1800209a5  cmp     eax, 4
0x1800209a8  jl      short loc_18002099B
0x1800209aa  mov     eax, r12d
0x1800209ad  mov     esi, eax
0x1800209af  mov     rcx, [r14+rsi*8]; hMem
0x1800209b3  cmp     [rcx+1Ch], r12d
0x1800209b7  jz      short loc_1800209CB
0x1800209b9  inc     eax
0x1800209bb  cmp     eax, 4
0x1800209be  jl      short loc_1800209AD
0x1800209c0  jmp     short loc_180020A02
0x1800209c2  mov     rbx, [r14+rsi*8]
0x1800209c6  inc     dword ptr [rbx+1Ch]
0x1800209c9  jmp     short loc_180020A02
0x1800209cb  call    NTFUnloadFile
0x1800209d0  mov     [r14+rsi*8], rbx
0x1800209d4  mov     dword ptr [rbx+1Ch], 1
0x1800209db  jmp     short loc_180020A02
0x1800209dd  mov     [r14+rcx*8], rbx
0x1800209e1  jmp     short loc_1800209D4
0x1800209e3  test    rcx, rcx
0x1800209e6  jz      short loc_1800209F0
0x1800209e8  mov     rdx, rsi
0x1800209eb  call    UnmapFileFromMemory
0x1800209f0  mov     rcx, rbx; hMem
0x1800209f3  call    cs:__imp_LocalFree
0x1800209fa  nop     dword ptr [rax+rax+00h]
0x1800209ff  mov     rbx, r12
0x180020a02  lea     rcx, gPSCritSection; lpCriticalSection
0x180020a09  call    cs:__imp_LeaveCriticalSection
0x180020a10  nop     dword ptr [rax+rax+00h]
0x180020a15  test    rbx, rbx
0x180020a18  jz      short loc_180020A1F
0x180020a1a  cmp     [rbx], rdi
0x180020a1d  jz      short loc_180020A2E
0x180020a1f  mov     rcx, rdi; hMem
0x180020a22  call    cs:__imp_LocalFree
0x180020a29  nop     dword ptr [rax+rax+00h]
0x180020a2e  mov     rax, rbx
0x180020a31  jmp     short loc_180020A35
0x180020a33  xor     eax, eax
0x180020a35  add     rsp, 40h
0x180020a39  pop     r15
0x180020a3b  pop     r14
0x180020a3d  pop     r12
0x180020a3f  pop     rdi
0x180020a40  pop     rsi
0x180020a41  pop     rbp
0x180020a42  pop     rbx
0x180020a43  retn
```
