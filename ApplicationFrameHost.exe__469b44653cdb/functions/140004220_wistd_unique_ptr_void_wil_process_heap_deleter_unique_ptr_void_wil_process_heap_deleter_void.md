# wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)

- ea: `0x140004220`
- end: `0x140004227`
- name: `??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140006e0c`
- `0x140006f70`

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
0x140004220  mov     [rcx], rdx
0x140004223  mov     rax, rcx
0x140004226  retn
```
