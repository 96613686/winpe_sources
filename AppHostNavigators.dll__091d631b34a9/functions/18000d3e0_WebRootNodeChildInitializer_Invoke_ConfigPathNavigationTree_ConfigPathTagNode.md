# WebRootNodeChildInitializer::Invoke(ConfigPathNavigationTree *,ConfigPathTagNode *)

- ea: `0x18000d3e0`
- end: `0x18000d422`
- name: `?Invoke@WebRootNodeChildInitializer@@UEAAXPEAVConfigPathNavigationTree@@PEAVConfigPathTagNode@@@Z`
- size: `66`
- prototype: `void __fastcall(WebRootNodeChildInitializer *__hidden this, struct ConfigPathNavigationTree *, struct ConfigPathTagNode *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000c9bc`

## string_xrefs

- `0x18000d3ef`: `ConfigPathNodeType_Apphost`

## pseudocode

```c
void __fastcall WebRootNodeChildInitializer::Invoke(
        WebRootNodeChildInitializer *this,
        struct ConfigPathNavigationTree *a2,
        struct ConfigPathTagNode *a3)
{
  int v3; // [rsp+20h] [rbp-18h] BYREF
  const wchar_t *v4; // [rsp+28h] [rbp-10h]

  v3 = 4;
  v4 = L"ConfigPathNodeType_Apphost";
  *(_QWORD *)(ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(a3, a2, L"APPHOST", &v3) + 128) = off_18001C1E8;
}

```

## disassembly

```asm
0x18000d3e0  sub     rsp, 38h
0x18000d3e4  mov     rax, r8
0x18000d3e7  mov     [rsp+38h+var_18], 4
0x18000d3ef  lea     rcx, aConfigpathnode_3; "ConfigPathNodeType_Apphost"
0x18000d3f6  mov     [rsp+38h+var_10], rcx
0x18000d3fb  lea     r9, [rsp+38h+var_18]
0x18000d400  mov     rcx, rax
0x18000d403  lea     r8, aApphost; "APPHOST"
0x18000d40a  call    ?GetOrCreateInstanceAtRelativePath@ConfigPathTagNode@@QEAAPEAV1@PEAVConfigPathNavigationTree@@PEBGAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(ConfigPathNavigationTree *,ushort const *,NamedEnum<ConfigPathNodeType> &)
0x18000d40f  lea     rcx, off_18001C1E8
0x18000d416  mov     [rax+80h], rcx
0x18000d41d  add     rsp, 38h
0x18000d421  retn
```
