# _MosStorageGetDataDirectory_::_1_::dtor$0

- ea: `0x18000ed34`
- end: `0x18000ed40`
- name: `_MosStorageGetDataDirectory_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006bec`

## pseudocode

```c
void __fastcall MosStorageGetDataDirectory_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(a2 + 32);
}

```

## disassembly

```asm
0x18000ed34  lea     rcx, [rdx+20h]
0x18000ed3b  jmp     ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
```
