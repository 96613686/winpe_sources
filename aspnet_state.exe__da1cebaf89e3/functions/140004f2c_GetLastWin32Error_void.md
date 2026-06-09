# GetLastWin32Error(void)

- ea: `0x140004f2c`
- end: `0x140004f55`
- name: `?GetLastWin32Error@@YAJXZ`
- size: `41`
- prototype: `__int64(void)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1400011ac`
- `0x140001a20`
- `0x140001c90`
- `0x140002200`
- `0x14000248c`
- `0x140002678`
- `0x140002704`
- `0x1400027ec`
- `0x140002840`
- `0x140003774`
- `0x140004e5c`

## callees

- `0x140004f2c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140004f30`
- `KERNEL32!GetLastError` at `0x140004f30`

## pseudocode

```c
__int64 GetLastWin32Error(void)
{
  signed int LastError; // ecx
  __int64 result; // rax

  LastError = GetLastError();
  if ( !LastError )
    return 2147500037LL;
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x140004f2c  sub     rsp, 28h
0x140004f30  call    cs:__imp_GetLastError
0x140004f36  mov     ecx, eax
0x140004f38  test    eax, eax
0x140004f3a  jz      short loc_140004F4B
0x140004f3c  movzx   eax, cx
0x140004f3f  or      eax, 80070000h
0x140004f44  test    ecx, ecx
0x140004f46  cmovle  eax, ecx
0x140004f49  jmp     short loc_140004F50
0x140004f4b  mov     eax, 80004005h
0x140004f50  add     rsp, 28h
0x140004f54  retn
```
