# BconsolidateBuffers

- ea: `0x18016c864`
- end: `0x18016cbb4`
- name: `BconsolidateBuffers`
- size: `848`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18016d1b4`

## callees

- `0x1800032e0`
- `0x180162b18`
- `0x180164fa0`
- `0x18016c864`
- `0x1801adb4c`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18016cb09`
- `KERNEL32!WriteFile` at `0x18016cb09`
- `KERNEL32!DeleteFileW` at `0x18016cab2`
- `KERNEL32!DeleteFileW` at `0x18016cb35`
- `KERNEL32!DeleteFileW` at `0x18016cab2`
- `KERNEL32!DeleteFileW` at `0x18016cb35`
- `KERNEL32!GetFileAttributesExW` at `0x18016caa5`
- `KERNEL32!GetFileAttributesExW` at `0x18016caa5`
- `KERNEL32!CreateFileW` at `0x18016cae3`
- `KERNEL32!CreateFileW` at `0x18016cae3`
- `KERNEL32!CloseHandle` at `0x18016cb27`
- `KERNEL32!CloseHandle` at `0x18016cb27`
- `KERNEL32!LocalFree` at `0x18016cb3e`
- `KERNEL32!LocalFree` at `0x18016cb58`
- `KERNEL32!LocalFree` at `0x18016cb3e`
- `KERNEL32!LocalFree` at `0x18016cb58`
- `KERNEL32!LocalAlloc` at `0x18016c950`
- `KERNEL32!LocalAlloc` at `0x18016c950`

## pseudocode

```c
__int64 __fastcall BconsolidateBuffers(STRSAFE_LPCWSTR pszSrc, __int64 a2, _QWORD *a3, DWORD *a4)
{
  __int64 v4; // r12
  __int64 v8; // rax
  int i; // edx
  DWORD v10; // ebx
  unsigned int v11; // r9d
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rax
  unsigned __int64 v15; // r8
  unsigned int v16; // eax
  char *v17; // rax
  char *v18; // rsi
  __int64 v19; // r15
  __int64 v20; // xmm0_8
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  const WCHAR *GPDfilename; // rax
  WCHAR *v33; // rdi
  HANDLE FileW; // rax
  void *v35; // r15
  BOOL v36; // r12d
  DWORD *v37; // rax
  __int64 result; // rax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  DWORD *v40; // [rsp+48h] [rbp-B8h]
  _OWORD v41[13]; // [rsp+50h] [rbp-B0h]
  __int64 v42; // [rsp+120h] [rbp+20h]
  _OWORD FileInformation[2]; // [rsp+130h] [rbp+30h] BYREF
  int v44; // [rsp+150h] [rbp+50h]

  v4 = 0;
  v40 = a4;
  if ( a3 )
    *a3 = 0;
  v8 = 1;
  for ( i = 0; i < 4; ++i )
  {
    *(_DWORD *)(a2 + 24 * v8 + 12) = *(_DWORD *)(a2 + 24 * v8 + 8);
    v8 = (unsigned int)(i + 11);
  }
  v10 = 288;
  v11 = 0;
  *(_DWORD *)(a2 + 24 * v8 + 12) = *(_DWORD *)(a2 + 24 * v8 + 8);
  *(_DWORD *)(a2 + 60) = *(_DWORD *)(a2 + 56);
  *(_DWORD *)(a2 + 372) = *(_DWORD *)(a2 + 368);
  *(_DWORD *)(a2 + 396) = *(_DWORD *)(a2 + 392);
  do
  {
    v12 = 3LL * v11;
    *((_DWORD *)v41 + v12) = v10;
    v13 = *(unsigned int *)(a2 + 24LL * v11 + 16);
    v14 = *(unsigned int *)(a2 + 24LL * v11 + 12);
    *((_DWORD *)v41 + v12 + 2) = v13;
    v15 = v14 * v13;
    *((_DWORD *)v41 + v12 + 1) = v14;
    if ( v15 > 0xFFFFFFFF )
      goto LABEL_29;
    v16 = v15 + v10;
    if ( (unsigned int)v15 + v10 < (unsigned int)v15 || v16 + 3 < v16 )
    {
      v10 = -1;
      goto LABEL_29;
    }
    v10 = (v16 + 3) & 0xFFFFFFFC;
    ++v11;
  }
  while ( v11 < 0x12 );
  v17 = (char *)LocalAlloc(0, v10);
  v18 = v17;
  if ( !v17 )
  {
LABEL_29:
    WriteDbgTraceErrorGpd("BconsolidateBuffers", "Fatal: unable to alloc requested memory: %d bytes.", v10);
    result = 0;
    *(_DWORD *)(a2 + 2224) = 2;
    *(_DWORD *)(a2 + 2220) = 3;
    return result;
  }
  *(_DWORD *)(a2 + 720) = v10;
  v19 = 0;
  *(_QWORD *)(a2 + 768) = 0;
  *(_QWORD *)(a2 + 748) = 0;
  *(_OWORD *)v17 = *(_OWORD *)(a2 + 720);
  *((_OWORD *)v17 + 1) = *(_OWORD *)(a2 + 736);
  *((_OWORD *)v17 + 2) = *(_OWORD *)(a2 + 752);
  *((_OWORD *)v17 + 3) = *(_OWORD *)(a2 + 768);
  v20 = *(_QWORD *)(a2 + 784);
  *(_OWORD *)(v17 + 72) = v41[0];
  v21 = v41[2];
  *((_QWORD *)v17 + 8) = v20;
  *(_OWORD *)(v17 + 88) = v41[1];
  v22 = v41[3];
  *(_OWORD *)(v17 + 104) = v21;
  v23 = v41[4];
  *(_OWORD *)(v17 + 120) = v22;
  v24 = v41[5];
  *(_OWORD *)(v17 + 136) = v23;
  v25 = v41[6];
  *(_OWORD *)(v17 + 152) = v24;
  v26 = v41[7];
  *(_OWORD *)(v17 + 168) = v25;
  v27 = v41[8];
  *(_OWORD *)(v17 + 184) = v26;
  v28 = v41[9];
  *(_OWORD *)(v17 + 200) = v27;
  v29 = v41[10];
  *(_OWORD *)(v17 + 216) = v28;
  v30 = v41[11];
  *(_OWORD *)(v17 + 232) = v29;
  v31 = v41[12];
  *(_OWORD *)(v17 + 248) = v30;
  *(_OWORD *)(v17 + 264) = v31;
  *((_QWORD *)v17 + 35) = v42;
  do
  {
    memcpy_0(
      &v18[*(unsigned int *)((char *)v41 + v4)],
      *(const void **)(a2 + 24 * v19++),
      (unsigned int)(*(_DWORD *)((char *)v41 + v4 + 4) * *(_DWORD *)((char *)v41 + v4 + 8)));
    v4 += 12;
  }
  while ( v19 != 18 );
  NumberOfBytesWritten = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v44 = 0;
  GPDfilename = (const WCHAR *)pwstrGenerateGPDfilename(pszSrc);
  v33 = (WCHAR *)GPDfilename;
  if ( GPDfilename )
  {
    if ( !GetFileAttributesExW(GPDfilename, GetFileExInfoStandard, FileInformation) || DeleteFileW(v33) )
    {
      FileW = CreateFileW(v33, 0x40000000u, 0, 0, 2u, 0x8100080u, 0);
      v35 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        v36 = WriteFile(FileW, v18, v10, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == v10;
        CloseHandle(v35);
        if ( !v36 )
          DeleteFileW(v33);
      }
    }
    LocalFree(v33);
  }
  if ( a3 )
  {
    v37 = v40;
    *a3 = v18;
    *v37 = v10;
  }
  else
  {
    LocalFree(v18);
  }
  return 1;
}

```

## disassembly

```asm
0x18016c864  push    rbp
0x18016c866  push    rbx
0x18016c867  push    rsi
0x18016c868  push    rdi
0x18016c869  push    r12
0x18016c86b  push    r13
0x18016c86d  push    r14
0x18016c86f  push    r15
0x18016c871  lea     rbp, [rsp-68h]
0x18016c876  sub     rsp, 168h
0x18016c87d  mov     rax, cs:__security_cookie
0x18016c884  xor     rax, rsp
0x18016c887  mov     [rbp+0A0h+var_48], rax
0x18016c88b  xor     r12d, r12d
0x18016c88e  mov     [rsp+1A0h+var_158], r9
0x18016c893  mov     r14, r8
0x18016c896  mov     rdi, rdx
0x18016c899  mov     r13, rcx
0x18016c89c  test    r8, r8
0x18016c89f  jz      short loc_18016C8A4
0x18016c8a1  mov     [r8], r12
0x18016c8a4  mov     eax, 1
0x18016c8a9  mov     edx, r12d
0x18016c8ac  lea     rcx, [rax+rax*2]
0x18016c8b0  mov     eax, [rdi+rcx*8+8]
0x18016c8b4  mov     [rdi+rcx*8+0Ch], eax
0x18016c8b8  lea     eax, [rdx+0Bh]
0x18016c8bb  inc     edx
0x18016c8bd  cmp     edx, 4
0x18016c8c0  jl      short loc_18016C8AC
0x18016c8c2  lea     rcx, [rax+rax*2]
0x18016c8c6  mov     ebx, 120h
0x18016c8cb  mov     eax, [rdi+rcx*8+8]
0x18016c8cf  mov     r9d, r12d
0x18016c8d2  mov     [rdi+rcx*8+0Ch], eax
0x18016c8d6  mov     r10d, 0FFFFFFFFh
0x18016c8dc  mov     eax, [rdi+38h]
0x18016c8df  mov     [rdi+3Ch], eax
0x18016c8e2  mov     eax, [rdi+170h]
0x18016c8e8  mov     [rdi+174h], eax
0x18016c8ee  mov     eax, [rdi+188h]
0x18016c8f4  mov     [rdi+18Ch], eax
0x18016c8fa  mov     eax, r9d
0x18016c8fd  lea     rdx, [rax+rax*2]
0x18016c901  lea     rcx, [rax+rax*2]
0x18016c905  mov     dword ptr [rsp+rdx*4+1A0h+var_150], ebx
0x18016c909  mov     r8d, [rdi+rcx*8+10h]
0x18016c90e  mov     eax, [rdi+rcx*8+0Ch]
0x18016c912  mov     dword ptr [rsp+rdx*4+1A0h+var_150+8], r8d
0x18016c917  imul    r8, rax
0x18016c91b  mov     dword ptr [rsp+rdx*4+1A0h+var_150+4], eax
0x18016c91f  cmp     r8, r10
0x18016c922  ja      loc_18016CB68
0x18016c928  lea     eax, [r8+rbx]
0x18016c92c  cmp     eax, r8d
0x18016c92f  jb      loc_18016CB65
0x18016c935  lea     ebx, [rax+3]
0x18016c938  cmp     ebx, eax
0x18016c93a  jb      loc_18016CB65
0x18016c940  and     ebx, 0FFFFFFFCh
0x18016c943  inc     r9d
0x18016c946  cmp     r9d, 12h
0x18016c94a  jb      short loc_18016C8FA
0x18016c94c  mov     edx, ebx; uBytes
0x18016c94e  xor     ecx, ecx; uFlags
0x18016c950  call    cs:__imp_LocalAlloc
0x18016c956  mov     rsi, rax
0x18016c959  test    rax, rax
0x18016c95c  jz      loc_18016CB68
0x18016c962  mov     [rdi+2D0h], ebx
0x18016c968  mov     r15, r12
0x18016c96b  mov     [rdi+300h], r12
0x18016c972  mov     [rdi+2ECh], r12
0x18016c979  movups  xmm0, xmmword ptr [rdi+2D0h]
0x18016c980  movups  xmmword ptr [rax], xmm0
0x18016c983  movups  xmm1, xmmword ptr [rdi+2E0h]
0x18016c98a  movups  xmmword ptr [rax+10h], xmm1
0x18016c98e  movups  xmm0, xmmword ptr [rdi+2F0h]
0x18016c995  movups  xmmword ptr [rax+20h], xmm0
0x18016c999  movups  xmm1, xmmword ptr [rdi+300h]
0x18016c9a0  movups  xmmword ptr [rax+30h], xmm1
0x18016c9a4  movsd   xmm0, qword ptr [rdi+310h]
0x18016c9ac  movaps  xmm1, [rsp+1A0h+var_150]
0x18016c9b1  movups  xmmword ptr [rax+48h], xmm1
0x18016c9b5  movaps  xmm1, [rsp+1A0h+var_130]
0x18016c9ba  movsd   qword ptr [rax+40h], xmm0
0x18016c9bf  movaps  xmm0, [rsp+1A0h+var_140]
0x18016c9c4  movups  xmmword ptr [rax+58h], xmm0
0x18016c9c8  movaps  xmm0, [rbp+0A0h+var_120]
0x18016c9cc  movups  xmmword ptr [rax+68h], xmm1
0x18016c9d0  movaps  xmm1, [rbp+0A0h+var_110]
0x18016c9d4  movups  xmmword ptr [rax+78h], xmm0
0x18016c9d8  movaps  xmm0, [rbp+0A0h+var_100]
0x18016c9dc  movups  xmmword ptr [rax+88h], xmm1
0x18016c9e3  movaps  xmm1, [rbp+0A0h+var_F0]
0x18016c9e7  movups  xmmword ptr [rax+98h], xmm0
0x18016c9ee  movaps  xmm0, [rbp+0A0h+var_E0]
0x18016c9f2  movups  xmmword ptr [rax+0A8h], xmm1
0x18016c9f9  movaps  xmm1, [rbp+0A0h+var_D0]
0x18016c9fd  movups  xmmword ptr [rax+0B8h], xmm0
0x18016ca04  movaps  xmm0, [rbp+0A0h+var_C0]
0x18016ca08  movups  xmmword ptr [rax+0C8h], xmm1
0x18016ca0f  movaps  xmm1, [rbp+0A0h+var_B0]
0x18016ca13  movups  xmmword ptr [rax+0D8h], xmm0
0x18016ca1a  movaps  xmm0, [rbp+0A0h+var_A0]
0x18016ca1e  movups  xmmword ptr [rax+0E8h], xmm1
0x18016ca25  movaps  xmm1, [rbp+0A0h+var_90]
0x18016ca29  movups  xmmword ptr [rax+0F8h], xmm0
0x18016ca30  movups  xmmword ptr [rax+108h], xmm1
0x18016ca37  mov     rax, [rbp+0A0h+var_80]
0x18016ca3b  mov     [rsi+118h], rax
0x18016ca42  mov     r8d, dword ptr [rsp+r12+1A0h+var_150+8]
0x18016ca47  lea     rdx, [r15+r15*2]
0x18016ca4b  imul    r8d, dword ptr [rsp+r12+1A0h+var_150+4]; Size
0x18016ca51  mov     ecx, dword ptr [rsp+r12+1A0h+var_150]
0x18016ca56  mov     rdx, [rdi+rdx*8]; Src
0x18016ca5a  add     rcx, rsi; void *
0x18016ca5d  call    memcpy_0
0x18016ca62  inc     r15
0x18016ca65  lea     r12, [r12+0Ch]
0x18016ca6a  cmp     r15, 12h
0x18016ca6e  jnz     short loc_18016CA42
0x18016ca70  xorps   xmm0, xmm0
0x18016ca73  mov     [rsp+1A0h+NumberOfBytesWritten], 0
0x18016ca7b  xor     eax, eax
0x18016ca7d  mov     rcx, r13; pszSrc
0x18016ca80  movups  [rbp+0A0h+FileInformation], xmm0
0x18016ca84  mov     [rbp+0A0h+var_50], eax
0x18016ca87  movups  [rbp+0A0h+var_60], xmm0
0x18016ca8b  call    pwstrGenerateGPDfilename
0x18016ca90  mov     rdi, rax
0x18016ca93  test    rax, rax
0x18016ca96  jz      loc_18016CB44
0x18016ca9c  lea     r8, [rbp+0A0h+FileInformation]; lpFileInformation
0x18016caa0  xor     edx, edx; fInfoLevelId
0x18016caa2  mov     rcx, rax; lpFileName
0x18016caa5  call    cs:__imp_GetFileAttributesExW
0x18016caab  test    eax, eax
0x18016caad  jz      short loc_18016CABC
0x18016caaf  mov     rcx, rdi; lpFileName
0x18016cab2  call    cs:__imp_DeleteFileW
0x18016cab8  test    eax, eax
0x18016caba  jz      short loc_18016CB3B
0x18016cabc  mov     [rsp+1A0h+hTemplateFile], 0; hTemplateFile
0x18016cac5  xor     r9d, r9d; lpSecurityAttributes
0x18016cac8  mov     [rsp+1A0h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x18016cad0  xor     r8d, r8d; dwShareMode
0x18016cad3  mov     edx, 40000000h; dwDesiredAccess
0x18016cad8  mov     [rsp+1A0h+dwCreationDisposition], 2; dwCreationDisposition
0x18016cae0  mov     rcx, rdi; lpFileName
0x18016cae3  call    cs:__imp_CreateFileW
0x18016cae9  mov     r15, rax
0x18016caec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18016caf0  jz      short loc_18016CB3B
0x18016caf2  lea     r9, [rsp+1A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18016caf7  mov     qword ptr [rsp+1A0h+dwCreationDisposition], 0; lpOverlapped
0x18016cb00  mov     r8d, ebx; nNumberOfBytesToWrite
0x18016cb03  mov     rdx, rsi; lpBuffer
0x18016cb06  mov     rcx, rax; hFile
0x18016cb09  call    cs:__imp_WriteFile
0x18016cb0f  test    eax, eax
0x18016cb11  jz      short loc_18016CB21
0x18016cb13  cmp     [rsp+1A0h+NumberOfBytesWritten], ebx
0x18016cb17  jnz     short loc_18016CB21
0x18016cb19  mov     r12d, 1
0x18016cb1f  jmp     short loc_18016CB24
0x18016cb21  xor     r12d, r12d
0x18016cb24  mov     rcx, r15; hObject
0x18016cb27  call    cs:__imp_CloseHandle
0x18016cb2d  test    r12d, r12d
0x18016cb30  jnz     short loc_18016CB3B
0x18016cb32  mov     rcx, rdi; lpFileName
0x18016cb35  call    cs:__imp_DeleteFileW
0x18016cb3b  mov     rcx, rdi; hMem
0x18016cb3e  call    cs:__imp_LocalFree
0x18016cb44  test    r14, r14
0x18016cb47  jz      short loc_18016CB55
0x18016cb49  mov     rax, [rsp+1A0h+var_158]
0x18016cb4e  mov     [r14], rsi
0x18016cb51  mov     [rax], ebx
0x18016cb53  jmp     short loc_18016CB5E
0x18016cb55  mov     rcx, rsi; hMem
0x18016cb58  call    cs:__imp_LocalFree
0x18016cb5e  mov     eax, 1
0x18016cb63  jmp     short loc_18016CB94
0x18016cb65  mov     ebx, r10d
0x18016cb68  mov     r8d, ebx
0x18016cb6b  lea     rdx, aFatalUnableToA; "Fatal: unable to alloc requested memory"...
0x18016cb72  lea     rcx, aBconsolidatebu; "BconsolidateBuffers"
0x18016cb79  call    WriteDbgTraceErrorGpd
0x18016cb7e  xor     eax, eax
0x18016cb80  mov     dword ptr [rdi+8B0h], 2
0x18016cb8a  mov     dword ptr [rdi+8ACh], 3
0x18016cb94  mov     rcx, [rbp+0A0h+var_48]
0x18016cb98  xor     rcx, rsp; StackCookie
0x18016cb9b  call    __security_check_cookie
0x18016cba0  add     rsp, 168h
0x18016cba7  pop     r15
0x18016cba9  pop     r14
0x18016cbab  pop     r13
0x18016cbad  pop     r12
0x18016cbaf  pop     rdi
0x18016cbb0  pop     rsi
0x18016cbb1  pop     rbx
0x18016cbb2  pop     rbp
0x18016cbb3  retn
```
