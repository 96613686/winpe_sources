# unknown_libname_35

- ea: `0x41beb7`
- end: `0x41bf0c`
- name: `unknown_libname_35`
- size: `85`
- prototype: `BOOL __cdecl(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x41b258`

## callees

- `0x41be61`
- `0x41bea0`
- `0x41beb7`

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x41bece`
- `KERNEL32!WriteConsoleW` at `0x41beff`
- `KERNEL32!WriteConsoleW` at `0x41bece`
- `KERNEL32!WriteConsoleW` at `0x41beff`
- `KERNEL32!GetLastError` at `0x41beda`
- `KERNEL32!GetLastError` at `0x41beda`

## pseudocode

```c
// Microsoft VisualC universal runtime
BOOL __cdecl unknown_libname_35(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
{
  BOOL v3; // esi

  v3 = WriteConsoleW(hConsoleOutput, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  if ( !v3 && GetLastError() == 6 )
  {
    unknown_libname_34();
    __dcrt_lowio_initialize_console_output();
    return WriteConsoleW(hConsoleOutput, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x41beb7  mov     edi, edi
0x41beb9  push    ebp
0x41beba  mov     ebp, esp
0x41bebc  push    esi
0x41bebd  push    0; lpReserved
0x41bebf  push    [ebp+lpNumberOfCharsWritten]; lpNumberOfCharsWritten
0x41bec2  push    [ebp+nNumberOfCharsToWrite]; nNumberOfCharsToWrite
0x41bec5  push    [ebp+lpBuffer]; lpBuffer
0x41bec8  push    hConsoleOutput; hConsoleOutput
0x41bece  call    ds:WriteConsoleW
0x41bed4  mov     esi, eax
0x41bed6  test    esi, esi
0x41bed8  jnz     short loc_41BF07
0x41beda  call    ds:GetLastError
0x41bee0  cmp     eax, 6
0x41bee3  jnz     short loc_41BF07
0x41bee5  call    unknown_libname_34; Microsoft VisualC universal runtime
0x41beea  call    ?__dcrt_lowio_initialize_console_output@@YAXXZ
0x41beef  push    esi; lpReserved
0x41bef0  push    [ebp+lpNumberOfCharsWritten]; lpNumberOfCharsWritten
0x41bef3  push    [ebp+nNumberOfCharsToWrite]; nNumberOfCharsToWrite
0x41bef6  push    [ebp+lpBuffer]; lpBuffer
0x41bef9  push    hConsoleOutput; hConsoleOutput
0x41beff  call    ds:WriteConsoleW
0x41bf05  mov     esi, eax
0x41bf07  mov     eax, esi
0x41bf09  pop     esi
0x41bf0a  pop     ebp
0x41bf0b  retn
```
