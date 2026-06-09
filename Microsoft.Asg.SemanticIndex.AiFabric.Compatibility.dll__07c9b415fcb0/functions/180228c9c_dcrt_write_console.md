# __dcrt_write_console

- ea: `0x180228c9c`
- end: `0x180228d5a`
- name: `__dcrt_write_console`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1802285ec`

## callees

- `0x180228c9c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180228cd9`
- `KERNEL32!GetLastError` at `0x180228cd9`
- `KERNEL32!CloseHandle` at `0x180228cf1`
- `KERNEL32!CloseHandle` at `0x180228cf1`
- `KERNEL32!CreateFileW` at `0x180228d1c`
- `KERNEL32!CreateFileW` at `0x180228d1c`
- `KERNEL32!WriteConsoleW` at `0x180228ccd`
- `KERNEL32!WriteConsoleW` at `0x180228d3b`
- `KERNEL32!WriteConsoleW` at `0x180228ccd`
- `KERNEL32!WriteConsoleW` at `0x180228d3b`

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
0x180228c9c  mov     rax, rsp
0x180228c9f  mov     [rax+8], rbx
0x180228ca3  mov     [rax+10h], rbp
0x180228ca7  mov     [rax+18h], rsi
0x180228cab  push    rdi
0x180228cac  sub     rsp, 40h
0x180228cb0  and     qword ptr [rax-28h], 0
0x180228cb5  mov     rdi, r8
0x180228cb8  mov     r9, r8; lpNumberOfCharsWritten
0x180228cbb  mov     esi, edx
0x180228cbd  mov     r8d, edx; nNumberOfCharsToWrite
0x180228cc0  mov     rbp, rcx
0x180228cc3  mov     rdx, rcx; lpBuffer
0x180228cc6  mov     rcx, cs:hObject; hConsoleOutput
0x180228ccd  call    cs:__imp_WriteConsoleW
0x180228cd3  mov     ebx, eax
0x180228cd5  test    eax, eax
0x180228cd7  jnz     short loc_180228D43
0x180228cd9  call    cs:__imp_GetLastError
0x180228cdf  cmp     eax, 6
0x180228ce2  jnz     short loc_180228D43
0x180228ce4  mov     rcx, cs:hObject; hObject
0x180228ceb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180228cef  ja      short loc_180228CF7
0x180228cf1  call    cs:__imp_CloseHandle
0x180228cf7  and     [rsp+48h+var_18], 0
0x180228cfd  lea     rcx, aConout; "CONOUT$"
0x180228d04  and     [rsp+48h+var_20], 0
0x180228d09  mov     r8d, 3; dwShareMode
0x180228d0f  xor     r9d, r9d; lpSecurityAttributes
0x180228d12  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x180228d17  mov     edx, 40000000h; dwDesiredAccess
0x180228d1c  call    cs:__imp_CreateFileW
0x180228d22  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x180228d28  mov     r9, rdi; lpNumberOfCharsWritten
0x180228d2b  mov     rcx, rax; hConsoleOutput
0x180228d2e  mov     cs:hObject, rax
0x180228d35  mov     r8d, esi; nNumberOfCharsToWrite
0x180228d38  mov     rdx, rbp; lpBuffer
0x180228d3b  call    cs:__imp_WriteConsoleW
0x180228d41  mov     ebx, eax
0x180228d43  mov     rbp, [rsp+48h+arg_8]
0x180228d48  mov     eax, ebx
0x180228d4a  mov     rbx, [rsp+48h+arg_0]
0x180228d4f  mov     rsi, [rsp+48h+arg_10]
0x180228d54  add     rsp, 40h
0x180228d58  pop     rdi
0x180228d59  retn
```
