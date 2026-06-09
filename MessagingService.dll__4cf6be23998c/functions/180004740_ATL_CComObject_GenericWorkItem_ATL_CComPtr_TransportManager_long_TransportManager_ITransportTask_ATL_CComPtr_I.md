# ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::Release(void)

- ea: `0x180004740`
- end: `0x1800047c1`
- name: `?Release@?$CComObject@V?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJPEAUITransportTask@@@ZV?$CComPtr@UITransportTask@@@2@UEmpty@detail@@U67@U67@U67@U67@U67@U67@U67@@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004740`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(ITransportTask *),ATL::CComPtr<ITransportTask>,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>>::Release(
        volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180004740  mov     [rsp+arg_0], rbx
0x180004745  push    rdi
0x180004746  sub     rsp, 20h
0x18000474a  mov     r8d, [rcx+8]
0x18000474e  mov     rbx, rcx
0x180004751  mov     ecx, 7FFFFFFFh
0x180004756  jmp     short loc_18000476A
0x180004758  lea     edx, [r8-1]
0x18000475c  mov     eax, r8d
0x18000475f  lock cmpxchg [rbx+8], edx
0x180004764  jz      short loc_18000476F
0x180004766  mov     r8d, [rbx+8]
0x18000476a  cmp     r8d, ecx
0x18000476d  jnz     short loc_180004758
0x18000476f  lea     edi, [r8-1]
0x180004773  test    edi, edi
0x180004775  jnz     short loc_1800047B4
0x180004777  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000477e  mov     rax, [rcx]
0x180004781  mov     rax, [rax+8]
0x180004785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000478a  test    rbx, rbx
0x18000478d  jz      short loc_1800047A1
0x18000478f  mov     rax, [rbx]
0x180004792  lea     edx, [rdi+1]
0x180004795  mov     rcx, rbx
0x180004798  mov     rax, [rax+28h]
0x18000479c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047a1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800047a8  mov     rdx, [rcx]
0x1800047ab  mov     rax, [rdx+10h]
0x1800047af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047b4  mov     rbx, [rsp+28h+arg_0]
0x1800047b9  mov     eax, edi
0x1800047bb  add     rsp, 20h
0x1800047bf  pop     rdi
0x1800047c0  retn
```
