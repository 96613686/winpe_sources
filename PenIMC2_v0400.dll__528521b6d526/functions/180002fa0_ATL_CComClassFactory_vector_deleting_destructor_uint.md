# ATL::CComClassFactory::`vector deleting destructor'(uint)

- ea: `0x180002fa0`
- end: `0x180002fcb`
- name: `??_ECComClassFactory@ATL@@UEAAPEAXI@Z`
- size: `43`
- prototype: `void *__fastcall(ATL::CComClassFactory *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002fa0`
- `0x18000ce0c`

## pseudocode

```c
ATL::CComClassFactory *__fastcall ATL::CComClassFactory::`vector deleting destructor'(
        ATL::CComClassFactory *this,
        char a2)
{
  *(_QWORD *)this = &ATL::CComClassFactory::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002fa0  push    rbx
0x180002fa2  sub     rsp, 20h
0x180002fa6  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180002fad  mov     rbx, rcx
0x180002fb0  mov     [rcx], rax
0x180002fb3  test    dl, 1
0x180002fb6  jz      short loc_180002FC2
0x180002fb8  mov     edx, 18h
0x180002fbd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002fc2  mov     rax, rbx
0x180002fc5  add     rsp, 20h
0x180002fc9  pop     rbx
0x180002fca  retn
```
