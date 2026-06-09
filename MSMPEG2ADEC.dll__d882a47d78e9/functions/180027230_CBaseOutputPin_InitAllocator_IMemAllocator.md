# CBaseOutputPin::InitAllocator(IMemAllocator * *)

- ea: `0x180027230`
- end: `0x18002725f`
- name: `?InitAllocator@CBaseOutputPin@@UEAAJPEAPEAUIMemAllocator@@@Z`
- size: `47`
- prototype: `int(CBaseOutputPin *__hidden this, struct IMemAllocator **)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002724d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002724d`

## pseudocode

```c
HRESULT __fastcall CBaseOutputPin::InitAllocator(CBaseOutputPin *this, LPVOID *ppv)
{
  return CoCreateInstance(&CLSID_MemoryAllocator, 0, 1u, &IID_IMemAllocator, ppv);
}

```

## disassembly

```asm
0x180027230  sub     rsp, 38h
0x180027234  mov     [rsp+38h+ppv], rdx; ppv
0x180027239  lea     r9, IID_IMemAllocator; riid
0x180027240  xor     edx, edx; pUnkOuter
0x180027242  lea     rcx, CLSID_MemoryAllocator; rclsid
0x180027249  lea     r8d, [rdx+1]; dwClsContext
0x18002724d  call    cs:__imp_CoCreateInstance
0x180027254  nop     dword ptr [rax+rax+00h]
0x180027259  add     rsp, 38h
0x18002725d  retn
```
