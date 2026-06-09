# HrCreateContactRaw(IMAPISession *,_MAPIUID *,_SBinary *,HWND__ *,IAddrBook *,int,wchar_t const *,IDispatch *,IDispatch * *)

- ea: `0x141736608`
- end: `0x141737488`
- name: `?HrCreateContactRaw@@YAJPEAUIMAPISession@@PEAU_MAPIUID@@PEAU_SBinary@@PEAUHWND__@@PEAUIAddrBook@@HPEB_WPEAUIDispatch@@PEAPEAU6@@Z`
- size: `3712`
- prototype: `__int64 __fastcall(struct IMAPISession *, struct _MAPIUID *, struct _SBinary *, HWND, struct IAddrBook *, int, const wchar_t *, struct IDispatch *, struct IDispatch **)`
- caller_count: `2`
- callee_count: `30`
- tags: `installer_update`

## callers

- `0x141023860`
- `0x141736484`

## callees

- `0x140069414`
- `0x1400dd0ac`
- `0x1400dd620`
- `0x1400dd670`
- `0x1400dd700`
- `0x14010aa08`
- `0x14010abac`
- `0x14010ac00`
- `0x14010addc`
- `0x140122a44`
- `0x140219f58`
- `0x1402a0170`
- `0x1402c4258`
- `0x1402c43f8`
- `0x1402d4114`
- `0x14034cb5c`
- `0x1405049f0`
- `0x14062950c`
- `0x14062ad6c`
- `0x1407058d8`
- `0x1407e9990`
- `0x1413715f0`
- `0x14165cd10`
- `0x141736608`
- `0x14173866c`
- `0x1417c9b8c`
- `0x1417f3450`
- `0x1417fc604`
- `0x14198ffc0`
- `0x141d3a220`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141736f4a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141736fbd`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141736f4a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141736fbd`
- `OLMAPI32!FValidEmsabpEntryIDBin` at `0x1417366d1`
- `OLMAPI32!FValidEmsabpEntryIDBin` at `0x1417366d1`
- `OLMAPI32!HrIdnToDisplayFormSMTP` at `0x141736ed5`
- `OLMAPI32!HrIdnToDisplayFormSMTP` at `0x141736f0f`
- `OLMAPI32!HrIdnToDisplayFormSMTP` at `0x141736ed5`
- `OLMAPI32!HrIdnToDisplayFormSMTP` at `0x141736f0f`
- `OLMAPI32!HrOpenABEntryWithProviderUID` at `0x141736763`
- `OLMAPI32!HrOpenABEntryWithProviderUID` at `0x141736763`
- `OLMAPI32!EtwTraceErrorTag` at `0x14173671d`
- `OLMAPI32!EtwTraceErrorTag` at `0x1417368bc`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736912`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736d5c`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736f34`
- `OLMAPI32!EtwTraceErrorTag` at `0x14173704e`
- `OLMAPI32!EtwTraceErrorTag` at `0x14173711f`
- `OLMAPI32!EtwTraceErrorTag` at `0x1417373cb`
- `OLMAPI32!EtwTraceErrorTag` at `0x14173671d`
- `OLMAPI32!EtwTraceErrorTag` at `0x1417368bc`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736912`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736d5c`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736f34`
- `OLMAPI32!EtwTraceErrorTag` at `0x14173704e`
- `OLMAPI32!EtwTraceErrorTag` at `0x14173711f`
- `OLMAPI32!EtwTraceErrorTag` at `0x1417373cb`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14173712f`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x141737277`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14173712f`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x141737277`
- `OLMAPI32!__imp_PpropFindProp` at `0x141736e63`
- `OLMAPI32!__imp_PpropFindProp` at `0x141736e7a`
- `OLMAPI32!__imp_PpropFindProp` at `0x1417372dd`
- `OLMAPI32!__imp_PpropFindProp` at `0x141736e63`
- `OLMAPI32!__imp_PpropFindProp` at `0x141736e7a`
- `OLMAPI32!__imp_PpropFindProp` at `0x1417372dd`
- `OLEAUT32!__imp_VariantInit` at `0x1417372fe`
- `OLEAUT32!__imp_VariantInit` at `0x1417372fe`
- `USER32!SetWindowPos` at `0x1417373bc`
- `USER32!SetWindowPos` at `0x1417373bc`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1417367c9`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1417371a3`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1417367c9`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1417371a3`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x141736e8e`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x141736ea8`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x141736e8e`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x141736ea8`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x141736b6c`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x141737215`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x141736b6c`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x141737215`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141737403`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141737403`
- `Mso20Win32Client!__imp_?MsoFRegValueExists@@YA_NPEBU_msoreg@@@Z` at `0x141736b5b`
- `Mso20Win32Client!__imp_?MsoFRegValueExists@@YA_NPEBU_msoreg@@@Z` at `0x141737204`
- `Mso20Win32Client!__imp_?MsoFRegValueExists@@YA_NPEBU_msoreg@@@Z` at `0x141736b5b`
- `Mso20Win32Client!__imp_?MsoFRegValueExists@@YA_NPEBU_msoreg@@@Z` at `0x141737204`
- `ExSec32!HrMAPISecUserX509FromSigInfo` at `0x1417371e8`
- `ExSec32!HrMAPISecUserX509FromSigInfo` at `0x1417371e8`
- `ExSec32!HrMergeMAPISecUserX509CertAndABX509Cert` at `0x141736b29`
- `ExSec32!HrMergeMAPISecUserX509CertAndABX509Cert` at `0x141736b29`
- `ExSec32!HrProcessUserX509` at `0x141736ad9`
- `ExSec32!HrProcessUserX509` at `0x141736ad9`

## pseudocode

```c

```
