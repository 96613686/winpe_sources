# GetTaskSchedulerTask(ITaskService *,ushort const *,IRegisteredTask * *)

- ea: `0x18010f0cc`
- end: `0x18010f207`
- name: `?GetTaskSchedulerTask@@YAJPEAUITaskService@@PEBGPEAPEAUIRegisteredTask@@@Z`
- size: `315`
- prototype: `int(struct ITaskService *, const unsigned __int16 *, struct IRegisteredTask **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18010f640`

## callees

- `0x180011ea4`
- `0x18001ffa8`
- `0x18010eedc`
- `0x18010f0cc`
- `0x18012d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18010f0f4`
- `OLEAUT32!__imp_SysAllocString` at `0x18010f0f4`

## string_xrefs

- `0x18010f0ed`: `\Microsoft\Windows\Shell\CreateObjectTask`
- `0x18010f114`: `shell\lib\comtaskserverutil.cpp`
- `0x18010f163`: `shell\lib\comtaskserverutil.cpp`
- `0x18010f1b3`: `shell\lib\comtaskserverutil.cpp`

## pseudocode

```c

```
