# _PrintCore::CreateXpsBitmapProvider_::_1_::dtor$3

- ea: `0x1800106cd`
- end: `0x1800106ed`
- name: `_PrintCore::CreateXpsBitmapProvider_::_1_::dtor$3`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001b30`

## pseudocode

```c
void __fastcall PrintCore::CreateXpsBitmapProvider_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 128));
}

```

## disassembly

```asm
0x1800106cd  push    rbp
0x1800106cf  sub     rsp, 20h
0x1800106d3  mov     rbp, rdx
0x1800106d6  mov     edx, 78h ; 'x'; unsigned __int64
0x1800106db  mov     rcx, [rbp+80h]; void *
0x1800106e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800106e7  add     rsp, 20h
0x1800106eb  pop     rbp
0x1800106ec  retn
```
