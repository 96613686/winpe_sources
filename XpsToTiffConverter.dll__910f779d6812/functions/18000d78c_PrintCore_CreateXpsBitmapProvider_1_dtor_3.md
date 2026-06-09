# _PrintCore::CreateXpsBitmapProvider_::_1_::dtor$3

- ea: `0x18000d78c`
- end: `0x18000d7ac`
- name: `_PrintCore::CreateXpsBitmapProvider_::_1_::dtor$3`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001a70`

## pseudocode

```c
void __fastcall PrintCore::CreateXpsBitmapProvider_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 128));
}

```

## disassembly

```asm
0x18000d78c  push    rbp
0x18000d78e  sub     rsp, 20h
0x18000d792  mov     rbp, rdx
0x18000d795  mov     edx, 78h ; 'x'; unsigned __int64
0x18000d79a  mov     rcx, [rbp+80h]; void *
0x18000d7a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d7a6  add     rsp, 20h
0x18000d7aa  pop     rbp
0x18000d7ab  retn
```
