# PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::Property const>(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)

- ea: `0x1800398a4`
- end: `0x180039af0`
- name: `??$GenericParseMultiple@$$CBVProperty@PrintDeviceCapabilitiesOM@@@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEAA?AV?$shared_ptr@V?$vector@V?$shared_ptr@$$CBVProperty@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVProperty@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z`
- size: `588`
- prototype: `_QWORD *(__int64, _QWORD *, __int64 *, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f720`

## callees

- `0x180002d70`
- `0x180038718`
- `0x1800398a4`
- `0x18003a5f4`
- `0x18003b7a4`
- `0x18003ca0c`
- `0x18003e0e0`
- `0x18003f2dc`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x18003997d`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x1800399ba`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180039a05`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::Property const>(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        ...)
{
  _DWORD *v6; // rax
  int v7; // r15d
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  __int64 v10; // rax
  int i; // esi
  void **v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rcx
  unsigned int v17; // [rsp+20h] [rbp-30h]
  _QWORD v18[2]; // [rsp+28h] [rbp-28h] BYREF
  void **v19; // [rsp+38h] [rbp-18h] BYREF
  void **v20; // [rsp+40h] [rbp-10h]
  __int64 v21; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v22; // [rsp+A8h] [rbp+58h] BYREF
  va_list va; // [rsp+A8h] [rbp+58h]
  va_list va1; // [rsp+B0h] [rbp+60h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v22 = va_arg(va1, _QWORD);
  v6 = operator new(0x28u);
  v18[0] = v6;
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
  v17 = 3;
  v21 = 0;
  v8 = *a3;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v8 + 288LL);
  v10 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v19, L"*[@psf2:psftype='Property']");
  LODWORD(v9) = v9(v8, *(_QWORD *)(v10 + 8), &v21);
  v19 = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v19);
  if ( (_DWORD)v9 )
    PrintCore::ThrowIfError(
      (PrintCore *)0x80040004LL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x10F,
      3u);
  LODWORD(v22) = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 64LL))(v21, (__int64 *)va) )
    PrintCore::ThrowIfError(
      (PrintCore *)0x80040004LL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x114,
      v17);
  for ( i = 0; i < (int)v22; ++i )
  {
    v18[0] = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v21 + 56LL))(v21, (unsigned int)i, v18) )
      PrintCore::ThrowIfError(
        (PrintCore *)0x80040004LL,
        "Unspecified.",
        "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
        (const char *)0x11B,
        v17);
    v12 = (void **)operator new(0x40u);
    v18[1] = v12;
    *(_OWORD *)v12 = 0;
    *((_DWORD *)v12 + 2) = 1;
    *((_DWORD *)v12 + 3) = 1;
    *v12 = &std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::Property const>::`vftable';
    PrintDeviceCapabilitiesOM::Property::Property(v12 + 2, v18, a1);
    v7 |= 4u;
    v17 = v7;
    v19 = v12 + 2;
    v20 = v12;
    v13 = *(_QWORD *)(*a2 + 8LL);
    if ( v13 == *(_QWORD *)(*a2 + 16LL) )
    {
      std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(
        *a2,
        *(_QWORD *)(*a2 + 8LL),
        &v19);
      v12 = v20;
    }
    else
    {
      std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(v13, &v19);
      *(_QWORD *)(v14 + 8) += 16LL;
    }
    if ( v12 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
    Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(v18);
  }
  v15 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return a2;
}

```

## disassembly

```asm
0x1800398a4  mov     [rsp-38h+arg_18], r9
0x1800398a9  mov     [rsp-38h+arg_8], rdx
0x1800398ae  push    rbp
0x1800398af  push    rbx
0x1800398b0  push    rsi
0x1800398b1  push    rdi
0x1800398b2  push    r12
0x1800398b4  push    r14
0x1800398b6  push    r15
0x1800398b8  mov     rbp, rsp
0x1800398bb  sub     rsp, 50h
0x1800398bf  mov     rdi, r8
0x1800398c2  mov     r14, rdx
0x1800398c5  mov     r12, rcx
0x1800398c8  mov     [rbp+var_30], 0
0x1800398cf  mov     ecx, 28h ; '('; Size
0x1800398d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800398d9  mov     [rbp+var_28], rax
0x1800398dd  xorps   xmm0, xmm0
0x1800398e0  movups  xmmword ptr [rax], xmm0
0x1800398e3  mov     ecx, 1
0x1800398e8  mov     [rax+8], ecx
0x1800398eb  mov     [rax+0Ch], ecx
0x1800398ee  lea     rcx, ??_7?$_Ref_count_obj2@V?$vector@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>>>::`vftable'
0x1800398f5  mov     [rax], rcx
0x1800398f8  lea     rcx, [rax+10h]
0x1800398fc  mov     qword ptr [rcx], 0
0x180039903  mov     qword ptr [rcx+8], 0
0x18003990b  mov     qword ptr [rcx+10h], 0
0x180039913  mov     [r14], rcx
0x180039916  mov     [r14+8], rax
0x18003991a  mov     r15d, 3
0x180039920  mov     [rbp+var_30], r15d
0x180039924  mov     [rbp+arg_10], 0
0x18003992c  mov     rdi, [rdi]
0x18003992f  mov     rax, [rdi]
0x180039932  mov     rbx, [rax+120h]
0x180039939  lea     rdx, aPsf2PsftypePro; "*[@psf2:psftype='Property']"
0x180039940  lea     rcx, [rbp+var_18]; this
0x180039944  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x180039949  nop
0x18003994a  lea     r8, [rbp+arg_10]
0x18003994e  mov     rdx, [rax+8]
0x180039952  mov     rcx, rdi
0x180039955  mov     rax, rbx
0x180039958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003995d  mov     ebx, eax
0x18003995f  lea     rax, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x180039966  mov     [rbp+var_18], rax
0x18003996a  lea     rcx, [rbp+var_18]; this
0x18003996e  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x180039973  test    ebx, ebx
0x180039975  jz      short loc_180039995
0x180039977  mov     r9d, 10Fh; char *
0x18003997d  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039984  lea     rdx, aUnspecified; "Unspecified."
0x18003998b  mov     ecx, 80040004h; this
0x180039990  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180039995  mov     dword ptr [rbp+arg_18], 0
0x18003999c  mov     rcx, [rbp+arg_10]
0x1800399a0  mov     rax, [rcx]
0x1800399a3  lea     rdx, [rbp+arg_18]
0x1800399a7  mov     rax, [rax+40h]
0x1800399ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399b0  test    eax, eax
0x1800399b2  jz      short loc_1800399D2
0x1800399b4  mov     r9d, 114h; char *
0x1800399ba  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800399c1  lea     rdx, aUnspecified; "Unspecified."
0x1800399c8  mov     ecx, 80040004h; this
0x1800399cd  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x1800399d2  xor     esi, esi
0x1800399d4  cmp     dword ptr [rbp+arg_18], esi
0x1800399d7  jle     loc_180039ABF
0x1800399dd  mov     [rbp+var_28], 0
0x1800399e5  mov     rcx, [rbp+arg_10]
0x1800399e9  mov     rax, [rcx]
0x1800399ec  lea     r8, [rbp+var_28]
0x1800399f0  mov     edx, esi
0x1800399f2  mov     rax, [rax+38h]
0x1800399f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399fb  test    eax, eax
0x1800399fd  jz      short loc_180039A1D
0x1800399ff  mov     r9d, 11Bh; char *
0x180039a05  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039a0c  lea     rdx, aUnspecified; "Unspecified."
0x180039a13  mov     ecx, 80040004h; this
0x180039a18  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180039a1d  mov     ecx, 40h ; '@'; Size
0x180039a22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039a27  mov     rdi, rax
0x180039a2a  mov     [rbp+var_20], rax
0x180039a2e  xorps   xmm0, xmm0
0x180039a31  movups  xmmword ptr [rax], xmm0
0x180039a34  mov     eax, 1
0x180039a39  mov     [rdi+8], eax
0x180039a3c  mov     [rdi+0Ch], eax
0x180039a3f  lea     rax, ??_7?$_Ref_count_obj2@$$CBVProperty@PrintDeviceCapabilitiesOM@@@std@@6B@; const std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::Property const>::`vftable'
0x180039a46  mov     [rdi], rax
0x180039a49  lea     rbx, [rdi+10h]
0x180039a4d  mov     r8, r12
0x180039a50  lea     rdx, [rbp+var_28]
0x180039a54  mov     rcx, rbx
0x180039a57  call    ??0Property@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z; PrintDeviceCapabilitiesOM::Property::Property(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)
0x180039a5c  nop
0x180039a5d  or      r15d, 4
0x180039a61  mov     [rbp+var_30], r15d
0x180039a65  mov     [rbp+var_18], rbx
0x180039a69  mov     [rbp+var_10], rdi
0x180039a6d  mov     r9, [r14]
0x180039a70  mov     rcx, [r9+8]
0x180039a74  cmp     rcx, [r9+10h]
0x180039a78  jz      short loc_180039A8A
0x180039a7a  lea     rdx, [rbp+var_18]
0x180039a7e  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x180039a83  add     qword ptr [r9+8], 10h
0x180039a88  jmp     short loc_180039A9D
0x180039a8a  lea     r8, [rbp+var_18]
0x180039a8e  mov     rdx, rcx
0x180039a91  mov     rcx, r9
0x180039a94  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@?$vector@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> * const,std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &)
0x180039a99  mov     rdi, [rbp+var_10]
0x180039a9d  test    rdi, rdi
0x180039aa0  jz      short loc_180039AAB
0x180039aa2  mov     rcx, rdi; this
0x180039aa5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039aaa  nop
0x180039aab  lea     rcx, [rbp+var_28]
0x180039aaf  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x180039ab4  inc     esi
0x180039ab6  cmp     esi, dword ptr [rbp+arg_18]
0x180039ab9  jl      loc_1800399DD
0x180039abf  mov     rcx, [rbp+arg_10]
0x180039ac3  test    rcx, rcx
0x180039ac6  jz      short loc_180039ADD
0x180039ac8  mov     [rbp+arg_10], 0
0x180039ad0  mov     rax, [rcx]
0x180039ad3  mov     rax, [rax+10h]
0x180039ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039adc  nop
0x180039add  mov     rax, r14
0x180039ae0  add     rsp, 50h
0x180039ae4  pop     r15
0x180039ae6  pop     r14
0x180039ae8  pop     r12
0x180039aea  pop     rdi
0x180039aeb  pop     rsi
0x180039aec  pop     rbx
0x180039aed  pop     rbp
0x180039aee  retn
```
