# _ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor$9

- ea: `0x18000eac6`
- end: `0x18000ead2`
- name: `_ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor$9`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002244`

## pseudocode

```c
__int64 __fastcall ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)(a2 + 112));
}

```

## disassembly

```asm
0x18000eac6  lea     rcx, [rdx+70h]
0x18000eacd  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ
```
