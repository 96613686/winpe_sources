# CWmsHypervWmi::s_EnumRelated(IWbemServices *,IWbemClassObject *,ushort const *,unsigned __int64,long (*)(IWbemServices *,IWbemClassObject *,void *),void *)

- ea: `0x1400436a4`
- end: `0x140043adf`
- name: `?s_EnumRelated@CWmsHypervWmi@@CAJPEAUIWbemServices@@PEAUIWbemClassObject@@PEBG_KP6AJ01PEAX@Z4@Z`
- size: `1083`
- prototype: `__int64 __fastcall(struct IWbemServices *, struct IWbemClassObject *, const unsigned __int16 *, unsigned __int64, int (*)(struct IWbemServices *, struct IWbemClassObject *, void *), void *)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x14003f220`
- `0x140043af0`
- `0x140043b30`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x1400033e8`
- `0x1400436a4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14004375c`
- `KERNEL32!IsDebuggerPresent` at `0x14004383b`
- `KERNEL32!IsDebuggerPresent` at `0x1400438cf`
- `KERNEL32!IsDebuggerPresent` at `0x140043946`
- `KERNEL32!IsDebuggerPresent` at `0x1400439f3`
- `KERNEL32!IsDebuggerPresent` at `0x14004375c`
- `KERNEL32!IsDebuggerPresent` at `0x14004383b`
- `KERNEL32!IsDebuggerPresent` at `0x1400438cf`
- `KERNEL32!IsDebuggerPresent` at `0x140043946`
- `KERNEL32!IsDebuggerPresent` at `0x1400439f3`
- `OLEAUT32!__imp_SysAllocString` at `0x1400438f2`
- `OLEAUT32!__imp_SysAllocString` at `0x1400438f2`
- `OLEAUT32!__imp_SysFreeString` at `0x140043a82`
- `OLEAUT32!__imp_SysFreeString` at `0x140043a82`
- `OLEAUT32!__imp_SysStringLen` at `0x1400437c7`
- `OLEAUT32!__imp_SysStringLen` at `0x1400437c7`
- `OLEAUT32!__imp_VariantInit` at `0x1400436ed`
- `OLEAUT32!__imp_VariantInit` at `0x1400436ed`
- `OLEAUT32!__imp_VariantClear` at `0x140043a8c`
- `OLEAUT32!__imp_VariantClear` at `0x140043a8c`

## string_xrefs

- `0x1400436ff`: `__PATH`
- `0x1400437ff`: `pszAssociatorsCommand`
- `0x140043843`: `pszAssociatorsCommand`
- `0x14004390a`: `bstrAssociatorsCommand`
- `0x14004394e`: `bstrAssociatorsCommand`

## pseudocode

```c

```
