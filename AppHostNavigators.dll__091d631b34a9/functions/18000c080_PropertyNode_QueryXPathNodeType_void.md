# PropertyNode::QueryXPathNodeType(void)

- ea: `0x18000c080`
- end: `0x18000c095`
- name: `?QueryXPathNodeType@PropertyNode@@UEAA?AV?$NamedEnum@W4XPathNodeType@@@@XZ`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x18000c080`: `XPathNodeType_Attribute`

## pseudocode

```c
__int64 __fastcall PropertyNode::QueryXPathNodeType(__int64 a1, __int64 a2)
{
  *(_DWORD *)a2 = 2;
  *(_QWORD *)(a2 + 8) = L"XPathNodeType_Attribute";
  return a2;
}

```

## disassembly

```asm
0x18000c080  lea     rax, aXpathnodetypeA; "XPathNodeType_Attribute"
0x18000c087  mov     dword ptr [rdx], 2
0x18000c08d  mov     [rdx+8], rax
0x18000c091  mov     rax, rdx
0x18000c094  retn
```
