# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180003280`
- end: `0x1800032ba`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `58`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800030a4`
- `0x180003280`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800032a6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800032a6`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(
        ATL::CComModule *this,
        int a2,
        unsigned int a3)
{
  char v3; // bl

  v3 = a2;
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::~CAtlModule(this, a2, a3);
  if ( (v3 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003280  mov     [rsp+arg_0], rbx
0x180003285  push    rdi
0x180003286  sub     rsp, 20h
0x18000328a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180003291  mov     ebx, edx
0x180003293  mov     [rcx], rax
0x180003296  mov     rdi, rcx
0x180003299  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x18000329e  test    bl, 1
0x1800032a1  jz      short loc_1800032AC
0x1800032a3  mov     rcx, rdi
0x1800032a6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800032ac  mov     rbx, [rsp+28h+arg_0]
0x1800032b1  mov     rax, rdi
0x1800032b4  add     rsp, 20h
0x1800032b8  pop     rdi
0x1800032b9  retn
```
