# __dcrt_write_console

- ea: `0x18003f724`
- end: `0x18003f7d8`
- name: `__dcrt_write_console`
- size: `180`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003ebe4`

## callees

- `0x18003f724`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003f75a`
- `KERNEL32!GetLastError` at `0x18003f75a`
- `KERNEL32!CloseHandle` at `0x18003f772`
- `KERNEL32!CloseHandle` at `0x18003f772`
- `KERNEL32!CreateFileW` at `0x18003f7a3`
- `KERNEL32!CreateFileW` at `0x18003f7a3`
- `KERNEL32!WriteConsoleW` at `0x18003f74e`
- `KERNEL32!WriteConsoleW` at `0x18003f7c5`
- `KERNEL32!WriteConsoleW` at `0x18003f74e`
- `KERNEL32!WriteConsoleW` at `0x18003f7c5`

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
0x18003f724  push    rbx
0x18003f726  push    rbp
0x18003f727  push    rsi
0x18003f728  push    rdi
0x18003f729  sub     rsp, 48h
0x18003f72d  mov     rdi, r8
0x18003f730  mov     [rsp+68h+lpReserved], 0; lpReserved
0x18003f739  mov     r9, r8; lpNumberOfCharsWritten
0x18003f73c  mov     esi, edx
0x18003f73e  mov     r8d, edx; nNumberOfCharsToWrite
0x18003f741  mov     rbp, rcx
0x18003f744  mov     rdx, rcx; lpBuffer
0x18003f747  mov     rcx, cs:hObject; hConsoleOutput
0x18003f74e  call    cs:__imp_WriteConsoleW
0x18003f754  mov     ebx, eax
0x18003f756  test    eax, eax
0x18003f758  jnz     short loc_18003F7CD
0x18003f75a  call    cs:__imp_GetLastError
0x18003f760  cmp     eax, 6
0x18003f763  jnz     short loc_18003F7CD
0x18003f765  mov     rcx, cs:hObject; hObject
0x18003f76c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18003f770  ja      short loc_18003F778
0x18003f772  call    cs:__imp_CloseHandle
0x18003f778  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18003f781  lea     rcx, FileName; "CONOUT$"
0x18003f788  mov     r8d, 3; dwShareMode
0x18003f78e  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18003f796  xor     r9d, r9d; lpSecurityAttributes
0x18003f799  mov     dword ptr [rsp+68h+lpReserved], r8d; dwCreationDisposition
0x18003f79e  mov     edx, 40000000h; dwDesiredAccess
0x18003f7a3  call    cs:__imp_CreateFileW
0x18003f7a9  mov     r9, rdi; lpNumberOfCharsWritten
0x18003f7ac  mov     [rsp+68h+lpReserved], 0; lpReserved
0x18003f7b5  mov     rcx, rax; hConsoleOutput
0x18003f7b8  mov     cs:hObject, rax
0x18003f7bf  mov     r8d, esi; nNumberOfCharsToWrite
0x18003f7c2  mov     rdx, rbp; lpBuffer
0x18003f7c5  call    cs:__imp_WriteConsoleW
0x18003f7cb  mov     ebx, eax
0x18003f7cd  mov     eax, ebx
0x18003f7cf  add     rsp, 48h
0x18003f7d3  pop     rdi
0x18003f7d4  pop     rsi
0x18003f7d5  pop     rbp
0x18003f7d6  pop     rbx
0x18003f7d7  retn
```
