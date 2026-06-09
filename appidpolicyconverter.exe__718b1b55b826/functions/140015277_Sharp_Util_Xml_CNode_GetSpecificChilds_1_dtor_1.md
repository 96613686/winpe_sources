# _Sharp::Util::Xml::CNode::GetSpecificChilds_::_1_::dtor$1

- ea: `0x140015277`
- end: `0x14001529d`
- name: `_Sharp::Util::Xml::CNode::GetSpecificChilds_::_1_::dtor$1`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14001377c`
- `0x140015277`

## pseudocode

```c
void __fastcall Sharp::Util::Xml::CNode::GetSpecificChilds_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    Sharp::Util::Xml::CNodeCollection::~CNodeCollection(*(Sharp::Util::Xml::CNodeCollection **)(a2 + 88));
  }
}

```

## disassembly

```asm
0x140015277  push    rbp
0x140015279  sub     rsp, 20h
0x14001527d  mov     rbp, rdx
0x140015280  mov     eax, [rbp+20h]
0x140015283  and     eax, 1
0x140015286  test    eax, eax
0x140015288  jz      short loc_140015297
0x14001528a  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x14001528e  mov     rcx, [rbp+58h]; this
0x140015292  call    ??1CNodeCollection@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNodeCollection::~CNodeCollection(void)
0x140015297  add     rsp, 20h
0x14001529b  pop     rbp
0x14001529c  retn
```
