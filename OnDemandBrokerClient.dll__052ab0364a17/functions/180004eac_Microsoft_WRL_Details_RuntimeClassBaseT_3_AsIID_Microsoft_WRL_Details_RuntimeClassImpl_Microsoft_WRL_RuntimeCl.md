# Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IInspectable>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IInspectable> *,_GUID const &,void * *)

- ea: `0x180004eac`
- end: `0x180004f91`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIInspectable@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIInspectable@@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `229`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005f00`

## callees

- `0x180004eac`
- `0x180005b30`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IInspectable>>(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  const struct _GUID *v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r10
  const struct _GUID *v6; // rdx
  const struct _GUID *v7; // rcx
  const struct _GUID *v8; // rcx
  _QWORD *v9; // r8
  __int64 v10; // r10
  int v11; // ebx
  const struct _GUID *v12; // rcx
  __int64 v13; // r10
  const struct _GUID *v14; // rcx
  const struct _GUID *v15; // rcx
  __int64 v16; // r10
  const struct _GUID *v17; // r11
  __int64 v18; // r10

  *a3 = 0;
  if ( !(unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046)
    && !(unsigned int)InlineIsEqualGUID(v3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90) )
  {
    if ( (unsigned int)InlineIsEqualGUID(v7, v6) )
    {
      *v9 = v10;
      v11 = 0;
      goto LABEL_15;
    }
    if ( (unsigned int)InlineIsEqualGUID(v8, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90)
      || (unsigned int)InlineIsEqualGUID(v12, &GUID_00000003_0000_0000_c000_000000000046) )
    {
      v11 = 0;
      *v9 = v13;
      goto LABEL_15;
    }
    if ( (unsigned int)InlineIsEqualGUID(v14, &GUID_00000038_0000_0000_c000_000000000046) )
    {
      *v9 = v16;
    }
    else
    {
      if ( !(unsigned int)InlineIsEqualGUID(v15, v17) )
      {
        v11 = -2147467262;
LABEL_14:
        if ( v11 < 0 )
          return (unsigned int)v11;
LABEL_15:
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
        return (unsigned int)v11;
      }
      *v9 = v18 + 8;
    }
    v11 = 0;
    goto LABEL_14;
  }
  *v4 = v5;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x180004eac  push    rbx
0x180004eae  sub     rsp, 20h
0x180004eb2  mov     r9, rdx
0x180004eb5  mov     qword ptr [r8], 0
0x180004ebc  mov     r10, rcx
0x180004ebf  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x180004ec6  mov     rcx, r9; struct _GUID *
0x180004ec9  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180004ece  test    eax, eax
0x180004ed0  jnz     loc_180004F77
0x180004ed6  lea     r11, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180004edd  mov     rdx, r11; struct _GUID *
0x180004ee0  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180004ee5  test    eax, eax
0x180004ee7  jnz     loc_180004F77
0x180004eed  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180004ef2  test    eax, eax
0x180004ef4  jz      short loc_180004EFD
0x180004ef6  mov     [r8], r10
0x180004ef9  xor     ebx, ebx
0x180004efb  jmp     short loc_180004F64
0x180004efd  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90; struct _GUID *
0x180004f04  add     r10, 8
0x180004f08  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180004f0d  test    eax, eax
0x180004f0f  jnz     short loc_180004F21
0x180004f11  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046; struct _GUID *
0x180004f18  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180004f1d  test    eax, eax
0x180004f1f  jz      short loc_180004F2B
0x180004f21  mov     rax, r8
0x180004f24  xor     ebx, ebx
0x180004f26  mov     [rax], r10
0x180004f29  jmp     short loc_180004F64
0x180004f2b  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046; struct _GUID *
0x180004f32  add     r10, 20h ; ' '
0x180004f36  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180004f3b  test    eax, eax
0x180004f3d  jz      short loc_180004F46
0x180004f3f  mov     [r8], r10
0x180004f42  xor     ebx, ebx
0x180004f44  jmp     short loc_180004F60
0x180004f46  mov     rdx, r11; struct _GUID *
0x180004f49  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180004f4e  test    eax, eax
0x180004f50  jz      short loc_180004F5B
0x180004f52  lea     rax, [r10+8]
0x180004f56  mov     [r8], rax
0x180004f59  jmp     short loc_180004F42
0x180004f5b  mov     ebx, 80004002h
0x180004f60  test    ebx, ebx
0x180004f62  js      short loc_180004F73
0x180004f64  mov     rcx, [r8]
0x180004f67  mov     rdx, [rcx]
0x180004f6a  mov     rax, [rdx+8]
0x180004f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f73  mov     eax, ebx
0x180004f75  jmp     short loc_180004F8B
0x180004f77  mov     [r8], r10
0x180004f7a  mov     rcx, r10
0x180004f7d  mov     rax, [r10]
0x180004f80  mov     rax, [rax+8]
0x180004f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f89  xor     eax, eax
0x180004f8b  add     rsp, 20h
0x180004f8f  pop     rbx
0x180004f90  retn
```
