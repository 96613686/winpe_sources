# RootNodeChildrenInitializer::Invoke(ConfigPathNavigationTree *,ConfigPathTagNode *)

- ea: `0x18000d160`
- end: `0x18000d1a2`
- name: `?Invoke@RootNodeChildrenInitializer@@UEAAXPEAVConfigPathNavigationTree@@PEAVConfigPathTagNode@@@Z`
- size: `66`
- prototype: `void __fastcall(RootNodeChildrenInitializer *__hidden this, struct ConfigPathNavigationTree *, struct ConfigPathTagNode *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000c9bc`

## string_xrefs

- `0x18000d16f`: `ConfigPathNodeType_Machine`

## pseudocode

```c
void __fastcall RootNodeChildrenInitializer::Invoke(
        RootNodeChildrenInitializer *this,
        struct ConfigPathNavigationTree *a2,
        struct ConfigPathTagNode *a3)
{
  int v3; // [rsp+20h] [rbp-18h] BYREF
  const wchar_t *v4; // [rsp+28h] [rbp-10h]

  v3 = 2;
  v4 = L"ConfigPathNodeType_Machine";
  *(_QWORD *)(ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(a3, a2, L"MACHINE", &v3) + 128) = off_18001C1E0;
}

```

## disassembly

```asm
0x18000d160  sub     rsp, 38h
0x18000d164  mov     rax, r8
0x18000d167  mov     [rsp+38h+var_18], 2
0x18000d16f  lea     rcx, aConfigpathnode_7; "ConfigPathNodeType_Machine"
0x18000d176  mov     [rsp+38h+var_10], rcx
0x18000d17b  lea     r9, [rsp+38h+var_18]
0x18000d180  mov     rcx, rax
0x18000d183  lea     r8, aMachine; "MACHINE"
0x18000d18a  call    ?GetOrCreateInstanceAtRelativePath@ConfigPathTagNode@@QEAAPEAV1@PEAVConfigPathNavigationTree@@PEBGAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(ConfigPathNavigationTree *,ushort const *,NamedEnum<ConfigPathNodeType> &)
0x18000d18f  lea     rcx, off_18001C1E0
0x18000d196  mov     [rax+80h], rcx
0x18000d19d  add     rsp, 38h
0x18000d1a1  retn
```
