# NVMeStorageHealthMonitor::NVMeStorageHealthMonitor(void)

- ea: `0x18006f944`
- end: `0x18006f9d6`
- name: `??0NVMeStorageHealthMonitor@@QEAA@XZ`
- size: `146`
- prototype: `NVMeStorageHealthMonitor *__fastcall(NVMeStorageHealthMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180020140`
- `0x180026250`

## callees

- `0x180003028`
- `0x180057218`
- `0x18006f944`
- `0x180070164`
- `0x1800702f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f9a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f9a0`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtSubscribe` at `0x18006f992`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtSubscribe` at `0x18006f992`

## string_xrefs

- `0x18006f976`: `<QueryList>         <Query Id = "0" Path = "Microsoft-Windows-Storage-Storport/Health">              <Select Path = "Microsoft-Windows-Storage-Storport/Health"> * [System[Provider[@Name = 'Microsoft-Windows-StorPort'] and (EventID = 512)]]</Select>         </Query>     </QueryList>`

## pseudocode

```c

```
