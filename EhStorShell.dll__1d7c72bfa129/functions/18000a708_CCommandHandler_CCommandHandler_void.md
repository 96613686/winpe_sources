# CCommandHandler::~CCommandHandler(void)

- ea: `0x18000a708`
- end: `0x18000a731`
- name: `??1CCommandHandler@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CCommandHandler *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a694`

## callees

- `0x18000453c`

## pseudocode

```c
void __fastcall CCommandHandler::~CCommandHandler(CCommandHandler *this)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 7);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 6);
}

```

## disassembly

```asm
0x18000a708  push    rbx
0x18000a70a  sub     rsp, 20h
0x18000a70e  mov     rbx, rcx
0x18000a711  add     rcx, 48h ; 'H'
0x18000a715  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a71a  lea     rcx, [rbx+38h]
0x18000a71e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a723  lea     rcx, [rbx+30h]
0x18000a727  add     rsp, 20h
0x18000a72b  pop     rbx
0x18000a72c  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
