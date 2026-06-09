# avpriv_slicethread_free

- ea: `0x180022936`
- end: `0x18002293c`
- name: `avpriv_slicethread_free`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180011c34`

## import_xrefs

- `avutil_ms!avpriv_slicethread_free` at `0x180022936`

## pseudocode

```c
// attributes: thunk
__int64 avpriv_slicethread_free()
{
  return __imp_avpriv_slicethread_free();
}

```

## disassembly

```asm
0x180022936  jmp     cs:__imp_avpriv_slicethread_free
```
