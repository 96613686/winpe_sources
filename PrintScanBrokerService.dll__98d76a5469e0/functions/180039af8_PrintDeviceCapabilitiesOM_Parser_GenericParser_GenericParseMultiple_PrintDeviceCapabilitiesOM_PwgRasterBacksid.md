# PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)

- ea: `0x180039af8`
- end: `0x180039d44`
- name: `??$GenericParseMultiple@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEAA?AV?$shared_ptr@V?$vector@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z`
- size: `588`
- prototype: `_QWORD *(__int64, _QWORD *, __int64 *, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f6b0`

## callees

- `0x180002d70`
- `0x180038718`
- `0x180039af8`
- `0x18003a5f4`
- `0x18003b7a4`
- `0x18003cadc`
- `0x18003e0e0`
- `0x18003f2dc`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x180039bd1`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180039c0e`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180039c59`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180039b8d`: `psf2:PwgRasterBacksideTumble`

## pseudocode

```c
_QWORD *PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>(
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
  v10 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v19, L"psf2:PwgRasterBacksideTumble");
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
    PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble::PwgRasterBacksideTumble(v12 + 2, v18, a1);
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
0x180039af8  mov     [rsp-38h+arg_18], r9
0x180039afd  mov     [rsp-38h+arg_8], rdx
0x180039b02  push    rbp
0x180039b03  push    rbx
0x180039b04  push    rsi
0x180039b05  push    rdi
0x180039b06  push    r12
0x180039b08  push    r14
0x180039b0a  push    r15
0x180039b0c  mov     rbp, rsp
0x180039b0f  sub     rsp, 50h
0x180039b13  mov     rdi, r8
0x180039b16  mov     r14, rdx
0x180039b19  mov     r12, rcx
0x180039b1c  mov     [rbp+var_30], 0
0x180039b23  mov     ecx, 28h ; '('; Size
0x180039b28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039b2d  mov     [rbp+var_28], rax
0x180039b31  xorps   xmm0, xmm0
0x180039b34  movups  xmmword ptr [rax], xmm0
0x180039b37  mov     ecx, 1
0x180039b3c  mov     [rax+8], ecx
0x180039b3f  mov     [rax+0Ch], ecx
0x180039b42  lea     rcx, ??_7?$_Ref_count_obj2@V?$vector@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>>>::`vftable'
0x180039b49  mov     [rax], rcx
0x180039b4c  lea     rcx, [rax+10h]
0x180039b50  mov     qword ptr [rcx], 0
0x180039b57  mov     qword ptr [rcx+8], 0
0x180039b5f  mov     qword ptr [rcx+10h], 0
0x180039b67  mov     [r14], rcx
0x180039b6a  mov     [r14+8], rax
0x180039b6e  mov     r15d, 3
0x180039b74  mov     [rbp+var_30], r15d
0x180039b78  mov     [rbp+arg_10], 0
0x180039b80  mov     rdi, [rdi]
0x180039b83  mov     rax, [rdi]
0x180039b86  mov     rbx, [rax+120h]
0x180039b8d  lea     rdx, aPsf2Pwgrasterb; "psf2:PwgRasterBacksideTumble"
0x180039b94  lea     rcx, [rbp+var_18]; this
0x180039b98  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x180039b9d  nop
0x180039b9e  lea     r8, [rbp+arg_10]
0x180039ba2  mov     rdx, [rax+8]
0x180039ba6  mov     rcx, rdi
0x180039ba9  mov     rax, rbx
0x180039bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039bb1  mov     ebx, eax
0x180039bb3  lea     rax, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x180039bba  mov     [rbp+var_18], rax
0x180039bbe  lea     rcx, [rbp+var_18]; this
0x180039bc2  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x180039bc7  test    ebx, ebx
0x180039bc9  jz      short loc_180039BE9
0x180039bcb  mov     r9d, 10Fh; char *
0x180039bd1  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039bd8  lea     rdx, aUnspecified; "Unspecified."
0x180039bdf  mov     ecx, 80040004h; this
0x180039be4  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180039be9  mov     dword ptr [rbp+arg_18], 0
0x180039bf0  mov     rcx, [rbp+arg_10]
0x180039bf4  mov     rax, [rcx]
0x180039bf7  lea     rdx, [rbp+arg_18]
0x180039bfb  mov     rax, [rax+40h]
0x180039bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c04  test    eax, eax
0x180039c06  jz      short loc_180039C26
0x180039c08  mov     r9d, 114h; char *
0x180039c0e  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039c15  lea     rdx, aUnspecified; "Unspecified."
0x180039c1c  mov     ecx, 80040004h; this
0x180039c21  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180039c26  xor     esi, esi
0x180039c28  cmp     dword ptr [rbp+arg_18], esi
0x180039c2b  jle     loc_180039D13
0x180039c31  mov     [rbp+var_28], 0
0x180039c39  mov     rcx, [rbp+arg_10]
0x180039c3d  mov     rax, [rcx]
0x180039c40  lea     r8, [rbp+var_28]
0x180039c44  mov     edx, esi
0x180039c46  mov     rax, [rax+38h]
0x180039c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c4f  test    eax, eax
0x180039c51  jz      short loc_180039C71
0x180039c53  mov     r9d, 11Bh; char *
0x180039c59  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180039c60  lea     rdx, aUnspecified; "Unspecified."
0x180039c67  mov     ecx, 80040004h; this
0x180039c6c  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180039c71  mov     ecx, 28h ; '('; Size
0x180039c76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039c7b  mov     rdi, rax
0x180039c7e  mov     [rbp+var_20], rax
0x180039c82  xorps   xmm0, xmm0
0x180039c85  movups  xmmword ptr [rax], xmm0
0x180039c88  mov     eax, 1
0x180039c8d  mov     [rdi+8], eax
0x180039c90  mov     [rdi+0Ch], eax
0x180039c93  lea     rax, ??_7?$_Ref_count_obj2@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@6B@; const std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>::`vftable'
0x180039c9a  mov     [rdi], rax
0x180039c9d  lea     rbx, [rdi+10h]
0x180039ca1  mov     r8, r12
0x180039ca4  lea     rdx, [rbp+var_28]
0x180039ca8  mov     rcx, rbx
0x180039cab  call    ??0PwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z; PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble::PwgRasterBacksideTumble(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)
0x180039cb0  nop
0x180039cb1  or      r15d, 4
0x180039cb5  mov     [rbp+var_30], r15d
0x180039cb9  mov     [rbp+var_18], rbx
0x180039cbd  mov     [rbp+var_10], rdi
0x180039cc1  mov     r9, [r14]
0x180039cc4  mov     rcx, [r9+8]
0x180039cc8  cmp     rcx, [r9+10h]
0x180039ccc  jz      short loc_180039CDE
0x180039cce  lea     rdx, [rbp+var_18]
0x180039cd2  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x180039cd7  add     qword ptr [r9+8], 10h
0x180039cdc  jmp     short loc_180039CF1
0x180039cde  lea     r8, [rbp+var_18]
0x180039ce2  mov     rdx, rcx
0x180039ce5  mov     rcx, r9
0x180039ce8  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@?$vector@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> * const,std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &)
0x180039ced  mov     rdi, [rbp+var_10]
0x180039cf1  test    rdi, rdi
0x180039cf4  jz      short loc_180039CFF
0x180039cf6  mov     rcx, rdi; this
0x180039cf9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039cfe  nop
0x180039cff  lea     rcx, [rbp+var_28]
0x180039d03  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x180039d08  inc     esi
0x180039d0a  cmp     esi, dword ptr [rbp+arg_18]
0x180039d0d  jl      loc_180039C31
0x180039d13  mov     rcx, [rbp+arg_10]
0x180039d17  test    rcx, rcx
0x180039d1a  jz      short loc_180039D31
0x180039d1c  mov     [rbp+arg_10], 0
0x180039d24  mov     rax, [rcx]
0x180039d27  mov     rax, [rax+10h]
0x180039d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d30  nop
0x180039d31  mov     rax, r14
0x180039d34  add     rsp, 50h
0x180039d38  pop     r15
0x180039d3a  pop     r14
0x180039d3c  pop     r12
0x180039d3e  pop     rdi
0x180039d3f  pop     rsi
0x180039d40  pop     rbx
0x180039d41  pop     rbp
0x180039d42  retn
```
