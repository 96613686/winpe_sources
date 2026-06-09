# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x1800026f0`
- end: `0x18000272a`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `58`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800026f0`
- `0x1800064c0`

## import_xrefs

- `msvcrt!free` at `0x180002716`
- `msvcrt!free` at `0x180002716`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(ATL::CComModule *this, unsigned int a2)
{
  char v2; // bl

  v2 = a2;
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::Term(this, a2);
  if ( (v2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x1800026f0  mov     [rsp+arg_0], rbx
0x1800026f5  push    rdi
0x1800026f6  sub     rsp, 20h
0x1800026fa  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180002701  mov     ebx, edx
0x180002703  mov     [rcx], rax
0x180002706  mov     rdi, rcx
0x180002709  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000270e  test    bl, 1
0x180002711  jz      short loc_18000271C
0x180002713  mov     rcx, rdi; Block
0x180002716  call    cs:__imp_free
0x18000271c  mov     rbx, [rsp+28h+arg_0]
0x180002721  mov     rax, rdi
0x180002724  add     rsp, 20h
0x180002728  pop     rdi
0x180002729  retn
```
