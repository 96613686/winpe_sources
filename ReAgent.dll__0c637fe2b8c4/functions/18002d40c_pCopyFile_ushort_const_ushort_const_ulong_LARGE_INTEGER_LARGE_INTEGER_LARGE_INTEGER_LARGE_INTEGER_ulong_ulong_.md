# pCopyFile(ushort const *,ushort const *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int,int)

- ea: `0x18002d40c`
- end: `0x18002d74b`
- name: `?pCopyFile@@YAJPEBG0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z22HH@Z`
- size: `831`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR, unsigned int (*)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *), void *, void *, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18002dd30`

## callees

- `0x180001f94`
- `0x180001fa0`
- `0x1800059fc`
- `0x18002d40c`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002d48c`
- `KERNEL32!GetLastError` at `0x18002d4a4`
- `KERNEL32!GetLastError` at `0x18002d4ee`
- `KERNEL32!GetLastError` at `0x18002d506`
- `KERNEL32!GetLastError` at `0x18002d575`
- `KERNEL32!GetLastError` at `0x18002d58d`
- `KERNEL32!GetLastError` at `0x18002d5c8`
- `KERNEL32!GetLastError` at `0x18002d5e0`
- `KERNEL32!GetLastError` at `0x18002d671`
- `KERNEL32!GetLastError` at `0x18002d6d9`
- `KERNEL32!GetLastError` at `0x18002d6eb`
- `KERNEL32!GetLastError` at `0x18002d48c`
- `KERNEL32!GetLastError` at `0x18002d4a4`
- `KERNEL32!GetLastError` at `0x18002d4ee`
- `KERNEL32!GetLastError` at `0x18002d506`
- `KERNEL32!GetLastError` at `0x18002d575`
- `KERNEL32!GetLastError` at `0x18002d58d`
- `KERNEL32!GetLastError` at `0x18002d5c8`
- `KERNEL32!GetLastError` at `0x18002d5e0`
- `KERNEL32!GetLastError` at `0x18002d671`
- `KERNEL32!GetLastError` at `0x18002d6d9`
- `KERNEL32!GetLastError` at `0x18002d6eb`
- `KERNEL32!GetFileSizeEx` at `0x18002d4e4`
- `KERNEL32!GetFileSizeEx` at `0x18002d4e4`
- `KERNEL32!WriteFile` at `0x18002d656`
- `KERNEL32!WriteFile` at `0x18002d656`
- `KERNEL32!ReadFile` at `0x18002d636`
- `KERNEL32!ReadFile` at `0x18002d636`
- `KERNEL32!CreateFileW` at `0x18002d47d`
- `KERNEL32!CreateFileW` at `0x18002d566`
- `KERNEL32!CreateFileW` at `0x18002d47d`
- `KERNEL32!CreateFileW` at `0x18002d566`
- `KERNEL32!CloseHandle` at `0x18002d6a9`
- `KERNEL32!CloseHandle` at `0x18002d6b2`
- `KERNEL32!CloseHandle` at `0x18002d6a9`
- `KERNEL32!CloseHandle` at `0x18002d6b2`
- `KERNEL32!GetFileAttributesW` at `0x18002d6bf`
- `KERNEL32!GetFileAttributesW` at `0x18002d6bf`
- `KERNEL32!SetFileAttributesW` at `0x18002d6cf`
- `KERNEL32!SetFileAttributesW` at `0x18002d6cf`

## string_xrefs

- `0x18002d711`: `%hs: Input Path is NULL`
- `0x18002d4c3`: `pCopyFile`
- `0x18002d528`: `pCopyFile`
- `0x18002d605`: `pCopyFile`
- `0x18002d689`: `pCopyFile`
- `0x18002d6fb`: `pCopyFile`
- `0x18002d4cc`: `%hs: Failed to open source file %s. Error: 0x%08X`
- `0x18002d5a8`: `%hs: Failed to open destination file %s. Error: 0x%08X`
- `0x18002d60c`: `%hs: Failed to allocate buffer for copy operation. Error: 0x%08X`
- `0x18002d690`: `%hs: Failed to write file. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall pCopyFile(
        LPCWSTR lpFileName,
        LPCWSTR a2,
        unsigned int (*a3)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *),
        void *a4)
{
  HANDLE FileW; // rax
  void *v7; // r13
  signed int LastError; // eax
  bool v9; // sf
  signed int v10; // eax
  signed int v11; // ebx
  signed int v12; // eax
  bool v13; // sf
  signed int v14; // eax
  LPCWSTR v15; // r9
  const wchar_t *v16; // rdx
  HANDLE v17; // r12
  signed int v18; // eax
  bool v19; // sf
  signed int v20; // eax
  void *v21; // rsi
  signed int v22; // eax
  bool v23; // sf
  signed int v24; // eax
  signed int v25; // eax
  DWORD FileAttributesW; // eax
  DWORD v27; // eax
  LPCWSTR v28; // r9
  const wchar_t *v29; // rdx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-40h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-20h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-18h] BYREF
  int v34; // [rsp+4Ch] [rbp-14h]
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-10h] BYREF

  if ( lpFileName && a2 )
  {
    FileSize.QuadPart = 0;
    v34 = 0;
    NumberOfBytesRead = 0;
    NumberOfBytesWritten = 0;
    FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x2000000u, 0);
    v7 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v9 = LastError < 0;
      if ( LastError > 0 )
        v9 = 1;
      if ( v9 )
      {
        v10 = GetLastError();
        v11 = v10;
        if ( v10 > 0 )
          v11 = (unsigned __int16)v10 | 0x80070000;
      }
      else
      {
        v11 = -2147467259;
      }
      dwCreationDisposition[0] = v11;
      UnattendLogW(
        0,
        L"%hs: Failed to open source file %s. Error: 0x%08X",
        "pCopyFile",
        lpFileName,
        *(_QWORD *)dwCreationDisposition);
LABEL_51:
      if ( v11 >= 0 )
      {
        FileAttributesW = GetFileAttributesW(lpFileName);
        if ( FileAttributesW == -1 )
        {
          v27 = GetLastError();
          v28 = lpFileName;
          v29 = L"%hs: Failed to get attributes for %s. Error: 0x%08X";
          goto LABEL_56;
        }
        if ( !SetFileAttributesW(a2, FileAttributesW) )
        {
          v27 = GetLastError();
          v28 = a2;
          v29 = L"%hs: Failed to set attributes for %s. Error: 0x%08X";
LABEL_56:
          dwCreationDisposition[0] = v27;
          UnattendLogW(0, v29, "pCopyFile", v28, *(_QWORD *)dwCreationDisposition);
        }
      }
      return (unsigned int)v11;
    }
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      v17 = CreateFileW(a2, 0x40000000u, 0, 0, 1u, 0xA000000u, 0);
      if ( v17 != (HANDLE)-1LL )
      {
        v21 = operator new[](0x400000u);
        if ( v21 )
        {
          v11 = 0;
          while ( ReadFile(v7, v21, 0x400000u, &NumberOfBytesRead, 0) )
          {
            NumberOfBytesWritten = 0;
            if ( !WriteFile(v17, v21, NumberOfBytesRead, &NumberOfBytesWritten, 0)
              || NumberOfBytesWritten != NumberOfBytesRead )
            {
              v25 = GetLastError();
              v11 = v25;
              if ( v25 > 0 )
                v11 = (unsigned __int16)v25 | 0x80070000;
              UnattendLogW(0, L"%hs: Failed to write file. Error: 0x%08X", "pCopyFile", (unsigned int)v11);
              break;
            }
            if ( NumberOfBytesRead < 0x400000 )
              break;
          }
          operator delete(v21);
        }
        else
        {
          v22 = GetLastError();
          v23 = v22 < 0;
          if ( v22 > 0 )
            v23 = 1;
          if ( v23 )
          {
            v24 = GetLastError();
            v11 = v24;
            if ( v24 > 0 )
              v11 = (unsigned __int16)v24 | 0x80070000;
            if ( v11 >= 0 )
              v11 = -2147024888;
          }
          else
          {
            v11 = -2147467259;
          }
          UnattendLogW(
            0,
            L"%hs: Failed to allocate buffer for copy operation. Error: 0x%08X",
            "pCopyFile",
            (unsigned int)v11);
        }
        CloseHandle(v17);
        goto LABEL_50;
      }
      v18 = GetLastError();
      v19 = v18 < 0;
      if ( v18 > 0 )
        v19 = 1;
      if ( v19 )
      {
        v20 = GetLastError();
        v11 = v20;
        if ( v20 > 0 )
          v11 = (unsigned __int16)v20 | 0x80070000;
      }
      else
      {
        v11 = -2147467259;
      }
      v15 = a2;
      v16 = L"%hs: Failed to open destination file %s. Error: 0x%08X";
    }
    else
    {
      v12 = GetLastError();
      v13 = v12 < 0;
      if ( v12 > 0 )
        v13 = 1;
      if ( v13 )
      {
        v14 = GetLastError();
        v11 = v14;
        if ( v14 > 0 )
          v11 = (unsigned __int16)v14 | 0x80070000;
      }
      else
      {
        v11 = -2147467259;
      }
      v15 = lpFileName;
      v16 = L"%hs: Failed to get the size for source file %s. Error: 0x%08X";
    }
    dwCreationDisposition[0] = v11;
    UnattendLogW(0, v16, "pCopyFile", v15, *(_QWORD *)dwCreationDisposition);
LABEL_50:
    CloseHandle(v7);
    goto LABEL_51;
  }
  UnattendLogW(1, L"%hs: Input Path is NULL", a3, a4);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002d40c  mov     [rsp-38h+arg_10], rbx
0x18002d411  push    rbp
0x18002d412  push    rsi
0x18002d413  push    rdi
0x18002d414  push    r12
0x18002d416  push    r13
0x18002d418  push    r14
0x18002d41a  push    r15
0x18002d41c  mov     rbp, rsp
0x18002d41f  sub     rsp, 60h
0x18002d423  mov     rax, cs:__security_cookie
0x18002d42a  xor     rax, rsp
0x18002d42d  mov     [rbp+var_8], rax
0x18002d431  mov     r15, rdx
0x18002d434  mov     r14, rcx
0x18002d437  test    rcx, rcx
0x18002d43a  jz      loc_18002D711
0x18002d440  test    rdx, rdx
0x18002d443  jz      loc_18002D711
0x18002d449  xor     eax, eax
0x18002d44b  mov     qword ptr [rbp+FileSize], 0
0x18002d453  mov     [rsp+60h+hTemplateFile], rax; hTemplateFile
0x18002d458  xor     r9d, r9d; lpSecurityAttributes
0x18002d45b  mov     [rsp+60h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002d463  mov     edx, 80000000h; dwDesiredAccess
0x18002d468  mov     [rbp+var_14], eax
0x18002d46b  lea     r8d, [rax+1]; dwShareMode
0x18002d46f  mov     [rbp+NumberOfBytesRead], eax
0x18002d472  mov     [rbp+NumberOfBytesWritten], eax
0x18002d475  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x18002d47d  call    cs:__imp_CreateFileW
0x18002d483  mov     r13, rax
0x18002d486  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d48a  jnz     short loc_18002D4DD
0x18002d48c  call    cs:__imp_GetLastError
0x18002d492  mov     edi, 80070000h
0x18002d497  test    eax, eax
0x18002d499  jle     short loc_18002D4A2
0x18002d49b  movzx   eax, ax
0x18002d49e  or      eax, edi
0x18002d4a0  test    eax, eax
0x18002d4a2  jns     short loc_18002D4B7
0x18002d4a4  call    cs:__imp_GetLastError
0x18002d4aa  mov     ebx, eax
0x18002d4ac  test    eax, eax
0x18002d4ae  jle     short loc_18002D4BC
0x18002d4b0  movzx   ebx, ax
0x18002d4b3  or      ebx, edi
0x18002d4b5  jmp     short loc_18002D4BC
0x18002d4b7  mov     ebx, 80004005h
0x18002d4bc  mov     r9, r14
0x18002d4bf  mov     [rsp+60h+dwCreationDisposition], ebx
0x18002d4c3  lea     r8, aPcopyfile; "pCopyFile"
0x18002d4ca  xor     ecx, ecx
0x18002d4cc  lea     rdx, aHsFailedToOpen; "%hs: Failed to open source file %s. Err"...
0x18002d4d3  call    UnattendLogW
0x18002d4d8  jmp     loc_18002D6B8
0x18002d4dd  lea     rdx, [rbp+FileSize]; lpFileSize
0x18002d4e1  mov     rcx, r13; hFile
0x18002d4e4  call    cs:__imp_GetFileSizeEx
0x18002d4ea  test    eax, eax
0x18002d4ec  jnz     short loc_18002D53F
0x18002d4ee  call    cs:__imp_GetLastError
0x18002d4f4  mov     edi, 80070000h
0x18002d4f9  test    eax, eax
0x18002d4fb  jle     short loc_18002D504
0x18002d4fd  movzx   eax, ax
0x18002d500  or      eax, edi
0x18002d502  test    eax, eax
0x18002d504  jns     short loc_18002D519
0x18002d506  call    cs:__imp_GetLastError
0x18002d50c  mov     ebx, eax
0x18002d50e  test    eax, eax
0x18002d510  jle     short loc_18002D51E
0x18002d512  movzx   ebx, ax
0x18002d515  or      ebx, edi
0x18002d517  jmp     short loc_18002D51E
0x18002d519  mov     ebx, 80004005h
0x18002d51e  mov     r9, r14
0x18002d521  lea     rdx, aHsFailedToGetT; "%hs: Failed to get the size for source "...
0x18002d528  lea     r8, aPcopyfile; "pCopyFile"
0x18002d52f  mov     [rsp+60h+dwCreationDisposition], ebx
0x18002d533  xor     ecx, ecx
0x18002d535  call    UnattendLogW
0x18002d53a  jmp     loc_18002D6AF
0x18002d53f  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x18002d548  xor     r9d, r9d; lpSecurityAttributes
0x18002d54b  mov     [rsp+60h+dwFlagsAndAttributes], 0A000000h; dwFlagsAndAttributes
0x18002d553  xor     r8d, r8d; dwShareMode
0x18002d556  mov     edx, 40000000h; dwDesiredAccess
0x18002d55b  mov     [rsp+60h+dwCreationDisposition], 1; dwCreationDisposition
0x18002d563  mov     rcx, r15; lpFileName
0x18002d566  call    cs:__imp_CreateFileW
0x18002d56c  mov     r12, rax
0x18002d56f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d573  jnz     short loc_18002D5B4
0x18002d575  call    cs:__imp_GetLastError
0x18002d57b  mov     edi, 80070000h
0x18002d580  test    eax, eax
0x18002d582  jle     short loc_18002D58B
0x18002d584  movzx   eax, ax
0x18002d587  or      eax, edi
0x18002d589  test    eax, eax
0x18002d58b  jns     short loc_18002D5A0
0x18002d58d  call    cs:__imp_GetLastError
0x18002d593  mov     ebx, eax
0x18002d595  test    eax, eax
0x18002d597  jle     short loc_18002D5A5
0x18002d599  movzx   ebx, ax
0x18002d59c  or      ebx, edi
0x18002d59e  jmp     short loc_18002D5A5
0x18002d5a0  mov     ebx, 80004005h
0x18002d5a5  mov     r9, r15
0x18002d5a8  lea     rdx, aHsFailedToOpen_0; "%hs: Failed to open destination file %s"...
0x18002d5af  jmp     loc_18002D528
0x18002d5b4  mov     ecx, 400000h; unsigned __int64
0x18002d5b9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d5be  xor     edi, edi
0x18002d5c0  mov     rsi, rax
0x18002d5c3  test    rax, rax
0x18002d5c6  jnz     short loc_18002D61F
0x18002d5c8  call    cs:__imp_GetLastError
0x18002d5ce  mov     edi, 80070000h
0x18002d5d3  test    eax, eax
0x18002d5d5  jle     short loc_18002D5DE
0x18002d5d7  movzx   eax, ax
0x18002d5da  or      eax, edi
0x18002d5dc  test    eax, eax
0x18002d5de  jns     short loc_18002D5FD
0x18002d5e0  call    cs:__imp_GetLastError
0x18002d5e6  mov     ebx, eax
0x18002d5e8  test    eax, eax
0x18002d5ea  jle     short loc_18002D5F1
0x18002d5ec  movzx   ebx, ax
0x18002d5ef  or      ebx, edi
0x18002d5f1  test    ebx, ebx
0x18002d5f3  mov     eax, 80070008h
0x18002d5f8  cmovns  ebx, eax
0x18002d5fb  jmp     short loc_18002D602
0x18002d5fd  mov     ebx, 80004005h
0x18002d602  mov     r9d, ebx
0x18002d605  lea     r8, aPcopyfile; "pCopyFile"
0x18002d60c  lea     rdx, aHsFailedToAllo; "%hs: Failed to allocate buffer for copy"...
0x18002d613  xor     ecx, ecx
0x18002d615  call    UnattendLogW
0x18002d61a  jmp     loc_18002D6A6
0x18002d61f  mov     ebx, edi
0x18002d621  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002d625  mov     qword ptr [rsp+60h+dwCreationDisposition], rdi; lpOverlapped
0x18002d62a  mov     r8d, 400000h; nNumberOfBytesToRead
0x18002d630  mov     rdx, rsi; lpBuffer
0x18002d633  mov     rcx, r13; hFile
0x18002d636  call    cs:__imp_ReadFile
0x18002d63c  test    eax, eax
0x18002d63e  jz      short loc_18002D69E
0x18002d640  mov     r8d, [rbp+NumberOfBytesRead]; nNumberOfBytesToWrite
0x18002d644  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002d648  mov     rdx, rsi; lpBuffer
0x18002d64b  mov     [rbp+NumberOfBytesWritten], edi
0x18002d64e  mov     rcx, r12; hFile
0x18002d651  mov     qword ptr [rsp+60h+dwCreationDisposition], rdi; lpOverlapped
0x18002d656  call    cs:__imp_WriteFile
0x18002d65c  test    eax, eax
0x18002d65e  jz      short loc_18002D671
0x18002d660  mov     eax, [rbp+NumberOfBytesRead]
0x18002d663  cmp     [rbp+NumberOfBytesWritten], eax
0x18002d666  jnz     short loc_18002D671
0x18002d668  cmp     eax, 400000h
0x18002d66d  jnb     short loc_18002D621
0x18002d66f  jmp     short loc_18002D69E
0x18002d671  call    cs:__imp_GetLastError
0x18002d677  mov     ebx, eax
0x18002d679  test    eax, eax
0x18002d67b  jle     short loc_18002D686
0x18002d67d  movzx   ebx, ax
0x18002d680  or      ebx, 80070000h
0x18002d686  mov     r9d, ebx
0x18002d689  lea     r8, aPcopyfile; "pCopyFile"
0x18002d690  lea     rdx, aHsFailedToWrit; "%hs: Failed to write file. Error: 0x%08"...
0x18002d697  xor     ecx, ecx
0x18002d699  call    UnattendLogW
0x18002d69e  mov     rcx, rsi; Block
0x18002d6a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d6a6  mov     rcx, r12; hObject
0x18002d6a9  call    cs:__imp_CloseHandle
0x18002d6af  mov     rcx, r13; hObject
0x18002d6b2  call    cs:__imp_CloseHandle
0x18002d6b8  test    ebx, ebx
0x18002d6ba  js      short loc_18002D70D
0x18002d6bc  mov     rcx, r14; lpFileName
0x18002d6bf  call    cs:__imp_GetFileAttributesW
0x18002d6c5  cmp     eax, 0FFFFFFFFh
0x18002d6c8  jz      short loc_18002D6EB
0x18002d6ca  mov     edx, eax; dwFileAttributes
0x18002d6cc  mov     rcx, r15; lpFileName
0x18002d6cf  call    cs:__imp_SetFileAttributesW
0x18002d6d5  test    eax, eax
0x18002d6d7  jnz     short loc_18002D70D
0x18002d6d9  call    cs:__imp_GetLastError
0x18002d6df  mov     r9, r15
0x18002d6e2  lea     rdx, aHsFailedToSetA; "%hs: Failed to set attributes for %s. E"...
0x18002d6e9  jmp     short loc_18002D6FB
0x18002d6eb  call    cs:__imp_GetLastError
0x18002d6f1  mov     r9, r14
0x18002d6f4  lea     rdx, aHsFailedToGetA; "%hs: Failed to get attributes for %s. E"...
0x18002d6fb  lea     r8, aPcopyfile; "pCopyFile"
0x18002d702  mov     [rsp+60h+dwCreationDisposition], eax
0x18002d706  xor     ecx, ecx
0x18002d708  call    UnattendLogW
0x18002d70d  mov     eax, ebx
0x18002d70f  jmp     short loc_18002D727
0x18002d711  lea     rdx, aHsInputPathIsN; "%hs: Input Path is NULL"
0x18002d718  mov     ecx, 1
0x18002d71d  call    UnattendLogW
0x18002d722  mov     eax, 80070057h
0x18002d727  mov     rcx, [rbp+var_8]
0x18002d72b  xor     rcx, rsp; StackCookie
0x18002d72e  call    __security_check_cookie
0x18002d733  mov     rbx, [rsp+60h+arg_10]
0x18002d73b  add     rsp, 60h
0x18002d73f  pop     r15
0x18002d741  pop     r14
0x18002d743  pop     r13
0x18002d745  pop     r12
0x18002d747  pop     rdi
0x18002d748  pop     rsi
0x18002d749  pop     rbp
0x18002d74a  retn
```
