# WaitForDebuggerWorkAround(void *)

- ea: `0x18008d78c`
- end: `0x18008d82c`
- name: `?WaitForDebuggerWorkAround@@YAXPEAX@Z`
- size: `160`
- prototype: `void __fastcall(HANDLE hHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18008d9c0`

## callees

- `0x18005ae90`
- `0x18007638c`
- `0x18008d78c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008d7f5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008d7f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18008d80a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18008d80a`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18008d7be`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18008d7be`

## string_xrefs

- `0x18008d7d0`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`

## pseudocode

```c

```
