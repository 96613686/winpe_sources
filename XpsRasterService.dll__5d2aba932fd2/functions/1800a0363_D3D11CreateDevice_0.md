# D3D11CreateDevice_0

- ea: `0x1800a0363`
- end: `0x1800a0369`
- name: `D3D11CreateDevice_0`
- size: `6`
- prototype: `HRESULT __stdcall(IDXGIAdapter *pAdapter, D3D_DRIVER_TYPE DriverType, HMODULE Software, UINT Flags, const D3D_FEATURE_LEVEL *pFeatureLevels, UINT FeatureLevels, UINT SDKVersion, ID3D11Device **ppDevice, D3D_FEATURE_LEVEL *pFeatureLevel, ID3D11DeviceContext **ppImmediateContext)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180016fc0`

## import_xrefs

- `d3d11!D3D11CreateDevice` at `0x1800a0363`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall D3D11CreateDevice_0(
        IDXGIAdapter *pAdapter,
        D3D_DRIVER_TYPE DriverType,
        HMODULE Software,
        UINT Flags,
        const D3D_FEATURE_LEVEL *pFeatureLevels,
        UINT FeatureLevels,
        UINT SDKVersion,
        ID3D11Device **ppDevice,
        D3D_FEATURE_LEVEL *pFeatureLevel,
        ID3D11DeviceContext **ppImmediateContext)
{
  return D3D11CreateDevice(
           pAdapter,
           DriverType,
           Software,
           Flags,
           pFeatureLevels,
           FeatureLevels,
           SDKVersion,
           ppDevice,
           pFeatureLevel,
           ppImmediateContext);
}

```

## disassembly

```asm
0x1800a0363  jmp     cs:__imp_D3D11CreateDevice
```
