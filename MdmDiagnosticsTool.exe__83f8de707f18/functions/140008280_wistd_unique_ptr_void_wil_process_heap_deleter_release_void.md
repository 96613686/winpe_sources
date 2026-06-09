# wistd::unique_ptr<void,wil::process_heap_deleter>::release(void)

- ea: `0x140008280`
- end: `0x14000828b`
- name: `?release@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAPEAXXZ`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140005934`

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
0x140008280  mov     rax, [rcx]
0x140008283  mov     qword ptr [rcx], 0
0x14000828a  retn
```
