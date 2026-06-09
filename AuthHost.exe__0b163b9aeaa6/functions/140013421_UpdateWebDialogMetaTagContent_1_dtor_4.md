# _UpdateWebDialogMetaTagContent_::_1_::dtor$4

- ea: `0x140013421`
- end: `0x14001342d`
- name: `_UpdateWebDialogMetaTagContent_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400089c8`

## pseudocode

```c
void __fastcall UpdateWebDialogMetaTagContent_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 80));
}

```

## disassembly

```asm
0x140013421  lea     rcx, [rdx+50h]; this
0x140013428  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
