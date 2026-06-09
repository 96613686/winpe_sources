# _ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor$0

- ea: `0x18000f08f`
- end: `0x18000f09b`
- name: `_ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c144`

## pseudocode

```c
void __fastcall ATL::CComObject_CPimcTablet_::_CComObject_CPimcTablet__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CPimcTablet::~CPimcTablet(*(CPimcTablet **)(a2 + 48));
}

```

## disassembly

```asm
0x18000f08f  mov     rcx, [rdx+30h]; this
0x18000f096  jmp     ??1CPimcTablet@@QEAA@XZ
```
