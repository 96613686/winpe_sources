# _CRegistrySearch::SearchAndBuildList_::_1_::dtor$0

- ea: `0x1400162e4`
- end: `0x1400162f0`
- name: `_CRegistrySearch::SearchAndBuildList_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistrySearch::SearchAndBuildList_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CHString::~CHString(*(const unsigned __int16 ***)(a2 + 216));
}

```

## disassembly

```asm
0x1400162e4  mov     rcx, [rdx+0D8h]; this
0x1400162eb  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
