# wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)

- ea: `0x18000f308`
- end: `0x18000f30f`
- name: `??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z`
- size: `7`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180010b38`

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
0x18000f308  mov     [rcx], rdx
0x18000f30b  mov     rax, rcx
0x18000f30e  retn
```
