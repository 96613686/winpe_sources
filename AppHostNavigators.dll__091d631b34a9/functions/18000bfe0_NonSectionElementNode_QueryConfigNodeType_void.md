# NonSectionElementNode::QueryConfigNodeType(void)

- ea: `0x18000bfe0`
- end: `0x18000bff5`
- name: `?QueryConfigNodeType@NonSectionElementNode@@UEAA?AV?$NamedEnum@W4ConfigNodeType@@@@XZ`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x18000bfe0`: `ConfigNodeType_Element`

## pseudocode

```c
__int64 __fastcall NonSectionElementNode::QueryConfigNodeType(__int64 a1, __int64 a2)
{
  *(_DWORD *)a2 = 4;
  *(_QWORD *)(a2 + 8) = L"ConfigNodeType_Element";
  return a2;
}

```

## disassembly

```asm
0x18000bfe0  lea     rax, aConfignodetype_0; "ConfigNodeType_Element"
0x18000bfe7  mov     dword ptr [rdx], 4
0x18000bfed  mov     [rdx+8], rax
0x18000bff1  mov     rax, rdx
0x18000bff4  retn
```
