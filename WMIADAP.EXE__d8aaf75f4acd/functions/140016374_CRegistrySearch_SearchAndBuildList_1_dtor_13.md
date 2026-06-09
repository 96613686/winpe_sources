# _CRegistrySearch::SearchAndBuildList_::_1_::dtor$13

- ea: `0x140016374`
- end: `0x140016380`
- name: `_CRegistrySearch::SearchAndBuildList_::_1_::dtor$13`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistrySearch::SearchAndBuildList_::_1_::dtor_13(__int64 a1, __int64 a2)
{
  CHString::~CHString(*(const unsigned __int16 ***)(a2 + 192));
}

```

## disassembly

```asm
0x140016374  mov     rcx, [rdx+0C0h]; this
0x14001637b  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
