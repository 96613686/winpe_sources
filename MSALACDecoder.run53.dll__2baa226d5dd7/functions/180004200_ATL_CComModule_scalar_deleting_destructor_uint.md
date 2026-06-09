# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180004200`
- end: `0x18000423e`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001574`
- `0x180004200`
- `0x180006acc`

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
0x180004200  mov     [rsp+arg_0], rbx
0x180004205  push    rdi
0x180004206  sub     rsp, 20h
0x18000420a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180004211  mov     ebx, edx
0x180004213  mov     [rcx], rax
0x180004216  mov     rdi, rcx
0x180004219  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000421e  test    bl, 1
0x180004221  jz      short loc_180004230
0x180004223  mov     edx, 50h ; 'P'
0x180004228  mov     rcx, rdi; Block
0x18000422b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004230  mov     rbx, [rsp+28h+arg_0]
0x180004235  mov     rax, rdi
0x180004238  add     rsp, 20h
0x18000423c  pop     rdi
0x18000423d  retn
```
