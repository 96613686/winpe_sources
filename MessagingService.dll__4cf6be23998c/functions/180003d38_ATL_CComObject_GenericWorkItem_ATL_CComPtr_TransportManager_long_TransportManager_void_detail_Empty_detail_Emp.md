# ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::~CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(void)

- ea: `0x180003d38`
- end: `0x180003d9d`
- name: `??1?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJXZUEmpty@detail@@U45@U45@U45@U45@U45@U45@U45@U45@@@@ATL@@UEAA@XZ`
- size: `101`
- prototype: `void **__fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ee0`

## callees

- `0x180003d38`
- `0x18000c010`

## pseudocode

```c
void **__fastcall ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::~CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>(
        __int64 a1)
{
  __int64 v2; // rcx
  void **result; // rax

  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *(_QWORD *)a1 = &GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::`vftable';
  if ( *(_DWORD *)(a1 + 56) )
  {
    v2 = **(_QWORD **)(a1 + 64);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  result = &IAsyncCallback::`vftable';
  *(_QWORD *)a1 = &IAsyncCallback::`vftable';
  return result;
}

```

## disassembly

```asm
0x180003d38  push    rbx
0x180003d3a  sub     rsp, 20h
0x180003d3e  mov     dword ptr [rcx+8], 0C0000001h
0x180003d45  lea     rax, ??_7?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJXZUEmpty@detail@@U45@U45@U45@U45@U45@U45@U45@U45@@@@ATL@@6B@; const ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::`vftable'
0x180003d4c  mov     [rcx], rax
0x180003d4f  mov     rbx, rcx
0x180003d52  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003d59  mov     rax, [rcx]
0x180003d5c  mov     rax, [rax+10h]
0x180003d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d65  lea     rax, ??_7?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJXZUEmpty@detail@@U45@U45@U45@U45@U45@U45@U45@U45@@@6B@; const GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::`vftable'
0x180003d6c  mov     [rbx], rax
0x180003d6f  cmp     dword ptr [rbx+38h], 0
0x180003d73  jz      short loc_180003D8D
0x180003d75  mov     rax, [rbx+40h]
0x180003d79  mov     rcx, [rax]
0x180003d7c  test    rcx, rcx
0x180003d7f  jz      short loc_180003D8D
0x180003d81  mov     rax, [rcx]
0x180003d84  mov     rax, [rax+10h]
0x180003d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d8d  lea     rax, ??_7IAsyncCallback@@6B@; const IAsyncCallback::`vftable'
0x180003d94  mov     [rbx], rax
0x180003d97  add     rsp, 20h
0x180003d9b  pop     rbx
0x180003d9c  retn
```
