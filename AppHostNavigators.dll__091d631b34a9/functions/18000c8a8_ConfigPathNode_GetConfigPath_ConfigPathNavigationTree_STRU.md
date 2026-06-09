# ConfigPathNode::GetConfigPath(ConfigPathNavigationTree *,STRU &)

- ea: `0x18000c8a8`
- end: `0x18000c8c6`
- name: `?GetConfigPath@ConfigPathNode@@QEAAXPEAVConfigPathNavigationTree@@AEAVSTRU@@@Z`
- size: `30`
- prototype: `void __fastcall(ConfigPathNode *__hidden this, struct ConfigPathNavigationTree *, struct STRU *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800098a0`
- `0x18000cb10`
- `0x18000cee0`
- `0x18000d9ac`

## callees

- `0x180014010`

## pseudocode

```c
void __fastcall ConfigPathNode::GetConfigPath(
        ConfigPathNode *this,
        struct ConfigPathNavigationTree *a2,
        struct STRU *a3)
{
  (*(void (__fastcall **)(ConfigPathNode *, struct ConfigPathNavigationTree *, __int64, struct STRU *))(*(_QWORD *)this + 72LL))(
    this,
    a2,
    1,
    a3);
}

```

## disassembly

```asm
0x18000c8a8  sub     rsp, 38h
0x18000c8ac  mov     rax, [rcx]
0x18000c8af  mov     r9, r8
0x18000c8b2  mov     r8d, 1
0x18000c8b8  mov     rax, [rax+48h]
0x18000c8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8c1  add     rsp, 38h
0x18000c8c5  retn
```
