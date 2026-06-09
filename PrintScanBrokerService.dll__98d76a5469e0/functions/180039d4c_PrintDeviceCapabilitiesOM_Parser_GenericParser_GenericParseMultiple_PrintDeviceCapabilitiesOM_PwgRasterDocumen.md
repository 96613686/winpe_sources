# PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::PwgRasterDocumentType const>(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)

- ea: `0x180039d4c`
- end: `0x180039f98`
- name: `??$GenericParseMultiple@$$CBVPwgRasterDocumentType@PrintDeviceCapabilitiesOM@@@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEAA?AV?$shared_ptr@V?$vector@V?$shared_ptr@$$CBVPwgRasterDocumentType@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVPwgRasterDocumentType@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z`
- size: `588`
- prototype: `_QWORD *(__int64, _QWORD *, __int64 *, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f740`

## callees

- `0x180002d70`
- `0x180038718`
- `0x180039d4c`
- `0x18003a5f4`
- `0x18003b7a4`
- `0x18003cc3c`
- `0x18003e0e0`
- `0x18003f2dc`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x180039e25`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180039e62`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180039ead`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::PwgRasterDocumentType const>(
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
  v10 = PrintCore::BStrRAII::BStrRAII(
          (PrintCore::BStrRAII *)&v19,
          L"psf2:PwgRasterDocumentTypesSupported/psf2:PwgRasterDocumentType");
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
    v12 = (void **)operator new(0x30u);
    v18[1] = v12;
    *(_OWORD *)v12 = 0;
    *((_DWORD *)v12 + 2) = 1;
    *((_DWORD *)v12 + 3) = 1;
    *v12 = &std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::InvalidCombinationEntry const>::`vftable';
    PrintDeviceCapabilitiesOM::PwgRasterDocumentType::PwgRasterDocumentType(v12 + 2, v18, a1);
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
0x180039d4c  mov     [rsp-38h+arg_18], r9
0x180039d51  mov     [rsp-38h+arg_8], rdx
0x180039d56  push    rbp
0x180039d57  push    rbx
0x180039d58  push    rsi
0x180039d59  push    rdi
0x180039d5a  push    r12
0x180039d5c  push    r14
0x180039d5e  push    r15
0x180039d60  mov     rbp, rsp
0x180039d63  sub     rsp, 50h
0x180039d67  mov     rdi, r8
0x180039d6a  mov     r14, rdx
0x180039d6d  mov     r12, rcx
0x180039d70  mov     [rbp+var_30], 0
0x180039d77  mov     ecx, 28h ; '('; Size
0x180039d7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039d81  mov     [rbp+var_28], rax
0x180039d85  xorps   xmm0, xmm0
0x180039d88  movups  xmmword ptr [rax], xmm0
0x180039d8b  mov     ecx, 1
0x180039d90  mov     [rax+8], ecx
0x180039d93  mov     [rax+0Ch], ecx
0x180039d96  lea     rcx, ??_7?$_Ref_count_obj2@V?$vector@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>>>::`vftable'
0x180039d9d  mov     [rax], rcx
0x180039da0  lea     rcx, [rax+10h]
0x180039da4  mov     qword ptr [rcx], 0
0x180039dab  mov     qword ptr [rcx+8], 0
0x180039db3  mov     qword ptr [rcx+10h], 0
0x180039dbb  mov     [r14], rcx
0x180039dbe  mov     [r14+8], rax
0x180039dc2  mov     r15d, 3
0x180039dc8  mov     [rbp+var_30], r15d
0x180039dcc  mov     [rbp+arg_10], 0
0x180039dd4  mov     rdi, [rdi]
0x180039dd7  mov     rax, [rdi]
0x180039dda  mov     rbx, [rax+120h]
0x180039de1  lea     rdx, aPsf2Pwgrasterd; "psf2:PwgRasterDocumentTypesSupported/ps"...
0x180039de8  lea     rcx, [rbp+var_18]; this
0x180039dec  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x180039df1  nop
0x180039df2  lea     r8, [rbp+arg_10]
0x180039df6  mov     rdx, [rax+8]
0x180039dfa  mov     rcx, rdi
0x180039dfd  mov     rax, rbx
0x180039e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e05  mov     ebx, eax
0x180039e07  lea     rax, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x180039e0e  mov     [rbp+var_18], rax
0x180039e12  lea     rcx, [rbp+var_18]; this
0x180039e16  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x180039e1b  test    ebx, ebx
0x180039e1d  jz      short loc_180039E3D
0x180039e1f  mov     r9d, 10Fh; char *
0x180039e25  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039e2c  lea     rdx, aUnspecified; "Unspecified."
0x180039e33  mov     ecx, 80040004h; this
0x180039e38  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180039e3d  mov     dword ptr [rbp+arg_18], 0
0x180039e44  mov     rcx, [rbp+arg_10]
0x180039e48  mov     rax, [rcx]
0x180039e4b  lea     rdx, [rbp+arg_18]
0x180039e4f  mov     rax, [rax+40h]
0x180039e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e58  test    eax, eax
0x180039e5a  jz      short loc_180039E7A
0x180039e5c  mov     r9d, 114h; char *
0x180039e62  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039e69  lea     rdx, aUnspecified; "Unspecified."
0x180039e70  mov     ecx, 80040004h; this
0x180039e75  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180039e7a  xor     esi, esi
0x180039e7c  cmp     dword ptr [rbp+arg_18], esi
0x180039e7f  jle     loc_180039F67
0x180039e85  mov     [rbp+var_28], 0
0x180039e8d  mov     rcx, [rbp+arg_10]
0x180039e91  mov     rax, [rcx]
0x180039e94  lea     r8, [rbp+var_28]
0x180039e98  mov     edx, esi
0x180039e9a  mov     rax, [rax+38h]
0x180039e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ea3  test    eax, eax
0x180039ea5  jz      short loc_180039EC5
0x180039ea7  mov     r9d, 11Bh; char *
0x180039ead  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039eb4  lea     rdx, aUnspecified; "Unspecified."
0x180039ebb  mov     ecx, 80040004h; this
0x180039ec0  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180039ec5  mov     ecx, 30h ; '0'; Size
0x180039eca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039ecf  mov     rdi, rax
0x180039ed2  mov     [rbp+var_20], rax
0x180039ed6  xorps   xmm0, xmm0
0x180039ed9  movups  xmmword ptr [rax], xmm0
0x180039edc  mov     eax, 1
0x180039ee1  mov     [rdi+8], eax
0x180039ee4  mov     [rdi+0Ch], eax
0x180039ee7  lea     rax, ??_7?$_Ref_count_obj2@$$CBVInvalidCombinationEntry@PrintDeviceCapabilitiesOM@@@std@@6B@; const std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::InvalidCombinationEntry const>::`vftable'
0x180039eee  mov     [rdi], rax
0x180039ef1  lea     rbx, [rdi+10h]
0x180039ef5  mov     r8, r12
0x180039ef8  lea     rdx, [rbp+var_28]
0x180039efc  mov     rcx, rbx
0x180039eff  call    ??0PwgRasterDocumentType@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z; PrintDeviceCapabilitiesOM::PwgRasterDocumentType::PwgRasterDocumentType(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)
0x180039f04  nop
0x180039f05  or      r15d, 4
0x180039f09  mov     [rbp+var_30], r15d
0x180039f0d  mov     [rbp+var_18], rbx
0x180039f11  mov     [rbp+var_10], rdi
0x180039f15  mov     r9, [r14]
0x180039f18  mov     rcx, [r9+8]
0x180039f1c  cmp     rcx, [r9+10h]
0x180039f20  jz      short loc_180039F32
0x180039f22  lea     rdx, [rbp+var_18]
0x180039f26  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x180039f2b  add     qword ptr [r9+8], 10h
0x180039f30  jmp     short loc_180039F45
0x180039f32  lea     r8, [rbp+var_18]
0x180039f36  mov     rdx, rcx
0x180039f39  mov     rcx, r9
0x180039f3c  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@?$vector@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> * const,std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &)
0x180039f41  mov     rdi, [rbp+var_10]
0x180039f45  test    rdi, rdi
0x180039f48  jz      short loc_180039F53
0x180039f4a  mov     rcx, rdi; this
0x180039f4d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039f52  nop
0x180039f53  lea     rcx, [rbp+var_28]
0x180039f57  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x180039f5c  inc     esi
0x180039f5e  cmp     esi, dword ptr [rbp+arg_18]
0x180039f61  jl      loc_180039E85
0x180039f67  mov     rcx, [rbp+arg_10]
0x180039f6b  test    rcx, rcx
0x180039f6e  jz      short loc_180039F85
0x180039f70  mov     [rbp+arg_10], 0
0x180039f78  mov     rax, [rcx]
0x180039f7b  mov     rax, [rax+10h]
0x180039f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f84  nop
0x180039f85  mov     rax, r14
0x180039f88  add     rsp, 50h
0x180039f8c  pop     r15
0x180039f8e  pop     r14
0x180039f90  pop     r12
0x180039f92  pop     rdi
0x180039f93  pop     rsi
0x180039f94  pop     rbx
0x180039f95  pop     rbp
0x180039f96  retn
```
