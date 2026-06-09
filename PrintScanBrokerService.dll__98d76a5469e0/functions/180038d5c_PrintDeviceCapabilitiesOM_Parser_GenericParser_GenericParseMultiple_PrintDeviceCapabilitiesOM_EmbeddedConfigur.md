# PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::EmbeddedConfigurationFormat const>(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)

- ea: `0x180038d5c`
- end: `0x180038fa3`
- name: `??$GenericParseMultiple@$$CBVEmbeddedConfigurationFormat@PrintDeviceCapabilitiesOM@@@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEAA?AV?$shared_ptr@V?$vector@V?$shared_ptr@$$CBVEmbeddedConfigurationFormat@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVEmbeddedConfigurationFormat@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z`
- size: `583`
- prototype: `_QWORD *(__int64, _QWORD *, __int64 *, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f5d0`

## callees

- `0x180002d70`
- `0x180038718`
- `0x180038d5c`
- `0x18003a5f4`
- `0x18003b7a4`
- `0x18003bb30`
- `0x18003e0e0`
- `0x18003f2dc`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x180038e35`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180038e72`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180038ebd`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180038df1`: `psf2:EmbeddedConfigurationFormats/psf2:EmbeddedConfigurationFormatEntry`

## pseudocode

```c
_QWORD *PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::EmbeddedConfigurationFormat const>(
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
  void **v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // rcx
  unsigned int v16; // [rsp+20h] [rbp-28h]
  void **v17; // [rsp+30h] [rbp-18h] BYREF
  void **v18; // [rsp+38h] [rbp-10h]
  __int64 v19; // [rsp+80h] [rbp+38h] BYREF
  _QWORD *v20; // [rsp+88h] [rbp+40h]
  _DWORD *v21; // [rsp+90h] [rbp+48h] BYREF
  __int64 v22; // [rsp+98h] [rbp+50h] BYREF
  va_list va; // [rsp+98h] [rbp+50h]
  va_list va1; // [rsp+A0h] [rbp+58h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v22 = va_arg(va1, _QWORD);
  v20 = a2;
  v19 = a1;
  v5 = operator new(0x28u);
  v21 = v5;
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
  v19 = 0;
  v7 = *a3;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v7 + 288LL);
  v9 = PrintCore::BStrRAII::BStrRAII(
         (PrintCore::BStrRAII *)&v17,
         L"psf2:EmbeddedConfigurationFormats/psf2:EmbeddedConfigurationFormatEntry");
  LODWORD(v8) = v8(v7, *(_QWORD *)(v9 + 8), &v19);
  v17 = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v17);
  if ( (_DWORD)v8 )
    PrintCore::ThrowIfError(
      (PrintCore *)0x80040004LL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x10F,
      3u);
  LODWORD(v22) = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 64LL))(v19, (__int64 *)va) )
    PrintCore::ThrowIfError(
      (PrintCore *)0x80040004LL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x114,
      v16);
  for ( i = 0; i < (int)v22; ++i )
  {
    v21 = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _DWORD **))(*(_QWORD *)v19 + 56LL))(
           v19,
           (unsigned int)i,
           &v21) )
    {
      PrintCore::ThrowIfError(
        (PrintCore *)0x80040004LL,
        "Unspecified.",
        "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
        (const char *)0x11B,
        v16);
    }
    v11 = (void **)operator new(0x28u);
    *(_OWORD *)v11 = 0;
    *((_DWORD *)v11 + 2) = 1;
    *((_DWORD *)v11 + 3) = 1;
    *v11 = &std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>::`vftable';
    PrintDeviceCapabilitiesOM::EmbeddedConfigurationFormat::EmbeddedConfigurationFormat(v11 + 2, &v21);
    v6 |= 4u;
    v16 = v6;
    v17 = v11 + 2;
    v18 = v11;
    v12 = *(_QWORD *)(*a2 + 8LL);
    if ( v12 == *(_QWORD *)(*a2 + 16LL) )
    {
      std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(
        *a2,
        *(_QWORD *)(*a2 + 8LL),
        &v17);
      v11 = v18;
    }
    else
    {
      std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(v12, &v17);
      *(_QWORD *)(v13 + 8) += 16LL;
    }
    if ( v11 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v11);
    Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(&v21);
  }
  v14 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return a2;
}

```

## disassembly

```asm
0x180038d5c  mov     [rsp-30h+arg_18], r9
0x180038d61  mov     [rsp-30h+arg_8], rdx
0x180038d66  mov     [rsp-30h+arg_0], rcx
0x180038d6b  push    rbp
0x180038d6c  push    rbx
0x180038d6d  push    rsi
0x180038d6e  push    rdi
0x180038d6f  push    r14
0x180038d71  push    r15
0x180038d73  mov     rbp, rsp
0x180038d76  sub     rsp, 48h
0x180038d7a  mov     rdi, r8
0x180038d7d  mov     r14, rdx
0x180038d80  mov     [rbp+var_28], 0
0x180038d87  mov     ecx, 28h ; '('; Size
0x180038d8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038d91  mov     [rbp+arg_10], rax
0x180038d95  xorps   xmm0, xmm0
0x180038d98  movups  xmmword ptr [rax], xmm0
0x180038d9b  mov     ecx, 1
0x180038da0  mov     [rax+8], ecx
0x180038da3  mov     [rax+0Ch], ecx
0x180038da6  lea     rcx, ??_7?$_Ref_count_obj2@V?$vector@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>>>::`vftable'
0x180038dad  mov     [rax], rcx
0x180038db0  lea     rcx, [rax+10h]
0x180038db4  mov     qword ptr [rcx], 0
0x180038dbb  mov     qword ptr [rcx+8], 0
0x180038dc3  mov     qword ptr [rcx+10h], 0
0x180038dcb  mov     [r14], rcx
0x180038dce  mov     [r14+8], rax
0x180038dd2  mov     r15d, 3
0x180038dd8  mov     [rbp+var_28], r15d
0x180038ddc  mov     [rbp+arg_0], 0
0x180038de4  mov     rdi, [rdi]
0x180038de7  mov     rax, [rdi]
0x180038dea  mov     rbx, [rax+120h]
0x180038df1  lea     rdx, aPsf2Embeddedco; "psf2:EmbeddedConfigurationFormats/psf2:"...
0x180038df8  lea     rcx, [rbp+var_18]; this
0x180038dfc  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x180038e01  nop
0x180038e02  lea     r8, [rbp+arg_0]
0x180038e06  mov     rdx, [rax+8]
0x180038e0a  mov     rcx, rdi
0x180038e0d  mov     rax, rbx
0x180038e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e15  mov     ebx, eax
0x180038e17  lea     rax, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x180038e1e  mov     [rbp+var_18], rax
0x180038e22  lea     rcx, [rbp+var_18]; this
0x180038e26  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x180038e2b  test    ebx, ebx
0x180038e2d  jz      short loc_180038E4D
0x180038e2f  mov     r9d, 10Fh; char *
0x180038e35  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180038e3c  lea     rdx, aUnspecified; "Unspecified."
0x180038e43  mov     ecx, 80040004h; this
0x180038e48  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180038e4d  mov     dword ptr [rbp+arg_18], 0
0x180038e54  mov     rcx, [rbp+arg_0]
0x180038e58  mov     rax, [rcx]
0x180038e5b  lea     rdx, [rbp+arg_18]
0x180038e5f  mov     rax, [rax+40h]
0x180038e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e68  test    eax, eax
0x180038e6a  jz      short loc_180038E8A
0x180038e6c  mov     r9d, 114h; char *
0x180038e72  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180038e79  lea     rdx, aUnspecified; "Unspecified."
0x180038e80  mov     ecx, 80040004h; this
0x180038e85  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180038e8a  xor     esi, esi
0x180038e8c  cmp     dword ptr [rbp+arg_18], esi
0x180038e8f  jle     loc_180038F74
0x180038e95  mov     [rbp+arg_10], 0
0x180038e9d  mov     rcx, [rbp+arg_0]
0x180038ea1  mov     rax, [rcx]
0x180038ea4  lea     r8, [rbp+arg_10]
0x180038ea8  mov     edx, esi
0x180038eaa  mov     rax, [rax+38h]
0x180038eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038eb3  test    eax, eax
0x180038eb5  jz      short loc_180038ED5
0x180038eb7  mov     r9d, 11Bh; char *
0x180038ebd  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180038ec4  lea     rdx, aUnspecified; "Unspecified."
0x180038ecb  mov     ecx, 80040004h; this
0x180038ed0  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180038ed5  mov     ecx, 28h ; '('; Size
0x180038eda  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038edf  mov     rdi, rax
0x180038ee2  mov     [rbp+var_20], rax
0x180038ee6  xorps   xmm0, xmm0
0x180038ee9  movups  xmmword ptr [rax], xmm0
0x180038eec  mov     eax, 1
0x180038ef1  mov     [rdi+8], eax
0x180038ef4  mov     [rdi+0Ch], eax
0x180038ef7  lea     rax, ??_7?$_Ref_count_obj2@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@6B@; const std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>::`vftable'
0x180038efe  mov     [rdi], rax
0x180038f01  lea     rbx, [rdi+10h]
0x180038f05  lea     rdx, [rbp+arg_10]
0x180038f09  mov     rcx, rbx
0x180038f0c  call    ??0EmbeddedConfigurationFormat@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z; PrintDeviceCapabilitiesOM::EmbeddedConfigurationFormat::EmbeddedConfigurationFormat(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)
0x180038f11  nop
0x180038f12  or      r15d, 4
0x180038f16  mov     [rbp+var_28], r15d
0x180038f1a  mov     [rbp+var_18], rbx
0x180038f1e  mov     [rbp+var_10], rdi
0x180038f22  mov     r9, [r14]
0x180038f25  mov     rcx, [r9+8]
0x180038f29  cmp     rcx, [r9+10h]
0x180038f2d  jz      short loc_180038F3F
0x180038f2f  lea     rdx, [rbp+var_18]
0x180038f33  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x180038f38  add     qword ptr [r9+8], 10h
0x180038f3d  jmp     short loc_180038F52
0x180038f3f  lea     r8, [rbp+var_18]
0x180038f43  mov     rdx, rcx
0x180038f46  mov     rcx, r9
0x180038f49  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@?$vector@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> * const,std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &)
0x180038f4e  mov     rdi, [rbp+var_10]
0x180038f52  test    rdi, rdi
0x180038f55  jz      short loc_180038F60
0x180038f57  mov     rcx, rdi; this
0x180038f5a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180038f5f  nop
0x180038f60  lea     rcx, [rbp+arg_10]
0x180038f64  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x180038f69  inc     esi
0x180038f6b  cmp     esi, dword ptr [rbp+arg_18]
0x180038f6e  jl      loc_180038E95
0x180038f74  mov     rcx, [rbp+arg_0]
0x180038f78  test    rcx, rcx
0x180038f7b  jz      short loc_180038F92
0x180038f7d  mov     [rbp+arg_0], 0
0x180038f85  mov     rax, [rcx]
0x180038f88  mov     rax, [rax+10h]
0x180038f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f91  nop
0x180038f92  mov     rax, r14
0x180038f95  add     rsp, 48h
0x180038f99  pop     r15
0x180038f9b  pop     r14
0x180038f9d  pop     rdi
0x180038f9e  pop     rsi
0x180038f9f  pop     rbx
0x180038fa0  pop     rbp
0x180038fa1  retn
```
