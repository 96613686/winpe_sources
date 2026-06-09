# GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::ProcessWorkItem(IUnknown *)

- ea: `0x180004690`
- end: `0x1800046b5`
- name: `?ProcessWorkItem@?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJXZUEmpty@detail@@U45@U45@U45@U45@U45@U45@U45@U45@@@UEAAJPEAUIUnknown@@@Z`
- size: `37`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::ProcessWorkItem(
        __int64 a1)
{
  (**(void (__fastcall ***)(_QWORD))(a1 + 32))(**(_QWORD **)(a1 + 64) + *(int *)(*(_QWORD *)(a1 + 32) + 8LL));
  return 0;
}

```

## disassembly

```asm
0x180004690  sub     rsp, 28h
0x180004694  mov     rdx, [rcx+20h]
0x180004698  mov     rax, [rcx+40h]
0x18000469c  movsxd  r8, dword ptr [rdx+8]
0x1800046a0  add     r8, [rax]
0x1800046a3  mov     rax, [rdx]
0x1800046a6  mov     rcx, r8
0x1800046a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ae  xor     eax, eax
0x1800046b0  add     rsp, 28h
0x1800046b4  retn
```
