# _CRegistrySearch::SearchAndBuildList_::_1_::dtor$10

- ea: `0x140016350`
- end: `0x14001635c`
- name: `_CRegistrySearch::SearchAndBuildList_::_1_::dtor$10`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistrySearch::SearchAndBuildList_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  CHString::~CHString(*(const unsigned __int16 ***)(a2 + 176));
}

```

## disassembly

```asm
0x140016350  mov     rcx, [rdx+0B0h]; this
0x140016357  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
