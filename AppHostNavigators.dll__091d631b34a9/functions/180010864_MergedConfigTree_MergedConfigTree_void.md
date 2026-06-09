# MergedConfigTree::~MergedConfigTree(void)

- ea: `0x180010864`
- end: `0x180010892`
- name: `??1MergedConfigTree@@UEAA@XZ`
- size: `46`
- prototype: `void __fastcall(MergedConfigTree *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800108e0`

## callees

- `0x1800021a4`
- `0x18001082c`
- `0x180012ea8`

## pseudocode

```c
void __fastcall MergedConfigTree::~MergedConfigTree(MergedConfigTree *this)
{
  ScopedBSTR::Reset((MergedConfigTree *)((char *)this + 136));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 16);
  ConfigTreeBase::~ConfigTreeBase((InvasivePtrObject **)this);
}

```

## disassembly

```asm
0x180010864  push    rbx
0x180010866  sub     rsp, 20h
0x18001086a  mov     rbx, rcx
0x18001086d  add     rcx, 88h; this
0x180010874  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x180010879  lea     rcx, [rbx+80h]
0x180010880  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010885  mov     rcx, rbx; this
0x180010888  add     rsp, 20h
0x18001088c  pop     rbx
0x18001088d  jmp     ??1ConfigTreeBase@@UEAA@XZ; ConfigTreeBase::~ConfigTreeBase(void)
```
