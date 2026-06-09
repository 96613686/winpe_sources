# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180008e30`
- end: `0x180008e6e`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `62`
- prototype: `ATL::CComModule *__fastcall(ATL::CComModule *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001744`
- `0x180008e30`
- `0x180010154`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(ATL::CComModule *this, char a2)
{
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::Term(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008e30  mov     [rsp+arg_0], rbx
0x180008e35  push    rdi
0x180008e36  sub     rsp, 20h
0x180008e3a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180008e41  mov     ebx, edx
0x180008e43  mov     [rcx], rax
0x180008e46  mov     rdi, rcx
0x180008e49  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x180008e4e  test    bl, 1
0x180008e51  jz      short loc_180008E60
0x180008e53  mov     edx, 50h ; 'P'
0x180008e58  mov     rcx, rdi; Block
0x180008e5b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008e60  mov     rbx, [rsp+28h+arg_0]
0x180008e65  mov     rax, rdi
0x180008e68  add     rsp, 20h
0x180008e6c  pop     rdi
0x180008e6d  retn
```
