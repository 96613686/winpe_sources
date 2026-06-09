# CoCreateInstance_0

- ea: `0x180003bc0`
- end: `0x180003bc6`
- name: `CoCreateInstance_0`
- size: `6`
- prototype: `HRESULT __stdcall(const IID *const rclsid, LPUNKNOWN pUnkOuter, DWORD dwClsContext, const IID *const riid, LPVOID *ppv)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022a0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003bc0`

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
0x180003bc0  jmp     cs:__imp_CoCreateInstance
```
