# SectionGroupNode::QueryConfigNodeType(void)

- ea: `0x18000c020`
- end: `0x18000c035`
- name: `?QueryConfigNodeType@SectionGroupNode@@UEAA?AV?$NamedEnum@W4ConfigNodeType@@@@XZ`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x18000c020`: `ConfigNodeType_SectionGroup`

## pseudocode

```c
__int64 __fastcall SectionGroupNode::QueryConfigNodeType(__int64 a1, __int64 a2)
{
  *(_DWORD *)a2 = 2;
  *(_QWORD *)(a2 + 8) = L"ConfigNodeType_SectionGroup";
  return a2;
}

```

## disassembly

```asm
0x18000c020  lea     rax, aConfignodetype_3; "ConfigNodeType_SectionGroup"
0x18000c027  mov     dword ptr [rdx], 2
0x18000c02d  mov     [rdx+8], rax
0x18000c031  mov     rax, rdx
0x18000c034  retn
```
