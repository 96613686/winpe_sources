# _ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$0

- ea: `0x18000990d`
- end: `0x180009919`
- name: `_ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800021d0`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::GetTI_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(a2 + 80);
}

```

## disassembly

```asm
0x18000990d  lea     rcx, [rdx+50h]
0x180009914  jmp     ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
```
