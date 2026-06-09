# CCrashOnLaunch::Initialize(WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)

- ea: `0x140051e60`
- end: `0x140051fc6`
- name: `?Initialize@CCrashOnLaunch@@UEAAJPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(CCrashOnLaunch *__hidden this, struct WER_PLUGIN_INIT_IN *, unsigned int, HINSTANCE)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1400166ec`
- `0x140051e60`
- `0x140051fcc`
- `0x14005f564`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140051f26`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140051f26`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140051f3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140051f3a`
- `ntdll!DbgPrint` at `0x140051fa1`
- `ntdll!DbgPrint` at `0x140051fa1`

## pseudocode

```c

```
