# CApplication::GetSmtcProcesses(std::forward_list<wil::com_ptr_t<CProcess,wil::err_returncode_policy>,std::allocator<wil::com_ptr_t<CProcess,wil::err_returncode_policy>>> *,uint *)

- ea: `0x180007da0`
- end: `0x180007e55`
- name: `?GetSmtcProcesses@CApplication@@QEAAJPEAV?$forward_list@V?$com_ptr_t@VCProcess@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCProcess@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@PEAI@Z`
- size: `181`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007bac`
- `0x18002bfac`

## callees

- `0x180007b60`
- `0x180007da0`
- `0x18001b750`
- `0x180037e60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007dbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007dbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e38`

## pseudocode

```c

```
