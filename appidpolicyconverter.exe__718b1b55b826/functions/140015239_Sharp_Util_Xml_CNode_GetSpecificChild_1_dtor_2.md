# _Sharp::Util::Xml::CNode::GetSpecificChild_::_1_::dtor$2

- ea: `0x140015239`
- end: `0x14001525f`
- name: `_Sharp::Util::Xml::CNode::GetSpecificChild_::_1_::dtor$2`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140012138`
- `0x140015239`

## pseudocode

```c
void __fastcall Sharp::Util::Xml::CNode::GetSpecificChild_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    Sharp::Util::Xml::CNode::~CNode(*(Sharp::Util::Xml::CNode **)(a2 + 48));
  }
}

```

## disassembly

```asm
0x140015239  push    rbp
0x14001523b  sub     rsp, 20h
0x14001523f  mov     rbp, rdx
0x140015242  mov     eax, [rbp+20h]
0x140015245  and     eax, 1
0x140015248  test    eax, eax
0x14001524a  jz      short loc_140015259
0x14001524c  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x140015250  mov     rcx, [rbp+30h]; this
0x140015254  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x140015259  add     rsp, 20h
0x14001525d  pop     rbp
0x14001525e  retn
```
