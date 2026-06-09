# _CRegistrySearch::CheckAndAddToList_::_1_::dtor$1

- ea: `0x14001618e`
- end: `0x14001619a`
- name: `_CRegistrySearch::CheckAndAddToList_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistrySearch::CheckAndAddToList_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CHString::~CHString(*(const unsigned __int16 ***)(a2 + 120));
}

```

## disassembly

```asm
0x14001618e  mov     rcx, [rdx+78h]; this
0x140016195  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
