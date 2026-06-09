# AppReadiness::Logging::EnableLogging(void)

- ea: `0x18005fb48`
- end: `0x18005fd38`
- name: `?EnableLogging@Logging@AppReadiness@@YAXXZ`
- size: `496`
- prototype: `void __fastcall(AppReadiness::Logging *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034620`

## callees

- `0x18001be10`
- `0x18003e210`
- `0x18003eca8`
- `0x18005f9c0`
- `0x18005fb48`
- `0x18005fd40`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18005fc16`
- `ntdll!NtQuerySystemInformation` at `0x18005fc16`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x18005fcb3`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x18005fcb3`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18005fd02`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18005fd02`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18005fc7c`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18005fc7c`

## string_xrefs

- `0x18005fbb7`: `Software\Microsoft\Windows\CurrentVersion\AppReadiness`
- `0x18005fc44`: `AppReadiness.etl`

## pseudocode

```c

```
