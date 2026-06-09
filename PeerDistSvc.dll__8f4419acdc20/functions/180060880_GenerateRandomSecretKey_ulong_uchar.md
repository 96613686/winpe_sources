# GenerateRandomSecretKey(ulong,uchar *)

- ea: `0x180060880`
- end: `0x18006095b`
- name: `?GenerateRandomSecretKey@@YAJKPEAE@Z`
- size: `219`
- prototype: `__int64 __fastcall(ULONG cbBuffer, PUCHAR pbBuffer)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800453d4`

## callees

- `0x180008290`
- `0x180060880`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800608f5`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800608f5`
- `bcrypt!BCryptGenRandom` at `0x1800608d9`
- `bcrypt!BCryptGenRandom` at `0x1800608d9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800608bf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800608bf`

## pseudocode

```c

```
