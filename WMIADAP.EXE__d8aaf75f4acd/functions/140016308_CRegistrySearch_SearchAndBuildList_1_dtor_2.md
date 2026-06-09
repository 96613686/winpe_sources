# _CRegistrySearch::SearchAndBuildList_::_1_::dtor$2

- ea: `0x140016308`
- end: `0x140016314`
- name: `_CRegistrySearch::SearchAndBuildList_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistrySearch::SearchAndBuildList_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CHString::~CHString(*(const unsigned __int16 ***)(a2 + 200));
}

```

## disassembly

```asm
0x140016308  mov     rcx, [rdx+0C8h]; this
0x14001630f  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
