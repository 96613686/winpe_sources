# __anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$5

- ea: `0x1400158ec`
- end: `0x1400158f8`
- name: `__anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002434`

## pseudocode

```c
void __fastcall _anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 64));
}

```

## disassembly

```asm
0x1400158ec  lea     rcx, [rdx+40h]; this
0x1400158f3  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
