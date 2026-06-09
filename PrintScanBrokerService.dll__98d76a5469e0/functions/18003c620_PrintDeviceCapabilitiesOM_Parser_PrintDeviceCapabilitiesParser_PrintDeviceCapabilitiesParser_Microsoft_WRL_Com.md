# PrintDeviceCapabilitiesOM::Parser::PrintDeviceCapabilitiesParser::PrintDeviceCapabilitiesParser(Microsoft::WRL::ComPtr<IXMLDOMDocument2> &)

- ea: `0x18003c620`
- end: `0x18003c7de`
- name: `??0PrintDeviceCapabilitiesParser@Parser@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@@Z`
- size: `446`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ee54`

## callees

- `0x180002d40`
- `0x180012498`
- `0x1800387fc`
- `0x18003b098`
- `0x18003b7a4`
- `0x18003c620`
- `0x18003e0e0`
- `0x18003e614`
- `0x180040bac`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x18003c68c`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003c6be`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003c6e9`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003c7c0`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
_QWORD *__fastcall PrintDeviceCapabilitiesOM::Parser::PrintDeviceCapabilitiesParser::PrintDeviceCapabilitiesParser(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v4; // r15
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64); // rbx
  PrintCore::BStrRAII *v10; // rax
  _QWORD *v11; // rax
  unsigned int v13; // [rsp+20h] [rbp-68h]
  unsigned int v14; // [rsp+20h] [rbp-68h]
  unsigned int v15; // [rsp+20h] [rbp-68h]
  int v16; // [rsp+30h] [rbp-58h] BYREF
  _QWORD *v17; // [rsp+38h] [rbp-50h]
  void **v18; // [rsp+40h] [rbp-48h] BYREF
  std::_Ref_count_base *v19; // [rsp+48h] [rbp-40h]

  v17 = a1;
  a1[1] = 0;
  a1[2] = 0;
  v4 = (__int64)(a1 + 3);
  a1[3] = 0;
  *a1 = &PrintDeviceCapabilitiesOM::Parser::PrintDeviceCapabilitiesParser::`vftable';
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a2 + 504LL))(*a2, 0);
  PrintCore::ThrowIfError(
    (PrintCore *)v5,
    "Unspecified.",
    "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
    (const char *)0xA2D,
    v13);
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a2 + 544LL))(*a2, 0);
  PrintCore::ThrowIfError(
    (PrintCore *)v6,
    "Unspecified.",
    "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
    (const char *)0xA2E,
    v14);
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a2 + 560LL))(*a2, 0);
  PrintCore::ThrowIfError(
    (PrintCore *)v7,
    "Unspecified.",
    "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
    (const char *)0xA2F,
    v15);
  PrintDeviceCapabilitiesOM::Parser::SetSelectionNamespaces(a2);
  v8 = *a2;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v8 + 296LL);
  v10 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v18, L"psf2:PrintDeviceCapabilities");
  LODWORD(v9) = v9(v8, *((_QWORD *)v10 + 1), v4);
  v18 = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v18);
  if ( (_DWORD)v9 )
  {
    std::wstring::wstring((__int64)&v18, (__int64)L"Root node");
    v16 = 9;
    PrintDeviceCapabilitiesOM::Exception::Throw::Error(
      (unsigned int)&v16,
      (unsigned int)&v18,
      (unsigned int)L"Can't find root \"PrintDeviceCapabilities\" node",
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      2615);
  }
  v11 = std::make_shared<PrintDeviceCapabilitiesOM::NamespaceVault,Microsoft::WRL::ComPtr<IXMLDOMNode> &>(&v18, v4);
  std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(a1 + 1, v11);
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  return a1;
}

```

## disassembly

```asm
0x18003c620  mov     [rsp+arg_10], rbx
0x18003c625  mov     [rsp+arg_18], rsi
0x18003c62a  push    rdi
0x18003c62b  push    r14
0x18003c62d  push    r15
0x18003c62f  sub     rsp, 70h
0x18003c633  mov     rax, cs:__security_cookie
0x18003c63a  xor     rax, rsp
0x18003c63d  mov     [rsp+88h+var_28], rax
0x18003c642  mov     rdi, rdx
0x18003c645  mov     rsi, rcx
0x18003c648  mov     [rsp+88h+var_50], rcx
0x18003c64d  mov     qword ptr [rcx+8], 0
0x18003c655  mov     qword ptr [rcx+10h], 0
0x18003c65d  lea     r15, [rcx+18h]
0x18003c661  mov     qword ptr [r15], 0
0x18003c668  lea     rax, ??_7PrintDeviceCapabilitiesParser@Parser@PrintDeviceCapabilitiesOM@@6B@; const PrintDeviceCapabilitiesOM::Parser::PrintDeviceCapabilitiesParser::`vftable'
0x18003c66f  mov     [rcx], rax
0x18003c672  mov     rcx, [rdx]
0x18003c675  mov     rax, [rcx]
0x18003c678  xor     edx, edx
0x18003c67a  mov     rax, [rax+1F8h]
0x18003c681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c686  mov     r9d, 0A2Dh; char *
0x18003c68c  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003c693  lea     rbx, aUnspecified; "Unspecified."
0x18003c69a  mov     rdx, rbx; char *
0x18003c69d  mov     ecx, eax; this
0x18003c69f  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003c6a4  mov     rcx, [rdi]
0x18003c6a7  mov     rax, [rcx]
0x18003c6aa  xor     edx, edx
0x18003c6ac  mov     rax, [rax+220h]
0x18003c6b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6b8  mov     r9d, 0A2Eh; char *
0x18003c6be  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003c6c5  mov     rdx, rbx; char *
0x18003c6c8  mov     ecx, eax; this
0x18003c6ca  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003c6cf  mov     rcx, [rdi]
0x18003c6d2  mov     rax, [rcx]
0x18003c6d5  xor     edx, edx
0x18003c6d7  mov     rax, [rax+230h]
0x18003c6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6e3  mov     r9d, 0A2Fh; char *
0x18003c6e9  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003c6f0  mov     rdx, rbx; char *
0x18003c6f3  mov     ecx, eax; this
0x18003c6f5  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003c6fa  mov     rcx, rdi
0x18003c6fd  call    ?SetSelectionNamespaces@Parser@PrintDeviceCapabilitiesOM@@YAXAEBV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@@Z; PrintDeviceCapabilitiesOM::Parser::SetSelectionNamespaces(Microsoft::WRL::ComPtr<IXMLDOMDocument2> const &)
0x18003c702  mov     rdi, [rdi]
0x18003c705  mov     rax, [rdi]
0x18003c708  mov     rbx, [rax+128h]
0x18003c70f  lea     rdx, aPsf2Printdevic; "psf2:PrintDeviceCapabilities"
0x18003c716  lea     rcx, [rsp+88h+var_48]; this
0x18003c71b  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x18003c720  nop
0x18003c721  mov     r8, r15
0x18003c724  mov     rdx, [rax+8]
0x18003c728  mov     rcx, rdi
0x18003c72b  mov     rax, rbx
0x18003c72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c733  mov     ebx, eax
0x18003c735  lea     rax, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x18003c73c  mov     [rsp+88h+var_48], rax
0x18003c741  lea     rcx, [rsp+88h+var_48]; this
0x18003c746  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003c74b  test    ebx, ebx
0x18003c74d  jnz     short loc_18003C79E
0x18003c74f  mov     rdx, r15
0x18003c752  lea     rcx, [rsp+88h+var_48]
0x18003c757  call    ??$make_shared@VNamespaceVault@PrintDeviceCapabilitiesOM@@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@std@@YA?AV?$shared_ptr@VNamespaceVault@PrintDeviceCapabilitiesOM@@@0@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z; std::make_shared<PrintDeviceCapabilitiesOM::NamespaceVault,Microsoft::WRL::ComPtr<IXMLDOMNode> &>(Microsoft::WRL::ComPtr<IXMLDOMNode> &)
0x18003c75c  mov     rdx, rax
0x18003c75f  lea     rcx, [rsi+8]
0x18003c763  call    ??4?$shared_ptr@VNamespaceVault@PrintDeviceCapabilitiesOM@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault> &&)
0x18003c768  mov     rcx, [rsp+88h+var_40]; this
0x18003c76d  test    rcx, rcx
0x18003c770  jz      short loc_18003C778
0x18003c772  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003c777  nop
0x18003c778  mov     rax, rsi
0x18003c77b  mov     rcx, [rsp+88h+var_28]
0x18003c780  xor     rcx, rsp; StackCookie
0x18003c783  call    __security_check_cookie
0x18003c788  lea     r11, [rsp+88h+var_18]
0x18003c78d  mov     rbx, [r11+30h]
0x18003c791  mov     rsi, [r11+38h]
0x18003c795  mov     rsp, r11
0x18003c798  pop     r15
0x18003c79a  pop     r14
0x18003c79c  pop     rdi
0x18003c79d  retn
0x18003c79e  lea     rdx, aRootNode; "Root node"
0x18003c7a5  lea     rcx, [rsp+88h+var_48]
0x18003c7aa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003c7af  nop
0x18003c7b0  mov     [rsp+88h+var_58], 9
0x18003c7b8  mov     [rsp+88h+var_68], 0A37h
0x18003c7c0  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003c7c7  lea     r8, aCanTFindRootPr; "Can't find root \"PrintDeviceCapabiliti"...
0x18003c7ce  lea     rdx, [rsp+88h+var_48]
0x18003c7d3  lea     rcx, [rsp+88h+var_58]
0x18003c7d8  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
```
