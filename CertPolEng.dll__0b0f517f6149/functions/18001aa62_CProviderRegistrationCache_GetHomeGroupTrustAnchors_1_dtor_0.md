# _CProviderRegistrationCache::GetHomeGroupTrustAnchors_::_1_::dtor$0

- ea: `0x18001aa62`
- end: `0x18001aa6e`
- name: `_CProviderRegistrationCache::GetHomeGroupTrustAnchors_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003dc0`

## pseudocode

```c
void __fastcall CProviderRegistrationCache::GetHomeGroupTrustAnchors_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)(a2 + 168), a2);
}

```

## disassembly

```asm
0x18001aa62  lea     rcx, [rdx+0A8h]; this
0x18001aa69  jmp     ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
```
