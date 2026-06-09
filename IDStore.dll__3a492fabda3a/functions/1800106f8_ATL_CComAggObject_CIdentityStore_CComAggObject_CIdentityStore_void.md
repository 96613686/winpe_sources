# ATL::CComAggObject<CIdentityStore>::CComAggObject<CIdentityStore>(void *)

- ea: `0x1800106f8`
- end: `0x180010772`
- name: `??0?$CComAggObject@VCIdentityStore@@@ATL@@QEAA@PEAX@Z`
- size: `122`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e9fc`

## callees

- `0x18000d230`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CIdentityStore>::CComAggObject<CIdentityStore>(__int64 a1, __int64 a2)
{
  struct ATL::CAtlModule *v4; // rcx

  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = &ATL::CComAggObject<CIdentityStore>::`vftable';
  CIdentityStore::CIdentityStore((CIdentityStore *)(a1 + 24));
  v4 = ATL::_pAtlModule;
  *(_QWORD *)(a1 + 24) = &ATL::CComContainedObject<CIdentityStore>::`vftable'{for `IIdentityStore'};
  *(_QWORD *)(a1 + 32) = &ATL::CComContainedObject<CIdentityStore>::`vftable'{for `IIdentityStore2'};
  *(_QWORD *)(a1 + 40) = &ATL::CComContainedObject<CIdentityStore>::`vftable'{for `IIdentityStoreEx'};
  *(_QWORD *)(a1 + 48) = a2;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v4 + 8LL))(v4);
  return a1;
}

```

## disassembly

```asm
0x1800106f8  mov     [rsp+arg_0], rbx
0x1800106fd  mov     [rsp+arg_8], rsi
0x180010702  push    rdi
0x180010703  sub     rsp, 20h
0x180010707  mov     dword ptr [rcx+8], 0
0x18001070e  lea     rax, ??_7?$CComAggObject@VCIdentityStore@@@ATL@@6B@; const ATL::CComAggObject<CIdentityStore>::`vftable'
0x180010715  mov     [rcx], rax
0x180010718  mov     rsi, rcx
0x18001071b  add     rcx, 18h; this
0x18001071f  mov     rdi, rdx
0x180010722  call    ??0CIdentityStore@@QEAA@XZ; CIdentityStore::CIdentityStore(void)
0x180010727  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001072e  lea     rax, ??_7?$CComContainedObject@VCIdentityStore@@@ATL@@6BIIdentityStore@@@; const ATL::CComContainedObject<CIdentityStore>::`vftable'{for `IIdentityStore'}
0x180010735  mov     [rsi+18h], rax
0x180010739  lea     rax, ??_7?$CComContainedObject@VCIdentityStore@@@ATL@@6BIIdentityStore2@@@; const ATL::CComContainedObject<CIdentityStore>::`vftable'{for `IIdentityStore2'}
0x180010740  mov     [rsi+20h], rax
0x180010744  lea     rax, ??_7?$CComContainedObject@VCIdentityStore@@@ATL@@6BIIdentityStoreEx@@@; const ATL::CComContainedObject<CIdentityStore>::`vftable'{for `IIdentityStoreEx'}
0x18001074b  mov     [rsi+28h], rax
0x18001074f  mov     [rsi+30h], rdi
0x180010753  mov     rax, [rcx]
0x180010756  mov     rax, [rax+8]
0x18001075a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001075f  mov     rbx, [rsp+28h+arg_0]
0x180010764  mov     rax, rsi
0x180010767  mov     rsi, [rsp+28h+arg_8]
0x18001076c  add     rsp, 20h
0x180010770  pop     rdi
0x180010771  retn
```
