# _ComUtils::GitComLockableWrapper_ITabletContextP_::GitComLockableWrapper_ITabletContextP__::_1_::dtor$0

- ea: `0x18000ea10`
- end: `0x18000ea1c`
- name: `_ComUtils::GitComLockableWrapper_ITabletContextP_::GitComLockableWrapper_ITabletContextP__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000627c`

## pseudocode

```c
__int64 __fastcall ComUtils::GitComLockableWrapper_ITabletContextP_::GitComLockableWrapper_ITabletContextP__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtr<ITabletContextP>::~CComPtr<ITabletContextP>(*(__int64 **)(a2 + 120));
}

```

## disassembly

```asm
0x18000ea10  mov     rcx, [rdx+78h]
0x18000ea17  jmp     ??1?$CComPtr@UITabletContextP@@@ATL@@QEAA@XZ; ATL::CComPtr<ITabletContextP>::~CComPtr<ITabletContextP>(void)
```
