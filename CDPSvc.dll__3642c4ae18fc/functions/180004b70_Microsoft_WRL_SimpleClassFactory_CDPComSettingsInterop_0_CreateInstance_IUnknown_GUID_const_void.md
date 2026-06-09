# Microsoft::WRL::SimpleClassFactory<CDPComSettingsInterop,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004b70`
- end: `0x180004d9b`
- name: `?CreateInstance@?$SimpleClassFactory@VCDPComSettingsInterop@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `555`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003e60`
- `0x180004614`
- `0x180004b70`
- `0x1800225d0`
- `0x180022acc`
- `0x18003c090`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004b98`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004b98`
- `cdp!CDPCreateSettingsInteropInternal` at `0x180004c3e`
- `cdp!CDPCreateSettingsInteropInternal` at `0x180004c3e`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CDPComSettingsInterop,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  int v9; // esi
  int v10; // r9d
  __int64 v11; // r14
  _DWORD *v12; // rax
  _QWORD *v13; // rdx
  std::_Ref_count_base *v14; // rcx
  __int64 v15; // rax
  int v16; // esi
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD *); // rcx
  unsigned int v18; // ebx
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v20)(_QWORD, __int64, _QWORD *); // [rsp+30h] [rbp-48h] BYREF
  __int64 v21; // [rsp+38h] [rbp-40h] BYREF
  _QWORD *v22; // [rsp+40h] [rbp-38h]
  int v23; // [rsp+88h] [rbp+10h] BYREF
  int v24; // [rsp+98h] [rbp+20h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    RoOriginateError(2147746064LL, 0);
    return 2147746064LL;
  }
  v20 = 0;
  v7 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v7;
  if ( !v7 )
  {
    v16 = -2147024882;
    goto LABEL_11;
  }
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICDPComNearShareSenderHost,IFastRundown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICDPComNearShareSenderHost,IFastRundown>(v7);
  *v8 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICDPComSettingsInterop,IFastRundown>::`vftable'{for `ICDPComSettingsInterop'};
  v8[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICDPComSettingsInterop,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v8 = &CDPComSettingsInterop::`vftable'{for `ICDPComSettingsInterop'};
  v8[1] = &CDPComSettingsInterop::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'};
  v8[3] = 0;
  v8[4] = 0;
  v21 = 0;
  v22 = v8 + 3;
  v9 = CDPCreateSettingsInteropInternal(&v21);
  v11 = v21;
  if ( v21 )
  {
    v12 = operator new(0x18u);
    v12[2] = 1;
    v12[3] = 1;
    *(_QWORD *)v12 = &std::_Ref_count_resource<ICDPSettingsInterop *,cdp::detail::iunknown_deleter<ICDPSettingsInterop>>::`vftable';
    *((_QWORD *)v12 + 2) = v11;
    v13 = v22;
    *v22 = v11;
    v14 = (std::_Ref_count_base *)v13[1];
    v13[1] = v12;
    if ( !v14 )
      goto LABEL_8;
  }
  else
  {
    v13 = v22;
    *v22 = 0;
    v14 = (std::_Ref_count_base *)v13[1];
    v13[1] = 0;
    if ( !v14 )
      goto LABEL_8;
  }
  std::_Ref_count_base::_Decref(v14);
LABEL_8:
  if ( v9 < 0 )
  {
    v23 = v9;
    v24 = 20;
    Log<long &,char const (&)[62],int>((_DWORD)v14, (_DWORD)v13, (unsigned int)&v23, v10, (__int64)&v24);
    v16 = v23;
    v15 = *v8;
    if ( v23 < 0 )
    {
      (*(void (__fastcall **)(_QWORD *))(v15 + 16))(v8);
      goto LABEL_11;
    }
  }
  else
  {
    v15 = *v8;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD))v15)(v8, &GUID_00000000_0000_0000_c000_000000000046, &v20);
  (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
  if ( v16 < 0 )
  {
LABEL_11:
    v17 = v20;
    if ( v20 )
    {
      v20 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v17)[2])(v17);
    }
    return (unsigned int)v16;
  }
  v18 = (**v20)(v20, a3, a4);
  v19 = v20;
  if ( v20 )
  {
    v20 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v19)[2])(v19);
  }
  return v18;
}

```

## disassembly

```asm
0x180004b70  mov     [rsp+arg_0], rbx
0x180004b75  push    rbp
0x180004b76  push    rsi
0x180004b77  push    rdi
0x180004b78  push    r14
0x180004b7a  push    r15
0x180004b7c  sub     rsp, 50h
0x180004b80  mov     rdi, r9
0x180004b83  mov     rbp, r8
0x180004b86  xor     r15d, r15d
0x180004b89  mov     [r9], r15
0x180004b8c  test    rdx, rdx
0x180004b8f  jz      short loc_180004BB7
0x180004b91  xor     edx, edx
0x180004b93  mov     ecx, 80040110h
0x180004b98  call    cs:__imp_RoOriginateError
0x180004b9e  mov     eax, 80040110h
0x180004ba3  mov     rbx, [rsp+78h+arg_0]
0x180004bab  add     rsp, 50h
0x180004baf  pop     r15
0x180004bb1  pop     r14
0x180004bb3  pop     rdi
0x180004bb4  pop     rsi
0x180004bb5  pop     rbp
0x180004bb6  retn
0x180004bb7  mov     [rsp+78h+var_48], r15
0x180004bbc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004bc3  mov     ecx, 28h ; '('; unsigned __int64
0x180004bc8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004bcd  mov     rbx, rax
0x180004bd0  test    rax, rax
0x180004bd3  jz      loc_180004D91
0x180004bd9  mov     rcx, rax
0x180004bdc  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICDPComNearShareSenderHost@@UIFastRundown@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICDPComNearShareSenderHost,IFastRundown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICDPComNearShareSenderHost,IFastRundown>(void)
0x180004be1  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICDPComSettingsInterop@@UIFastRundown@@@WRL@Microsoft@@6BICDPComSettingsInterop@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICDPComSettingsInterop,IFastRundown>::`vftable'{for `ICDPComSettingsInterop'}
0x180004be8  mov     [rbx], rcx
0x180004beb  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICDPComSettingsInterop@@UIFastRundown@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIFastRundown@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICDPComSettingsInterop,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'}
0x180004bf2  mov     [rbx+8], rax
0x180004bf6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004bfd  test    rcx, rcx
0x180004c00  jz      short loc_180004C0F
0x180004c02  mov     rax, [rcx]
0x180004c05  mov     rax, [rax+8]
0x180004c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c0e  nop
0x180004c0f  lea     rax, ??_7CDPComSettingsInterop@@6BICDPComSettingsInterop@@@; const CDPComSettingsInterop::`vftable'{for `ICDPComSettingsInterop'}
0x180004c16  mov     [rbx], rax
0x180004c19  lea     rax, ??_7CDPComSettingsInterop@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIFastRundown@@@Details@WRL@Microsoft@@@; const CDPComSettingsInterop::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'}
0x180004c20  mov     [rbx+8], rax
0x180004c24  lea     rax, [rbx+18h]
0x180004c28  mov     [rax], r15
0x180004c2b  mov     [rax+8], r15
0x180004c2f  mov     [rsp+78h+var_40], r15
0x180004c34  mov     [rsp+78h+var_38], rax
0x180004c39  lea     rcx, [rsp+78h+var_40]
0x180004c3e  call    cs:__imp_CDPCreateSettingsInteropInternal
0x180004c44  mov     esi, eax
0x180004c46  mov     r14, [rsp+78h+var_40]
0x180004c4b  test    r14, r14
0x180004c4e  jz      loc_180004CEA
0x180004c54  mov     ecx, 18h; Size
0x180004c59  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c5e  mov     dword ptr [rax+8], 1
0x180004c65  mov     dword ptr [rax+0Ch], 1
0x180004c6c  lea     rcx, ??_7?$_Ref_count_resource@PEAVICDPSettingsInterop@@U?$iunknown_deleter@VICDPSettingsInterop@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPSettingsInterop *,cdp::detail::iunknown_deleter<ICDPSettingsInterop>>::`vftable'
0x180004c73  mov     [rax], rcx
0x180004c76  mov     [rax+10h], r14
0x180004c7a  mov     rdx, [rsp+78h+var_38]
0x180004c7f  mov     [rdx], r14
0x180004c82  mov     rcx, [rdx+8]
0x180004c86  mov     [rdx+8], rax
0x180004c8a  test    rcx, rcx
0x180004c8d  jnz     short loc_180004CFF
0x180004c8f  test    esi, esi
0x180004c91  js      loc_180004D41
0x180004c97  mov     rax, [rbx]
0x180004c9a  lea     r8, [rsp+78h+var_48]
0x180004c9f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004ca6  mov     rcx, rbx
0x180004ca9  mov     rax, [rax]
0x180004cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cb1  mov     esi, eax
0x180004cb3  mov     rax, [rbx]
0x180004cb6  mov     rcx, rbx
0x180004cb9  mov     rax, [rax+10h]
0x180004cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc2  nop
0x180004cc3  test    esi, esi
0x180004cc5  jns     short loc_180004D06
0x180004cc7  mov     rcx, [rsp+78h+var_48]
0x180004ccc  test    rcx, rcx
0x180004ccf  jz      short loc_180004CE3
0x180004cd1  mov     [rsp+78h+var_48], r15
0x180004cd6  mov     rdx, [rcx]
0x180004cd9  mov     rax, [rdx+10h]
0x180004cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce2  nop
0x180004ce3  mov     eax, esi
0x180004ce5  jmp     loc_180004BA3
0x180004cea  mov     rdx, [rsp+78h+var_38]
0x180004cef  mov     [rdx], r15
0x180004cf2  mov     rcx, [rdx+8]; this
0x180004cf6  mov     [rdx+8], r15
0x180004cfa  test    rcx, rcx
0x180004cfd  jz      short loc_180004C8F
0x180004cff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180004d04  jmp     short loc_180004C8F
0x180004d06  mov     rcx, [rsp+78h+var_48]
0x180004d0b  mov     rax, [rcx]
0x180004d0e  mov     r8, rdi
0x180004d11  mov     rdx, rbp
0x180004d14  mov     rax, [rax]
0x180004d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d1c  mov     ebx, eax
0x180004d1e  mov     rcx, [rsp+78h+var_48]
0x180004d23  test    rcx, rcx
0x180004d26  jz      short loc_180004D3A
0x180004d28  mov     [rsp+78h+var_48], r15
0x180004d2d  mov     rdx, [rcx]
0x180004d30  mov     rax, [rdx+10h]
0x180004d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d39  nop
0x180004d3a  mov     eax, ebx
0x180004d3c  jmp     loc_180004BA3
0x180004d41  mov     [rsp+78h+arg_8], esi
0x180004d48  mov     [rsp+78h+arg_18], 14h
0x180004d53  lea     rax, [rsp+78h+arg_18]
0x180004d5b  mov     [rsp+78h+var_58], rax
0x180004d60  lea     r8, [rsp+78h+arg_8]
0x180004d68  call    ??$Log@AEAJAEAY0DO@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0DO@$$CBD$$QEAH@Z; Log<long &,char const (&)[62],int>(CDPLogLevel,char const *,long &,char const (&)[62],int &&)
0x180004d6d  mov     esi, [rsp+78h+arg_8]
0x180004d74  mov     rax, [rbx]
0x180004d77  test    esi, esi
0x180004d79  jns     loc_180004C9A
0x180004d7f  mov     rcx, rbx
0x180004d82  mov     rax, [rax+10h]
0x180004d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d8b  nop
0x180004d8c  jmp     loc_180004CC7
0x180004d91  mov     esi, 8007000Eh
0x180004d96  jmp     loc_180004CC7
```
