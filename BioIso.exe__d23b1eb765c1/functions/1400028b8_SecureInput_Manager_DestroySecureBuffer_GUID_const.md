# SecureInput::Manager::DestroySecureBuffer(_GUID const &)

- ea: `0x1400028b8`
- end: `0x140002b10`
- name: `?DestroySecureBuffer@Manager@SecureInput@@SAJAEBU_GUID@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(const struct _GUID *Buf1)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001a660`
- `0x140040100`

## callees

- `0x1400028b8`
- `0x140002b20`
- `0x14000a2e4`
- `0x14000a420`
- `0x14000bd48`
- `0x14000d640`
- `0x140013640`
- `0x14001bfb4`
- `0x14001c15c`
- `0x14001c1c4`
- `0x14001cb6c`
- `0x140062c88`
- `0x140062cd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140002975`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140002975`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140002a97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140002a97`

## string_xrefs

- `0x140002904`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`
- `0x140002a7e`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`

## pseudocode

```c

```
