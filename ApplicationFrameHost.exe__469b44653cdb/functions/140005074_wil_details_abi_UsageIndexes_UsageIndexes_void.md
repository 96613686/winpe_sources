# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140005074`
- end: `0x1400050a6`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140004fa0`
- `0x14000740c`
- `0x140007924`
- `0x14000a527`

## callees

- `0x140002c70`

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
0x140005074  push    rbx
0x140005076  sub     rsp, 20h
0x14000507a  mov     rbx, rcx
0x14000507d  xor     edx, edx
0x14000507f  add     rcx, 0B0h
0x140005086  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x14000508b  lea     rcx, [rbx+70h]
0x14000508f  xor     edx, edx
0x140005091  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x140005096  lea     rcx, [rbx+30h]
0x14000509a  xor     edx, edx
0x14000509c  add     rsp, 20h
0x1400050a0  pop     rbx
0x1400050a1  jmp     ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
```
