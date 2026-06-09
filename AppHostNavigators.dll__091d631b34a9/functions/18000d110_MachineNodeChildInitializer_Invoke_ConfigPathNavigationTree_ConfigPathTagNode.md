# MachineNodeChildInitializer::Invoke(ConfigPathNavigationTree *,ConfigPathTagNode *)

- ea: `0x18000d110`
- end: `0x18000d152`
- name: `?Invoke@MachineNodeChildInitializer@@UEAAXPEAVConfigPathNavigationTree@@PEAVConfigPathTagNode@@@Z`
- size: `66`
- prototype: `void __fastcall(MachineNodeChildInitializer *__hidden this, struct ConfigPathNavigationTree *, struct ConfigPathTagNode *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000c9bc`

## string_xrefs

- `0x18000d11f`: `ConfigPathNodeType_Webroot`

## pseudocode

```c
void __fastcall MachineNodeChildInitializer::Invoke(
        MachineNodeChildInitializer *this,
        struct ConfigPathNavigationTree *a2,
        struct ConfigPathTagNode *a3)
{
  int v3; // [rsp+20h] [rbp-18h] BYREF
  const wchar_t *v4; // [rsp+28h] [rbp-10h]

  v3 = 3;
  v4 = L"ConfigPathNodeType_Webroot";
  *(_QWORD *)(ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(a3, a2, L"WEBROOT", &v3) + 128) = off_18001C1D8;
}

```

## disassembly

```asm
0x18000d110  sub     rsp, 38h
0x18000d114  mov     rax, r8
0x18000d117  mov     [rsp+38h+var_18], 3
0x18000d11f  lea     rcx, aConfigpathnode; "ConfigPathNodeType_Webroot"
0x18000d126  mov     [rsp+38h+var_10], rcx
0x18000d12b  lea     r9, [rsp+38h+var_18]
0x18000d130  mov     rcx, rax
0x18000d133  lea     r8, aWebroot; "WEBROOT"
0x18000d13a  call    ?GetOrCreateInstanceAtRelativePath@ConfigPathTagNode@@QEAAPEAV1@PEAVConfigPathNavigationTree@@PEBGAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(ConfigPathNavigationTree *,ushort const *,NamedEnum<ConfigPathNodeType> &)
0x18000d13f  lea     rcx, off_18001C1D8
0x18000d146  mov     [rax+80h], rcx
0x18000d14d  add     rsp, 38h
0x18000d151  retn
```
