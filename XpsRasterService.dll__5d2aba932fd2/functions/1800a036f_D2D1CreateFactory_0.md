# D2D1CreateFactory_0

- ea: `0x1800a036f`
- end: `0x1800a0375`
- name: `D2D1CreateFactory_0`
- size: `6`
- prototype: `HRESULT __stdcall(D2D1_FACTORY_TYPE factoryType, const IID *const riid, const D2D1_FACTORY_OPTIONS *pFactoryOptions, void **ppIFactory)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180016fc0`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x1800a036f`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall D2D1CreateFactory_0(
        D2D1_FACTORY_TYPE factoryType,
        const IID *const riid,
        const D2D1_FACTORY_OPTIONS *pFactoryOptions,
        void **ppIFactory)
{
  return D2D1CreateFactory(factoryType, riid, pFactoryOptions, ppIFactory);
}

```

## disassembly

```asm
0x1800a036f  jmp     cs:__imp_D2D1CreateFactory
```
