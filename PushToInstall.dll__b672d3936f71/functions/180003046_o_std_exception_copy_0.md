# _o___std_exception_copy_0

- ea: `0x180003046`
- end: `0x18000304c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180005d30`
- `0x18000c520`
- `0x18000c570`
- `0x18000c5c0`
- `0x18000c610`
- `0x18000eac8`
- `0x18000ebdc`
- `0x180021914`
- `0x180021980`
- `0x1800219c4`
- `0x180021a20`
- `0x180021a64`
- `0x18002df64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180003046`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x180003046  jmp     cs:__imp__o___std_exception_copy
```
