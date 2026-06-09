# _CProviderRegistrationCache::GetCertificates_::_1_::dtor$1

- ea: `0x18001a664`
- end: `0x18001a670`
- name: `_CProviderRegistrationCache::GetCertificates_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003dc0`

## pseudocode

```c
void __fastcall CProviderRegistrationCache::GetCertificates_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)(a2 + 280), a2);
}

```

## disassembly

```asm
0x18001a664  lea     rcx, [rdx+118h]; this
0x18001a66b  jmp     ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
```
