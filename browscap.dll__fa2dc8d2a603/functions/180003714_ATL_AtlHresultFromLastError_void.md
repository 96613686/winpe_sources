# ATL::AtlHresultFromLastError(void)

- ea: `0x180003714`
- end: `0x18000372f`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800050c0`
- `0x18000672c`
- `0x180006b14`

## callees

- `0x180003714`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003718`
- `KERNEL32!GetLastError` at `0x180003718`

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
0x180003714  sub     rsp, 28h
0x180003718  call    cs:__imp_GetLastError
0x18000371e  test    eax, eax
0x180003720  jle     short loc_18000372A
0x180003722  movzx   eax, ax
0x180003725  or      eax, 80070000h
0x18000372a  add     rsp, 28h
0x18000372e  retn
```
