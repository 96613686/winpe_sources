# Windows::Internal::Details::CreateGitHelper<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Windows::Internal::GitPtr>(Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *> *,Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *> * *)

- ea: `0x18000f468`
- end: `0x18000f5fc`
- name: `??$CreateGitHelper@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@VGitPtr@Internal@4@@Details@Internal@Windows@@YAJPEAU?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@2@PEAPEAU3452@@Z`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800225b0`

## callees

- `0x180002380`
- `0x180002ed4`
- `0x18000f468`
- `0x180011744`
- `0x1800132ac`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Details::CreateGitHelper<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Windows::Internal::GitPtr>(
        __int64 a1,
        _QWORD *a2)
{
  _DWORD *v4; // rbx
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  Windows::Internal::Details::Git *v7; // rcx
  int v8; // edi

  *a2 = 0;
  v4 = 0;
  v5 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x40u);
    *(_QWORD *)v6 = &Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v6 + 2));
    v6[11] = 1;
    *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>'};
    *((_QWORD *)v6 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v7 = Microsoft::WRL::Details::ModuleBase::module_;
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v6 = &Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Windows::Internal::GitPtr,2>::`vftable'{for `Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>'};
    *((_QWORD *)v6 + 1) = &Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Windows::Internal::GitPtr,2>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *((_QWORD *)v6 + 6) = &Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
    v6[14] = 0;
    v6[15] = Windows::Internal::Details::Git::Acquire(v7);
    *((_QWORD *)v6 + 6) = &Windows::Internal::GitPtr::`vftable';
    v4 = v6;
  }
  if ( v4 )
  {
    v8 = 0;
    if ( v4[14] )
    {
      v8 = v4[15];
      if ( v8 >= 0 )
        v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_18005A068 + 32LL))(qword_18005A068);
    }
    v4[14] = 0;
    if ( v8 >= 0 )
    {
      if ( !a1
        || (v8 = v4[15], v8 >= 0)
        && (v8 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, _DWORD *))(*(_QWORD *)qword_18005A068 + 24LL))(
                   qword_18005A068,
                   a1,
                   &GUID_8d898f19_2a9e_5f0f_a13e_0fb5e9ff7c76,
                   v4 + 14),
            v8 >= 0) )
      {
        v8 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, _QWORD *))v4)(
               v4,
               &GUID_8d898f19_2a9e_5f0f_a13e_0fb5e9ff7c76,
               a2);
      }
    }
  }
  else
  {
    v8 = -2147024882;
  }
  if ( v4 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000f468  mov     [rsp+arg_0], rbx
0x18000f46d  mov     [rsp+arg_10], rbp
0x18000f472  push    rsi
0x18000f473  push    rdi
0x18000f474  push    r14
0x18000f476  sub     rsp, 30h
0x18000f47a  mov     r14, rdx
0x18000f47d  mov     rbp, rcx
0x18000f480  mov     qword ptr [rdx], 0
0x18000f487  mov     [rsp+48h+arg_8], 0
0x18000f490  xor     ebx, ebx
0x18000f492  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f499  lea     esi, [rbx+40h]
0x18000f49c  mov     ecx, esi; unsigned __int64
0x18000f49e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f4a3  mov     rdi, rax
0x18000f4a6  test    rax, rax
0x18000f4a9  jz      loc_18000F543
0x18000f4af  mov     r8d, esi; Size
0x18000f4b2  xor     edx, edx; Val
0x18000f4b4  mov     rcx, rax; void *
0x18000f4b7  call    memset_0
0x18000f4bc  nop
0x18000f4bd  lea     rax, ??_7?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@6B@; const Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>::`vftable'
0x18000f4c4  mov     [rdi], rax
0x18000f4c7  lea     rbx, [rdi+8]
0x18000f4cb  mov     rcx, rbx; this
0x18000f4ce  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000f4d3  mov     dword ptr [rdi+2Ch], 1
0x18000f4da  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>'}
0x18000f4e1  mov     [rdi], rax
0x18000f4e4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000f4eb  mov     [rbx], rax
0x18000f4ee  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000f4f5  test    rcx, rcx
0x18000f4f8  jz      short loc_18000F507
0x18000f4fa  mov     rax, [rcx]
0x18000f4fd  mov     rax, [rax+8]
0x18000f501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f506  nop
0x18000f507  lea     rax, ??_7?$GitInvokeHelper@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@VGitPtr@Internal@4@$01@Details@Internal@Windows@@6B?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@3@@; const Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Windows::Internal::GitPtr,2>::`vftable'{for `Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>'}
0x18000f50e  mov     [rdi], rax
0x18000f511  lea     rax, ??_7?$GitInvokeHelper@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@VGitPtr@Internal@4@$01@Details@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@1WRL@Microsoft@@@; const Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Windows::Internal::GitPtr,2>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000f518  mov     [rbx], rax
0x18000f51b  lea     rax, ??_7?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable'
0x18000f522  mov     [rdi+30h], rax
0x18000f526  mov     dword ptr [rdi+38h], 0
0x18000f52d  call    ?Acquire@Git@Details@Internal@Windows@@QEAAJXZ; Windows::Internal::Details::Git::Acquire(void)
0x18000f532  mov     [rdi+3Ch], eax
0x18000f535  lea     rax, ??_7GitPtr@Internal@Windows@@6B@; const Windows::Internal::GitPtr::`vftable'
0x18000f53c  mov     [rdi+30h], rax
0x18000f540  mov     rbx, rdi
0x18000f543  mov     [rsp+48h+arg_8], rbx
0x18000f548  test    rbx, rbx
0x18000f54b  jnz     short loc_18000F554
0x18000f54d  mov     edi, 8007000Eh
0x18000f552  jmp     short loc_18000F5D2
0x18000f554  xor     edi, edi
0x18000f556  lea     rsi, [rbx+38h]
0x18000f55a  mov     edx, [rsi]
0x18000f55c  test    edx, edx
0x18000f55e  jz      short loc_18000F57C
0x18000f560  mov     edi, [rbx+3Ch]
0x18000f563  test    edi, edi
0x18000f565  js      short loc_18000F57C
0x18000f567  mov     rcx, cs:qword_18005A068
0x18000f56e  mov     rax, [rcx]
0x18000f571  mov     rax, [rax+20h]
0x18000f575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f57a  mov     edi, eax
0x18000f57c  mov     dword ptr [rsi], 0
0x18000f582  test    edi, edi
0x18000f584  js      short loc_18000F5D2
0x18000f586  test    rbp, rbp
0x18000f589  jz      short loc_18000F5B8
0x18000f58b  mov     edi, [rbx+3Ch]
0x18000f58e  test    edi, edi
0x18000f590  js      short loc_18000F5D2
0x18000f592  mov     rcx, cs:qword_18005A068
0x18000f599  mov     rax, [rcx]
0x18000f59c  mov     r9, rsi
0x18000f59f  lea     r8, _GUID_8d898f19_2a9e_5f0f_a13e_0fb5e9ff7c76
0x18000f5a6  mov     rdx, rbp
0x18000f5a9  mov     rax, [rax+18h]
0x18000f5ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5b2  mov     edi, eax
0x18000f5b4  test    eax, eax
0x18000f5b6  js      short loc_18000F5D2
0x18000f5b8  mov     rax, [rbx]
0x18000f5bb  mov     r8, r14
0x18000f5be  lea     rdx, _GUID_8d898f19_2a9e_5f0f_a13e_0fb5e9ff7c76
0x18000f5c5  mov     rcx, rbx
0x18000f5c8  mov     rax, [rax]
0x18000f5cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5d0  mov     edi, eax
0x18000f5d2  test    rbx, rbx
0x18000f5d5  jz      short loc_18000F5E7
0x18000f5d7  mov     rcx, [rbx]
0x18000f5da  mov     rax, [rcx+10h]
0x18000f5de  mov     rcx, rbx
0x18000f5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5e6  nop
0x18000f5e7  mov     eax, edi
0x18000f5e9  mov     rbx, [rsp+48h+arg_0]
0x18000f5ee  mov     rbp, [rsp+48h+arg_10]
0x18000f5f3  add     rsp, 30h
0x18000f5f7  pop     r14
0x18000f5f9  pop     rdi
0x18000f5fa  pop     rsi
0x18000f5fb  retn
```
