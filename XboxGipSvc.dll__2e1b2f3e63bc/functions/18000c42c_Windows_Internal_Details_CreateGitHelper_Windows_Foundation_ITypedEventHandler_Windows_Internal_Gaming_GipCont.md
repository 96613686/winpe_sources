# Windows::Internal::Details::CreateGitHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>>(Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *> *,Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *> * *)

- ea: `0x18000c42c`
- end: `0x18000c59a`
- name: `??$CreateGitHelper@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@V?$GitPtrSupportsAgile@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@@Internal@3@@Details@Internal@Windows@@YAJPEAU?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@2@PEAPEAU342@@Z`
- size: `366`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e060`

## callees

- `0x1800021ac`
- `0x1800042f4`
- `0x18000c42c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18000c538`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18000c538`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Details::CreateGitHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>>(
        __int64 a1,
        _QWORD *a2)
{
  __int64 *v4; // rbx
  char *v5; // rax
  char *v6; // rdi
  _QWORD *v7; // rbx
  int AgileReference; // edi
  __int64 *v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rcx

  *a2 = 0;
  v4 = 0;
  v5 = (char *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    *(_OWORD *)v5 = 0;
    *((_OWORD *)v5 + 1) = 0;
    *((_OWORD *)v5 + 2) = 0;
    *((_QWORD *)v5 + 6) = 0;
    *(_QWORD *)v5 = &Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>::`vftable';
    v7 = v5 + 8;
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v5 + 8));
    *((_DWORD *)v6 + 11) = 1;
    *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>'};
    *((_QWORD *)v6 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v6 = &Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>,2>::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>'};
    *v7 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *((_QWORD *)v6 + 6) = 0;
    v4 = (__int64 *)v6;
  }
  if ( !v4 )
  {
    AgileReference = -2147024882;
    goto LABEL_17;
  }
  v9 = v4 + 6;
  v10 = v4[6];
  v4[6] = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = *v9;
  if ( !a1 )
  {
    *v9 = 0;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    goto LABEL_16;
  }
  if ( v11 )
  {
    *v9 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  AgileReference = RoGetAgileReference(0, &GUID_30189f26_f479_5bc9_871f_bc98ffba72c1, a1, v4 + 6);
  if ( AgileReference >= 0 )
LABEL_16:
    AgileReference = (*(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD *))*v4)(
                       v4,
                       &GUID_30189f26_f479_5bc9_871f_bc98ffba72c1,
                       a2);
LABEL_17:
  if ( v4 )
    (*(void (__fastcall **)(__int64 *))(*v4 + 16))(v4);
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x18000c42c  push    rbx
0x18000c42e  push    rsi
0x18000c42f  push    rdi
0x18000c430  push    r14
0x18000c432  sub     rsp, 28h
0x18000c436  mov     r14, rdx
0x18000c439  mov     rsi, rcx
0x18000c43c  mov     qword ptr [rdx], 0
0x18000c443  xor     ebx, ebx
0x18000c445  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c44c  lea     ecx, [rbx+38h]; unsigned __int64
0x18000c44f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c454  mov     rdi, rax
0x18000c457  test    rax, rax
0x18000c45a  jz      short loc_18000C4D9
0x18000c45c  xorps   xmm0, xmm0
0x18000c45f  xor     eax, eax
0x18000c461  movups  xmmword ptr [rdi], xmm0
0x18000c464  movups  xmmword ptr [rdi+10h], xmm0
0x18000c468  movups  xmmword ptr [rdi+20h], xmm0
0x18000c46c  mov     [rdi+30h], rax
0x18000c470  lea     rax, ??_7?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>::`vftable'
0x18000c477  mov     [rdi], rax
0x18000c47a  lea     rbx, [rdi+8]
0x18000c47e  mov     rcx, rbx; this
0x18000c481  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000c486  mov     dword ptr [rdi+2Ch], 1
0x18000c48d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>'}
0x18000c494  mov     [rdi], rax
0x18000c497  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000c49e  mov     [rbx], rax
0x18000c4a1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000c4a8  test    rcx, rcx
0x18000c4ab  jz      short loc_18000C4BA
0x18000c4ad  mov     rax, [rcx]
0x18000c4b0  mov     rax, [rax+8]
0x18000c4b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4b9  nop
0x18000c4ba  lea     rax, ??_7?$GitInvokeHelper@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@V?$GitPtrSupportsAgile@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@@Internal@3@$01@Details@Internal@Windows@@6B?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@3@@; const Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>,2>::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>'}
0x18000c4c1  mov     [rdi], rax
0x18000c4c4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000c4cb  mov     [rbx], rax
0x18000c4ce  mov     qword ptr [rdi+30h], 0
0x18000c4d6  mov     rbx, rdi
0x18000c4d9  test    rbx, rbx
0x18000c4dc  jnz     short loc_18000C4E8
0x18000c4de  mov     edi, 8007000Eh
0x18000c4e3  jmp     loc_18000C579
0x18000c4e8  lea     rdi, [rbx+30h]
0x18000c4ec  mov     rcx, [rdi]
0x18000c4ef  mov     qword ptr [rdi], 0
0x18000c4f6  test    rcx, rcx
0x18000c4f9  jz      short loc_18000C508
0x18000c4fb  mov     rax, [rcx]
0x18000c4fe  mov     rax, [rax+10h]
0x18000c502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c507  nop
0x18000c508  mov     rcx, [rdi]
0x18000c50b  test    rsi, rsi
0x18000c50e  jz      short loc_18000C546
0x18000c510  test    rcx, rcx
0x18000c513  jz      short loc_18000C529
0x18000c515  mov     qword ptr [rdi], 0
0x18000c51c  mov     rax, [rcx]
0x18000c51f  mov     rax, [rax+10h]
0x18000c523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c528  nop
0x18000c529  mov     r9, rdi
0x18000c52c  mov     r8, rsi
0x18000c52f  lea     rdx, _GUID_30189f26_f479_5bc9_871f_bc98ffba72c1
0x18000c536  xor     ecx, ecx
0x18000c538  call    cs:__imp_RoGetAgileReference
0x18000c53e  mov     edi, eax
0x18000c540  test    eax, eax
0x18000c542  jns     short loc_18000C55F
0x18000c544  jmp     short loc_18000C579
0x18000c546  mov     qword ptr [rdi], 0
0x18000c54d  test    rcx, rcx
0x18000c550  jz      short loc_18000C55F
0x18000c552  mov     rax, [rcx]
0x18000c555  mov     rax, [rax+10h]
0x18000c559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c55e  nop
0x18000c55f  mov     rax, [rbx]
0x18000c562  mov     r8, r14
0x18000c565  lea     rdx, _GUID_30189f26_f479_5bc9_871f_bc98ffba72c1
0x18000c56c  mov     rcx, rbx
0x18000c56f  mov     rax, [rax]
0x18000c572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c577  mov     edi, eax
0x18000c579  test    rbx, rbx
0x18000c57c  jz      short loc_18000C58E
0x18000c57e  mov     rcx, [rbx]
0x18000c581  mov     rax, [rcx+10h]
0x18000c585  mov     rcx, rbx
0x18000c588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c58d  nop
0x18000c58e  mov     eax, edi
0x18000c590  add     rsp, 28h
0x18000c594  pop     r14
0x18000c596  pop     rdi
0x18000c597  pop     rsi
0x18000c598  pop     rbx
0x18000c599  retn
```
