# HrCreateContactRaw(IMAPISession *,_MAPIUID *,_SBinary *,HWND__ *,IAddrBook *,int,wchar_t const *,IDispatch *,IDispatch * *)

- ea: `0x141736548`
- end: `0x1417373c8`
- name: `?HrCreateContactRaw@@YAJPEAUIMAPISession@@PEAU_MAPIUID@@PEAU_SBinary@@PEAUHWND__@@PEAUIAddrBook@@HPEB_WPEAUIDispatch@@PEAPEAU6@@Z`
- size: `3712`
- prototype: `__int64 __fastcall(struct IMAPISession *, struct _MAPIUID *, struct _SBinary *, HWND, struct IAddrBook *, int, const wchar_t *, struct IDispatch *, struct IDispatch **)`
- caller_count: `2`
- callee_count: `30`
- tags: `installer_update`

## callers

- `0x1410237a0`
- `0x1417363c4`

## callees

- `0x1400693c4`
- `0x1400dd0bc`
- `0x1400dd630`
- `0x1400dd680`
- `0x1400dd710`
- `0x14010a978`
- `0x14010ab1c`
- `0x14010ab70`
- `0x14010ad4c`
- `0x140122a04`
- `0x140219778`
- `0x14029f8d0`
- `0x1402c39b8`
- `0x1402c3b58`
- `0x1402d3894`
- `0x14034c22c`
- `0x140503f00`
- `0x14062f0e8`
- `0x1406311b8`
- `0x1407e4558`
- `0x1407e99f0`
- `0x141371530`
- `0x14165cc50`
- `0x141736548`
- `0x1417385ac`
- `0x1417c9acc`
- `0x1417f3390`
- `0x1417fc544`
- `0x14198ff00`
- `0x141d3a160`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141736e8a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141736efd`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141736e8a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141736efd`
- `OLMAPI32!FValidEmsabpEntryIDBin` at `0x141736611`
- `OLMAPI32!FValidEmsabpEntryIDBin` at `0x141736611`
- `OLMAPI32!HrIdnToDisplayFormSMTP` at `0x141736e15`
- `OLMAPI32!HrIdnToDisplayFormSMTP` at `0x141736e4f`
- `OLMAPI32!HrIdnToDisplayFormSMTP` at `0x141736e15`
- `OLMAPI32!HrIdnToDisplayFormSMTP` at `0x141736e4f`
- `OLMAPI32!HrOpenABEntryWithProviderUID` at `0x1417366a3`
- `OLMAPI32!HrOpenABEntryWithProviderUID` at `0x1417366a3`
- `OLMAPI32!EtwTraceErrorTag` at `0x14173665d`
- `OLMAPI32!EtwTraceErrorTag` at `0x1417367fc`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736852`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736c9c`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736e74`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736f8e`
- `OLMAPI32!EtwTraceErrorTag` at `0x14173705f`
- `OLMAPI32!EtwTraceErrorTag` at `0x14173730b`
- `OLMAPI32!EtwTraceErrorTag` at `0x14173665d`
- `OLMAPI32!EtwTraceErrorTag` at `0x1417367fc`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736852`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736c9c`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736e74`
- `OLMAPI32!EtwTraceErrorTag` at `0x141736f8e`
- `OLMAPI32!EtwTraceErrorTag` at `0x14173705f`
- `OLMAPI32!EtwTraceErrorTag` at `0x14173730b`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14173706f`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1417371b7`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x14173706f`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1417371b7`
- `OLMAPI32!__imp_PpropFindProp` at `0x141736da3`
- `OLMAPI32!__imp_PpropFindProp` at `0x141736dba`
- `OLMAPI32!__imp_PpropFindProp` at `0x14173721d`
- `OLMAPI32!__imp_PpropFindProp` at `0x141736da3`
- `OLMAPI32!__imp_PpropFindProp` at `0x141736dba`
- `OLMAPI32!__imp_PpropFindProp` at `0x14173721d`
- `OLEAUT32!__imp_VariantInit` at `0x14173723e`
- `OLEAUT32!__imp_VariantInit` at `0x14173723e`
- `USER32!SetWindowPos` at `0x1417372fc`
- `USER32!SetWindowPos` at `0x1417372fc`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x141736709`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1417370e3`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x141736709`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1417370e3`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x141736dce`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x141736de8`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x141736dce`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x141736de8`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x141736aac`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x141737155`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x141736aac`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x141737155`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141737343`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141737343`
- `Mso20Win32Client!__imp_?MsoFRegValueExists@@YA_NPEBU_msoreg@@@Z` at `0x141736a9b`
- `Mso20Win32Client!__imp_?MsoFRegValueExists@@YA_NPEBU_msoreg@@@Z` at `0x141737144`
- `Mso20Win32Client!__imp_?MsoFRegValueExists@@YA_NPEBU_msoreg@@@Z` at `0x141736a9b`
- `Mso20Win32Client!__imp_?MsoFRegValueExists@@YA_NPEBU_msoreg@@@Z` at `0x141737144`
- `ExSec32!HrMAPISecUserX509FromSigInfo` at `0x141737128`
- `ExSec32!HrMAPISecUserX509FromSigInfo` at `0x141737128`
- `ExSec32!HrMergeMAPISecUserX509CertAndABX509Cert` at `0x141736a69`
- `ExSec32!HrMergeMAPISecUserX509CertAndABX509Cert` at `0x141736a69`
- `ExSec32!HrProcessUserX509` at `0x141736a19`
- `ExSec32!HrProcessUserX509` at `0x141736a19`

## pseudocode

```c

```
