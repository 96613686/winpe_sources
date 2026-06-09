# _o___std_exception_copy_0

- ea: `0x1800034e6`
- end: `0x1800034ec`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180005190`
- `0x180008650`
- `0x1800086a0`
- `0x1800086f0`
- `0x180009a44`
- `0x180009c18`
- `0x180011f3c`
- `0x180012114`
- `0x180012158`
- `0x1800121b4`
- `0x180018a50`
- `0x1800226f0`
- `0x180022748`
- `0x180022830`
- `0x180022a60`
- `0x180022aa4`
- `0x180022b04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800034e6`

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
0x1800034e6  jmp     cs:__imp__o___std_exception_copy
```
