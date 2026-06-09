# _CRegistrySearch::SearchAndBuildList_::_1_::dtor$1

- ea: `0x1400162f6`
- end: `0x140016302`
- name: `_CRegistrySearch::SearchAndBuildList_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistrySearch::SearchAndBuildList_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CHString::~CHString(*(const unsigned __int16 ***)(a2 + 208));
}

```

## disassembly

```asm
0x1400162f6  mov     rcx, [rdx+0D0h]; this
0x1400162fd  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
