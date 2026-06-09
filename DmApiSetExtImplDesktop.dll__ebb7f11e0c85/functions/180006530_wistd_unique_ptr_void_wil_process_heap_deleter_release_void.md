# wistd::unique_ptr<void,wil::process_heap_deleter>::release(void)

- ea: `0x180006530`
- end: `0x18000653b`
- name: `?release@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAPEAXXZ`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800046f4`

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
0x180006530  mov     rax, [rcx]
0x180006533  mov     qword ptr [rcx], 0
0x18000653a  retn
```
