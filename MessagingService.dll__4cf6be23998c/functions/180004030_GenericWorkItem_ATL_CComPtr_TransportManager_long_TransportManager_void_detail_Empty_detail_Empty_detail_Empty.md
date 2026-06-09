# GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::`scalar deleting destructor'(uint)

- ea: `0x180004030`
- end: `0x18000408e`
- name: `??_G?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJXZUEmpty@detail@@U45@U45@U45@U45@U45@U45@U45@U45@@@MEAAPEAXI@Z`
- size: `94`
- prototype: `_QWORD **__fastcall(_QWORD **, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004030`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000407a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000407a`

## pseudocode

```c
_QWORD **__fastcall GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::`scalar deleting destructor'(
        _QWORD **a1,
        char a2)
{
  __int64 v4; // rcx

  *a1 = &GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::`vftable';
  if ( *((_DWORD *)a1 + 14) )
  {
    v4 = *a1[8];
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *a1 = &IAsyncCallback::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180004030  mov     [rsp+arg_0], rbx
0x180004035  push    rdi
0x180004036  sub     rsp, 20h
0x18000403a  lea     rax, ??_7?$GenericWorkItem@V?$CComPtr@VTransportManager@@@ATL@@P8TransportManager@@EAAJXZUEmpty@detail@@U45@U45@U45@U45@U45@U45@U45@U45@@@6B@; const GenericWorkItem<ATL::CComPtr<TransportManager>,long (TransportManager::*)(void),detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty,detail::Empty>::`vftable'
0x180004041  mov     edi, edx
0x180004043  mov     [rcx], rax
0x180004046  mov     rbx, rcx
0x180004049  cmp     dword ptr [rcx+38h], 0
0x18000404d  jz      short loc_180004067
0x18000404f  mov     rax, [rcx+40h]
0x180004053  mov     rcx, [rax]
0x180004056  test    rcx, rcx
0x180004059  jz      short loc_180004067
0x18000405b  mov     rax, [rcx]
0x18000405e  mov     rax, [rax+10h]
0x180004062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004067  lea     rax, ??_7IAsyncCallback@@6B@; const IAsyncCallback::`vftable'
0x18000406e  mov     [rbx], rax
0x180004071  test    dil, 1
0x180004075  jz      short loc_180004080
0x180004077  mov     rcx, rbx
0x18000407a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004080  mov     rax, rbx
0x180004083  mov     rbx, [rsp+28h+arg_0]
0x180004088  add     rsp, 20h
0x18000408c  pop     rdi
0x18000408d  retn
```
