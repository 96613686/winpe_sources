# ATL::CComObject<CPimcManager>::~CComObject<CPimcManager>(void)

- ea: `0x180001edc`
- end: `0x180001f6b`
- name: `??1?$CComObject@VCPimcManager@@@ATL@@UEAA@XZ`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002140`

## callees

- `0x1800012c0`
- `0x180001edc`
- `0x180002264`
- `0x180007e24`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComObject<CPimcManager>::~CComObject<CPimcManager>(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  *(_QWORD *)a1 = &ATL::CComObject<CPimcManager>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  if ( *(_DWORD *)(a1 + 40) )
  {
    LODWORD(v4) = *(_DWORD *)(a1 + 40);
    ATL::CComGITPtr<ITabletContextP>::Revoke(&v4);
    ATL::CComGITPtr<ITabletContextP>::Revoke(&v4);
  }
  if ( *(_QWORD *)(a1 + 64) )
    ComUtils::ComLockableWrapper::Unlock((ComUtils::ComLockableWrapper *)(a1 + 64));
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = a1 + 32;
  v2 = *(_QWORD *)(a1 + 32);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return CPbList<CPimcManager::CHookWindowItem>::~CPbList<CPimcManager::CHookWindowItem>(a1 + 16);
}

```

## disassembly

```asm
0x180001edc  mov     [rsp+arg_0], rcx
0x180001ee1  push    rbx
0x180001ee2  sub     rsp, 20h
0x180001ee6  mov     rbx, rcx
0x180001ee9  lea     rax, ??_7?$CComObject@VCPimcManager@@@ATL@@6B@; const ATL::CComObject<CPimcManager>::`vftable'
0x180001ef0  mov     [rcx], rax
0x180001ef3  mov     dword ptr [rcx+8], 0C0000001h
0x180001efa  mov     eax, [rcx+28h]
0x180001efd  test    eax, eax
0x180001eff  jz      short loc_180001F1A
0x180001f01  mov     dword ptr [rsp+28h+arg_8], eax
0x180001f05  lea     rcx, [rsp+28h+arg_8]
0x180001f0a  call    ?Revoke@?$CComGITPtr@UITabletContextP@@@ATL@@QEAAJXZ; ATL::CComGITPtr<ITabletContextP>::Revoke(void)
0x180001f0f  nop
0x180001f10  lea     rcx, [rsp+28h+arg_8]
0x180001f15  call    ?Revoke@?$CComGITPtr@UITabletContextP@@@ATL@@QEAAJXZ; ATL::CComGITPtr<ITabletContextP>::Revoke(void)
0x180001f1a  lea     rcx, [rbx+40h]; this
0x180001f1e  cmp     qword ptr [rcx], 0
0x180001f22  jz      short loc_180001F29
0x180001f24  call    ?Unlock@ComLockableWrapper@ComUtils@@QEAAJXZ; ComUtils::ComLockableWrapper::Unlock(void)
0x180001f29  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001f30  mov     rax, [rcx]
0x180001f33  mov     rax, [rax+10h]
0x180001f37  call    cs:__guard_dispatch_icall_fptr
0x180001f3d  nop
0x180001f3e  lea     rax, [rbx+20h]
0x180001f42  mov     [rsp+28h+arg_8], rax
0x180001f47  mov     rcx, [rax]
0x180001f4a  test    rcx, rcx
0x180001f4d  jz      short loc_180001F5D
0x180001f4f  mov     rax, [rcx]
0x180001f52  mov     rax, [rax+10h]
0x180001f56  call    cs:__guard_dispatch_icall_fptr
0x180001f5c  nop
0x180001f5d  lea     rcx, [rbx+10h]
0x180001f61  add     rsp, 20h
0x180001f65  pop     rbx
0x180001f66  jmp     ??1?$CPbList@UCHookWindowItem@CPimcManager@@@@QEAA@XZ; CPbList<CPimcManager::CHookWindowItem>::~CPbList<CPimcManager::CHookWindowItem>(void)
```
