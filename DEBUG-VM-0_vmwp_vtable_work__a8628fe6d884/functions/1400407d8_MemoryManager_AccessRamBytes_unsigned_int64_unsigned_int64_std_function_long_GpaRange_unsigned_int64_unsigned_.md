# MemoryManager::AccessRamBytes(unsigned __int64,unsigned __int64,std::function<long (GpaRange *,unsigned __int64,unsigned __int64)> const &)

- ea: `0x1400407d8`
- end: `0x140040a43`
- name: `?AccessRamBytes@MemoryManager@@AEAAJ_K0AEBV?$function@$$A6AJPEAVGpaRange@@_K1@Z@std@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400edee0`

## callees

- `0x1400407d8`
- `0x140040fd8`
- `0x14009d7ac`
- `0x140132940`
- `0x1402c2010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140040a2b`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140040a2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004086e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004086e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140040843`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140040843`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400409af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400409af`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400409e2`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400409e2`

## string_xrefs

- `0x140040a19`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```
