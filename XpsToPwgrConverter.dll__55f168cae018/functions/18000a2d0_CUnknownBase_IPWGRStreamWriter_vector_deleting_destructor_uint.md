# CUnknownBase<IPWGRStreamWriter>::`vector deleting destructor'(uint)

- ea: `0x18000a2d0`
- end: `0x18000a2fb`
- name: `??_E?$CUnknownBase@UIPWGRStreamWriter@@@@UEAAPEAXI@Z`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001b30`
- `0x18000a2d0`

## pseudocode

```c
_QWORD *__fastcall CUnknownBase<IPWGRStreamWriter>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CUnknownBase<IPWGRStreamWriter>::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a2d0  push    rbx
0x18000a2d2  sub     rsp, 20h
0x18000a2d6  lea     rax, ??_7?$CUnknownBase@UIPWGRStreamWriter@@@@6B@; const CUnknownBase<IPWGRStreamWriter>::`vftable'
0x18000a2dd  mov     rbx, rcx
0x18000a2e0  mov     [rcx], rax
0x18000a2e3  test    dl, 1
0x18000a2e6  jz      short loc_18000A2F2
0x18000a2e8  mov     edx, 10h; unsigned __int64
0x18000a2ed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a2f2  mov     rax, rbx
0x18000a2f5  add     rsp, 20h
0x18000a2f9  pop     rbx
0x18000a2fa  retn
```
