# NTFLoadFile

- ea: `0x18001fb10`
- end: `0x18001fe23`
- name: `NTFLoadFile`
- size: `787`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001af6c`

## callees

- `0x180005568`
- `0x18001fb10`
- `0x18001fe2c`
- `0x18001fe90`
- `0x18002ef48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001fc3e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001fc3e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001fb39`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001fb4f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001fb61`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001fb39`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001fb4f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001fb61`
- `KERNEL32!MapViewOfFile` at `0x18001fd01`
- `KERNEL32!MapViewOfFile` at `0x18001fd01`
- `KERNEL32!CreateFileMappingW` at `0x18001fce1`
- `KERNEL32!CreateFileMappingW` at `0x18001fce1`
- `KERNEL32!GetFileSize` at `0x18001fcbd`
- `KERNEL32!GetFileSize` at `0x18001fcbd`
- `KERNEL32!LeaveCriticalSection` at `0x18001fdf4`
- `KERNEL32!LeaveCriticalSection` at `0x18001fdf4`
- `KERNEL32!EnterCriticalSection` at `0x18001fc1d`
- `KERNEL32!EnterCriticalSection` at `0x18001fc1d`
- `KERNEL32!CreateFileW` at `0x18001fca1`
- `KERNEL32!CreateFileW` at `0x18001fca1`
- `KERNEL32!CloseHandle` at `0x18001fd0d`
- `KERNEL32!CloseHandle` at `0x18001fd1b`
- `KERNEL32!CloseHandle` at `0x18001fd6c`
- `KERNEL32!CloseHandle` at `0x18001fddb`
- `KERNEL32!CloseHandle` at `0x18001fd0d`
- `KERNEL32!CloseHandle` at `0x18001fd1b`
- `KERNEL32!CloseHandle` at `0x18001fd6c`
- `KERNEL32!CloseHandle` at `0x18001fddb`
- `KERNEL32!LocalFree` at `0x18001fbfb`
- `KERNEL32!LocalFree` at `0x18001fc07`
- `KERNEL32!LocalFree` at `0x18001fde4`
- `KERNEL32!LocalFree` at `0x18001fe07`
- `KERNEL32!LocalFree` at `0x18001fbfb`
- `KERNEL32!LocalFree` at `0x18001fc07`
- `KERNEL32!LocalFree` at `0x18001fde4`
- `KERNEL32!LocalFree` at `0x18001fe07`
- `KERNEL32!LocalAlloc` at `0x18001fbc3`
- `KERNEL32!LocalAlloc` at `0x18001fc5b`
- `KERNEL32!LocalAlloc` at `0x18001fbc3`
- `KERNEL32!LocalAlloc` at `0x18001fc5b`
- `KERNEL32!UnmapViewOfFile` at `0x18001fdcc`
- `KERNEL32!UnmapViewOfFile` at `0x18001fdcc`

## pseudocode

```c
_DWORD *__fastcall NTFLoadFile(__int64 a1, const wchar_t *a2)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rbx
  wchar_t *v6; // rax
  const wchar_t *v7; // rbx
  wchar_t *DriverDirectory; // rsi
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
  DriverDirectory = (wchar_t *)PtstrGetDriverDirectory(*(void **)(*(_QWORD *)(a1 + 696) + 24LL));
  if ( !DriverDirectory )
    return 0;
  v9 = -1;
  do
    ++v9;
  while ( DriverDirectory[v9] );
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
    if ( StringCchCopyW(v12, v14, DriverDirectory) < 0 || StringCchCatW(v13, v14, v7) < 0 )
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
      goto LABEL_52;
    }
  }
  v17 = LocalAlloc(0x40u, 0x20u);
  v18 = v17;
  if ( !v17 )
    goto LABEL_52;
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
          goto LABEL_52;
      }
      NTFUnloadFile(v29);
      *((_QWORD *)&gCachedNtfFiles + v28) = v18;
LABEL_47:
      v18[7] = 1;
      goto LABEL_52;
    }
    UnmapViewOfFile(v25);
    if ( v20 != -1 )
      CloseHandle((HANDLE)v20);
  }
  LocalFree(v18);
  v18 = 0;
LABEL_52:
  LeaveCriticalSection(&gPSCritSection);
  if ( !v18 || *(wchar_t **)v18 != v13 )
    LocalFree(v13);
  return v18;
}

```

## disassembly

```asm
0x18001fb10  push    rbx
0x18001fb12  push    rbp
0x18001fb13  push    rsi
0x18001fb14  push    rdi
0x18001fb15  push    r12
0x18001fb17  push    r14
0x18001fb19  push    r15
0x18001fb1b  sub     rsp, 40h
0x18001fb1f  xor     r12d, r12d
0x18001fb22  mov     rdi, rdx
0x18001fb25  mov     rsi, rcx
0x18001fb28  test    rdx, rdx
0x18001fb2b  jz      loc_18001FE12
0x18001fb31  lea     edx, [r12+5Ch]; Ch
0x18001fb36  mov     rcx, rdi; Str
0x18001fb39  call    cs:__imp_wcsrchr
0x18001fb3f  lea     edx, [r12+2Fh]; Ch
0x18001fb44  mov     rbx, rax
0x18001fb47  test    rax, rax
0x18001fb4a  jz      short loc_18001FB5E
0x18001fb4c  mov     rcx, rax; Str
0x18001fb4f  call    cs:__imp_wcsrchr
0x18001fb55  test    rax, rax
0x18001fb58  cmovnz  rbx, rax
0x18001fb5c  jmp     short loc_18001FB6F
0x18001fb5e  mov     rcx, rdi; Str
0x18001fb61  call    cs:__imp_wcsrchr
0x18001fb67  mov     rbx, rax
0x18001fb6a  test    rax, rax
0x18001fb6d  jz      short loc_18001FB75
0x18001fb6f  add     rbx, 2
0x18001fb73  jmp     short loc_18001FB78
0x18001fb75  mov     rbx, rdi
0x18001fb78  mov     rcx, [rsi+2B8h]
0x18001fb7f  mov     rcx, [rcx+18h]; Src
0x18001fb83  call    PtstrGetDriverDirectory
0x18001fb88  mov     rsi, rax
0x18001fb8b  test    rax, rax
0x18001fb8e  jz      loc_18001FE12
0x18001fb94  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001fb98  mov     rax, r15
0x18001fb9b  inc     rax
0x18001fb9e  cmp     [rsi+rax*2], r12w
0x18001fba3  jnz     short loc_18001FB9B
0x18001fba5  mov     rcx, r15
0x18001fba8  inc     rcx
0x18001fbab  cmp     [rbx+rcx*2], r12w
0x18001fbb0  jnz     short loc_18001FBA8
0x18001fbb2  add     rax, rcx
0x18001fbb5  xor     ecx, ecx; uFlags
0x18001fbb7  lea     rax, ds:2[rax*2]
0x18001fbbf  mov     edx, eax; uBytes
0x18001fbc1  mov     ebp, eax
0x18001fbc3  call    cs:__imp_LocalAlloc
0x18001fbc9  mov     rdi, rax
0x18001fbcc  test    rax, rax
0x18001fbcf  jz      short loc_18001FC04
0x18001fbd1  shr     rbp, 1
0x18001fbd4  mov     r8, rsi; pszSrc
0x18001fbd7  mov     rdx, rbp; cchDest
0x18001fbda  mov     rcx, rax; pszDest
0x18001fbdd  call    StringCchCopyW
0x18001fbe2  test    eax, eax
0x18001fbe4  js      short loc_18001FBF8
0x18001fbe6  mov     r8, rbx; pszSrc
0x18001fbe9  mov     rdx, rbp; cchDest
0x18001fbec  mov     rcx, rdi; pszDest
0x18001fbef  call    StringCchCatW
0x18001fbf4  test    eax, eax
0x18001fbf6  jns     short loc_18001FC04
0x18001fbf8  mov     rcx, rdi; hMem
0x18001fbfb  call    cs:__imp_LocalFree
0x18001fc01  mov     rdi, r12
0x18001fc04  mov     rcx, rsi; hMem
0x18001fc07  call    cs:__imp_LocalFree
0x18001fc0d  test    rdi, rdi
0x18001fc10  jz      loc_18001FE12
0x18001fc16  lea     rcx, gPSCritSection; lpCriticalSection
0x18001fc1d  call    cs:__imp_EnterCriticalSection
0x18001fc23  mov     ebx, r12d
0x18001fc26  lea     r14, gCachedNtfFiles
0x18001fc2d  mov     esi, ebx
0x18001fc2f  mov     rcx, [r14+rsi*8]
0x18001fc33  test    rcx, rcx
0x18001fc36  jz      short loc_18001FC4C
0x18001fc38  mov     rcx, [rcx]
0x18001fc3b  mov     rdx, rdi
0x18001fc3e  call    cs:__imp__o__wcsicmp
0x18001fc44  test    eax, eax
0x18001fc46  jz      loc_18001FDA6
0x18001fc4c  inc     ebx
0x18001fc4e  cmp     ebx, 4
0x18001fc51  jl      short loc_18001FC2D
0x18001fc53  mov     edx, 20h ; ' '; uBytes
0x18001fc58  lea     ecx, [rdx+20h]; uFlags
0x18001fc5b  call    cs:__imp_LocalAlloc
0x18001fc61  mov     rbx, rax
0x18001fc64  test    rax, rax
0x18001fc67  jz      loc_18001FDED
0x18001fc6d  lea     r14, [rax+10h]
0x18001fc71  mov     rsi, r15
0x18001fc74  test    r14, r14
0x18001fc77  jz      loc_18001FD28
0x18001fc7d  xor     r9d, r9d; lpSecurityAttributes
0x18001fc80  mov     [rsp+78h+hTemplateFile], r12; hTemplateFile
0x18001fc85  mov     [rsp+78h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18001fc8d  mov     edx, 80000000h; dwDesiredAccess
0x18001fc92  mov     rcx, rdi; lpFileName
0x18001fc95  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18001fc9d  lea     r8d, [r9+1]; dwShareMode
0x18001fca1  call    cs:__imp_CreateFileW
0x18001fca7  mov     rsi, rax
0x18001fcaa  cmp     rax, r15
0x18001fcad  jz      short loc_18001FD25
0x18001fcaf  lea     r15, [rbx+18h]
0x18001fcb3  test    r15, r15
0x18001fcb6  jz      short loc_18001FCCB
0x18001fcb8  xor     edx, edx; lpFileSizeHigh
0x18001fcba  mov     rcx, rax; hFile
0x18001fcbd  call    cs:__imp_GetFileSize
0x18001fcc3  mov     [r15], eax
0x18001fcc6  cmp     eax, 0FFFFFFFFh
0x18001fcc9  jz      short loc_18001FD18
0x18001fccb  xor     r9d, r9d; dwMaximumSizeHigh
0x18001fcce  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r12; lpName
0x18001fcd3  xor     edx, edx; lpFileMappingAttributes
0x18001fcd5  mov     [rsp+78h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x18001fcda  mov     rcx, rsi; hFile
0x18001fcdd  lea     r8d, [r9+2]; flProtect
0x18001fce1  call    cs:__imp_CreateFileMappingW
0x18001fce7  mov     rbp, rax
0x18001fcea  test    rax, rax
0x18001fced  jz      short loc_18001FD18
0x18001fcef  xor     r9d, r9d; dwFileOffsetLow
0x18001fcf2  mov     qword ptr [rsp+78h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x18001fcf7  xor     r8d, r8d; dwFileOffsetHigh
0x18001fcfa  mov     rcx, rax; hFileMappingObject
0x18001fcfd  lea     edx, [r9+4]; dwDesiredAccess
0x18001fd01  call    cs:__imp_MapViewOfFile
0x18001fd07  mov     rcx, rbp; hObject
0x18001fd0a  mov     [r14], rax
0x18001fd0d  call    cs:__imp_CloseHandle
0x18001fd13  cmp     [r14], r12
0x18001fd16  jnz     short loc_18001FD28
0x18001fd18  mov     rcx, rsi; hObject
0x18001fd1b  call    cs:__imp_CloseHandle
0x18001fd21  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001fd25  mov     [r14], r12
0x18001fd28  mov     rcx, [r14]; lpBaseAddress
0x18001fd2b  mov     [rbx+8], rcx
0x18001fd2f  test    rcx, rcx
0x18001fd32  jz      loc_18001FDE1
0x18001fd38  cmp     dword ptr [rbx+18h], 34h ; '4'
0x18001fd3c  jb      loc_18001FDC7
0x18001fd42  cmp     dword ptr [rcx], 4E544631h
0x18001fd48  jnz     short loc_18001FDC7
0x18001fd4a  cmp     dword ptr [rcx+4], 4E545053h
0x18001fd51  jnz     short loc_18001FDC7
0x18001fd53  cmp     dword ptr [rcx+8], 10000h
0x18001fd5a  jnz     short loc_18001FDC7
0x18001fd5c  mov     eax, [rbx+18h]
0x18001fd5f  cmp     dword ptr [rax+rcx-4], 25454F46h
0x18001fd67  jnz     short loc_18001FDC7
0x18001fd69  mov     rcx, rsi; hObject
0x18001fd6c  call    cs:__imp_CloseHandle
0x18001fd72  mov     eax, r12d
0x18001fd75  mov     [rbx], rdi
0x18001fd78  lea     r14, gCachedNtfFiles
0x18001fd7f  mov     ecx, eax
0x18001fd81  cmp     [r14+rcx*8], r12
0x18001fd85  jz      short loc_18001FDC1
0x18001fd87  inc     eax
0x18001fd89  cmp     eax, 4
0x18001fd8c  jl      short loc_18001FD7F
0x18001fd8e  mov     eax, r12d
0x18001fd91  mov     esi, eax
0x18001fd93  mov     rcx, [r14+rsi*8]; hMem
0x18001fd97  cmp     [rcx+1Ch], r12d
0x18001fd9b  jz      short loc_18001FDAF
0x18001fd9d  inc     eax
0x18001fd9f  cmp     eax, 4
0x18001fda2  jl      short loc_18001FD91
0x18001fda4  jmp     short loc_18001FDED
0x18001fda6  mov     rbx, [r14+rsi*8]
0x18001fdaa  inc     dword ptr [rbx+1Ch]
0x18001fdad  jmp     short loc_18001FDED
0x18001fdaf  call    NTFUnloadFile
0x18001fdb4  mov     [r14+rsi*8], rbx
0x18001fdb8  mov     dword ptr [rbx+1Ch], 1
0x18001fdbf  jmp     short loc_18001FDED
0x18001fdc1  mov     [r14+rcx*8], rbx
0x18001fdc5  jmp     short loc_18001FDB8
0x18001fdc7  test    rcx, rcx
0x18001fdca  jz      short loc_18001FDE1
0x18001fdcc  call    cs:__imp_UnmapViewOfFile
0x18001fdd2  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001fdd6  jz      short loc_18001FDE1
0x18001fdd8  mov     rcx, rsi; hObject
0x18001fddb  call    cs:__imp_CloseHandle
0x18001fde1  mov     rcx, rbx; hMem
0x18001fde4  call    cs:__imp_LocalFree
0x18001fdea  mov     rbx, r12
0x18001fded  lea     rcx, gPSCritSection; lpCriticalSection
0x18001fdf4  call    cs:__imp_LeaveCriticalSection
0x18001fdfa  test    rbx, rbx
0x18001fdfd  jz      short loc_18001FE04
0x18001fdff  cmp     [rbx], rdi
0x18001fe02  jz      short loc_18001FE0D
0x18001fe04  mov     rcx, rdi; hMem
0x18001fe07  call    cs:__imp_LocalFree
0x18001fe0d  mov     rax, rbx
0x18001fe10  jmp     short loc_18001FE14
0x18001fe12  xor     eax, eax
0x18001fe14  add     rsp, 40h
0x18001fe18  pop     r15
0x18001fe1a  pop     r14
0x18001fe1c  pop     r12
0x18001fe1e  pop     rdi
0x18001fe1f  pop     rsi
0x18001fe20  pop     rbp
0x18001fe21  pop     rbx
0x18001fe22  retn
```
