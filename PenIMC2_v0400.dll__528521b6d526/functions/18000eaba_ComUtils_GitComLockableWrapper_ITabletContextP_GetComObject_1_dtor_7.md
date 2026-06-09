# _ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor$7

- ea: `0x18000eaba`
- end: `0x18000eac6`
- name: `_ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000627c`

## pseudocode

```c
__int64 __fastcall ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ITabletContextP>::~CComPtr<ITabletContextP>((__int64 *)(a2 + 112));
}

```

## disassembly

```asm
0x18000eaba  lea     rcx, [rdx+70h]
0x18000eac1  jmp     ??1?$CComPtr@UITabletContextP@@@ATL@@QEAA@XZ
```
