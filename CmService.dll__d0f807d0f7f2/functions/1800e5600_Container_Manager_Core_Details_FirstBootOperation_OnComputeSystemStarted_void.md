# Container::Manager::Core::Details::FirstBootOperation::OnComputeSystemStarted(void)

- ea: `0x1800e5600`
- end: `0x1800e6b75`
- name: `?OnComputeSystemStarted@FirstBootOperation@Details@Core@Manager@Container@@AEAAJXZ`
- size: `5493`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::FirstBootOperation *__hidden this)`
- caller_count: `1`
- callee_count: `40`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e6b80`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180005704`
- `0x180007b48`
- `0x180007dd4`
- `0x180008bf0`
- `0x180009ba0`
- `0x18000b49c`
- `0x18000da88`
- `0x18000dad8`
- `0x180015238`
- `0x180016718`
- `0x180016774`
- `0x18002dc8c`
- `0x18002fae4`
- `0x18002fc34`
- `0x18003134c`
- `0x180031564`
- `0x18003943c`
- `0x180049a0c`
- `0x180049ce4`
- `0x180049e5c`
- `0x18004ee38`
- `0x18004f1f4`
- `0x1800785d4`
- `0x1800a3388`
- `0x1800e5600`
- `0x1800e70ac`
- `0x1800e71e0`
- `0x1800e7314`
- `0x1800e7638`
- `0x180110cc8`
- `0x18011e928`
- `0x180122b4c`
- `0x18012312c`
- `0x180123250`
- `0x180123878`
- `0x180125d00`
- `0x1801929e4`
- `0x180193394`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x1800e5be4`
- `ntdll!RtlDoesFileExists_U` at `0x1800e5be4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e57f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e5a0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e57f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e5a0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e576a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e597c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6756`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e576a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e597c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6756`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e577e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e5990`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e676a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e577e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e5990`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e676a`
- `RPCRT4!RpcBindingFree` at `0x1800e5743`
- `RPCRT4!RpcBindingFree` at `0x1800e5955`
- `RPCRT4!RpcBindingFree` at `0x1800e5b6f`
- `RPCRT4!RpcBindingFree` at `0x1800e5c6a`
- `RPCRT4!RpcBindingFree` at `0x1800e5d35`
- `RPCRT4!RpcBindingFree` at `0x1800e5dfc`
- `RPCRT4!RpcBindingFree` at `0x1800e5ee1`
- `RPCRT4!RpcBindingFree` at `0x1800e5fbe`
- `RPCRT4!RpcBindingFree` at `0x1800e61be`
- `RPCRT4!RpcBindingFree` at `0x1800e62a3`
- `RPCRT4!RpcBindingFree` at `0x1800e639f`
- `RPCRT4!RpcBindingFree` at `0x1800e6487`
- `RPCRT4!RpcBindingFree` at `0x1800e656e`
- `RPCRT4!RpcBindingFree` at `0x1800e672f`
- `RPCRT4!RpcBindingFree` at `0x1800e6896`
- `RPCRT4!RpcBindingFree` at `0x1800e6a2d`
- `RPCRT4!RpcBindingFree` at `0x1800e6b37`
- `RPCRT4!RpcBindingFree` at `0x1800e5743`
- `RPCRT4!RpcBindingFree` at `0x1800e5955`
- `RPCRT4!RpcBindingFree` at `0x1800e5b6f`
- `RPCRT4!RpcBindingFree` at `0x1800e5c6a`
- `RPCRT4!RpcBindingFree` at `0x1800e5d35`
- `RPCRT4!RpcBindingFree` at `0x1800e5dfc`
- `RPCRT4!RpcBindingFree` at `0x1800e5ee1`
- `RPCRT4!RpcBindingFree` at `0x1800e5fbe`
- `RPCRT4!RpcBindingFree` at `0x1800e61be`
- `RPCRT4!RpcBindingFree` at `0x1800e62a3`
- `RPCRT4!RpcBindingFree` at `0x1800e639f`
- `RPCRT4!RpcBindingFree` at `0x1800e6487`
- `RPCRT4!RpcBindingFree` at `0x1800e656e`
- `RPCRT4!RpcBindingFree` at `0x1800e672f`
- `RPCRT4!RpcBindingFree` at `0x1800e6896`
- `RPCRT4!RpcBindingFree` at `0x1800e6a2d`
- `RPCRT4!RpcBindingFree` at `0x1800e6b37`

## string_xrefs

- `0x1800e62e0`: `C:\Windows\System32\wpr.exe -boottrace -addboot `
- `0x1800e5867`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x1800e5a85`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`

## pseudocode

```c

```
