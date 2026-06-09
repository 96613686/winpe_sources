# CCrashOnLaunch::Initialize(WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)

- ea: `0x14004e7f0`
- end: `0x14004e943`
- name: `?Initialize@CCrashOnLaunch@@UEAAJPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z`
- size: `339`
- prototype: `__int64 __fastcall(CCrashOnLaunch *__hidden this, struct WER_PLUGIN_INIT_IN *, unsigned int, HINSTANCE)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140015b40`
- `0x14004e7f0`
- `0x14004e94c`
- `0x14005b7c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14004e8b6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14004e8b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14004e8c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14004e8c4`
- `ntdll!DbgPrint` at `0x14004e925`
- `ntdll!DbgPrint` at `0x14004e925`

## pseudocode

```c

```
