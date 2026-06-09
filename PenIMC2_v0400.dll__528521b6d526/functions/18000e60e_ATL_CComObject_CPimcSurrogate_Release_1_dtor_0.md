# _ATL::CComObject_CPimcSurrogate_::Release_::_1_::dtor$0

- ea: `0x18000e60e`
- end: `0x18000e61a`
- name: `_ATL::CComObject_CPimcSurrogate_::Release_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800023a8`

## pseudocode

```c
void __fastcall ATL::CComObject_CPimcSurrogate_::Release_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::ModuleLockHelper::~ModuleLockHelper((ATL::ModuleLockHelper *)(a2 + 32));
}

```

## disassembly

```asm
0x18000e60e  lea     rcx, [rdx+20h]; this
0x18000e615  jmp     ??1ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::~ModuleLockHelper(void)
```
