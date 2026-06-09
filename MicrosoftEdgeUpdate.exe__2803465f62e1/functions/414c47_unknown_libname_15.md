# unknown_libname_15

- ea: `0x414c47`
- end: `0x414c9c`
- name: `unknown_libname_15`
- size: `85`
- prototype: `BOOL __cdecl(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x41468a`

## callees

- `0x414bf1`
- `0x414c30`
- `0x414c47`

## import_xrefs

- `KERNEL32!GetLastError` at `0x414c6a`
- `KERNEL32!GetLastError` at `0x414c6a`
- `KERNEL32!WriteConsoleW` at `0x414c5e`
- `KERNEL32!WriteConsoleW` at `0x414c8f`
- `KERNEL32!WriteConsoleW` at `0x414c5e`
- `KERNEL32!WriteConsoleW` at `0x414c8f`

## pseudocode

```c
// Microsoft VisualC universal runtime
BOOL __cdecl unknown_libname_15(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
{
  BOOL v3; // esi

  v3 = WriteConsoleW(hConsoleOutput, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  if ( !v3 && GetLastError() == 6 )
  {
    unknown_libname_14();
    __dcrt_lowio_initialize_console_output();
    return WriteConsoleW(hConsoleOutput, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x414c47  mov     edi, edi
0x414c49  push    ebp
0x414c4a  mov     ebp, esp
0x414c4c  push    esi
0x414c4d  push    0; lpReserved
0x414c4f  push    [ebp+lpNumberOfCharsWritten]; lpNumberOfCharsWritten
0x414c52  push    [ebp+nNumberOfCharsToWrite]; nNumberOfCharsToWrite
0x414c55  push    [ebp+lpBuffer]; lpBuffer
0x414c58  push    hConsoleOutput; hConsoleOutput
0x414c5e  call    ds:WriteConsoleW
0x414c64  mov     esi, eax
0x414c66  test    esi, esi
0x414c68  jnz     short loc_414C97
0x414c6a  call    ds:GetLastError
0x414c70  cmp     eax, 6
0x414c73  jnz     short loc_414C97
0x414c75  call    unknown_libname_14; Microsoft VisualC universal runtime
0x414c7a  call    ?__dcrt_lowio_initialize_console_output@@YAXXZ
0x414c7f  push    esi; lpReserved
0x414c80  push    [ebp+lpNumberOfCharsWritten]; lpNumberOfCharsWritten
0x414c83  push    [ebp+nNumberOfCharsToWrite]; nNumberOfCharsToWrite
0x414c86  push    [ebp+lpBuffer]; lpBuffer
0x414c89  push    hConsoleOutput; hConsoleOutput
0x414c8f  call    ds:WriteConsoleW
0x414c95  mov     esi, eax
0x414c97  mov     eax, esi
0x414c99  pop     esi
0x414c9a  pop     ebp
0x414c9b  retn
```
