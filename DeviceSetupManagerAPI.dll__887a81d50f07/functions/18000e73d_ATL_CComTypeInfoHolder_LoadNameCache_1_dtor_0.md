# _ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$0

- ea: `0x18000e73d`
- end: `0x18000e77b`
- name: `_ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$0`
- size: `62`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800017e4`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  is_mul_ok(*(_QWORD *)(a2 + 80), 0x10u);
  operator delete[](*(void **)(a2 + 88));
}

```

## disassembly

```asm
0x18000e73d  push    rbp
0x18000e73f  sub     rsp, 20h
0x18000e743  mov     rbp, rdx
0x18000e746  mov     eax, 10h
0x18000e74b  mul     qword ptr [rbp+50h]
0x18000e74f  mov     rdx, rax
0x18000e752  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000e759  cmovb   rdx, rax
0x18000e75d  add     rdx, 8
0x18000e761  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000e768  cmovb   rdx, rax; unsigned __int64
0x18000e76c  mov     rcx, [rbp+58h]; void *
0x18000e770  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x18000e775  add     rsp, 20h
0x18000e779  pop     rbp
0x18000e77a  retn
```
