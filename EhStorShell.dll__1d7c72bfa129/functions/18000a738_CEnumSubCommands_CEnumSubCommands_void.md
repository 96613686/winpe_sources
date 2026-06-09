# CEnumSubCommands::~CEnumSubCommands(void)

- ea: `0x18000a738`
- end: `0x18000a758`
- name: `??1CEnumSubCommands@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(CEnumSubCommands *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b160`

## callees

- `0x18000453c`

## pseudocode

```c
void __fastcall CEnumSubCommands::~CEnumSubCommands(CEnumSubCommands *this)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 4);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 2);
}

```

## disassembly

```asm
0x18000a738  push    rbx
0x18000a73a  sub     rsp, 20h
0x18000a73e  mov     rbx, rcx
0x18000a741  add     rcx, 20h ; ' '
0x18000a745  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a74a  lea     rcx, [rbx+10h]
0x18000a74e  add     rsp, 20h
0x18000a752  pop     rbx
0x18000a753  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
