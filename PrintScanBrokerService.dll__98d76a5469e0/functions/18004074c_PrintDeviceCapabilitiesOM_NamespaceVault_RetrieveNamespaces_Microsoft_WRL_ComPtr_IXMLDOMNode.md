# PrintDeviceCapabilitiesOM::NamespaceVault::RetrieveNamespaces(Microsoft::WRL::ComPtr<IXMLDOMNode> &)

- ea: `0x18004074c`
- end: `0x180040ba6`
- name: `?RetrieveNamespaces@NamespaceVault@PrintDeviceCapabilitiesOM@@AEAAXAEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z`
- size: `1114`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c248`

## callees

- `0x180002d40`
- `0x180002d70`
- `0x18000f8a8`
- `0x180012498`
- `0x18003470c`
- `0x180036044`
- `0x180038718`
- `0x1800387fc`
- `0x18003b7a4`
- `0x18003d8d8`
- `0x18003e008`
- `0x18003e0e0`
- `0x18003e10c`
- `0x18003e614`
- `0x18003f2dc`
- `0x18004074c`
- `0x180040d3c`
- `0x1800421e0`
- `0x1800425d8`
- `0x180048010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180040866`
- `OLEAUT32!__imp_VariantInit` at `0x180040866`
- `OLEAUT32!__imp_VariantClear` at `0x180040b04`
- `OLEAUT32!__imp_VariantClear` at `0x180040b04`

## string_xrefs

- `0x1800407f8`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOMTypes.hxx`
- `0x18004084a`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOMTypes.hxx`
- `0x18004088c`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOMTypes.hxx`
- `0x1800408b1`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOMTypes.hxx`
- `0x18004092c`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOMTypes.hxx`
- `0x180040b89`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOMTypes.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall PrintDeviceCapabilitiesOM::NamespaceVault::RetrieveNamespaces(__int64 a1, __int64 *a2)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, _QWORD, __int64 *); // rbx
  PrintCore::BStrRAII *v5; // rax
  unsigned int i; // r14d
  __int64 v7; // rax
  __int64 v8; // rdi
  unsigned int (__fastcall *v9)(__int64, __int64 *); // rbx
  __int64 v10; // rax
  std::_Ref_count_base *v11; // rdi
  __int64 v12; // rbx
  _DWORD *v13; // rax
  _QWORD *v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  void **v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  void **v22; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v23; // [rsp+60h] [rbp-A0h]
  _DWORD *v24; // [rsp+68h] [rbp-98h]
  _DWORD *v25; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v26; // [rsp+78h] [rbp-88h]
  _DWORD *v27; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v28; // [rsp+88h] [rbp-78h]
  VARIANTARG pvarg; // [rsp+90h] [rbp-70h] BYREF
  std::_Ref_count_base *v30; // [rsp+A8h] [rbp-58h]
  __int64 v31; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v32; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v33[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v34[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v35[32]; // [rsp+110h] [rbp+10h] BYREF

  v19 = 0;
  v3 = *a2;
  v4 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a2 + 288LL);
  v5 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v22, L"namespace::node()");
  LODWORD(v4) = v4(v3, *((_QWORD *)v5 + 1), &v19);
  v22 = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v22);
  if ( (_DWORD)v4 )
  {
    std::wstring::wstring((__int64)v34, (__int64)L"Root Node");
    LODWORD(v18) = 11;
    PrintDeviceCapabilitiesOM::Exception::Throw::Error(
      (unsigned int)&v18,
      (unsigned int)v34,
      (unsigned int)L"Namespaces not defined",
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOMTypes.hxx",
      839);
  }
  v17 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 64LL))(v19, &v17) )
    PrintCore::ThrowIfError(
      (PrintCore *)0x80040004LL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOMTypes.hxx",
      (const char *)0x34C,
      v16);
  for ( i = 0; (int)i < v17; ++i )
  {
    v18 = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 56LL))(v19, i, &v18) )
      PrintCore::ThrowIfError(
        (PrintCore *)0x80040004LL,
        "Unspecified.",
        "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOMTypes.hxx",
        (const char *)0x352,
        v16);
    VariantInit(&pvarg);
    if ( (*(unsigned int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v18 + 64LL))(v18, &pvarg) )
      PrintCore::ThrowIfError(
        (PrintCore *)0x80040004LL,
        "Unspecified.",
        "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOMTypes.hxx",
        (const char *)0x356,
        v16);
    if ( pvarg.vt != 8 )
      PrintCore::ThrowIfError(
        (PrintCore *)0x80004005LL,
        "Internal error",
        "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOMTypes.hxx",
        (const char *)0x35A,
        v16);
    v7 = std::wstring::wstring((__int64)v33, pvarg.llVal);
    PrintDeviceCapabilitiesOM::NamespaceUri::Create(&v22, v7);
    std::wstring::_Tidy_deallocate(v33);
    v20 = &PrintCore::BStrRAII::`vftable';
    v21 = 0;
    v8 = v18;
    v9 = *(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 56LL);
    PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v20);
    if ( v9(v8, &v21) )
      PrintCore::ThrowIfError(
        (PrintCore *)0x80040004LL,
        "Unspecified.",
        "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOMTypes.hxx",
        (const char *)0x361,
        v16);
    std::wstring::wstring((__int64)v34, v21);
    *(_OWORD *)v33 = 0;
    v10 = std::wstring::find(v34, 58, 0);
    if ( v10 == -1 )
    {
      v11 = (std::_Ref_count_base *)operator new(0x30u);
      v30 = v11;
      *(_OWORD *)v11 = 0;
      *((_DWORD *)v11 + 2) = 1;
      *((_DWORD *)v11 + 3) = 1;
      *(_QWORD *)v11 = &std::_Ref_count_obj2<std::wstring>::`vftable';
      std::wstring::wstring((char *)v11 + 16, v34);
      v25 = (_DWORD *)((char *)v11 + 16);
      v26 = v11;
      std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(v33, (__int64 *)&v25);
      if ( v26 )
        std::_Ref_count_base::_Decref(v26);
      std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::operator=(a1 + 48, &v22);
    }
    else
    {
      v12 = std::wstring::substr(v34, v35, v10 + 1, -1);
      v13 = operator new(0x30u);
      v24 = v13;
      *(_OWORD *)v13 = 0;
      v13[2] = 1;
      v13[3] = 1;
      *(_QWORD *)v13 = &std::_Ref_count_obj2<std::wstring>::`vftable';
      *((_OWORD *)v13 + 1) = 0;
      *((_QWORD *)v13 + 4) = 0;
      *((_QWORD *)v13 + 5) = 0;
      *((_OWORD *)v13 + 1) = *(_OWORD *)v12;
      *((_OWORD *)v13 + 2) = *(_OWORD *)(v12 + 16);
      *(_QWORD *)(v12 + 16) = 0;
      *(_QWORD *)(v12 + 24) = 7;
      *(_WORD *)v12 = 0;
      v27 = v13 + 4;
      v28 = (std::_Ref_count_base *)v13;
      std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(v33, (__int64 *)&v27);
      if ( v28 )
        std::_Ref_count_base::_Decref(v28);
      std::wstring::_Tidy_deallocate(v35);
      std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(&v31, &v22);
      v14 = std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(&v32, v33);
      PrintDeviceCapabilitiesOM::NamespaceVault::AddToVault(a1, v14);
    }
    if ( v33[1] )
      std::_Ref_count_base::_Decref(v33[1]);
    std::wstring::_Tidy_deallocate(v34);
    v20 = &PrintCore::BStrRAII::`vftable';
    PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v20);
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    VariantClear(&pvarg);
    Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(&v18);
  }
  v15 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
}

```

## disassembly

```asm
0x18004074c  mov     [rsp-8+arg_10], rbx
0x180040751  mov     [rsp-8+arg_18], rdi
0x180040756  push    rbp
0x180040757  push    r14
0x180040759  push    r15
0x18004075b  lea     rbp, [rsp-40h]
0x180040760  sub     rsp, 140h
0x180040767  mov     rax, cs:__security_cookie
0x18004076e  xor     rax, rsp
0x180040771  mov     [rbp+50h+var_20], rax
0x180040775  mov     r15, rcx
0x180040778  mov     [rsp+150h+var_110], 0
0x180040781  mov     rdi, [rdx]
0x180040784  mov     rax, [rdi]
0x180040787  mov     rbx, [rax+120h]
0x18004078e  lea     rdx, aNamespaceNode; "namespace::node()"
0x180040795  lea     rcx, [rsp+150h+var_F8]; this
0x18004079a  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x18004079f  nop
0x1800407a0  lea     r8, [rsp+150h+var_110]
0x1800407a5  mov     rdx, [rax+8]
0x1800407a9  mov     rcx, rdi
0x1800407ac  mov     rax, rbx
0x1800407af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407b4  mov     ebx, eax
0x1800407b6  lea     rdi, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x1800407bd  mov     [rsp+150h+var_F8], rdi
0x1800407c2  lea     rcx, [rsp+150h+var_F8]; this
0x1800407c7  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x1800407cc  test    ebx, ebx
0x1800407ce  jnz     loc_180040B68
0x1800407d4  mov     [rsp+150h+var_120], ebx
0x1800407d8  mov     rcx, [rsp+150h+var_110]
0x1800407dd  mov     rax, [rcx]
0x1800407e0  lea     rdx, [rsp+150h+var_120]
0x1800407e5  mov     rax, [rax+40h]
0x1800407e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407ee  test    eax, eax
0x1800407f0  jz      short loc_180040810
0x1800407f2  mov     r9d, 34Ch; char *
0x1800407f8  lea     r8, aOnecoreuapInte_4; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800407ff  lea     rdx, aUnspecified; "Unspecified."
0x180040806  mov     ecx, 80040004h; this
0x18004080b  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180040810  xor     r14d, r14d
0x180040813  cmp     [rsp+150h+var_120], r14d
0x180040818  jle     loc_180040B23
0x18004081e  mov     [rsp+150h+var_118], 0
0x180040827  mov     rcx, [rsp+150h+var_110]
0x18004082c  mov     rax, [rcx]
0x18004082f  lea     r8, [rsp+150h+var_118]
0x180040834  mov     edx, r14d
0x180040837  mov     rax, [rax+38h]
0x18004083b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040840  test    eax, eax
0x180040842  jz      short loc_180040862
0x180040844  mov     r9d, 352h; char *
0x18004084a  lea     r8, aOnecoreuapInte_4; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180040851  lea     rdx, aUnspecified; "Unspecified."
0x180040858  mov     ecx, 80040004h; this
0x18004085d  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180040862  lea     rcx, [rbp+50h+pvarg]; pvarg
0x180040866  call    cs:__imp_VariantInit
0x18004086c  nop
0x18004086d  mov     rcx, [rsp+150h+var_118]
0x180040872  mov     rax, [rcx]
0x180040875  lea     rdx, [rbp+50h+pvarg]
0x180040879  mov     rax, [rax+40h]
0x18004087d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040882  test    eax, eax
0x180040884  jz      short loc_1800408A4
0x180040886  mov     r9d, 356h; char *
0x18004088c  lea     r8, aOnecoreuapInte_4; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180040893  lea     rdx, aUnspecified; "Unspecified."
0x18004089a  mov     ecx, 80040004h; this
0x18004089f  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x1800408a4  cmp     word ptr [rbp+50h+pvarg], 8
0x1800408a9  jz      short loc_1800408C9
0x1800408ab  mov     r9d, 35Ah; char *
0x1800408b1  lea     r8, aOnecoreuapInte_4; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800408b8  lea     rdx, aInternalError; "Internal error"
0x1800408bf  mov     ecx, 80004005h; this
0x1800408c4  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x1800408c9  mov     rdx, qword ptr [rbp+50h+pvarg+8]
0x1800408cd  lea     rcx, [rbp+50h+var_80]
0x1800408d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800408d6  nop
0x1800408d7  mov     rdx, rax
0x1800408da  lea     rcx, [rsp+150h+var_F8]
0x1800408df  call    ?Create@NamespaceUri@PrintDeviceCapabilitiesOM@@SA?AV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; PrintDeviceCapabilitiesOM::NamespaceUri::Create(std::wstring const &)
0x1800408e4  nop
0x1800408e5  lea     rcx, [rbp+50h+var_80]
0x1800408e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800408ee  mov     [rsp+150h+var_108], rdi
0x1800408f3  mov     [rsp+150h+var_100], 0
0x1800408fc  mov     rdi, [rsp+150h+var_118]
0x180040901  mov     rax, [rdi]
0x180040904  mov     rbx, [rax+38h]
0x180040908  lea     rcx, [rsp+150h+var_108]; this
0x18004090d  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x180040912  lea     rdx, [rsp+150h+var_100]
0x180040917  mov     rcx, rdi
0x18004091a  mov     rax, rbx
0x18004091d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040922  test    eax, eax
0x180040924  jz      short loc_180040944
0x180040926  mov     r9d, 361h; char *
0x18004092c  lea     r8, aOnecoreuapInte_4; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180040933  lea     rdx, aUnspecified; "Unspecified."
0x18004093a  mov     ecx, 80040004h; this
0x18004093f  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180040944  mov     rdx, [rsp+150h+var_100]
0x180040949  lea     rcx, [rbp+50h+var_60]
0x18004094d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180040952  nop
0x180040953  xorps   xmm0, xmm0
0x180040956  movdqu  xmmword ptr [rbp+50h+var_80], xmm0
0x18004095b  mov     edx, 3Ah ; ':'
0x180040960  xor     r8d, r8d
0x180040963  lea     rcx, [rbp+50h+var_60]
0x180040967  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x18004096c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180040970  jnz     short loc_1800409E7
0x180040972  lea     ecx, [rax+31h]; Size
0x180040975  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004097a  mov     rdi, rax
0x18004097d  mov     [rbp+50h+var_A8], rax
0x180040981  xorps   xmm0, xmm0
0x180040984  movups  xmmword ptr [rax], xmm0
0x180040987  mov     eax, 1
0x18004098c  mov     [rdi+8], eax
0x18004098f  mov     [rdi+0Ch], eax
0x180040992  lea     rax, ??_7?$_Ref_count_obj2@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::wstring>::`vftable'
0x180040999  mov     [rdi], rax
0x18004099c  lea     rbx, [rdi+10h]
0x1800409a0  lea     rdx, [rbp+50h+var_60]
0x1800409a4  mov     rcx, rbx
0x1800409a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800409ac  nop
0x1800409ad  mov     [rsp+150h+var_E0], rbx
0x1800409b2  mov     [rsp+150h+var_D8], rdi
0x1800409b7  lea     rdx, [rsp+150h+var_E0]
0x1800409bc  lea     rcx, [rbp+50h+var_80]
0x1800409c0  call    ??4?$shared_ptr@VNamespaceVault@PrintDeviceCapabilitiesOM@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault> &&)
0x1800409c5  mov     rcx, [rsp+150h+var_D8]; this
0x1800409ca  test    rcx, rcx
0x1800409cd  jz      short loc_1800409D4
0x1800409cf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800409d4  lea     rcx, [r15+30h]
0x1800409d8  lea     rdx, [rsp+150h+var_F8]
0x1800409dd  call    ??4?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::operator=(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x1800409e2  jmp     loc_180040AC0
0x1800409e7  lea     r8, [rax+1]
0x1800409eb  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800409ef  lea     rdx, [rbp+50h+var_40]
0x1800409f3  lea     rcx, [rbp+50h+var_60]
0x1800409f7  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800409fc  mov     rbx, rax
0x1800409ff  mov     ecx, 30h ; '0'; Size
0x180040a04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040a09  mov     rdx, rax
0x180040a0c  mov     [rsp+150h+var_E8], rax
0x180040a11  xorps   xmm0, xmm0
0x180040a14  movups  xmmword ptr [rax], xmm0
0x180040a17  mov     dword ptr [rax+8], 1
0x180040a1e  mov     dword ptr [rax+0Ch], 1
0x180040a25  lea     rax, ??_7?$_Ref_count_obj2@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::wstring>::`vftable'
0x180040a2c  mov     [rdx], rax
0x180040a2f  lea     rcx, [rdx+10h]
0x180040a33  movups  xmmword ptr [rcx], xmm0
0x180040a36  mov     qword ptr [rcx+10h], 0
0x180040a3e  mov     qword ptr [rcx+18h], 0
0x180040a46  movups  xmm0, xmmword ptr [rbx]
0x180040a49  movups  xmmword ptr [rcx], xmm0
0x180040a4c  movups  xmm1, xmmword ptr [rbx+10h]
0x180040a50  movups  xmmword ptr [rcx+10h], xmm1
0x180040a54  mov     qword ptr [rbx+10h], 0
0x180040a5c  mov     qword ptr [rbx+18h], 7
0x180040a64  xor     eax, eax
0x180040a66  mov     [rbx], ax
0x180040a69  mov     [rbp+50h+var_D0], rcx
0x180040a6d  mov     [rbp+50h+var_C8], rdx
0x180040a71  lea     rdx, [rbp+50h+var_D0]
0x180040a75  lea     rcx, [rbp+50h+var_80]
0x180040a79  call    ??4?$shared_ptr@VNamespaceVault@PrintDeviceCapabilitiesOM@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault> &&)
0x180040a7e  mov     rcx, [rbp+50h+var_C8]; this
0x180040a82  test    rcx, rcx
0x180040a85  jz      short loc_180040A8D
0x180040a87  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180040a8c  nop
0x180040a8d  lea     rcx, [rbp+50h+var_40]
0x180040a91  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040a96  lea     rdx, [rsp+150h+var_F8]
0x180040a9b  lea     rcx, [rbp+50h+var_A0]
0x180040a9f  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x180040aa4  mov     r8, rax
0x180040aa7  lea     rdx, [rbp+50h+var_80]
0x180040aab  lea     rcx, [rbp+50h+var_90]
0x180040aaf  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x180040ab4  mov     rdx, rax
0x180040ab7  mov     rcx, r15
0x180040aba  call    ?AddToVault@NamespaceVault@PrintDeviceCapabilitiesOM@@QEAAXV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@4@@Z; PrintDeviceCapabilitiesOM::NamespaceVault::AddToVault(std::shared_ptr<std::wstring>,std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceUri const>)
0x180040abf  nop
0x180040ac0  mov     rcx, [rbp+50h+var_80+8]; this
0x180040ac4  test    rcx, rcx
0x180040ac7  jz      short loc_180040ACF
0x180040ac9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180040ace  nop
0x180040acf  lea     rcx, [rbp+50h+var_60]
0x180040ad3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040ad8  nop
0x180040ad9  lea     rdi, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x180040ae0  mov     [rsp+150h+var_108], rdi
0x180040ae5  lea     rcx, [rsp+150h+var_108]; this
0x180040aea  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x180040aef  nop
0x180040af0  mov     rcx, [rsp+150h+var_F0]; this
0x180040af5  test    rcx, rcx
0x180040af8  jz      short loc_180040B00
0x180040afa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180040aff  nop
0x180040b00  lea     rcx, [rbp+50h+pvarg]; pvarg
0x180040b04  call    cs:__imp_VariantClear
0x180040b0a  nop
0x180040b0b  lea     rcx, [rsp+150h+var_118]
0x180040b10  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x180040b15  inc     r14d
0x180040b18  cmp     r14d, [rsp+150h+var_120]
0x180040b1d  jl      loc_18004081E
0x180040b23  mov     rcx, [rsp+150h+var_110]
0x180040b28  test    rcx, rcx
0x180040b2b  jz      short loc_180040B43
0x180040b2d  mov     [rsp+150h+var_110], 0
0x180040b36  mov     rax, [rcx]
0x180040b39  mov     rax, [rax+10h]
0x180040b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b42  nop
0x180040b43  mov     rcx, [rbp+50h+var_20]
0x180040b47  xor     rcx, rsp; StackCookie
0x180040b4a  call    __security_check_cookie
0x180040b4f  lea     r11, [rsp+150h+var_10]
0x180040b57  mov     rbx, [r11+30h]
0x180040b5b  mov     rdi, [r11+38h]
0x180040b5f  mov     rsp, r11
0x180040b62  pop     r15
0x180040b64  pop     r14
0x180040b66  pop     rbp
0x180040b67  retn
0x180040b68  lea     rdx, aRootNode_0; "Root Node"
0x180040b6f  lea     rcx, [rbp+50h+var_60]
0x180040b73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180040b78  nop
0x180040b79  mov     dword ptr [rsp+150h+var_118], 0Bh
0x180040b81  mov     [rsp+150h+var_130], 347h
0x180040b89  lea     r9, aOnecoreuapInte_4; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180040b90  lea     r8, aNamespacesNotD; "Namespaces not defined"
0x180040b97  lea     rdx, [rbp+50h+var_60]
0x180040b9b  lea     rcx, [rsp+150h+var_118]
0x180040ba0  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
```
