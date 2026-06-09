# ConfigLocationRootNode::QueryConfigLocationNodeType(void)

- ea: `0x18000a490`
- end: `0x18000a4a5`
- name: `?QueryConfigLocationNodeType@ConfigLocationRootNode@@UEAA?AV?$NamedEnum@W4ConfigLocationNodeType@@@@XZ`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x18000a490`: `ConfigLocationNodeType_Root`

## pseudocode

```c
__int64 __fastcall ConfigLocationRootNode::QueryConfigLocationNodeType(__int64 a1, __int64 a2)
{
  *(_DWORD *)a2 = 1;
  *(_QWORD *)(a2 + 8) = L"ConfigLocationNodeType_Root";
  return a2;
}

```

## disassembly

```asm
0x18000a490  lea     rax, aConfiglocation; "ConfigLocationNodeType_Root"
0x18000a497  mov     dword ptr [rdx], 1
0x18000a49d  mov     [rdx+8], rax
0x18000a4a1  mov     rax, rdx
0x18000a4a4  retn
```
