# utility::details::_dynamic_atexit_destructor_for__g_c_localeLock__

- ea: `0x18005e7f0`
- end: `0x18005e7fe`
- name: `utility::details::_dynamic_atexit_destructor_for__g_c_localeLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005e7f7`

## pseudocode

```c
void utility::details::_dynamic_atexit_destructor_for__g_c_localeLock__()
{
  DeleteCriticalSection(&utility::details::g_c_localeLock);
}

```

## disassembly

```asm
0x18005e7f0  lea     rcx, ?g_c_localeLock@details@utility@@3Vcritical_section_impl@1pplx@@A; pplx::details::critical_section_impl utility::details::g_c_localeLock
0x18005e7f7  jmp     cs:__imp_DeleteCriticalSection
```
