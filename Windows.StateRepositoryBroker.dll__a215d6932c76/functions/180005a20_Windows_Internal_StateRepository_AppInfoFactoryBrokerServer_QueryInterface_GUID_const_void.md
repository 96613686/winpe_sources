# Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::QueryInterface(_GUID const &,void * *)

- ea: `0x180005a20`
- end: `0x180005aac`
- name: `?QueryInterface@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `140`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::AppInfoFactoryBrokerServer *this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005ac0`
- `0x180005ad0`

## callees

- `0x180004460`
- `0x18000532c`
- `0x180005a20`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::QueryInterface(
        Windows::Internal::StateRepository::AppInfoFactoryBrokerServer *this,
        const struct _GUID *a2,
        void **a3)
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
  if ( InlineIsEqualGUID(v6, &GUID_6305b671_f6cd_4ff6_9120_e0c4cd921011) )
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
0x180005a20  push    rbx
0x180005a22  sub     rsp, 20h
0x180005a26  mov     r10, rdx
0x180005a29  mov     r9, rcx
0x180005a2c  mov     qword ptr [r8], 0
0x180005a33  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x180005a3a  mov     rcx, r10; struct _GUID *
0x180005a3d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180005a42  test    eax, eax
0x180005a44  jnz     short loc_180005A90
0x180005a46  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x180005a4d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180005a52  test    eax, eax
0x180005a54  jnz     short loc_180005A90
0x180005a56  lea     rdx, _GUID_6305b671_f6cd_4ff6_9120_e0c4cd921011; struct _GUID *
0x180005a5d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180005a62  test    eax, eax
0x180005a64  jz      short loc_180005A6D
0x180005a66  mov     [r8], r9
0x180005a69  xor     ebx, ebx
0x180005a6b  jmp     short loc_180005A7F
0x180005a6d  lea     rcx, [r9+8]
0x180005a71  mov     rdx, r10
0x180005a74  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x180005a79  mov     ebx, eax
0x180005a7b  test    eax, eax
0x180005a7d  js      short loc_180005AA4
0x180005a7f  mov     rcx, [r8]
0x180005a82  mov     rax, [rcx]
0x180005a85  mov     rax, [rax+8]
0x180005a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a8e  jmp     short loc_180005AA4
0x180005a90  mov     [r8], r9
0x180005a93  mov     rax, [r9]
0x180005a96  mov     rcx, r9
0x180005a99  mov     rax, [rax+8]
0x180005a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aa2  xor     ebx, ebx
0x180005aa4  mov     eax, ebx
0x180005aa6  add     rsp, 20h
0x180005aaa  pop     rbx
0x180005aab  retn
```
