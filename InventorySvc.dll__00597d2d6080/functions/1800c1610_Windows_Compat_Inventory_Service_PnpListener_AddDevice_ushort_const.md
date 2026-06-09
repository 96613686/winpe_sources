# Windows::Compat::Inventory::Service::PnpListener::AddDevice(ushort const *)

- ea: `0x1800c1610`
- end: `0x1800c179d`
- name: `?AddDevice@PnpListener@Service@Inventory@Compat@Windows@@QEAAXPEBG@Z`
- size: `397`
- prototype: `void __fastcall(RTL_SRWLOCK *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c22d0`

## callees

- `0x180002bf0`
- `0x180002c40`
- `0x180006a04`
- `0x1800074f0`
- `0x180009060`
- `0x1800108d4`
- `0x1800c1610`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800c16d1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800c16d1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800c1649`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800c1666`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800c1649`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800c1666`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c1680`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c1680`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c1742`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c1742`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1738`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1738`

## string_xrefs

- `0x1800c1775`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800c178b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c

```
