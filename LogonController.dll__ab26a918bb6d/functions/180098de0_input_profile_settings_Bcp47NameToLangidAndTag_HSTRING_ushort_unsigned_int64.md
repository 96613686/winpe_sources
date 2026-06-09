# input_profile_settings::Bcp47NameToLangidAndTag(HSTRING__ *,ushort *,unsigned __int64 *)

- ea: `0x180098de0`
- end: `0x180098edf`
- name: `?Bcp47NameToLangidAndTag@input_profile_settings@@YAJPEAUHSTRING__@@PEAGPEA_K@Z`
- size: `255`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180099fc4`

## callees

- `0x18002547c`
- `0x180085c90`
- `0x180096208`
- `0x180098de0`

## import_xrefs

- `KERNEL32!LocaleNameToLCID` at `0x180098e5c`
- `KERNEL32!LocaleNameToLCID` at `0x180098e5c`
- `KERNEL32!GetLastError` at `0x180098e85`
- `KERNEL32!GetLastError` at `0x180098e85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180098e51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180098e51`
- `Bcp47Langs!CompactTagFromBcp47Internal` at `0x180098ea8`
- `Bcp47Langs!CompactTagFromBcp47Internal` at `0x180098ea8`
- `Bcp47Langs!LcidFromBcp47` at `0x180098e23`
- `Bcp47Langs!LcidFromBcp47` at `0x180098e23`

## pseudocode

```c

```
