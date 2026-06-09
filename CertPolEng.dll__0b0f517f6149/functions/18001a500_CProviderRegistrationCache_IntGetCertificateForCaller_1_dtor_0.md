# _CProviderRegistrationCache::IntGetCertificateForCaller_::_1_::dtor$0

- ea: `0x18001a500`
- end: `0x18001a50c`
- name: `_CProviderRegistrationCache::IntGetCertificateForCaller_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003dc0`

## pseudocode

```c
void __fastcall CProviderRegistrationCache::IntGetCertificateForCaller_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)(a2 + 176), a2);
}

```

## disassembly

```asm
0x18001a500  lea     rcx, [rdx+0B0h]; this
0x18001a507  jmp     ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
```
