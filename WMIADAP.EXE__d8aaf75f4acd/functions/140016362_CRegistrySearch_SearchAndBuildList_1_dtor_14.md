# _CRegistrySearch::SearchAndBuildList_::_1_::dtor$14

- ea: `0x140016362`
- end: `0x14001636e`
- name: `_CRegistrySearch::SearchAndBuildList_::_1_::dtor$14`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistrySearch::SearchAndBuildList_::_1_::dtor_14(__int64 a1, __int64 a2)
{
  CHString::~CHString(*(const unsigned __int16 ***)(a2 + 184));
}

```

## disassembly

```asm
0x140016362  mov     rcx, [rdx+0B8h]; this
0x140016369  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
