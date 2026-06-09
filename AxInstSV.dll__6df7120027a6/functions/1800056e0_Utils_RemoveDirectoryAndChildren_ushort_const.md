# Utils::RemoveDirectoryAndChildren(ushort const *)

- ea: `0x1800056e0`
- end: `0x18000592b`
- name: `?RemoveDirectoryAndChildren@Utils@@SAJPEBG@Z`
- size: `587`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800056e0`
- `0x180006370`
- `0x180009f74`
- `0x18000bf6c`

## callees

- `0x180001720`
- `0x1800021b8`
- `0x1800056e0`
- `0x180005a28`
- `0x180005a88`
- `0x180005b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058ed`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180005728`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800058e3`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180005728`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800058e3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180005860`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000587f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180005860`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000587f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000588c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000588c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000589e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000589e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800058cf`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800058da`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800058cf`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800058da`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180005781`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180005781`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800057a0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800057ba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800057a0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800057ba`

## pseudocode

```c
__int64 __fastcall Utils::RemoveDirectoryAndChildren(const unsigned __int16 *a1)
{
  signed int v2; // ebx
  unsigned __int64 v3; // rdx
  HANDLE FirstFileW; // rdi
  signed int LastError; // eax
  signed int v6; // eax
  unsigned int v8; // [rsp+28h] [rbp-D8h]
  unsigned int v9; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v10; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v11; // [rsp+38h] [rbp-C8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR PathName[264]; // [rsp+290h] [rbp+190h] BYREF

  v2 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !RemoveDirectoryW(a1) )
  {
    v2 = StringCchCopyW(PathName, 0x104u, a1);
    if ( v2 >= 0 )
    {
      v2 = StringCchCatW(PathName, v3, L"\\*");
      if ( v2 >= 0 )
      {
        FirstFileW = FindFirstFileW(PathName, &FindFileData);
        if ( FirstFileW == (HANDLE)-1LL )
          goto LABEL_20;
        do
        {
          if ( lstrcmpW(FindFileData.cFileName, L".") && lstrcmpW(FindFileData.cFileName, L"..") )
          {
            v10 = 260;
            v11 = PathName;
            v2 = StringCchCopyExW(PathName, 0x104u, a1, &v11, &v10, v8);
            if ( v2 < 0 )
              goto LABEL_18;
            v2 = StringCchCopyExW(v11, v10, L"\\", &v11, &v10, v9);
            if ( v2 < 0 )
              goto LABEL_18;
            v2 = StringCchCopyW(v11, v10, FindFileData.cFileName);
            if ( v2 < 0 )
              goto LABEL_18;
            if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
            {
              SetFileAttributesW(PathName, 0x90u);
              v2 = Utils::RemoveDirectoryAndChildren(PathName);
              if ( v2 < 0 )
                goto LABEL_18;
            }
            else
            {
              SetFileAttributesW(PathName, 0x80u);
              if ( !DeleteFileW(PathName) )
                goto LABEL_16;
            }
          }
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        if ( GetLastError() != 18 )
        {
LABEL_16:
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
          FindClose(FirstFileW);
          return (unsigned int)v2;
        }
        FindClose(FirstFileW);
        if ( !RemoveDirectoryW(a1) )
        {
LABEL_20:
          v6 = GetLastError();
          v2 = v6;
          if ( v6 > 0 )
            return (unsigned __int16)v6 | 0x80070000;
        }
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800056e0  mov     [rsp-8+arg_8], rbx
0x1800056e5  mov     [rsp-8+arg_10], rsi
0x1800056ea  push    rbp
0x1800056eb  push    rdi
0x1800056ec  push    r14
0x1800056ee  lea     rbp, [rsp-3B0h]
0x1800056f6  sub     rsp, 4B0h
0x1800056fd  mov     rax, cs:__security_cookie
0x180005704  xor     rax, rsp
0x180005707  mov     [rbp+3C0h+var_20], rax
0x18000570e  mov     rsi, rcx
0x180005711  xor     edx, edx; Val
0x180005713  lea     rcx, [rsp+4C0h+FindFileData]; void *
0x180005718  mov     r8d, 250h; Size
0x18000571e  xor     ebx, ebx
0x180005720  call    memset_0
0x180005725  mov     rcx, rsi; lpPathName
0x180005728  call    cs:__imp_RemoveDirectoryW
0x18000572e  test    eax, eax
0x180005730  jnz     loc_180005902
0x180005736  mov     r14d, 104h
0x18000573c  lea     rcx, [rbp+3C0h+PathName]; unsigned __int16 *
0x180005743  mov     edx, r14d; unsigned __int64
0x180005746  mov     r8, rsi; unsigned __int16 *
0x180005749  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000574e  mov     ebx, eax
0x180005750  test    eax, eax
0x180005752  js      loc_180005902
0x180005758  lea     r8, asc_180018400; "\\*"
0x18000575f  lea     rcx, [rbp+3C0h+PathName]; unsigned __int16 *
0x180005766  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000576b  mov     ebx, eax
0x18000576d  test    eax, eax
0x18000576f  js      loc_180005902
0x180005775  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x18000577a  lea     rcx, [rbp+3C0h+PathName]; lpFileName
0x180005781  call    cs:__imp_FindFirstFileW
0x180005787  mov     rdi, rax
0x18000578a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000578e  jz      loc_1800058ED
0x180005794  lea     rdx, String2; "."
0x18000579b  lea     rcx, [rsp+4C0h+FindFileData.cFileName]; lpString1
0x1800057a0  call    cs:__imp_lstrcmpW
0x1800057a6  test    eax, eax
0x1800057a8  jz      loc_180005896
0x1800057ae  lea     rdx, asc_18001840C; ".."
0x1800057b5  lea     rcx, [rsp+4C0h+FindFileData.cFileName]; lpString1
0x1800057ba  call    cs:__imp_lstrcmpW
0x1800057c0  test    eax, eax
0x1800057c2  jz      loc_180005896
0x1800057c8  lea     rax, [rbp+3C0h+PathName]
0x1800057cf  mov     [rsp+4C0h+var_490], r14
0x1800057d4  mov     [rsp+4C0h+var_488], rax
0x1800057d9  lea     r9, [rsp+4C0h+var_488]; unsigned __int16 **
0x1800057de  lea     rax, [rsp+4C0h+var_490]
0x1800057e3  mov     r8, rsi; unsigned __int16 *
0x1800057e6  mov     rdx, r14; unsigned __int64
0x1800057e9  mov     [rsp+4C0h+var_4A0], rax; unsigned __int64 *
0x1800057ee  lea     rcx, [rbp+3C0h+PathName]; unsigned __int16 *
0x1800057f5  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800057fa  mov     ebx, eax
0x1800057fc  test    eax, eax
0x1800057fe  js      loc_1800058CC
0x180005804  mov     rdx, [rsp+4C0h+var_490]; unsigned __int64
0x180005809  lea     rax, [rsp+4C0h+var_490]
0x18000580e  mov     rcx, [rsp+4C0h+var_488]; unsigned __int16 *
0x180005813  lea     r9, [rsp+4C0h+var_488]; unsigned __int16 **
0x180005818  lea     r8, asc_1800176C0; "\\"
0x18000581f  mov     [rsp+4C0h+var_4A0], rax; unsigned __int64 *
0x180005824  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180005829  mov     ebx, eax
0x18000582b  test    eax, eax
0x18000582d  js      loc_1800058CC
0x180005833  mov     rdx, [rsp+4C0h+var_490]; unsigned __int64
0x180005838  lea     r8, [rsp+4C0h+FindFileData.cFileName]; unsigned __int16 *
0x18000583d  mov     rcx, [rsp+4C0h+var_488]; unsigned __int16 *
0x180005842  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005847  mov     ebx, eax
0x180005849  test    eax, eax
0x18000584b  js      short loc_1800058CC
0x18000584d  test    byte ptr [rsp+4C0h+FindFileData.dwFileAttributes], 10h
0x180005852  lea     rcx, [rbp+3C0h+PathName]; lpFileName
0x180005859  jz      short loc_18000587A
0x18000585b  mov     edx, 90h; dwFileAttributes
0x180005860  call    cs:__imp_SetFileAttributesW
0x180005866  lea     rcx, [rbp+3C0h+PathName]; unsigned __int16 *
0x18000586d  call    ?RemoveDirectoryAndChildren@Utils@@SAJPEBG@Z; Utils::RemoveDirectoryAndChildren(ushort const *)
0x180005872  mov     ebx, eax
0x180005874  test    eax, eax
0x180005876  js      short loc_1800058CC
0x180005878  jmp     short loc_180005896
0x18000587a  mov     edx, 80h; dwFileAttributes
0x18000587f  call    cs:__imp_SetFileAttributesW
0x180005885  lea     rcx, [rbp+3C0h+PathName]; lpFileName
0x18000588c  call    cs:__imp_DeleteFileW
0x180005892  test    eax, eax
0x180005894  jz      short loc_1800058B7
0x180005896  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x18000589b  mov     rcx, rdi; hFindFile
0x18000589e  call    cs:__imp_FindNextFileW
0x1800058a4  test    eax, eax
0x1800058a6  jnz     loc_180005794
0x1800058ac  call    cs:__imp_GetLastError
0x1800058b2  cmp     eax, 12h
0x1800058b5  jz      short loc_1800058D7
0x1800058b7  call    cs:__imp_GetLastError
0x1800058bd  mov     ebx, eax
0x1800058bf  test    eax, eax
0x1800058c1  jle     short loc_1800058CC
0x1800058c3  movzx   ebx, ax
0x1800058c6  or      ebx, 80070000h
0x1800058cc  mov     rcx, rdi; hFindFile
0x1800058cf  call    cs:__imp_FindClose
0x1800058d5  jmp     short loc_180005902
0x1800058d7  mov     rcx, rdi; hFindFile
0x1800058da  call    cs:__imp_FindClose
0x1800058e0  mov     rcx, rsi; lpPathName
0x1800058e3  call    cs:__imp_RemoveDirectoryW
0x1800058e9  test    eax, eax
0x1800058eb  jnz     short loc_180005902
0x1800058ed  call    cs:__imp_GetLastError
0x1800058f3  mov     ebx, eax
0x1800058f5  test    eax, eax
0x1800058f7  jle     short loc_180005902
0x1800058f9  movzx   ebx, ax
0x1800058fc  or      ebx, 80070000h
0x180005902  mov     eax, ebx
0x180005904  mov     rcx, [rbp+3C0h+var_20]
0x18000590b  xor     rcx, rsp; StackCookie
0x18000590e  call    __security_check_cookie
0x180005913  lea     r11, [rsp+4C0h+var_10]
0x18000591b  mov     rbx, [r11+28h]
0x18000591f  mov     rsi, [r11+30h]
0x180005923  mov     rsp, r11
0x180005926  pop     r14
0x180005928  pop     rdi
0x180005929  pop     rbp
0x18000592a  retn
```
