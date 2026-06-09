# _ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor$1

- ea: `0x18000ea8a`
- end: `0x18000ea96`
- name: `_ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007ecc`

## pseudocode

```c
__int64 __fastcall ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComGITPtr<ITablet>::~CComGITPtr<ITablet>((_DWORD *)(a2 + 96));
}

```

## disassembly

```asm
0x18000ea8a  lea     rcx, [rdx+60h]
0x18000ea91  jmp     ??1?$CComGITPtr@UITablet@@@ATL@@QEAA@XZ; ATL::CComGITPtr<ITablet>::~CComGITPtr<ITablet>(void)
```
