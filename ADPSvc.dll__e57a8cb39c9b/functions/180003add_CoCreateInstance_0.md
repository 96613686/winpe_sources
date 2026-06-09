# CoCreateInstance_0

- ea: `0x180003add`
- end: `0x180003ae3`
- name: `CoCreateInstance_0`
- size: `6`
- prototype: `HRESULT __stdcall(const IID *const rclsid, LPUNKNOWN pUnkOuter, DWORD dwClsContext, const IID *const riid, LPVOID *ppv)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010b6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003add`

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
0x180003add  jmp     cs:__imp_CoCreateInstance
```
