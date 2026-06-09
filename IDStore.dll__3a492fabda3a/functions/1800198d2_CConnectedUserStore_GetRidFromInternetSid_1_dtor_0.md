# _CConnectedUserStore::GetRidFromInternetSid_::_1_::dtor$0

- ea: `0x1800198d2`
- end: `0x1800198de`
- name: `_CConnectedUserStore::GetRidFromInternetSid_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180003560`

## pseudocode

```c
void __fastcall CConnectedUserStore::GetRidFromInternetSid_::_1_::dtor_0(__int64 a1, __int64 a2, __int64 a3)
{
  CLogBlock::~CLogBlock((CLogBlock *)(a2 + 96), a2, a3);
}

```

## disassembly

```asm
0x1800198d2  lea     rcx, [rdx+60h]; this
0x1800198d9  jmp     ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
```
