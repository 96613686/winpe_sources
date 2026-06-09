# avpriv_slicethread_create

- ea: `0x18002292a`
- end: `0x180022930`
- name: `avpriv_slicethread_create`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180011c5c`

## import_xrefs

- `avutil_ms!avpriv_slicethread_create` at `0x18002292a`

## pseudocode

```c
// attributes: thunk
__int64 avpriv_slicethread_create()
{
  return __imp_avpriv_slicethread_create();
}

```

## disassembly

```asm
0x18002292a  jmp     cs:__imp_avpriv_slicethread_create
```
