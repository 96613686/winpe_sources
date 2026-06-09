# CPimcSurrogate::GetWisptisITabletManager(IUnknown * *)

- ea: `0x18000c4b0`
- end: `0x18000c4d8`
- name: `?GetWisptisITabletManager@CPimcSurrogate@@UEAAJPEAPEAUIUnknown@@@Z`
- size: `40`
- prototype: `HRESULT __fastcall(CPimcSurrogate *this, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000c4cd`
- `ole32!CoCreateInstance` at `0x18000c4cd`

## pseudocode

```c
HRESULT __fastcall CPimcSurrogate::GetWisptisITabletManager(CPimcSurrogate *this, LPVOID *ppv)
{
  return CoCreateInstance(&CLSID_TabletManagerS, 0, 5u, &IID_IUnknown, ppv);
}

```

## disassembly

```asm
0x18000c4b0  sub     rsp, 38h
0x18000c4b4  mov     [rsp+38h+ppv], rdx; ppv
0x18000c4b9  lea     r9, IID_IUnknown; riid
0x18000c4c0  xor     edx, edx; pUnkOuter
0x18000c4c2  lea     rcx, CLSID_TabletManagerS; rclsid
0x18000c4c9  lea     r8d, [rdx+5]; dwClsContext
0x18000c4cd  call    cs:__imp_CoCreateInstance
0x18000c4d3  add     rsp, 38h
0x18000c4d7  retn
```
