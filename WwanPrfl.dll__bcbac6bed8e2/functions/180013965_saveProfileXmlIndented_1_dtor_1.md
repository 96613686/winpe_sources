# __saveProfileXmlIndented_::_1_::dtor$1

- ea: `0x180013965`
- end: `0x180013971`
- name: `__saveProfileXmlIndented_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003304`

## pseudocode

```c
void __fastcall _saveProfileXmlIndented_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 152));
}

```

## disassembly

```asm
0x180013965  lea     rcx, [rdx+98h]; this
0x18001396c  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
