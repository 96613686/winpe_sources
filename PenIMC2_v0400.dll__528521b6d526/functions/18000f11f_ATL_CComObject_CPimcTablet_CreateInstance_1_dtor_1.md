# _ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor$1

- ea: `0x18000f11f`
- end: `0x18000f12b`
- name: `_ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c144`

## pseudocode

```c
void __fastcall ATL::CComObject_CPimcTablet_::CreateInstance_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CPimcTablet::~CPimcTablet(*(CPimcTablet **)(a2 + 120));
}

```

## disassembly

```asm
0x18000f11f  mov     rcx, [rdx+78h]; this
0x18000f126  jmp     ??1CPimcTablet@@QEAA@XZ
```
