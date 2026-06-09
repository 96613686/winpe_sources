# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180002e20`
- end: `0x180002e5a`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `58`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002e20`
- `0x180006238`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002e46`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002e46`

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
0x180002e20  mov     [rsp+arg_0], rbx
0x180002e25  push    rdi
0x180002e26  sub     rsp, 20h
0x180002e2a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180002e31  mov     ebx, edx
0x180002e33  mov     [rcx], rax
0x180002e36  mov     rdi, rcx
0x180002e39  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x180002e3e  test    bl, 1
0x180002e41  jz      short loc_180002E4C
0x180002e43  mov     rcx, rdi
0x180002e46  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002e4c  mov     rbx, [rsp+28h+arg_0]
0x180002e51  mov     rax, rdi
0x180002e54  add     rsp, 20h
0x180002e58  pop     rdi
0x180002e59  retn
```
