# ATL::CComAggObject<CPimcManager>::~CComAggObject<CPimcManager>(void)

- ea: `0x1800020a8`
- end: `0x18000213d`
- name: `??1?$CComAggObject@VCPimcManager@@@ATL@@UEAA@XZ`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800021b0`

## callees

- `0x1800012c0`
- `0x1800020a8`
- `0x180002264`
- `0x180007e24`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ATL::CComAggObject<CPimcManager>::~CComAggObject<CPimcManager>(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  *(_QWORD *)a1 = &ATL::CComAggObject<CPimcManager>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  v1 = a1 + 16;
  if ( *(_DWORD *)(a1 + 56) )
  {
    LODWORD(v4) = *(_DWORD *)(a1 + 56);
    ATL::CComGITPtr<ITabletContextP>::Revoke(&v4);
    ATL::CComGITPtr<ITabletContextP>::Revoke(&v4);
  }
  if ( *(_QWORD *)(v1 + 64) )
    ComUtils::ComLockableWrapper::Unlock((ComUtils::ComLockableWrapper *)(v1 + 64));
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = v1 + 32;
  v2 = *(_QWORD *)(v1 + 32);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return CPbList<CPimcManager::CHookWindowItem>::~CPbList<CPimcManager::CHookWindowItem>(v1 + 16);
}

```

## disassembly

```asm
0x1800020a8  mov     [rsp+arg_0], rcx
0x1800020ad  push    rbx
0x1800020ae  sub     rsp, 20h
0x1800020b2  lea     rax, ??_7?$CComAggObject@VCPimcManager@@@ATL@@6B@; const ATL::CComAggObject<CPimcManager>::`vftable'
0x1800020b9  mov     [rcx], rax
0x1800020bc  mov     dword ptr [rcx+8], 0C0000001h
0x1800020c3  lea     rbx, [rcx+10h]
0x1800020c7  mov     eax, [rbx+28h]
0x1800020ca  test    eax, eax
0x1800020cc  jz      short loc_1800020E7
0x1800020ce  mov     dword ptr [rsp+28h+arg_8], eax
0x1800020d2  lea     rcx, [rsp+28h+arg_8]
0x1800020d7  call    ?Revoke@?$CComGITPtr@UITabletContextP@@@ATL@@QEAAJXZ; ATL::CComGITPtr<ITabletContextP>::Revoke(void)
0x1800020dc  nop
0x1800020dd  lea     rcx, [rsp+28h+arg_8]
0x1800020e2  call    ?Revoke@?$CComGITPtr@UITabletContextP@@@ATL@@QEAAJXZ; ATL::CComGITPtr<ITabletContextP>::Revoke(void)
0x1800020e7  lea     rcx, [rbx+40h]; this
0x1800020eb  cmp     qword ptr [rcx], 0
0x1800020ef  jz      short loc_1800020F6
0x1800020f1  call    ?Unlock@ComLockableWrapper@ComUtils@@QEAAJXZ; ComUtils::ComLockableWrapper::Unlock(void)
0x1800020f6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800020fd  mov     rax, [rcx]
0x180002100  mov     rax, [rax+10h]
0x180002104  call    cs:__guard_dispatch_icall_fptr
0x18000210a  nop
0x18000210b  mov     [rsp+28h+arg_0], rbx
0x180002110  lea     rax, [rbx+20h]
0x180002114  mov     [rsp+28h+arg_8], rax
0x180002119  mov     rcx, [rax]
0x18000211c  test    rcx, rcx
0x18000211f  jz      short loc_18000212F
0x180002121  mov     rax, [rcx]
0x180002124  mov     rax, [rax+10h]
0x180002128  call    cs:__guard_dispatch_icall_fptr
0x18000212e  nop
0x18000212f  lea     rcx, [rbx+10h]
0x180002133  add     rsp, 20h
0x180002137  pop     rbx
0x180002138  jmp     ??1?$CPbList@UCHookWindowItem@CPimcManager@@@@QEAA@XZ; CPbList<CPimcManager::CHookWindowItem>::~CPbList<CPimcManager::CHookWindowItem>(void)
```
