# HrGetOtherUsersStore(IMAPISession *,_SBinary *,IMsgStore * *,_SBinary * *,wchar_t * *,int,_MAPIUID *)

- ea: `0x1406c70d8`
- end: `0x1406c80d0`
- name: `?HrGetOtherUsersStore@@YAJPEAUIMAPISession@@PEAU_SBinary@@PEAPEAUIMsgStore@@PEAPEAU2@PEAPEA_WHPEAU_MAPIUID@@@Z`
- size: `4088`
- prototype: `__int64 __usercall@<rax>(struct IMAPISession *@<rcx>, struct _SBinary *@<rdx>, struct IMsgStore **@<r8>, struct _SBinary **@<r9>, wchar_t **, int, struct _MAPIUID *)`
- caller_count: `5`
- callee_count: `48`
- tags: `broker_com_uri`

## callers

- `0x1406932f8`
- `0x1406c6b2c`
- `0x140a23768`
- `0x141357578`
- `0x1414492f0`

## callees

- `0x1400d3de0`
- `0x1400d3e10`
- `0x1400d4d0c`
- `0x1400dd670`
- `0x1400dd700`
- `0x14010aa08`
- `0x14010abac`
- `0x14015bc70`
- `0x1401c7b70`
- `0x14024b31c`
- `0x14024b7e0`
- `0x140295bd0`
- `0x14029f9dc`
- `0x1405049f0`
- `0x140549920`
- `0x14057363c`
- `0x1406232b0`
- `0x14063b728`
- `0x14064b480`
- `0x1406c5858`
- `0x1406c5d94`
- `0x1406c65a0`
- `0x1406c6750`
- `0x1406c67c8`
- `0x1406c696c`
- `0x1406c69b4`
- `0x1406c70d8`
- `0x1406c80d0`
- `0x1407e9990`
- `0x1408c6620`
- `0x1409c744c`
- `0x140a23630`
- `0x140a236cc`
- `0x14143accc`
- `0x14143ad70`
- `0x14143adec`
- `0x14143ae68`
- `0x14143aee4`
- `0x14143af80`
- `0x14143affc`
- `0x14143b078`
- `0x14143b114`
- `0x14143b1b0`
- `0x14143b2c4`
- `0x14143b33c`
- `0x14143b3d4`
- `0x14143b46c`
- `0x14143b64c`

## import_xrefs

- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c795b`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c7966`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c7974`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c797f`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c7af6`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c80b7`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c795b`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c7966`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c7974`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c797f`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c7af6`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x1406c80b7`
- `OLMAPI32!__imp_FreeProws` at `0x1406c7769`
- `OLMAPI32!__imp_FreeProws` at `0x1406c7769`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1406c72a2`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1406c7b4f`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1406c72a2`
- `Mso98Win32Client!__imp_?HrGetProps@@YAJPEAUIMAPIProp@@PEAPEAU_SPropValue@@KZZ` at `0x1406c7b4f`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c72c5`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c72e5`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7309`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7389`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c73ab`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7a1f`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7a57`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7b72`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7dac`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7ddf`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7dfe`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7e14`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7ef5`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c8008`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c72c5`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c72e5`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7309`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7389`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c73ab`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7a1f`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7a57`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7b72`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7dac`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7ddf`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7dfe`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7e14`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c7ef5`
- `Mso98Win32Client!__imp_?FErrorMTAG@@YA_NK@Z` at `0x1406c8008`
- `Mso30Win32Client!__imp_?MsoSgnSzCompare@@YAHPEBD0H@Z` at `0x1406c749f`
- `Mso30Win32Client!__imp_?MsoSgnSzCompare@@YAHPEBD0H@Z` at `0x1406c7fbb`
- `Mso30Win32Client!__imp_?MsoSgnSzCompare@@YAHPEBD0H@Z` at `0x1406c749f`
- `Mso30Win32Client!__imp_?MsoSgnSzCompare@@YAHPEBD0H@Z` at `0x1406c7fbb`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@@Z` at `0x1406c7205`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@@Z` at `0x1406c7430`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@@Z` at `0x1406c760a`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@@Z` at `0x1406c7205`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@@Z` at `0x1406c7430`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@@Z` at `0x1406c760a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1406c7704`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1406c7704`

## pseudocode

```c

```
