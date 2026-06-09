# TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryXPathNodeType(void)

- ea: `0x180005720`
- end: `0x180005735`
- name: `?QueryXPathNodeType@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@UEAA?AV?$NamedEnum@W4XPathNodeType@@@@XZ`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x180005720`: `XPathNodeType_Element`

## pseudocode

```c
__int64 __fastcall TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryXPathNodeType(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)a2 = 1;
  *(_QWORD *)(a2 + 8) = L"XPathNodeType_Element";
  return a2;
}

```

## disassembly

```asm
0x180005720  lea     rax, aXpathnodetypeE; "XPathNodeType_Element"
0x180005727  mov     dword ptr [rdx], 1
0x18000572d  mov     [rdx+8], rax
0x180005731  mov     rax, rdx
0x180005734  retn
```
