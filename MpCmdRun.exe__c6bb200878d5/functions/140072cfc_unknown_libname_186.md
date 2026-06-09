# unknown_libname_186

- ea: `0x140072cfc`
- end: `0x140072dba`
- name: `unknown_libname_186`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14006be28`

## callees

- `0x140072cfc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140072d39`
- `KERNEL32!GetLastError` at `0x140072d39`
- `KERNEL32!CloseHandle` at `0x140072d51`
- `KERNEL32!CloseHandle` at `0x140072d51`
- `KERNEL32!CreateFileW` at `0x140072d7c`
- `KERNEL32!CreateFileW` at `0x140072d7c`
- `KERNEL32!WriteConsoleW` at `0x140072d2d`
- `KERNEL32!WriteConsoleW` at `0x140072d9b`
- `KERNEL32!WriteConsoleW` at `0x140072d2d`
- `KERNEL32!WriteConsoleW` at `0x140072d9b`

## pseudocode

```c
// Microsoft VisualC 64bit universal runtime
__int64 __fastcall unknown_libname_186(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
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
0x140072cfc  mov     rax, rsp
0x140072cff  mov     [rax+8], rbx
0x140072d03  mov     [rax+10h], rbp
0x140072d07  mov     [rax+18h], rsi
0x140072d0b  push    rdi
0x140072d0c  sub     rsp, 40h
0x140072d10  and     qword ptr [rax-28h], 0
0x140072d15  mov     rdi, r8
0x140072d18  mov     r9, r8; lpNumberOfCharsWritten
0x140072d1b  mov     esi, edx
0x140072d1d  mov     r8d, edx; nNumberOfCharsToWrite
0x140072d20  mov     rbp, rcx
0x140072d23  mov     rdx, rcx; lpBuffer
0x140072d26  mov     rcx, cs:hObject; hConsoleOutput
0x140072d2d  call    cs:WriteConsoleW
0x140072d33  mov     ebx, eax
0x140072d35  test    eax, eax
0x140072d37  jnz     short loc_140072DA3
0x140072d39  call    cs:GetLastError
0x140072d3f  cmp     eax, 6
0x140072d42  jnz     short loc_140072DA3
0x140072d44  mov     rcx, cs:hObject; hObject
0x140072d4b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140072d4f  ja      short loc_140072D57
0x140072d51  call    cs:__imp_CloseHandle
0x140072d57  and     [rsp+48h+var_18], 0
0x140072d5d  lea     rcx, FileName
0x140072d64  and     [rsp+48h+var_20], 0
0x140072d69  mov     r8d, 3; dwShareMode
0x140072d6f  xor     r9d, r9d; lpSecurityAttributes
0x140072d72  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x140072d77  mov     edx, 40000000h; dwDesiredAccess
0x140072d7c  call    cs:CreateFileW
0x140072d82  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x140072d88  mov     r9, rdi; lpNumberOfCharsWritten
0x140072d8b  mov     rcx, rax; hConsoleOutput
0x140072d8e  mov     cs:hObject, rax
0x140072d95  mov     r8d, esi; nNumberOfCharsToWrite
0x140072d98  mov     rdx, rbp; lpBuffer
0x140072d9b  call    cs:WriteConsoleW
0x140072da1  mov     ebx, eax
0x140072da3  mov     rbp, [rsp+48h+arg_8]
0x140072da8  mov     eax, ebx
0x140072daa  mov     rbx, [rsp+48h+arg_0]
0x140072daf  mov     rsi, [rsp+48h+arg_10]
0x140072db4  add     rsp, 40h
0x140072db8  pop     rdi
0x140072db9  retn
```
