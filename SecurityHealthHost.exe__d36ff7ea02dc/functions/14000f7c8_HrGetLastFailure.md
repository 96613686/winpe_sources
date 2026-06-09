# HrGetLastFailure

- ea: `0x14000f7c8`
- end: `0x14000f7ed`
- name: `HrGetLastFailure`
- size: `37`
- prototype: `signed int()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d6f8`
- `0x14000d778`
- `0x14000d82c`
- `0x14000d89c`
- `0x14000da58`
- `0x14000daa8`
- `0x14000ee14`

## callees

- `0x14000f7c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f7cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f7cc`

## pseudocode

```c
signed int HrGetLastFailure()
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
0x14000f7c8  sub     rsp, 28h
0x14000f7cc  call    cs:__imp_GetLastError
0x14000f7d2  test    eax, eax
0x14000f7d4  jle     short loc_14000F7DE
0x14000f7d6  movzx   eax, ax
0x14000f7d9  or      eax, 80070000h
0x14000f7de  test    eax, eax
0x14000f7e0  mov     ecx, 80004005h
0x14000f7e5  cmovns  eax, ecx
0x14000f7e8  add     rsp, 28h
0x14000f7ec  retn
```
