# CBasicTopLexicon::ReadFrom(ushort const *)

- ea: `0x18009c320`
- end: `0x18009c3fe`
- name: `?ReadFrom@CBasicTopLexicon@@UEAA_NPEBG@Z`
- size: `222`
- prototype: `bool __fastcall(CBasicTopLexicon *__hidden this, LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180005b20`
- `0x180058fdc`
- `0x18009c320`
- `0x18009c51c`
- `0x18009c588`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18009c3cd`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18009c3cd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18009c3a5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18009c3a5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009c371`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009c371`

## pseudocode

```c
bool __fastcall CBasicTopLexicon::ReadFrom(CBasicTopLexicon *this, LPCWSTR lpFileName)
{
  char *FileW; // rax
  HANDLE FileMappingW; // rax
  LPVOID v6; // rax

  TString<CArray<unsigned short,CArrayAllocator_malloc>>::operator=((char *)this + 24);
  CBasicTopLexicon::ReleaseHeaders(this);
  CBasicTopLexicon::ReleaseHandles(this);
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  *((_QWORD *)this + 19) = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
    *((_QWORD *)this + 20) = FileMappingW;
    if ( FileMappingW )
    {
      v6 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      *((_QWORD *)this + 18) = v6;
      if ( v6 )
        return CBasicTopLexicon::EstablishHeaders(this);
    }
    CBasicTopLexicon::ReleaseHandles(this);
  }
  return 0;
}

```

## disassembly

```asm
0x18009c320  mov     [rsp+arg_0], rbx
0x18009c325  push    rdi
0x18009c326  sub     rsp, 40h
0x18009c32a  mov     rdi, rcx
0x18009c32d  mov     rbx, rdx
0x18009c330  add     rcx, 18h
0x18009c334  call    ??4?$TString@V?$CArray@GVCArrayAllocator_malloc@@@@@@QEAAAEBV0@PEBG@Z; TString<CArray<ushort,CArrayAllocator_malloc>>::operator=(ushort const *)
0x18009c339  mov     rcx, rdi; this
0x18009c33c  call    ?ReleaseHeaders@CBasicTopLexicon@@IEAAXXZ; CBasicTopLexicon::ReleaseHeaders(void)
0x18009c341  mov     rcx, rdi; this
0x18009c344  call    ?ReleaseHandles@CBasicTopLexicon@@IEAAXXZ; CBasicTopLexicon::ReleaseHandles(void)
0x18009c349  xor     r9d, r9d; lpSecurityAttributes
0x18009c34c  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18009c355  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009c35d  mov     edx, 80000000h; dwDesiredAccess
0x18009c362  mov     rcx, rbx; lpFileName
0x18009c365  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18009c36d  lea     r8d, [r9+1]; dwShareMode
0x18009c371  call    cs:__imp_CreateFileW
0x18009c377  mov     [rdi+98h], rax
0x18009c37e  lea     rcx, [rax-1]
0x18009c382  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18009c386  ja      short loc_18009C3F1
0x18009c388  xor     r9d, r9d; dwMaximumSizeHigh
0x18009c38b  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x18009c394  xor     edx, edx; lpFileMappingAttributes
0x18009c396  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18009c39e  mov     rcx, rax; hFile
0x18009c3a1  lea     r8d, [r9+2]; flProtect
0x18009c3a5  call    cs:__imp_CreateFileMappingW
0x18009c3ab  mov     [rdi+0A0h], rax
0x18009c3b2  test    rax, rax
0x18009c3b5  jz      short loc_18009C3E9
0x18009c3b7  xor     r9d, r9d; dwFileOffsetLow
0x18009c3ba  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18009c3c3  xor     r8d, r8d; dwFileOffsetHigh
0x18009c3c6  mov     rcx, rax; hFileMappingObject
0x18009c3c9  lea     edx, [r9+4]; dwDesiredAccess
0x18009c3cd  call    cs:__imp_MapViewOfFile
0x18009c3d3  mov     [rdi+90h], rax
0x18009c3da  test    rax, rax
0x18009c3dd  jz      short loc_18009C3E9
0x18009c3df  mov     rcx, rdi; this
0x18009c3e2  call    ?EstablishHeaders@CBasicTopLexicon@@IEAA_NXZ; CBasicTopLexicon::EstablishHeaders(void)
0x18009c3e7  jmp     short loc_18009C3F3
0x18009c3e9  mov     rcx, rdi; this
0x18009c3ec  call    ?ReleaseHandles@CBasicTopLexicon@@IEAAXXZ; CBasicTopLexicon::ReleaseHandles(void)
0x18009c3f1  xor     al, al
0x18009c3f3  mov     rbx, [rsp+48h+arg_0]
0x18009c3f8  add     rsp, 40h
0x18009c3fc  pop     rdi
0x18009c3fd  retn
```
