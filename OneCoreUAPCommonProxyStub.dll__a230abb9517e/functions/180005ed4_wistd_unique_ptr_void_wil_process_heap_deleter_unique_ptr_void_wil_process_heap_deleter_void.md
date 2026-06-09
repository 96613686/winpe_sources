# wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)

- ea: `0x180005ed4`
- end: `0x180005edb`
- name: `??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800087d8`

## pseudocode

```c
_QWORD *__fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
        _QWORD *a1,
        __int64 a2)
{
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x180005ed4  mov     [rcx], rdx
0x180005ed7  mov     rax, rcx
0x180005eda  retn
```
