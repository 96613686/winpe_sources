# _Sharp::Util::Xml::CNode::CreateChild_::_1_::dtor$4

- ea: `0x14001517f`
- end: `0x1400151a5`
- name: `_Sharp::Util::Xml::CNode::CreateChild_::_1_::dtor$4`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140012138`
- `0x14001517f`

## pseudocode

```c
void __fastcall Sharp::Util::Xml::CNode::CreateChild_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 48) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    Sharp::Util::Xml::CNode::~CNode(*(Sharp::Util::Xml::CNode **)(a2 + 64));
  }
}

```

## disassembly

```asm
0x14001517f  push    rbp
0x140015181  sub     rsp, 20h
0x140015185  mov     rbp, rdx
0x140015188  mov     eax, [rbp+30h]
0x14001518b  and     eax, 1
0x14001518e  test    eax, eax
0x140015190  jz      short loc_14001519F
0x140015192  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x140015196  mov     rcx, [rbp+40h]; this
0x14001519a  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14001519f  add     rsp, 20h
0x1400151a3  pop     rbp
0x1400151a4  retn
```
