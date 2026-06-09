# __dcrt_write_console

- ea: `0x18001a6ac`
- end: `0x18001a76a`
- name: `__dcrt_write_console`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180019c84`

## callees

- `0x18001a6ac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001a6e9`
- `KERNEL32!GetLastError` at `0x18001a6e9`
- `KERNEL32!CloseHandle` at `0x18001a701`
- `KERNEL32!CloseHandle` at `0x18001a701`
- `KERNEL32!CreateFileW` at `0x18001a72c`
- `KERNEL32!CreateFileW` at `0x18001a72c`
- `KERNEL32!WriteConsoleW` at `0x18001a6dd`
- `KERNEL32!WriteConsoleW` at `0x18001a74b`
- `KERNEL32!WriteConsoleW` at `0x18001a6dd`
- `KERNEL32!WriteConsoleW` at `0x18001a74b`

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
0x18001a6ac  mov     rax, rsp
0x18001a6af  mov     [rax+8], rbx
0x18001a6b3  mov     [rax+10h], rbp
0x18001a6b7  mov     [rax+18h], rsi
0x18001a6bb  push    rdi
0x18001a6bc  sub     rsp, 40h
0x18001a6c0  and     qword ptr [rax-28h], 0
0x18001a6c5  mov     rdi, r8
0x18001a6c8  mov     r9, r8; lpNumberOfCharsWritten
0x18001a6cb  mov     esi, edx
0x18001a6cd  mov     r8d, edx; nNumberOfCharsToWrite
0x18001a6d0  mov     rbp, rcx
0x18001a6d3  mov     rdx, rcx; lpBuffer
0x18001a6d6  mov     rcx, cs:hObject; hConsoleOutput
0x18001a6dd  call    cs:__imp_WriteConsoleW
0x18001a6e3  mov     ebx, eax
0x18001a6e5  test    eax, eax
0x18001a6e7  jnz     short loc_18001A753
0x18001a6e9  call    cs:__imp_GetLastError
0x18001a6ef  cmp     eax, 6
0x18001a6f2  jnz     short loc_18001A753
0x18001a6f4  mov     rcx, cs:hObject; hObject
0x18001a6fb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001a6ff  ja      short loc_18001A707
0x18001a701  call    cs:__imp_CloseHandle
0x18001a707  and     [rsp+48h+var_18], 0
0x18001a70d  lea     rcx, FileName; "CONOUT$"
0x18001a714  and     [rsp+48h+var_20], 0
0x18001a719  mov     r8d, 3; dwShareMode
0x18001a71f  xor     r9d, r9d; lpSecurityAttributes
0x18001a722  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x18001a727  mov     edx, 40000000h; dwDesiredAccess
0x18001a72c  call    cs:__imp_CreateFileW
0x18001a732  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x18001a738  mov     r9, rdi; lpNumberOfCharsWritten
0x18001a73b  mov     rcx, rax; hConsoleOutput
0x18001a73e  mov     cs:hObject, rax
0x18001a745  mov     r8d, esi; nNumberOfCharsToWrite
0x18001a748  mov     rdx, rbp; lpBuffer
0x18001a74b  call    cs:__imp_WriteConsoleW
0x18001a751  mov     ebx, eax
0x18001a753  mov     rbp, [rsp+48h+arg_8]
0x18001a758  mov     eax, ebx
0x18001a75a  mov     rbx, [rsp+48h+arg_0]
0x18001a75f  mov     rsi, [rsp+48h+arg_10]
0x18001a764  add     rsp, 40h
0x18001a768  pop     rdi
0x18001a769  retn
```
