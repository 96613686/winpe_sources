# PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::ScoredProperty const>(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)

- ea: `0x180039fa0`
- end: `0x18003a1ec`
- name: `??$GenericParseMultiple@$$CBVScoredProperty@PrintDeviceCapabilitiesOM@@@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEAA?AV?$shared_ptr@V?$vector@V?$shared_ptr@$$CBVScoredProperty@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVScoredProperty@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z`
- size: `588`
- prototype: `_QWORD *(__int64, _QWORD *, __int64 *, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f810`

## callees

- `0x180002d70`
- `0x180038718`
- `0x180039fa0`
- `0x18003a5f4`
- `0x18003b7a4`
- `0x18003cec4`
- `0x18003e0e0`
- `0x18003f2dc`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x18003a079`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003a0b6`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003a101`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::ScoredProperty const>(
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
  v10 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v19, L"*[@psf2:psftype='ScoredProperty']");
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
    PrintDeviceCapabilitiesOM::ScoredProperty::ScoredProperty(v12 + 2, v18, a1);
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
0x180039fa0  mov     [rsp-38h+arg_18], r9
0x180039fa5  mov     [rsp-38h+arg_8], rdx
0x180039faa  push    rbp
0x180039fab  push    rbx
0x180039fac  push    rsi
0x180039fad  push    rdi
0x180039fae  push    r12
0x180039fb0  push    r14
0x180039fb2  push    r15
0x180039fb4  mov     rbp, rsp
0x180039fb7  sub     rsp, 50h
0x180039fbb  mov     rdi, r8
0x180039fbe  mov     r14, rdx
0x180039fc1  mov     r12, rcx
0x180039fc4  mov     [rbp+var_30], 0
0x180039fcb  mov     ecx, 28h ; '('; Size
0x180039fd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039fd5  mov     [rbp+var_28], rax
0x180039fd9  xorps   xmm0, xmm0
0x180039fdc  movups  xmmword ptr [rax], xmm0
0x180039fdf  mov     ecx, 1
0x180039fe4  mov     [rax+8], ecx
0x180039fe7  mov     [rax+0Ch], ecx
0x180039fea  lea     rcx, ??_7?$_Ref_count_obj2@V?$vector@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>>>::`vftable'
0x180039ff1  mov     [rax], rcx
0x180039ff4  lea     rcx, [rax+10h]
0x180039ff8  mov     qword ptr [rcx], 0
0x180039fff  mov     qword ptr [rcx+8], 0
0x18003a007  mov     qword ptr [rcx+10h], 0
0x18003a00f  mov     [r14], rcx
0x18003a012  mov     [r14+8], rax
0x18003a016  mov     r15d, 3
0x18003a01c  mov     [rbp+var_30], r15d
0x18003a020  mov     [rbp+arg_10], 0
0x18003a028  mov     rdi, [rdi]
0x18003a02b  mov     rax, [rdi]
0x18003a02e  mov     rbx, [rax+120h]
0x18003a035  lea     rdx, aPsf2PsftypeSco; "*[@psf2:psftype='ScoredProperty']"
0x18003a03c  lea     rcx, [rbp+var_18]; this
0x18003a040  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x18003a045  nop
0x18003a046  lea     r8, [rbp+arg_10]
0x18003a04a  mov     rdx, [rax+8]
0x18003a04e  mov     rcx, rdi
0x18003a051  mov     rax, rbx
0x18003a054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a059  mov     ebx, eax
0x18003a05b  lea     rax, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x18003a062  mov     [rbp+var_18], rax
0x18003a066  lea     rcx, [rbp+var_18]; this
0x18003a06a  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003a06f  test    ebx, ebx
0x18003a071  jz      short loc_18003A091
0x18003a073  mov     r9d, 10Fh; char *
0x18003a079  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003a080  lea     rdx, aUnspecified; "Unspecified."
0x18003a087  mov     ecx, 80040004h; this
0x18003a08c  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003a091  mov     dword ptr [rbp+arg_18], 0
0x18003a098  mov     rcx, [rbp+arg_10]
0x18003a09c  mov     rax, [rcx]
0x18003a09f  lea     rdx, [rbp+arg_18]
0x18003a0a3  mov     rax, [rax+40h]
0x18003a0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0ac  test    eax, eax
0x18003a0ae  jz      short loc_18003A0CE
0x18003a0b0  mov     r9d, 114h; char *
0x18003a0b6  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003a0bd  lea     rdx, aUnspecified; "Unspecified."
0x18003a0c4  mov     ecx, 80040004h; this
0x18003a0c9  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003a0ce  xor     esi, esi
0x18003a0d0  cmp     dword ptr [rbp+arg_18], esi
0x18003a0d3  jle     loc_18003A1BB
0x18003a0d9  mov     [rbp+var_28], 0
0x18003a0e1  mov     rcx, [rbp+arg_10]
0x18003a0e5  mov     rax, [rcx]
0x18003a0e8  lea     r8, [rbp+var_28]
0x18003a0ec  mov     edx, esi
0x18003a0ee  mov     rax, [rax+38h]
0x18003a0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0f7  test    eax, eax
0x18003a0f9  jz      short loc_18003A119
0x18003a0fb  mov     r9d, 11Bh; char *
0x18003a101  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003a108  lea     rdx, aUnspecified; "Unspecified."
0x18003a10f  mov     ecx, 80040004h; this
0x18003a114  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003a119  mov     ecx, 30h ; '0'; Size
0x18003a11e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a123  mov     rdi, rax
0x18003a126  mov     [rbp+var_20], rax
0x18003a12a  xorps   xmm0, xmm0
0x18003a12d  movups  xmmword ptr [rax], xmm0
0x18003a130  mov     eax, 1
0x18003a135  mov     [rdi+8], eax
0x18003a138  mov     [rdi+0Ch], eax
0x18003a13b  lea     rax, ??_7?$_Ref_count_obj2@$$CBVInvalidCombinationEntry@PrintDeviceCapabilitiesOM@@@std@@6B@; const std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::InvalidCombinationEntry const>::`vftable'
0x18003a142  mov     [rdi], rax
0x18003a145  lea     rbx, [rdi+10h]
0x18003a149  mov     r8, r12
0x18003a14c  lea     rdx, [rbp+var_28]
0x18003a150  mov     rcx, rbx
0x18003a153  call    ??0ScoredProperty@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z; PrintDeviceCapabilitiesOM::ScoredProperty::ScoredProperty(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)
0x18003a158  nop
0x18003a159  or      r15d, 4
0x18003a15d  mov     [rbp+var_30], r15d
0x18003a161  mov     [rbp+var_18], rbx
0x18003a165  mov     [rbp+var_10], rdi
0x18003a169  mov     r9, [r14]
0x18003a16c  mov     rcx, [r9+8]
0x18003a170  cmp     rcx, [r9+10h]
0x18003a174  jz      short loc_18003A186
0x18003a176  lea     rdx, [rbp+var_18]
0x18003a17a  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003a17f  add     qword ptr [r9+8], 10h
0x18003a184  jmp     short loc_18003A199
0x18003a186  lea     r8, [rbp+var_18]
0x18003a18a  mov     rdx, rcx
0x18003a18d  mov     rcx, r9
0x18003a190  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@?$vector@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> * const,std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &)
0x18003a195  mov     rdi, [rbp+var_10]
0x18003a199  test    rdi, rdi
0x18003a19c  jz      short loc_18003A1A7
0x18003a19e  mov     rcx, rdi; this
0x18003a1a1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003a1a6  nop
0x18003a1a7  lea     rcx, [rbp+var_28]
0x18003a1ab  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x18003a1b0  inc     esi
0x18003a1b2  cmp     esi, dword ptr [rbp+arg_18]
0x18003a1b5  jl      loc_18003A0D9
0x18003a1bb  mov     rcx, [rbp+arg_10]
0x18003a1bf  test    rcx, rcx
0x18003a1c2  jz      short loc_18003A1D9
0x18003a1c4  mov     [rbp+arg_10], 0
0x18003a1cc  mov     rax, [rcx]
0x18003a1cf  mov     rax, [rax+10h]
0x18003a1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1d8  nop
0x18003a1d9  mov     rax, r14
0x18003a1dc  add     rsp, 50h
0x18003a1e0  pop     r15
0x18003a1e2  pop     r14
0x18003a1e4  pop     r12
0x18003a1e6  pop     rdi
0x18003a1e7  pop     rsi
0x18003a1e8  pop     rbx
0x18003a1e9  pop     rbp
0x18003a1ea  retn
```
