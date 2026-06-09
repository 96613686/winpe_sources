# wistd::unique_ptr<void,wil::process_heap_deleter>::release(void)

- ea: `0x18001168c`
- end: `0x180011697`
- name: `?release@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAPEAXXZ`
- size: `11`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180010b38`

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
0x18001168c  mov     rax, [rcx]
0x18001168f  mov     qword ptr [rcx], 0
0x180011696  retn
```
