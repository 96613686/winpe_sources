# Microsoft::WRL::Details::CreateActivationFactory<WindowsInternal::ApplicationModel::Calls::AppLauncherStatics>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x1800029f0`
- end: `0x180002b8e`
- name: `??$CreateActivationFactory@VAppLauncherStatics@Calls@ApplicationModel@WindowsInternal@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001de4`
- `0x1800029f0`
- `0x180004220`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<WindowsInternal::ApplicationModel::Calls::AppLauncherStatics>(
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
  *(_QWORD *)v7 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IAppLauncherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `IActivationFactory'};
  *((_QWORD *)v7 + 1) = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IAppLauncherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IAppLauncherStatics>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  v13 = v7 + 48;
  *((_QWORD *)v7 + 6) = 0;
  v14 = v7 + 56;
  *((_DWORD *)v7 + 14) = 4;
  if ( v10 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v10 + 8LL))(v10);
  *v8 = &WindowsInternal::ApplicationModel::Calls::AppLauncherStatics::`vftable'{for `IActivationFactory'};
  *v12 = &WindowsInternal::ApplicationModel::Calls::AppLauncherStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IAppLauncherStatics>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
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
    if ( *a3 != 1402147373
      || a3[1] != *(_DWORD *)&GUID_5393122d_07dd_45d3_9aed_acfbf1895eab.Data2
      || a3[2] != *(_DWORD *)GUID_5393122d_07dd_45d3_9aed_acfbf1895eab.Data4
      || a3[3] != *(_DWORD *)&GUID_5393122d_07dd_45d3_9aed_acfbf1895eab.Data4[4] )
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
0x1800029f0  mov     [rsp+arg_8], rbx
0x1800029f5  push    rbp
0x1800029f6  push    rsi
0x1800029f7  push    rdi
0x1800029f8  push    r12
0x1800029fa  push    r13
0x1800029fc  push    r14
0x1800029fe  push    r15
0x180002a00  sub     rsp, 30h
0x180002a04  mov     [rsp+68h+var_48], rdx
0x180002a09  mov     r12, rcx
0x180002a0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002a13  mov     ecx, 40h ; '@'; unsigned __int64
0x180002a18  mov     r14, r9
0x180002a1b  mov     rsi, r8
0x180002a1e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002a23  mov     rbx, rax
0x180002a26  test    rax, rax
0x180002a29  jnz     short loc_180002A35
0x180002a2b  mov     eax, 8007000Eh
0x180002a30  jmp     loc_180002B15
0x180002a35  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002a3c  lea     rdi, [rax+24h]
0x180002a40  mov     dword ptr [rdi], 1
0x180002a46  lea     r15, [rax+8]
0x180002a4a  lea     rax, ??_7?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIAppLauncherStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6BIActivationFactory@@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IAppLauncherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `IActivationFactory'}
0x180002a51  mov     [rbx], rax
0x180002a54  lea     rax, ??_7?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIAppLauncherStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00U?$ImplementsMarker@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIAppLauncherStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@@Details@23@VNil@523@V6523@V6523@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IAppLauncherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IAppLauncherStatics>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180002a5b  mov     [r15], rax
0x180002a5e  lea     r13, [rbx+30h]
0x180002a62  mov     qword ptr [r13+0], 0
0x180002a6a  lea     rbp, [rbx+38h]
0x180002a6e  mov     dword ptr [rbp+0], 4
0x180002a75  test    rcx, rcx
0x180002a78  jz      short loc_180002A86
0x180002a7a  mov     rax, [rcx]
0x180002a7d  mov     rax, [rax+8]
0x180002a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a86  lea     rax, ??_7AppLauncherStatics@Calls@ApplicationModel@WindowsInternal@@6BIActivationFactory@@@; const WindowsInternal::ApplicationModel::Calls::AppLauncherStatics::`vftable'{for `IActivationFactory'}
0x180002a8d  mov     r8d, 7FFFFFFFh
0x180002a93  mov     [rbx], rax
0x180002a96  lea     rax, ??_7AppLauncherStatics@Calls@ApplicationModel@WindowsInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00U?$ImplementsMarker@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIAppLauncherStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@@Details@23@VNil@523@V6523@V6523@@Details@WRL@Microsoft@@@; const WindowsInternal::ApplicationModel::Calls::AppLauncherStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IAppLauncherStatics>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180002a9d  mov     [r15], rax
0x180002aa0  jmp     short loc_180002AAD
0x180002aa2  lea     ecx, [rdx+1]
0x180002aa5  mov     eax, edx
0x180002aa7  lock cmpxchg [rdi], ecx
0x180002aab  jz      short loc_180002B2A
0x180002aad  mov     edx, [rdi]
0x180002aaf  cmp     edx, r8d
0x180002ab2  jnz     short loc_180002AA2
0x180002ab4  mov     edx, r8d
0x180002ab7  test    byte ptr [rbp+0], 4
0x180002abb  jnz     short loc_180002ADA
0x180002abd  cmp     edx, 2
0x180002ac0  jnz     short loc_180002ADA
0x180002ac2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002ac9  test    rcx, rcx
0x180002acc  jz      short loc_180002ADA
0x180002ace  mov     rax, [rcx]
0x180002ad1  mov     rax, [rax+8]
0x180002ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ada  mov     rcx, rbx
0x180002add  call    ?Release@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180002ae2  cmp     dword ptr [rsi], 35h ; '5'
0x180002ae5  jnz     short loc_180002B2E
0x180002ae7  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x180002aed  cmp     [rsi+4], eax
0x180002af0  jnz     short loc_180002B08
0x180002af2  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x180002af8  cmp     [rsi+8], eax
0x180002afb  jnz     short loc_180002B08
0x180002afd  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x180002b03  cmp     [rsi+0Ch], eax
0x180002b06  jz      short loc_180002B5A
0x180002b08  mov     rcx, rbx
0x180002b0b  call    ?Release@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180002b10  mov     eax, 80004002h
0x180002b15  mov     rbx, [rsp+68h+arg_8]
0x180002b1a  add     rsp, 30h
0x180002b1e  pop     r15
0x180002b20  pop     r14
0x180002b22  pop     r13
0x180002b24  pop     r12
0x180002b26  pop     rdi
0x180002b27  pop     rsi
0x180002b28  pop     rbp
0x180002b29  retn
0x180002b2a  inc     edx
0x180002b2c  jmp     short loc_180002AB7
0x180002b2e  cmp     dword ptr [rsi], 5393122Dh
0x180002b34  jnz     short loc_180002B08
0x180002b36  mov     eax, dword ptr cs:_GUID_5393122d_07dd_45d3_9aed_acfbf1895eab.Data2
0x180002b3c  cmp     [rsi+4], eax
0x180002b3f  jnz     short loc_180002B08
0x180002b41  mov     eax, dword ptr cs:_GUID_5393122d_07dd_45d3_9aed_acfbf1895eab.Data4
0x180002b47  cmp     [rsi+8], eax
0x180002b4a  jnz     short loc_180002B08
0x180002b4c  mov     eax, dword ptr cs:_GUID_5393122d_07dd_45d3_9aed_acfbf1895eab.Data4+4
0x180002b52  cmp     [rsi+0Ch], eax
0x180002b55  jnz     short loc_180002B08
0x180002b57  mov     rbx, r15
0x180002b5a  mov     [r14], rbx
0x180002b5d  test    byte ptr [r12], 4
0x180002b62  jnz     short loc_180002B7A
0x180002b64  mov     edx, 7FFFFFFFh
0x180002b69  jmp     short loc_180002B74
0x180002b6b  lea     ecx, [rax+1]
0x180002b6e  lock cmpxchg [rdi], ecx
0x180002b72  jz      short loc_180002B7A
0x180002b74  mov     eax, [rdi]
0x180002b76  cmp     eax, edx
0x180002b78  jnz     short loc_180002B6B
0x180002b7a  mov     eax, [r12]
0x180002b7e  mov     [rbp+0], eax
0x180002b81  mov     rax, [rsp+68h+var_48]
0x180002b86  mov     [r13+0], rax
0x180002b8a  xor     eax, eax
0x180002b8c  jmp     short loc_180002B15
```
