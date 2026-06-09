# GetAppUriHandlerJsonFromFile(ushort const *)

- ea: `0x14000bc30`
- end: `0x14000be18`
- name: `?GetAppUriHandlerJsonFromFile@@YA?AV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEBG@Z`
- size: `488`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000eb7c`

## callees

- `0x140002210`
- `0x1400076b8`
- `0x140007724`
- `0x14000834c`
- `0x140008814`
- `0x140009b1c`
- `0x140009c50`
- `0x140009d24`
- `0x14000a5d8`
- `0x14000a604`
- `0x14000ac20`
- `0x14000bc30`
- `0x14000d49c`
- `0x14000f940`
- `0x14000fbb0`
- `0x14000fd5c`
- `0x140012010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z` at `0x14000bc86`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z` at `0x14000bc86`

## string_xrefs

- `0x14000bcf8`: `Windows.Data.Json.JsonArray`

## pseudocode

```c
_QWORD *__fastcall GetAppUriHandlerJsonFromFile(_QWORD *a1)
{
  int v2; // eax
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, _QWORD, _QWORD *); // rbx
  char v5; // al
  _QWORD *v6; // rdx
  __int64 v7; // rax
  int v8; // eax
  int v10; // [rsp+20h] [rbp-E0h]
  __int64 v11; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v12[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[232]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v15[16]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v16[256]; // [rsp+150h] [rbp+50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+250h] [rbp+150h] BYREF
  __int64 v18; // [rsp+268h] [rbp+168h]
  _QWORD v19[4]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v12[1] = a1;
  std::basic_ifstream<unsigned short>::basic_ifstream<unsigned short>(v15);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v13);
  std::basic_ostream<unsigned short>::operator<<(v13, v16);
  std::wstring::wstring(v19);
  std::basic_stringbuf<unsigned short>::_Get_buffer_view(v14, &hstringHeader);
  if ( hstringHeader.Reserved.Reserved1 )
    std::wstring::assign(v19, hstringHeader.Reserved.Reserved1, *(_QWORD *)&hstringHeader.Reserved.Reserved2[8]);
  v11 = 0;
  v18 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonArray",
    0x1Cu,
    0x1Bu);
  v2 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArrayStatics>>(
         v18,
         &v11);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x223,
      (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v2,
      v10);
  *a1 = 0;
  v3 = v11;
  v4 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v11 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(a1);
  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(v19);
  v6 = v19;
  if ( v5 )
    v6 = (_QWORD *)v19[0];
  v12[0] = v6;
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v12);
  v8 = v4(v3, *(_QWORD *)(v7 + 24), a1);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x225,
      (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v8,
      v10);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v11);
  std::wstring::_Tidy_deallocate(v19);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v13);
  std::basic_ifstream<unsigned short>::`vbase destructor'(v15);
  return a1;
}

```

## disassembly

```asm
0x14000bc30  mov     [rsp-8+arg_10], rbx
0x14000bc35  push    rbp
0x14000bc36  push    rsi
0x14000bc37  push    rdi
0x14000bc38  lea     rbp, [rsp-1A0h]
0x14000bc40  sub     rsp, 2A0h
0x14000bc47  mov     rax, cs:__security_cookie
0x14000bc4e  xor     rax, rsp
0x14000bc51  mov     [rbp+1B0h+var_20], rax
0x14000bc58  mov     rsi, rcx
0x14000bc5b  mov     [rsp+2B0h+var_268], rcx
0x14000bc60  mov     [rsp+2B0h+var_280], 0
0x14000bc68  lea     rcx, [rbp+1B0h+var_170]
0x14000bc6c  call    ??0?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAA@PEBGHH@Z; std::basic_ifstream<ushort>::basic_ifstream<ushort>(ushort const *,int,int)
0x14000bc71  nop
0x14000bc72  lea     rcx, [rsp+2B0h+var_260]
0x14000bc77  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x14000bc7c  nop
0x14000bc7d  lea     rdx, [rbp+1B0h+var_160]
0x14000bc81  lea     rcx, [rsp+2B0h+var_260]
0x14000bc86  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z; std::basic_ostream<ushort>::operator<<(std::basic_streambuf<ushort> *)
0x14000bc8c  nop
0x14000bc8d  lea     rcx, [rbp+1B0h+var_40]
0x14000bc94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::allocator<ushort> const &)
0x14000bc99  mov     [rsp+2B0h+var_280], 4
0x14000bca1  lea     rdx, [rbp+1B0h+hstringHeader]
0x14000bca8  lea     rcx, [rsp+2B0h+var_258]
0x14000bcad  call    ?_Get_buffer_view@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AU_Buffer_view@12@XZ; std::basic_stringbuf<ushort>::_Get_buffer_view(void)
0x14000bcb2  mov     rdx, qword ptr [rbp+1B0h+hstringHeader.Reserved]
0x14000bcb9  test    rdx, rdx
0x14000bcbc  jz      short loc_14000BCD2
0x14000bcbe  mov     r8, qword ptr [rbp+1B0h+hstringHeader.Reserved+8]
0x14000bcc5  lea     rcx, [rbp+1B0h+var_40]
0x14000bccc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x14000bcd1  nop
0x14000bcd2  mov     [rsp+2B0h+var_280], 2
0x14000bcda  mov     [rsp+2B0h+var_278], 0
0x14000bce3  mov     [rbp+1B0h+var_48], 0
0x14000bcee  mov     r9d, 1Bh; unsigned int
0x14000bcf4  lea     r8d, [r9+1]; unsigned int
0x14000bcf8  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x14000bcff  lea     rcx, [rbp+1B0h+hstringHeader]; hstringHeader
0x14000bd06  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14000bd0b  nop
0x14000bd0c  lea     rdx, [rsp+2B0h+var_278]
0x14000bd11  mov     rcx, [rbp+1B0h+var_48]
0x14000bd18  call    ??$GetActivationFactory@V?$ComPtr@UIJsonArrayStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArrayStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArrayStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArrayStatics>>)
0x14000bd1d  mov     rcx, [rbp+1B8h]; this
0x14000bd24  test    eax, eax
0x14000bd26  jns     short loc_14000BD3D
0x14000bd28  mov     r9d, eax; char *
0x14000bd2b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000bd32  mov     edx, 223h; void *
0x14000bd37  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000bd3d  mov     qword ptr [rsi], 0
0x14000bd44  mov     [rsp+2B0h+var_280], 3
0x14000bd4c  mov     rdi, [rsp+2B0h+var_278]
0x14000bd51  mov     rax, [rdi]
0x14000bd54  mov     rbx, [rax+30h]
0x14000bd58  mov     rcx, rsi
0x14000bd5b  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000bd60  lea     rcx, [rbp+1B0h+var_40]
0x14000bd67  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x14000bd6c  lea     rdx, [rbp+1B0h+var_40]
0x14000bd73  test    al, al
0x14000bd75  cmovnz  rdx, [rbp+1B0h+var_40]
0x14000bd7d  mov     [rsp+2B0h+var_270], rdx
0x14000bd82  lea     rdx, [rsp+2B0h+var_270]
0x14000bd87  lea     rcx, [rbp+1B0h+hstringHeader]
0x14000bd8e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14000bd93  nop
0x14000bd94  mov     r8, rsi
0x14000bd97  mov     rdx, [rax+18h]
0x14000bd9b  mov     rcx, rdi
0x14000bd9e  mov     rax, rbx
0x14000bda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bda6  mov     rcx, [rbp+1B8h]; this
0x14000bdad  test    eax, eax
0x14000bdaf  jns     short loc_14000BDC6
0x14000bdb1  mov     r9d, eax; char *
0x14000bdb4  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000bdbb  mov     edx, 225h; void *
0x14000bdc0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000bdc6  lea     rcx, [rsp+2B0h+var_278]
0x14000bdcb  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000bdd0  nop
0x14000bdd1  lea     rcx, [rbp+1B0h+var_40]
0x14000bdd8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000bddd  nop
0x14000bdde  lea     rcx, [rsp+2B0h+var_260]
0x14000bde3  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x14000bde8  nop
0x14000bde9  lea     rcx, [rbp+1B0h+var_170]
0x14000bded  call    ??_D?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ifstream<ushort>::`vbase destructor'(void)
0x14000bdf2  mov     rax, rsi
0x14000bdf5  mov     rcx, [rbp+1B0h+var_20]
0x14000bdfc  xor     rcx, rsp; StackCookie
0x14000bdff  call    __security_check_cookie
0x14000be04  mov     rbx, [rsp+2B0h+arg_10]
0x14000be0c  add     rsp, 2A0h
0x14000be13  pop     rdi
0x14000be14  pop     rsi
0x14000be15  pop     rbp
0x14000be16  retn
```
