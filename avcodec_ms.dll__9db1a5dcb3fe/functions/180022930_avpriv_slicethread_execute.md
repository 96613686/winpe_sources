# avpriv_slicethread_execute

- ea: `0x180022930`
- end: `0x180022936`
- name: `avpriv_slicethread_execute`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180011da0`

## import_xrefs

- `avutil_ms!avpriv_slicethread_execute` at `0x180022930`

## pseudocode

```c
// attributes: thunk
__int64 avpriv_slicethread_execute()
{
  return __imp_avpriv_slicethread_execute();
}

```

## disassembly

```asm
0x180022930  jmp     cs:__imp_avpriv_slicethread_execute
```
