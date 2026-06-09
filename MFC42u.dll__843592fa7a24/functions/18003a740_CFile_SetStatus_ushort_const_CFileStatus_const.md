# CFile::SetStatus(ushort const *,CFileStatus const &)

- ea: `0x18003a740`
- end: `0x18003a8de`
- name: `?SetStatus@CFile@@SAXPEBGAEBUCFileStatus@@@Z`
- size: `414`
- prototype: `void __fastcall(LPCWSTR lpFileName, const struct CFileStatus *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18003a0e0`
- `0x18003a120`
- `0x18003a740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a77d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a7a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a86c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a77d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a7a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a86c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8be`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003a833`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003a833`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a770`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a770`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003a79d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003a8b4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003a79d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003a8b4`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18003a862`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18003a862`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a877`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a88a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a877`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a88a`

## pseudocode

```c
void __fastcall CFile::SetStatus(LPCWSTR lpFileName, const struct CFileStatus *this)
{
  DWORD FileAttributesW; // esi
  DWORD LastError; // eax
  DWORD v6; // edx
  DWORD v7; // eax
  struct _FILETIME *v8; // rbx
  struct _FILETIME *p_FileTime; // r15
  HANDLE FileW; // rbp
  DWORD v11; // eax
  DWORD v12; // ebx
  DWORD v13; // ecx
  DWORD v14; // edx
  DWORD v15; // eax
  struct _FILETIME FileTime; // [rsp+78h] [rbp+10h] BYREF
  struct _FILETIME v17; // [rsp+80h] [rbp+18h] BYREF
  FILETIME LastWriteTime; // [rsp+88h] [rbp+20h] BYREF

  v17 = 0;
  FileTime = 0;
  LastWriteTime = 0;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    CFileException::ThrowOsError(LastError, 0);
  }
  v6 = *((unsigned __int8 *)this + 28);
  if ( v6 != FileAttributesW && (FileAttributesW & 1) != 0 && !SetFileAttributesW(lpFileName, v6) )
  {
    v7 = GetLastError();
    CFileException::ThrowOsError(v7, 0);
  }
  if ( *((_QWORD *)this + 1) )
  {
    v8 = 0;
    p_FileTime = 0;
    AfxTimeToFileTime((const struct CFileStatus *)((char *)this + 8), &LastWriteTime);
    if ( *((_QWORD *)this + 2) )
    {
      AfxTimeToFileTime((const struct CFileStatus *)((char *)this + 16), &FileTime);
      p_FileTime = &FileTime;
    }
    if ( *(_QWORD *)this )
    {
      AfxTimeToFileTime(this, &v17);
      v8 = &v17;
    }
    FileW = CreateFileW(lpFileName, 0xC0000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      v11 = GetLastError();
      CFileException::ThrowOsError(v11, 0);
    }
    if ( !SetFileTime(FileW, v8, p_FileTime, &LastWriteTime) )
    {
      v12 = GetLastError();
      CloseHandle(FileW);
      v13 = v12;
LABEL_19:
      CFileException::ThrowOsError(v13, 0);
      goto LABEL_20;
    }
    if ( FileW != (HANDLE)-1LL && !CloseHandle(FileW) )
    {
      v13 = GetLastError();
      goto LABEL_19;
    }
  }
LABEL_20:
  v14 = *((unsigned __int8 *)this + 28);
  if ( v14 != FileAttributesW && (FileAttributesW & 1) == 0 && !SetFileAttributesW(lpFileName, v14) )
  {
    v15 = GetLastError();
    CFileException::ThrowOsError(v15, 0);
  }
}

```

## disassembly

```asm
0x18003a740  mov     rax, rsp
0x18003a743  mov     [rax+8], rbx
0x18003a747  push    rbp
0x18003a748  push    rsi
0x18003a749  push    rdi
0x18003a74a  push    r14
0x18003a74c  push    r15
0x18003a74e  sub     rsp, 40h
0x18003a752  mov     rdi, rdx
0x18003a755  mov     qword ptr [rax+18h], 0
0x18003a75d  mov     r14, rcx
0x18003a760  mov     qword ptr [rax+10h], 0
0x18003a768  mov     qword ptr [rax+20h], 0
0x18003a770  call    cs:__imp_GetFileAttributesW
0x18003a776  mov     esi, eax
0x18003a778  cmp     eax, 0FFFFFFFFh
0x18003a77b  jnz     short loc_18003A78C
0x18003a77d  call    cs:__imp_GetLastError
0x18003a783  mov     ecx, eax; int
0x18003a785  xor     edx, edx; unsigned __int16 *
0x18003a787  call    ?ThrowOsError@CFileException@@SAXJPEBG@Z; CFileException::ThrowOsError(long,ushort const *)
0x18003a78c  movzx   edx, byte ptr [rdi+1Ch]; dwFileAttributes
0x18003a790  cmp     edx, esi
0x18003a792  jz      short loc_18003A7B6
0x18003a794  test    sil, 1
0x18003a798  jz      short loc_18003A7B6
0x18003a79a  mov     rcx, r14; lpFileName
0x18003a79d  call    cs:__imp_SetFileAttributesW
0x18003a7a3  test    eax, eax
0x18003a7a5  jnz     short loc_18003A7B6
0x18003a7a7  call    cs:__imp_GetLastError
0x18003a7ad  mov     ecx, eax; int
0x18003a7af  xor     edx, edx; unsigned __int16 *
0x18003a7b1  call    ?ThrowOsError@CFileException@@SAXJPEBG@Z; CFileException::ThrowOsError(long,ushort const *)
0x18003a7b6  lea     rcx, [rdi+8]; this
0x18003a7ba  cmp     qword ptr [rcx], 0
0x18003a7be  jz      loc_18003A8A3
0x18003a7c4  lea     rdx, [rsp+68h+LastWriteTime]; lpFileTime
0x18003a7cc  xor     ebx, ebx
0x18003a7ce  xor     r15d, r15d
0x18003a7d1  call    ?AfxTimeToFileTime@@YAXAEBVCTime@@PEAU_FILETIME@@@Z; AfxTimeToFileTime(CTime const &,_FILETIME *)
0x18003a7d6  lea     rcx, [rdi+10h]; this
0x18003a7da  cmp     [rcx], rbx
0x18003a7dd  jz      short loc_18003A7EE
0x18003a7df  lea     rdx, [rsp+68h+FileTime]; lpFileTime
0x18003a7e4  call    ?AfxTimeToFileTime@@YAXAEBVCTime@@PEAU_FILETIME@@@Z; AfxTimeToFileTime(CTime const &,_FILETIME *)
0x18003a7e9  lea     r15, [rsp+68h+FileTime]
0x18003a7ee  cmp     [rdi], rbx
0x18003a7f1  jz      short loc_18003A80B
0x18003a7f3  lea     rdx, [rsp+68h+arg_10]; lpFileTime
0x18003a7fb  mov     rcx, rdi; this
0x18003a7fe  call    ?AfxTimeToFileTime@@YAXAEBVCTime@@PEAU_FILETIME@@@Z; AfxTimeToFileTime(CTime const &,_FILETIME *)
0x18003a803  lea     rbx, [rsp+68h+arg_10]
0x18003a80b  xor     r9d, r9d; lpSecurityAttributes
0x18003a80e  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18003a817  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003a81f  mov     edx, 0C0000000h; dwDesiredAccess
0x18003a824  mov     rcx, r14; lpFileName
0x18003a827  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18003a82f  lea     r8d, [r9+1]; dwShareMode
0x18003a833  call    cs:__imp_CreateFileW
0x18003a839  mov     rbp, rax
0x18003a83c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003a840  jnz     short loc_18003A851
0x18003a842  call    cs:__imp_GetLastError
0x18003a848  mov     ecx, eax; int
0x18003a84a  xor     edx, edx; unsigned __int16 *
0x18003a84c  call    ?ThrowOsError@CFileException@@SAXJPEBG@Z; CFileException::ThrowOsError(long,ushort const *)
0x18003a851  lea     r9, [rsp+68h+LastWriteTime]; lpLastWriteTime
0x18003a859  mov     r8, r15; lpLastAccessTime
0x18003a85c  mov     rdx, rbx; lpCreationTime
0x18003a85f  mov     rcx, rbp; hFile
0x18003a862  call    cs:__imp_SetFileTime
0x18003a868  test    eax, eax
0x18003a86a  jnz     short loc_18003A881
0x18003a86c  call    cs:__imp_GetLastError
0x18003a872  mov     rcx, rbp; hObject
0x18003a875  mov     ebx, eax
0x18003a877  call    cs:__imp_CloseHandle
0x18003a87d  mov     ecx, ebx
0x18003a87f  jmp     short loc_18003A89C
0x18003a881  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18003a885  jz      short loc_18003A8A3
0x18003a887  mov     rcx, rbp; hObject
0x18003a88a  call    cs:__imp_CloseHandle
0x18003a890  test    eax, eax
0x18003a892  jnz     short loc_18003A8A3
0x18003a894  call    cs:__imp_GetLastError
0x18003a89a  mov     ecx, eax; int
0x18003a89c  xor     edx, edx; unsigned __int16 *
0x18003a89e  call    ?ThrowOsError@CFileException@@SAXJPEBG@Z; CFileException::ThrowOsError(long,ushort const *)
0x18003a8a3  movzx   edx, byte ptr [rdi+1Ch]; dwFileAttributes
0x18003a8a7  cmp     edx, esi
0x18003a8a9  jz      short loc_18003A8CD
0x18003a8ab  test    sil, 1
0x18003a8af  jnz     short loc_18003A8CD
0x18003a8b1  mov     rcx, r14; lpFileName
0x18003a8b4  call    cs:__imp_SetFileAttributesW
0x18003a8ba  test    eax, eax
0x18003a8bc  jnz     short loc_18003A8CD
0x18003a8be  call    cs:__imp_GetLastError
0x18003a8c4  mov     ecx, eax; int
0x18003a8c6  xor     edx, edx; unsigned __int16 *
0x18003a8c8  call    ?ThrowOsError@CFileException@@SAXJPEBG@Z; CFileException::ThrowOsError(long,ushort const *)
0x18003a8cd  mov     rbx, [rsp+68h+arg_0]
0x18003a8d2  add     rsp, 40h
0x18003a8d6  pop     r15
0x18003a8d8  pop     r14
0x18003a8da  pop     rdi
0x18003a8db  pop     rsi
0x18003a8dc  pop     rbp
0x18003a8dd  retn
```
