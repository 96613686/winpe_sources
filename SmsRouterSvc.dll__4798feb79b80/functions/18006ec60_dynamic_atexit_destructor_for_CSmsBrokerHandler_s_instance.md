# _dynamic_atexit_destructor_for__CSmsBrokerHandler::s_instance__

- ea: `0x18006ec60`
- end: `0x18006ec91`
- name: `_dynamic_atexit_destructor_for__CSmsBrokerHandler::s_instance__`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003bc3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006ec85`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006ec85`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void dynamic_atexit_destructor_for__CSmsBrokerHandler::s_instance__()
{
  CSmsBrokerHandler::Uninitialize((CSmsBrokerHandler *)&CSmsBrokerHandler::s_instance);
  off_18008C270 = &Windows::Sms::Common::recursive_mutex::`vftable';
  DeleteCriticalSection(&stru_18008C278);
}

```

## disassembly

```asm
0x18006ec60  sub     rsp, 28h
0x18006ec64  lea     rcx, ?s_instance@CSmsBrokerHandler@@0V1@A; this
0x18006ec6b  call    ?Uninitialize@CSmsBrokerHandler@@QEAAJXZ; CSmsBrokerHandler::Uninitialize(void)
0x18006ec70  lea     rax, ??_7recursive_mutex@Common@Sms@Windows@@6B@; const Windows::Sms::Common::recursive_mutex::`vftable'
0x18006ec77  mov     cs:off_18008C270, rax
0x18006ec7e  lea     rcx, stru_18008C278; lpCriticalSection
0x18006ec85  call    cs:__imp_DeleteCriticalSection
0x18006ec8b  nop
0x18006ec8c  add     rsp, 28h
0x18006ec90  retn
```
