# __CxxSetUnhandledExceptionFilter

- ea: `0x140001370`
- end: `0x140001388`
- name: `__CxxSetUnhandledExceptionFilter`
- size: `24`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000137b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000137b`

## pseudocode

```c
__int64 _CxxSetUnhandledExceptionFilter()
{
  SetUnhandledExceptionFilter((LPTOP_LEVEL_EXCEPTION_FILTER)__CxxUnhandledExceptionFilter);
  return 0;
}

```

## disassembly

```asm
0x140001370  sub     rsp, 28h
0x140001374  lea     rcx, ?__CxxUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; lpTopLevelExceptionFilter
0x14000137b  call    cs:__imp_SetUnhandledExceptionFilter
0x140001381  xor     eax, eax
0x140001383  add     rsp, 28h
0x140001387  retn
```
