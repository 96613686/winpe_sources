# __dcrt_write_console

- ea: `0x14007790c`
- end: `0x1400779ca`
- name: `__dcrt_write_console`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140075e70`

## callees

- `0x14007790c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14007798c`
- `KERNEL32!CreateFileW` at `0x14007798c`
- `KERNEL32!CloseHandle` at `0x140077961`
- `KERNEL32!CloseHandle` at `0x140077961`
- `KERNEL32!GetLastError` at `0x140077949`
- `KERNEL32!GetLastError` at `0x140077949`
- `KERNEL32!WriteConsoleW` at `0x14007793d`
- `KERNEL32!WriteConsoleW` at `0x1400779ab`
- `KERNEL32!WriteConsoleW` at `0x14007793d`
- `KERNEL32!WriteConsoleW` at `0x1400779ab`

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
0x14007790c  mov     rax, rsp
0x14007790f  mov     [rax+8], rbx
0x140077913  mov     [rax+10h], rbp
0x140077917  mov     [rax+18h], rsi
0x14007791b  push    rdi
0x14007791c  sub     rsp, 40h
0x140077920  and     qword ptr [rax-28h], 0
0x140077925  mov     rdi, r8
0x140077928  mov     r9, r8; lpNumberOfCharsWritten
0x14007792b  mov     esi, edx
0x14007792d  mov     r8d, edx; nNumberOfCharsToWrite
0x140077930  mov     rbp, rcx
0x140077933  mov     rdx, rcx; lpBuffer
0x140077936  mov     rcx, cs:hObject; hConsoleOutput
0x14007793d  call    cs:__imp_WriteConsoleW
0x140077943  mov     ebx, eax
0x140077945  test    eax, eax
0x140077947  jnz     short loc_1400779B3
0x140077949  call    cs:__imp_GetLastError
0x14007794f  cmp     eax, 6
0x140077952  jnz     short loc_1400779B3
0x140077954  mov     rcx, cs:hObject; hObject
0x14007795b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14007795f  ja      short loc_140077967
0x140077961  call    cs:__imp_CloseHandle
0x140077967  and     [rsp+48h+var_18], 0
0x14007796d  lea     rcx, aConout
0x140077974  and     [rsp+48h+var_20], 0
0x140077979  mov     r8d, 3; dwShareMode
0x14007797f  xor     r9d, r9d; lpSecurityAttributes
0x140077982  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x140077987  mov     edx, 40000000h; dwDesiredAccess
0x14007798c  call    cs:__imp_CreateFileW
0x140077992  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x140077998  mov     r9, rdi; lpNumberOfCharsWritten
0x14007799b  mov     rcx, rax; hConsoleOutput
0x14007799e  mov     cs:hObject, rax
0x1400779a5  mov     r8d, esi; nNumberOfCharsToWrite
0x1400779a8  mov     rdx, rbp; lpBuffer
0x1400779ab  call    cs:__imp_WriteConsoleW
0x1400779b1  mov     ebx, eax
0x1400779b3  mov     rbp, [rsp+48h+arg_8]
0x1400779b8  mov     eax, ebx
0x1400779ba  mov     rbx, [rsp+48h+arg_0]
0x1400779bf  mov     rsi, [rsp+48h+arg_10]
0x1400779c4  add     rsp, 40h
0x1400779c8  pop     rdi
0x1400779c9  retn
```
