# _ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor$1

- ea: `0x18000e539`
- end: `0x18000e545`
- name: `_ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002fcc`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  ATL::CComClassFactory::~CComClassFactory(*(ATL::CComClassFactory **)(a2 + 40));
}

```

## disassembly

```asm
0x18000e539  mov     rcx, [rdx+28h]; this
0x18000e540  jmp     ??1CComClassFactory@ATL@@UEAA@XZ; ATL::CComClassFactory::~CComClassFactory(void)
```
