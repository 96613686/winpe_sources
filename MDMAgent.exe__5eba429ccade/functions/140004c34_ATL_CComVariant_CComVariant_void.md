# ATL::CComVariant::~CComVariant(void)

- ea: `0x140004c34`
- end: `0x140004c3b`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `25`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000a0b8`
- `0x14000bdc4`
- `0x14000d0fc`
- `0x14000d70c`
- `0x14000dca0`
- `0x14000e200`
- `0x14000e6e8`
- `0x14000eaa8`
- `0x14000ef04`
- `0x14000f56c`
- `0x14001464c`
- `0x140018b90`
- `0x140018ba2`
- `0x140018bb4`
- `0x140018bc6`
- `0x140018c8c`
- `0x140018c9e`
- `0x140018cb0`
- `0x140018cc2`
- `0x140018dbe`
- `0x140018e21`
- `0x140018e33`
- `0x140018e45`
- `0x140018e7b`
- `0x140018f50`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x140004c34`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall ATL::CComVariant::~CComVariant(VARIANTARG *pvarg)
{
  return VariantClear(pvarg);
}

```

## disassembly

```asm
0x140004c34  jmp     cs:__imp_VariantClear
```
