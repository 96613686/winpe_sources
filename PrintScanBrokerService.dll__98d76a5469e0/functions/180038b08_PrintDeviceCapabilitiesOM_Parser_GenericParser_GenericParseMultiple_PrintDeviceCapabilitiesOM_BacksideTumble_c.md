# PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::BacksideTumble const>(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)

- ea: `0x180038b08`
- end: `0x180038d54`
- name: `??$GenericParseMultiple@$$CBVBacksideTumble@PrintDeviceCapabilitiesOM@@@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEAA?AV?$shared_ptr@V?$vector@V?$shared_ptr@$$CBVBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z`
- size: `588`
- prototype: `_QWORD *(__int64, _QWORD *, __int64 *, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f430`

## callees

- `0x180002d70`
- `0x180038718`
- `0x180038b08`
- `0x18003a5f4`
- `0x18003b7a4`
- `0x18003b7f4`
- `0x18003e0e0`
- `0x18003f2dc`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x180038be1`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180038c1e`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180038c69`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180038b9d`: `ns0000:BacksideTumble`

## pseudocode

```c
_QWORD *PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::BacksideTumble const>(
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
  v10 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v19, L"ns0000:BacksideTumble");
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
    v12 = (void **)operator new(0x28u);
    v18[1] = v12;
    *(_OWORD *)v12 = 0;
    *((_DWORD *)v12 + 2) = 1;
    *((_DWORD *)v12 + 3) = 1;
    *v12 = &std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>::`vftable';
    PrintDeviceCapabilitiesOM::BacksideTumble::BacksideTumble(v12 + 2, v18, a1);
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
0x180038b08  mov     [rsp-38h+arg_18], r9
0x180038b0d  mov     [rsp-38h+arg_8], rdx
0x180038b12  push    rbp
0x180038b13  push    rbx
0x180038b14  push    rsi
0x180038b15  push    rdi
0x180038b16  push    r12
0x180038b18  push    r14
0x180038b1a  push    r15
0x180038b1c  mov     rbp, rsp
0x180038b1f  sub     rsp, 50h
0x180038b23  mov     rdi, r8
0x180038b26  mov     r14, rdx
0x180038b29  mov     r12, rcx
0x180038b2c  mov     [rbp+var_30], 0
0x180038b33  mov     ecx, 28h ; '('; Size
0x180038b38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038b3d  mov     [rbp+var_28], rax
0x180038b41  xorps   xmm0, xmm0
0x180038b44  movups  xmmword ptr [rax], xmm0
0x180038b47  mov     ecx, 1
0x180038b4c  mov     [rax+8], ecx
0x180038b4f  mov     [rax+0Ch], ecx
0x180038b52  lea     rcx, ??_7?$_Ref_count_obj2@V?$vector@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>>>::`vftable'
0x180038b59  mov     [rax], rcx
0x180038b5c  lea     rcx, [rax+10h]
0x180038b60  mov     qword ptr [rcx], 0
0x180038b67  mov     qword ptr [rcx+8], 0
0x180038b6f  mov     qword ptr [rcx+10h], 0
0x180038b77  mov     [r14], rcx
0x180038b7a  mov     [r14+8], rax
0x180038b7e  mov     r15d, 3
0x180038b84  mov     [rbp+var_30], r15d
0x180038b88  mov     [rbp+arg_10], 0
0x180038b90  mov     rdi, [rdi]
0x180038b93  mov     rax, [rdi]
0x180038b96  mov     rbx, [rax+120h]
0x180038b9d  lea     rdx, aNs0000Backside; "ns0000:BacksideTumble"
0x180038ba4  lea     rcx, [rbp+var_18]; this
0x180038ba8  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x180038bad  nop
0x180038bae  lea     r8, [rbp+arg_10]
0x180038bb2  mov     rdx, [rax+8]
0x180038bb6  mov     rcx, rdi
0x180038bb9  mov     rax, rbx
0x180038bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bc1  mov     ebx, eax
0x180038bc3  lea     rax, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x180038bca  mov     [rbp+var_18], rax
0x180038bce  lea     rcx, [rbp+var_18]; this
0x180038bd2  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x180038bd7  test    ebx, ebx
0x180038bd9  jz      short loc_180038BF9
0x180038bdb  mov     r9d, 10Fh; char *
0x180038be1  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180038be8  lea     rdx, aUnspecified; "Unspecified."
0x180038bef  mov     ecx, 80040004h; this
0x180038bf4  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180038bf9  mov     dword ptr [rbp+arg_18], 0
0x180038c00  mov     rcx, [rbp+arg_10]
0x180038c04  mov     rax, [rcx]
0x180038c07  lea     rdx, [rbp+arg_18]
0x180038c0b  mov     rax, [rax+40h]
0x180038c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c14  test    eax, eax
0x180038c16  jz      short loc_180038C36
0x180038c18  mov     r9d, 114h; char *
0x180038c1e  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180038c25  lea     rdx, aUnspecified; "Unspecified."
0x180038c2c  mov     ecx, 80040004h; this
0x180038c31  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180038c36  xor     esi, esi
0x180038c38  cmp     dword ptr [rbp+arg_18], esi
0x180038c3b  jle     loc_180038D23
0x180038c41  mov     [rbp+var_28], 0
0x180038c49  mov     rcx, [rbp+arg_10]
0x180038c4d  mov     rax, [rcx]
0x180038c50  lea     r8, [rbp+var_28]
0x180038c54  mov     edx, esi
0x180038c56  mov     rax, [rax+38h]
0x180038c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c5f  test    eax, eax
0x180038c61  jz      short loc_180038C81
0x180038c63  mov     r9d, 11Bh; char *
0x180038c69  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180038c70  lea     rdx, aUnspecified; "Unspecified."
0x180038c77  mov     ecx, 80040004h; this
0x180038c7c  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180038c81  mov     ecx, 28h ; '('; Size
0x180038c86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038c8b  mov     rdi, rax
0x180038c8e  mov     [rbp+var_20], rax
0x180038c92  xorps   xmm0, xmm0
0x180038c95  movups  xmmword ptr [rax], xmm0
0x180038c98  mov     eax, 1
0x180038c9d  mov     [rdi+8], eax
0x180038ca0  mov     [rdi+0Ch], eax
0x180038ca3  lea     rax, ??_7?$_Ref_count_obj2@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@6B@; const std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>::`vftable'
0x180038caa  mov     [rdi], rax
0x180038cad  lea     rbx, [rdi+10h]
0x180038cb1  mov     r8, r12
0x180038cb4  lea     rdx, [rbp+var_28]
0x180038cb8  mov     rcx, rbx
0x180038cbb  call    ??0BacksideTumble@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z; PrintDeviceCapabilitiesOM::BacksideTumble::BacksideTumble(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)
0x180038cc0  nop
0x180038cc1  or      r15d, 4
0x180038cc5  mov     [rbp+var_30], r15d
0x180038cc9  mov     [rbp+var_18], rbx
0x180038ccd  mov     [rbp+var_10], rdi
0x180038cd1  mov     r9, [r14]
0x180038cd4  mov     rcx, [r9+8]
0x180038cd8  cmp     rcx, [r9+10h]
0x180038cdc  jz      short loc_180038CEE
0x180038cde  lea     rdx, [rbp+var_18]
0x180038ce2  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x180038ce7  add     qword ptr [r9+8], 10h
0x180038cec  jmp     short loc_180038D01
0x180038cee  lea     r8, [rbp+var_18]
0x180038cf2  mov     rdx, rcx
0x180038cf5  mov     rcx, r9
0x180038cf8  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@?$vector@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> * const,std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &)
0x180038cfd  mov     rdi, [rbp+var_10]
0x180038d01  test    rdi, rdi
0x180038d04  jz      short loc_180038D0F
0x180038d06  mov     rcx, rdi; this
0x180038d09  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180038d0e  nop
0x180038d0f  lea     rcx, [rbp+var_28]
0x180038d13  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x180038d18  inc     esi
0x180038d1a  cmp     esi, dword ptr [rbp+arg_18]
0x180038d1d  jl      loc_180038C41
0x180038d23  mov     rcx, [rbp+arg_10]
0x180038d27  test    rcx, rcx
0x180038d2a  jz      short loc_180038D41
0x180038d2c  mov     [rbp+arg_10], 0
0x180038d34  mov     rax, [rcx]
0x180038d37  mov     rax, [rax+10h]
0x180038d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d40  nop
0x180038d41  mov     rax, r14
0x180038d44  add     rsp, 50h
0x180038d48  pop     r15
0x180038d4a  pop     r14
0x180038d4c  pop     r12
0x180038d4e  pop     rdi
0x180038d4f  pop     rsi
0x180038d50  pop     rbx
0x180038d51  pop     rbp
0x180038d52  retn
```
