# ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800046c0`
- end: `0x1800046d2`
- name: `?QueryInterface@?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800043b8`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x1800046c0  mov     r9, r8; void **
0x1800046c3  mov     r8, rdx; struct _GUID *
0x1800046c6  lea     rdx, ?_entries@?1??_GetEntries@?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800046cd  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
