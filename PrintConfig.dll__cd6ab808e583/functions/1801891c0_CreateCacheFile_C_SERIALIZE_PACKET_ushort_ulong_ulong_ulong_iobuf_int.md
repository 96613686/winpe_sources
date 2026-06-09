# CreateCacheFile(C_SERIALIZE_PACKET *,ushort *,ulong,ulong,ulong *,_iobuf *,int *)

- ea: `0x1801891c0`
- end: `0x1801895c0`
- name: `?CreateCacheFile@@YAHPEAVC_SERIALIZE_PACKET@@PEAGKKPEAKPEAU_iobuf@@PEAH@Z`
- size: `1024`
- prototype: `__int64 __usercall@<rax>(struct C_SERIALIZE_PACKET *@<rcx>, LPCWSTR lpFileName@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int *, struct _iobuf *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18017835c`

## callees

- `0x1800032e0`
- `0x180003304`
- `0x180003b00`
- `0x1800042ec`
- `0x1800042f8`
- `0x1801495bc`
- `0x18017d480`
- `0x18017d874`
- `0x1801891c0`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x18018942a`
- `KERNEL32!GetTempFileNameW` at `0x18018942a`
- `KERNEL32!WriteFile` at `0x180189525`
- `KERNEL32!WriteFile` at `0x180189525`
- `KERNEL32!DeleteFileW` at `0x1801892ee`
- `KERNEL32!DeleteFileW` at `0x1801892ee`
- `KERNEL32!GetFileAttributesExW` at `0x1801892da`
- `KERNEL32!GetFileAttributesExW` at `0x1801892da`
- `KERNEL32!CreateFileW` at `0x180189500`
- `KERNEL32!CreateFileW` at `0x180189500`
- `KERNEL32!CloseHandle` at `0x180189543`
- `KERNEL32!CloseHandle` at `0x180189543`
- `KERNEL32!MoveFileExW` at `0x180189484`
- `KERNEL32!MoveFileExW` at `0x1801894a0`
- `KERNEL32!MoveFileExW` at `0x180189484`
- `KERNEL32!MoveFileExW` at `0x1801894a0`

## string_xrefs

- `0x18018923b`: `CreateCacheFile: C_SERIALIZE::SaveGraph Failed.\n`
- `0x180189293`: `CreateCacheFile: SerializeTree Failed.\n`
- `0x180189434`: `CreateCacheFile: Unable to create Tmp Name.\n`
- `0x18018948e`: `CreateCacheFile: Unable to rename existing cache file to Tmp Name.\n`
- `0x18018954d`: `CreateCacheFile: Unable to write cache file to File System.\n`

## pseudocode

```c
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
  unsigned int v12; // eax
  char *v14; // r14
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
  v14 = (char *)(v12 + 24);
  v31 = 0;
  LODWORD(v36) = 0;
  DWORD1(v36) = v12 + 24;
  *((_QWORD *)&v36 + 1) = 0x1C05251955LL;
  v37 = __PAIR64__(a4, a3);
  v15 = (unsigned __int8 *)operator new((unsigned int)v14);
  if ( (char *)C_SERIALIZE::SaveGraph(a1, v15 + 24) != v14 - 24 )
  {
    v16 = "CreateCacheFile: SerializeTree Failed.\n";
LABEL_37:
    ErrorMessage(v8, v16, 2u);
    goto LABEL_38;
  }
  v17 = v37;
  *(_OWORD *)v15 = v36;
  *((_QWORD *)v15 + 2) = v17;
  v18 = ComputeCrc32Checksum(v15 + 4, (unsigned int)((_DWORD)v14 - 4), 0);
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
    v14 = (char *)operator new(v21);
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
    operator delete(v14);
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
    operator delete(v14);
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
      if ( !WriteFile(FileW, v15, (DWORD)v14, &NumberOfBytesWritten, 0)
        || (v29 = 1, (_DWORD)v14 != NumberOfBytesWritten) )
      {
        v29 = 0;
      }
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
  operator delete(v14);
  operator delete(v19);
LABEL_38:
  operator delete(v15);
  return v31;
}

```

## disassembly

```asm
0x1801891c0  push    rbp
0x1801891c2  push    rbx
0x1801891c3  push    rsi
0x1801891c4  push    rdi
0x1801891c5  push    r12
0x1801891c7  push    r13
0x1801891c9  push    r14
0x1801891cb  push    r15
0x1801891cd  lea     rbp, [rsp-7]
0x1801891d2  sub     rsp, 0C8h
0x1801891d9  mov     rax, cs:__security_cookie
0x1801891e0  xor     rax, rsp
0x1801891e3  mov     [rbp+3Fh+var_48], rax
0x1801891e7  mov     rax, [rbp+3Fh+arg_30]
0x1801891eb  mov     r13, rcx
0x1801891ee  mov     rdi, [rbp+3Fh+arg_28]
0x1801891f2  xor     ecx, ecx
0x1801891f4  mov     r15, [rbp+3Fh+arg_20]
0x1801891f8  xorps   xmm0, xmm0
0x1801891fb  mov     [rbp+3Fh+var_50], ecx
0x1801891fe  mov     rsi, rdx
0x180189201  mov     [rbp+3Fh+FullPath], rdx
0x180189205  mov     rcx, r13; struct C_SERIALIZE_PACKET *
0x180189208  xor     edx, edx; unsigned __int8 *
0x18018920a  mov     dword ptr [rax], 1
0x180189210  mov     r12d, r9d
0x180189213  mov     [rbp+3Fh+var_98], rdi
0x180189217  mov     ebx, r8d
0x18018921a  mov     [rbp+3Fh+var_78], rax
0x18018921e  movups  [rbp+3Fh+FileInformation], xmm0
0x180189222  movups  [rbp+3Fh+var_60], xmm0
0x180189226  call    ?SaveGraph@C_SERIALIZE@@SAKPEAVC_SERIALIZE_PACKET@@PEAE@Z; C_SERIALIZE::SaveGraph(C_SERIALIZE_PACKET *,uchar *)
0x18018922b  xor     ecx, ecx
0x18018922d  mov     dword ptr [rbp+3Fh+var_90+4], eax
0x180189230  test    eax, eax
0x180189232  jnz     short loc_18018924E
0x180189234  lea     r8d, [rax+2]; unsigned int
0x180189238  mov     rcx, rdi; struct _iobuf *
0x18018923b  lea     rdx, aCreatecachefil_2; "CreateCacheFile: C_SERIALIZE::SaveGraph"...
0x180189242  call    ?ErrorMessage@@YAXPEAU_iobuf@@PEADK@Z; ErrorMessage(_iobuf *,char *,ulong)
0x180189247  xor     eax, eax
0x180189249  jmp     loc_18018956D
0x18018924e  lea     r14d, [rax+18h]
0x180189252  mov     [rbp+3Fh+var_AC], ecx
0x180189255  mov     dword ptr [rbp+3Fh+var_90], ecx
0x180189258  mov     ecx, r14d; Size
0x18018925b  mov     dword ptr [rbp+3Fh+var_90+4], r14d
0x18018925f  mov     dword ptr [rbp+3Fh+var_90+8], 5251955h
0x180189266  mov     dword ptr [rbp+3Fh+var_90+0Ch], 1Ch
0x18018926d  mov     dword ptr [rbp+3Fh+var_80], ebx
0x180189270  mov     dword ptr [rbp+3Fh+var_80+4], r12d
0x180189274  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180189279  mov     rcx, r13; struct C_SERIALIZE_PACKET *
0x18018927c  mov     r12, rax
0x18018927f  lea     rdx, [rax+18h]; unsigned __int8 *
0x180189283  call    ?SaveGraph@C_SERIALIZE@@SAKPEAVC_SERIALIZE_PACKET@@PEAE@Z; C_SERIALIZE::SaveGraph(C_SERIALIZE_PACKET *,uchar *)
0x180189288  mov     edx, eax
0x18018928a  lea     rcx, [r14-18h]
0x18018928e  cmp     rdx, rcx
0x180189291  jz      short loc_18018929F
0x180189293  lea     rdx, aCreatecachefil; "CreateCacheFile: SerializeTree Failed."...
0x18018929a  jmp     loc_180189554
0x18018929f  movups  xmm0, [rbp+3Fh+var_90]
0x1801892a3  lea     edx, [r14-4]
0x1801892a7  xor     r8d, r8d
0x1801892aa  movsd   xmm1, [rbp+3Fh+var_80]
0x1801892af  lea     rcx, [r12+4]
0x1801892b4  movups  xmmword ptr [r12], xmm0
0x1801892b9  movsd   qword ptr [r12+10h], xmm1
0x1801892c0  call    ComputeCrc32Checksum
0x1801892c5  test    r15, r15
0x1801892c8  jz      short loc_1801892CD
0x1801892ca  mov     [r15], eax
0x1801892cd  lea     r8, [rbp+3Fh+FileInformation]; lpFileInformation
0x1801892d1  mov     [r12], eax
0x1801892d5  xor     edx, edx; fInfoLevelId
0x1801892d7  mov     rcx, rsi; lpFileName
0x1801892da  call    cs:__imp_GetFileAttributesExW
0x1801892e0  xor     r15d, r15d
0x1801892e3  test    eax, eax
0x1801892e5  jz      loc_1801894DD
0x1801892eb  mov     rcx, rsi; lpFileName
0x1801892ee  call    cs:__imp_DeleteFileW
0x1801892f4  test    eax, eax
0x1801892f6  jnz     loc_1801894DD
0x1801892fc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180189300  inc     rdi
0x180189303  cmp     [rsi+rdi*2], r15w
0x180189308  jnz     short loc_180189300
0x18018930a  lea     edi, ds:2[rdi*2]
0x180189311  test    edi, edi
0x180189313  jz      short loc_18018934C
0x180189315  mov     ecx, edi; Size
0x180189317  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018931c  mov     ecx, edi; Size
0x18018931e  mov     r15, rax
0x180189321  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180189326  mov     ecx, edi; Size
0x180189328  mov     r14, rax
0x18018932b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180189330  xor     edx, edx
0x180189332  mov     [rbp+3Fh+var_A8], edi
0x180189335  mov     r13, rax
0x180189338  mov     [rbp+3Fh+var_A4], edi
0x18018933b  lea     eax, [rdi+208h]
0x180189341  mov     [rbp+3Fh+NumberOfBytesWritten], edi
0x180189344  mov     ebx, edx
0x180189346  test    eax, eax
0x180189348  jz      short loc_180189376
0x18018934a  jmp     short loc_18018936A
0x18018934c  mov     ecx, [rbp+3Fh+NumberOfBytesWritten]
0x18018934f  lea     eax, [rdi+208h]
0x180189355  mov     [rbp+3Fh+var_A8], ecx
0x180189358  mov     r13, r15
0x18018935b  mov     ecx, [rbp+3Fh+NumberOfBytesWritten]
0x18018935e  mov     r14, r15
0x180189361  mov     [rbp+3Fh+var_A4], ecx
0x180189364  mov     ecx, [rbp+3Fh+NumberOfBytesWritten]
0x180189367  mov     [rbp+3Fh+NumberOfBytesWritten], ecx
0x18018936a  mov     ecx, eax; Size
0x18018936c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180189371  mov     rbx, rax
0x180189374  xor     edx, edx
0x180189376  mov     rsi, rdx
0x180189379  test    edi, edi
0x18018937b  jz      short loc_18018938B
0x18018937d  mov     ecx, edi; Size
0x18018937f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180189384  mov     rsi, rax
0x180189387  xor     edx, edx
0x180189389  jmp     short loc_18018938E
0x18018938b  mov     edi, [rbp+3Fh+NumberOfBytesWritten]
0x18018938e  test    r15, r15
0x180189391  jz      loc_18018958D
0x180189397  test    r14, r14
0x18018939a  jz      loc_18018958D
0x1801893a0  test    r13, r13
0x1801893a3  jz      loc_18018958D
0x1801893a9  test    rbx, rbx
0x1801893ac  jz      loc_18018958D
0x1801893b2  test    rsi, rsi
0x1801893b5  jz      loc_18018958D
0x1801893bb  mov     eax, [rbp+3Fh+var_A8]
0x1801893be  mov     r9, r14; Dir
0x1801893c1  mov     ecx, [rbp+3Fh+var_A4]
0x1801893c4  mov     r8d, [rbp+3Fh+NumberOfBytesWritten]
0x1801893c8  mov     [rsp+100h+ExtCount], rdx; ExtCount
0x1801893cd  mov     [rsp+100h+Ext], rdx; Ext
0x1801893d2  mov     rdx, r15; Drive
0x1801893d5  shr     rcx, 1
0x1801893d8  shr     rax, 1
0x1801893db  mov     [rsp+100h+FilenameCount], rax; FilenameCount
0x1801893e0  mov     [rsp+100h+Filename], r13; Filename
0x1801893e5  mov     [rsp+100h+DirCount], rcx; DirCount
0x1801893ea  mov     rcx, [rbp+3Fh+FullPath]; FullPath
0x1801893ee  shr     r8, 1; DriveCount
0x1801893f1  call    _wsplitpath_s
0x1801893f6  lea     rax, Filename
0x1801893fd  mov     edx, edi
0x1801893ff  mov     [rsp+100h+Filename], rax; Ext
0x180189404  mov     r9, r14; Dir
0x180189407  shr     rdx, 1; BufferCount
0x18018940a  mov     r8, r15; Drive
0x18018940d  mov     rcx, rsi; Buffer
0x180189410  mov     [rsp+100h+DirCount], rax; Filename
0x180189415  call    _wmakepath_s
0x18018941a  mov     r9, rbx; lpTempFileName
0x18018941d  lea     rdx, aSer_0; "SER"
0x180189424  xor     r8d, r8d; uUnique
0x180189427  mov     rcx, rsi; lpPathName
0x18018942a  call    cs:__imp_GetTempFileNameW
0x180189430  test    eax, eax
0x180189432  jnz     short loc_180189477
0x180189434  lea     rdx, aCreatecachefil_0; "CreateCacheFile: Unable to create Tmp N"...
0x18018943b  mov     rcx, [rbp+3Fh+var_98]; struct _iobuf *
0x18018943f  mov     r8d, 2; unsigned int
0x180189445  call    ?ErrorMessage@@YAXPEAU_iobuf@@PEADK@Z; ErrorMessage(_iobuf *,char *,ulong)
0x18018944a  mov     rcx, rsi; Block
0x18018944d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180189452  mov     rcx, rbx; Block
0x180189455  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18018945a  mov     rcx, r13; Block
0x18018945d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180189462  mov     rcx, r14; Block
0x180189465  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18018946a  mov     rcx, r15; Block
0x18018946d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180189472  jmp     loc_180189562
0x180189477  mov     rcx, [rbp+3Fh+FullPath]; lpExistingFileName
0x18018947b  mov     r8d, 1; dwFlags
0x180189481  mov     rdx, rbx; lpNewFileName
0x180189484  call    cs:__imp_MoveFileExW
0x18018948a  test    eax, eax
0x18018948c  jnz     short loc_180189497
0x18018948e  lea     rdx, aCreatecachefil_1; "CreateCacheFile: Unable to rename exist"...
0x180189495  jmp     short loc_18018943B
0x180189497  xor     edx, edx; lpNewFileName
0x180189499  mov     rcx, rbx; lpExistingFileName
0x18018949c  lea     r8d, [rdx+4]; dwFlags
0x1801894a0  call    cs:__imp_MoveFileExW
0x1801894a6  mov     rcx, rsi; Block
0x1801894a9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801894ae  mov     rcx, rbx; Block
0x1801894b1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801894b6  mov     rcx, r13; Block
0x1801894b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801894be  mov     rcx, r14; Block
0x1801894c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801894c6  mov     rcx, r15; Block
0x1801894c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801894ce  mov     rsi, [rbp+3Fh+FullPath]
0x1801894d2  xor     r15d, r15d
0x1801894d5  mov     rdi, [rbp+3Fh+var_98]
0x1801894d9  mov     r14d, dword ptr [rbp+3Fh+var_90+4]
0x1801894dd  mov     [rsp+100h+FilenameCount], r15; hTemplateFile
0x1801894e2  xor     r9d, r9d; lpSecurityAttributes
0x1801894e5  mov     dword ptr [rsp+100h+Filename], 8000080h; dwFlagsAndAttributes
0x1801894ed  xor     r8d, r8d; dwShareMode
0x1801894f0  mov     edx, 40000000h; dwDesiredAccess
0x1801894f5  mov     dword ptr [rsp+100h+DirCount], 2; dwCreationDisposition
0x1801894fd  mov     rcx, rsi; lpFileName
0x180189500  call    cs:__imp_CreateFileW
0x180189506  mov     rbx, rax
0x180189509  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18018950d  jz      short loc_18018954D
0x18018950f  lea     r9, [rbp+3Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180189513  mov     [rbp+3Fh+NumberOfBytesWritten], r15d
0x180189517  mov     r8d, r14d; nNumberOfBytesToWrite
0x18018951a  mov     [rsp+100h+DirCount], r15; lpOverlapped
0x18018951f  mov     rdx, r12; lpBuffer
0x180189522  mov     rcx, rax; hFile
0x180189525  call    cs:__imp_WriteFile
0x18018952b  test    eax, eax
0x18018952d  jz      short loc_18018953A
0x18018952f  mov     esi, 1
0x180189534  cmp     r14d, [rbp+3Fh+NumberOfBytesWritten]
0x180189538  jz      short loc_18018953D
0x18018953a  mov     esi, r15d
0x18018953d  mov     rcx, rbx; hObject
0x180189540  mov     [rbp+3Fh+var_AC], esi
0x180189543  call    cs:__imp_CloseHandle
0x180189549  test    esi, esi
0x18018954b  jnz     short loc_180189562
0x18018954d  lea     rdx, aCreatecachefil_3; "CreateCacheFile: Unable to write cache "...
0x180189554  mov     r8d, 2; unsigned int
0x18018955a  mov     rcx, rdi; struct _iobuf *
0x18018955d  call    ?ErrorMessage@@YAXPEAU_iobuf@@PEADK@Z; ErrorMessage(_iobuf *,char *,ulong)
0x180189562  mov     rcx, r12; Block
0x180189565  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18018956a  mov     eax, [rbp+3Fh+var_AC]
0x18018956d  mov     rcx, [rbp+3Fh+var_48]
0x180189571  xor     rcx, rsp; StackCookie
0x180189574  call    __security_check_cookie
0x180189579  add     rsp, 0C8h
0x180189580  pop     r15
0x180189582  pop     r14
0x180189584  pop     r13
0x180189586  pop     r12
0x180189588  pop     rdi
0x180189589  pop     rsi
0x18018958a  pop     rbx
0x18018958b  pop     rbp
0x18018958c  retn
0x18018958d  mov     rax, [rbp+3Fh+var_78]
0x180189591  mov     rcx, rsi; Block
0x180189594  mov     [rax], edx
0x180189596  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18018959b  mov     rcx, rbx; Block
0x18018959e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801895a3  mov     rcx, r13; Block
0x1801895a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801895ab  mov     rcx, r14; Block
0x1801895ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801895b3  mov     rcx, r15; Block
0x1801895b6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801895bb  jmp     loc_180189247
```
