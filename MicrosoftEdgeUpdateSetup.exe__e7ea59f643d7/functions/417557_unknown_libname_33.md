# unknown_libname_33

- ea: `0x417557`
- end: `0x4175ac`
- name: `unknown_libname_33`
- size: `85`
- prototype: `BOOL __cdecl(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x4168f8`

## callees

- `0x417501`
- `0x417540`
- `0x417557`

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x41756e`
- `KERNEL32!WriteConsoleW` at `0x41759f`
- `KERNEL32!WriteConsoleW` at `0x41756e`
- `KERNEL32!WriteConsoleW` at `0x41759f`
- `KERNEL32!GetLastError` at `0x41757a`
- `KERNEL32!GetLastError` at `0x41757a`

## pseudocode

```c
// Microsoft VisualC universal runtime
BOOL __cdecl unknown_libname_33(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
{
  BOOL v3; // esi

  v3 = WriteConsoleW(hConsoleOutput, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  if ( !v3 && GetLastError() == 6 )
  {
    unknown_libname_32();
    __dcrt_lowio_initialize_console_output();
    return WriteConsoleW(hConsoleOutput, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x417557  mov     edi, edi
0x417559  push    ebp
0x41755a  mov     ebp, esp
0x41755c  push    esi
0x41755d  push    0; lpReserved
0x41755f  push    [ebp+lpNumberOfCharsWritten]; lpNumberOfCharsWritten
0x417562  push    [ebp+nNumberOfCharsToWrite]; nNumberOfCharsToWrite
0x417565  push    [ebp+lpBuffer]; lpBuffer
0x417568  push    hConsoleOutput; hConsoleOutput
0x41756e  call    ds:WriteConsoleW
0x417574  mov     esi, eax
0x417576  test    esi, esi
0x417578  jnz     short loc_4175A7
0x41757a  call    ds:GetLastError
0x417580  cmp     eax, 6
0x417583  jnz     short loc_4175A7
0x417585  call    unknown_libname_32; Microsoft VisualC universal runtime
0x41758a  call    ?__dcrt_lowio_initialize_console_output@@YAXXZ
0x41758f  push    esi; lpReserved
0x417590  push    [ebp+lpNumberOfCharsWritten]; lpNumberOfCharsWritten
0x417593  push    [ebp+nNumberOfCharsToWrite]; nNumberOfCharsToWrite
0x417596  push    [ebp+lpBuffer]; lpBuffer
0x417599  push    hConsoleOutput; hConsoleOutput
0x41759f  call    ds:WriteConsoleW
0x4175a5  mov     esi, eax
0x4175a7  mov     eax, esi
0x4175a9  pop     esi
0x4175aa  pop     ebp
0x4175ab  retn
```
