# GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::`scalar deleting destructor'(uint)

- ea: `0x180003fa0`
- end: `0x18000401d`
- name: `??_G?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@MEAAPEAXI@Z`
- size: `125`
- prototype: `_QWORD **__fastcall(_QWORD **, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003fa0`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004009`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004009`

## pseudocode

```c
_QWORD **__fastcall GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::`scalar deleting destructor'(
        _QWORD **a1,
        char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx

  *a1 = &GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::`vftable';
  if ( *((_DWORD *)a1 + 20) )
  {
    v4 = *a1[11];
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( *((_DWORD *)a1 + 14) )
  {
    v5 = *a1[8];
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  *a1 = &IAsyncCallback::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003fa0  mov     [rsp+arg_0], rbx
0x180003fa5  push    rdi
0x180003fa6  sub     rsp, 20h
0x180003faa  mov     edi, edx
0x180003fac  mov     rbx, rcx
0x180003faf  lea     rax, ??_7?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@6B@; const GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::`vftable'
0x180003fb6  mov     [rcx], rax
0x180003fb9  cmp     dword ptr [rcx+50h], 0
0x180003fbd  jz      short loc_180003FD8
0x180003fbf  mov     rax, [rcx+58h]
0x180003fc3  mov     rcx, [rax]
0x180003fc6  test    rcx, rcx
0x180003fc9  jz      short loc_180003FD8
0x180003fcb  mov     rax, [rcx]
0x180003fce  mov     rax, [rax+10h]
0x180003fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fd7  nop
0x180003fd8  cmp     dword ptr [rbx+38h], 0
0x180003fdc  jz      short loc_180003FF6
0x180003fde  mov     rax, [rbx+40h]
0x180003fe2  mov     rcx, [rax]
0x180003fe5  test    rcx, rcx
0x180003fe8  jz      short loc_180003FF6
0x180003fea  mov     rax, [rcx]
0x180003fed  mov     rax, [rax+10h]
0x180003ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ff6  lea     rax, ??_7IAsyncCallback@@6B@; const IAsyncCallback::`vftable'
0x180003ffd  mov     [rbx], rax
0x180004000  test    dil, 1
0x180004004  jz      short loc_18000400F
0x180004006  mov     rcx, rbx
0x180004009  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000400f  mov     rax, rbx
0x180004012  mov     rbx, [rsp+28h+arg_0]
0x180004017  add     rsp, 20h
0x18000401b  pop     rdi
0x18000401c  retn
```
