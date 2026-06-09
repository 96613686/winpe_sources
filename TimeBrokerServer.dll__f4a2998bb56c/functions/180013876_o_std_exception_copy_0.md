# _o___std_exception_copy_0

- ea: `0x180013876`
- end: `0x18001387c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000809c`
- `0x180008168`
- `0x18000a474`
- `0x18000ec10`
- `0x180011240`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180013876`

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
0x180013876  jmp     cs:__imp__o___std_exception_copy
```
