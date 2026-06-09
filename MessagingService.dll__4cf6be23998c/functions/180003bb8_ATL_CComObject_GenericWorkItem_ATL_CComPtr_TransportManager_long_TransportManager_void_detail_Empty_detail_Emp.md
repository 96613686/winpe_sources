# ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(void *)

- ea: `0x180003bb8`
- end: `0x180003ca4`
- name: `??0?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJXZUEmpty@detail@@U45@U45@U45@U45@U45@U45@U45@U45@@@@ATL@@QEAA@PEAX@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000422c`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(
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
  *(_QWORD *)a1 = &ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v2 + 8LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x180003bb8  push    rbx
0x180003bba  sub     rsp, 20h
0x180003bbe  mov     rbx, rcx
0x180003bc1  xor     ecx, ecx
0x180003bc3  mov     [rbx+8], ecx
0x180003bc6  lea     rax, [rbx+28h]
0x180003bca  mov     [rbx+20h], rax
0x180003bce  lea     rax, [rbx+48h]
0x180003bd2  mov     [rbx+40h], rax
0x180003bd6  lea     rax, [rbx+60h]
0x180003bda  mov     [rbx+58h], rax
0x180003bde  lea     rax, [rbx+78h]
0x180003be2  mov     [rbx+70h], rax
0x180003be6  lea     rax, [rbx+90h]
0x180003bed  mov     [rbx+88h], rax
0x180003bf4  lea     rax, [rbx+0A8h]
0x180003bfb  mov     [rbx+0A0h], rax
0x180003c02  lea     rax, [rbx+0C0h]
0x180003c09  mov     [rbx+0B8h], rax
0x180003c10  lea     rax, [rbx+0D8h]
0x180003c17  mov     [rbx+0D0h], rax
0x180003c1e  lea     rax, [rbx+0F0h]
0x180003c25  mov     [rbx+0E8h], rax
0x180003c2c  lea     rax, [rbx+108h]
0x180003c33  mov     [rbx+100h], rax
0x180003c3a  lea     rax, [rbx+120h]
0x180003c41  mov     [rbx+118h], rax
0x180003c48  lea     rax, ??_7?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJXZUEmpty@detail@@U45@U45@U45@U45@U45@U45@U45@U45@@@@ATL@@6B@; const ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::`vftable'
0x180003c4f  mov     [rbx+18h], ecx
0x180003c52  mov     [rbx+38h], ecx
0x180003c55  mov     [rbx+50h], ecx
0x180003c58  mov     [rbx+68h], ecx
0x180003c5b  mov     [rbx+80h], ecx
0x180003c61  mov     [rbx+98h], ecx
0x180003c67  mov     [rbx+0B0h], ecx
0x180003c6d  mov     [rbx+0C8h], ecx
0x180003c73  mov     [rbx+0E0h], ecx
0x180003c79  mov     [rbx+0F8h], ecx
0x180003c7f  mov     [rbx+110h], ecx
0x180003c85  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003c8c  mov     [rbx], rax
0x180003c8f  mov     rax, [rcx]
0x180003c92  mov     rax, [rax+8]
0x180003c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c9b  mov     rax, rbx
0x180003c9e  add     rsp, 20h
0x180003ca2  pop     rbx
0x180003ca3  retn
```
