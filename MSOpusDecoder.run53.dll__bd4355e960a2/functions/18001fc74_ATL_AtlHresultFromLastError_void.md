# ATL::AtlHresultFromLastError(void)

- ea: `0x18001fc74`
- end: `0x18001fc8f`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180021228`
- `0x180021f9c`
- `0x1800222c4`

## callees

- `0x18001fc74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc78`

## pseudocode

```c
signed int ATL::AtlHresultFromLastError(void)
{
  signed int result; // eax

  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001fc74  sub     rsp, 28h
0x18001fc78  call    cs:__imp_GetLastError
0x18001fc7e  test    eax, eax
0x18001fc80  jle     short loc_18001FC8A
0x18001fc82  movzx   eax, ax
0x18001fc85  or      eax, 80070000h
0x18001fc8a  add     rsp, 28h
0x18001fc8e  retn
```
