# _ATL::CComAggObject_CPimcManager_::_CComAggObject_CPimcManager__::_1_::dtor$0

- ea: `0x18000e626`
- end: `0x18000e636`
- name: `_ATL::CComAggObject_CPimcManager_::_CComAggObject_CPimcManager__::_1_::dtor$0`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800021e4`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject_CPimcManager_::_CComAggObject_CPimcManager__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComContainedObject<CPimcManager>::~CComContainedObject<CPimcManager>(*(_QWORD *)(a2 + 48) + 16LL);
}

```

## disassembly

```asm
0x18000e626  mov     rcx, [rdx+30h]
0x18000e62d  add     rcx, 10h
0x18000e631  jmp     ??1?$CComContainedObject@VCPimcManager@@@ATL@@QEAA@XZ; ATL::CComContainedObject<CPimcManager>::~CComContainedObject<CPimcManager>(void)
```
