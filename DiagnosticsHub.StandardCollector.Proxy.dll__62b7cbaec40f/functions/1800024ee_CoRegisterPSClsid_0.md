# CoRegisterPSClsid_0

- ea: `0x1800024ee`
- end: `0x1800024f4`
- name: `CoRegisterPSClsid_0`
- size: `6`
- prototype: `HRESULT __stdcall(const IID *const riid, const IID *const rclsid)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `ole32!CoRegisterPSClsid` at `0x1800024ee`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall CoRegisterPSClsid_0(const IID *const riid, const IID *const rclsid)
{
  return CoRegisterPSClsid(riid, rclsid);
}

```

## disassembly

```asm
0x1800024ee  jmp     cs:__imp_CoRegisterPSClsid
```
