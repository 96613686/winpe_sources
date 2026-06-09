# _Sharp::Util::Xml::CNode::GetChilds_::_1_::dtor$2

- ea: `0x1400151bd`
- end: `0x1400151e3`
- name: `_Sharp::Util::Xml::CNode::GetChilds_::_1_::dtor$2`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14001377c`
- `0x1400151bd`

## pseudocode

```c
void __fastcall Sharp::Util::Xml::CNode::GetChilds_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    Sharp::Util::Xml::CNodeCollection::~CNodeCollection(*(Sharp::Util::Xml::CNodeCollection **)(a2 + 56));
  }
}

```

## disassembly

```asm
0x1400151bd  push    rbp
0x1400151bf  sub     rsp, 20h
0x1400151c3  mov     rbp, rdx
0x1400151c6  mov     eax, [rbp+20h]
0x1400151c9  and     eax, 1
0x1400151cc  test    eax, eax
0x1400151ce  jz      short loc_1400151DD
0x1400151d0  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x1400151d4  mov     rcx, [rbp+38h]; this
0x1400151d8  call    ??1CNodeCollection@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNodeCollection::~CNodeCollection(void)
0x1400151dd  add     rsp, 20h
0x1400151e1  pop     rbp
0x1400151e2  retn
```
