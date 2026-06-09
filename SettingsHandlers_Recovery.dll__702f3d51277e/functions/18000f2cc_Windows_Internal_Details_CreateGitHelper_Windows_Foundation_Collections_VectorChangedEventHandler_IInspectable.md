# Windows::Internal::Details::CreateGitHelper<Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>,Windows::Internal::GitPtr>(Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *> *,Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *> * *)

- ea: `0x18000f2cc`
- end: `0x18000f460`
- name: `??$CreateGitHelper@U?$VectorChangedEventHandler@PEAUIInspectable@@@Collections@Foundation@Windows@@VGitPtr@Internal@4@@Details@Internal@Windows@@YAJPEAU?$VectorChangedEventHandler@PEAUIInspectable@@@Collections@Foundation@2@PEAPEAU3452@@Z`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022510`

## callees

- `0x180002380`
- `0x180002ed4`
- `0x18000f2cc`
- `0x180011744`
- `0x1800132ac`
- `0x18002b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Details::CreateGitHelper<Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>,Windows::Internal::GitPtr>(
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
    *(_QWORD *)v6 = &Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v6 + 2));
    v6[11] = 1;
    *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>'};
    *((_QWORD *)v6 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v7 = Microsoft::WRL::Details::ModuleBase::module_;
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v6 = &Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>,Windows::Internal::GitPtr,2>::`vftable'{for `Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>'};
    *((_QWORD *)v6 + 1) = &Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>,Windows::Internal::GitPtr,2>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
                   &GUID_b423a801_d35e_56b9_813b_00889536cb98,
                   v4 + 14),
            v8 >= 0) )
      {
        v8 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, _QWORD *))v4)(
               v4,
               &GUID_b423a801_d35e_56b9_813b_00889536cb98,
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
0x18000f2cc  mov     [rsp+arg_0], rbx
0x18000f2d1  mov     [rsp+arg_10], rbp
0x18000f2d6  push    rsi
0x18000f2d7  push    rdi
0x18000f2d8  push    r14
0x18000f2da  sub     rsp, 30h
0x18000f2de  mov     r14, rdx
0x18000f2e1  mov     rbp, rcx
0x18000f2e4  mov     qword ptr [rdx], 0
0x18000f2eb  mov     [rsp+48h+arg_8], 0
0x18000f2f4  xor     ebx, ebx
0x18000f2f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f2fd  lea     esi, [rbx+40h]
0x18000f300  mov     ecx, esi; unsigned __int64
0x18000f302  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f307  mov     rdi, rax
0x18000f30a  test    rax, rax
0x18000f30d  jz      loc_18000F3A7
0x18000f313  mov     r8d, esi; Size
0x18000f316  xor     edx, edx; Val
0x18000f318  mov     rcx, rax; void *
0x18000f31b  call    memset_0
0x18000f320  nop
0x18000f321  lea     rax, ??_7?$VectorChangedEventHandler@PEAUIInspectable@@@Collections@Foundation@Windows@@6B@; const Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>::`vftable'
0x18000f328  mov     [rdi], rax
0x18000f32b  lea     rbx, [rdi+8]
0x18000f32f  mov     rcx, rbx; this
0x18000f332  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000f337  mov     dword ptr [rdi+2Ch], 1
0x18000f33e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$VectorChangedEventHandler@PEAUIInspectable@@@Collections@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$VectorChangedEventHandler@PEAUIInspectable@@@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>'}
0x18000f345  mov     [rdi], rax
0x18000f348  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$VectorChangedEventHandler@PEAUIInspectable@@@Collections@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000f34f  mov     [rbx], rax
0x18000f352  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000f359  test    rcx, rcx
0x18000f35c  jz      short loc_18000F36B
0x18000f35e  mov     rax, [rcx]
0x18000f361  mov     rax, [rax+8]
0x18000f365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f36a  nop
0x18000f36b  lea     rax, ??_7?$GitInvokeHelper@U?$VectorChangedEventHandler@PEAUIInspectable@@@Collections@Foundation@Windows@@VGitPtr@Internal@4@$01@Details@Internal@Windows@@6B?$VectorChangedEventHandler@PEAUIInspectable@@@Collections@Foundation@3@@; const Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>,Windows::Internal::GitPtr,2>::`vftable'{for `Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>'}
0x18000f372  mov     [rdi], rax
0x18000f375  lea     rax, ??_7?$GitInvokeHelper@U?$VectorChangedEventHandler@PEAUIInspectable@@@Collections@Foundation@Windows@@VGitPtr@Internal@4@$01@Details@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@1WRL@Microsoft@@@; const Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<IInspectable *>,Windows::Internal::GitPtr,2>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000f37c  mov     [rbx], rax
0x18000f37f  lea     rax, ??_7?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable'
0x18000f386  mov     [rdi+30h], rax
0x18000f38a  mov     dword ptr [rdi+38h], 0
0x18000f391  call    ?Acquire@Git@Details@Internal@Windows@@QEAAJXZ; Windows::Internal::Details::Git::Acquire(void)
0x18000f396  mov     [rdi+3Ch], eax
0x18000f399  lea     rax, ??_7GitPtr@Internal@Windows@@6B@; const Windows::Internal::GitPtr::`vftable'
0x18000f3a0  mov     [rdi+30h], rax
0x18000f3a4  mov     rbx, rdi
0x18000f3a7  mov     [rsp+48h+arg_8], rbx
0x18000f3ac  test    rbx, rbx
0x18000f3af  jnz     short loc_18000F3B8
0x18000f3b1  mov     edi, 8007000Eh
0x18000f3b6  jmp     short loc_18000F436
0x18000f3b8  xor     edi, edi
0x18000f3ba  lea     rsi, [rbx+38h]
0x18000f3be  mov     edx, [rsi]
0x18000f3c0  test    edx, edx
0x18000f3c2  jz      short loc_18000F3E0
0x18000f3c4  mov     edi, [rbx+3Ch]
0x18000f3c7  test    edi, edi
0x18000f3c9  js      short loc_18000F3E0
0x18000f3cb  mov     rcx, cs:qword_18005A068
0x18000f3d2  mov     rax, [rcx]
0x18000f3d5  mov     rax, [rax+20h]
0x18000f3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3de  mov     edi, eax
0x18000f3e0  mov     dword ptr [rsi], 0
0x18000f3e6  test    edi, edi
0x18000f3e8  js      short loc_18000F436
0x18000f3ea  test    rbp, rbp
0x18000f3ed  jz      short loc_18000F41C
0x18000f3ef  mov     edi, [rbx+3Ch]
0x18000f3f2  test    edi, edi
0x18000f3f4  js      short loc_18000F436
0x18000f3f6  mov     rcx, cs:qword_18005A068
0x18000f3fd  mov     rax, [rcx]
0x18000f400  mov     r9, rsi
0x18000f403  lea     r8, _GUID_b423a801_d35e_56b9_813b_00889536cb98
0x18000f40a  mov     rdx, rbp
0x18000f40d  mov     rax, [rax+18h]
0x18000f411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f416  mov     edi, eax
0x18000f418  test    eax, eax
0x18000f41a  js      short loc_18000F436
0x18000f41c  mov     rax, [rbx]
0x18000f41f  mov     r8, r14
0x18000f422  lea     rdx, _GUID_b423a801_d35e_56b9_813b_00889536cb98
0x18000f429  mov     rcx, rbx
0x18000f42c  mov     rax, [rax]
0x18000f42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f434  mov     edi, eax
0x18000f436  test    rbx, rbx
0x18000f439  jz      short loc_18000F44B
0x18000f43b  mov     rcx, [rbx]
0x18000f43e  mov     rax, [rcx+10h]
0x18000f442  mov     rcx, rbx
0x18000f445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f44a  nop
0x18000f44b  mov     eax, edi
0x18000f44d  mov     rbx, [rsp+48h+arg_0]
0x18000f452  mov     rbp, [rsp+48h+arg_10]
0x18000f457  add     rsp, 30h
0x18000f45b  pop     r14
0x18000f45d  pop     rdi
0x18000f45e  pop     rsi
0x18000f45f  retn
```
