# GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::ProcessWorkItem(IUnknown *)

- ea: `0x180004650`
- end: `0x18000467c`
- name: `?ProcessWorkItem@?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@UEAAJPEAUIUnknown@@@Z`
- size: `44`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::ProcessWorkItem(
        __int64 a1)
{
  (**(void (__fastcall ***)(_QWORD, _QWORD))(a1 + 32))(
    **(_QWORD **)(a1 + 64) + *(int *)(*(_QWORD *)(a1 + 32) + 8LL),
    **(_QWORD **)(a1 + 88));
  return 0;
}

```

## disassembly

```asm
0x180004650  sub     rsp, 28h
0x180004654  mov     r8, [rcx+20h]
0x180004658  mov     rax, [rcx+40h]
0x18000465c  mov     rdx, [rcx+58h]
0x180004660  movsxd  r9, dword ptr [r8+8]
0x180004664  add     r9, [rax]
0x180004667  mov     rdx, [rdx]
0x18000466a  mov     rcx, r9
0x18000466d  mov     rax, [r8]
0x180004670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004675  xor     eax, eax
0x180004677  add     rsp, 28h
0x18000467b  retn
```
