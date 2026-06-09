# _CThread::Create_::_1_::dtor$0

- ea: `0x18000a4a5`
- end: `0x18000a4c2`
- name: `_CThread::Create_::_1_::dtor$0`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800019e0`

## pseudocode

```c
void __fastcall CThread::Create_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x18000a4a5  push    rbp
0x18000a4a7  sub     rsp, 20h
0x18000a4ab  mov     rbp, rdx
0x18000a4ae  mov     edx, 80h; unsigned __int64
0x18000a4b3  mov     rcx, [rbp+40h]; void *
0x18000a4b7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a4bc  add     rsp, 20h
0x18000a4c0  pop     rbp
0x18000a4c1  retn
```
