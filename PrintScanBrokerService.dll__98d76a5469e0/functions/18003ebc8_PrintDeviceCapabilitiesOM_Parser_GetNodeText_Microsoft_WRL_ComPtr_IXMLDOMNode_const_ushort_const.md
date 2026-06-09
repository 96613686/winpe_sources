# PrintDeviceCapabilitiesOM::Parser::GetNodeText(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)

- ea: `0x18003ebc8`
- end: `0x18003ed0f`
- name: `?GetNodeText@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b7f4`
- `0x18003bb30`
- `0x18003cadc`
- `0x18003cc3c`
- `0x18003f510`
- `0x18003f830`

## callees

- `0x18003ae84`
- `0x18003b7a4`
- `0x18003e0e0`
- `0x18003ebc8`
- `0x18003f2b8`
- `0x18003f2dc`
- `0x180040d3c`
- `0x180048010`

## string_xrefs

- `0x18003ec9c`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall PrintDeviceCapabilitiesOM::Parser::GetNodeText(_QWORD *a1, __int64 *a2, const unsigned __int16 *a3)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _QWORD, __int64 *); // rbx
  PrintCore::BStrRAII *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, __int64 *); // rdi
  unsigned int v10; // eax
  unsigned int v12; // [rsp+20h] [rbp-20h]
  void **v13; // [rsp+28h] [rbp-18h] BYREF
  __int64 v14; // [rsp+30h] [rbp-10h] BYREF
  __int64 v15; // [rsp+70h] [rbp+30h] BYREF
  __int64 v16; // [rsp+78h] [rbp+38h] BYREF

  v15 = 0;
  if ( a3 )
  {
    v4 = *a2;
    v5 = *(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a2 + 296LL);
    v6 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v13, a3);
    v5(v4, *((_QWORD *)v6 + 1), &v15);
    v13 = &PrintCore::BStrRAII::`vftable';
    PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v13);
  }
  else
  {
    v7 = *a2;
    if ( !*a2 )
    {
LABEL_9:
      *a1 = 0;
      a1[1] = 0;
      goto LABEL_10;
    }
    v16 = *a2;
    Microsoft::WRL::ComPtr<IXMLDOMNode>::InternalAddRef(&v16);
    v16 = v15;
    v15 = v7;
    Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(&v16);
  }
  v8 = v15;
  if ( !v15 )
    goto LABEL_9;
  v13 = &PrintCore::BStrRAII::`vftable';
  v14 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 208LL);
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v13);
  v10 = v9(v8, &v14);
  PrintCore::ThrowIfError(
    (PrintCore *)v10,
    "Unspecified.",
    "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
    (const char *)0x6D,
    v12);
  if ( !v14 )
  {
    v13 = &PrintCore::BStrRAII::`vftable';
    PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v13);
    goto LABEL_9;
  }
  std::make_shared<std::wstring,PrintCore::BStrRAII &>(a1, &v13);
  v13 = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v13);
LABEL_10:
  Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(&v15);
  return a1;
}

```

## disassembly

```asm
0x18003ebc8  mov     [rsp-18h+arg_0], rbx
0x18003ebcd  mov     [rsp-18h+arg_8], rsi
0x18003ebd2  push    rbp
0x18003ebd3  push    rdi
0x18003ebd4  push    r15
0x18003ebd6  mov     rbp, rsp
0x18003ebd9  sub     rsp, 40h
0x18003ebdd  mov     rsi, rcx
0x18003ebe0  mov     [rbp+arg_10], 0
0x18003ebe8  lea     r15, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x18003ebef  test    r8, r8
0x18003ebf2  jz      short loc_18003EC31
0x18003ebf4  mov     rdi, [rdx]
0x18003ebf7  mov     rax, [rdi]
0x18003ebfa  mov     rbx, [rax+128h]
0x18003ec01  mov     rdx, r8; unsigned __int16 *
0x18003ec04  lea     rcx, [rbp+var_18]; this
0x18003ec08  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x18003ec0d  nop
0x18003ec0e  lea     r8, [rbp+arg_10]
0x18003ec12  mov     rdx, [rax+8]
0x18003ec16  mov     rcx, rdi
0x18003ec19  mov     rax, rbx
0x18003ec1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec21  nop
0x18003ec22  mov     [rbp+var_18], r15
0x18003ec26  lea     rcx, [rbp+var_18]; this
0x18003ec2a  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003ec2f  jmp     short loc_18003EC5F
0x18003ec31  mov     rbx, [rdx]
0x18003ec34  test    rbx, rbx
0x18003ec37  jz      loc_18003ECE1
0x18003ec3d  mov     [rbp+arg_18], rbx
0x18003ec41  lea     rcx, [rbp+arg_18]
0x18003ec45  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNode>::InternalAddRef(void)
0x18003ec4a  mov     rax, [rbp+arg_10]
0x18003ec4e  mov     [rbp+arg_18], rax
0x18003ec52  mov     [rbp+arg_10], rbx
0x18003ec56  lea     rcx, [rbp+arg_18]
0x18003ec5a  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x18003ec5f  mov     rbx, [rbp+arg_10]
0x18003ec63  test    rbx, rbx
0x18003ec66  jz      short loc_18003ECE1
0x18003ec68  mov     [rbp+var_18], r15
0x18003ec6c  mov     [rbp+var_10], 0
0x18003ec74  mov     rax, [rbx]
0x18003ec77  mov     rdi, [rax+0D0h]
0x18003ec7e  lea     rcx, [rbp+var_18]; this
0x18003ec82  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003ec87  lea     rdx, [rbp+var_10]
0x18003ec8b  mov     rcx, rbx
0x18003ec8e  mov     rax, rdi
0x18003ec91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec96  mov     r9d, 6Dh ; 'm'; char *
0x18003ec9c  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003eca3  lea     rdx, aUnspecified; "Unspecified."
0x18003ecaa  mov     ecx, eax; this
0x18003ecac  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003ecb1  cmp     [rbp+var_10], 0
0x18003ecb6  jz      short loc_18003ECD4
0x18003ecb8  lea     rdx, [rbp+var_18]
0x18003ecbc  mov     rcx, rsi
0x18003ecbf  call    ??$make_shared@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVBStrRAII@PrintCore@@@std@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@AEAVBStrRAII@PrintCore@@@Z; std::make_shared<std::wstring,PrintCore::BStrRAII &>(PrintCore::BStrRAII &)
0x18003ecc4  nop
0x18003ecc5  mov     [rbp+var_18], r15
0x18003ecc9  lea     rcx, [rbp+var_18]; this
0x18003eccd  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003ecd2  jmp     short loc_18003ECF0
0x18003ecd4  mov     [rbp+var_18], r15
0x18003ecd8  lea     rcx, [rbp+var_18]; this
0x18003ecdc  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003ece1  mov     qword ptr [rsi], 0
0x18003ece8  mov     qword ptr [rsi+8], 0
0x18003ecf0  lea     rcx, [rbp+arg_10]
0x18003ecf4  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x18003ecf9  mov     rax, rsi
0x18003ecfc  mov     rbx, [rsp+40h+arg_0]
0x18003ed01  mov     rsi, [rsp+40h+arg_8]
0x18003ed06  add     rsp, 40h
0x18003ed0a  pop     r15
0x18003ed0c  pop     rdi
0x18003ed0d  pop     rbp
0x18003ed0e  retn
```
