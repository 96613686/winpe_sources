# PropertyNode::QueryConfigNodeType(void)

- ea: `0x18000c000`
- end: `0x18000c015`
- name: `?QueryConfigNodeType@PropertyNode@@UEAA?AV?$NamedEnum@W4ConfigNodeType@@@@XZ`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x18000c000`: `ConfigNodeType_Property`

## pseudocode

```c
__int64 __fastcall PropertyNode::QueryConfigNodeType(__int64 a1, __int64 a2)
{
  *(_DWORD *)a2 = 5;
  *(_QWORD *)(a2 + 8) = L"ConfigNodeType_Property";
  return a2;
}

```

## disassembly

```asm
0x18000c000  lea     rax, aConfignodetype_2; "ConfigNodeType_Property"
0x18000c007  mov     dword ptr [rdx], 5
0x18000c00d  mov     [rdx+8], rax
0x18000c011  mov     rax, rdx
0x18000c014  retn
```
