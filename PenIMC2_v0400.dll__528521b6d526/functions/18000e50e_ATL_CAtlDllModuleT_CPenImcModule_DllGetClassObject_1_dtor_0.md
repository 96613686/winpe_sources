# _ATL::CAtlDllModuleT_CPenImcModule_::DllGetClassObject_::_1_::dtor$0

- ea: `0x18000e50e`
- end: `0x18000e51a`
- name: `_ATL::CAtlDllModuleT_CPenImcModule_::DllGetClassObject_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002ed4`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT_CPenImcModule_::DllGetClassObject_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(a2 + 32);
}

```

## disassembly

```asm
0x18000e50e  lea     rcx, [rdx+20h]
0x18000e515  jmp     ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
```
