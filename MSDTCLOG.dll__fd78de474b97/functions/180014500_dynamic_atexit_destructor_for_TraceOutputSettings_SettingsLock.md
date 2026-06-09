# _dynamic_atexit_destructor_for__TraceOutputSettings::SettingsLock__

- ea: `0x180014500`
- end: `0x180014525`
- name: `_dynamic_atexit_destructor_for__TraceOutputSettings::SettingsLock__`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014519`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014519`

## pseudocode

```c
void dynamic_atexit_destructor_for__TraceOutputSettings::SettingsLock__()
{
  TraceOutputSettings::SettingsLock = &CSemExclusive::`vftable';
  DeleteCriticalSection(&stru_18001FA50);
}

```

## disassembly

```asm
0x180014500  sub     rsp, 28h
0x180014504  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18001450b  mov     cs:?SettingsLock@TraceOutputSettings@@0VCSemExclusive@@A, rax; CSemExclusive TraceOutputSettings::SettingsLock
0x180014512  lea     rcx, stru_18001FA50; lpCriticalSection
0x180014519  call    cs:__imp_DeleteCriticalSection
0x18001451f  nop
0x180014520  add     rsp, 28h
0x180014524  retn
```
