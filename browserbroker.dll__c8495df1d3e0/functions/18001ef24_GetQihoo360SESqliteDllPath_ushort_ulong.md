# GetQihoo360SESqliteDllPath(ushort *,ulong)

- ea: `0x18001ef24`
- end: `0x18001f05c`
- name: `?GetQihoo360SESqliteDllPath@@YAJPEAGK@Z`
- size: `312`
- prototype: `__int64 __fastcall(PWSTR pszPath, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000c640`
- `0x18001f5b4`

## callees

- `0x180002ce0`
- `0x18001ef24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f029`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ef86`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001eff4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ef86`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001eff4`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001efa3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f00b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f021`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001efa3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f00b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f021`

## string_xrefs

- `0x18001ef69`: `Software\Microsoft\Windows\CurrentVersion\App Paths\360se6.exe`
- `0x18001efdd`: `Software\360\360se6\Update\Clients\{02E720BD-2B50-4404-947C-65DBE64F6970}`
- `0x18001f015`: `sqlite3.dll`

## pseudocode

```c
HRESULT __fastcall GetQihoo360SESqliteDllPath(PWSTR pszPath)
{
  HRESULT result; // eax
  DWORD pcbData[4]; // [rsp+40h] [rbp-448h] BYREF
  WCHAR pszMore[264]; // [rsp+50h] [rbp-438h] BYREF
  WCHAR pvData[264]; // [rsp+260h] [rbp-228h] BYREF

  pcbData[0] = 520;
  if ( RegGetValueW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\App Paths\\360se6.exe",
         L"Path",
         2u,
         0,
         pszMore,
         pcbData) )
  {
    goto LABEL_6;
  }
  result = PathCchAppend(pszPath, 0x104u, pszMore);
  if ( result < 0 )
    return result;
  pcbData[0] = 520;
  if ( RegGetValueW(
         HKEY_CURRENT_USER,
         L"Software\\360\\360se6\\Update\\Clients\\{02E720BD-2B50-4404-947C-65DBE64F6970}",
         L"pv",
         2u,
         0,
         pvData,
         pcbData) )
  {
LABEL_6:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    result = PathCchAppend(pszPath, 0x104u, pvData);
    if ( result >= 0 )
      return PathCchAppend(pszPath, 0x104u, L"sqlite3.dll");
  }
  return result;
}

```

## disassembly

```asm
0x18001ef24  mov     [rsp+arg_8], rbx
0x18001ef29  push    rdi
0x18001ef2a  sub     rsp, 480h
0x18001ef31  mov     rax, cs:__security_cookie
0x18001ef38  xor     rax, rsp
0x18001ef3b  mov     [rsp+488h+var_18], rax
0x18001ef43  lea     rax, [rsp+488h+var_448]
0x18001ef48  mov     [rsp+488h+var_448], 208h
0x18001ef50  mov     [rsp+488h+pcbData], rax; pcbData
0x18001ef55  lea     r8, KeyName; "Path"
0x18001ef5c  lea     rax, [rsp+488h+pszMore]
0x18001ef61  mov     rbx, rcx
0x18001ef64  mov     [rsp+488h+pvData], rax; pvData
0x18001ef69  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001ef70  mov     r9d, 2; dwFlags
0x18001ef76  mov     [rsp+488h+pdwType], 0; pdwType
0x18001ef7f  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001ef86  call    cs:__imp_RegGetValueW
0x18001ef8c  test    eax, eax
0x18001ef8e  jnz     loc_18001F029
0x18001ef94  mov     edi, 104h
0x18001ef99  lea     r8, [rsp+488h+pszMore]; pszMore
0x18001ef9e  mov     edx, edi; cchPath
0x18001efa0  mov     rcx, rbx; pszPath
0x18001efa3  call    cs:__imp_PathCchAppend
0x18001efa9  test    eax, eax
0x18001efab  js      loc_18001F03B
0x18001efb1  lea     rax, [rsp+488h+var_448]
0x18001efb6  mov     [rsp+488h+var_448], 208h
0x18001efbe  mov     [rsp+488h+pcbData], rax; pcbData
0x18001efc3  lea     r8, aPv; "pv"
0x18001efca  lea     rax, [rsp+488h+var_228]
0x18001efd2  mov     r9d, 2; dwFlags
0x18001efd8  mov     [rsp+488h+pvData], rax; pvData
0x18001efdd  lea     rdx, aSoftware360360; "Software\\360\\360se6\\Update\\Clients"...
0x18001efe4  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001efeb  mov     [rsp+488h+pdwType], 0; pdwType
0x18001eff4  call    cs:__imp_RegGetValueW
0x18001effa  test    eax, eax
0x18001effc  jnz     short loc_18001F029
0x18001effe  lea     r8, [rsp+488h+var_228]; pszMore
0x18001f006  mov     edx, edi; cchPath
0x18001f008  mov     rcx, rbx; pszPath
0x18001f00b  call    cs:__imp_PathCchAppend
0x18001f011  test    eax, eax
0x18001f013  js      short loc_18001F03B
0x18001f015  lea     r8, aSqlite3Dll; "sqlite3.dll"
0x18001f01c  mov     edx, edi; cchPath
0x18001f01e  mov     rcx, rbx; pszPath
0x18001f021  call    cs:__imp_PathCchAppend
0x18001f027  jmp     short loc_18001F03B
0x18001f029  call    cs:__imp_GetLastError
0x18001f02f  test    eax, eax
0x18001f031  jle     short loc_18001F03B
0x18001f033  movzx   eax, ax
0x18001f036  or      eax, 80070000h
0x18001f03b  mov     rcx, [rsp+488h+var_18]
0x18001f043  xor     rcx, rsp; StackCookie
0x18001f046  call    __security_check_cookie
0x18001f04b  mov     rbx, [rsp+488h+arg_8]
0x18001f053  add     rsp, 480h
0x18001f05a  pop     rdi
0x18001f05b  retn
```
