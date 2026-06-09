# Windows::Hash::Implementation::Rtl::CCryptHash::Create(ulong,ulong *)

- ea: `0x1802814d8`
- end: `0x180281934`
- name: `?Create@CCryptHash@Rtl@Implementation@Hash@Windows@@QEAAJKPEAK@Z`
- size: `1116`
- prototype: `__int64 __fastcall(Windows::Hash::Implementation::Rtl::CCryptHash *__hidden this, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180281f94`

## callees

- `0x1800059d0`
- `0x1800692fc`
- `0x180184fc0`
- `0x1801efdc0`
- `0x1801f8c90`
- `0x1802810e8`
- `0x180281320`
- `0x1802813fc`
- `0x1802814d8`
- `0x18028193c`
- `0x1802b1010`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x1802815e8`
- `ntdll!RtlRaiseStatus` at `0x180281709`
- `ntdll!RtlRaiseStatus` at `0x18028178b`
- `ntdll!RtlRaiseStatus` at `0x1802817c9`
- `ntdll!RtlRaiseStatus` at `0x1802815e8`
- `ntdll!RtlRaiseStatus` at `0x180281709`
- `ntdll!RtlRaiseStatus` at `0x18028178b`
- `ntdll!RtlRaiseStatus` at `0x1802817c9`
- `ntdll!RtlLeaveCriticalSection` at `0x1802815d6`
- `ntdll!RtlLeaveCriticalSection` at `0x1802816f3`
- `ntdll!RtlLeaveCriticalSection` at `0x180281779`
- `ntdll!RtlLeaveCriticalSection` at `0x1802817b7`
- `ntdll!RtlLeaveCriticalSection` at `0x1802815d6`
- `ntdll!RtlLeaveCriticalSection` at `0x1802816f3`
- `ntdll!RtlLeaveCriticalSection` at `0x180281779`
- `ntdll!RtlLeaveCriticalSection` at `0x1802817b7`
- `ntdll!RtlEnterCriticalSection` at `0x1802815ae`
- `ntdll!RtlEnterCriticalSection` at `0x1802815ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180281668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180281841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180281668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180281841`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x180281658`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x180281658`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18028182d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18028182d`

## string_xrefs

- `0x180281729`: `Windows::Hash::Implementation::Rtl::CCryptHash::Create`
- `0x18028186c`: `Windows::Hash::Implementation::Rtl::CCryptHash::Create`

## pseudocode

```c

```
