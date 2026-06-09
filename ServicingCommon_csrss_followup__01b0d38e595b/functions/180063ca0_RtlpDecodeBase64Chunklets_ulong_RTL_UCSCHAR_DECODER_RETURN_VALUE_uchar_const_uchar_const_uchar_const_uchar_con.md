# RtlpDecodeBase64Chunklets(ulong,_RTL_UCSCHAR_DECODER_RETURN_VALUE (*)(uchar const *,uchar const *),uchar const *,uchar const *,_RTL_SMART_LBLOB_WRITING_CONTEXT &)

- ea: `0x180063ca0`
- end: `0x1800641be`
- name: `?RtlpDecodeBase64Chunklets@@YAJKP6A?AU_RTL_UCSCHAR_DECODER_RETURN_VALUE@@PEBE0@Z00AEAU_RTL_SMART_LBLOB_WRITING_CONTEXT@@@Z`
- size: `1310`
- prototype: `int(unsigned int, struct _RTL_UCSCHAR_DECODER_RETURN_VALUE (__high *)(const unsigned __int8 *, const unsigned __int8 *), const unsigned __int8 *, const unsigned __int8 *, struct _RTL_SMART_LBLOB_WRITING_CONTEXT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180064c40`
- `0x180064e60`

## callees

- `0x180017af0`
- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x1800639f0`
- `0x180063ca0`
- `0x1800641c4`
- `0x18009e020`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180064125`
- `ntdll!RtlRaiseStatus` at `0x180064125`

## string_xrefs

- `0x180063fc7`: `(BytesToCopy == 3) || (Cursor == OnePastEnd)`

## pseudocode

```c

```
