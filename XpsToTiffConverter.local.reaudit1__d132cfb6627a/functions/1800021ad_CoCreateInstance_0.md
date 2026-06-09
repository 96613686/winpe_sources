# CoCreateInstance_0

- ea: `0x1800021ad`
- end: `0x1800021b3`
- name: `CoCreateInstance_0`
- size: `6`
- prototype: `HRESULT __stdcall(const IID *const rclsid, LPUNKNOWN pUnkOuter, DWORD dwClsContext, const IID *const riid, LPVOID *ppv)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a870`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800021ad`

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
0x1800021ad  jmp     cs:__imp_CoCreateInstance
```
