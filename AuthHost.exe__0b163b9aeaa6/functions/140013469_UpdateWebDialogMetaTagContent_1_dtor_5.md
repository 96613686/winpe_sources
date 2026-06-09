# _UpdateWebDialogMetaTagContent_::_1_::dtor$5

- ea: `0x140013469`
- end: `0x140013475`
- name: `_UpdateWebDialogMetaTagContent_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400089c8`

## pseudocode

```c
void __fastcall UpdateWebDialogMetaTagContent_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 112));
}

```

## disassembly

```asm
0x140013469  lea     rcx, [rdx+70h]; this
0x140013470  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
