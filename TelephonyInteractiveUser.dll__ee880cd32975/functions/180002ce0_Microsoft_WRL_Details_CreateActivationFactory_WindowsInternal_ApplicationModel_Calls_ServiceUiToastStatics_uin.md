# Microsoft::WRL::Details::CreateActivationFactory<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002ce0`
- end: `0x180002e7e`
- name: `??$CreateActivationFactory@VServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001de4`
- `0x180002ce0`
- `0x180004220`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics>(
        _BYTE *a1,
        __int64 a2,
        _DWORD *a3,
        _QWORD *a4)
{
  char *v7; // rax
  _QWORD *v8; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v10; // rcx
  volatile signed __int32 *v11; // rdi
  _QWORD *v12; // r15
  _QWORD *v13; // r13
  _BYTE *v14; // rbp
  signed __int32 v15; // edx
  __int64 v16; // rdx
  __int64 v17; // rdx
  signed __int32 v18; // eax

  v7 = (char *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  v10 = Microsoft::WRL::Details::ModuleBase::module_;
  v11 = (volatile signed __int32 *)(v7 + 36);
  *((_DWORD *)v7 + 9) = 1;
  v12 = v7 + 8;
  *(_QWORD *)v7 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `IActivationFactory'};
  *((_QWORD *)v7 + 1) = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  v13 = v7 + 48;
  *((_QWORD *)v7 + 6) = 0;
  v14 = v7 + 56;
  *((_DWORD *)v7 + 14) = 4;
  if ( v10 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v10 + 8LL))(v10);
  *v8 = &WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::`vftable'{for `IActivationFactory'};
  *v12 = &WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  do
  {
    v15 = *v11;
    if ( *v11 == 0x7FFFFFFF )
    {
      v16 = 0x7FFFFFFF;
      goto LABEL_9;
    }
  }
  while ( v15 != _InterlockedCompareExchange(v11, v15 + 1, v15) );
  v16 = (unsigned int)(v15 + 1);
LABEL_9:
  if ( (*v14 & 4) == 0 && (_DWORD)v16 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                           + 8LL))(
      Microsoft::WRL::Details::ModuleBase::module_,
      v16,
      0x7FFFFFFF);
  Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
    (__int64)v8,
    v16);
  if ( *a3 == 53 )
  {
    if ( a3[1] != *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data2
      || a3[2] != *(_DWORD *)GUID_00000035_0000_0000_c000_000000000046.Data4
      || a3[3] != *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data4[4] )
    {
LABEL_17:
      Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
        (__int64)v8,
        v17);
      return 2147500034LL;
    }
  }
  else
  {
    if ( *a3 != -621168275
      || a3[1] != *(_DWORD *)&GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67.Data2
      || a3[2] != *(_DWORD *)GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67.Data4
      || a3[3] != *(_DWORD *)&GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67.Data4[4] )
    {
      goto LABEL_17;
    }
    v8 = v12;
  }
  *a4 = v8;
  if ( (*a1 & 4) == 0 )
  {
    do
    {
      if ( *v11 == 0x7FFFFFFF )
        break;
      v18 = *v11;
    }
    while ( v18 != _InterlockedCompareExchange(v11, v18 + 1, v18) );
  }
  *(_DWORD *)v14 = *(_DWORD *)a1;
  *v13 = a2;
  return 0;
}

```

## disassembly

```asm
0x180002ce0  mov     [rsp+arg_8], rbx
0x180002ce5  push    rbp
0x180002ce6  push    rsi
0x180002ce7  push    rdi
0x180002ce8  push    r12
0x180002cea  push    r13
0x180002cec  push    r14
0x180002cee  push    r15
0x180002cf0  sub     rsp, 30h
0x180002cf4  mov     [rsp+68h+var_48], rdx
0x180002cf9  mov     r12, rcx
0x180002cfc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002d03  mov     ecx, 40h ; '@'; unsigned __int64
0x180002d08  mov     r14, r9
0x180002d0b  mov     rsi, r8
0x180002d0e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002d13  mov     rbx, rax
0x180002d16  test    rax, rax
0x180002d19  jnz     short loc_180002D25
0x180002d1b  mov     eax, 8007000Eh
0x180002d20  jmp     loc_180002E05
0x180002d25  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002d2c  lea     rdi, [rax+24h]
0x180002d30  mov     dword ptr [rdi], 1
0x180002d36  lea     r15, [rax+8]
0x180002d3a  lea     rax, ??_7?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6BIActivationFactory@@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `IActivationFactory'}
0x180002d41  mov     [rbx], rax
0x180002d44  lea     rax, ??_7?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00U?$ImplementsMarker@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@@Details@23@VNil@523@V6523@V6523@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180002d4b  mov     [r15], rax
0x180002d4e  lea     r13, [rbx+30h]
0x180002d52  mov     qword ptr [r13+0], 0
0x180002d5a  lea     rbp, [rbx+38h]
0x180002d5e  mov     dword ptr [rbp+0], 4
0x180002d65  test    rcx, rcx
0x180002d68  jz      short loc_180002D76
0x180002d6a  mov     rax, [rcx]
0x180002d6d  mov     rax, [rax+8]
0x180002d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d76  lea     rax, ??_7ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@6BIActivationFactory@@@; const WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::`vftable'{for `IActivationFactory'}
0x180002d7d  mov     r8d, 7FFFFFFFh
0x180002d83  mov     [rbx], rax
0x180002d86  lea     rax, ??_7ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00U?$ImplementsMarker@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@@Details@23@VNil@523@V6523@V6523@@Details@WRL@Microsoft@@@; const WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180002d8d  mov     [r15], rax
0x180002d90  jmp     short loc_180002D9D
0x180002d92  lea     ecx, [rdx+1]
0x180002d95  mov     eax, edx
0x180002d97  lock cmpxchg [rdi], ecx
0x180002d9b  jz      short loc_180002E1A
0x180002d9d  mov     edx, [rdi]
0x180002d9f  cmp     edx, r8d
0x180002da2  jnz     short loc_180002D92
0x180002da4  mov     edx, r8d
0x180002da7  test    byte ptr [rbp+0], 4
0x180002dab  jnz     short loc_180002DCA
0x180002dad  cmp     edx, 2
0x180002db0  jnz     short loc_180002DCA
0x180002db2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002db9  test    rcx, rcx
0x180002dbc  jz      short loc_180002DCA
0x180002dbe  mov     rax, [rcx]
0x180002dc1  mov     rax, [rax+8]
0x180002dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dca  mov     rcx, rbx
0x180002dcd  call    ?Release@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180002dd2  cmp     dword ptr [rsi], 35h ; '5'
0x180002dd5  jnz     short loc_180002E1E
0x180002dd7  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x180002ddd  cmp     [rsi+4], eax
0x180002de0  jnz     short loc_180002DF8
0x180002de2  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x180002de8  cmp     [rsi+8], eax
0x180002deb  jnz     short loc_180002DF8
0x180002ded  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x180002df3  cmp     [rsi+0Ch], eax
0x180002df6  jz      short loc_180002E4A
0x180002df8  mov     rcx, rbx
0x180002dfb  call    ?Release@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180002e00  mov     eax, 80004002h
0x180002e05  mov     rbx, [rsp+68h+arg_8]
0x180002e0a  add     rsp, 30h
0x180002e0e  pop     r15
0x180002e10  pop     r14
0x180002e12  pop     r13
0x180002e14  pop     r12
0x180002e16  pop     rdi
0x180002e17  pop     rsi
0x180002e18  pop     rbp
0x180002e19  retn
0x180002e1a  inc     edx
0x180002e1c  jmp     short loc_180002DA7
0x180002e1e  cmp     dword ptr [rsi], 0DAF9B96Dh
0x180002e24  jnz     short loc_180002DF8
0x180002e26  mov     eax, dword ptr cs:_GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67.Data2
0x180002e2c  cmp     [rsi+4], eax
0x180002e2f  jnz     short loc_180002DF8
0x180002e31  mov     eax, dword ptr cs:_GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67.Data4
0x180002e37  cmp     [rsi+8], eax
0x180002e3a  jnz     short loc_180002DF8
0x180002e3c  mov     eax, dword ptr cs:_GUID_daf9b96d_b02b_4c08_a51e_bfaf8e625d67.Data4+4
0x180002e42  cmp     [rsi+0Ch], eax
0x180002e45  jnz     short loc_180002DF8
0x180002e47  mov     rbx, r15
0x180002e4a  mov     [r14], rbx
0x180002e4d  test    byte ptr [r12], 4
0x180002e52  jnz     short loc_180002E6A
0x180002e54  mov     edx, 7FFFFFFFh
0x180002e59  jmp     short loc_180002E64
0x180002e5b  lea     ecx, [rax+1]
0x180002e5e  lock cmpxchg [rdi], ecx
0x180002e62  jz      short loc_180002E6A
0x180002e64  mov     eax, [rdi]
0x180002e66  cmp     eax, edx
0x180002e68  jnz     short loc_180002E5B
0x180002e6a  mov     eax, [r12]
0x180002e6e  mov     [rbp+0], eax
0x180002e71  mov     rax, [rsp+68h+var_48]
0x180002e76  mov     [r13+0], rax
0x180002e7a  xor     eax, eax
0x180002e7c  jmp     short loc_180002E05
```
