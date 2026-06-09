# _GetDefaultProviderInfo_::_2_::_dynamic_atexit_destructor_for__s_critSec__

- ea: `0x14001b460`
- end: `0x14001b46e`
- name: `_GetDefaultProviderInfo_::_2_::_dynamic_atexit_destructor_for__s_critSec__`
- size: `14`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14001b467`

## pseudocode

```c
void __fastcall GetDefaultProviderInfo_::_2_::_dynamic_atexit_destructor_for__s_critSec__()
{
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x14001b460  lea     rcx, CriticalSection
0x14001b467  jmp     cs:__imp_DeleteCriticalSection
```
