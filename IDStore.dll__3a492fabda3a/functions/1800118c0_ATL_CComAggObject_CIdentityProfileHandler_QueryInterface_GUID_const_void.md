# ATL::CComAggObject<CIdentityProfileHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800118c0`
- end: `0x18001190d`
- name: `?QueryInterface@?$CComAggObject@VCIdentityProfileHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `77`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d34c`
- `0x18000d450`
- `0x1800118c0`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CIdentityProfileHandler>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  const struct _GUID *v5; // rdx
  void **v6; // r8
  __int64 v7; // r9

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( ATL::InlineIsEqualUnknown(a2) )
  {
    *v6 = (void *)v7;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  }
  else
  {
    return (unsigned int)CIdentityProfileHandler::_InternalQueryInterface((CIdentityProfileHandler *)(v7 + 24), v5, v6);
  }
  return v3;
}

```

## disassembly

```asm
0x1800118c0  push    rbx
0x1800118c2  sub     rsp, 20h
0x1800118c6  xor     ebx, ebx
0x1800118c8  mov     r9, rcx
0x1800118cb  test    r8, r8
0x1800118ce  jnz     short loc_1800118D7
0x1800118d0  mov     eax, 80004003h
0x1800118d5  jmp     short loc_180011907
0x1800118d7  mov     rcx, rdx; struct _GUID *
0x1800118da  mov     [r8], rbx
0x1800118dd  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x1800118e2  test    eax, eax
0x1800118e4  jz      short loc_1800118FA
0x1800118e6  mov     [r8], r9
0x1800118e9  mov     rcx, r9
0x1800118ec  mov     rax, [r9]
0x1800118ef  mov     rax, [rax+8]
0x1800118f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118f8  jmp     short loc_180011905
0x1800118fa  lea     rcx, [r9+18h]; this
0x1800118fe  call    ?_InternalQueryInterface@CIdentityProfileHandler@@QEAAJAEBU_GUID@@PEAPEAX@Z; CIdentityProfileHandler::_InternalQueryInterface(_GUID const &,void * *)
0x180011903  mov     ebx, eax
0x180011905  mov     eax, ebx
0x180011907  add     rsp, 20h
0x18001190b  pop     rbx
0x18001190c  retn
```
