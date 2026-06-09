# HrIsProcessOE

- ea: `0x18000b940`
- end: `0x18000b9cd`
- name: `HrIsProcessOE`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001c80`
- `0x18000b940`
- `0x180012fc0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b995`
- `msvcrt!_wcsicmp` at `0x18000b995`
- `KERNEL32!GetModuleFileNameW` at `0x18000b971`
- `KERNEL32!GetModuleFileNameW` at `0x18000b971`
- `SHLWAPI!PathFindFileNameW` at `0x18000b980`
- `SHLWAPI!PathFindFileNameW` at `0x18000b980`

## pseudocode

```c
__int64 __fastcall HrIsProcessOE(BOOL *a1)
{
  const wchar_t *FileNameW; // rax
  BOOL v3; // ecx
  __int64 result; // rax
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  *a1 = 1;
  if ( !GetModuleFileNameW(0, Filename, 0x104u) )
    return HrGetLastError();
  FileNameW = PathFindFileNameW(Filename);
  if ( !FileNameW )
    return 2147500037LL;
  v3 = _wcsicmp(FileNameW, L"WinMail.exe") == 0;
  result = 0;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x18000b940  push    rbx
0x18000b942  sub     rsp, 240h
0x18000b949  mov     rax, cs:__security_cookie
0x18000b950  xor     rax, rsp
0x18000b953  mov     [rsp+248h+var_18], rax
0x18000b95b  mov     rbx, rcx
0x18000b95e  mov     dword ptr [rcx], 1
0x18000b964  xor     ecx, ecx; hModule
0x18000b966  lea     rdx, [rsp+248h+Filename]; lpFilename
0x18000b96b  mov     r8d, 104h; nSize
0x18000b971  call    cs:__imp_GetModuleFileNameW
0x18000b977  test    eax, eax
0x18000b979  jz      short loc_18000B9AF
0x18000b97b  lea     rcx, [rsp+248h+Filename]; pszPath
0x18000b980  call    cs:__imp_PathFindFileNameW
0x18000b986  test    rax, rax
0x18000b989  jz      short loc_18000B9A8
0x18000b98b  lea     rdx, aWinmailExe; "WinMail.exe"
0x18000b992  mov     rcx, rax; String1
0x18000b995  call    cs:__imp__wcsicmp
0x18000b99b  xor     ecx, ecx
0x18000b99d  test    eax, eax
0x18000b99f  setz    cl
0x18000b9a2  xor     eax, eax
0x18000b9a4  mov     [rbx], ecx
0x18000b9a6  jmp     short loc_18000B9B4
0x18000b9a8  mov     eax, 80004005h
0x18000b9ad  jmp     short loc_18000B9B4
0x18000b9af  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18000b9b4  mov     rcx, [rsp+248h+var_18]
0x18000b9bc  xor     rcx, rsp; StackCookie
0x18000b9bf  call    __security_check_cookie
0x18000b9c4  add     rsp, 240h
0x18000b9cb  pop     rbx
0x18000b9cc  retn
```
