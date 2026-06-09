# _CRegistrySearch::CheckAndAddToList_::_1_::dtor$3

- ea: `0x1400161b2`
- end: `0x1400161be`
- name: `_CRegistrySearch::CheckAndAddToList_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistrySearch::CheckAndAddToList_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  CHString::~CHString(*(const unsigned __int16 ***)(a2 + 96));
}

```

## disassembly

```asm
0x1400161b2  mov     rcx, [rdx+60h]; this
0x1400161b9  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
