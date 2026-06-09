# WaasMedic::CWaasMedic::GetTimeState(ushort const *,_FILETIME &,bool &)

- ea: `0x180067924`
- end: `0x180067a09`
- name: `?GetTimeState@CWaasMedic@WaasMedic@@AEAAJPEBGAEAU_FILETIME@@AEA_N@Z`
- size: `229`
- prototype: `int(WaasMedic::CWaasMedic *__hidden this, const unsigned __int16 *, struct _FILETIME *, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180067204`
- `0x1800675b8`

## callees

- `0x180029d0c`
- `0x18002e81c`
- `0x1800639bc`
- `0x180067924`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18006793f`
- `OLEAUT32!__imp_VariantInit` at `0x18006793f`
- `OLEAUT32!__imp_VariantClear` at `0x1800679eb`
- `OLEAUT32!__imp_VariantClear` at `0x1800679eb`

## string_xrefs

- `0x1800679bb`: `Error reading %s using State provider value or it does not exist.`

## pseudocode

```c

```
