# _CRegistrySearch::SearchAndBuildList_::_1_::dtor$7

- ea: `0x140015f95`
- end: `0x140015fa1`
- name: `_CRegistrySearch::SearchAndBuildList_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistrySearch::SearchAndBuildList_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  CHString::~CHString((const unsigned __int16 **)(a2 + 104));
}

```

## disassembly

```asm
0x140015f95  lea     rcx, [rdx+68h]; this
0x140015f9c  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
