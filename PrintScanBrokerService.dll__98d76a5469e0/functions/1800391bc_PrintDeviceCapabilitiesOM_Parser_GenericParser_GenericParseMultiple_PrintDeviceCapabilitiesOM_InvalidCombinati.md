# PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::InvalidCombination const>(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)

- ea: `0x1800391bc`
- end: `0x1800393f3`
- name: `??$GenericParseMultiple@$$CBVInvalidCombination@PrintDeviceCapabilitiesOM@@@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEAA?AV?$shared_ptr@V?$vector@V?$shared_ptr@$$CBVInvalidCombination@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVInvalidCombination@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z`
- size: `567`
- prototype: `_QWORD *(__int64, _QWORD *, __int64 *, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f650`

## callees

- `0x180002d70`
- `0x180038390`
- `0x180038718`
- `0x1800391bc`
- `0x18003a5f4`
- `0x18003b7a4`
- `0x18003e0e0`
- `0x18003f2dc`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x18003928d`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180039253`: `psf2:InvalidCombination`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::InvalidCombination const>(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        ...)
{
  _DWORD *v6; // rax
  int v7; // r14d
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  __int64 v10; // rax
  int i; // ebx
  __int64 v12; // rax
  __int64 v13; // rcx
  std::_Ref_count_base *v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  unsigned int v18; // [rsp+20h] [rbp-30h]
  __int64 v19; // [rsp+28h] [rbp-28h] BYREF
  _DWORD *v20; // [rsp+30h] [rbp-20h] BYREF
  void *v21; // [rsp+38h] [rbp-18h]
  void **v22; // [rsp+40h] [rbp-10h] BYREF
  std::_Ref_count_base *v23; // [rsp+48h] [rbp-8h]
  __int64 v24; // [rsp+90h] [rbp+40h] BYREF
  __int64 v25; // [rsp+98h] [rbp+48h] BYREF
  va_list va; // [rsp+98h] [rbp+48h]
  va_list va1; // [rsp+A0h] [rbp+50h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v25 = va_arg(va1, _QWORD);
  v6 = operator new(0x28u);
  v20 = v6;
  *(_OWORD *)v6 = 0;
  v6[2] = 1;
  v6[3] = 1;
  *(_QWORD *)v6 = &std::_Ref_count_obj2<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>>>::`vftable';
  *((_QWORD *)v6 + 2) = 0;
  *((_QWORD *)v6 + 3) = 0;
  *((_QWORD *)v6 + 4) = 0;
  *a2 = v6 + 4;
  a2[1] = v6;
  v7 = 3;
  v18 = 3;
  v24 = 0;
  v8 = *a3;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v8 + 288LL);
  v10 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v22, L"psf2:InvalidCombination");
  LODWORD(v9) = v9(v8, *(_QWORD *)(v10 + 8), &v24);
  v22 = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v22);
  if ( (_DWORD)v9 )
    PrintCore::ThrowIfError(
      (PrintCore *)0x80040004LL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x10F,
      3u);
  LODWORD(v25) = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 64LL))(v24, (__int64 *)va) )
    PrintCore::ThrowIfError(
      (PrintCore *)0x80040004LL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x114,
      v18);
  for ( i = 0; i < (int)v25; ++i )
  {
    v19 = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 56LL))(
           v24,
           (unsigned int)i,
           &v19) )
    {
      PrintCore::ThrowIfError(
        (PrintCore *)0x80040004LL,
        "Unspecified.",
        "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
        (const char *)0x11B,
        v18);
    }
    v20 = (_DWORD *)a1;
    v21 = operator new(0x20u);
    v12 = std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::InvalidCombination const>::_Ref_count_obj2<PrintDeviceCapabilitiesOM::InvalidCombination const>(
            (__int64)v21,
            (__int64)&v19,
            (__int64 *)&v20);
    v7 |= 4u;
    v18 = v7;
    v22 = (void **)(v12 + 16);
    v23 = (std::_Ref_count_base *)v12;
    v13 = *(_QWORD *)(*a2 + 8LL);
    if ( v13 == *(_QWORD *)(*a2 + 16LL) )
    {
      std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(
        *a2,
        *(_QWORD *)(*a2 + 8LL),
        &v22);
      v14 = v23;
    }
    else
    {
      std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(v13, &v22);
      *(_QWORD *)(v15 + 8) += 16LL;
    }
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(&v19);
  }
  v16 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return a2;
}

```

## disassembly

```asm
0x1800391bc  mov     [rsp-28h+arg_0], rbx
0x1800391c1  mov     [rsp-28h+arg_18], r9
0x1800391c6  mov     [rsp-28h+arg_8], rdx
0x1800391cb  push    rbp
0x1800391cc  push    rsi
0x1800391cd  push    rdi
0x1800391ce  push    r14
0x1800391d0  push    r15
0x1800391d2  mov     rbp, rsp
0x1800391d5  sub     rsp, 50h
0x1800391d9  mov     rdi, r8
0x1800391dc  mov     rsi, rdx
0x1800391df  mov     r15, rcx
0x1800391e2  mov     [rbp+var_30], 0
0x1800391e9  mov     ecx, 28h ; '('; Size
0x1800391ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800391f3  mov     [rbp+var_20], rax
0x1800391f7  xorps   xmm0, xmm0
0x1800391fa  movups  xmmword ptr [rax], xmm0
0x1800391fd  mov     ecx, 1
0x180039202  mov     [rax+8], ecx
0x180039205  mov     [rax+0Ch], ecx
0x180039208  lea     rcx, ??_7?$_Ref_count_obj2@V?$vector@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>>>::`vftable'
0x18003920f  mov     [rax], rcx
0x180039212  lea     rcx, [rax+10h]
0x180039216  mov     qword ptr [rcx], 0
0x18003921d  mov     qword ptr [rcx+8], 0
0x180039225  mov     qword ptr [rcx+10h], 0
0x18003922d  mov     [rsi], rcx
0x180039230  mov     [rsi+8], rax
0x180039234  mov     r14d, 3
0x18003923a  mov     [rbp+var_30], r14d
0x18003923e  mov     [rbp+arg_10], 0
0x180039246  mov     rdi, [rdi]
0x180039249  mov     rax, [rdi]
0x18003924c  mov     rbx, [rax+120h]
0x180039253  lea     rdx, aPsf2Invalidcom; "psf2:InvalidCombination"
0x18003925a  lea     rcx, [rbp+var_10]; this
0x18003925e  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x180039263  nop
0x180039264  lea     r8, [rbp+arg_10]
0x180039268  mov     rdx, [rax+8]
0x18003926c  mov     rcx, rdi
0x18003926f  mov     rax, rbx
0x180039272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039277  mov     ebx, eax
0x180039279  lea     rax, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x180039280  mov     [rbp+var_10], rax
0x180039284  lea     rcx, [rbp+var_10]; this
0x180039288  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003928d  lea     rdi, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039294  test    ebx, ebx
0x180039296  jz      short loc_1800392B2
0x180039298  mov     r9d, 10Fh; char *
0x18003929e  mov     r8, rdi; char *
0x1800392a1  lea     rdx, aUnspecified; "Unspecified."
0x1800392a8  mov     ecx, 80040004h; this
0x1800392ad  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x1800392b2  mov     dword ptr [rbp+arg_18], 0
0x1800392b9  mov     rcx, [rbp+arg_10]
0x1800392bd  mov     rax, [rcx]
0x1800392c0  lea     rdx, [rbp+arg_18]
0x1800392c4  mov     rax, [rax+40h]
0x1800392c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392cd  test    eax, eax
0x1800392cf  jz      short loc_1800392EB
0x1800392d1  mov     r9d, 114h; char *
0x1800392d7  mov     r8, rdi; char *
0x1800392da  lea     rdx, aUnspecified; "Unspecified."
0x1800392e1  mov     ecx, 80040004h; this
0x1800392e6  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x1800392eb  xor     ebx, ebx
0x1800392ed  cmp     dword ptr [rbp+arg_18], ebx
0x1800392f0  jle     loc_1800393BD
0x1800392f6  mov     [rbp+var_28], 0
0x1800392fe  mov     rcx, [rbp+arg_10]
0x180039302  mov     rax, [rcx]
0x180039305  lea     r8, [rbp+var_28]
0x180039309  mov     edx, ebx
0x18003930b  mov     rax, [rax+38h]
0x18003930f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039314  test    eax, eax
0x180039316  jz      short loc_180039332
0x180039318  mov     r9d, 11Bh; char *
0x18003931e  mov     r8, rdi; char *
0x180039321  lea     rdx, aUnspecified; "Unspecified."
0x180039328  mov     ecx, 80040004h; this
0x18003932d  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180039332  mov     [rbp+var_20], r15
0x180039336  mov     ecx, 20h ; ' '; Size
0x18003933b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039340  mov     [rbp+var_18], rax
0x180039344  lea     r8, [rbp+var_20]
0x180039348  lea     rdx, [rbp+var_28]
0x18003934c  mov     rcx, rax
0x18003934f  call    ??$?0AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@PrintDeviceCapabilitiesOM@@@?$_Ref_count_obj2@$$CBVInvalidCombination@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@$$QEAPEAVGenericParser@Parser@PrintDeviceCapabilitiesOM@@@Z; std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::InvalidCombination const>::_Ref_count_obj2<PrintDeviceCapabilitiesOM::InvalidCombination const>(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser * &&)
0x180039354  mov     r8, rax
0x180039357  or      r14d, 4
0x18003935b  mov     [rbp+var_30], r14d
0x18003935f  add     rax, 10h
0x180039363  mov     [rbp+var_10], rax
0x180039367  mov     [rbp+var_8], r8
0x18003936b  mov     r9, [rsi]
0x18003936e  mov     rcx, [r9+8]
0x180039372  cmp     rcx, [r9+10h]
0x180039376  jz      short loc_180039388
0x180039378  lea     rdx, [rbp+var_10]
0x18003937c  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x180039381  add     qword ptr [r9+8], 10h
0x180039386  jmp     short loc_18003939B
0x180039388  lea     r8, [rbp+var_10]
0x18003938c  mov     rdx, rcx
0x18003938f  mov     rcx, r9
0x180039392  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@?$vector@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> * const,std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &)
0x180039397  mov     r8, [rbp+var_8]
0x18003939b  test    r8, r8
0x18003939e  jz      short loc_1800393A9
0x1800393a0  mov     rcx, r8; this
0x1800393a3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800393a8  nop
0x1800393a9  lea     rcx, [rbp+var_28]
0x1800393ad  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x1800393b2  inc     ebx
0x1800393b4  cmp     ebx, dword ptr [rbp+arg_18]
0x1800393b7  jl      loc_1800392F6
0x1800393bd  mov     rcx, [rbp+arg_10]
0x1800393c1  test    rcx, rcx
0x1800393c4  jz      short loc_1800393DB
0x1800393c6  mov     [rbp+arg_10], 0
0x1800393ce  mov     rax, [rcx]
0x1800393d1  mov     rax, [rax+10h]
0x1800393d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393da  nop
0x1800393db  mov     rax, rsi
0x1800393de  mov     rbx, [rsp+50h+arg_0]
0x1800393e6  add     rsp, 50h
0x1800393ea  pop     r15
0x1800393ec  pop     r14
0x1800393ee  pop     rdi
0x1800393ef  pop     rsi
0x1800393f0  pop     rbp
0x1800393f1  retn
```
