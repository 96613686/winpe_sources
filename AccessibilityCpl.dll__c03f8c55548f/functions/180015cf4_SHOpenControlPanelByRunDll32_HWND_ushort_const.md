# SHOpenControlPanelByRunDll32(HWND__ *,ushort const *)

- ea: `0x180015cf4`
- end: `0x180015dc8`
- name: `?SHOpenControlPanelByRunDll32@@YAJPEAUHWND__@@PEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800134a0`

## callees

- `0x180015cf4`
- `0x18001a6c0`
- `0x18002d1ee`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d90`
- `SHELL32!ShellExecuteExW` at `0x180015d86`
- `SHELL32!ShellExecuteExW` at `0x180015d86`

## string_xrefs

- `0x180015d31`: `%systemroot%\system32\rundll32.exe`
- `0x180015d45`: `shell32.dll,Control_RunDLL %s`

## pseudocode

```c
__int64 __fastcall SHOpenControlPanelByRunDll32(HWND a1, const unsigned __int16 *a2)
{
  int v4; // ebx
  signed int LastError; // eax
  SHELLEXECUTEINFOW pExecInfo; // [rsp+20h] [rbp-298h] BYREF
  unsigned __int16 v8[264]; // [rsp+90h] [rbp-228h] BYREF

  pExecInfo.cbSize = 112;
  memset_0(&pExecInfo.fMask, 0, 0x6Cu);
  pExecInfo.fMask = 768;
  pExecInfo.lpFile = L"%systemroot%\\system32\\rundll32.exe";
  pExecInfo.nShow = 1;
  pExecInfo.lpParameters = v8;
  v4 = StringCchPrintfW(v8, 0x104u, L"shell32.dll,Control_RunDLL %s", a2, *(_QWORD *)&pExecInfo.cbSize, a1);
  if ( v4 >= 0 && !ShellExecuteExW(&pExecInfo) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015cf4  mov     [rsp+arg_10], rbx
0x180015cf9  push    rdi
0x180015cfa  sub     rsp, 2B0h
0x180015d01  mov     rax, cs:__security_cookie
0x180015d08  xor     rax, rsp
0x180015d0b  mov     [rsp+2B8h+var_18], rax
0x180015d13  mov     rdi, rdx
0x180015d16  mov     [rsp+2B8h+pExecInfo.cbSize], 70h ; 'p'
0x180015d1e  xor     edx, edx; Val
0x180015d20  mov     rbx, rcx
0x180015d23  lea     rcx, [rsp+2B8h+pExecInfo.fMask]; void *
0x180015d28  lea     r8d, [rdx+6Ch]; Size
0x180015d2c  call    memset_0
0x180015d31  lea     rax, aSystemrootSyst_1; "%systemroot%\\system32\\rundll32.exe"
0x180015d38  mov     [rsp+2B8h+pExecInfo.fMask], 300h
0x180015d40  mov     [rsp+2B8h+pExecInfo.lpFile], rax
0x180015d45  lea     r8, aShell32DllCont; "shell32.dll,Control_RunDLL %s"
0x180015d4c  lea     rax, [rsp+2B8h+var_228]
0x180015d54  mov     [rsp+2B8h+pExecInfo.nShow], 1
0x180015d5c  mov     r9, rdi
0x180015d5f  mov     [rsp+2B8h+pExecInfo.lpParameters], rax
0x180015d64  mov     edx, 104h; unsigned __int64
0x180015d69  mov     [rsp+2B8h+pExecInfo.hwnd], rbx
0x180015d6e  lea     rcx, [rsp+2B8h+var_228]; unsigned __int16 *
0x180015d76  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015d7b  mov     ebx, eax
0x180015d7d  test    eax, eax
0x180015d7f  js      short loc_180015DA5
0x180015d81  lea     rcx, [rsp+2B8h+pExecInfo]; pExecInfo
0x180015d86  call    cs:__imp_ShellExecuteExW
0x180015d8c  test    eax, eax
0x180015d8e  jnz     short loc_180015DA5
0x180015d90  call    cs:__imp_GetLastError
0x180015d96  mov     ebx, eax
0x180015d98  test    eax, eax
0x180015d9a  jle     short loc_180015DA5
0x180015d9c  movzx   ebx, ax
0x180015d9f  or      ebx, 80070000h
0x180015da5  mov     eax, ebx
0x180015da7  mov     rcx, [rsp+2B8h+var_18]
0x180015daf  xor     rcx, rsp; StackCookie
0x180015db2  call    __security_check_cookie
0x180015db7  mov     rbx, [rsp+2B8h+arg_10]
0x180015dbf  add     rsp, 2B0h
0x180015dc6  pop     rdi
0x180015dc7  retn
```
