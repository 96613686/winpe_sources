# ConfigTreeBase::~ConfigTreeBase(void)

- ea: `0x18001082c`
- end: `0x18001085e`
- name: `??1ConfigTreeBase@@UEAA@XZ`
- size: `50`
- prototype: `void __fastcall(ConfigTreeBase *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010864`
- `0x1800108a0`
- `0x18001153c`
- `0x180013c2d`
- `0x180013ccb`

## callees

- `0x180003a1c`
- `0x1800044ac`
- `0x18000a960`

## pseudocode

```c
void __fastcall ConfigTreeBase::~ConfigTreeBase(InvasivePtrObject **this)
{
  *this = (InvasivePtrObject *)&ConfigTreeBase::`vftable';
  SectionGroupNode::~SectionGroupNode((SectionGroupNode *)(this + 4));
  InvasivePtr<ConfigLocationsTree>::Reset(this + 3);
  NavigationTreeBase::~NavigationTreeBase((NavigationTreeBase *)this);
}

```

## disassembly

```asm
0x18001082c  push    rbx
0x18001082e  sub     rsp, 20h
0x180010832  lea     rax, ??_7ConfigTreeBase@@6B@; const ConfigTreeBase::`vftable'
0x180010839  mov     rbx, rcx
0x18001083c  mov     [rcx], rax
0x18001083f  add     rcx, 20h ; ' '; this
0x180010843  call    ??1SectionGroupNode@@UEAA@XZ; SectionGroupNode::~SectionGroupNode(void)
0x180010848  lea     rcx, [rbx+18h]
0x18001084c  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180010851  mov     rcx, rbx; this
0x180010854  add     rsp, 20h
0x180010858  pop     rbx
0x180010859  jmp     ??1NavigationTreeBase@@UEAA@XZ; NavigationTreeBase::~NavigationTreeBase(void)
```
