# _Sharp::Util::Xml::CDocument::GetRootNode_::_1_::dtor$2

- ea: `0x140015015`
- end: `0x14001503b`
- name: `_Sharp::Util::Xml::CDocument::GetRootNode_::_1_::dtor$2`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140012138`
- `0x140015015`

## pseudocode

```c
void __fastcall Sharp::Util::Xml::CDocument::GetRootNode_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    Sharp::Util::Xml::CNode::~CNode(*(Sharp::Util::Xml::CNode **)(a2 + 56));
  }
}

```

## disassembly

```asm
0x140015015  push    rbp
0x140015017  sub     rsp, 20h
0x14001501b  mov     rbp, rdx
0x14001501e  mov     eax, [rbp+20h]
0x140015021  and     eax, 1
0x140015024  test    eax, eax
0x140015026  jz      short loc_140015035
0x140015028  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x14001502c  mov     rcx, [rbp+38h]; this
0x140015030  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x140015035  add     rsp, 20h
0x140015039  pop     rbp
0x14001503a  retn
```
