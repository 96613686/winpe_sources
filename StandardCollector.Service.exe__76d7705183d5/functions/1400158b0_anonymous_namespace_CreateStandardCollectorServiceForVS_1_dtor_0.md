# __anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$0

- ea: `0x1400158b0`
- end: `0x1400158bc`
- name: `__anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002434`

## pseudocode

```c
void __fastcall _anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 80));
}

```

## disassembly

```asm
0x1400158b0  lea     rcx, [rdx+50h]; this
0x1400158b7  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
