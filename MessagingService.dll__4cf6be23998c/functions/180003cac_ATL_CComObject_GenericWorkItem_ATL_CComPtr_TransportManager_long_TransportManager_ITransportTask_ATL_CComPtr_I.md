# ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::~CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(void)

- ea: `0x180003cac`
- end: `0x180003d30`
- name: `??1?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@@ATL@@UEAA@XZ`
- size: `132`
- prototype: `void **__fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003ea0`

## callees

- `0x180003cac`
- `0x18000c010`

## pseudocode

```c
void **__fastcall ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::~CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void **result; // rax

  *(_QWORD *)a1 = &ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *(_QWORD *)a1 = &GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::`vftable';
  if ( *(_DWORD *)(a1 + 80) )
  {
    v2 = **(_QWORD **)(a1 + 88);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  if ( *(_DWORD *)(a1 + 56) )
  {
    v3 = **(_QWORD **)(a1 + 64);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  result = &IAsyncCallback::`vftable';
  *(_QWORD *)a1 = &IAsyncCallback::`vftable';
  return result;
}

```

## disassembly

```asm
0x180003cac  push    rbx
0x180003cae  sub     rsp, 20h
0x180003cb2  mov     rbx, rcx
0x180003cb5  lea     rax, ??_7?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@@ATL@@6B@; const ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::`vftable'
0x180003cbc  mov     [rcx], rax
0x180003cbf  mov     dword ptr [rcx+8], 0C0000001h
0x180003cc6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003ccd  mov     rax, [rcx]
0x180003cd0  mov     rax, [rax+10h]
0x180003cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cd9  lea     rax, ??_7?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@6B@; const GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::`vftable'
0x180003ce0  mov     [rbx], rax
0x180003ce3  cmp     dword ptr [rbx+50h], 0
0x180003ce7  jz      short loc_180003D02
0x180003ce9  mov     rax, [rbx+58h]
0x180003ced  mov     rcx, [rax]
0x180003cf0  test    rcx, rcx
0x180003cf3  jz      short loc_180003D02
0x180003cf5  mov     rax, [rcx]
0x180003cf8  mov     rax, [rax+10h]
0x180003cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d01  nop
0x180003d02  cmp     dword ptr [rbx+38h], 0
0x180003d06  jz      short loc_180003D20
0x180003d08  mov     rax, [rbx+40h]
0x180003d0c  mov     rcx, [rax]
0x180003d0f  test    rcx, rcx
0x180003d12  jz      short loc_180003D20
0x180003d14  mov     rax, [rcx]
0x180003d17  mov     rax, [rax+10h]
0x180003d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d20  lea     rax, ??_7IAsyncCallback@@6B@; const IAsyncCallback::`vftable'
0x180003d27  mov     [rbx], rax
0x180003d2a  add     rsp, 20h
0x180003d2e  pop     rbx
0x180003d2f  retn
```
