# Windows::Compat::Appraiser::Utilities::RunFunctionInSeparateProcess(void * *,bool,bool,ushort const *,ushort const *,ushort const *)

- ea: `0x180090b64`
- end: `0x180090e6b`
- name: `?RunFunctionInSeparateProcess@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAX_N1PEBG22@Z`
- size: `775`
- prototype: `__int64 __fastcall(void **, __int64, __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180090ea4`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x180011d94`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180087108`
- `0x180090b64`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x180090d35`
- `KERNEL32!CreateProcessW` at `0x180090d35`
- `KERNEL32!CloseHandle` at `0x180090e35`
- `KERNEL32!CloseHandle` at `0x180090e45`
- `KERNEL32!CloseHandle` at `0x180090e35`
- `KERNEL32!CloseHandle` at `0x180090e45`
- `KERNEL32!GetLastError` at `0x180090d3f`
- `KERNEL32!GetLastError` at `0x180090ddd`
- `KERNEL32!GetLastError` at `0x180090dfc`
- `KERNEL32!GetLastError` at `0x180090d3f`
- `KERNEL32!GetLastError` at `0x180090ddd`
- `KERNEL32!GetLastError` at `0x180090dfc`
- `KERNEL32!WaitForSingleObject` at `0x180090d8a`
- `KERNEL32!WaitForSingleObject` at `0x180090d8a`

## string_xrefs

- `0x180090c4e`: `GeneralTel.dll`
- `0x180090be0`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180090c13`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180090bd0`: `Expand Directory failed: [0x%x].`
- `0x180090c1e`: `Expand Directory failed: [0x%x].`
- `0x180090be7`: `Windows::Compat::Appraiser::Utilities::RunFunctionInSeparateProcess`
- `0x180090c0c`: `Windows::Compat::Appraiser::Utilities::RunFunctionInSeparateProcess`
- `0x180090bb0`: `%WINDIR%\system32\compattelrunner.exe`
- `0x180090dc3`: `Waiting on process %ls with command %ls failed: [%d].`

## pseudocode

```c

```
