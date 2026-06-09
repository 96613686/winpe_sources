# ATL::AtlHresultFromLastError(void)

- ea: `0x180003a98`
- end: `0x180003ab3`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ad4`
- `0x180005588`
- `0x18000633c`
- `0x1800065d0`

## callees

- `0x180003a98`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003a9c`
- `KERNEL32!GetLastError` at `0x180003a9c`

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
0x180003a98  sub     rsp, 28h
0x180003a9c  call    cs:__imp_GetLastError
0x180003aa2  test    eax, eax
0x180003aa4  jle     short loc_180003AAE
0x180003aa6  movzx   eax, ax
0x180003aa9  or      eax, 80070000h
0x180003aae  add     rsp, 28h
0x180003ab2  retn
```
