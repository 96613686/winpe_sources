# ConfigPathRootNode::QueryConfigPathNodeType(void)

- ea: `0x18000d660`
- end: `0x18000d675`
- name: `?QueryConfigPathNodeType@ConfigPathRootNode@@UEAA?AV?$NamedEnum@W4ConfigPathNodeType@@@@XZ`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x18000d660`: `ConfigPathNodeType_Root`

## pseudocode

```c
__int64 __fastcall ConfigPathRootNode::QueryConfigPathNodeType(__int64 a1, __int64 a2)
{
  *(_DWORD *)a2 = 1;
  *(_QWORD *)(a2 + 8) = L"ConfigPathNodeType_Root";
  return a2;
}

```

## disassembly

```asm
0x18000d660  lea     rax, aConfigpathnode_8; "ConfigPathNodeType_Root"
0x18000d667  mov     dword ptr [rdx], 1
0x18000d66d  mov     [rdx+8], rax
0x18000d671  mov     rax, rdx
0x18000d674  retn
```
