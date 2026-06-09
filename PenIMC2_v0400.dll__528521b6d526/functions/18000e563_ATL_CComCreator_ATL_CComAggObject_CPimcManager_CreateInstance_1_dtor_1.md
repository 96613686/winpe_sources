# _ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor$1

- ea: `0x18000e563`
- end: `0x18000e573`
- name: `_ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor$1`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800021e4`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator_ATL::CComAggObject_CPimcManager___::CreateInstance_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComContainedObject<CPimcManager>::~CComContainedObject<CPimcManager>(*(_QWORD *)(a2 + 40) + 16LL);
}

```

## disassembly

```asm
0x18000e563  mov     rcx, [rdx+28h]
0x18000e56a  add     rcx, 10h
0x18000e56e  jmp     ??1?$CComContainedObject@VCPimcManager@@@ATL@@QEAA@XZ
```
