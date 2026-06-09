# ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(void *)

- ea: `0x180003ac4`
- end: `0x180003bb0`
- name: `??0?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@@ATL@@QEAA@PEAX@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004190`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(
        __int64 a1)
{
  struct ATL::CAtlModule *v2; // rcx

  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 32) = a1 + 40;
  *(_QWORD *)(a1 + 64) = a1 + 72;
  *(_QWORD *)(a1 + 88) = a1 + 96;
  *(_QWORD *)(a1 + 112) = a1 + 120;
  *(_QWORD *)(a1 + 136) = a1 + 144;
  *(_QWORD *)(a1 + 160) = a1 + 168;
  *(_QWORD *)(a1 + 184) = a1 + 192;
  *(_QWORD *)(a1 + 208) = a1 + 216;
  *(_QWORD *)(a1 + 232) = a1 + 240;
  *(_QWORD *)(a1 + 256) = a1 + 264;
  *(_QWORD *)(a1 + 280) = a1 + 288;
  *(_DWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  *(_DWORD *)(a1 + 80) = 0;
  *(_DWORD *)(a1 + 104) = 0;
  *(_DWORD *)(a1 + 128) = 0;
  *(_DWORD *)(a1 + 152) = 0;
  *(_DWORD *)(a1 + 176) = 0;
  *(_DWORD *)(a1 + 200) = 0;
  *(_DWORD *)(a1 + 224) = 0;
  *(_DWORD *)(a1 + 248) = 0;
  *(_DWORD *)(a1 + 272) = 0;
  v2 = ATL::_pAtlModule;
  *(_QWORD *)a1 = &ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v2 + 8LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x180003ac4  push    rbx
0x180003ac6  sub     rsp, 20h
0x180003aca  mov     rbx, rcx
0x180003acd  xor     ecx, ecx
0x180003acf  mov     [rbx+8], ecx
0x180003ad2  lea     rax, [rbx+28h]
0x180003ad6  mov     [rbx+20h], rax
0x180003ada  lea     rax, [rbx+48h]
0x180003ade  mov     [rbx+40h], rax
0x180003ae2  lea     rax, [rbx+60h]
0x180003ae6  mov     [rbx+58h], rax
0x180003aea  lea     rax, [rbx+78h]
0x180003aee  mov     [rbx+70h], rax
0x180003af2  lea     rax, [rbx+90h]
0x180003af9  mov     [rbx+88h], rax
0x180003b00  lea     rax, [rbx+0A8h]
0x180003b07  mov     [rbx+0A0h], rax
0x180003b0e  lea     rax, [rbx+0C0h]
0x180003b15  mov     [rbx+0B8h], rax
0x180003b1c  lea     rax, [rbx+0D8h]
0x180003b23  mov     [rbx+0D0h], rax
0x180003b2a  lea     rax, [rbx+0F0h]
0x180003b31  mov     [rbx+0E8h], rax
0x180003b38  lea     rax, [rbx+108h]
0x180003b3f  mov     [rbx+100h], rax
0x180003b46  lea     rax, [rbx+120h]
0x180003b4d  mov     [rbx+118h], rax
0x180003b54  lea     rax, ??_7?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@@ATL@@6B@; const ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::`vftable'
0x180003b5b  mov     [rbx+18h], ecx
0x180003b5e  mov     [rbx+38h], ecx
0x180003b61  mov     [rbx+50h], ecx
0x180003b64  mov     [rbx+68h], ecx
0x180003b67  mov     [rbx+80h], ecx
0x180003b6d  mov     [rbx+98h], ecx
0x180003b73  mov     [rbx+0B0h], ecx
0x180003b79  mov     [rbx+0C8h], ecx
0x180003b7f  mov     [rbx+0E0h], ecx
0x180003b85  mov     [rbx+0F8h], ecx
0x180003b8b  mov     [rbx+110h], ecx
0x180003b91  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003b98  mov     [rbx], rax
0x180003b9b  mov     rax, [rcx]
0x180003b9e  mov     rax, [rax+8]
0x180003ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ba7  mov     rax, rbx
0x180003baa  add     rsp, 20h
0x180003bae  pop     rbx
0x180003baf  retn
```
