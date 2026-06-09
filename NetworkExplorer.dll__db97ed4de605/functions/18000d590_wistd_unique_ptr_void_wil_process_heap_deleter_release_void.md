# wistd::unique_ptr<void,wil::process_heap_deleter>::release(void)

- ea: `0x18000d590`
- end: `0x18000d59b`
- name: `?release@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAPEAXXZ`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a60c`

## pseudocode

```c
__int64 __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::release(__int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000d590  mov     rax, [rcx]
0x18000d593  mov     qword ptr [rcx], 0
0x18000d59a  retn
```
