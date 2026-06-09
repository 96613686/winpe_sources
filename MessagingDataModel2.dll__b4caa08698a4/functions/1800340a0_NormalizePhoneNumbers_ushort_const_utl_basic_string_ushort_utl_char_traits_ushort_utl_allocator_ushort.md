# NormalizePhoneNumbers(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x1800340a0`
- end: `0x18003424f`
- name: `?NormalizePhoneNumbers@@YAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x180033578`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18000b7d4`
- `0x18000b7fc`
- `0x180028108`
- `0x18002ba74`
- `0x18002bb1c`
- `0x180033c28`
- `0x1800340a0`
- `0x1800c6940`

## import_xrefs

- `msvcrt!towlower` at `0x18003414f`
- `msvcrt!towlower` at `0x18003414f`
- `msvcrt!iswdigit` at `0x180034161`
- `msvcrt!iswdigit` at `0x180034161`
- `PhoneUtil!IsDialableChar` at `0x18003418b`
- `PhoneUtil!IsDialableChar` at `0x18003418b`
- `PhoneUtil!GetCchTailMin` at `0x1800341aa`
- `PhoneUtil!GetCchTailMin` at `0x1800341aa`

## string_xrefs

- `0x180034214`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`

## pseudocode

```c

```
