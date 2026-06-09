# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IPackageResourceResolver,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007720`
- end: `0x1800077ac`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIPackageResourceResolver@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `140`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007370`
- `0x1800077c0`
- `0x1800077d0`

## callees

- `0x180004460`
- `0x18000532c`
- `0x180007720`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IPackageResourceResolver,Microsoft::WRL::FtmBase>::QueryInterface(
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
  const struct _GUID *v9; // r10
  int CanCastTo; // ebx

  *a3 = 0;
  if ( InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046)
    || InlineIsEqualGUID(v3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90) )
  {
    *v4 = v5;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  if ( InlineIsEqualGUID(v6, &GUID_5f23e0db_307f_47c2_b201_f75be694da0d) )
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
0x180007720  push    rbx
0x180007722  sub     rsp, 20h
0x180007726  mov     r10, rdx
0x180007729  mov     qword ptr [r8], 0
0x180007730  mov     r9, rcx
0x180007733  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x18000773a  mov     rcx, r10; struct _GUID *
0x18000773d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180007742  test    eax, eax
0x180007744  jnz     short loc_180007790
0x180007746  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x18000774d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180007752  test    eax, eax
0x180007754  jnz     short loc_180007790
0x180007756  lea     rdx, _GUID_5f23e0db_307f_47c2_b201_f75be694da0d; struct _GUID *
0x18000775d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180007762  test    eax, eax
0x180007764  jz      short loc_18000776D
0x180007766  mov     [r8], r9
0x180007769  xor     ebx, ebx
0x18000776b  jmp     short loc_18000777F
0x18000776d  lea     rcx, [r9+8]
0x180007771  mov     rdx, r10
0x180007774  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x180007779  mov     ebx, eax
0x18000777b  test    eax, eax
0x18000777d  js      short loc_1800077A4
0x18000777f  mov     rcx, [r8]
0x180007782  mov     rax, [rcx]
0x180007785  mov     rax, [rax+8]
0x180007789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000778e  jmp     short loc_1800077A4
0x180007790  mov     [r8], r9
0x180007793  mov     rcx, r9
0x180007796  mov     rax, [r9]
0x180007799  mov     rax, [rax+8]
0x18000779d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077a2  xor     ebx, ebx
0x1800077a4  mov     eax, ebx
0x1800077a6  add     rsp, 20h
0x1800077aa  pop     rbx
0x1800077ab  retn
```
