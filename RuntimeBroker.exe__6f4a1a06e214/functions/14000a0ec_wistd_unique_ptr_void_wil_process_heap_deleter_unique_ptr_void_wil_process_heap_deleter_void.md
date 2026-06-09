# wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)

- ea: `0x14000a0ec`
- end: `0x14000a0f3`
- name: `??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140008668`
- `0x1400087cc`

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
0x14000a0ec  mov     [rcx], rdx
0x14000a0ef  mov     rax, rcx
0x14000a0f2  retn
```
