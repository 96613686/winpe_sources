# WwanFsDeleteFile(ushort const *,int)

- ea: `0x1800a5b90`
- end: `0x1800a5c4f`
- name: `?WwanFsDeleteFile@@YAKPEBGH@Z`
- size: `191`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, int)`
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18009f9f0`
- `0x1800a083c`
- `0x1800a1148`
- `0x1800a3e84`
- `0x1800a4478`
- `0x1800a4af8`
- `0x1800a4e14`

## callees

- `0x1800085d0`
- `0x180012300`
- `0x180019f24`
- `0x180074758`
- `0x180074cec`
- `0x1800a5b90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5c16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5c16`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a5c08`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a5c08`
- `WwanPrfl!WwanProfileGetPath` at `0x1800a5bd1`
- `WwanPrfl!WwanProfileGetPath` at `0x1800a5bd1`

## string_xrefs

- `0x1800a5be0`: `WwanProfileGetRootPath failed, errCode (0x%8x)`
- `0x1800a5bb4`: `WwanFsDeleteFile`
- `0x1800a5be9`: `WwanFsDeleteFile`
- `0x1800a5bf5`: `WwanFsDeleteFile`
- `0x1800a5c20`: `WwanFsDeleteFile`

## pseudocode

```c
__int64 __fastcall WwanFsDeleteFile(const unsigned __int16 *a1, unsigned int a2)
{
  DWORD Path; // eax
  DWORD LastError; // ebx
  WCHAR FileName[264]; // [rsp+20h] [rbp-228h] BYREF

  WwanLog::Enter("WwanFsDeleteFile");
  Path = WwanProfileGetPath(a1, FileName, 260, a2);
  LastError = Path;
  if ( Path )
  {
    WwanLog::Error("WwanFsDeleteFile", 0, L"WwanProfileGetRootPath failed, errCode (0x%8x)", Path);
    WwanLog::Exit("WwanFsDeleteFile");
  }
  else
  {
    if ( DeleteFileW(FileName) )
      LastError = 0;
    else
      LastError = GetLastError();
    WwanLog::ExitWithStatus("WwanFsDeleteFile", LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800a5b90  mov     [rsp+arg_10], rbx
0x1800a5b95  push    rdi
0x1800a5b96  sub     rsp, 240h
0x1800a5b9d  mov     rax, cs:__security_cookie
0x1800a5ba4  xor     rax, rsp
0x1800a5ba7  mov     [rsp+248h+var_18], rax
0x1800a5baf  mov     rdi, rcx
0x1800a5bb2  mov     ebx, edx
0x1800a5bb4  lea     rcx, aWwanfsdeletefi; "WwanFsDeleteFile"
0x1800a5bbb  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800a5bc0  mov     r9d, ebx
0x1800a5bc3  lea     rdx, [rsp+248h+FileName]
0x1800a5bc8  mov     r8d, 104h
0x1800a5bce  mov     rcx, rdi
0x1800a5bd1  call    cs:__imp_WwanProfileGetPath
0x1800a5bd7  mov     ebx, eax
0x1800a5bd9  test    eax, eax
0x1800a5bdb  jz      short loc_1800A5C03
0x1800a5bdd  mov     r9d, eax
0x1800a5be0  lea     r8, aWwanprofileget; "WwanProfileGetRootPath failed, errCode "...
0x1800a5be7  xor     edx, edx; struct _GUID *
0x1800a5be9  lea     rcx, aWwanfsdeletefi; "WwanFsDeleteFile"
0x1800a5bf0  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a5bf5  lea     rcx, aWwanfsdeletefi; "WwanFsDeleteFile"
0x1800a5bfc  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800a5c01  jmp     short loc_1800A5C2C
0x1800a5c03  lea     rcx, [rsp+248h+FileName]; lpFileName
0x1800a5c08  call    cs:__imp_DeleteFileW
0x1800a5c0e  test    eax, eax
0x1800a5c10  jz      short loc_1800A5C16
0x1800a5c12  xor     ebx, ebx
0x1800a5c14  jmp     short loc_1800A5C1E
0x1800a5c16  call    cs:__imp_GetLastError
0x1800a5c1c  mov     ebx, eax
0x1800a5c1e  mov     edx, ebx; unsigned int
0x1800a5c20  lea     rcx, aWwanfsdeletefi; "WwanFsDeleteFile"
0x1800a5c27  call    ?ExitWithStatus@WwanLog@@SAXPEBDK@Z; WwanLog::ExitWithStatus(char const *,ulong)
0x1800a5c2c  mov     eax, ebx
0x1800a5c2e  mov     rcx, [rsp+248h+var_18]
0x1800a5c36  xor     rcx, rsp; StackCookie
0x1800a5c39  call    __security_check_cookie
0x1800a5c3e  mov     rbx, [rsp+248h+arg_10]
0x1800a5c46  add     rsp, 240h
0x1800a5c4d  pop     rdi
0x1800a5c4e  retn
```
