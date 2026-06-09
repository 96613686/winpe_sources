# PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::InvalidCombinationEntry const>(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)

- ea: `0x1800393fc`
- end: `0x180039648`
- name: `??$GenericParseMultiple@$$CBVInvalidCombinationEntry@PrintDeviceCapabilitiesOM@@@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEAA?AV?$shared_ptr@V?$vector@V?$shared_ptr@$$CBVInvalidCombinationEntry@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVInvalidCombinationEntry@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z`
- size: `588`
- prototype: `_QWORD *(__int64, _QWORD *, __int64 *, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f630`

## callees

- `0x180002d70`
- `0x180038718`
- `0x1800393fc`
- `0x18003a5f4`
- `0x18003b7a4`
- `0x18003bfd4`
- `0x18003e0e0`
- `0x18003f2dc`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x1800394d5`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180039512`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003955d`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180039491`: `psf2:InvalidCombinationEntry`

## pseudocode

```c
_QWORD *PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::InvalidCombinationEntry const>(
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
  v10 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v19, L"psf2:InvalidCombinationEntry");
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
    PrintDeviceCapabilitiesOM::InvalidCombinationEntry::InvalidCombinationEntry(v12 + 2, v18, a1);
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
0x1800393fc  mov     [rsp-38h+arg_18], r9
0x180039401  mov     [rsp-38h+arg_8], rdx
0x180039406  push    rbp
0x180039407  push    rbx
0x180039408  push    rsi
0x180039409  push    rdi
0x18003940a  push    r12
0x18003940c  push    r14
0x18003940e  push    r15
0x180039410  mov     rbp, rsp
0x180039413  sub     rsp, 50h
0x180039417  mov     rdi, r8
0x18003941a  mov     r14, rdx
0x18003941d  mov     r12, rcx
0x180039420  mov     [rbp+var_30], 0
0x180039427  mov     ecx, 28h ; '('; Size
0x18003942c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039431  mov     [rbp+var_28], rax
0x180039435  xorps   xmm0, xmm0
0x180039438  movups  xmmword ptr [rax], xmm0
0x18003943b  mov     ecx, 1
0x180039440  mov     [rax+8], ecx
0x180039443  mov     [rax+0Ch], ecx
0x180039446  lea     rcx, ??_7?$_Ref_count_obj2@V?$vector@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>>>::`vftable'
0x18003944d  mov     [rax], rcx
0x180039450  lea     rcx, [rax+10h]
0x180039454  mov     qword ptr [rcx], 0
0x18003945b  mov     qword ptr [rcx+8], 0
0x180039463  mov     qword ptr [rcx+10h], 0
0x18003946b  mov     [r14], rcx
0x18003946e  mov     [r14+8], rax
0x180039472  mov     r15d, 3
0x180039478  mov     [rbp+var_30], r15d
0x18003947c  mov     [rbp+arg_10], 0
0x180039484  mov     rdi, [rdi]
0x180039487  mov     rax, [rdi]
0x18003948a  mov     rbx, [rax+120h]
0x180039491  lea     rdx, aPsf2Invalidcom_0; "psf2:InvalidCombinationEntry"
0x180039498  lea     rcx, [rbp+var_18]; this
0x18003949c  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x1800394a1  nop
0x1800394a2  lea     r8, [rbp+arg_10]
0x1800394a6  mov     rdx, [rax+8]
0x1800394aa  mov     rcx, rdi
0x1800394ad  mov     rax, rbx
0x1800394b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394b5  mov     ebx, eax
0x1800394b7  lea     rax, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x1800394be  mov     [rbp+var_18], rax
0x1800394c2  lea     rcx, [rbp+var_18]; this
0x1800394c6  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x1800394cb  test    ebx, ebx
0x1800394cd  jz      short loc_1800394ED
0x1800394cf  mov     r9d, 10Fh; char *
0x1800394d5  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800394dc  lea     rdx, aUnspecified; "Unspecified."
0x1800394e3  mov     ecx, 80040004h; this
0x1800394e8  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x1800394ed  mov     dword ptr [rbp+arg_18], 0
0x1800394f4  mov     rcx, [rbp+arg_10]
0x1800394f8  mov     rax, [rcx]
0x1800394fb  lea     rdx, [rbp+arg_18]
0x1800394ff  mov     rax, [rax+40h]
0x180039503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039508  test    eax, eax
0x18003950a  jz      short loc_18003952A
0x18003950c  mov     r9d, 114h; char *
0x180039512  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039519  lea     rdx, aUnspecified; "Unspecified."
0x180039520  mov     ecx, 80040004h; this
0x180039525  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003952a  xor     esi, esi
0x18003952c  cmp     dword ptr [rbp+arg_18], esi
0x18003952f  jle     loc_180039617
0x180039535  mov     [rbp+var_28], 0
0x18003953d  mov     rcx, [rbp+arg_10]
0x180039541  mov     rax, [rcx]
0x180039544  lea     r8, [rbp+var_28]
0x180039548  mov     edx, esi
0x18003954a  mov     rax, [rax+38h]
0x18003954e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039553  test    eax, eax
0x180039555  jz      short loc_180039575
0x180039557  mov     r9d, 11Bh; char *
0x18003955d  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039564  lea     rdx, aUnspecified; "Unspecified."
0x18003956b  mov     ecx, 80040004h; this
0x180039570  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180039575  mov     ecx, 30h ; '0'; Size
0x18003957a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003957f  mov     rdi, rax
0x180039582  mov     [rbp+var_20], rax
0x180039586  xorps   xmm0, xmm0
0x180039589  movups  xmmword ptr [rax], xmm0
0x18003958c  mov     eax, 1
0x180039591  mov     [rdi+8], eax
0x180039594  mov     [rdi+0Ch], eax
0x180039597  lea     rax, ??_7?$_Ref_count_obj2@$$CBVInvalidCombinationEntry@PrintDeviceCapabilitiesOM@@@std@@6B@; const std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::InvalidCombinationEntry const>::`vftable'
0x18003959e  mov     [rdi], rax
0x1800395a1  lea     rbx, [rdi+10h]
0x1800395a5  mov     r8, r12
0x1800395a8  lea     rdx, [rbp+var_28]
0x1800395ac  mov     rcx, rbx
0x1800395af  call    ??0InvalidCombinationEntry@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z; PrintDeviceCapabilitiesOM::InvalidCombinationEntry::InvalidCombinationEntry(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)
0x1800395b4  nop
0x1800395b5  or      r15d, 4
0x1800395b9  mov     [rbp+var_30], r15d
0x1800395bd  mov     [rbp+var_18], rbx
0x1800395c1  mov     [rbp+var_10], rdi
0x1800395c5  mov     r9, [r14]
0x1800395c8  mov     rcx, [r9+8]
0x1800395cc  cmp     rcx, [r9+10h]
0x1800395d0  jz      short loc_1800395E2
0x1800395d2  lea     rdx, [rbp+var_18]
0x1800395d6  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x1800395db  add     qword ptr [r9+8], 10h
0x1800395e0  jmp     short loc_1800395F5
0x1800395e2  lea     r8, [rbp+var_18]
0x1800395e6  mov     rdx, rcx
0x1800395e9  mov     rcx, r9
0x1800395ec  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@?$vector@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> * const,std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &)
0x1800395f1  mov     rdi, [rbp+var_10]
0x1800395f5  test    rdi, rdi
0x1800395f8  jz      short loc_180039603
0x1800395fa  mov     rcx, rdi; this
0x1800395fd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039602  nop
0x180039603  lea     rcx, [rbp+var_28]
0x180039607  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x18003960c  inc     esi
0x18003960e  cmp     esi, dword ptr [rbp+arg_18]
0x180039611  jl      loc_180039535
0x180039617  mov     rcx, [rbp+arg_10]
0x18003961b  test    rcx, rcx
0x18003961e  jz      short loc_180039635
0x180039620  mov     [rbp+arg_10], 0
0x180039628  mov     rax, [rcx]
0x18003962b  mov     rax, [rax+10h]
0x18003962f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039634  nop
0x180039635  mov     rax, r14
0x180039638  add     rsp, 50h
0x18003963c  pop     r15
0x18003963e  pop     r14
0x180039640  pop     r12
0x180039642  pop     rdi
0x180039643  pop     rsi
0x180039644  pop     rbx
0x180039645  pop     rbp
0x180039646  retn
```
