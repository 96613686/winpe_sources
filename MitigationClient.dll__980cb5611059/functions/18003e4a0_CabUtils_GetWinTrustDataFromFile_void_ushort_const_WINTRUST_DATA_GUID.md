# CabUtils::GetWinTrustDataFromFile(void *,ushort const *,_WINTRUST_DATA *,_GUID *)

- ea: `0x18003e4a0`
- end: `0x18003e5cb`
- name: `?GetWinTrustDataFromFile@CabUtils@@CAJPEAXPEBGPEAU_WINTRUST_DATA@@PEAU_GUID@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, struct _WINTRUST_DATA *, struct _GUID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18003e60c`
- `0x18003e9ec`

## callees

- `0x18000a6e0`
- `0x18000b2b4`
- `0x18001208c`
- `0x18003e4a0`
- `0x18003e5d4`

## import_xrefs

- `WINTRUST!WinVerifyTrust` at `0x18003e556`
- `WINTRUST!WinVerifyTrust` at `0x18003e556`

## string_xrefs

- `0x18003e560`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`

## pseudocode

```c

```
