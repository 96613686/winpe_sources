# CreateLowILTempFileW

- ea: `0x18000a8dc`
- end: `0x18000a9dd`
- name: `CreateLowILTempFileW`
- size: `257`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x18000ab80`

## callees

- `0x180001c80`
- `0x18000a8dc`
- `0x18000ffa0`
- `0x180012fc0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18000a990`
- `KERNEL32!CreateFileW` at `0x18000a990`
- `KERNEL32!GetTempFileNameW` at `0x18000a943`
- `KERNEL32!GetTempFileNameW` at `0x18000a943`
- `ole32!CoTaskMemFree` at `0x18000a9b0`
- `ole32!CoTaskMemFree` at `0x18000a9b0`
- `SHELL32!SHGetKnownFolderPath` at `0x18000a923`
- `SHELL32!SHGetKnownFolderPath` at `0x18000a923`

## pseudocode

```c
__int64 __fastcall CreateLowILTempFileW(__int64 *a1, _QWORD *a2)
{
  HRESULT LastError; // ebx
  __int64 v5; // rax
  HANDLE FileW; // rax
  PWSTR ppszPath; // [rsp+40h] [rbp-238h] BYREF
  WCHAR TempFileName[264]; // [rsp+50h] [rbp-228h] BYREF

  ppszPath = 0;
  LastError = SHGetKnownFolderPath(&FOLDERID_LocalAppDataLow, 0x4000u, 0, &ppszPath);
  if ( LastError >= 0 )
  {
    if ( GetTempFileNameW(ppszPath, L"wbk", 0, TempFileName) )
    {
      v5 = PszDupW(TempFileName);
      *a1 = v5;
      if ( v5 )
      {
        FileW = CreateFileW(TempFileName, 0xC0000000, 4u, 0, 3u, 0x100u, 0);
        *a2 = FileW;
        if ( FileW == (HANDLE)-1LL )
          LastError = HrGetLastError();
      }
    }
    else
    {
      LastError = -2147467259;
    }
  }
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000a8dc  mov     [rsp+arg_10], rbx
0x18000a8e1  mov     [rsp+arg_18], rsi
0x18000a8e6  push    rdi
0x18000a8e7  sub     rsp, 270h
0x18000a8ee  mov     rax, cs:__security_cookie
0x18000a8f5  xor     rax, rsp
0x18000a8f8  mov     [rsp+278h+var_18], rax
0x18000a900  mov     rsi, rdx
0x18000a903  mov     [rsp+278h+ppszPath], 0
0x18000a90c  mov     rdi, rcx
0x18000a90f  lea     r9, [rsp+278h+ppszPath]; ppszPath
0x18000a914  mov     edx, 4000h; dwFlags
0x18000a919  lea     rcx, FOLDERID_LocalAppDataLow; rfid
0x18000a920  xor     r8d, r8d; hToken
0x18000a923  call    cs:__imp_SHGetKnownFolderPath
0x18000a929  mov     ebx, eax
0x18000a92b  test    eax, eax
0x18000a92d  js      short loc_18000A9A6
0x18000a92f  mov     rcx, [rsp+278h+ppszPath]; lpPathName
0x18000a934  lea     r9, [rsp+278h+TempFileName]; lpTempFileName
0x18000a939  xor     r8d, r8d; uUnique
0x18000a93c  lea     rdx, aWbk_0; "wbk"
0x18000a943  call    cs:__imp_GetTempFileNameW
0x18000a949  test    eax, eax
0x18000a94b  jnz     short loc_18000A954
0x18000a94d  mov     ebx, 80004005h
0x18000a952  jmp     short loc_18000A9A6
0x18000a954  lea     rcx, [rsp+278h+TempFileName]; Src
0x18000a959  call    PszDupW
0x18000a95e  mov     [rdi], rax
0x18000a961  test    rax, rax
0x18000a964  jz      short loc_18000A9A6
0x18000a966  xor     r9d, r9d; lpSecurityAttributes
0x18000a969  mov     [rsp+278h+hTemplateFile], 0; hTemplateFile
0x18000a972  mov     [rsp+278h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x18000a97a  lea     rcx, [rsp+278h+TempFileName]; lpFileName
0x18000a97f  mov     edx, 0C0000000h; dwDesiredAccess
0x18000a984  mov     [rsp+278h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a98c  lea     r8d, [r9+4]; dwShareMode
0x18000a990  call    cs:__imp_CreateFileW
0x18000a996  mov     [rsi], rax
0x18000a999  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a99d  jnz     short loc_18000A9A6
0x18000a99f  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18000a9a4  mov     ebx, eax
0x18000a9a6  mov     rcx, [rsp+278h+ppszPath]; pv
0x18000a9ab  test    rcx, rcx
0x18000a9ae  jz      short loc_18000A9B6
0x18000a9b0  call    cs:__imp_CoTaskMemFree
0x18000a9b6  mov     eax, ebx
0x18000a9b8  mov     rcx, [rsp+278h+var_18]
0x18000a9c0  xor     rcx, rsp; StackCookie
0x18000a9c3  call    __security_check_cookie
0x18000a9c8  lea     r11, [rsp+278h+var_8]
0x18000a9d0  mov     rbx, [r11+20h]
0x18000a9d4  mov     rsi, [r11+28h]
0x18000a9d8  mov     rsp, r11
0x18000a9db  pop     rdi
0x18000a9dc  retn
```
