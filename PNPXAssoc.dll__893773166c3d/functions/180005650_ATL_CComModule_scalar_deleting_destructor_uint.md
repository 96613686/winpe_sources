# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180005650`
- end: `0x180005689`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `57`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800019b0`
- `0x180005650`
- `0x1800087c8`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(ATL::CComModule *this, unsigned int a2)
{
  char v2; // bl

  v2 = a2;
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::Term(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005650  mov     [rsp+arg_0], rbx
0x180005655  push    rdi
0x180005656  sub     rsp, 20h
0x18000565a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180005661  mov     ebx, edx
0x180005663  mov     [rcx], rax
0x180005666  mov     rdi, rcx
0x180005669  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000566e  test    bl, 1
0x180005671  jz      short loc_18000567B
0x180005673  mov     rcx, rdi; Block
0x180005676  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000567b  mov     rbx, [rsp+28h+arg_0]
0x180005680  mov     rax, rdi
0x180005683  add     rsp, 20h
0x180005687  pop     rdi
0x180005688  retn
```
