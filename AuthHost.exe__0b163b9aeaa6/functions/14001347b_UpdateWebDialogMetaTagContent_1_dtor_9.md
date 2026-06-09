# _UpdateWebDialogMetaTagContent_::_1_::dtor$9

- ea: `0x14001347b`
- end: `0x140013487`
- name: `_UpdateWebDialogMetaTagContent_::_1_::dtor$9`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400089c8`

## pseudocode

```c
void __fastcall UpdateWebDialogMetaTagContent_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 48));
}

```

## disassembly

```asm
0x14001347b  lea     rcx, [rdx+30h]; this
0x140013482  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
