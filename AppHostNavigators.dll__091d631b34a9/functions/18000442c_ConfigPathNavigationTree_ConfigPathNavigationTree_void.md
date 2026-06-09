# ConfigPathNavigationTree::~ConfigPathNavigationTree(void)

- ea: `0x18000442c`
- end: `0x180004463`
- name: `??1ConfigPathNavigationTree@@UEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ConfigPathNavigationTree *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004640`

## callees

- `0x180003a1c`
- `0x1800043c4`
- `0x1800044ac`
- `0x1800044ec`

## pseudocode

```c
void __fastcall ConfigPathNavigationTree::~ConfigPathNavigationTree(InvasivePtrObject **this)
{
  VDirMappingOwnerTable::~VDirMappingOwnerTable((VDirMappingOwnerTable *)(this + 21));
  InvasivePtr<ConfigLocationsTree>::Reset(this + 20);
  TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::~TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>((ConfigPathNode *)(this + 3));
  NavigationTreeBase::~NavigationTreeBase((NavigationTreeBase *)this);
}

```

## disassembly

```asm
0x18000442c  push    rbx
0x18000442e  sub     rsp, 20h
0x180004432  mov     rbx, rcx
0x180004435  add     rcx, 0A8h; this
0x18000443c  call    ??1VDirMappingOwnerTable@@UEAA@XZ; VDirMappingOwnerTable::~VDirMappingOwnerTable(void)
0x180004441  lea     rcx, [rbx+0A0h]
0x180004448  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x18000444d  lea     rcx, [rbx+18h]; this
0x180004451  call    ??1?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@UEAA@XZ; TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::~TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>(void)
0x180004456  mov     rcx, rbx; this
0x180004459  add     rsp, 20h
0x18000445d  pop     rbx
0x18000445e  jmp     ??1NavigationTreeBase@@UEAA@XZ; NavigationTreeBase::~NavigationTreeBase(void)
```
