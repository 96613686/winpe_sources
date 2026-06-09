# _UpdateWebDialogMetaTagContent_::_1_::dtor$3

- ea: `0x1400138b4`
- end: `0x1400138c0`
- name: `_UpdateWebDialogMetaTagContent_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400089c8`

## pseudocode

```c
void __fastcall UpdateWebDialogMetaTagContent_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 136));
}

```

## disassembly

```asm
0x1400138b4  lea     rcx, [rdx+88h]; this
0x1400138bb  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
