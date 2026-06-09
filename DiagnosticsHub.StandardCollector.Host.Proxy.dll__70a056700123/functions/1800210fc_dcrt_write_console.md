# __dcrt_write_console

- ea: `0x1800210fc`
- end: `0x1800211ba`
- name: `__dcrt_write_console`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001c098`

## callees

- `0x1800210fc`

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x18002112d`
- `KERNEL32!WriteConsoleW` at `0x18002119b`
- `KERNEL32!WriteConsoleW` at `0x18002112d`
- `KERNEL32!WriteConsoleW` at `0x18002119b`
- `KERNEL32!CloseHandle` at `0x180021151`
- `KERNEL32!CloseHandle` at `0x180021151`
- `KERNEL32!CreateFileW` at `0x18002117c`
- `KERNEL32!CreateFileW` at `0x18002117c`
- `KERNEL32!GetLastError` at `0x180021139`
- `KERNEL32!GetLastError` at `0x180021139`

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
0x1800210fc  mov     rax, rsp
0x1800210ff  mov     [rax+8], rbx
0x180021103  mov     [rax+10h], rbp
0x180021107  mov     [rax+18h], rsi
0x18002110b  push    rdi
0x18002110c  sub     rsp, 40h
0x180021110  and     qword ptr [rax-28h], 0
0x180021115  mov     rdi, r8
0x180021118  mov     r9, r8; lpNumberOfCharsWritten
0x18002111b  mov     esi, edx
0x18002111d  mov     r8d, edx; nNumberOfCharsToWrite
0x180021120  mov     rbp, rcx
0x180021123  mov     rdx, rcx; lpBuffer
0x180021126  mov     rcx, cs:hObject; hConsoleOutput
0x18002112d  call    cs:__imp_WriteConsoleW
0x180021133  mov     ebx, eax
0x180021135  test    eax, eax
0x180021137  jnz     short loc_1800211A3
0x180021139  call    cs:__imp_GetLastError
0x18002113f  cmp     eax, 6
0x180021142  jnz     short loc_1800211A3
0x180021144  mov     rcx, cs:hObject; hObject
0x18002114b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002114f  ja      short loc_180021157
0x180021151  call    cs:__imp_CloseHandle
0x180021157  and     [rsp+48h+var_18], 0
0x18002115d  lea     rcx, FileName; "CONOUT$"
0x180021164  and     [rsp+48h+var_20], 0
0x180021169  mov     r8d, 3; dwShareMode
0x18002116f  xor     r9d, r9d; lpSecurityAttributes
0x180021172  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x180021177  mov     edx, 40000000h; dwDesiredAccess
0x18002117c  call    cs:__imp_CreateFileW
0x180021182  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x180021188  mov     r9, rdi; lpNumberOfCharsWritten
0x18002118b  mov     rcx, rax; hConsoleOutput
0x18002118e  mov     cs:hObject, rax
0x180021195  mov     r8d, esi; nNumberOfCharsToWrite
0x180021198  mov     rdx, rbp; lpBuffer
0x18002119b  call    cs:__imp_WriteConsoleW
0x1800211a1  mov     ebx, eax
0x1800211a3  mov     rbp, [rsp+48h+arg_8]
0x1800211a8  mov     eax, ebx
0x1800211aa  mov     rbx, [rsp+48h+arg_0]
0x1800211af  mov     rsi, [rsp+48h+arg_10]
0x1800211b4  add     rsp, 40h
0x1800211b8  pop     rdi
0x1800211b9  retn
```
