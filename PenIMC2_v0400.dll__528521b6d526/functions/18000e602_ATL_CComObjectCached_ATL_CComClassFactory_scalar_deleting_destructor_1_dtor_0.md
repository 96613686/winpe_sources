# _ATL::CComObjectCached_ATL::CComClassFactory_::_scalar_deleting_destructor__::_1_::dtor$0

- ea: `0x18000e602`
- end: `0x18000e60e`
- name: `_ATL::CComObjectCached_ATL::CComClassFactory_::_scalar_deleting_destructor__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002fcc`

## pseudocode

```c
void __fastcall ATL::CComObjectCached_ATL::CComClassFactory_::_scalar_deleting_destructor__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  ATL::CComClassFactory::~CComClassFactory(*(ATL::CComClassFactory **)(a2 + 48));
}

```

## disassembly

```asm
0x18000e602  mov     rcx, [rdx+30h]; this
0x18000e609  jmp     ??1CComClassFactory@ATL@@UEAA@XZ; ATL::CComClassFactory::~CComClassFactory(void)
```
