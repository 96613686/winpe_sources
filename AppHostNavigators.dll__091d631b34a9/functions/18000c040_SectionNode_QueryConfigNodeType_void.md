# SectionNode::QueryConfigNodeType(void)

- ea: `0x18000c040`
- end: `0x18000c055`
- name: `?QueryConfigNodeType@SectionNode@@UEAA?AV?$NamedEnum@W4ConfigNodeType@@@@XZ`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x18000c040`: `ConfigNodeType_Section`

## pseudocode

```c
__int64 __fastcall SectionNode::QueryConfigNodeType(__int64 a1, __int64 a2)
{
  *(_DWORD *)a2 = 3;
  *(_QWORD *)(a2 + 8) = L"ConfigNodeType_Section";
  return a2;
}

```

## disassembly

```asm
0x18000c040  lea     rax, aConfignodetype; "ConfigNodeType_Section"
0x18000c047  mov     dword ptr [rdx], 3
0x18000c04d  mov     [rdx+8], rax
0x18000c051  mov     rax, rdx
0x18000c054  retn
```
