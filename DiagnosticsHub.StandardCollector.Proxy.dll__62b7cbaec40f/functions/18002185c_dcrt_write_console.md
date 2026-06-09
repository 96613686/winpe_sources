# __dcrt_write_console

- ea: `0x18002185c`
- end: `0x18002191a`
- name: `__dcrt_write_console`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001c7f8`

## callees

- `0x18002185c`

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x18002188d`
- `KERNEL32!WriteConsoleW` at `0x1800218fb`
- `KERNEL32!WriteConsoleW` at `0x18002188d`
- `KERNEL32!WriteConsoleW` at `0x1800218fb`
- `KERNEL32!CloseHandle` at `0x1800218b1`
- `KERNEL32!CloseHandle` at `0x1800218b1`
- `KERNEL32!CreateFileW` at `0x1800218dc`
- `KERNEL32!CreateFileW` at `0x1800218dc`
- `KERNEL32!GetLastError` at `0x180021899`
- `KERNEL32!GetLastError` at `0x180021899`

## pseudocode

```c
__int64 __fastcall _dcrt_write_console(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
{
  unsigned int v6; // ebx

  v6 = WriteConsoleW(hObject, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  if ( !v6 && GetLastError() == 6 )
  {
    if ( (unsigned __int64)hObject <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject);
    hObject = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
    return WriteConsoleW(hObject, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x18002185c  mov     rax, rsp
0x18002185f  mov     [rax+8], rbx
0x180021863  mov     [rax+10h], rbp
0x180021867  mov     [rax+18h], rsi
0x18002186b  push    rdi
0x18002186c  sub     rsp, 40h
0x180021870  and     qword ptr [rax-28h], 0
0x180021875  mov     rdi, r8
0x180021878  mov     r9, r8; lpNumberOfCharsWritten
0x18002187b  mov     esi, edx
0x18002187d  mov     r8d, edx; nNumberOfCharsToWrite
0x180021880  mov     rbp, rcx
0x180021883  mov     rdx, rcx; lpBuffer
0x180021886  mov     rcx, cs:hObject; hConsoleOutput
0x18002188d  call    cs:__imp_WriteConsoleW
0x180021893  mov     ebx, eax
0x180021895  test    eax, eax
0x180021897  jnz     short loc_180021903
0x180021899  call    cs:__imp_GetLastError
0x18002189f  cmp     eax, 6
0x1800218a2  jnz     short loc_180021903
0x1800218a4  mov     rcx, cs:hObject; hObject
0x1800218ab  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800218af  ja      short loc_1800218B7
0x1800218b1  call    cs:__imp_CloseHandle
0x1800218b7  and     [rsp+48h+var_18], 0
0x1800218bd  lea     rcx, FileName; "CONOUT$"
0x1800218c4  and     [rsp+48h+var_20], 0
0x1800218c9  mov     r8d, 3; dwShareMode
0x1800218cf  xor     r9d, r9d; lpSecurityAttributes
0x1800218d2  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x1800218d7  mov     edx, 40000000h; dwDesiredAccess
0x1800218dc  call    cs:__imp_CreateFileW
0x1800218e2  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x1800218e8  mov     r9, rdi; lpNumberOfCharsWritten
0x1800218eb  mov     rcx, rax; hConsoleOutput
0x1800218ee  mov     cs:hObject, rax
0x1800218f5  mov     r8d, esi; nNumberOfCharsToWrite
0x1800218f8  mov     rdx, rbp; lpBuffer
0x1800218fb  call    cs:__imp_WriteConsoleW
0x180021901  mov     ebx, eax
0x180021903  mov     rbp, [rsp+48h+arg_8]
0x180021908  mov     eax, ebx
0x18002190a  mov     rbx, [rsp+48h+arg_0]
0x18002190f  mov     rsi, [rsp+48h+arg_10]
0x180021914  add     rsp, 40h
0x180021918  pop     rdi
0x180021919  retn
```
