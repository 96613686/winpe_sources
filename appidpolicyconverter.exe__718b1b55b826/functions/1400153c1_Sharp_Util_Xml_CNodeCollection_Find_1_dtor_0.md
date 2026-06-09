# _Sharp::Util::Xml::CNodeCollection::Find_::_1_::dtor$0

- ea: `0x1400153c1`
- end: `0x1400153e7`
- name: `_Sharp::Util::Xml::CNodeCollection::Find_::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14001377c`
- `0x1400153c1`

## pseudocode

```c
void __fastcall Sharp::Util::Xml::CNodeCollection::Find_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    Sharp::Util::Xml::CNodeCollection::~CNodeCollection(*(Sharp::Util::Xml::CNodeCollection **)(a2 + 40));
  }
}

```

## disassembly

```asm
0x1400153c1  push    rbp
0x1400153c3  sub     rsp, 20h
0x1400153c7  mov     rbp, rdx
0x1400153ca  mov     eax, [rbp+20h]
0x1400153cd  and     eax, 1
0x1400153d0  test    eax, eax
0x1400153d2  jz      short loc_1400153E1
0x1400153d4  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x1400153d8  mov     rcx, [rbp+28h]; this
0x1400153dc  call    ??1CNodeCollection@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNodeCollection::~CNodeCollection(void)
0x1400153e1  add     rsp, 20h
0x1400153e5  pop     rbp
0x1400153e6  retn
```
