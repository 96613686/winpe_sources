# ConfigLocationsTree::~ConfigLocationsTree(void)

- ea: `0x180009b74`
- end: `0x180009bae`
- name: `??1ConfigLocationsTree@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ConfigLocationsTree *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c80`

## callees

- `0x1800021a4`
- `0x180003a1c`
- `0x1800044ac`
- `0x180009b1c`
- `0x18001277c`

## pseudocode

```c
void __fastcall ConfigLocationsTree::~ConfigLocationsTree(ConfigLocationsTree *this)
{
  ConfigLocationTagNode::~ConfigLocationTagNode((ConfigLocationsTree *)((char *)this + 48));
  String::Reset((ConfigLocationsTree *)((char *)this + 40));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 4);
  InvasivePtr<ConfigLocationsTree>::Reset((InvasivePtrObject **)this + 3);
  NavigationTreeBase::~NavigationTreeBase(this);
}

```

## disassembly

```asm
0x180009b74  push    rbx
0x180009b76  sub     rsp, 20h
0x180009b7a  mov     rbx, rcx
0x180009b7d  add     rcx, 30h ; '0'; this
0x180009b81  call    ??1ConfigLocationTagNode@@UEAA@XZ; ConfigLocationTagNode::~ConfigLocationTagNode(void)
0x180009b86  lea     rcx, [rbx+28h]; this
0x180009b8a  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x180009b8f  lea     rcx, [rbx+20h]
0x180009b93  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009b98  lea     rcx, [rbx+18h]
0x180009b9c  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180009ba1  mov     rcx, rbx; this
0x180009ba4  add     rsp, 20h
0x180009ba8  pop     rbx
0x180009ba9  jmp     ??1NavigationTreeBase@@UEAA@XZ; NavigationTreeBase::~NavigationTreeBase(void)
```
