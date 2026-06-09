# PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::Feature const>(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)

- ea: `0x180038fac`
- end: `0x1800391b5`
- name: `??$GenericParseMultiple@$$CBVFeature@PrintDeviceCapabilitiesOM@@@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEAA?AV?$shared_ptr@V?$vector@V?$shared_ptr@$$CBVFeature@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVFeature@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z`
- size: `521`
- prototype: `_QWORD *(__int64, _QWORD *, __int64 *, ...)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003f5f0`

## callees

- `0x180002d70`
- `0x180038718`
- `0x180038fac`
- `0x18003a5f4`
- `0x18003af5c`
- `0x18003b7a4`
- `0x18003bcac`
- `0x18003e0e0`
- `0x18003f2dc`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x180039042`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003907f`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x1800390ca`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::Feature const>(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        ...)
{
  int v5; // r15d
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rax
  int i; // esi
  _DWORD *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rcx
  unsigned int v15; // [rsp+20h] [rbp-30h]
  _QWORD v16[2]; // [rsp+28h] [rbp-28h] BYREF
  void **v17; // [rsp+38h] [rbp-18h] BYREF
  _DWORD *v18; // [rsp+40h] [rbp-10h]
  __int64 v19; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+58h] BYREF
  va_list va; // [rsp+A8h] [rbp+58h]
  va_list va1; // [rsp+B0h] [rbp+60h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v20 = va_arg(va1, _QWORD);
  std::make_shared<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::Feature const>>,>(a2);
  v5 = 1;
  v15 = 1;
  v19 = 0;
  v6 = *a3;
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v6 + 288LL);
  v8 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v17, L"*[@psf2:psftype='Feature']");
  LODWORD(v7) = v7(v6, *(_QWORD *)(v8 + 8), &v19);
  v17 = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v17);
  if ( (_DWORD)v7 )
    PrintCore::ThrowIfError(
      (PrintCore *)0x80040004LL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x10F,
      1u);
  LODWORD(v20) = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 64LL))(v19, (__int64 *)va) )
    PrintCore::ThrowIfError(
      (PrintCore *)0x80040004LL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x114,
      v15);
  for ( i = 0; i < (int)v20; ++i )
  {
    v16[0] = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v19 + 56LL))(v19, (unsigned int)i, v16) )
      PrintCore::ThrowIfError(
        (PrintCore *)0x80040004LL,
        "Unspecified.",
        "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
        (const char *)0x11B,
        v15);
    v10 = operator new(0x50u);
    v16[1] = v10;
    *(_OWORD *)v10 = 0;
    v10[2] = 1;
    v10[3] = 1;
    *(_QWORD *)v10 = &std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::Feature const>::`vftable';
    PrintDeviceCapabilitiesOM::Feature::Feature((PrintDeviceCapabilitiesOM::Feature *)(v10 + 4));
    v5 |= 2u;
    v15 = v5;
    v17 = (void **)(v10 + 4);
    v18 = v10;
    v11 = *(_QWORD *)(*a2 + 8LL);
    if ( v11 == *(_QWORD *)(*a2 + 16LL) )
    {
      std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(
        *a2,
        *(_QWORD *)(*a2 + 8LL),
        &v17);
      v10 = v18;
    }
    else
    {
      std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(v11, &v17);
      *(_QWORD *)(v12 + 8) += 16LL;
    }
    if ( v10 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v10);
    Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(v16);
  }
  v13 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return a2;
}

```

## disassembly

```asm
0x180038fac  mov     [rsp-38h+arg_18], r9
0x180038fb1  mov     [rsp-38h+arg_8], rdx
0x180038fb6  push    rbp
0x180038fb7  push    rbx
0x180038fb8  push    rsi
0x180038fb9  push    rdi
0x180038fba  push    r12
0x180038fbc  push    r14
0x180038fbe  push    r15
0x180038fc0  mov     rbp, rsp
0x180038fc3  sub     rsp, 50h
0x180038fc7  mov     rdi, r8
0x180038fca  mov     r14, rdx
0x180038fcd  mov     r12, rcx
0x180038fd0  mov     [rbp+var_30], 0
0x180038fd7  mov     rcx, rdx
0x180038fda  call    ??$make_shared@V?$vector@V?$shared_ptr@$$CBVFeature@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVFeature@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@$$V@std@@YA?AV?$shared_ptr@V?$vector@V?$shared_ptr@$$CBVFeature@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVFeature@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@0@XZ; std::make_shared<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::Feature const>>,>(void)
0x180038fdf  mov     r15d, 1
0x180038fe5  mov     [rbp+var_30], r15d
0x180038fe9  mov     [rbp+arg_10], 0
0x180038ff1  mov     rdi, [rdi]
0x180038ff4  mov     rax, [rdi]
0x180038ff7  mov     rbx, [rax+120h]
0x180038ffe  lea     rdx, aPsf2PsftypeFea; "*[@psf2:psftype='Feature']"
0x180039005  lea     rcx, [rbp+var_18]; this
0x180039009  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x18003900e  nop
0x18003900f  lea     r8, [rbp+arg_10]
0x180039013  mov     rdx, [rax+8]
0x180039017  mov     rcx, rdi
0x18003901a  mov     rax, rbx
0x18003901d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039022  mov     ebx, eax
0x180039024  lea     rax, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x18003902b  mov     [rbp+var_18], rax
0x18003902f  lea     rcx, [rbp+var_18]; this
0x180039033  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x180039038  test    ebx, ebx
0x18003903a  jz      short loc_18003905A
0x18003903c  mov     r9d, 10Fh; char *
0x180039042  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039049  lea     rdx, aUnspecified; "Unspecified."
0x180039050  mov     ecx, 80040004h; this
0x180039055  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003905a  mov     dword ptr [rbp+arg_18], 0
0x180039061  mov     rcx, [rbp+arg_10]
0x180039065  mov     rax, [rcx]
0x180039068  lea     rdx, [rbp+arg_18]
0x18003906c  mov     rax, [rax+40h]
0x180039070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039075  test    eax, eax
0x180039077  jz      short loc_180039097
0x180039079  mov     r9d, 114h; char *
0x18003907f  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039086  lea     rdx, aUnspecified; "Unspecified."
0x18003908d  mov     ecx, 80040004h; this
0x180039092  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180039097  xor     esi, esi
0x180039099  cmp     dword ptr [rbp+arg_18], esi
0x18003909c  jle     loc_180039184
0x1800390a2  mov     [rbp+var_28], 0
0x1800390aa  mov     rcx, [rbp+arg_10]
0x1800390ae  mov     rax, [rcx]
0x1800390b1  lea     r8, [rbp+var_28]
0x1800390b5  mov     edx, esi
0x1800390b7  mov     rax, [rax+38h]
0x1800390bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390c0  test    eax, eax
0x1800390c2  jz      short loc_1800390E2
0x1800390c4  mov     r9d, 11Bh; char *
0x1800390ca  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800390d1  lea     rdx, aUnspecified; "Unspecified."
0x1800390d8  mov     ecx, 80040004h; this
0x1800390dd  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x1800390e2  mov     ecx, 50h ; 'P'; Size
0x1800390e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800390ec  mov     rdi, rax
0x1800390ef  mov     [rbp+var_20], rax
0x1800390f3  xorps   xmm0, xmm0
0x1800390f6  movups  xmmword ptr [rax], xmm0
0x1800390f9  mov     eax, 1
0x1800390fe  mov     [rdi+8], eax
0x180039101  mov     [rdi+0Ch], eax
0x180039104  lea     rax, ??_7?$_Ref_count_obj2@$$CBVFeature@PrintDeviceCapabilitiesOM@@@std@@6B@; const std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::Feature const>::`vftable'
0x18003910b  mov     [rdi], rax
0x18003910e  lea     rbx, [rdi+10h]
0x180039112  mov     r8, r12
0x180039115  lea     rdx, [rbp+var_28]
0x180039119  mov     rcx, rbx; this
0x18003911c  call    ??0Feature@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z; PrintDeviceCapabilitiesOM::Feature::Feature(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)
0x180039121  nop
0x180039122  or      r15d, 2
0x180039126  mov     [rbp+var_30], r15d
0x18003912a  mov     [rbp+var_18], rbx
0x18003912e  mov     [rbp+var_10], rdi
0x180039132  mov     r9, [r14]
0x180039135  mov     rcx, [r9+8]
0x180039139  cmp     rcx, [r9+10h]
0x18003913d  jz      short loc_18003914F
0x18003913f  lea     rdx, [rbp+var_18]
0x180039143  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x180039148  add     qword ptr [r9+8], 10h
0x18003914d  jmp     short loc_180039162
0x18003914f  lea     r8, [rbp+var_18]
0x180039153  mov     rdx, rcx
0x180039156  mov     rcx, r9
0x180039159  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@?$vector@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> * const,std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &)
0x18003915e  mov     rdi, [rbp+var_10]
0x180039162  test    rdi, rdi
0x180039165  jz      short loc_180039170
0x180039167  mov     rcx, rdi; this
0x18003916a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003916f  nop
0x180039170  lea     rcx, [rbp+var_28]
0x180039174  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x180039179  inc     esi
0x18003917b  cmp     esi, dword ptr [rbp+arg_18]
0x18003917e  jl      loc_1800390A2
0x180039184  mov     rcx, [rbp+arg_10]
0x180039188  test    rcx, rcx
0x18003918b  jz      short loc_1800391A2
0x18003918d  mov     [rbp+arg_10], 0
0x180039195  mov     rax, [rcx]
0x180039198  mov     rax, [rax+10h]
0x18003919c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391a1  nop
0x1800391a2  mov     rax, r14
0x1800391a5  add     rsp, 50h
0x1800391a9  pop     r15
0x1800391ab  pop     r14
0x1800391ad  pop     r12
0x1800391af  pop     rdi
0x1800391b0  pop     rsi
0x1800391b1  pop     rbx
0x1800391b2  pop     rbp
0x1800391b3  retn
```
