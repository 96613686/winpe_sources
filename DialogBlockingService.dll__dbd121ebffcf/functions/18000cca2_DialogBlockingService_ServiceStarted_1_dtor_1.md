# _DialogBlockingService::ServiceStarted_::_1_::dtor$1

- ea: `0x18000cca2`
- end: `0x18000ccbf`
- name: `_DialogBlockingService::ServiceStarted_::_1_::dtor$1`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task`

## callees

- `0x180001644`

## pseudocode

```c
void __fastcall DialogBlockingService::ServiceStarted_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 56));
}

```

## disassembly

```asm
0x18000cca2  push    rbp
0x18000cca4  sub     rsp, 20h
0x18000cca8  mov     rbp, rdx
0x18000ccab  mov     edx, 60h ; '`'; unsigned __int64
0x18000ccb0  mov     rcx, [rbp+38h]; void *
0x18000ccb4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ccb9  add     rsp, 20h
0x18000ccbd  pop     rbp
0x18000ccbe  retn
```
