# ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::`scalar deleting destructor'(uint)

- ea: `0x180003ea0`
- end: `0x180003ed0`
- name: `??_G?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003cac`
- `0x180003ea0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003ebc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003ebc`

## pseudocode

```c
void *__fastcall ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::`scalar deleting destructor'(
        void *a1,
        char a2)
{
  ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::~CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003ea0  mov     [rsp+arg_0], rbx
0x180003ea5  push    rdi
0x180003ea6  sub     rsp, 20h
0x180003eaa  mov     ebx, edx
0x180003eac  mov     rdi, rcx
0x180003eaf  call    ??1?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@@ATL@@UEAA@XZ; ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::~CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(void)
0x180003eb4  test    bl, 1
0x180003eb7  jz      short loc_180003EC2
0x180003eb9  mov     rcx, rdi
0x180003ebc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003ec2  mov     rbx, [rsp+28h+arg_0]
0x180003ec7  mov     rax, rdi
0x180003eca  add     rsp, 20h
0x180003ece  pop     rdi
0x180003ecf  retn
```
