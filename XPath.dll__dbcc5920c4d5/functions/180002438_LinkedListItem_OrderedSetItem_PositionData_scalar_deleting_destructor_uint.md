# LinkedListItem<OrderedSetItem<PositionData>>::`scalar deleting destructor'(uint)

- ea: `0x180002438`
- end: `0x18000245b`
- name: `??_G?$LinkedListItem@V?$OrderedSetItem@VPositionData@@@@@@QEAAPEAXI@Z`
- size: `35`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002c10`
- `0x180002e9c`

## callees

- `0x1800010b8`
- `0x1800020b4`

## pseudocode

```c
__int64 *__fastcall LinkedListItem<OrderedSetItem<PositionData>>::`scalar deleting destructor'(__int64 *Block)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(Block + 3);
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002438  push    rbx
0x18000243a  sub     rsp, 20h
0x18000243e  mov     rbx, rcx
0x180002441  add     rcx, 18h
0x180002445  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000244a  mov     rcx, rbx; Block
0x18000244d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002452  mov     rax, rbx
0x180002455  add     rsp, 20h
0x180002459  pop     rbx
0x18000245a  retn
```
