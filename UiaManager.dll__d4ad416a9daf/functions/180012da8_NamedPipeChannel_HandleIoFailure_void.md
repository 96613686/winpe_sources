# NamedPipeChannel::HandleIoFailure(void)

- ea: `0x180012da8`
- end: `0x180012e02`
- name: `?HandleIoFailure@NamedPipeChannel@@AEAA?AW4IoFailure@1@XZ`
- size: `90`
- prototype: `__int64 __fastcall(NamedPipeChannel *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010558`
- `0x18001900c`

## callees

- `0x180012da8`
- `0x18002a514`
- `0x180075ee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012db1`

## string_xrefs

- `0x180012dd2`: `onecore\windows\accessibletech\uiamanager\dll\namedpipechannel.cpp`

## pseudocode

```c

```
