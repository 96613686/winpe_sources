# _CRegistrySearch::SearchAndBuildList_::_1_::dtor$6

- ea: `0x140016276`
- end: `0x140016282`
- name: `_CRegistrySearch::SearchAndBuildList_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistrySearch::SearchAndBuildList_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  CHString::~CHString((const unsigned __int16 **)(a2 + 88));
}

```

## disassembly

```asm
0x140016276  lea     rcx, [rdx+58h]; this
0x14001627d  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
