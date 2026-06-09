# UlpComputeSecureHash

- ea: `0x1400be2e4`
- end: `0x1400be497`
- name: `UlpComputeSecureHash`
- size: `435`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, ULONG cbOutput)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400be1d8`

## callees

- `0x1400be2e4`
- `0x140167810`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x1400be392`
- `ntoskrnl!ExAllocatePool3` at `0x1400be392`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400be46a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400be46a`
- `ksecdd!BCryptCreateHash` at `0x1400be3d6`
- `ksecdd!BCryptCreateHash` at `0x1400be3d6`
- `ksecdd!BCryptHashData` at `0x1400be3f6`
- `ksecdd!BCryptHashData` at `0x1400be3f6`
- `ksecdd!BCryptDestroyHash` at `0x1400be432`
- `ksecdd!BCryptDestroyHash` at `0x1400be432`
- `ksecdd!BCryptFinishHash` at `0x1400be41a`
- `ksecdd!BCryptFinishHash` at `0x1400be41a`
- `ksecdd!BCryptGetProperty` at `0x1400be34a`
- `ksecdd!BCryptGetProperty` at `0x1400be34a`

## pseudocode

```c

```
