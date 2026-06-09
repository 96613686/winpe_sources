# ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(ConfigPathNavigationTree *,ushort const *,NamedEnum<ConfigPathNodeType> &)

- ea: `0x18000c9bc`
- end: `0x18000c9e1`
- name: `?GetOrCreateInstanceAtRelativePath@ConfigPathTagNode@@QEAAPEAV1@PEAVConfigPathNavigationTree@@PEBGAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z`
- size: `37`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005390`
- `0x18000c8cc`
- `0x18000cb10`
- `0x18000cc48`
- `0x18000d110`
- `0x18000d160`
- `0x18000d3e0`
- `0x18000d430`

## callees

- `0x18000c9e8`
- `0x18000da84`

## pseudocode

```c
__int64 __fastcall ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(
        ConfigPathTagNode *a1,
        struct ConfigPathNavigationTree *a2,
        unsigned __int16 *a3,
        __int64 a4)
{
  struct ConfigPathTagNode *InstanceAtRelativePathRecursiveHelper; // rax
  __int64 v6; // r11

  InstanceAtRelativePathRecursiveHelper = ConfigPathTagNode::GetOrCreateInstanceAtRelativePathRecursiveHelper(
                                            a1,
                                            a2,
                                            a3);
  ConfigPathTagNode::TrySetConfigPathNodeType(InstanceAtRelativePathRecursiveHelper, a4);
  return v6;
}

```

## disassembly

```asm
0x18000c9bc  push    rbx
0x18000c9be  sub     rsp, 20h
0x18000c9c2  mov     rbx, r9
0x18000c9c5  call    ?GetOrCreateInstanceAtRelativePathRecursiveHelper@ConfigPathTagNode@@AEAAPEAV1@PEAVConfigPathNavigationTree@@PEBG@Z; ConfigPathTagNode::GetOrCreateInstanceAtRelativePathRecursiveHelper(ConfigPathNavigationTree *,ushort const *)
0x18000c9ca  mov     rdx, rbx
0x18000c9cd  mov     rcx, rax
0x18000c9d0  mov     r11, rax
0x18000c9d3  call    ?TrySetConfigPathNodeType@ConfigPathTagNode@@IEAA_NAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::TrySetConfigPathNodeType(NamedEnum<ConfigPathNodeType> &)
0x18000c9d8  mov     rax, r11
0x18000c9db  add     rsp, 20h
0x18000c9df  pop     rbx
0x18000c9e0  retn
```
