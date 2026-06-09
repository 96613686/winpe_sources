# _LookupRPCConnectionFromCache_::_1_::dtor$0

- ea: `0x18000fba0`
- end: `0x18000fbac`
- name: `_LookupRPCConnectionFromCache_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003938`

## pseudocode

```c
void __fastcall LookupRPCConnectionFromCache_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CSR::~CSR((CSR *)(a2 + 56));
}

```

## disassembly

```asm
0x18000fba0  lea     rcx, [rdx+38h]; this
0x18000fba7  jmp     ??1CSR@@QEAA@XZ; CSR::~CSR(void)
```
