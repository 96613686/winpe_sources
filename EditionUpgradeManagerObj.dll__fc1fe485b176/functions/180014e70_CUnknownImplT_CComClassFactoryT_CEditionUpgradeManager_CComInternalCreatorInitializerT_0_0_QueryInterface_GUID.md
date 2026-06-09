# CUnknownImplT<CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x180014e70`
- end: `0x180014ee7`
- name: `?QueryInterface@?$CUnknownImplT@V?$CComClassFactoryT@VCEditionUpgradeManager@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `119`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, __int64 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x180014e70`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>,0>::QueryInterface(
        __int64 *a1,
        _QWORD *a2,
        __int64 **a3)
{
  unsigned int v5; // ebx
  int v6; // ecx
  __int64 v7; // rax
  __int64 v8; // r9
  int v9; // eax

  if ( !a3 )
  {
    v5 = -2147467261;
    v6 = -2147467261;
LABEL_9:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_10;
  }
  v7 = *(_QWORD *)&IID_IUnknown.Data1 - *a2;
  if ( *(_QWORD *)&IID_IUnknown.Data1 == *a2 )
    v7 = *(_QWORD *)IID_IUnknown.Data4 - a2[1];
  v8 = *a1;
  if ( v7 )
  {
    v9 = (*(__int64 (**)(void))(v8 + 40))();
    v5 = v9;
    if ( v9 < 0 )
    {
      v6 = v9;
      goto LABEL_9;
    }
  }
  else
  {
    (*(void (**)(void))(v8 + 8))();
    *a3 = a1;
    v5 = 0;
  }
LABEL_10:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x180014e70  mov     [rsp+arg_0], rbx
0x180014e75  push    rdi
0x180014e76  sub     rsp, 20h
0x180014e7a  mov     rdi, r8
0x180014e7d  mov     rbx, rcx
0x180014e80  test    r8, r8
0x180014e83  jnz     short loc_180014E8E
0x180014e85  mov     ebx, 80004003h
0x180014e8a  mov     ecx, ebx
0x180014e8c  jmp     short loc_180014ECE
0x180014e8e  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x180014e95  sub     rax, [rdx]
0x180014e98  jnz     short loc_180014EA5
0x180014e9a  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x180014ea1  sub     rax, [rdx+8]
0x180014ea5  mov     r9, [rcx]
0x180014ea8  test    rax, rax
0x180014eab  jnz     short loc_180014EBD
0x180014ead  mov     rax, [r9+8]
0x180014eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eb6  mov     [rdi], rbx
0x180014eb9  xor     ebx, ebx
0x180014ebb  jmp     short loc_180014ED3
0x180014ebd  mov     rax, [r9+28h]
0x180014ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ec6  mov     ebx, eax
0x180014ec8  test    eax, eax
0x180014eca  jns     short loc_180014ED3
0x180014ecc  mov     ecx, eax
0x180014ece  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180014ed3  mov     ecx, ebx
0x180014ed5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180014eda  mov     eax, ebx
0x180014edc  mov     rbx, [rsp+28h+arg_0]
0x180014ee1  add     rsp, 20h
0x180014ee5  pop     rdi
0x180014ee6  retn
```
