# PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::ParameterDef const>(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)

- ea: `0x180039650`
- end: `0x18003989c`
- name: `??$GenericParseMultiple@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEAA?AV?$shared_ptr@V?$vector@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z`
- size: `588`
- prototype: `_QWORD *(__int64, _QWORD *, __int64 *, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f690`

## callees

- `0x180002d70`
- `0x180038718`
- `0x180039650`
- `0x18003a5f4`
- `0x18003b7a4`
- `0x18003c428`
- `0x18003e0e0`
- `0x18003f2dc`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x180039729`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180039766`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x1800397b1`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::ParameterDef const>(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        ...)
{
  _DWORD *v5; // rax
  int v6; // r15d
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rbx
  __int64 v9; // rax
  int i; // esi
  _DWORD *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // rcx
  unsigned int v16; // [rsp+20h] [rbp-30h]
  _QWORD v17[2]; // [rsp+28h] [rbp-28h] BYREF
  void **v18; // [rsp+38h] [rbp-18h] BYREF
  _DWORD *v19; // [rsp+40h] [rbp-10h]
  __int64 v20; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v21; // [rsp+A8h] [rbp+58h] BYREF
  va_list va; // [rsp+A8h] [rbp+58h]
  va_list va1; // [rsp+B0h] [rbp+60h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v21 = va_arg(va1, _QWORD);
  v5 = operator new(0x28u);
  v17[0] = v5;
  *(_OWORD *)v5 = 0;
  v5[2] = 1;
  v5[3] = 1;
  *(_QWORD *)v5 = &std::_Ref_count_obj2<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>>>::`vftable';
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 4) = 0;
  *a2 = v5 + 4;
  a2[1] = v5;
  v6 = 3;
  v16 = 3;
  v20 = 0;
  v7 = *a3;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v7 + 288LL);
  v9 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v18, L"*[@psf2:psftype='ParameterDef']");
  LODWORD(v8) = v8(v7, *(_QWORD *)(v9 + 8), &v20);
  v18 = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v18);
  if ( (_DWORD)v8 )
    PrintCore::ThrowIfError(
      (PrintCore *)0x80040004LL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x10F,
      3u);
  LODWORD(v21) = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 64LL))(v20, (__int64 *)va) )
    PrintCore::ThrowIfError(
      (PrintCore *)0x80040004LL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x114,
      v16);
  for ( i = 0; i < (int)v21; ++i )
  {
    v17[0] = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v20 + 56LL))(v20, (unsigned int)i, v17) )
      PrintCore::ThrowIfError(
        (PrintCore *)0x80040004LL,
        "Unspecified.",
        "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
        (const char *)0x11B,
        v16);
    v11 = operator new(0x78u);
    v17[1] = v11;
    *(_OWORD *)v11 = 0;
    v11[2] = 1;
    v11[3] = 1;
    *(_QWORD *)v11 = &std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::ParameterDef const>::`vftable';
    PrintDeviceCapabilitiesOM::ParameterDef::ParameterDef((PrintDeviceCapabilitiesOM::ParameterDef *)(v11 + 4));
    v6 |= 4u;
    v16 = v6;
    v18 = (void **)(v11 + 4);
    v19 = v11;
    v12 = *(_QWORD *)(*a2 + 8LL);
    if ( v12 == *(_QWORD *)(*a2 + 16LL) )
    {
      std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(
        *a2,
        *(_QWORD *)(*a2 + 8LL),
        &v18);
      v11 = v19;
    }
    else
    {
      std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(v12, &v18);
      *(_QWORD *)(v13 + 8) += 16LL;
    }
    if ( v11 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v11);
    Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(v17);
  }
  v14 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return a2;
}

```

## disassembly

```asm
0x180039650  mov     [rsp-38h+arg_18], r9
0x180039655  mov     [rsp-38h+arg_8], rdx
0x18003965a  push    rbp
0x18003965b  push    rbx
0x18003965c  push    rsi
0x18003965d  push    rdi
0x18003965e  push    r12
0x180039660  push    r14
0x180039662  push    r15
0x180039664  mov     rbp, rsp
0x180039667  sub     rsp, 50h
0x18003966b  mov     rdi, r8
0x18003966e  mov     r14, rdx
0x180039671  mov     r12, rcx
0x180039674  mov     [rbp+var_30], 0
0x18003967b  mov     ecx, 28h ; '('; Size
0x180039680  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039685  mov     [rbp+var_28], rax
0x180039689  xorps   xmm0, xmm0
0x18003968c  movups  xmmword ptr [rax], xmm0
0x18003968f  mov     ecx, 1
0x180039694  mov     [rax+8], ecx
0x180039697  mov     [rax+0Ch], ecx
0x18003969a  lea     rcx, ??_7?$_Ref_count_obj2@V?$vector@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>>>::`vftable'
0x1800396a1  mov     [rax], rcx
0x1800396a4  lea     rcx, [rax+10h]
0x1800396a8  mov     qword ptr [rcx], 0
0x1800396af  mov     qword ptr [rcx+8], 0
0x1800396b7  mov     qword ptr [rcx+10h], 0
0x1800396bf  mov     [r14], rcx
0x1800396c2  mov     [r14+8], rax
0x1800396c6  mov     r15d, 3
0x1800396cc  mov     [rbp+var_30], r15d
0x1800396d0  mov     [rbp+arg_10], 0
0x1800396d8  mov     rdi, [rdi]
0x1800396db  mov     rax, [rdi]
0x1800396de  mov     rbx, [rax+120h]
0x1800396e5  lea     rdx, aPsf2PsftypePar; "*[@psf2:psftype='ParameterDef']"
0x1800396ec  lea     rcx, [rbp+var_18]; this
0x1800396f0  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x1800396f5  nop
0x1800396f6  lea     r8, [rbp+arg_10]
0x1800396fa  mov     rdx, [rax+8]
0x1800396fe  mov     rcx, rdi
0x180039701  mov     rax, rbx
0x180039704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039709  mov     ebx, eax
0x18003970b  lea     rax, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x180039712  mov     [rbp+var_18], rax
0x180039716  lea     rcx, [rbp+var_18]; this
0x18003971a  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003971f  test    ebx, ebx
0x180039721  jz      short loc_180039741
0x180039723  mov     r9d, 10Fh; char *
0x180039729  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039730  lea     rdx, aUnspecified; "Unspecified."
0x180039737  mov     ecx, 80040004h; this
0x18003973c  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180039741  mov     dword ptr [rbp+arg_18], 0
0x180039748  mov     rcx, [rbp+arg_10]
0x18003974c  mov     rax, [rcx]
0x18003974f  lea     rdx, [rbp+arg_18]
0x180039753  mov     rax, [rax+40h]
0x180039757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003975c  test    eax, eax
0x18003975e  jz      short loc_18003977E
0x180039760  mov     r9d, 114h; char *
0x180039766  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003976d  lea     rdx, aUnspecified; "Unspecified."
0x180039774  mov     ecx, 80040004h; this
0x180039779  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003977e  xor     esi, esi
0x180039780  cmp     dword ptr [rbp+arg_18], esi
0x180039783  jle     loc_18003986B
0x180039789  mov     [rbp+var_28], 0
0x180039791  mov     rcx, [rbp+arg_10]
0x180039795  mov     rax, [rcx]
0x180039798  lea     r8, [rbp+var_28]
0x18003979c  mov     edx, esi
0x18003979e  mov     rax, [rax+38h]
0x1800397a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397a7  test    eax, eax
0x1800397a9  jz      short loc_1800397C9
0x1800397ab  mov     r9d, 11Bh; char *
0x1800397b1  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800397b8  lea     rdx, aUnspecified; "Unspecified."
0x1800397bf  mov     ecx, 80040004h; this
0x1800397c4  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x1800397c9  mov     ecx, 78h ; 'x'; Size
0x1800397ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800397d3  mov     rdi, rax
0x1800397d6  mov     [rbp+var_20], rax
0x1800397da  xorps   xmm0, xmm0
0x1800397dd  movups  xmmword ptr [rax], xmm0
0x1800397e0  mov     eax, 1
0x1800397e5  mov     [rdi+8], eax
0x1800397e8  mov     [rdi+0Ch], eax
0x1800397eb  lea     rax, ??_7?$_Ref_count_obj2@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@6B@; const std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::ParameterDef const>::`vftable'
0x1800397f2  mov     [rdi], rax
0x1800397f5  lea     rbx, [rdi+10h]
0x1800397f9  mov     r8, r12
0x1800397fc  lea     rdx, [rbp+var_28]
0x180039800  mov     rcx, rbx; this
0x180039803  call    ??0ParameterDef@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z; PrintDeviceCapabilitiesOM::ParameterDef::ParameterDef(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)
0x180039808  nop
0x180039809  or      r15d, 4
0x18003980d  mov     [rbp+var_30], r15d
0x180039811  mov     [rbp+var_18], rbx
0x180039815  mov     [rbp+var_10], rdi
0x180039819  mov     r9, [r14]
0x18003981c  mov     rcx, [r9+8]
0x180039820  cmp     rcx, [r9+10h]
0x180039824  jz      short loc_180039836
0x180039826  lea     rdx, [rbp+var_18]
0x18003982a  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003982f  add     qword ptr [r9+8], 10h
0x180039834  jmp     short loc_180039849
0x180039836  lea     r8, [rbp+var_18]
0x18003983a  mov     rdx, rcx
0x18003983d  mov     rcx, r9
0x180039840  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@?$vector@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> * const,std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &)
0x180039845  mov     rdi, [rbp+var_10]
0x180039849  test    rdi, rdi
0x18003984c  jz      short loc_180039857
0x18003984e  mov     rcx, rdi; this
0x180039851  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039856  nop
0x180039857  lea     rcx, [rbp+var_28]
0x18003985b  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x180039860  inc     esi
0x180039862  cmp     esi, dword ptr [rbp+arg_18]
0x180039865  jl      loc_180039789
0x18003986b  mov     rcx, [rbp+arg_10]
0x18003986f  test    rcx, rcx
0x180039872  jz      short loc_180039889
0x180039874  mov     [rbp+arg_10], 0
0x18003987c  mov     rax, [rcx]
0x18003987f  mov     rax, [rax+10h]
0x180039883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039888  nop
0x180039889  mov     rax, r14
0x18003988c  add     rsp, 50h
0x180039890  pop     r15
0x180039892  pop     r14
0x180039894  pop     r12
0x180039896  pop     rdi
0x180039897  pop     rsi
0x180039898  pop     rbx
0x180039899  pop     rbp
0x18003989a  retn
```
