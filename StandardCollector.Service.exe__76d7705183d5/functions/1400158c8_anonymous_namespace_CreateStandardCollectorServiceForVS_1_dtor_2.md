# __anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$2

- ea: `0x1400158c8`
- end: `0x1400158d4`
- name: `__anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002434`

## pseudocode

```c
void __fastcall _anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 48));
}

```

## disassembly

```asm
0x1400158c8  lea     rcx, [rdx+30h]; this
0x1400158cf  jmp     ??1CComBSTR@ATL@@QEAA@XZ
```
