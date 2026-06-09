# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x180001e00`
- end: `0x180001e40`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAPEAXI@Z`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001e00`
- `0x18000ce0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_DWORD *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(_DWORD *a1, char a2)
{
  *(_QWORD *)a1 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180001e00  mov     [rsp+arg_0], rcx
0x180001e05  push    rbx
0x180001e06  sub     rsp, 20h
0x180001e0a  mov     rbx, rcx
0x180001e0d  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180001e14  mov     [rcx], rax
0x180001e17  mov     dword ptr [rcx+8], 0C0000001h
0x180001e1e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180001e25  mov     [rcx], rax
0x180001e28  test    dl, 1
0x180001e2b  jz      short loc_180001E37
0x180001e2d  mov     edx, 18h
0x180001e32  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001e37  mov     rax, rbx
0x180001e3a  add     rsp, 20h
0x180001e3e  pop     rbx
0x180001e3f  retn
```
