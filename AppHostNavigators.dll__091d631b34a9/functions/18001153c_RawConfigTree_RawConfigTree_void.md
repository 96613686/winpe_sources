# RawConfigTree::~RawConfigTree(void)

- ea: `0x18001153c`
- end: `0x180011582`
- name: `??1RawConfigTree@@UEAA@XZ`
- size: `70`
- prototype: `void __fastcall(RawConfigTree *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011590`

## callees

- `0x1800021a4`
- `0x18001082c`
- `0x18001277c`

## pseudocode

```c
void __fastcall RawConfigTree::~RawConfigTree(RawConfigTree *this)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 19);
  String::Reset((RawConfigTree *)((char *)this + 144));
  String::Reset((RawConfigTree *)((char *)this + 136));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 16);
  ConfigTreeBase::~ConfigTreeBase((InvasivePtrObject **)this);
}

```

## disassembly

```asm
0x18001153c  push    rbx
0x18001153e  sub     rsp, 20h
0x180011542  mov     rbx, rcx
0x180011545  add     rcx, 98h
0x18001154c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180011551  lea     rcx, [rbx+90h]; this
0x180011558  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18001155d  lea     rcx, [rbx+88h]; this
0x180011564  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x180011569  lea     rcx, [rbx+80h]
0x180011570  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180011575  mov     rcx, rbx; this
0x180011578  add     rsp, 20h
0x18001157c  pop     rbx
0x18001157d  jmp     ??1ConfigTreeBase@@UEAA@XZ; ConfigTreeBase::~ConfigTreeBase(void)
```
