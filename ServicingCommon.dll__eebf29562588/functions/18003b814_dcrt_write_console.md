# __dcrt_write_console

- ea: `0x18003b814`
- end: `0x18003b8c8`
- name: `__dcrt_write_console`
- size: `180`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003acd4`

## callees

- `0x18003b814`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003b84a`
- `KERNEL32!GetLastError` at `0x18003b84a`
- `KERNEL32!CloseHandle` at `0x18003b862`
- `KERNEL32!CloseHandle` at `0x18003b862`
- `KERNEL32!CreateFileW` at `0x18003b893`
- `KERNEL32!CreateFileW` at `0x18003b893`
- `KERNEL32!WriteConsoleW` at `0x18003b83e`
- `KERNEL32!WriteConsoleW` at `0x18003b8b5`
- `KERNEL32!WriteConsoleW` at `0x18003b83e`
- `KERNEL32!WriteConsoleW` at `0x18003b8b5`

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
0x18003b814  push    rbx
0x18003b816  push    rbp
0x18003b817  push    rsi
0x18003b818  push    rdi
0x18003b819  sub     rsp, 48h
0x18003b81d  mov     rdi, r8
0x18003b820  mov     [rsp+68h+lpReserved], 0; lpReserved
0x18003b829  mov     r9, r8; lpNumberOfCharsWritten
0x18003b82c  mov     esi, edx
0x18003b82e  mov     r8d, edx; nNumberOfCharsToWrite
0x18003b831  mov     rbp, rcx
0x18003b834  mov     rdx, rcx; lpBuffer
0x18003b837  mov     rcx, cs:hObject; hConsoleOutput
0x18003b83e  call    cs:__imp_WriteConsoleW
0x18003b844  mov     ebx, eax
0x18003b846  test    eax, eax
0x18003b848  jnz     short loc_18003B8BD
0x18003b84a  call    cs:__imp_GetLastError
0x18003b850  cmp     eax, 6
0x18003b853  jnz     short loc_18003B8BD
0x18003b855  mov     rcx, cs:hObject; hObject
0x18003b85c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18003b860  ja      short loc_18003B868
0x18003b862  call    cs:__imp_CloseHandle
0x18003b868  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18003b871  lea     rcx, FileName; "CONOUT$"
0x18003b878  mov     r8d, 3; dwShareMode
0x18003b87e  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18003b886  xor     r9d, r9d; lpSecurityAttributes
0x18003b889  mov     dword ptr [rsp+68h+lpReserved], r8d; dwCreationDisposition
0x18003b88e  mov     edx, 40000000h; dwDesiredAccess
0x18003b893  call    cs:__imp_CreateFileW
0x18003b899  mov     r9, rdi; lpNumberOfCharsWritten
0x18003b89c  mov     [rsp+68h+lpReserved], 0; lpReserved
0x18003b8a5  mov     rcx, rax; hConsoleOutput
0x18003b8a8  mov     cs:hObject, rax
0x18003b8af  mov     r8d, esi; nNumberOfCharsToWrite
0x18003b8b2  mov     rdx, rbp; lpBuffer
0x18003b8b5  call    cs:__imp_WriteConsoleW
0x18003b8bb  mov     ebx, eax
0x18003b8bd  mov     eax, ebx
0x18003b8bf  add     rsp, 48h
0x18003b8c3  pop     rdi
0x18003b8c4  pop     rsi
0x18003b8c5  pop     rbp
0x18003b8c6  pop     rbx
0x18003b8c7  retn
```
