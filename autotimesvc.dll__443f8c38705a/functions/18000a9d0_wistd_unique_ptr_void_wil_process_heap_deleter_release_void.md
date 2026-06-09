# wistd::unique_ptr<void,wil::process_heap_deleter>::release(void)

- ea: `0x18000a9d0`
- end: `0x18000a9db`
- name: `?release@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAPEAXXZ`
- size: `11`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180007e70`

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
0x18000a9d0  mov     rax, [rcx]
0x18000a9d3  mov     qword ptr [rcx], 0
0x18000a9da  retn
```
