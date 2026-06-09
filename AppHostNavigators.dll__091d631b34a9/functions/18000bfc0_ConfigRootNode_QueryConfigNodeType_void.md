# ConfigRootNode::QueryConfigNodeType(void)

- ea: `0x18000bfc0`
- end: `0x18000bfd5`
- name: `?QueryConfigNodeType@ConfigRootNode@@UEAA?AV?$NamedEnum@W4ConfigNodeType@@@@XZ`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x18000bfc0`: `ConfigNodeType_Root`

## pseudocode

```c
__int64 __fastcall ConfigRootNode::QueryConfigNodeType(__int64 a1, __int64 a2)
{
  *(_DWORD *)a2 = 1;
  *(_QWORD *)(a2 + 8) = L"ConfigNodeType_Root";
  return a2;
}

```

## disassembly

```asm
0x18000bfc0  lea     rax, aConfignodetype_1; "ConfigNodeType_Root"
0x18000bfc7  mov     dword ptr [rdx], 1
0x18000bfcd  mov     [rdx+8], rax
0x18000bfd1  mov     rax, rdx
0x18000bfd4  retn
```
