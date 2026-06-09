# ATL::AtlHresultFromLastError(void)

- ea: `0x180004648`
- end: `0x180004663`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000766c`
- `0x180008c84`
- `0x180009250`

## callees

- `0x180004648`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000464c`
- `KERNEL32!GetLastError` at `0x18000464c`

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
0x180004648  sub     rsp, 28h
0x18000464c  call    cs:__imp_GetLastError
0x180004652  test    eax, eax
0x180004654  jle     short loc_18000465E
0x180004656  movzx   eax, ax
0x180004659  or      eax, 80070000h
0x18000465e  add     rsp, 28h
0x180004662  retn
```
