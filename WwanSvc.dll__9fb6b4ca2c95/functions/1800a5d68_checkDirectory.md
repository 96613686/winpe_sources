# _checkDirectory

- ea: `0x1800a5d68`
- end: `0x1800a5e3c`
- name: `_checkDirectory`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800a5c58`

## callees

- `0x1800085d0`
- `0x180012300`
- `0x180014f1c`
- `0x180015d6c`
- `0x1800a5d68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5dc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5dc6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a5dbb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a5dbb`
- `WwanPrfl!WwanProfileGetRootPath` at `0x1800a5d92`
- `WwanPrfl!WwanProfileGetRootPath` at `0x1800a5d92`

## string_xrefs

- `0x1800a5d9f`: `WwanProfileGetRootPath failed (errCode 0x%8x)`
- `0x1800a5dd3`: `GetFileAttributes failed for the path %s (errCode 0x%8x)`
- `0x1800a5da8`: `_checkDirectory`
- `0x1800a5dde`: `_checkDirectory`
- `0x1800a5df7`: `_checkDirectory`
- `0x1800a5e15`: `The path %s exists but not a directory (Attributes 0x%x)`
- `0x1800a5e02`: `The directory %s is found (Attributes 0x%x)`

## pseudocode

```c
__int64 __fastcall checkDirectory(unsigned int a1)
{
  unsigned int v1; // ebx
  unsigned int RootPath; // eax
  DWORD FileAttributesW; // eax
  DWORD LastError; // [rsp+20h] [rbp-238h]
  DWORD v6; // [rsp+20h] [rbp-238h]
  WCHAR FileName[264]; // [rsp+30h] [rbp-228h] BYREF

  v1 = 0;
  RootPath = WwanProfileGetRootPath(FileName, 260, a1);
  if ( RootPath )
  {
    WwanLog::Error("_checkDirectory", 0, L"WwanProfileGetRootPath failed (errCode 0x%8x)", RootPath);
  }
  else
  {
    FileAttributesW = GetFileAttributesW(FileName);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      WwanLog::Error(
        "_checkDirectory",
        0,
        L"GetFileAttributes failed for the path %s (errCode 0x%8x)",
        FileName,
        LastError);
    }
    else
    {
      v6 = FileAttributesW;
      if ( (FileAttributesW & 0x10) != 0 )
      {
        WwanLog::Info("_checkDirectory", 0, L"The directory %s is found (Attributes 0x%x)", FileName, v6);
        return 1;
      }
      else
      {
        WwanLog::Warning(
          "_checkDirectory",
          0,
          L"The path %s exists but not a directory (Attributes 0x%x)",
          FileName,
          v6);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800a5d68  push    rbx
0x1800a5d6a  sub     rsp, 250h
0x1800a5d71  mov     rax, cs:__security_cookie
0x1800a5d78  xor     rax, rsp
0x1800a5d7b  mov     [rsp+258h+var_18], rax
0x1800a5d83  mov     r8d, ecx
0x1800a5d86  mov     edx, 104h
0x1800a5d8b  lea     rcx, [rsp+258h+FileName]
0x1800a5d90  xor     ebx, ebx
0x1800a5d92  call    cs:__imp_WwanProfileGetRootPath
0x1800a5d98  test    eax, eax
0x1800a5d9a  jz      short loc_1800A5DB6
0x1800a5d9c  mov     r9d, eax
0x1800a5d9f  lea     r8, aWwanprofileget_0; "WwanProfileGetRootPath failed (errCode "...
0x1800a5da6  xor     edx, edx; struct _GUID *
0x1800a5da8  lea     rcx, aCheckdirectory; "_checkDirectory"
0x1800a5daf  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a5db4  jmp     short loc_1800A5E21
0x1800a5db6  lea     rcx, [rsp+258h+FileName]; lpFileName
0x1800a5dbb  call    cs:__imp_GetFileAttributesW
0x1800a5dc1  cmp     eax, 0FFFFFFFFh
0x1800a5dc4  jnz     short loc_1800A5DEC
0x1800a5dc6  call    cs:__imp_GetLastError
0x1800a5dcc  lea     r9, [rsp+258h+FileName]
0x1800a5dd1  xor     edx, edx; struct _GUID *
0x1800a5dd3  lea     r8, aGetfileattribu_0; "GetFileAttributes failed for the path %"...
0x1800a5dda  mov     [rsp+258h+var_238], eax
0x1800a5dde  lea     rcx, aCheckdirectory; "_checkDirectory"
0x1800a5de5  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a5dea  jmp     short loc_1800A5E21
0x1800a5dec  xor     edx, edx; struct _GUID *
0x1800a5dee  mov     [rsp+258h+var_238], eax
0x1800a5df2  lea     r9, [rsp+258h+FileName]
0x1800a5df7  lea     rcx, aCheckdirectory; "_checkDirectory"
0x1800a5dfe  test    al, 10h
0x1800a5e00  jz      short loc_1800A5E15
0x1800a5e02  lea     r8, aTheDirectorySI; "The directory %s is found (Attributes 0"...
0x1800a5e09  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800a5e0e  mov     ebx, 1
0x1800a5e13  jmp     short loc_1800A5E21
0x1800a5e15  lea     r8, aThePathSExists; "The path %s exists but not a directory "...
0x1800a5e1c  call    ?Warning@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Warning(char const *,_GUID const *,ushort const *,...)
0x1800a5e21  mov     eax, ebx
0x1800a5e23  mov     rcx, [rsp+258h+var_18]
0x1800a5e2b  xor     rcx, rsp; StackCookie
0x1800a5e2e  call    __security_check_cookie
0x1800a5e33  add     rsp, 250h
0x1800a5e3a  pop     rbx
0x1800a5e3b  retn
```
