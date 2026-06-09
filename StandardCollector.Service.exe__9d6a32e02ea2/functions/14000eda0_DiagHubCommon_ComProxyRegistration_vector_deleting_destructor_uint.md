# DiagHubCommon::ComProxyRegistration::`vector deleting destructor'(uint)

- ea: `0x14000eda0`
- end: `0x14000edcb`
- name: `??_EComProxyRegistration@DiagHubCommon@@UEAAPEAXI@Z`
- size: `43`
- prototype: `DiagHubCommon::ComProxyRegistration *__fastcall(DiagHubCommon::ComProxyRegistration *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000eda0`
- `0x14001382c`

## pseudocode

```c
DiagHubCommon::ComProxyRegistration *__fastcall DiagHubCommon::ComProxyRegistration::`vector deleting destructor'(
        DiagHubCommon::ComProxyRegistration *this,
        char a2)
{
  *(_QWORD *)this = &DiagHubCommon::ComProxyRegistration::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000eda0  push    rbx
0x14000eda2  sub     rsp, 20h
0x14000eda6  lea     rax, ??_7ComProxyRegistration@DiagHubCommon@@6B@; const DiagHubCommon::ComProxyRegistration::`vftable'
0x14000edad  mov     rbx, rcx
0x14000edb0  mov     [rcx], rax
0x14000edb3  test    dl, 1
0x14000edb6  jz      short loc_14000EDC2
0x14000edb8  mov     edx, 8
0x14000edbd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000edc2  mov     rax, rbx
0x14000edc5  add     rsp, 20h
0x14000edc9  pop     rbx
0x14000edca  retn
```
