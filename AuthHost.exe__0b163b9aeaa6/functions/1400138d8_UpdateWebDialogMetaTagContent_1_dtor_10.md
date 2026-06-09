# _UpdateWebDialogMetaTagContent_::_1_::dtor$10

- ea: `0x1400138d8`
- end: `0x1400138e4`
- name: `_UpdateWebDialogMetaTagContent_::_1_::dtor$10`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140011774`

## pseudocode

```c
HRESULT __fastcall UpdateWebDialogMetaTagContent_::_1_::dtor_10(__int64 a1, VARIANTARG *a2)
{
  return Common::AutoVariant::~AutoVariant(a2 + 6);
}

```

## disassembly

```asm
0x1400138d8  lea     rcx, [rdx+90h]; pvarg
0x1400138df  jmp     ??1AutoVariant@Common@@QEAA@XZ; Common::AutoVariant::~AutoVariant(void)
```
