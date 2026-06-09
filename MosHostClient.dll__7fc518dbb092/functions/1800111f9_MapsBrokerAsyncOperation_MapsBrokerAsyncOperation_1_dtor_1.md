# _MapsBrokerAsyncOperation::MapsBrokerAsyncOperation_::_1_::dtor$1

- ea: `0x1800111f9`
- end: `0x180011209`
- name: `_MapsBrokerAsyncOperation::MapsBrokerAsyncOperation_::_1_::dtor$1`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007938`

## pseudocode

```c
void __fastcall MapsBrokerAsyncOperation::MapsBrokerAsyncOperation_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CComAutoCriticalSection::~CComAutoCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a2 + 64) + 16LL));
}

```

## disassembly

```asm
0x1800111f9  mov     rcx, [rdx+40h]
0x180011200  add     rcx, 10h; lpCriticalSection
0x180011204  jmp     ??1CComAutoCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoCriticalSection::~CComAutoCriticalSection(void)
```
