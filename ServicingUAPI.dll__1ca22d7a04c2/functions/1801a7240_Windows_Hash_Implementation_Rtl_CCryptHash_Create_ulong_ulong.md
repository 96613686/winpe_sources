# Windows::Hash::Implementation::Rtl::CCryptHash::Create(ulong,ulong *)

- ea: `0x1801a7240`
- end: `0x1801a769c`
- name: `?Create@CCryptHash@Rtl@Implementation@Hash@Windows@@QEAAJKPEAK@Z`
- size: `1116`
- prototype: `__int64 __fastcall(Windows::Hash::Implementation::Rtl::CCryptHash *__hidden this, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801a7d04`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x1800497c0`
- `0x180050360`
- `0x180121cd0`
- `0x1801a6e50`
- `0x1801a7088`
- `0x1801a7164`
- `0x1801a7240`
- `0x1801a76a4`
- `0x1801bd010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1801a733e`
- `ntdll!RtlLeaveCriticalSection` at `0x1801a745b`
- `ntdll!RtlLeaveCriticalSection` at `0x1801a74e1`
- `ntdll!RtlLeaveCriticalSection` at `0x1801a751f`
- `ntdll!RtlLeaveCriticalSection` at `0x1801a733e`
- `ntdll!RtlLeaveCriticalSection` at `0x1801a745b`
- `ntdll!RtlLeaveCriticalSection` at `0x1801a74e1`
- `ntdll!RtlLeaveCriticalSection` at `0x1801a751f`
- `ntdll!RtlEnterCriticalSection` at `0x1801a7316`
- `ntdll!RtlEnterCriticalSection` at `0x1801a7316`
- `ntdll!RtlRaiseStatus` at `0x1801a7350`
- `ntdll!RtlRaiseStatus` at `0x1801a7471`
- `ntdll!RtlRaiseStatus` at `0x1801a74f3`
- `ntdll!RtlRaiseStatus` at `0x1801a7531`
- `ntdll!RtlRaiseStatus` at `0x1801a7350`
- `ntdll!RtlRaiseStatus` at `0x1801a7471`
- `ntdll!RtlRaiseStatus` at `0x1801a74f3`
- `ntdll!RtlRaiseStatus` at `0x1801a7531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a73d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a75a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a73d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a75a9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1801a7595`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1801a7595`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x1801a73c0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x1801a73c0`

## string_xrefs

- `0x1801a7491`: `Windows::Hash::Implementation::Rtl::CCryptHash::Create`
- `0x1801a75d4`: `Windows::Hash::Implementation::Rtl::CCryptHash::Create`

## pseudocode

```c

```
