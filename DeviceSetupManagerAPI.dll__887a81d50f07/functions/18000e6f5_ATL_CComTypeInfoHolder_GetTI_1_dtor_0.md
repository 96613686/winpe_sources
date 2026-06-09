# _ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$0

- ea: `0x18000e6f5`
- end: `0x18000e701`
- name: `_ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009ea0`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::GetTI_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(a2 + 80);
}

```

## disassembly

```asm
0x18000e6f5  lea     rcx, [rdx+50h]
0x18000e6fc  jmp     ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
```
