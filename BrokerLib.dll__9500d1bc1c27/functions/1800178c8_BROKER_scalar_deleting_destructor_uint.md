# _BROKER::`scalar deleting destructor'(uint)

- ea: `0x1800178c8`
- end: `0x1800178f5`
- name: `??_G_BROKER@@QEAAPEAXI@Z`
- size: `45`
- prototype: `void *__fastcall(_BROKER *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001364c`
- `0x18001d8a9`

## callees

- `0x180004ae0`
- `0x180015b58`
- `0x1800178c8`

## pseudocode

```c
_BROKER *__fastcall _BROKER::`scalar deleting destructor'(_BROKER *this)
{
  std::_Ref_count_base *v2; // rcx

  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 3);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800178c8  push    rbx
0x1800178ca  sub     rsp, 20h
0x1800178ce  mov     rbx, rcx
0x1800178d1  mov     rcx, [rcx+18h]; this
0x1800178d5  test    rcx, rcx
0x1800178d8  jz      short loc_1800178DF
0x1800178da  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800178df  mov     edx, 20h ; ' '; unsigned __int64
0x1800178e4  mov     rcx, rbx; void *
0x1800178e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800178ec  mov     rax, rbx
0x1800178ef  add     rsp, 20h
0x1800178f3  pop     rbx
0x1800178f4  retn
```
