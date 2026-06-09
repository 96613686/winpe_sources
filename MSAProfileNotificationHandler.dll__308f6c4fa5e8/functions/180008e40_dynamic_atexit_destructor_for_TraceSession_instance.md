# _dynamic_atexit_destructor_for__TraceSession::_instance__

- ea: `0x180008e40`
- end: `0x180008e64`
- name: `_dynamic_atexit_destructor_for__TraceSession::_instance__`
- size: `36`
- prototype: `void **()`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008e4b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008e4b`

## pseudocode

```c
void **dynamic_atexit_destructor_for__TraceSession::_instance__()
{
  void **result; // rax

  DeleteCriticalSection(&CriticalSection);
  result = &IRegistryFunctions::`vftable';
  off_1800130A8 = &IRegistryFunctions::`vftable';
  return result;
}

```

## disassembly

```asm
0x180008e40  sub     rsp, 28h
0x180008e44  lea     rcx, CriticalSection; lpCriticalSection
0x180008e4b  call    cs:__imp_DeleteCriticalSection
0x180008e51  lea     rax, ??_7IRegistryFunctions@@6B@; const IRegistryFunctions::`vftable'
0x180008e58  mov     cs:off_1800130A8, rax
0x180008e5f  add     rsp, 28h
0x180008e63  retn
```
