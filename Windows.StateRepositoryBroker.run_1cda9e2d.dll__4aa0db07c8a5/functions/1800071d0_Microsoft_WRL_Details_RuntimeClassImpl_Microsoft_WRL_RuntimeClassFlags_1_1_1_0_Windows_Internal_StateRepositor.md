# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IApplicationResourceResolver,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800071d0`
- end: `0x18000725c`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIApplicationResourceResolver@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `140`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006d10`
- `0x180007270`
- `0x180007280`

## callees

- `0x180004460`
- `0x18000532c`
- `0x1800071d0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IApplicationResourceResolver,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  const struct _GUID *v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  const struct _GUID *v6; // rcx
  _QWORD *v7; // r8
  __int64 v8; // r9
  __int64 v9; // r10
  int CanCastTo; // ebx

  *a3 = 0;
  if ( InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046)
    || InlineIsEqualGUID(v3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90) )
  {
    *v4 = v5;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  if ( InlineIsEqualGUID(v6, &GUID_ceea08dc_f598_4d17_85f5_713c8f3194d3) )
  {
    *v7 = v8;
    CanCastTo = 0;
LABEL_6:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
    return (unsigned int)CanCastTo;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(
                v8 + 8,
                v9);
  if ( CanCastTo >= 0 )
    goto LABEL_6;
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x1800071d0  push    rbx
0x1800071d2  sub     rsp, 20h
0x1800071d6  mov     r10, rdx
0x1800071d9  mov     qword ptr [r8], 0
0x1800071e0  mov     r9, rcx
0x1800071e3  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x1800071ea  mov     rcx, r10; struct _GUID *
0x1800071ed  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800071f2  test    eax, eax
0x1800071f4  jnz     short loc_180007240
0x1800071f6  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x1800071fd  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180007202  test    eax, eax
0x180007204  jnz     short loc_180007240
0x180007206  lea     rdx, _GUID_ceea08dc_f598_4d17_85f5_713c8f3194d3; struct _GUID *
0x18000720d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180007212  test    eax, eax
0x180007214  jz      short loc_18000721D
0x180007216  mov     [r8], r9
0x180007219  xor     ebx, ebx
0x18000721b  jmp     short loc_18000722F
0x18000721d  lea     rcx, [r9+8]
0x180007221  mov     rdx, r10
0x180007224  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x180007229  mov     ebx, eax
0x18000722b  test    eax, eax
0x18000722d  js      short loc_180007254
0x18000722f  mov     rcx, [r8]
0x180007232  mov     rax, [rcx]
0x180007235  mov     rax, [rax+8]
0x180007239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000723e  jmp     short loc_180007254
0x180007240  mov     [r8], r9
0x180007243  mov     rcx, r9
0x180007246  mov     rax, [r9]
0x180007249  mov     rax, [rax+8]
0x18000724d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007252  xor     ebx, ebx
0x180007254  mov     eax, ebx
0x180007256  add     rsp, 20h
0x18000725a  pop     rbx
0x18000725b  retn
```
