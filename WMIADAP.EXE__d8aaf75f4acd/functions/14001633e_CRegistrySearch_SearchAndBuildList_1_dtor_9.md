# _CRegistrySearch::SearchAndBuildList_::_1_::dtor$9

- ea: `0x14001633e`
- end: `0x14001634a`
- name: `_CRegistrySearch::SearchAndBuildList_::_1_::dtor$9`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistrySearch::SearchAndBuildList_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  CHString::~CHString(*(const unsigned __int16 ***)(a2 + 224));
}

```

## disassembly

```asm
0x14001633e  mov     rcx, [rdx+0E0h]; this
0x140016345  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
