# CreateCacheFile(C_SERIALIZE_PACKET *,ushort *,ulong,ulong,ulong *,_iobuf *,int *)

- ea: `0x180190ca8`
- end: `0x1801910d9`
- name: `?CreateCacheFile@@YAHPEAVC_SERIALIZE_PACKET@@PEAGKKPEAKPEAU_iobuf@@PEAH@Z`
- size: `1073`
- prototype: `__int64 __fastcall(struct C_SERIALIZE_PACKET *, wchar_t *lpFileName, unsigned int, unsigned int, unsigned int *, struct _iobuf *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18017fee4`

## callees

- `0x180003400`
- `0x180003424`
- `0x180003c20`
- `0x18000442c`
- `0x180004438`
- `0x1801502f4`
- `0x1801850b8`
- `0x1801854bc`
- `0x180190ca8`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x180190f1e`
- `KERNEL32!GetTempFileNameW` at `0x180190f1e`
- `KERNEL32!WriteFile` at `0x180191031`
- `KERNEL32!WriteFile` at `0x180191031`
- `KERNEL32!DeleteFileW` at `0x180190ddc`
- `KERNEL32!DeleteFileW` at `0x180190ddc`
- `KERNEL32!GetFileAttributesExW` at `0x180190dc2`
- `KERNEL32!GetFileAttributesExW` at `0x180190dc2`
- `KERNEL32!CreateFileW` at `0x180191006`
- `KERNEL32!CreateFileW` at `0x180191006`
- `KERNEL32!CloseHandle` at `0x180191055`
- `KERNEL32!CloseHandle` at `0x180191055`
- `KERNEL32!MoveFileExW` at `0x180190f7e`
- `KERNEL32!MoveFileExW` at `0x180190fa0`
- `KERNEL32!MoveFileExW` at `0x180190f7e`
- `KERNEL32!MoveFileExW` at `0x180190fa0`

## string_xrefs

- `0x180190f2e`: `CreateCacheFile: Unable to create Tmp Name.\n`
- `0x180190f8e`: `CreateCacheFile: Unable to rename existing cache file to Tmp Name.\n`
- `0x180191065`: `CreateCacheFile: Unable to write cache file to File System.\n`
- `0x180190d23`: `CreateCacheFile: C_SERIALIZE::SaveGraph Failed.\n`
- `0x180190d7b`: `CreateCacheFile: SerializeTree Failed.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=57
__int64 __fastcall CreateCacheFile(
        struct C_SERIALIZE_PACKET *a1,
        wchar_t *lpFileName,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5,
        struct _iobuf *a6,
        int *a7)
{
  struct _iobuf *v8; // rdi
  wchar_t *v9; // rsi
  int v12; // eax
  unsigned __int64 v14; // r14
  unsigned __int8 *v15; // r12
  char *v16; // rdx
  unsigned __int64 v17; // xmm1_8
  unsigned int v18; // eax
  void *v19; // r15
  __int64 v20; // rdi
  DWORD v21; // edi
  void *Filename; // r13
  unsigned int v23; // eax
  void *v24; // rbx
  void *v25; // rsi
  char *v26; // rdx
  HANDLE FileW; // rax
  void *v28; // rbx
  int v29; // esi
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-71h] BYREF
  unsigned int v31; // [rsp+54h] [rbp-6Dh]
  DWORD v32; // [rsp+58h] [rbp-69h]
  DWORD v33; // [rsp+5Ch] [rbp-65h]
  wchar_t *FullPath; // [rsp+60h] [rbp-61h]
  struct _iobuf *v35; // [rsp+68h] [rbp-59h]
  __int128 v36; // [rsp+70h] [rbp-51h]
  unsigned __int64 v37; // [rsp+80h] [rbp-41h]
  int *v38; // [rsp+88h] [rbp-39h]
  _OWORD FileInformation[2]; // [rsp+90h] [rbp-31h] BYREF
  int v40; // [rsp+B0h] [rbp-11h]

  v8 = a6;
  v40 = 0;
  v9 = lpFileName;
  FullPath = lpFileName;
  *a7 = 1;
  v35 = a6;
  v38 = a7;
  memset(FileInformation, 0, sizeof(FileInformation));
  v12 = C_SERIALIZE::SaveGraph(a1, 0);
  DWORD1(v36) = v12;
  if ( !v12 )
  {
    ErrorMessage(a6, "CreateCacheFile: C_SERIALIZE::SaveGraph Failed.\n", 2u);
    return 0;
  }
  v14 = (unsigned int)(v12 + 24);
  v31 = 0;
  LODWORD(v36) = 0;
  DWORD1(v36) = v12 + 24;
  *((_QWORD *)&v36 + 1) = 0x1C05251955LL;
  v37 = __PAIR64__(a4, a3);
  v15 = (unsigned __int8 *)operator new((unsigned int)v14);
  if ( (unsigned int)C_SERIALIZE::SaveGraph(a1, v15 + 24) != v14 - 24 )
  {
    v16 = "CreateCacheFile: SerializeTree Failed.\n";
LABEL_37:
    ErrorMessage(v8, v16, 2u);
    goto LABEL_38;
  }
  v17 = v37;
  *(_OWORD *)v15 = v36;
  *((_QWORD *)v15 + 2) = v17;
  v18 = ComputeCrc32Checksum(v15 + 4, (int)v14 - 4, 0);
  if ( a5 )
    *a5 = v18;
  *(_DWORD *)v15 = v18;
  v19 = 0;
  if ( !GetFileAttributesExW(v9, GetFileExInfoStandard, FileInformation) || DeleteFileW(v9) )
    goto LABEL_31;
  v20 = -1;
  do
    ++v20;
  while ( v9[v20] );
  v21 = 2 * v20 + 2;
  if ( v21 )
  {
    v19 = operator new(v21);
    v14 = (unsigned __int64)operator new(v21);
    v32 = v21;
    Filename = operator new(v21);
    v33 = v21;
    v23 = v21 + 520;
    NumberOfBytesWritten = v21;
    v24 = 0;
    if ( v21 == -520 )
      goto LABEL_17;
  }
  else
  {
    v23 = 520;
    v32 = NumberOfBytesWritten;
    Filename = 0;
    v14 = 0;
    v33 = NumberOfBytesWritten;
  }
  v24 = operator new(v23);
LABEL_17:
  v25 = 0;
  if ( v21 )
    v25 = operator new(v21);
  else
    v21 = NumberOfBytesWritten;
  if ( !v19 || !v14 || !Filename || !v24 || !v25 )
  {
    *v38 = 0;
    operator delete(v25);
    operator delete(v24);
    operator delete(Filename);
    operator delete((void *)v14);
    operator delete(v19);
    return 0;
  }
  wsplitpath_s(
    FullPath,
    (wchar_t *)v19,
    (unsigned __int64)NumberOfBytesWritten >> 1,
    (wchar_t *)v14,
    (unsigned __int64)v33 >> 1,
    (wchar_t *)Filename,
    (unsigned __int64)v32 >> 1,
    0,
    0);
  wmakepath_s(
    (wchar_t *)v25,
    (unsigned __int64)v21 >> 1,
    (const wchar_t *)v19,
    (const wchar_t *)v14,
    &::Filename,
    &::Filename);
  if ( GetTempFileNameW((LPCWSTR)v25, L"SER", 0, (LPWSTR)v24) )
  {
    if ( !MoveFileExW(FullPath, (LPCWSTR)v24, 1u) )
    {
      v26 = "CreateCacheFile: Unable to rename existing cache file to Tmp Name.\n";
      goto LABEL_27;
    }
    MoveFileExW((LPCWSTR)v24, 0, 4u);
    operator delete(v25);
    operator delete(v24);
    operator delete(Filename);
    operator delete((void *)v14);
    operator delete(v19);
    v9 = FullPath;
    v8 = v35;
    LODWORD(v14) = DWORD1(v36);
LABEL_31:
    FileW = CreateFileW(v9, 0x40000000u, 0, 0, 2u, 0x8000080u, 0);
    v28 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      NumberOfBytesWritten = 0;
      if ( !WriteFile(FileW, v15, v14, &NumberOfBytesWritten, 0) || (v29 = 1, (_DWORD)v14 != NumberOfBytesWritten) )
        v29 = 0;
      v31 = v29;
      CloseHandle(v28);
      if ( v29 )
        goto LABEL_38;
    }
    v16 = "CreateCacheFile: Unable to write cache file to File System.\n";
    goto LABEL_37;
  }
  v26 = "CreateCacheFile: Unable to create Tmp Name.\n";
LABEL_27:
  ErrorMessage(v35, v26, 2u);
  operator delete(v25);
  operator delete(v24);
  operator delete(Filename);
  operator delete((void *)v14);
  operator delete(v19);
LABEL_38:
  operator delete(v15);
  return v31;
}

```

## disassembly

```asm
0x180190ca8  push    rbp
0x180190caa  push    rbx
0x180190cab  push    rsi
0x180190cac  push    rdi
0x180190cad  push    r12
0x180190caf  push    r13
0x180190cb1  push    r14
0x180190cb3  push    r15
0x180190cb5  lea     rbp, [rsp-7]
0x180190cba  sub     rsp, 0C8h
0x180190cc1  mov     rax, cs:__security_cookie
0x180190cc8  xor     rax, rsp
0x180190ccb  mov     [rbp+3Fh+var_48], rax
0x180190ccf  mov     rax, [rbp+3Fh+arg_30]
0x180190cd3  mov     r13, rcx
0x180190cd6  mov     rdi, [rbp+3Fh+arg_28]
0x180190cda  xor     ecx, ecx
0x180190cdc  mov     r15, [rbp+3Fh+arg_20]
0x180190ce0  xorps   xmm0, xmm0
0x180190ce3  mov     [rbp+3Fh+var_50], ecx
0x180190ce6  mov     rsi, rdx
0x180190ce9  mov     [rbp+3Fh+FullPath], rdx
0x180190ced  mov     rcx, r13; struct C_SERIALIZE_PACKET *
0x180190cf0  xor     edx, edx; unsigned __int8 *
0x180190cf2  mov     dword ptr [rax], 1
0x180190cf8  mov     r12d, r9d
0x180190cfb  mov     [rbp+3Fh+var_98], rdi
0x180190cff  mov     ebx, r8d
0x180190d02  mov     [rbp+3Fh+var_78], rax
0x180190d06  movups  [rbp+3Fh+FileInformation], xmm0
0x180190d0a  movups  [rbp+3Fh+var_60], xmm0
0x180190d0e  call    ?SaveGraph@C_SERIALIZE@@SAKPEAVC_SERIALIZE_PACKET@@PEAE@Z; C_SERIALIZE::SaveGraph(C_SERIALIZE_PACKET *,uchar *)
0x180190d13  xor     ecx, ecx
0x180190d15  mov     dword ptr [rbp+3Fh+var_90+4], eax
0x180190d18  test    eax, eax
0x180190d1a  jnz     short loc_180190D36
0x180190d1c  lea     r8d, [rax+2]; unsigned int
0x180190d20  mov     rcx, rdi; struct _iobuf *
0x180190d23  lea     rdx, aCreatecachefil_2; "CreateCacheFile: C_SERIALIZE::SaveGraph"...
0x180190d2a  call    ?ErrorMessage@@YAXPEAU_iobuf@@PEADK@Z; ErrorMessage(_iobuf *,char *,ulong)
0x180190d2f  xor     eax, eax
0x180190d31  jmp     loc_180191085
0x180190d36  lea     r14d, [rax+18h]
0x180190d3a  mov     [rbp+3Fh+var_AC], ecx
0x180190d3d  mov     dword ptr [rbp+3Fh+var_90], ecx
0x180190d40  mov     ecx, r14d; Size
0x180190d43  mov     dword ptr [rbp+3Fh+var_90+4], r14d
0x180190d47  mov     dword ptr [rbp+3Fh+var_90+8], 5251955h
0x180190d4e  mov     dword ptr [rbp+3Fh+var_90+0Ch], 1Ch
0x180190d55  mov     dword ptr [rbp+3Fh+var_80], ebx
0x180190d58  mov     dword ptr [rbp+3Fh+var_80+4], r12d
0x180190d5c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180190d61  mov     rcx, r13; struct C_SERIALIZE_PACKET *
0x180190d64  mov     r12, rax
0x180190d67  lea     rdx, [rax+18h]; unsigned __int8 *
0x180190d6b  call    ?SaveGraph@C_SERIALIZE@@SAKPEAVC_SERIALIZE_PACKET@@PEAE@Z; C_SERIALIZE::SaveGraph(C_SERIALIZE_PACKET *,uchar *)
0x180190d70  mov     edx, eax
0x180190d72  lea     rcx, [r14-18h]
0x180190d76  cmp     rdx, rcx
0x180190d79  jz      short loc_180190D87
0x180190d7b  lea     rdx, aCreatecachefil; "CreateCacheFile: SerializeTree Failed."...
0x180190d82  jmp     loc_18019106C
0x180190d87  movups  xmm0, [rbp+3Fh+var_90]
0x180190d8b  lea     edx, [r14-4]
0x180190d8f  xor     r8d, r8d
0x180190d92  movsd   xmm1, [rbp+3Fh+var_80]
0x180190d97  lea     rcx, [r12+4]
0x180190d9c  movups  xmmword ptr [r12], xmm0
0x180190da1  movsd   qword ptr [r12+10h], xmm1
0x180190da8  call    ComputeCrc32Checksum
0x180190dad  test    r15, r15
0x180190db0  jz      short loc_180190DB5
0x180190db2  mov     [r15], eax
0x180190db5  lea     r8, [rbp+3Fh+FileInformation]; lpFileInformation
0x180190db9  mov     [r12], eax
0x180190dbd  xor     edx, edx; fInfoLevelId
0x180190dbf  mov     rcx, rsi; lpFileName
0x180190dc2  call    cs:__imp_GetFileAttributesExW
0x180190dc9  nop     dword ptr [rax+rax+00h]
0x180190dce  xor     r15d, r15d
0x180190dd1  test    eax, eax
0x180190dd3  jz      loc_180190FE3
0x180190dd9  mov     rcx, rsi; lpFileName
0x180190ddc  call    cs:__imp_DeleteFileW
0x180190de3  nop     dword ptr [rax+rax+00h]
0x180190de8  test    eax, eax
0x180190dea  jnz     loc_180190FE3
0x180190df0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180190df4  inc     rdi
0x180190df7  cmp     [rsi+rdi*2], r15w
0x180190dfc  jnz     short loc_180190DF4
0x180190dfe  lea     edi, ds:2[rdi*2]
0x180190e05  test    edi, edi
0x180190e07  jz      short loc_180190E40
0x180190e09  mov     ecx, edi; Size
0x180190e0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180190e10  mov     ecx, edi; Size
0x180190e12  mov     r15, rax
0x180190e15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180190e1a  mov     ecx, edi; Size
0x180190e1c  mov     r14, rax
0x180190e1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180190e24  xor     edx, edx
0x180190e26  mov     [rbp+3Fh+var_A8], edi
0x180190e29  mov     r13, rax
0x180190e2c  mov     [rbp+3Fh+var_A4], edi
0x180190e2f  lea     eax, [rdi+208h]
0x180190e35  mov     [rbp+3Fh+NumberOfBytesWritten], edi
0x180190e38  mov     ebx, edx
0x180190e3a  test    eax, eax
0x180190e3c  jz      short loc_180190E6A
0x180190e3e  jmp     short loc_180190E5E
0x180190e40  mov     ecx, [rbp+3Fh+NumberOfBytesWritten]
0x180190e43  lea     eax, [rdi+208h]
0x180190e49  mov     [rbp+3Fh+var_A8], ecx
0x180190e4c  mov     r13, r15
0x180190e4f  mov     ecx, [rbp+3Fh+NumberOfBytesWritten]
0x180190e52  mov     r14, r15
0x180190e55  mov     [rbp+3Fh+var_A4], ecx
0x180190e58  mov     ecx, [rbp+3Fh+NumberOfBytesWritten]
0x180190e5b  mov     [rbp+3Fh+NumberOfBytesWritten], ecx
0x180190e5e  mov     ecx, eax; Size
0x180190e60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180190e65  mov     rbx, rax
0x180190e68  xor     edx, edx
0x180190e6a  mov     rsi, rdx
0x180190e6d  test    edi, edi
0x180190e6f  jz      short loc_180190E7F
0x180190e71  mov     ecx, edi; Size
0x180190e73  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180190e78  mov     rsi, rax
0x180190e7b  xor     edx, edx
0x180190e7d  jmp     short loc_180190E82
0x180190e7f  mov     edi, [rbp+3Fh+NumberOfBytesWritten]
0x180190e82  test    r15, r15
0x180190e85  jz      loc_1801910A6
0x180190e8b  test    r14, r14
0x180190e8e  jz      loc_1801910A6
0x180190e94  test    r13, r13
0x180190e97  jz      loc_1801910A6
0x180190e9d  test    rbx, rbx
0x180190ea0  jz      loc_1801910A6
0x180190ea6  test    rsi, rsi
0x180190ea9  jz      loc_1801910A6
0x180190eaf  mov     eax, [rbp+3Fh+var_A8]
0x180190eb2  mov     r9, r14; Dir
0x180190eb5  mov     ecx, [rbp+3Fh+var_A4]
0x180190eb8  mov     r8d, [rbp+3Fh+NumberOfBytesWritten]
0x180190ebc  mov     [rsp+100h+ExtCount], rdx; ExtCount
0x180190ec1  mov     [rsp+100h+Ext], rdx; Ext
0x180190ec6  mov     rdx, r15; Drive
0x180190ec9  shr     rcx, 1
0x180190ecc  shr     rax, 1
0x180190ecf  mov     [rsp+100h+FilenameCount], rax; FilenameCount
0x180190ed4  mov     [rsp+100h+Filename], r13; Filename
0x180190ed9  mov     [rsp+100h+DirCount], rcx; DirCount
0x180190ede  mov     rcx, [rbp+3Fh+FullPath]; FullPath
0x180190ee2  shr     r8, 1; DriveCount
0x180190ee5  call    _wsplitpath_s
0x180190eea  lea     rax, Filename
0x180190ef1  mov     edx, edi
0x180190ef3  mov     [rsp+100h+Filename], rax; Ext
0x180190ef8  mov     r9, r14; Dir
0x180190efb  shr     rdx, 1; BufferCount
0x180190efe  mov     r8, r15; Drive
0x180190f01  mov     rcx, rsi; Buffer
0x180190f04  mov     [rsp+100h+DirCount], rax; Filename
0x180190f09  call    _wmakepath_s
0x180190f0e  mov     r9, rbx; lpTempFileName
0x180190f11  lea     rdx, aSer_0; "SER"
0x180190f18  xor     r8d, r8d; uUnique
0x180190f1b  mov     rcx, rsi; lpPathName
0x180190f1e  call    cs:__imp_GetTempFileNameW
0x180190f25  nop     dword ptr [rax+rax+00h]
0x180190f2a  test    eax, eax
0x180190f2c  jnz     short loc_180190F71
0x180190f2e  lea     rdx, aCreatecachefil_0; "CreateCacheFile: Unable to create Tmp N"...
0x180190f35  mov     rcx, [rbp+3Fh+var_98]; struct _iobuf *
0x180190f39  mov     r8d, 2; unsigned int
0x180190f3f  call    ?ErrorMessage@@YAXPEAU_iobuf@@PEADK@Z; ErrorMessage(_iobuf *,char *,ulong)
0x180190f44  mov     rcx, rsi; Block
0x180190f47  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180190f4c  mov     rcx, rbx; Block
0x180190f4f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180190f54  mov     rcx, r13; Block
0x180190f57  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180190f5c  mov     rcx, r14; Block
0x180190f5f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180190f64  mov     rcx, r15; Block
0x180190f67  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180190f6c  jmp     loc_18019107A
0x180190f71  mov     rcx, [rbp+3Fh+FullPath]; lpExistingFileName
0x180190f75  mov     r8d, 1; dwFlags
0x180190f7b  mov     rdx, rbx; lpNewFileName
0x180190f7e  call    cs:__imp_MoveFileExW
0x180190f85  nop     dword ptr [rax+rax+00h]
0x180190f8a  test    eax, eax
0x180190f8c  jnz     short loc_180190F97
0x180190f8e  lea     rdx, aCreatecachefil_1; "CreateCacheFile: Unable to rename exist"...
0x180190f95  jmp     short loc_180190F35
0x180190f97  xor     edx, edx; lpNewFileName
0x180190f99  mov     rcx, rbx; lpExistingFileName
0x180190f9c  lea     r8d, [rdx+4]; dwFlags
0x180190fa0  call    cs:__imp_MoveFileExW
0x180190fa7  nop     dword ptr [rax+rax+00h]
0x180190fac  mov     rcx, rsi; Block
0x180190faf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180190fb4  mov     rcx, rbx; Block
0x180190fb7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180190fbc  mov     rcx, r13; Block
0x180190fbf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180190fc4  mov     rcx, r14; Block
0x180190fc7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180190fcc  mov     rcx, r15; Block
0x180190fcf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180190fd4  mov     rsi, [rbp+3Fh+FullPath]
0x180190fd8  xor     r15d, r15d
0x180190fdb  mov     rdi, [rbp+3Fh+var_98]
0x180190fdf  mov     r14d, dword ptr [rbp+3Fh+var_90+4]
0x180190fe3  mov     [rsp+100h+FilenameCount], r15; hTemplateFile
0x180190fe8  xor     r9d, r9d; lpSecurityAttributes
0x180190feb  mov     dword ptr [rsp+100h+Filename], 8000080h; dwFlagsAndAttributes
0x180190ff3  xor     r8d, r8d; dwShareMode
0x180190ff6  mov     edx, 40000000h; dwDesiredAccess
0x180190ffb  mov     dword ptr [rsp+100h+DirCount], 2; dwCreationDisposition
0x180191003  mov     rcx, rsi; lpFileName
0x180191006  call    cs:__imp_CreateFileW
0x18019100d  nop     dword ptr [rax+rax+00h]
0x180191012  mov     rbx, rax
0x180191015  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180191019  jz      short loc_180191065
0x18019101b  lea     r9, [rbp+3Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18019101f  mov     [rbp+3Fh+NumberOfBytesWritten], r15d
0x180191023  mov     r8d, r14d; nNumberOfBytesToWrite
0x180191026  mov     [rsp+100h+DirCount], r15; lpOverlapped
0x18019102b  mov     rdx, r12; lpBuffer
0x18019102e  mov     rcx, rax; hFile
0x180191031  call    cs:__imp_WriteFile
0x180191038  nop     dword ptr [rax+rax+00h]
0x18019103d  test    eax, eax
0x18019103f  jz      short loc_18019104C
0x180191041  mov     esi, 1
0x180191046  cmp     r14d, [rbp+3Fh+NumberOfBytesWritten]
0x18019104a  jz      short loc_18019104F
0x18019104c  mov     esi, r15d
0x18019104f  mov     rcx, rbx; hObject
0x180191052  mov     [rbp+3Fh+var_AC], esi
0x180191055  call    cs:__imp_CloseHandle
0x18019105c  nop     dword ptr [rax+rax+00h]
0x180191061  test    esi, esi
0x180191063  jnz     short loc_18019107A
0x180191065  lea     rdx, aCreatecachefil_3; "CreateCacheFile: Unable to write cache "...
0x18019106c  mov     r8d, 2; unsigned int
0x180191072  mov     rcx, rdi; struct _iobuf *
0x180191075  call    ?ErrorMessage@@YAXPEAU_iobuf@@PEADK@Z; ErrorMessage(_iobuf *,char *,ulong)
0x18019107a  mov     rcx, r12; Block
0x18019107d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180191082  mov     eax, [rbp+3Fh+var_AC]
0x180191085  mov     rcx, [rbp+3Fh+var_48]
0x180191089  xor     rcx, rsp; StackCookie
0x18019108c  call    __security_check_cookie
0x180191091  add     rsp, 0C8h
0x180191098  pop     r15
0x18019109a  pop     r14
0x18019109c  pop     r13
0x18019109e  pop     r12
0x1801910a0  pop     rdi
0x1801910a1  pop     rsi
0x1801910a2  pop     rbx
0x1801910a3  pop     rbp
0x1801910a4  retn
0x1801910a6  mov     rax, [rbp+3Fh+var_78]
0x1801910aa  mov     rcx, rsi; Block
0x1801910ad  mov     [rax], edx
0x1801910af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801910b4  mov     rcx, rbx; Block
0x1801910b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801910bc  mov     rcx, r13; Block
0x1801910bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801910c4  mov     rcx, r14; Block
0x1801910c7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801910cc  mov     rcx, r15; Block
0x1801910cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801910d4  jmp     loc_180190D2F
```
