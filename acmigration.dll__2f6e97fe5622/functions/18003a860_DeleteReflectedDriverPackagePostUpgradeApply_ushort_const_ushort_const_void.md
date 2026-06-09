# DeleteReflectedDriverPackagePostUpgradeApply(ushort const *,ushort const *,void *)

- ea: `0x18003a860`
- end: `0x18003ac0b`
- name: `?DeleteReflectedDriverPackagePostUpgradeApply@@YAJPEBG0PEAX@Z`
- size: `939`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x1800028e0`
- `0x18003a860`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!MoveFileW` at `0x18003ab7c`
- `KERNEL32!MoveFileW` at `0x18003ab7c`
- `KERNEL32!CreateDirectoryW` at `0x18003aa72`
- `KERNEL32!CreateDirectoryW` at `0x18003ab05`
- `KERNEL32!CreateDirectoryW` at `0x18003aa72`
- `KERNEL32!CreateDirectoryW` at `0x18003ab05`
- `KERNEL32!FindClose` at `0x18003abe4`
- `KERNEL32!FindClose` at `0x18003abe4`
- `KERNEL32!FindFirstFileW` at `0x18003a99c`
- `KERNEL32!FindFirstFileW` at `0x18003a99c`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003a921`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003a921`
- `KERNEL32!GetLastError` at `0x18003a92b`
- `KERNEL32!GetLastError` at `0x18003a9ab`
- `KERNEL32!GetLastError` at `0x18003aa7c`
- `KERNEL32!GetLastError` at `0x18003ab0f`
- `KERNEL32!GetLastError` at `0x18003ab86`
- `KERNEL32!GetLastError` at `0x18003a92b`
- `KERNEL32!GetLastError` at `0x18003a9ab`
- `KERNEL32!GetLastError` at `0x18003aa7c`
- `KERNEL32!GetLastError` at `0x18003ab0f`
- `KERNEL32!GetLastError` at `0x18003ab86`

## string_xrefs

- `0x18003a8f0`: `DeleteReflectedDriverPackagePostUpgradeApply`
- `0x18003a94a`: `Error expanding Windows directory. [%x]`
- `0x18003a96e`: `System32\DriverStore\FileRepository`
- `0x18003aa27`: `Directory found = %S`
- `0x18003aa40`: `Temp\MigrationShims`
- `0x18003aac7`: `Temp\MigrationShims`
- `0x18003ab4a`: `Temp\MigrationShims`
- `0x18003aaa5`: `Failed to create directory: %S. [%x]`
- `0x18003aad1`: `DeleteReflectedDriverPackagePostUpgrade`
- `0x18003aba8`: `Error deleting directory: %S. [%x]`

## pseudocode

```c
__int64 __fastcall DeleteReflectedDriverPackagePostUpgradeApply(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        void *a3)
{
  signed int v4; // eax
  unsigned int v5; // ebx
  HANDLE FirstFileW; // rdi
  signed int LastError; // eax
  signed int v8; // eax
  __int64 v9; // r8
  wchar_t *v10; // rax
  const char *v11; // r9
  signed int v12; // eax
  signed int v13; // eax
  __int64 v15; // [rsp+28h] [rbp-D8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t PathName[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR Dst[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  wchar_t ExistingFileName[264]; // [rsp+6B0h] [rbp+5B0h] BYREF
  wchar_t Buffer[264]; // [rsp+8C0h] [rbp+7C0h] BYREF

  memset_0(Dst, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  memset_0(ExistingFileName, 0, 0x208u);
  memset_0(PathName, 0, 0x208u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  AslLogCallPrintf(3, "DeleteReflectedDriverPackagePostUpgradeApply", 115, "StrongName = %S", a2);
  if ( ExpandEnvironmentStringsW(L"%WinDir%", Dst, 0x104u) )
  {
    swprintf_s(Buffer, 0x104u, L"%s\\%s\\%s", Dst, L"System32\\DriverStore\\FileRepository", a2);
    FirstFileW = FindFirstFileW(Buffer, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      AslLogCallPrintf(
        1,
        "DeleteReflectedDriverPackagePostUpgradeApply",
        129,
        "No driver package folder where found with pattern: %S. [%x]",
        Buffer,
        v5);
      goto LABEL_27;
    }
    swprintf_s(
      ExistingFileName,
      0x104u,
      L"%s\\%s\\%s",
      Dst,
      L"System32\\DriverStore\\FileRepository",
      FindFileData.cFileName);
    AslLogCallPrintf(3, "DeleteReflectedDriverPackagePostUpgradeApply", 134, "Directory found = %S", ExistingFileName);
    swprintf_s(PathName, 0x104u, L"%s\\%s", Dst, L"Temp\\MigrationShims");
    if ( CreateDirectoryW(PathName, 0) || (v8 = GetLastError(), v5 = v8, v8 == 183) )
    {
      swprintf_s(
        PathName,
        0x104u,
        L"%s\\%s\\%s",
        Dst,
        L"Temp\\MigrationShims",
        L"DeleteReflectedDriverPackagePostUpgrade");
      if ( CreateDirectoryW(PathName, 0) || (v12 = GetLastError(), v5 = v12, v12 == 183) )
      {
        swprintf_s(
          PathName,
          0x104u,
          L"%s\\%s\\%s\\%s",
          Dst,
          L"Temp\\MigrationShims",
          L"DeleteReflectedDriverPackagePostUpgrade",
          FindFileData.cFileName);
        if ( MoveFileW(ExistingFileName, PathName) )
        {
          AslLogCallPrintf(
            3,
            "DeleteReflectedDriverPackagePostUpgradeApply",
            171,
            "Driver package backed-up at: %S",
            PathName);
          v5 = 0;
LABEL_26:
          if ( !FirstFileW )
            return v5;
LABEL_27:
          FindClose(FirstFileW);
          return v5;
        }
        v13 = GetLastError();
        v5 = v13;
        if ( v13 > 0 )
          v5 = (unsigned __int16)v13 | 0x80070000;
        v10 = ExistingFileName;
        v9 = 168;
        v11 = "Error deleting directory: %S. [%x]";
LABEL_15:
        LODWORD(v15) = v5;
        AslLogCallPrintf(1, "DeleteReflectedDriverPackagePostUpgradeApply", v9, v11, v10, v15);
        goto LABEL_26;
      }
      if ( v12 > 0 )
        v5 = (unsigned __int16)v12 | 0x80070000;
      v9 = 155;
    }
    else
    {
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      v9 = 143;
    }
    v10 = PathName;
    v11 = "Failed to create directory: %S. [%x]";
    goto LABEL_15;
  }
  v4 = GetLastError();
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  AslLogCallPrintf(
    1,
    "DeleteReflectedDriverPackagePostUpgradeApply",
    120,
    "Error expanding Windows directory. [%x]",
    v5);
  return v5;
}

```

## disassembly

```asm
0x18003a860  push    rbp
0x18003a862  push    rbx
0x18003a863  push    rsi
0x18003a864  push    rdi
0x18003a865  push    r13
0x18003a867  push    r14
0x18003a869  lea     rbp, [rsp-9E8h]
0x18003a871  sub     rsp, 0AE8h
0x18003a878  mov     rax, cs:__security_cookie
0x18003a87f  xor     rax, rsp
0x18003a882  mov     [rbp+0A10h+var_40], rax
0x18003a889  mov     rbx, rdx
0x18003a88c  lea     rcx, [rbp+0A10h+Dst]; void *
0x18003a893  mov     edi, 208h
0x18003a898  xor     edx, edx; Val
0x18003a89a  mov     r8d, edi; Size
0x18003a89d  call    memset_0
0x18003a8a2  mov     r8d, edi; Size
0x18003a8a5  lea     rcx, [rbp+0A10h+Buffer]; void *
0x18003a8ac  xor     edx, edx; Val
0x18003a8ae  call    memset_0
0x18003a8b3  mov     r8d, edi; Size
0x18003a8b6  lea     rcx, [rbp+0A10h+ExistingFileName]; void *
0x18003a8bd  xor     edx, edx; Val
0x18003a8bf  call    memset_0
0x18003a8c4  mov     r8d, edi; Size
0x18003a8c7  lea     rcx, [rbp+0A10h+PathName]; void *
0x18003a8ce  xor     edx, edx; Val
0x18003a8d0  call    memset_0
0x18003a8d5  xor     edx, edx; Val
0x18003a8d7  lea     r8d, [rdi+48h]; Size
0x18003a8db  lea     rcx, [rsp+0B10h+FindFileData]; void *
0x18003a8e0  call    memset_0
0x18003a8e5  mov     r8d, 73h ; 's'
0x18003a8eb  mov     [rsp+0B10h+var_AF0], rbx
0x18003a8f0  lea     rsi, aDeletereflecte; "DeleteReflectedDriverPackagePostUpgrade"...
0x18003a8f7  lea     r9, aStrongnameS; "StrongName = %S"
0x18003a8fe  mov     rdx, rsi
0x18003a901  lea     ecx, [r8-70h]
0x18003a905  call    AslLogCallPrintf
0x18003a90a  mov     r14d, 104h
0x18003a910  lea     rdx, [rbp+0A10h+Dst]; lpDst
0x18003a917  mov     r8d, r14d; nSize
0x18003a91a  lea     rcx, aWindir_1; "%WinDir%"
0x18003a921  call    cs:__imp_ExpandEnvironmentStringsW
0x18003a927  test    eax, eax
0x18003a929  jnz     short loc_18003A962
0x18003a92b  call    cs:__imp_GetLastError
0x18003a931  mov     ebx, eax
0x18003a933  test    eax, eax
0x18003a935  jle     short loc_18003A940
0x18003a937  movzx   ebx, ax
0x18003a93a  or      ebx, 80070000h
0x18003a940  mov     r8d, 78h ; 'x'
0x18003a946  mov     dword ptr [rsp+0B10h+var_AF0], ebx
0x18003a94a  lea     r9, aErrorExpanding; "Error expanding Windows directory. [%x]"
0x18003a951  mov     rdx, rsi
0x18003a954  lea     ecx, [r8-77h]
0x18003a958  call    AslLogCallPrintf
0x18003a95d  jmp     loc_18003ABEA
0x18003a962  mov     [rsp+0B10h+var_AE8], rbx
0x18003a967  lea     r9, [rbp+0A10h+Dst]
0x18003a96e  lea     rbx, aSystem32Driver; "System32\\DriverStore\\FileRepository"
0x18003a975  mov     rdx, r14; BufferCount
0x18003a978  lea     r8, aSSS; "%s\\%s\\%s"
0x18003a97f  mov     [rsp+0B10h+var_AF0], rbx
0x18003a984  lea     rcx, [rbp+0A10h+Buffer]; Buffer
0x18003a98b  call    swprintf_s
0x18003a990  lea     rdx, [rsp+0B10h+FindFileData]; lpFindFileData
0x18003a995  lea     rcx, [rbp+0A10h+Buffer]; lpFileName
0x18003a99c  call    cs:__imp_FindFirstFileW
0x18003a9a2  mov     rdi, rax
0x18003a9a5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003a9a9  jnz     short loc_18003A9EE
0x18003a9ab  call    cs:__imp_GetLastError
0x18003a9b1  mov     ebx, eax
0x18003a9b3  test    eax, eax
0x18003a9b5  jle     short loc_18003A9C0
0x18003a9b7  movzx   ebx, ax
0x18003a9ba  or      ebx, 80070000h
0x18003a9c0  mov     r8d, 81h
0x18003a9c6  mov     dword ptr [rsp+0B10h+var_AE8], ebx
0x18003a9ca  lea     rax, [rbp+0A10h+Buffer]
0x18003a9d1  mov     rdx, rsi
0x18003a9d4  lea     r9, aNoDriverPackag; "No driver package folder where found wi"...
0x18003a9db  mov     [rsp+0B10h+var_AF0], rax
0x18003a9e0  lea     ecx, [r8-80h]
0x18003a9e4  call    AslLogCallPrintf
0x18003a9e9  jmp     loc_18003ABE1
0x18003a9ee  lea     rax, [rsp+0B10h+FindFileData.cFileName]
0x18003a9f3  mov     rdx, r14; BufferCount
0x18003a9f6  mov     [rsp+0B10h+var_AE8], rax
0x18003a9fb  lea     r9, [rbp+0A10h+Dst]
0x18003aa02  lea     r8, aSSS; "%s\\%s\\%s"
0x18003aa09  mov     [rsp+0B10h+var_AF0], rbx
0x18003aa0e  lea     rcx, [rbp+0A10h+ExistingFileName]; Buffer
0x18003aa15  call    swprintf_s
0x18003aa1a  lea     rax, [rbp+0A10h+ExistingFileName]
0x18003aa21  mov     r8d, 86h
0x18003aa27  lea     r9, aDirectoryFound; "Directory found = %S"
0x18003aa2e  mov     [rsp+0B10h+var_AF0], rax
0x18003aa33  mov     rdx, rsi
0x18003aa36  mov     ecx, 3
0x18003aa3b  call    AslLogCallPrintf
0x18003aa40  lea     rax, aTempMigrations; "Temp\\MigrationShims"
0x18003aa47  mov     rdx, r14; BufferCount
0x18003aa4a  lea     r9, [rbp+0A10h+Dst]
0x18003aa51  mov     [rsp+0B10h+var_AF0], rax
0x18003aa56  lea     r8, aSS_0; "%s\\%s"
0x18003aa5d  lea     rcx, [rbp+0A10h+PathName]; Buffer
0x18003aa64  call    swprintf_s
0x18003aa69  xor     edx, edx; lpSecurityAttributes
0x18003aa6b  lea     rcx, [rbp+0A10h+PathName]; lpPathName
0x18003aa72  call    cs:__imp_CreateDirectoryW
0x18003aa78  test    eax, eax
0x18003aa7a  jnz     short loc_18003AAC7
0x18003aa7c  call    cs:__imp_GetLastError
0x18003aa82  mov     ebx, eax
0x18003aa84  cmp     eax, 0B7h
0x18003aa89  jz      short loc_18003AAC7
0x18003aa8b  test    eax, eax
0x18003aa8d  jle     short loc_18003AA98
0x18003aa8f  movzx   ebx, ax
0x18003aa92  or      ebx, 80070000h
0x18003aa98  mov     r8d, 8Fh
0x18003aa9e  lea     rax, [rbp+0A10h+PathName]
0x18003aaa5  lea     r9, aFailedToCreate_5; "Failed to create directory: %S. [%x]"
0x18003aaac  mov     dword ptr [rsp+0B10h+var_AE8], ebx
0x18003aab0  mov     rdx, rsi
0x18003aab3  mov     ecx, 1
0x18003aab8  mov     [rsp+0B10h+var_AF0], rax
0x18003aabd  call    AslLogCallPrintf
0x18003aac2  jmp     loc_18003ABDC
0x18003aac7  lea     rax, aTempMigrations; "Temp\\MigrationShims"
0x18003aace  mov     rdx, r14; BufferCount
0x18003aad1  lea     r13, aDeletereflecte_0; "DeleteReflectedDriverPackagePostUpgrade"
0x18003aad8  mov     [rsp+0B10h+var_AE8], r13
0x18003aadd  lea     r9, [rbp+0A10h+Dst]
0x18003aae4  lea     r8, aSSS; "%s\\%s\\%s"
0x18003aaeb  mov     [rsp+0B10h+var_AF0], rax
0x18003aaf0  lea     rcx, [rbp+0A10h+PathName]; Buffer
0x18003aaf7  call    swprintf_s
0x18003aafc  xor     edx, edx; lpSecurityAttributes
0x18003aafe  lea     rcx, [rbp+0A10h+PathName]; lpPathName
0x18003ab05  call    cs:__imp_CreateDirectoryW
0x18003ab0b  test    eax, eax
0x18003ab0d  jnz     short loc_18003AB36
0x18003ab0f  call    cs:__imp_GetLastError
0x18003ab15  mov     ebx, eax
0x18003ab17  cmp     eax, 0B7h
0x18003ab1c  jz      short loc_18003AB36
0x18003ab1e  test    eax, eax
0x18003ab20  jle     short loc_18003AB2B
0x18003ab22  movzx   ebx, ax
0x18003ab25  or      ebx, 80070000h
0x18003ab2b  mov     r8d, 9Bh
0x18003ab31  jmp     loc_18003AA9E
0x18003ab36  lea     rax, [rsp+0B10h+FindFileData.cFileName]
0x18003ab3b  mov     rdx, r14; BufferCount
0x18003ab3e  mov     [rsp+0B10h+var_AE0], rax
0x18003ab43  lea     r9, [rbp+0A10h+Dst]
0x18003ab4a  lea     rax, aTempMigrations; "Temp\\MigrationShims"
0x18003ab51  mov     [rsp+0B10h+var_AE8], r13
0x18003ab56  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x18003ab5d  mov     [rsp+0B10h+var_AF0], rax
0x18003ab62  lea     rcx, [rbp+0A10h+PathName]; Buffer
0x18003ab69  call    swprintf_s
0x18003ab6e  lea     rdx, [rbp+0A10h+PathName]; lpNewFileName
0x18003ab75  lea     rcx, [rbp+0A10h+ExistingFileName]; lpExistingFileName
0x18003ab7c  call    cs:__imp_MoveFileW
0x18003ab82  test    eax, eax
0x18003ab84  jnz     short loc_18003ABB4
0x18003ab86  call    cs:__imp_GetLastError
0x18003ab8c  mov     ebx, eax
0x18003ab8e  test    eax, eax
0x18003ab90  jle     short loc_18003AB9B
0x18003ab92  movzx   ebx, ax
0x18003ab95  or      ebx, 80070000h
0x18003ab9b  lea     rax, [rbp+0A10h+ExistingFileName]
0x18003aba2  mov     r8d, 0A8h
0x18003aba8  lea     r9, aErrorDeletingD; "Error deleting directory: %S. [%x]"
0x18003abaf  jmp     loc_18003AAAC
0x18003abb4  lea     rax, [rbp+0A10h+PathName]
0x18003abbb  mov     r8d, 0ABh
0x18003abc1  lea     r9, aDriverPackageB; "Driver package backed-up at: %S"
0x18003abc8  mov     [rsp+0B10h+var_AF0], rax
0x18003abcd  mov     rdx, rsi
0x18003abd0  mov     ecx, 3
0x18003abd5  call    AslLogCallPrintf
0x18003abda  xor     ebx, ebx
0x18003abdc  test    rdi, rdi
0x18003abdf  jz      short loc_18003ABEA
0x18003abe1  mov     rcx, rdi; hFindFile
0x18003abe4  call    cs:__imp_FindClose
0x18003abea  mov     eax, ebx
0x18003abec  mov     rcx, [rbp+0A10h+var_40]
0x18003abf3  xor     rcx, rsp; StackCookie
0x18003abf6  call    __security_check_cookie
0x18003abfb  add     rsp, 0AE8h
0x18003ac02  pop     r14
0x18003ac04  pop     r13
0x18003ac06  pop     rdi
0x18003ac07  pop     rsi
0x18003ac08  pop     rbx
0x18003ac09  pop     rbp
0x18003ac0a  retn
```
