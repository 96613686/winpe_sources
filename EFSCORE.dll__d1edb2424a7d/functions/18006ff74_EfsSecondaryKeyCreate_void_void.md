# EfsSecondaryKeyCreate(void *,void * *)

- ea: `0x18006ff74`
- end: `0x1800700d9`
- name: `?EfsSecondaryKeyCreate@@YAKPEAXPEAPEAX@Z`
- size: `357`
- prototype: `unsigned int __fastcall(BCRYPT_HANDLE hObject, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800364c4`
- `0x18007f60c`
- `0x180080224`

## callees

- `0x180063698`
- `0x18006ff74`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x18006ffc5`
- `bcrypt!BCryptGetProperty` at `0x18007002b`
- `bcrypt!BCryptGetProperty` at `0x18006ffc5`
- `bcrypt!BCryptGetProperty` at `0x18007002b`
- `bcrypt!BCryptFinalizeKeyPair` at `0x180070087`
- `bcrypt!BCryptFinalizeKeyPair` at `0x180070087`
- `bcrypt!BCryptGenerateKeyPair` at `0x18007005c`
- `bcrypt!BCryptGenerateKeyPair` at `0x18007005c`
- `bcrypt!BCryptDestroyKey` at `0x1800700c4`
- `bcrypt!BCryptDestroyKey` at `0x1800700c4`
- `ntdll!RtlNtStatusToDosError` at `0x18006ffd1`
- `ntdll!RtlNtStatusToDosError` at `0x180070037`
- `ntdll!RtlNtStatusToDosError` at `0x180070068`
- `ntdll!RtlNtStatusToDosError` at `0x180070093`
- `ntdll!RtlNtStatusToDosError` at `0x18006ffd1`
- `ntdll!RtlNtStatusToDosError` at `0x180070037`
- `ntdll!RtlNtStatusToDosError` at `0x180070068`
- `ntdll!RtlNtStatusToDosError` at `0x180070093`

## pseudocode

```c

```
