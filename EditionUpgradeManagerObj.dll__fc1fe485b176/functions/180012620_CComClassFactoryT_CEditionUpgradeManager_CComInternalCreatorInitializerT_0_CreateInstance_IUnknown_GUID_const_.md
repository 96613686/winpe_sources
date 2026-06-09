# CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180012620`
- end: `0x180012703`
- name: `?CreateInstance@?$CComClassFactoryT@VCEditionUpgradeManager@@VCComInternalCreatorInitializerT@@$0A@@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `227`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001ed8`
- `0x1800090dc`
- `0x180009480`
- `0x180012620`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  unsigned __int64 v7; // rdi
  int v8; // eax

  if ( !a4 )
  {
    v6 = -2147467261;
LABEL_8:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_9;
  }
  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    goto LABEL_8;
  }
  v7 = (unsigned __int64)operator new(0x18u);
  *(_OWORD *)(v7 & -(__int64)(v7 != -8)) = 0;
  *(_QWORD *)(v7 + 8) = 0;
  *(_QWORD *)v7 = &CUnknownImplT<CEditionUpgradeManager,0>::`vftable';
  *(_DWORD *)(v7 + 16) = 1;
  _InterlockedIncrement(&CComProcessCounter<0>::g_lServerLockCount);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)((void *)v7, a3, a4);
  v6 = v8;
  if ( v8 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_8;
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  return v6;
}

```

## disassembly

```asm
0x180012620  mov     [rsp+arg_0], rbx
0x180012625  mov     [rsp+arg_8], rsi
0x18001262a  push    rdi
0x18001262b  sub     rsp, 20h
0x18001262f  mov     rbx, r9
0x180012632  mov     rsi, r8
0x180012635  test    r9, r9
0x180012638  jnz     short loc_180012644
0x18001263a  mov     ebx, 80004003h
0x18001263f  jmp     loc_1800126E3
0x180012644  mov     qword ptr [r9], 0
0x18001264b  test    rdx, rdx
0x18001264e  jz      short loc_18001265A
0x180012650  mov     ebx, 80040110h
0x180012655  jmp     loc_1800126E3
0x18001265a  mov     ecx, 18h; Size
0x18001265f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012664  mov     rdi, rax
0x180012667  xorps   xmm0, xmm0
0x18001266a  add     rax, 8
0x18001266e  neg     rax
0x180012671  lea     rax, ??_7?$CUnknownImplT@VCEditionUpgradeManager@@$0A@@@6B@; const CUnknownImplT<CEditionUpgradeManager,0>::`vftable'
0x180012678  sbb     rcx, rcx
0x18001267b  and     rcx, rdi
0x18001267e  movups  xmmword ptr [rcx], xmm0
0x180012681  mov     qword ptr [rdi+8], 0
0x180012689  mov     [rdi], rax
0x18001268c  mov     dword ptr [rdi+10h], 1
0x180012693  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001269a  xor     ecx, ecx
0x18001269c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800126a1  xor     ecx, ecx
0x1800126a3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800126a8  mov     rax, [rdi]
0x1800126ab  mov     r8, rbx
0x1800126ae  mov     rdx, rsi
0x1800126b1  mov     rcx, rdi
0x1800126b4  mov     rax, [rax]
0x1800126b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126bc  mov     ebx, eax
0x1800126be  test    eax, eax
0x1800126c0  jns     short loc_1800126C9
0x1800126c2  mov     ecx, eax
0x1800126c4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800126c9  mov     ecx, ebx
0x1800126cb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800126d0  mov     rax, [rdi]
0x1800126d3  mov     rcx, rdi
0x1800126d6  mov     rax, [rax+10h]
0x1800126da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126df  test    ebx, ebx
0x1800126e1  jns     short loc_1800126EA
0x1800126e3  mov     ecx, ebx
0x1800126e5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800126ea  mov     ecx, ebx
0x1800126ec  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800126f1  mov     rsi, [rsp+28h+arg_8]
0x1800126f6  mov     eax, ebx
0x1800126f8  mov     rbx, [rsp+28h+arg_0]
0x1800126fd  add     rsp, 20h
0x180012701  pop     rdi
0x180012702  retn
```
