# _CThread::thread_list_::_2_::_dynamic_atexit_destructor_for__lock__

- ea: `0x18000a670`
- end: `0x18000a67e`
- name: `_CThread::thread_list_::_2_::_dynamic_atexit_destructor_for__lock__`
- size: `14`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a677`

## pseudocode

```c
void __fastcall CThread::thread_list_::_2_::_dynamic_atexit_destructor_for__lock__()
{
  DeleteCriticalSection(&stru_180010628);
}

```

## disassembly

```asm
0x18000a670  lea     rcx, stru_180010628
0x18000a677  jmp     cs:__imp_DeleteCriticalSection
```
