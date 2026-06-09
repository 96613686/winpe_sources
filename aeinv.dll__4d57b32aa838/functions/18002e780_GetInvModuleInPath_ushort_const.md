# GetInvModuleInPath(ushort const *)

- ea: `0x18002e780`
- end: `0x18002e8a8`
- name: `?GetInvModuleInPath@@YAJPEBG@Z`
- size: `296`
- prototype: `__int64 __fastcall(LPCWSTR pszFile2)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180030430`

## callees

- `0x1800197d4`
- `0x18002e780`
- `0x180059920`
- `0x18005a8bc`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18002e808`
- `KERNEL32!GetModuleFileNameW` at `0x18002e808`
- `KERNEL32!GetLastError` at `0x18002e7d4`
- `KERNEL32!GetLastError` at `0x18002e819`
- `KERNEL32!GetLastError` at `0x18002e84e`
- `KERNEL32!GetLastError` at `0x18002e7d4`
- `KERNEL32!GetLastError` at `0x18002e819`
- `KERNEL32!GetLastError` at `0x18002e84e`
- `KERNEL32!GetModuleHandleExW` at `0x18002e7ca`
- `KERNEL32!GetModuleHandleExW` at `0x18002e7ca`
- `SHLWAPI!PathCommonPrefixW` at `0x18002e82f`
- `SHLWAPI!PathCommonPrefixW` at `0x18002e82f`

## string_xrefs

- `0x18002e870`: `GetInvModuleInPath`

## pseudocode

```c
__int64 __fastcall GetInvModuleInPath(LPCWSTR pszFile2)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  int v5; // r8d
  DWORD ModuleFileNameW; // eax
  int v7; // eax
  __int64 v8; // rcx
  signed int v9; // eax
  HMODULE phModule; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(Filename, 0, 0x208u);
  phModule = 0;
  if ( !GetModuleHandleExW(6u, (LPCWSTR)GetInvModuleInPath, &phModule) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v4 = "GetModuleHandleEx failed %#x";
    v5 = 387;
LABEL_14:
    AslLogCallPrintf(1, (unsigned int)"GetInvModuleInPath", v5, (_DWORD)v4);
    return v3;
  }
  ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW >= 0x104 && GetLastError() == 122 )
  {
    v9 = GetLastError();
    v3 = v9;
    if ( v9 > 0 )
      v3 = (unsigned __int16)v9 | 0x80070000;
    v4 = "GetModuleFileName failed %#x";
    v5 = 396;
    goto LABEL_14;
  }
  v7 = PathCommonPrefixW(Filename, pszFile2, 0);
  v8 = -1;
  do
    ++v8;
  while ( pszFile2[v8] );
  return v7 != v8;
}

```

## disassembly

```asm
0x18002e780  mov     [rsp+arg_8], rbx
0x18002e785  push    rdi
0x18002e786  sub     rsp, 260h
0x18002e78d  mov     rax, cs:__security_cookie
0x18002e794  xor     rax, rsp
0x18002e797  mov     [rsp+268h+var_18], rax
0x18002e79f  mov     rbx, rcx
0x18002e7a2  xor     edx, edx; Val
0x18002e7a4  lea     rcx, [rsp+268h+Filename]; void *
0x18002e7a9  mov     r8d, 208h; Size
0x18002e7af  call    memset_0
0x18002e7b4  xor     edi, edi
0x18002e7b6  lea     r8, [rsp+268h+phModule]; phModule
0x18002e7bb  lea     rdx, ?GetInvModuleInPath@@YAJPEBG@Z; lpModuleName
0x18002e7c2  mov     [rsp+268h+phModule], rdi
0x18002e7c7  lea     ecx, [rdi+6]; dwFlags
0x18002e7ca  call    cs:__imp_GetModuleHandleExW
0x18002e7d0  test    eax, eax
0x18002e7d2  jnz     short loc_18002E7F8
0x18002e7d4  call    cs:__imp_GetLastError
0x18002e7da  mov     ebx, eax
0x18002e7dc  test    eax, eax
0x18002e7de  jle     short loc_18002E7E9
0x18002e7e0  movzx   ebx, ax
0x18002e7e3  or      ebx, 80070000h
0x18002e7e9  lea     r9, aGetmodulehandl; "GetModuleHandleEx failed %#x"
0x18002e7f0  mov     r8d, 183h
0x18002e7f6  jmp     short loc_18002E870
0x18002e7f8  mov     rcx, [rsp+268h+phModule]; hModule
0x18002e7fd  lea     rdx, [rsp+268h+Filename]; lpFilename
0x18002e802  mov     r8d, 104h; nSize
0x18002e808  call    cs:__imp_GetModuleFileNameW
0x18002e80e  test    eax, eax
0x18002e810  jz      short loc_18002E84E
0x18002e812  cmp     eax, 104h
0x18002e817  jb      short loc_18002E824
0x18002e819  call    cs:__imp_GetLastError
0x18002e81f  cmp     eax, 7Ah ; 'z'
0x18002e822  jz      short loc_18002E84E
0x18002e824  xor     r8d, r8d; achPath
0x18002e827  lea     rcx, [rsp+268h+Filename]; pszFile1
0x18002e82c  mov     rdx, rbx; pszFile2
0x18002e82f  call    cs:__imp_PathCommonPrefixW
0x18002e835  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002e839  inc     rcx
0x18002e83c  cmp     [rbx+rcx*2], di
0x18002e840  jnz     short loc_18002E839
0x18002e842  mov     eax, eax
0x18002e844  mov     ebx, edi
0x18002e846  cmp     rax, rcx
0x18002e849  setnz   bl
0x18002e84c  jmp     short loc_18002E885
0x18002e84e  call    cs:__imp_GetLastError
0x18002e854  mov     ebx, eax
0x18002e856  test    eax, eax
0x18002e858  jle     short loc_18002E863
0x18002e85a  movzx   ebx, ax
0x18002e85d  or      ebx, 80070000h
0x18002e863  lea     r9, aGetmodulefilen; "GetModuleFileName failed %#x"
0x18002e86a  mov     r8d, 18Ch
0x18002e870  lea     rdx, aGetinvmodulein_0; "GetInvModuleInPath"
0x18002e877  mov     [rsp+268h+var_248], ebx
0x18002e87b  mov     ecx, 1
0x18002e880  call    AslLogCallPrintf
0x18002e885  mov     eax, ebx
0x18002e887  mov     rcx, [rsp+268h+var_18]
0x18002e88f  xor     rcx, rsp; StackCookie
0x18002e892  call    __security_check_cookie
0x18002e897  mov     rbx, [rsp+268h+arg_8]
0x18002e89f  add     rsp, 260h
0x18002e8a6  pop     rdi
0x18002e8a7  retn
```
