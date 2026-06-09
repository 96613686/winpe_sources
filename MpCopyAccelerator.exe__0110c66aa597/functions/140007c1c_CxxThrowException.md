# _CxxThrowException

- ea: `0x140007c1c`
- end: `0x140007cc3`
- name: `_CxxThrowException`
- size: `167`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002e74`
- `0x140002f14`
- `0x140005900`
- `0x140006758`
- `0x140008a3c`
- `0x140008f40`
- `0x1400209d4`

## callees

- `0x140007c1c`
- `0x140024c40`

## import_xrefs

- `ntdll!RtlPcToFileHeader` at `0x140007c6c`
- `ntdll!RtlPcToFileHeader` at `0x140007c6c`
- `KERNEL32!RaiseException` at `0x140007cad`
- `KERNEL32!RaiseException` at `0x140007cad`

## pseudocode

```c

```
