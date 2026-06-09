# Windows::COM::CopyOut(_LUNICODE_STRING const &,unsigned __int64,wchar_t *,unsigned __int64 *)

- ea: `0x18009676c`
- end: `0x180096858`
- name: `?CopyOut@COM@Windows@@YAJAEBU_LUNICODE_STRING@@_KPEA_WPEA_K@Z`
- size: `236`
- prototype: `int(Windows::COM *__hidden this, const struct _LUNICODE_STRING *, unsigned __int64, wchar_t *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180077d04`
- `0x180077ec4`

## callees

- `0x1800211f0`
- `0x18002d2b0`
- `0x18009676c`
- `0x1800981e0`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18009684b`
- `ntdll!RtlRaiseStatus` at `0x18009684b`

## string_xrefs

- `0x180096819`: `Windows::COM::CopyOut`
- `0x1800967ff`: `onecore\base\wcp\library\copyout.cpp`

## pseudocode

```c

```
