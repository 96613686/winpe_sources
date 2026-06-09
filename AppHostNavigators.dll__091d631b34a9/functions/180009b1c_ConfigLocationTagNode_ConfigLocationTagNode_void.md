# ConfigLocationTagNode::~ConfigLocationTagNode(void)

- ea: `0x180009b1c`
- end: `0x180009b3b`
- name: `??1ConfigLocationTagNode@@UEAA@XZ`
- size: `31`
- prototype: `void __fastcall(ConfigLocationTagNode *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009b10`
- `0x180009b74`
- `0x180009c40`

## callees

- `0x1800021a4`
- `0x180009aa4`

## pseudocode

```c
void __fastcall ConfigLocationTagNode::~ConfigLocationTagNode(ConfigLocationTagNode *this)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 10);
  TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::~TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>(this);
}

```

## disassembly

```asm
0x180009b1c  push    rbx
0x180009b1e  sub     rsp, 20h
0x180009b22  mov     rbx, rcx
0x180009b25  add     rcx, 50h ; 'P'
0x180009b29  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009b2e  mov     rcx, rbx
0x180009b31  add     rsp, 20h
0x180009b35  pop     rbx
0x180009b36  jmp     ??1?$TagNavigationNode@VConfigLocationTagNode@@VConfigLocationNode@@VConfigLocationsTree@@@@UEAA@XZ; TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::~TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>(void)
```
