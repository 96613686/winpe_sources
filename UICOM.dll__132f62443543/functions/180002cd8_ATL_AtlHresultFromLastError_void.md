# ATL::AtlHresultFromLastError(void)

- ea: `0x180002cd8`
- end: `0x180002cf3`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d14`
- `0x180004038`
- `0x180004bac`

## callees

- `0x180002cd8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002cdc`
- `KERNEL32!GetLastError` at `0x180002cdc`

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
0x180002cd8  sub     rsp, 28h
0x180002cdc  call    cs:__imp_GetLastError
0x180002ce2  test    eax, eax
0x180002ce4  jle     short loc_180002CEE
0x180002ce6  movzx   eax, ax
0x180002ce9  or      eax, 80070000h
0x180002cee  add     rsp, 28h
0x180002cf2  retn
```
