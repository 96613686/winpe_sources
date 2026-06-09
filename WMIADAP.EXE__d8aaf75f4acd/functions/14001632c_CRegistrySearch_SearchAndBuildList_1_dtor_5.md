# _CRegistrySearch::SearchAndBuildList_::_1_::dtor$5

- ea: `0x14001632c`
- end: `0x140016338`
- name: `_CRegistrySearch::SearchAndBuildList_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistrySearch::SearchAndBuildList_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  CHString::~CHString((const unsigned __int16 **)(a2 + 72));
}

```

## disassembly

```asm
0x14001632c  lea     rcx, [rdx+48h]; this
0x140016333  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
