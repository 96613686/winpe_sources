# HrGetOtherUsersStore(IMAPISession *,_SBinary *,IMsgStore * *,_SBinary * *,wchar_t * *,int,_MAPIUID *)

- ea: `0x1406c89f8`
- end: `0x1406c99f0`
- name: `?HrGetOtherUsersStore@@YAJPEAUIMAPISession@@PEAU_SBinary@@PEAPEAUIMsgStore@@PEAPEAU2@PEAPEA_WHPEAU_MAPIUID@@@Z`
- size: `4088`
- prototype: `__int64 __usercall@<rax>(struct IMAPISession *@<rcx>, struct _SBinary *@<rdx>, struct IMsgStore **@<r8>, struct _SBinary **@<r9>, wchar_t **, int, struct _MAPIUID *)`
- caller_count: `5`
- callee_count: `48`
- tags: `broker_com_uri`

## callers

- `0x140698758`
- `0x1406c844c`
- `0x140a23598`
- `0x1413574b8`
- `0x141449230`

## callees

- `0x1400d3df0`
- `0x1400d3e20`
- `0x1400d4d1c`
- `0x1400dd680`
- `0x1400dd710`
- `0x14010a978`
- `0x14010ab1c`
- `0x14015bc30`
- `0x1401c7b50`
- `0x14024ab3c`
- `0x14024b000`
- `0x140295330`
- `0x14029f13c`
- `0x140503f00`
- `0x140549820`
- `0x140572f74`
- `0x14062f110`
- `0x14063fe88`
- `0x14064fc20`
- `0x1406c7178`
- `0x1406c76b4`
- `0x1406c7ec0`
- `0x1406c8070`
- `0x1406c80e8`
- `0x1406c828c`
- `0x1406c82d4`
- `0x1406c89f8`
- `0x1406c99f0`
- `0x1407e99f0`
- `0x1408c6640`
- `0x1409c72fc`
- `0x140a23460`
- `0x140a234fc`
- `0x14143ac0c`
- `0x14143acb0`
- `0x14143ad2c`
- `0x14143ada8`
- `0x14143ae24`
- `0x14143aec0`
- `0x14143af3c`
- `0x14143afb8`
- `0x14143b054`
- `0x14143b0f0`
- `0x14143b204`
- `0x14143b27c`
- `0x14143b314`
- `0x14143b3ac`
- `0x14143b58c`

## import_xrefs

- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c927b`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c9286`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c9294`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c929f`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c9416`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c99d7`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c927b`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c9286`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c9294`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c929f`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c9416`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c99d7`
- `OLMAPI32!__imp_FreeProws` at `0x1406c9089`
- `OLMAPI32!__imp_FreeProws` at `0x1406c9089`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1406c8bc2`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1406c946f`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1406c8bc2`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1406c946f`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c8be5`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c8c05`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c8c29`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c8ca9`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c8ccb`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c933f`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c9377`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c9492`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c96cc`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c96ff`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c971e`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c9734`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c9815`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c9928`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c8be5`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c8c05`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c8c29`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c8ca9`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c8ccb`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c933f`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c9377`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c9492`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c96cc`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c96ff`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c971e`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c9734`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c9815`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c9928`
- `Mso30Win32Client!__imp_?MsoSgnSzCompare@@YAHPEBD0H@Z` at `0x1406c8dbf`
- `Mso30Win32Client!__imp_?MsoSgnSzCompare@@YAHPEBD0H@Z` at `0x1406c98db`
- `Mso30Win32Client!__imp_?MsoSgnSzCompare@@YAHPEBD0H@Z` at `0x1406c8dbf`
- `Mso30Win32Client!__imp_?MsoSgnSzCompare@@YAHPEBD0H@Z` at `0x1406c98db`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@@Z` at `0x1406c8b25`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@@Z` at `0x1406c8d50`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@@Z` at `0x1406c8f2a`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@@Z` at `0x1406c8b25`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@@Z` at `0x1406c8d50`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@@Z` at `0x1406c8f2a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1406c9024`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1406c9024`

## pseudocode

```c

```
