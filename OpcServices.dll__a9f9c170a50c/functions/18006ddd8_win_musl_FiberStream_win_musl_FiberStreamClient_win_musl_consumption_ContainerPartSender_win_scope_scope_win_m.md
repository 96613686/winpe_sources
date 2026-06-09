# win_musl::FiberStream<win_musl::FiberStreamClient<win_musl::consumption::ContainerPartSender,win_scope::scope<win_musl::consumption::ContainerPartSender *,win_scope::const_policies<win_scope::com_policies>>>>::TransferToFiber(void)

- ea: `0x18006ddd8`
- end: `0x18006df07`
- name: `?TransferToFiber@?$FiberStream@V?$FiberStreamClient@VContainerPartSender@consumption@win_musl@@V?$scope@PEAVContainerPartSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@win_musl@@@win_musl@@AEAAXXZ`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006dc08`
- `0x1800eaad8`

## callees

- `0x1800016dc`
- `0x18000d950`
- `0x180018c00`
- `0x18004f508`
- `0x18006ddd8`
- `0x18006df10`
- `0x18007b96c`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18006de72`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18006de72`

## string_xrefs

- `0x18006de6b`: `win_musl::FiberStream<class win_musl::FiberStreamClient<class win_musl::consumption::ContainerPartSender,class win_scope::scope<class win_musl::consumption::ContainerPartSender *,struct win_scope::const_policies<struct win_scope::com_policies> > > >::TransferToFiber, m_pCommandDerecurser->IsRecursed() is true, must call command syncronously for the data copy to work!\n`

## pseudocode

```c

```
