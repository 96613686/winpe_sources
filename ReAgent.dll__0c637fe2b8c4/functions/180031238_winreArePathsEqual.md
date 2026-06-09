# winreArePathsEqual

- ea: `0x180031238`
- end: `0x18003142e`
- name: `winreArePathsEqual`
- size: `502`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001e4c8`
- `0x180037780`

## callees

- `0x1800059fc`
- `0x180031238`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800312a3`
- `KERNEL32!GetLastError` at `0x1800312d3`
- `KERNEL32!GetLastError` at `0x18003132c`
- `KERNEL32!GetLastError` at `0x18003136d`
- `KERNEL32!GetLastError` at `0x18003139d`
- `KERNEL32!GetLastError` at `0x1800313c0`
- `KERNEL32!GetLastError` at `0x1800312a3`
- `KERNEL32!GetLastError` at `0x1800312d3`
- `KERNEL32!GetLastError` at `0x18003132c`
- `KERNEL32!GetLastError` at `0x18003136d`
- `KERNEL32!GetLastError` at `0x18003139d`
- `KERNEL32!GetLastError` at `0x1800313c0`
- `KERNEL32!CreateFileW` at `0x18003131d`
- `KERNEL32!CreateFileW` at `0x18003135e`
- `KERNEL32!CreateFileW` at `0x18003131d`
- `KERNEL32!CreateFileW` at `0x18003135e`
- `KERNEL32!CloseHandle` at `0x1800313f8`
- `KERNEL32!CloseHandle` at `0x180031407`
- `KERNEL32!CloseHandle` at `0x1800313f8`
- `KERNEL32!CloseHandle` at `0x180031407`
- `KERNEL32!GetFileAttributesW` at `0x180031292`
- `KERNEL32!GetFileAttributesW` at `0x1800312c8`
- `KERNEL32!GetFileAttributesW` at `0x180031292`
- `KERNEL32!GetFileAttributesW` at `0x1800312c8`
- `KERNEL32!GetFileInformationByHandle` at `0x180031393`
- `KERNEL32!GetFileInformationByHandle` at `0x1800313b6`
- `KERNEL32!GetFileInformationByHandle` at `0x180031393`
- `KERNEL32!GetFileInformationByHandle` at `0x1800313b6`

## string_xrefs

- `0x1800312ac`: `winreArePathsEqualFailed to get attributes for %s: 0x%x`
- `0x180031335`: `winreArePathsEqualFailed to open for read %s: 0x%x`
- `0x180031376`: `winreArePathsEqualFailed to open for read %s: 0x%x`
- `0x1800313a6`: `winreArePathsEqualFailed to get file information for %s: 0x%x`

## pseudocode

```c
__int64 __fastcall winreArePathsEqual(LPCWSTR lpFileName, LPCWSTR a2, BOOL *a3)
{
  unsigned int v6; // r14d
  DWORD FileAttributesW; // eax
  char v8; // bl
  DWORD LastError; // eax
  LPCWSTR v10; // r8
  DWORD v11; // eax
  int v12; // ebx
  DWORD dwFlagsAndAttributes; // ebx
  HANDLE FileW; // r12
  DWORD v15; // eax
  HANDLE v16; // rbx
  DWORD v17; // eax
  DWORD v18; // eax
  LPCWSTR v19; // r8
  BOOL v20; // eax
  struct _BY_HANDLE_FILE_INFORMATION v22; // [rsp+40h] [rbp-59h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+78h] [rbp-21h] BYREF

  FileInformation.nFileIndexLow = 0;
  memset(&FileInformation, 0, 32);
  v22.nFileIndexLow = 0;
  *a3 = 0;
  *(_OWORD *)&FileInformation.nFileSizeHigh = 0;
  v6 = 0;
  memset(&v22, 0, 48);
  FileAttributesW = GetFileAttributesW(lpFileName);
  v8 = FileAttributesW;
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v10 = lpFileName;
LABEL_3:
    UnattendLogW(1, L"winreArePathsEqualFailed to get attributes for %s: 0x%x", v10, LastError);
    return v6;
  }
  v11 = GetFileAttributesW(a2);
  if ( v11 == -1 )
  {
    LastError = GetLastError();
    v10 = a2;
    goto LABEL_3;
  }
  v12 = v8 & 0x10;
  if ( v12 != (v11 & 0x10) )
  {
    *a3 = 0;
    return 1;
  }
  dwFlagsAndAttributes = v12 != 0 ? 0x2000000 : 0;
  FileW = CreateFileW(lpFileName, 0, 7u, 0, 3u, dwFlagsAndAttributes, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v15 = GetLastError();
    UnattendLogW(1, L"winreArePathsEqualFailed to open for read %s: 0x%x", lpFileName, v15);
    return v6;
  }
  v16 = CreateFileW(a2, 0, 7u, 0, 3u, dwFlagsAndAttributes, 0);
  if ( v16 == (HANDLE)-1LL )
  {
    v17 = GetLastError();
    UnattendLogW(1, L"winreArePathsEqualFailed to open for read %s: 0x%x", a2, v17);
  }
  else
  {
    if ( GetFileInformationByHandle(FileW, &FileInformation) )
    {
      if ( GetFileInformationByHandle(v16, &v22) )
      {
        v20 = FileInformation.dwVolumeSerialNumber == v22.dwVolumeSerialNumber
           && FileInformation.nFileIndexLow == v22.nFileIndexLow
           && FileInformation.nFileIndexHigh == v22.nFileIndexHigh;
        *a3 = v20;
        v6 = 1;
        goto LABEL_25;
      }
      v18 = GetLastError();
      v19 = a2;
    }
    else
    {
      v18 = GetLastError();
      v19 = lpFileName;
    }
    UnattendLogW(1, L"winreArePathsEqualFailed to get file information for %s: 0x%x", v19, v18);
  }
LABEL_25:
  CloseHandle(FileW);
  if ( v16 != (HANDLE)-1LL )
    CloseHandle(v16);
  return v6;
}

```

## disassembly

```asm
0x180031238  push    rbp
0x18003123a  push    rbx
0x18003123b  push    rsi
0x18003123c  push    rdi
0x18003123d  push    r12
0x18003123f  push    r14
0x180031241  push    r15
0x180031243  lea     rbp, [rsp-27h]
0x180031248  sub     rsp, 0C0h
0x18003124f  mov     rax, cs:__security_cookie
0x180031256  xor     rax, rsp
0x180031259  mov     [rbp+57h+var_40], rax
0x18003125d  xorps   xmm0, xmm0
0x180031260  xor     eax, eax
0x180031262  xorps   xmm1, xmm1
0x180031265  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x180031268  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x18003126c  mov     [rbp+57h+var_B0.nFileIndexLow], eax
0x18003126f  mov     r15, r8
0x180031272  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180031276  mov     [r8], eax
0x180031279  mov     rdi, rdx
0x18003127c  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x180031280  mov     rsi, rcx
0x180031283  xor     r14d, r14d
0x180031286  movups  xmmword ptr [rbp+57h+var_B0.dwFileAttributes], xmm1
0x18003128a  movups  xmmword ptr [rbp+57h+var_B0.ftLastAccessTime.dwHighDateTime], xmm1
0x18003128e  movups  xmmword ptr [rbp+57h+var_B0.nFileSizeHigh], xmm1
0x180031292  call    cs:__imp_GetFileAttributesW
0x180031298  or      r12d, 0FFFFFFFFh
0x18003129c  mov     ebx, eax
0x18003129e  cmp     eax, r12d
0x1800312a1  jnz     short loc_1800312C5
0x1800312a3  call    cs:__imp_GetLastError
0x1800312a9  mov     r8, rsi
0x1800312ac  lea     rdx, aWinrearepathse_1; "winreArePathsEqualFailed to get attribu"...
0x1800312b3  mov     r9d, eax
0x1800312b6  mov     ecx, 1
0x1800312bb  call    UnattendLogW
0x1800312c0  jmp     loc_18003140D
0x1800312c5  mov     rcx, rdi; lpFileName
0x1800312c8  call    cs:__imp_GetFileAttributesW
0x1800312ce  cmp     eax, r12d
0x1800312d1  jnz     short loc_1800312DE
0x1800312d3  call    cs:__imp_GetLastError
0x1800312d9  mov     r8, rdi
0x1800312dc  jmp     short loc_1800312AC
0x1800312de  and     ebx, 10h
0x1800312e1  and     eax, 10h
0x1800312e4  cmp     ebx, eax
0x1800312e6  jz      short loc_1800312F6
0x1800312e8  mov     [r15], r14d
0x1800312eb  mov     r14d, 1
0x1800312f1  jmp     loc_18003140D
0x1800312f6  neg     ebx
0x1800312f8  mov     [rsp+0F0h+hTemplateFile], r14; hTemplateFile
0x1800312fd  mov     rcx, rsi; lpFileName
0x180031300  sbb     ebx, ebx
0x180031302  xor     r9d, r9d; lpSecurityAttributes
0x180031305  and     ebx, 2000000h
0x18003130b  xor     edx, edx; dwDesiredAccess
0x18003130d  mov     [rsp+0F0h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180031311  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x180031319  lea     r8d, [r9+7]; dwShareMode
0x18003131d  call    cs:__imp_CreateFileW
0x180031323  mov     r12, rax
0x180031326  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003132a  jnz     short loc_180031341
0x18003132c  call    cs:__imp_GetLastError
0x180031332  mov     r8, rsi
0x180031335  lea     rdx, aWinrearepathse_0; "winreArePathsEqualFailed to open for re"...
0x18003133c  jmp     loc_1800312B3
0x180031341  xor     r9d, r9d; lpSecurityAttributes
0x180031344  mov     [rsp+0F0h+hTemplateFile], r14; hTemplateFile
0x180031349  mov     [rsp+0F0h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18003134d  xor     edx, edx; dwDesiredAccess
0x18003134f  mov     rcx, rdi; lpFileName
0x180031352  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18003135a  lea     r8d, [r9+7]; dwShareMode
0x18003135e  call    cs:__imp_CreateFileW
0x180031364  mov     rbx, rax
0x180031367  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003136b  jnz     short loc_18003138C
0x18003136d  call    cs:__imp_GetLastError
0x180031373  mov     r8, rdi
0x180031376  lea     rdx, aWinrearepathse_0; "winreArePathsEqualFailed to open for re"...
0x18003137d  mov     r9d, eax
0x180031380  mov     ecx, 1
0x180031385  call    UnattendLogW
0x18003138a  jmp     short loc_1800313F5
0x18003138c  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x180031390  mov     rcx, r12; hFile
0x180031393  call    cs:__imp_GetFileInformationByHandle
0x180031399  test    eax, eax
0x18003139b  jnz     short loc_1800313AF
0x18003139d  call    cs:__imp_GetLastError
0x1800313a3  mov     r8, rsi
0x1800313a6  lea     rdx, aWinrearepathse; "winreArePathsEqualFailed to get file in"...
0x1800313ad  jmp     short loc_18003137D
0x1800313af  lea     rdx, [rbp+57h+var_B0]; lpFileInformation
0x1800313b3  mov     rcx, rbx; hFile
0x1800313b6  call    cs:__imp_GetFileInformationByHandle
0x1800313bc  test    eax, eax
0x1800313be  jnz     short loc_1800313CB
0x1800313c0  call    cs:__imp_GetLastError
0x1800313c6  mov     r8, rdi
0x1800313c9  jmp     short loc_1800313A6
0x1800313cb  mov     eax, [rbp+57h+var_B0.dwVolumeSerialNumber]
0x1800313ce  cmp     [rbp+57h+FileInformation.dwVolumeSerialNumber], eax
0x1800313d1  jnz     short loc_1800313EA
0x1800313d3  mov     eax, [rbp+57h+var_B0.nFileIndexLow]
0x1800313d6  cmp     [rbp+57h+FileInformation.nFileIndexLow], eax
0x1800313d9  jnz     short loc_1800313EA
0x1800313db  mov     eax, [rbp+57h+var_B0.nFileIndexHigh]
0x1800313de  cmp     [rbp+57h+FileInformation.nFileIndexHigh], eax
0x1800313e1  jnz     short loc_1800313EA
0x1800313e3  mov     eax, 1
0x1800313e8  jmp     short loc_1800313EC
0x1800313ea  xor     eax, eax
0x1800313ec  mov     [r15], eax
0x1800313ef  mov     r14d, 1
0x1800313f5  mov     rcx, r12; hObject
0x1800313f8  call    cs:__imp_CloseHandle
0x1800313fe  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180031402  jz      short loc_18003140D
0x180031404  mov     rcx, rbx; hObject
0x180031407  call    cs:__imp_CloseHandle
0x18003140d  mov     eax, r14d
0x180031410  mov     rcx, [rbp+57h+var_40]
0x180031414  xor     rcx, rsp; StackCookie
0x180031417  call    __security_check_cookie
0x18003141c  add     rsp, 0C0h
0x180031423  pop     r15
0x180031425  pop     r14
0x180031427  pop     r12
0x180031429  pop     rdi
0x18003142a  pop     rsi
0x18003142b  pop     rbx
0x18003142c  pop     rbp
0x18003142d  retn
```
