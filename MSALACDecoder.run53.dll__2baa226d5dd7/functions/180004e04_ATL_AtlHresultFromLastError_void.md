# ATL::AtlHresultFromLastError(void)

- ea: `0x180004e04`
- end: `0x180004e1f`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e98`
- `0x180006bcc`
- `0x180006ef4`

## callees

- `0x180004e04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e08`

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
0x180004e04  sub     rsp, 28h
0x180004e08  call    cs:__imp_GetLastError
0x180004e0e  test    eax, eax
0x180004e10  jle     short loc_180004E1A
0x180004e12  movzx   eax, ax
0x180004e15  or      eax, 80070000h
0x180004e1a  add     rsp, 28h
0x180004e1e  retn
```
