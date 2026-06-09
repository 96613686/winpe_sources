# _o___std_exception_copy

- ea: `0x1800041a6`
- end: `0x1800041ac`
- name: `_o___std_exception_copy`
- size: `6`
- prototype: `__int64()`
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x1800069dc`
- `0x180006bb8`
- `0x180006bfc`
- `0x180006c68`
- `0x18000f1f8`
- `0x18000f3f0`
- `0x18000f444`
- `0x18000f4b0`
- `0x18000f6b4`
- `0x18000f714`
- `0x18001497c`
- `0x18001f7d4`
- `0x18001f828`
- `0x18001f8a4`
- `0x18001f904`
- `0x18002db3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800041a6`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x1800041a6  jmp     cs:__imp__o___std_exception_copy
```
