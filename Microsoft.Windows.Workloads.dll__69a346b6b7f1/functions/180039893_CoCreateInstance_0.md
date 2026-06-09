# CoCreateInstance_0

- ea: `0x180039893`
- end: `0x180039899`
- name: `CoCreateInstance_0`
- size: `6`
- prototype: `HRESULT __stdcall(const IID *const rclsid, LPUNKNOWN pUnkOuter, DWORD dwClsContext, const IID *const riid, LPVOID *ppv)`
- caller_count: `9`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007150`
- `0x180021b10`
- `0x180022260`
- `0x1800229c0`
- `0x180023620`
- `0x180023860`
- `0x180023c50`
- `0x180024120`
- `0x18003aec0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180039893`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall CoCreateInstance_0(
        const IID *const rclsid,
        LPUNKNOWN pUnkOuter,
        DWORD dwClsContext,
        const IID *const riid,
        LPVOID *ppv)
{
  return CoCreateInstance(rclsid, pUnkOuter, dwClsContext, riid, ppv);
}

```

## disassembly

```asm
0x180039893  jmp     cs:__imp_CoCreateInstance
```
