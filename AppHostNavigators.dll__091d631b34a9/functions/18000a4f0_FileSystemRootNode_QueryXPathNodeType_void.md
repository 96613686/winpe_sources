# FileSystemRootNode::QueryXPathNodeType(void)

- ea: `0x18000a4f0`
- end: `0x18000a505`
- name: `?QueryXPathNodeType@FileSystemRootNode@@UEAA?AV?$NamedEnum@W4XPathNodeType@@@@XZ`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x18000a4f0`: `XPathNodeType_Root`

## pseudocode

```c
__int64 __fastcall FileSystemRootNode::QueryXPathNodeType(__int64 a1, __int64 a2)
{
  *(_DWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = L"XPathNodeType_Root";
  return a2;
}

```

## disassembly

```asm
0x18000a4f0  lea     rax, aXpathnodetypeR; "XPathNodeType_Root"
0x18000a4f7  mov     dword ptr [rdx], 0
0x18000a4fd  mov     [rdx+8], rax
0x18000a501  mov     rax, rdx
0x18000a504  retn
```
