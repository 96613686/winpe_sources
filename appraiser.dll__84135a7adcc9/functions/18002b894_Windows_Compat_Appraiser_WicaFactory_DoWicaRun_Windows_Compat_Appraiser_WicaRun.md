# Windows::Compat::Appraiser::WicaFactory::DoWicaRun(Windows::Compat::Appraiser::WicaRun)

- ea: `0x18002b894`
- end: `0x18002bc82`
- name: `?DoWicaRun@WicaFactory@Appraiser@Compat@Windows@@SAJUWicaRun@234@@Z`
- size: `1006`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044030`
- `0x18005bc4c`
- `0x180064f4c`

## callees

- `0x180008570`
- `0x1800151f4`
- `0x18001b324`
- `0x18001b468`
- `0x180026040`
- `0x180028a24`
- `0x18002ae9c`
- `0x18002b894`
- `0x18002c6fc`
- `0x18002d030`
- `0x18002d884`
- `0x18002ebb8`
- `0x18002efa4`
- `0x18002f5b8`
- `0x1800301d0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002baf8`
- `ntdll!RtlLeaveCriticalSection` at `0x18002baf8`
- `ntdll!RtlEnterCriticalSection` at `0x18002badb`
- `ntdll!RtlEnterCriticalSection` at `0x18002badb`
- `KERNEL32!InitOnceExecuteOnce` at `0x18002bb12`
- `KERNEL32!InitOnceExecuteOnce` at `0x18002bb12`
- `KERNEL32!IsWow64Process` at `0x18002b956`
- `KERNEL32!IsWow64Process` at `0x18002b956`
- `KERNEL32!GetCurrentProcess` at `0x18002b948`
- `KERNEL32!GetCurrentProcess` at `0x18002b948`
- `KERNEL32!GetProcessHeap` at `0x18002b8db`
- `KERNEL32!GetProcessHeap` at `0x18002b8db`
- `KERNEL32!GetLastError` at `0x18002b964`
- `KERNEL32!GetLastError` at `0x18002b983`
- `KERNEL32!GetLastError` at `0x18002b964`
- `KERNEL32!GetLastError` at `0x18002b983`

## string_xrefs

- `0x18002b928`: `onecore\base\appcompat\appraiser\engine\engine.cpp`
- `0x18002b91e`: `Windows::Compat::Appraiser::WicaFactory::DoWicaRun`
- `0x18002b9a4`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18002b99d`: `Windows::Compat::Appraiser::Utilities::CheckWow64`

## pseudocode

```c

```
