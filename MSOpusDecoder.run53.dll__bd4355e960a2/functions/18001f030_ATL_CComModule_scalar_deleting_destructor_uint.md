# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x18001f030`
- end: `0x18001f06e`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001914`
- `0x18001f030`
- `0x180021e9c`

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
0x18001f030  mov     [rsp+arg_0], rbx
0x18001f035  push    rdi
0x18001f036  sub     rsp, 20h
0x18001f03a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x18001f041  mov     ebx, edx
0x18001f043  mov     [rcx], rax
0x18001f046  mov     rdi, rcx
0x18001f049  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18001f04e  test    bl, 1
0x18001f051  jz      short loc_18001F060
0x18001f053  mov     edx, 50h ; 'P'
0x18001f058  mov     rcx, rdi; Block
0x18001f05b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f060  mov     rbx, [rsp+28h+arg_0]
0x18001f065  mov     rax, rdi
0x18001f068  add     rsp, 20h
0x18001f06c  pop     rdi
0x18001f06d  retn
```
