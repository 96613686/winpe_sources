# PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::Option>(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)

- ea: `0x18003a1f4`
- end: `0x18003a440`
- name: `??$GenericParseMultiple@VOption@PrintDeviceCapabilitiesOM@@@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEAA?AV?$shared_ptr@V?$vector@V?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z`
- size: `588`
- prototype: `_QWORD *(__int64, _QWORD *, __int64 *, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f670`

## callees

- `0x180002d70`
- `0x180038718`
- `0x18003a1f4`
- `0x18003a5f4`
- `0x18003b7a4`
- `0x18003c32c`
- `0x18003e0e0`
- `0x18003f2dc`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x18003a2cd`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003a30a`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003a355`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *PrintDeviceCapabilitiesOM::Parser::GenericParser::GenericParseMultiple<PrintDeviceCapabilitiesOM::Option>(
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
  v10 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v19, L"*[@psf2:psftype='Option']");
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
    v12 = (void **)operator new(0x58u);
    v18[1] = v12;
    *(_OWORD *)v12 = 0;
    *((_DWORD *)v12 + 2) = 1;
    *((_DWORD *)v12 + 3) = 1;
    *v12 = &std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::Option>::`vftable';
    PrintDeviceCapabilitiesOM::Option::Option(v12 + 2, v18, a1);
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
0x18003a1f4  mov     [rsp-38h+arg_18], r9
0x18003a1f9  mov     [rsp-38h+arg_8], rdx
0x18003a1fe  push    rbp
0x18003a1ff  push    rbx
0x18003a200  push    rsi
0x18003a201  push    rdi
0x18003a202  push    r12
0x18003a204  push    r14
0x18003a206  push    r15
0x18003a208  mov     rbp, rsp
0x18003a20b  sub     rsp, 50h
0x18003a20f  mov     rdi, r8
0x18003a212  mov     r14, rdx
0x18003a215  mov     r12, rcx
0x18003a218  mov     [rbp+var_30], 0
0x18003a21f  mov     ecx, 28h ; '('; Size
0x18003a224  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a229  mov     [rbp+var_28], rax
0x18003a22d  xorps   xmm0, xmm0
0x18003a230  movups  xmmword ptr [rax], xmm0
0x18003a233  mov     ecx, 1
0x18003a238  mov     [rax+8], ecx
0x18003a23b  mov     [rax+0Ch], ecx
0x18003a23e  lea     rcx, ??_7?$_Ref_count_obj2@V?$vector@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVPwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble const>>>::`vftable'
0x18003a245  mov     [rax], rcx
0x18003a248  lea     rcx, [rax+10h]
0x18003a24c  mov     qword ptr [rcx], 0
0x18003a253  mov     qword ptr [rcx+8], 0
0x18003a25b  mov     qword ptr [rcx+10h], 0
0x18003a263  mov     [r14], rcx
0x18003a266  mov     [r14+8], rax
0x18003a26a  mov     r15d, 3
0x18003a270  mov     [rbp+var_30], r15d
0x18003a274  mov     [rbp+arg_10], 0
0x18003a27c  mov     rdi, [rdi]
0x18003a27f  mov     rax, [rdi]
0x18003a282  mov     rbx, [rax+120h]
0x18003a289  lea     rdx, aPsf2PsftypeOpt; "*[@psf2:psftype='Option']"
0x18003a290  lea     rcx, [rbp+var_18]; this
0x18003a294  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x18003a299  nop
0x18003a29a  lea     r8, [rbp+arg_10]
0x18003a29e  mov     rdx, [rax+8]
0x18003a2a2  mov     rcx, rdi
0x18003a2a5  mov     rax, rbx
0x18003a2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2ad  mov     ebx, eax
0x18003a2af  lea     rax, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x18003a2b6  mov     [rbp+var_18], rax
0x18003a2ba  lea     rcx, [rbp+var_18]; this
0x18003a2be  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003a2c3  test    ebx, ebx
0x18003a2c5  jz      short loc_18003A2E5
0x18003a2c7  mov     r9d, 10Fh; char *
0x18003a2cd  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003a2d4  lea     rdx, aUnspecified; "Unspecified."
0x18003a2db  mov     ecx, 80040004h; this
0x18003a2e0  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003a2e5  mov     dword ptr [rbp+arg_18], 0
0x18003a2ec  mov     rcx, [rbp+arg_10]
0x18003a2f0  mov     rax, [rcx]
0x18003a2f3  lea     rdx, [rbp+arg_18]
0x18003a2f7  mov     rax, [rax+40h]
0x18003a2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a300  test    eax, eax
0x18003a302  jz      short loc_18003A322
0x18003a304  mov     r9d, 114h; char *
0x18003a30a  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003a311  lea     rdx, aUnspecified; "Unspecified."
0x18003a318  mov     ecx, 80040004h; this
0x18003a31d  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003a322  xor     esi, esi
0x18003a324  cmp     dword ptr [rbp+arg_18], esi
0x18003a327  jle     loc_18003A40F
0x18003a32d  mov     [rbp+var_28], 0
0x18003a335  mov     rcx, [rbp+arg_10]
0x18003a339  mov     rax, [rcx]
0x18003a33c  lea     r8, [rbp+var_28]
0x18003a340  mov     edx, esi
0x18003a342  mov     rax, [rax+38h]
0x18003a346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a34b  test    eax, eax
0x18003a34d  jz      short loc_18003A36D
0x18003a34f  mov     r9d, 11Bh; char *
0x18003a355  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003a35c  lea     rdx, aUnspecified; "Unspecified."
0x18003a363  mov     ecx, 80040004h; this
0x18003a368  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003a36d  mov     ecx, 58h ; 'X'; Size
0x18003a372  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a377  mov     rdi, rax
0x18003a37a  mov     [rbp+var_20], rax
0x18003a37e  xorps   xmm0, xmm0
0x18003a381  movups  xmmword ptr [rax], xmm0
0x18003a384  mov     eax, 1
0x18003a389  mov     [rdi+8], eax
0x18003a38c  mov     [rdi+0Ch], eax
0x18003a38f  lea     rax, ??_7?$_Ref_count_obj2@VOption@PrintDeviceCapabilitiesOM@@@std@@6B@; const std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::Option>::`vftable'
0x18003a396  mov     [rdi], rax
0x18003a399  lea     rbx, [rdi+10h]
0x18003a39d  mov     r8, r12
0x18003a3a0  lea     rdx, [rbp+var_28]
0x18003a3a4  mov     rcx, rbx
0x18003a3a7  call    ??0Option@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z; PrintDeviceCapabilitiesOM::Option::Option(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)
0x18003a3ac  nop
0x18003a3ad  or      r15d, 4
0x18003a3b1  mov     [rbp+var_30], r15d
0x18003a3b5  mov     [rbp+var_18], rbx
0x18003a3b9  mov     [rbp+var_10], rdi
0x18003a3bd  mov     r9, [r14]
0x18003a3c0  mov     rcx, [r9+8]
0x18003a3c4  cmp     rcx, [r9+10h]
0x18003a3c8  jz      short loc_18003A3DA
0x18003a3ca  lea     rdx, [rbp+var_18]
0x18003a3ce  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003a3d3  add     qword ptr [r9+8], 10h
0x18003a3d8  jmp     short loc_18003A3ED
0x18003a3da  lea     r8, [rbp+var_18]
0x18003a3de  mov     rdx, rcx
0x18003a3e1  mov     rcx, r9
0x18003a3e4  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@?$vector@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVParameterDef@PrintDeviceCapabilitiesOM@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const>>::_Emplace_reallocate<std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &>(std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> * const,std::shared_ptr<PrintDeviceCapabilitiesOM::ParameterDef const> const &)
0x18003a3e9  mov     rdi, [rbp+var_10]
0x18003a3ed  test    rdi, rdi
0x18003a3f0  jz      short loc_18003A3FB
0x18003a3f2  mov     rcx, rdi; this
0x18003a3f5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003a3fa  nop
0x18003a3fb  lea     rcx, [rbp+var_28]
0x18003a3ff  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x18003a404  inc     esi
0x18003a406  cmp     esi, dword ptr [rbp+arg_18]
0x18003a409  jl      loc_18003A32D
0x18003a40f  mov     rcx, [rbp+arg_10]
0x18003a413  test    rcx, rcx
0x18003a416  jz      short loc_18003A42D
0x18003a418  mov     [rbp+arg_10], 0
0x18003a420  mov     rax, [rcx]
0x18003a423  mov     rax, [rax+10h]
0x18003a427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a42c  nop
0x18003a42d  mov     rax, r14
0x18003a430  add     rsp, 50h
0x18003a434  pop     r15
0x18003a436  pop     r14
0x18003a438  pop     r12
0x18003a43a  pop     rdi
0x18003a43b  pop     rsi
0x18003a43c  pop     rbx
0x18003a43d  pop     rbp
0x18003a43e  retn
```
