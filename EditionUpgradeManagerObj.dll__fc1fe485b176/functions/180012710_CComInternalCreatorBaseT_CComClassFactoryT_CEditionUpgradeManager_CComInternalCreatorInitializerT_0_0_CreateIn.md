# CComInternalCreatorBaseT<CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>,0>::CreateInstance(_GUID const &,void * *)

- ea: `0x180012710`
- end: `0x18001279a`
- name: `?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCEditionUpgradeManager@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001ed8`
- `0x1800090dc`
- `0x180009480`
- `0x180012710`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CComInternalCreatorBaseT<CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>,0>::CreateInstance(
        __int64 a1,
        __int64 a2)
{
  _DWORD *v4; // rsi
  int v5; // eax
  unsigned int v6; // ebx

  v4 = operator new(0x10u);
  *(_QWORD *)v4 = &CUnknownImplT<CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>,0>::`vftable';
  v4[2] = 1;
  _InterlockedIncrement(&CComProcessCounter<0>::g_lServerLockCount);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v5 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v4)(v4, a1, a2);
  v6 = v5;
  if ( v5 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
  return v6;
}

```

## disassembly

```asm
0x180012710  mov     [rsp+arg_0], rbx
0x180012715  mov     [rsp+arg_8], rsi
0x18001271a  push    rdi
0x18001271b  sub     rsp, 20h
0x18001271f  mov     rdi, rcx
0x180012722  mov     rbx, rdx
0x180012725  mov     ecx, 10h; Size
0x18001272a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001272f  mov     rsi, rax
0x180012732  lea     rax, ??_7?$CUnknownImplT@V?$CComClassFactoryT@VCEditionUpgradeManager@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@6B@; const CUnknownImplT<CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>,0>::`vftable'
0x180012739  mov     [rsi], rax
0x18001273c  mov     dword ptr [rsi+8], 1
0x180012743  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001274a  xor     ecx, ecx
0x18001274c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180012751  mov     r8, [rsi]
0x180012754  mov     rdx, rdi
0x180012757  mov     rcx, rsi
0x18001275a  mov     rax, [r8]
0x18001275d  mov     r8, rbx
0x180012760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012765  mov     ebx, eax
0x180012767  test    eax, eax
0x180012769  jns     short loc_180012772
0x18001276b  mov     ecx, eax
0x18001276d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180012772  mov     ecx, ebx
0x180012774  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180012779  mov     rcx, [rsi]
0x18001277c  mov     rax, [rcx+10h]
0x180012780  mov     rcx, rsi
0x180012783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012788  mov     rsi, [rsp+28h+arg_8]
0x18001278d  mov     eax, ebx
0x18001278f  mov     rbx, [rsp+28h+arg_0]
0x180012794  add     rsp, 20h
0x180012798  pop     rdi
0x180012799  retn
```
