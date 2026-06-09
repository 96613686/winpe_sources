# _dynamic_initializer_for__Hooked_CoCreateInstance__

- ea: `0x180001b10`
- end: `0x180001b1f`
- name: `_dynamic_initializer_for__Hooked_CoCreateInstance__`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180001b10`

## pseudocode

```c
HRESULT (__stdcall *dynamic_initializer_for__Hooked_CoCreateInstance__())(const IID *const rclsid, LPUNKNOWN pUnkOuter, DWORD dwClsContext, const IID *const riid, LPVOID *ppv)
{
  HRESULT (__stdcall *result)(const IID *const, LPUNKNOWN, DWORD, const IID *const, LPVOID *); // rax

  result = CoCreateInstance;
  Hooked_CoCreateInstance = (int (*)(const struct _GUID *, struct IUnknown *, unsigned int, const struct _GUID *, void **))CoCreateInstance;
  return result;
}

```

## disassembly

```asm
0x180001b10  mov     rax, cs:__imp_CoCreateInstance
0x180001b17  mov     cs:?Hooked_CoCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA, rax; long (*Hooked_CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x180001b1e  retn
```
