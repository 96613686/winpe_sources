# unknown_libname_43

- ea: `0x100202d6`
- end: `0x1002032b`
- name: `unknown_libname_43`
- size: `85`
- prototype: `int __cdecl(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1001edbd`

## callees

- `0x10020281`
- `0x100202bf`
- `0x100202d6`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100202f9`
- `KERNEL32!GetLastError` at `0x100202f9`
- `KERNEL32!WriteConsoleW` at `0x100202ed`
- `KERNEL32!WriteConsoleW` at `0x1002031e`
- `KERNEL32!WriteConsoleW` at `0x100202ed`
- `KERNEL32!WriteConsoleW` at `0x1002031e`

## pseudocode

```c
// Microsoft VisualC universal runtime
BOOL __cdecl unknown_libname_43(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
{
  BOOL v3; // esi

  v3 = WriteConsoleW(hConsoleOutput, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  if ( !v3 && GetLastError() == 6 )
  {
    unknown_libname_42();
    __dcrt_lowio_initialize_console_output();
    return WriteConsoleW(hConsoleOutput, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x100202d6  mov     edi, edi
0x100202d8  push    ebp
0x100202d9  mov     ebp, esp
0x100202db  push    esi
0x100202dc  push    0; lpReserved
0x100202de  push    [ebp+lpNumberOfCharsWritten]; lpNumberOfCharsWritten
0x100202e1  push    [ebp+nNumberOfCharsToWrite]; nNumberOfCharsToWrite
0x100202e4  push    [ebp+lpBuffer]; lpBuffer
0x100202e7  push    hConsoleOutput; hConsoleOutput
0x100202ed  call    ds:WriteConsoleW
0x100202f3  mov     esi, eax
0x100202f5  test    esi, esi
0x100202f7  jnz     short loc_10020326
0x100202f9  call    ds:GetLastError
0x100202ff  cmp     eax, 6
0x10020302  jnz     short loc_10020326
0x10020304  call    unknown_libname_42; Microsoft VisualC universal runtime
0x10020309  call    ?__dcrt_lowio_initialize_console_output@@YAXXZ
0x1002030e  push    esi; lpReserved
0x1002030f  push    [ebp+lpNumberOfCharsWritten]; lpNumberOfCharsWritten
0x10020312  push    [ebp+nNumberOfCharsToWrite]; nNumberOfCharsToWrite
0x10020315  push    [ebp+lpBuffer]; lpBuffer
0x10020318  push    hConsoleOutput; hConsoleOutput
0x1002031e  call    ds:WriteConsoleW
0x10020324  mov     esi, eax
0x10020326  mov     eax, esi
0x10020328  pop     esi
0x10020329  pop     ebp
0x1002032a  retn
```
