# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180009698`
- end: `0x1800096ca`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ae28`
- `0x18000bf80`
- `0x18000d502`

## callees

- `0x180005950`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(void **this)
{
  wistd::unique_ptr<void,wil::process_heap_deleter>::reset(this + 22, 0);
  wistd::unique_ptr<void,wil::process_heap_deleter>::reset(this + 14, 0);
  wistd::unique_ptr<void,wil::process_heap_deleter>::reset(this + 6, 0);
}

```

## disassembly

```asm
0x180009698  push    rbx
0x18000969a  sub     rsp, 20h
0x18000969e  mov     rbx, rcx
0x1800096a1  xor     edx, edx
0x1800096a3  add     rcx, 0B0h
0x1800096aa  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x1800096af  lea     rcx, [rbx+70h]
0x1800096b3  xor     edx, edx
0x1800096b5  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x1800096ba  lea     rcx, [rbx+30h]
0x1800096be  xor     edx, edx
0x1800096c0  add     rsp, 20h
0x1800096c4  pop     rbx
0x1800096c5  jmp     ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
```
