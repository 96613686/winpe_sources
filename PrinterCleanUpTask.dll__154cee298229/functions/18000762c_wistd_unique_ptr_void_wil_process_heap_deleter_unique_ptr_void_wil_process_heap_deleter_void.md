# wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)

- ea: `0x18000762c`
- end: `0x180007633`
- name: `??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z`
- size: `7`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c930`
- `0x18000dba0`
- `0x18000dd60`
- `0x18000f660`
- `0x18000f6d0`
- `0x18001323c`

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
0x18000762c  mov     [rcx], rdx
0x18000762f  mov     rax, rcx
0x180007632  retn
```
