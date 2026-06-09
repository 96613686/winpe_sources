# ResultFromKnownLastError(void)

- ea: `0x1800034cc`
- end: `0x1800034f1`
- name: `?ResultFromKnownLastError@@YAJXZ`
- size: `37`
- prototype: `signed int(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034f8`
- `0x180003efc`
- `0x180009468`

## callees

- `0x1800034cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034d0`

## pseudocode

```c
signed int ResultFromKnownLastError(void)
{
  signed int result; // eax

  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x1800034cc  sub     rsp, 28h
0x1800034d0  call    cs:__imp_GetLastError
0x1800034d6  test    eax, eax
0x1800034d8  jle     short loc_1800034E2
0x1800034da  movzx   eax, ax
0x1800034dd  or      eax, 80070000h
0x1800034e2  test    eax, eax
0x1800034e4  mov     ecx, 80004005h
0x1800034e9  cmovns  eax, ecx
0x1800034ec  add     rsp, 28h
0x1800034f0  retn
```
