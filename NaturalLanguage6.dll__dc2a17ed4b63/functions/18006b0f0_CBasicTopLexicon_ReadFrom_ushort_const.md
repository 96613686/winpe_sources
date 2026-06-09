# CBasicTopLexicon::ReadFrom(ushort const *)

- ea: `0x18006b0f0`
- end: `0x18006b1ce`
- name: `?ReadFrom@CBasicTopLexicon@@UEAA_NPEBG@Z`
- size: `222`
- prototype: `bool __fastcall(CBasicTopLexicon *__hidden this, LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18005b074`
- `0x18006a768`
- `0x18006b0f0`
- `0x18006b7e4`
- `0x18006b850`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006b141`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006b141`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18006b175`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18006b175`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18006b19d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18006b19d`

## pseudocode

```c
bool __fastcall CBasicTopLexicon::ReadFrom(CBasicTopLexicon *this, LPCWSTR lpFileName)
{
  char *FileW; // rax
  HANDLE FileMappingW; // rax
  LPVOID v6; // rax

  TString<CArray<unsigned short,CArrayAllocator_malloc>>::operator=((char *)this + 72);
  CBasicTopLexicon::ReleaseHeaders(this);
  CBasicTopLexicon::ReleaseHandles(this);
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  *((_QWORD *)this + 25) = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
    *((_QWORD *)this + 26) = FileMappingW;
    if ( FileMappingW )
    {
      v6 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      *((_QWORD *)this + 24) = v6;
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
0x18006b0f0  mov     [rsp+arg_0], rbx
0x18006b0f5  push    rdi
0x18006b0f6  sub     rsp, 40h
0x18006b0fa  mov     rdi, rcx
0x18006b0fd  mov     rbx, rdx
0x18006b100  add     rcx, 48h ; 'H'
0x18006b104  call    ??4?$TString@V?$CArray@GVCArrayAllocator_malloc@@@@@@QEAAAEBV0@PEBG@Z; TString<CArray<ushort,CArrayAllocator_malloc>>::operator=(ushort const *)
0x18006b109  mov     rcx, rdi; this
0x18006b10c  call    ?ReleaseHeaders@CBasicTopLexicon@@IEAAXXZ; CBasicTopLexicon::ReleaseHeaders(void)
0x18006b111  mov     rcx, rdi; this
0x18006b114  call    ?ReleaseHandles@CBasicTopLexicon@@IEAAXXZ; CBasicTopLexicon::ReleaseHandles(void)
0x18006b119  xor     r9d, r9d; lpSecurityAttributes
0x18006b11c  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18006b125  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006b12d  mov     edx, 80000000h; dwDesiredAccess
0x18006b132  mov     rcx, rbx; lpFileName
0x18006b135  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18006b13d  lea     r8d, [r9+1]; dwShareMode
0x18006b141  call    cs:__imp_CreateFileW
0x18006b147  mov     [rdi+0C8h], rax
0x18006b14e  lea     rcx, [rax-1]
0x18006b152  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18006b156  ja      short loc_18006B1C1
0x18006b158  xor     r9d, r9d; dwMaximumSizeHigh
0x18006b15b  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x18006b164  xor     edx, edx; lpFileMappingAttributes
0x18006b166  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18006b16e  mov     rcx, rax; hFile
0x18006b171  lea     r8d, [r9+2]; flProtect
0x18006b175  call    cs:__imp_CreateFileMappingW
0x18006b17b  mov     [rdi+0D0h], rax
0x18006b182  test    rax, rax
0x18006b185  jz      short loc_18006B1B9
0x18006b187  xor     r9d, r9d; dwFileOffsetLow
0x18006b18a  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18006b193  xor     r8d, r8d; dwFileOffsetHigh
0x18006b196  mov     rcx, rax; hFileMappingObject
0x18006b199  lea     edx, [r9+4]; dwDesiredAccess
0x18006b19d  call    cs:__imp_MapViewOfFile
0x18006b1a3  mov     [rdi+0C0h], rax
0x18006b1aa  test    rax, rax
0x18006b1ad  jz      short loc_18006B1B9
0x18006b1af  mov     rcx, rdi; this
0x18006b1b2  call    ?EstablishHeaders@CBasicTopLexicon@@IEAA_NXZ; CBasicTopLexicon::EstablishHeaders(void)
0x18006b1b7  jmp     short loc_18006B1C3
0x18006b1b9  mov     rcx, rdi; this
0x18006b1bc  call    ?ReleaseHandles@CBasicTopLexicon@@IEAAXXZ; CBasicTopLexicon::ReleaseHandles(void)
0x18006b1c1  xor     al, al
0x18006b1c3  mov     rbx, [rsp+48h+arg_0]
0x18006b1c8  add     rsp, 40h
0x18006b1cc  pop     rdi
0x18006b1cd  retn
```
