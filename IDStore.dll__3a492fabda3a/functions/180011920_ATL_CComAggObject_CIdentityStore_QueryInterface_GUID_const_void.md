# ATL::CComAggObject<CIdentityStore>::QueryInterface(_GUID const &,void * *)

- ea: `0x180011920`
- end: `0x18001196d`
- name: `?QueryInterface@?$CComAggObject@VCIdentityStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `77`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000aa30`
- `0x18000d450`
- `0x180011920`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CIdentityStore>::QueryInterface(__int64 a1, const struct _GUID *a2, _QWORD *a3)
{
  unsigned int v3; // ebx
  _QWORD *v5; // r8
  __int64 v6; // r9

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( ATL::InlineIsEqualUnknown(a2) )
  {
    *v5 = v6;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  }
  else
  {
    return (unsigned int)ATL::CComObject<CIdentityStore>::QueryInterface(v6 + 24);
  }
  return v3;
}

```

## disassembly

```asm
0x180011920  push    rbx
0x180011922  sub     rsp, 20h
0x180011926  xor     ebx, ebx
0x180011928  mov     r9, rcx
0x18001192b  test    r8, r8
0x18001192e  jnz     short loc_180011937
0x180011930  mov     eax, 80004003h
0x180011935  jmp     short loc_180011967
0x180011937  mov     rcx, rdx; struct _GUID *
0x18001193a  mov     [r8], rbx
0x18001193d  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180011942  test    eax, eax
0x180011944  jz      short loc_18001195A
0x180011946  mov     [r8], r9
0x180011949  mov     rcx, r9
0x18001194c  mov     rax, [r9]
0x18001194f  mov     rax, [rax+8]
0x180011953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011958  jmp     short loc_180011965
0x18001195a  lea     rcx, [r9+18h]
0x18001195e  call    ?QueryInterface@?$CComObject@VCIdentityStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CIdentityStore>::QueryInterface(_GUID const &,void * *)
0x180011963  mov     ebx, eax
0x180011965  mov     eax, ebx
0x180011967  add     rsp, 20h
0x18001196b  pop     rbx
0x18001196c  retn
```
