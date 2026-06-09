# ATL::CComVariant::~CComVariant(void)

- ea: `0x140004cd0`
- end: `0x140004cd7`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `25`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000a51c`
- `0x14000c314`
- `0x14000d780`
- `0x14000ddd8`
- `0x14000e3a4`
- `0x14000e934`
- `0x14000ee48`
- `0x14000f220`
- `0x14000f69c`
- `0x14000fd3c`
- `0x1400151d8`
- `0x1400198f1`
- `0x140019903`
- `0x140019915`
- `0x140019927`
- `0x1400199ed`
- `0x1400199ff`
- `0x140019a11`
- `0x140019a23`
- `0x140019b1f`
- `0x140019b82`
- `0x140019b94`
- `0x140019ba6`
- `0x140019bdc`
- `0x140019cb0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x140004cd0`

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
0x140004cd0  jmp     cs:__imp_VariantClear
```
