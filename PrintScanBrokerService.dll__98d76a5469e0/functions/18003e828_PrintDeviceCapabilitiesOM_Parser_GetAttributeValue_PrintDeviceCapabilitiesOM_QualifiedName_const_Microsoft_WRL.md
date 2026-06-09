# PrintDeviceCapabilitiesOM::Parser::GetAttributeValue(PrintDeviceCapabilitiesOM::QualifiedName const &,Microsoft::WRL::ComPtr<IXMLDOMNode> &)

- ea: `0x18003e828`
- end: `0x18003ea25`
- name: `?GetAttributeValue@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBVQualifiedName@2@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z`
- size: `509`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b7f4`
- `0x18003bb30`
- `0x18003bfd4`
- `0x18003c428`
- `0x18003cadc`
- `0x18003cc3c`
- `0x18003e53c`
- `0x18003faa4`

## callees

- `0x180038718`
- `0x18003ae84`
- `0x18003b7a4`
- `0x18003e0e0`
- `0x18003e828`
- `0x18003f2dc`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x18003e87d`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003e9b5`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall PrintDeviceCapabilitiesOM::Parser::GetAttributeValue(_QWORD *a1, _QWORD *a2, __int64 *a3)
{
  __int64 v5; // rdi
  unsigned int (__fastcall *v6)(__int64, __int64 *); // rbx
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64, __int64 *); // r15
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rdi
  const unsigned __int16 *v11; // rdx
  PrintCore::BStrRAII *v12; // rax
  int v13; // ebx
  __int64 v14; // rdi
  unsigned int (__fastcall *v15)(__int64, __int64 *); // rbx
  unsigned int v17; // [rsp+20h] [rbp-49h]
  void **v18; // [rsp+38h] [rbp-31h] BYREF
  __int64 v19; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v20[2]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v21; // [rsp+58h] [rbp-11h] BYREF
  std::_Ref_count_base *v22; // [rsp+60h] [rbp-9h]
  _QWORD v23[2]; // [rsp+68h] [rbp-1h] BYREF
  __int64 v24; // [rsp+78h] [rbp+Fh] BYREF
  std::_Ref_count_base *v25; // [rsp+80h] [rbp+17h]
  _QWORD *v26; // [rsp+88h] [rbp+1Fh] BYREF
  std::_Ref_count_base *v27; // [rsp+90h] [rbp+27h]
  __int64 v28; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+E0h] [rbp+77h] BYREF

  v29 = 0;
  v5 = *a3;
  v6 = *(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a3 + 136LL);
  Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(&v29);
  if ( v6(v5, &v29) )
    PrintCore::ThrowIfError(
      (PrintCore *)0x80040004LL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x37,
      v17);
  v28 = 0;
  v7 = v29;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v29 + 96LL);
  Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(&v28);
  std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(&v26, a2 + 2);
  std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(&v24, v26);
  v9 = (const unsigned __int16 *)v24;
  if ( *(_QWORD *)(v24 + 24) > 7u )
    v9 = *(const unsigned __int16 **)v24;
  v10 = *((_QWORD *)PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)v23, v9) + 1);
  std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(&v21, a2);
  v11 = (const unsigned __int16 *)v21;
  if ( *(_QWORD *)(v21 + 24) > 7u )
    v11 = *(const unsigned __int16 **)v21;
  v12 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)v20, v11);
  v13 = v8(v7, *((_QWORD *)v12 + 1), v10, &v28);
  v20[0] = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)v20);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  v23[0] = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)v23);
  if ( v25 )
    std::_Ref_count_base::_Decref(v25);
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  v18 = &PrintCore::BStrRAII::`vftable';
  v19 = 0;
  if ( v13 )
  {
    *a1 = 0;
    a1[1] = 0;
  }
  else
  {
    v14 = v28;
    v15 = *(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 208LL);
    PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v18);
    if ( v15(v14, &v19) )
      PrintCore::ThrowIfError(
        (PrintCore *)0x80040004LL,
        "Unspecified.",
        "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
        (const char *)0x45,
        v17);
    std::make_shared<std::wstring,PrintCore::BStrRAII &>(a1, &v18);
  }
  v18 = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v18);
  Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(&v29);
  return a1;
}

```

## disassembly

```asm
0x18003e828  mov     [rsp-8+arg_0], rbx
0x18003e82d  push    rbp
0x18003e82e  push    rsi
0x18003e82f  push    rdi
0x18003e830  push    r14
0x18003e832  push    r15
0x18003e834  lea     rbp, [rsp-37h]
0x18003e839  sub     rsp, 0A0h
0x18003e840  mov     r14, rdx
0x18003e843  mov     rsi, rcx
0x18003e846  mov     [rbp+57h+arg_10], 0
0x18003e84e  mov     rdi, [r8]
0x18003e851  mov     rax, [rdi]
0x18003e854  mov     rbx, [rax+88h]
0x18003e85b  lea     rcx, [rbp+57h+arg_10]
0x18003e85f  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x18003e864  lea     rdx, [rbp+57h+arg_10]
0x18003e868  mov     rcx, rdi
0x18003e86b  mov     rax, rbx
0x18003e86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e873  test    eax, eax
0x18003e875  jz      short loc_18003E895
0x18003e877  mov     r9d, 37h ; '7'; char *
0x18003e87d  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003e884  lea     rdx, aUnspecified; "Unspecified."
0x18003e88b  mov     ecx, 80040004h; this
0x18003e890  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003e895  mov     [rbp+57h+arg_8], 0
0x18003e89d  mov     rbx, [rbp+57h+arg_10]
0x18003e8a1  mov     rax, [rbx]
0x18003e8a4  mov     r15, [rax+60h]
0x18003e8a8  lea     rcx, [rbp+57h+arg_8]
0x18003e8ac  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x18003e8b1  lea     rdx, [r14+10h]
0x18003e8b5  lea     rcx, [rbp+57h+var_38]
0x18003e8b9  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003e8be  nop
0x18003e8bf  mov     rdx, [rbp+57h+var_38]
0x18003e8c3  lea     rcx, [rbp+57h+var_48]
0x18003e8c7  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003e8cc  nop
0x18003e8cd  mov     rdx, [rbp+57h+var_48]
0x18003e8d1  cmp     qword ptr [rdx+18h], 7
0x18003e8d6  jbe     short loc_18003E8DB
0x18003e8d8  mov     rdx, [rdx]; unsigned __int16 *
0x18003e8db  lea     rcx, [rbp+57h+var_58]; this
0x18003e8df  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x18003e8e4  nop
0x18003e8e5  mov     rdi, [rax+8]
0x18003e8e9  mov     rdx, r14
0x18003e8ec  lea     rcx, [rbp+57h+var_68]
0x18003e8f0  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003e8f5  nop
0x18003e8f6  mov     rdx, [rbp+57h+var_68]
0x18003e8fa  cmp     qword ptr [rdx+18h], 7
0x18003e8ff  jbe     short loc_18003E904
0x18003e901  mov     rdx, [rdx]; unsigned __int16 *
0x18003e904  lea     rcx, [rbp+57h+var_78]; this
0x18003e908  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x18003e90d  nop
0x18003e90e  lea     r9, [rbp+57h+arg_8]
0x18003e912  mov     r8, rdi
0x18003e915  mov     rdx, [rax+8]
0x18003e919  mov     rcx, rbx
0x18003e91c  mov     rax, r15
0x18003e91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e924  mov     ebx, eax
0x18003e926  lea     r14, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x18003e92d  mov     [rbp+57h+var_78], r14
0x18003e931  lea     rcx, [rbp+57h+var_78]; this
0x18003e935  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003e93a  nop
0x18003e93b  mov     rcx, [rbp+57h+var_60]; this
0x18003e93f  test    rcx, rcx
0x18003e942  jz      short loc_18003E94A
0x18003e944  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e949  nop
0x18003e94a  mov     [rbp+57h+var_58], r14
0x18003e94e  lea     rcx, [rbp+57h+var_58]; this
0x18003e952  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003e957  nop
0x18003e958  mov     rcx, [rbp+57h+var_40]; this
0x18003e95c  test    rcx, rcx
0x18003e95f  jz      short loc_18003E967
0x18003e961  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e966  nop
0x18003e967  mov     rcx, [rbp+57h+var_30]; this
0x18003e96b  test    rcx, rcx
0x18003e96e  jz      short loc_18003E975
0x18003e970  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e975  mov     [rbp+57h+var_88], r14
0x18003e979  mov     [rbp+57h+var_80], 0
0x18003e981  test    ebx, ebx
0x18003e983  jnz     short loc_18003E9DB
0x18003e985  mov     rdi, [rbp+57h+arg_8]
0x18003e989  mov     rax, [rdi]
0x18003e98c  mov     rbx, [rax+0D0h]
0x18003e993  lea     rcx, [rbp+57h+var_88]; this
0x18003e997  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003e99c  lea     rdx, [rbp+57h+var_80]
0x18003e9a0  mov     rcx, rdi
0x18003e9a3  mov     rax, rbx
0x18003e9a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9ab  test    eax, eax
0x18003e9ad  jz      short loc_18003E9CD
0x18003e9af  mov     r9d, 45h ; 'E'; char *
0x18003e9b5  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003e9bc  lea     rdx, aUnspecified; "Unspecified."
0x18003e9c3  mov     ecx, 80040004h; this
0x18003e9c8  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003e9cd  lea     rdx, [rbp+57h+var_88]
0x18003e9d1  mov     rcx, rsi
0x18003e9d4  call    ??$make_shared@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVBStrRAII@PrintCore@@@std@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@AEAVBStrRAII@PrintCore@@@Z; std::make_shared<std::wstring,PrintCore::BStrRAII &>(PrintCore::BStrRAII &)
0x18003e9d9  jmp     short loc_18003E9EA
0x18003e9db  mov     qword ptr [rsi], 0
0x18003e9e2  mov     qword ptr [rsi+8], 0
0x18003e9ea  mov     [rbp+57h+var_88], r14
0x18003e9ee  lea     rcx, [rbp+57h+var_88]; this
0x18003e9f2  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003e9f7  nop
0x18003e9f8  lea     rcx, [rbp+57h+arg_8]
0x18003e9fc  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x18003ea01  nop
0x18003ea02  lea     rcx, [rbp+57h+arg_10]
0x18003ea06  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x18003ea0b  mov     rax, rsi
0x18003ea0e  mov     rbx, [rsp+0C0h+arg_0]
0x18003ea16  add     rsp, 0A0h
0x18003ea1d  pop     r15
0x18003ea1f  pop     r14
0x18003ea21  pop     rdi
0x18003ea22  pop     rsi
0x18003ea23  pop     rbp
0x18003ea24  retn
```
