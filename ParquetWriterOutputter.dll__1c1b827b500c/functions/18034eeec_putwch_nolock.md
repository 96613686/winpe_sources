# _putwch_nolock

- ea: `0x18034eeec`
- end: `0x18034ef45`
- name: `_putwch_nolock`
- size: `89`
- prototype: `wint_t __cdecl(wchar_t Character)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18033ca10`

## callees

- `0x18034eeec`
- `0x18035746c`

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x18034ef31`
- `KERNEL32!WriteConsoleW` at `0x18034ef31`

## pseudocode

```c
wint_t __cdecl putwch_nolock(wchar_t Character)
{
  HANDLE v1; // rcx
  wint_t Buffer; // [rsp+40h] [rbp+8h] BYREF
  DWORD NumberOfCharsWritten; // [rsp+48h] [rbp+10h] BYREF

  Buffer = Character;
  v1 = _dcrt_lowio_console_output_handle;
  if ( _dcrt_lowio_console_output_handle == (HANDLE)-2LL )
  {
    _dcrt_lowio_initialize_console_output();
    v1 = _dcrt_lowio_console_output_handle;
  }
  if ( v1 == (HANDLE)-1LL || !WriteConsoleW(v1, &Buffer, 1u, &NumberOfCharsWritten, 0) )
    return -1;
  else
    return Buffer;
}

```

## disassembly

```asm
0x18034eeec  mov     [rsp+Buffer], cx
0x18034eef1  sub     rsp, 38h
0x18034eef5  mov     rcx, cs:__dcrt_lowio_console_output_handle
0x18034eefc  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x18034ef00  jnz     short loc_18034EF0E
0x18034ef02  call    __dcrt_lowio_initialize_console_output
0x18034ef07  mov     rcx, cs:__dcrt_lowio_console_output_handle; hConsoleOutput
0x18034ef0e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18034ef12  jnz     short loc_18034EF1B
0x18034ef14  mov     eax, 0FFFFh
0x18034ef19  jmp     short loc_18034EF40
0x18034ef1b  and     [rsp+38h+var_18], 0
0x18034ef21  lea     r9, [rsp+38h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x18034ef26  mov     r8d, 1; nNumberOfCharsToWrite
0x18034ef2c  lea     rdx, [rsp+38h+Buffer]; lpBuffer
0x18034ef31  call    cs:__imp_WriteConsoleW
0x18034ef37  test    eax, eax
0x18034ef39  jz      short loc_18034EF14
0x18034ef3b  movzx   eax, [rsp+38h+Buffer]
0x18034ef40  add     rsp, 38h
0x18034ef44  retn
```
