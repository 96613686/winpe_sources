# ATL::CSecurityDesc::`scalar deleting destructor'(uint)

- ea: `0x140009480`
- end: `0x1400094be`
- name: `??_GCSecurityDesc@ATL@@UEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(ATL::CSecurityDesc *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140009480`
- `0x1400094c0`
- `0x14001382c`

## pseudocode

```c
ATL::CSecurityDesc *__fastcall ATL::CSecurityDesc::`scalar deleting destructor'(ATL::CSecurityDesc *this, char a2)
{
  *(_QWORD *)this = &ATL::CSecurityDesc::`vftable';
  ATL::CSecurityDesc::Clear(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140009480  mov     [rsp+arg_0], rbx
0x140009485  push    rdi
0x140009486  sub     rsp, 20h
0x14000948a  lea     rax, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x140009491  mov     ebx, edx
0x140009493  mov     [rcx], rax
0x140009496  mov     rdi, rcx
0x140009499  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x14000949e  test    bl, 1
0x1400094a1  jz      short loc_1400094B0
0x1400094a3  mov     edx, 10h
0x1400094a8  mov     rcx, rdi; Block
0x1400094ab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400094b0  mov     rbx, [rsp+28h+arg_0]
0x1400094b5  mov     rax, rdi
0x1400094b8  add     rsp, 20h
0x1400094bc  pop     rdi
0x1400094bd  retn
```
