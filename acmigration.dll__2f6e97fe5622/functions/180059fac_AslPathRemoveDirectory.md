# AslPathRemoveDirectory

- ea: `0x180059fac`
- end: `0x18005a221`
- name: `AslPathRemoveDirectory`
- size: `629`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18004d1e0`
- `0x18004d4d0`
- `0x180059f10`
- `0x180059fac`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x180002a8b`
- `0x180002b3f`
- `0x180002b4b`
- `0x180002b57`
- `0x180002b6f`
- `0x18005364c`
- `0x1800543c0`
- `0x180059fac`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x18005a02e`
- `KERNEL32!RemoveDirectoryW` at `0x18005a1b3`
- `KERNEL32!RemoveDirectoryW` at `0x18005a02e`
- `KERNEL32!RemoveDirectoryW` at `0x18005a1b3`

## string_xrefs

- `0x18005a1eb`: `Failed to make full file path [%x]`
- `0x18005a07f`: `AslPathRemoveDirectory`
- `0x18005a0c5`: `AslPathRemoveDirectory`
- `0x18005a06d`: `RemoveDirectory failed [%S] [%x]`

## pseudocode

```c
__int64 __fastcall AslPathRemoveDirectory(const WCHAR *a1)
{
  __int64 FirstFileW_0; // rsi
  signed int LastError_0; // ebx
  int v4; // eax
  const char *v5; // r9
  __int64 v6; // r8
  signed int v7; // eax
  __int64 v9; // [rsp+20h] [rbp-E0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR PathName[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR FileName[264]; // [rsp+490h] [rbp+390h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(FileName, 0, 0x208u);
  memset_0(PathName, 0, 0x208u);
  if ( !a1 || !*a1 )
    return 3221225485LL;
  FirstFileW_0 = -1;
  if ( RemoveDirectoryW(a1) || (LastError_0 = GetLastError_0(), (unsigned int)(LastError_0 - 2) <= 1) )
  {
LABEL_28:
    LastError_0 = 0;
  }
  else if ( LastError_0 == 145 )
  {
    v4 = RtlStringCchPrintfW(FileName, 260, L"%s\\*", a1);
    LastError_0 = v4;
    if ( v4 >= 0 )
    {
      FirstFileW_0 = (__int64)FindFirstFileW_0(FileName, &FindFileData);
      if ( FirstFileW_0 == -1 )
      {
        if ( (int)GetLastError_0() > 0 )
          LastError_0 = (unsigned __int16)GetLastError_0() | 0xC0070000;
        else
          LastError_0 = GetLastError_0();
        AslLogCallPrintf(1, "AslPathRemoveDirectory", 1404, "FindFirstFile failed [%x]", LastError_0);
      }
      else
      {
        do
        {
          if ( FindFileData.cFileName[0] != 46
            || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
          {
            v4 = RtlStringCchPrintfW(PathName, 260, L"%s\\%s", a1, FindFileData.cFileName);
            LastError_0 = v4;
            if ( v4 < 0 )
            {
              v5 = "Failed to make full file path [%x]";
              v6 = 1422;
              goto LABEL_11;
            }
            if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
              AslPathRemoveDirectory(PathName);
            else
              DeleteFileW_0(PathName);
          }
        }
        while ( FindNextFileW_0((HANDLE)FirstFileW_0, &FindFileData) );
        v7 = GetLastError_0();
        LastError_0 = v7;
        if ( v7 == 18 )
        {
          RemoveDirectoryW(a1);
          goto LABEL_28;
        }
        if ( v7 > 0 )
          LastError_0 = (unsigned __int16)v7 | 0xC0070000;
        LODWORD(v9) = LastError_0;
        AslLogCallPrintf(1, "AslPathRemoveDirectory", 1450, "FindNextFile failed [%x]", v9);
      }
    }
    else
    {
      v5 = "Failed to make find string [%x]";
      v6 = 1397;
LABEL_11:
      LODWORD(v9) = v4;
      AslLogCallPrintf(1, "AslPathRemoveDirectory", v6, v5, v9);
    }
  }
  else
  {
    if ( LastError_0 > 0 )
      LastError_0 = (unsigned __int16)LastError_0 | 0xC0070000;
    AslLogCallPrintf(1, "AslPathRemoveDirectory", 1387, "RemoveDirectory failed [%S] [%x]", a1, LastError_0);
  }
  FindClose_0((HANDLE)FirstFileW_0);
  return (unsigned int)LastError_0;
}

```

## disassembly

```asm
0x180059fac  push    rbp
0x180059fae  push    rbx
0x180059faf  push    rsi
0x180059fb0  push    rdi
0x180059fb1  push    r14
0x180059fb3  push    r15
0x180059fb5  lea     rbp, [rsp-5B8h]
0x180059fbd  sub     rsp, 6B8h
0x180059fc4  mov     rax, cs:__security_cookie
0x180059fcb  xor     rax, rsp
0x180059fce  mov     [rbp+5E0h+var_40], rax
0x180059fd5  mov     rdi, rcx
0x180059fd8  xor     edx, edx; Val
0x180059fda  lea     rcx, [rsp+6E0h+FindFileData]; void *
0x180059fdf  mov     r8d, 250h; Size
0x180059fe5  call    memset_0
0x180059fea  mov     ebx, 208h
0x180059fef  lea     rcx, [rbp+5E0h+FileName]; void *
0x180059ff6  mov     r8d, ebx; Size
0x180059ff9  xor     edx, edx; Val
0x180059ffb  call    memset_0
0x18005a000  mov     r8d, ebx; Size
0x18005a003  lea     rcx, [rbp+5E0h+PathName]; void *
0x18005a00a  xor     edx, edx; Val
0x18005a00c  call    memset_0
0x18005a011  xor     r14d, r14d
0x18005a014  test    rdi, rdi
0x18005a017  jz      loc_18005A1FD
0x18005a01d  cmp     [rdi], r14w
0x18005a021  jz      loc_18005A1FD
0x18005a027  mov     rcx, rdi; lpPathName
0x18005a02a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005a02e  call    cs:__imp_RemoveDirectoryW
0x18005a034  lea     r15d, [r14+1]
0x18005a038  cmp     eax, r15d
0x18005a03b  jz      loc_18005A1B9
0x18005a041  call    GetLastError_0
0x18005a046  mov     ebx, eax
0x18005a048  add     eax, 0FFFFFFFEh
0x18005a04b  cmp     eax, r15d
0x18005a04e  jbe     loc_18005A1B9
0x18005a054  cmp     ebx, 91h
0x18005a05a  jz      short loc_18005A093
0x18005a05c  test    ebx, ebx
0x18005a05e  jle     short loc_18005A069
0x18005a060  movzx   ebx, bx
0x18005a063  or      ebx, 0C0070000h
0x18005a069  mov     [rsp+6E0h+var_6B8], ebx
0x18005a06d  lea     r9, aRemovedirector; "RemoveDirectory failed [%S] [%x]"
0x18005a074  mov     r8d, 56Bh
0x18005a07a  mov     [rsp+6E0h+var_6C0], rdi
0x18005a07f  lea     rdx, aAslpathremoved; "AslPathRemoveDirectory"
0x18005a086  mov     ecx, r15d
0x18005a089  call    AslLogCallPrintf
0x18005a08e  jmp     loc_18005A1BC
0x18005a093  mov     r9, rdi
0x18005a096  lea     r8, aS; "%s\\*"
0x18005a09d  mov     edx, 104h
0x18005a0a2  lea     rcx, [rbp+5E0h+FileName]
0x18005a0a9  call    RtlStringCchPrintfW
0x18005a0ae  mov     ebx, eax
0x18005a0b0  test    eax, eax
0x18005a0b2  jns     short loc_18005A0D9
0x18005a0b4  lea     r9, aFailedToMakeFi; "Failed to make find string [%x]"
0x18005a0bb  mov     r8d, 575h
0x18005a0c1  mov     dword ptr [rsp+6E0h+var_6C0], eax
0x18005a0c5  lea     rdx, aAslpathremoved; "AslPathRemoveDirectory"
0x18005a0cc  mov     ecx, r15d
0x18005a0cf  call    AslLogCallPrintf
0x18005a0d4  jmp     loc_18005A1BC
0x18005a0d9  lea     rdx, [rsp+6E0h+FindFileData]; lpFindFileData
0x18005a0de  lea     rcx, [rbp+5E0h+FileName]; lpFileName
0x18005a0e5  call    FindFirstFileW_0
0x18005a0ea  mov     rsi, rax
0x18005a0ed  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005a0f1  jnz     short loc_18005A126
0x18005a0f3  call    GetLastError_0
0x18005a0f8  test    eax, eax
0x18005a0fa  jg      short loc_18005A105
0x18005a0fc  call    GetLastError_0
0x18005a101  mov     ebx, eax
0x18005a103  jmp     short loc_18005A113
0x18005a105  call    GetLastError_0
0x18005a10a  movzx   ebx, ax
0x18005a10d  or      ebx, 0C0070000h
0x18005a113  mov     dword ptr [rsp+6E0h+var_6C0], ebx
0x18005a117  lea     r9, aFindfirstfileF; "FindFirstFile failed [%x]"
0x18005a11e  mov     r8d, 57Ch
0x18005a124  jmp     short loc_18005A0C5
0x18005a126  cmp     [rsp+6E0h+FindFileData.cFileName], 2Eh ; '.'
0x18005a12c  movzx   eax, [rsp+6E0h+FindFileData.cFileName+2]
0x18005a131  jnz     short loc_18005A14E
0x18005a133  test    ax, ax
0x18005a136  jz      short loc_18005A193
0x18005a138  cmp     [rsp+6E0h+FindFileData.cFileName], 2Eh ; '.'
0x18005a13e  jnz     short loc_18005A14E
0x18005a140  cmp     ax, 2Eh ; '.'
0x18005a144  jnz     short loc_18005A14E
0x18005a146  cmp     [rsp+6E0h+FindFileData.cFileName+4], r14w
0x18005a14c  jz      short loc_18005A193
0x18005a14e  lea     rax, [rsp+6E0h+FindFileData.cFileName]
0x18005a153  mov     r9, rdi
0x18005a156  lea     r8, aSS_0; "%s\\%s"
0x18005a15d  mov     [rsp+6E0h+var_6C0], rax
0x18005a162  mov     edx, 104h
0x18005a167  lea     rcx, [rbp+5E0h+PathName]
0x18005a16e  call    RtlStringCchPrintfW
0x18005a173  mov     ebx, eax
0x18005a175  test    eax, eax
0x18005a177  js      short loc_18005A1EB
0x18005a179  test    byte ptr [rsp+6E0h+FindFileData.dwFileAttributes], 10h
0x18005a17e  lea     rcx, [rbp+5E0h+PathName]; lpFileName
0x18005a185  jnz     short loc_18005A18E
0x18005a187  call    DeleteFileW_0
0x18005a18c  jmp     short loc_18005A193
0x18005a18e  call    AslPathRemoveDirectory
0x18005a193  lea     rdx, [rsp+6E0h+FindFileData]; lpFindFileData
0x18005a198  mov     rcx, rsi; hFindFile
0x18005a19b  call    FindNextFileW_0
0x18005a1a0  test    eax, eax
0x18005a1a2  jnz     short loc_18005A126
0x18005a1a4  call    GetLastError_0
0x18005a1a9  mov     ebx, eax
0x18005a1ab  cmp     eax, 12h
0x18005a1ae  jnz     short loc_18005A1C8
0x18005a1b0  mov     rcx, rdi; lpPathName
0x18005a1b3  call    cs:__imp_RemoveDirectoryW
0x18005a1b9  mov     ebx, r14d
0x18005a1bc  mov     rcx, rsi; hFindFile
0x18005a1bf  call    FindClose_0
0x18005a1c4  mov     eax, ebx
0x18005a1c6  jmp     short loc_18005A202
0x18005a1c8  test    eax, eax
0x18005a1ca  jle     short loc_18005A1D5
0x18005a1cc  movzx   ebx, ax
0x18005a1cf  or      ebx, 0C0070000h
0x18005a1d5  mov     dword ptr [rsp+6E0h+var_6C0], ebx
0x18005a1d9  lea     r9, aFindnextfileFa; "FindNextFile failed [%x]"
0x18005a1e0  mov     r8d, 5AAh
0x18005a1e6  jmp     loc_18005A0C5
0x18005a1eb  lea     r9, aFailedToMakeFu; "Failed to make full file path [%x]"
0x18005a1f2  mov     r8d, 58Eh
0x18005a1f8  jmp     loc_18005A0C1
0x18005a1fd  mov     eax, 0C000000Dh
0x18005a202  mov     rcx, [rbp+5E0h+var_40]
0x18005a209  xor     rcx, rsp; StackCookie
0x18005a20c  call    __security_check_cookie
0x18005a211  add     rsp, 6B8h
0x18005a218  pop     r15
0x18005a21a  pop     r14
0x18005a21c  pop     rdi
0x18005a21d  pop     rsi
0x18005a21e  pop     rbx
0x18005a21f  pop     rbp
0x18005a220  retn
```
