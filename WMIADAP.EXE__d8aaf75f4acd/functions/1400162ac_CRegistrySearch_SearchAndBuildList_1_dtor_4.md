# _CRegistrySearch::SearchAndBuildList_::_1_::dtor$4

- ea: `0x1400162ac`
- end: `0x1400162b8`
- name: `_CRegistrySearch::SearchAndBuildList_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistrySearch::SearchAndBuildList_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  CHString::~CHString((const unsigned __int16 **)(a2 + 64));
}

```

## disassembly

```asm
0x1400162ac  lea     rcx, [rdx+40h]; this
0x1400162b3  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
