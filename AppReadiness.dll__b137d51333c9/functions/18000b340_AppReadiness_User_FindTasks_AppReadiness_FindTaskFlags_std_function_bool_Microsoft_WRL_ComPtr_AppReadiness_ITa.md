# AppReadiness::User::FindTasks(AppReadiness::FindTaskFlags,std::function<bool (Microsoft::WRL::ComPtr<AppReadiness::ITask> const &)> const &)

- ea: `0x18000b340`
- end: `0x18000b45b`
- name: `?FindTasks@User@AppReadiness@@IEBA?AV?$vector@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@@std@@@std@@W4FindTaskFlags@2@AEBV?$function@$$A6A_NAEBV?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@@Z@4@@Z`
- size: `283`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a520`
- `0x18000a680`
- `0x18000adb0`
- `0x18003448c`
- `0x180039840`
- `0x18003cd90`

## callees

- `0x180002a48`
- `0x18000b340`
- `0x18000b464`
- `0x18000d7d0`
- `0x18004a2b8`
- `0x180079010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000b454`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000b454`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b3fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b3fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b384`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b384`

## pseudocode

```c

```
