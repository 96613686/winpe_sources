# _CProviderRegistrationCache::IntGetTrustAnchors_::_1_::dtor$0

- ea: `0x18001a540`
- end: `0x18001a54c`
- name: `_CProviderRegistrationCache::IntGetTrustAnchors_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003dc0`

## pseudocode

```c
void __fastcall CProviderRegistrationCache::IntGetTrustAnchors_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)(a2 + 160), a2);
}

```

## disassembly

```asm
0x18001a540  lea     rcx, [rdx+0A0h]; this
0x18001a547  jmp     ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
```
