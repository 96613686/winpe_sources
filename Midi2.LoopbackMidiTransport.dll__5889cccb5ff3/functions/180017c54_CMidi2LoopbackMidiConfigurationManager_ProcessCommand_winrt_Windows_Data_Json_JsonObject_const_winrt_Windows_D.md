# CMidi2LoopbackMidiConfigurationManager::ProcessCommand(winrt::Windows::Data::Json::JsonObject const &,winrt::Windows::Data::Json::JsonObject &)

- ea: `0x180017c54`
- end: `0x180017e95`
- name: `?ProcessCommand@CMidi2LoopbackMidiConfigurationManager@@AEAAJAEBUJsonObject@Json@Data@Windows@winrt@@AEAU23456@@Z`
- size: `577`
- prototype: `__int64 __fastcall(CMidi2LoopbackMidiConfigurationManager *__hidden this, const struct winrt::Windows::Data::Json::JsonObject *, struct winrt::Windows::Data::Json::JsonObject *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018710`

## callees

- `0x180004180`
- `0x1800041d0`
- `0x18000b740`
- `0x18000e178`
- `0x18000f0a4`
- `0x180014974`
- `0x180014ab8`
- `0x180015790`
- `0x1800158e8`
- `0x180015a48`
- `0x180015ba0`
- `0x180016380`
- `0x1800163f0`
- `0x1800168a0`
- `0x1800176ec`
- `0x180017c54`
- `0x180018090`
- `0x180018264`
- `0x1800183a0`
- `0x180032010`

## string_xrefs

- `0x180017cd8`: `Missing command.`
- `0x180017e4c`: `Unrecognized command.`

## pseudocode

```c
__int64 __fastcall CMidi2LoopbackMidiConfigurationManager::ProcessCommand(
        CMidi2LoopbackMidiConfigurationManager *this,
        const struct winrt::Windows::Data::Json::JsonObject *a2,
        struct winrt::Windows::Data::Json::JsonObject *a3)
{
  __int64 v4; // rcx
  bool v5; // bl
  wchar_t **v6; // rdx
  const wchar_t *v7; // rcx
  bool v8; // bl
  _QWORD *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // r8
  _BYTE v14[8]; // [rsp+20h] [rbp-59h] BYREF
  bool v15[8]; // [rsp+28h] [rbp-51h] BYREF
  wchar_t *S1[2]; // [rsp+38h] [rbp-41h] BYREF
  __int64 v17; // [rsp+48h] [rbp-31h]
  unsigned __int64 v18; // [rsp+50h] [rbp-29h]
  __int128 v19; // [rsp+58h] [rbp-21h] BYREF
  __int64 v20; // [rsp+68h] [rbp-11h]
  const unsigned __int16 *v21; // [rsp+70h] [rbp-9h]
  _BYTE v22[32]; // [rsp+78h] [rbp-1h] BYREF
  _BYTE v23[16]; // [rsp+98h] [rbp+1Fh] BYREF

  v4 = *(_QWORD *)a2;
  *(_QWORD *)v15 = v4;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  WindowsMidiServicesInternal::MidiTransportCommandHelper::ParseCommand(v22, v15);
  std::wstring::wstring(&v19, v22);
  v5 = v20 == 0;
  std::wstring::~wstring(&v19);
  if ( v5 )
  {
    *(_OWORD *)S1 = 0;
    v17 = 0;
    v18 = 0;
    std::wstring::_Construct<1,unsigned short const *>(S1, L"Missing command.");
    v6 = S1;
LABEL_15:
    WindowsMidiServicesInternal::SetConfigurationResponseObjectFail(a3, v6);
    goto LABEL_16;
  }
  std::wstring::wstring(S1, v22);
  v7 = (const wchar_t *)S1;
  if ( v18 > 7 )
    v7 = S1[0];
  v8 = v17 == 17 && wmemcmp(v7, L"queryCapabilities", 0x11u) == 0;
  std::wstring::~wstring(S1);
  if ( !v8 )
  {
    v19 = 0;
    v20 = 0;
    v21 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v19, L"Unrecognized command.");
    v6 = (wchar_t **)&v19;
    goto LABEL_15;
  }
  *(_OWORD *)S1 = 0;
  v9 = operator new(0x48u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  S1[0] = (wchar_t *)v9;
  v14[0] = 0;
  ((void (__fastcall *)(wchar_t **, bool *, const wchar_t *, _BYTE *))std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<unsigned short const (&)[18],bool>)(
    S1,
    v15,
    L"customizeEndpoint",
    v14);
  v14[0] = 0;
  ((void (__fastcall *)(wchar_t **, bool *, __int64, _BYTE *))std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<unsigned short const (&)[15],bool>)(
    S1,
    v15,
    v10,
    v14);
  v14[0] = 0;
  ((void (__fastcall *)(wchar_t **, bool *, __int64, _BYTE *))std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<unsigned short const (&)[16],bool>)(
    S1,
    v15,
    v11,
    v14);
  v14[0] = 0;
  ((void (__fastcall *)(wchar_t **, bool *, __int64, _BYTE *))std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<unsigned short const (&)[19],bool>)(
    S1,
    v15,
    v12,
    v14);
  v14[0] = 0;
  ((void (__fastcall *)(wchar_t **, bool *, const wchar_t *, _BYTE *))std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<unsigned short const (&)[18],bool>)(
    S1,
    v15,
    L"reconnectEndpoint",
    v14);
  winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v15);
  *((_QWORD *)&v19 + 1) = 0x700000001LL;
  v21 = L"success";
  *(_QWORD *)&v19 = (char *)&v19 + 8;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    a3,
    &v19,
    v15);
  if ( *(_QWORD *)v15 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v15);
  WindowsMidiServicesInternal::SetConfigurationCommandResponseQueryCapabilities(a3, S1);
  std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>(S1);
LABEL_16:
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v23);
  std::wstring::~wstring(v22);
  return 0;
}

```

## disassembly

```asm
0x180017c54  push    rbp
0x180017c56  push    rbx
0x180017c57  push    rsi
0x180017c58  push    rdi
0x180017c59  lea     rbp, [rsp-3Fh]
0x180017c5e  sub     rsp, 0B8h
0x180017c65  mov     rax, cs:__security_cookie
0x180017c6c  xor     rax, rsp
0x180017c6f  mov     [rbp+57h+var_28], rax
0x180017c73  mov     rdi, r8
0x180017c76  xor     esi, esi
0x180017c78  mov     rcx, [rdx]
0x180017c7b  mov     qword ptr [rbp+57h+var_A8], rcx
0x180017c7f  test    rcx, rcx
0x180017c82  jz      short loc_180017C90
0x180017c84  mov     rax, [rcx]
0x180017c87  mov     rax, [rax+8]
0x180017c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c90  lea     rdx, [rbp+57h+var_A8]
0x180017c94  lea     rcx, [rbp+57h+var_58]
0x180017c98  call    ?ParseCommand@MidiTransportCommandHelper@WindowsMidiServicesInternal@@SA?AV12@UJsonObject@Json@Data@Windows@winrt@@@Z; WindowsMidiServicesInternal::MidiTransportCommandHelper::ParseCommand(winrt::Windows::Data::Json::JsonObject)
0x180017c9d  nop
0x180017c9e  lea     rdx, [rbp+57h+var_58]
0x180017ca2  lea     rcx, [rbp+57h+var_78]
0x180017ca6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017cab  cmp     [rbp+57h+var_68], rsi
0x180017caf  setz    bl
0x180017cb2  lea     rcx, [rbp+57h+var_78]; void *
0x180017cb6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017cbb  lea     rcx, [rbp+57h+S1]
0x180017cbf  test    bl, bl
0x180017cc1  jz      short loc_180017CED
0x180017cc3  xorps   xmm0, xmm0
0x180017cc6  movups  xmmword ptr [rbp+57h+S1], xmm0
0x180017cca  mov     [rbp+57h+var_88], rsi
0x180017cce  mov     [rbp+57h+var_80], rsi
0x180017cd2  mov     r8d, 10h
0x180017cd8  lea     rdx, aMissingCommand; "Missing command."
0x180017cdf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017ce4  lea     rdx, [rbp+57h+S1]
0x180017ce8  jmp     loc_180017E60
0x180017ced  lea     rdx, [rbp+57h+var_58]
0x180017cf1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017cf6  lea     rcx, [rbp+57h+S1]
0x180017cfa  cmp     [rbp+57h+var_80], 7
0x180017cff  cmova   rcx, [rbp+57h+S1]; S1
0x180017d04  mov     r8d, 11h; N
0x180017d0a  cmp     [rbp+57h+var_88], r8
0x180017d0e  jz      short loc_180017D15
0x180017d10  mov     bl, sil
0x180017d13  jmp     short loc_180017D26
0x180017d15  lea     rdx, aQuerycapabilit; "queryCapabilities"
0x180017d1c  call    wmemcmp
0x180017d21  test    eax, eax
0x180017d23  setz    bl
0x180017d26  lea     rcx, [rbp+57h+S1]; void *
0x180017d2a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017d2f  xorps   xmm0, xmm0
0x180017d32  test    bl, bl
0x180017d34  jz      loc_180017E3A
0x180017d3a  movdqu  xmmword ptr [rbp+57h+S1], xmm0
0x180017d3f  mov     ecx, 48h ; 'H'; Size
0x180017d44  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017d49  mov     [rax], rax
0x180017d4c  mov     [rax+8], rax
0x180017d50  mov     [rax+10h], rax
0x180017d54  mov     word ptr [rax+18h], 101h
0x180017d5a  mov     [rbp+57h+S1], rax
0x180017d5e  mov     [rbp+57h+var_B0], sil
0x180017d62  lea     r9, [rbp+57h+var_B0]
0x180017d66  lea     r8, aCustomizeendpo; "customizeEndpoint"
0x180017d6d  lea     rdx, [rbp+57h+var_A8]
0x180017d71  lea     rcx, [rbp+57h+S1]
0x180017d75  call    ??$emplace@AEAY0BC@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0BC@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[18],bool>(ushort const (&)[18],bool &&)
0x180017d7a  mov     [rbp+57h+var_B0], sil
0x180017d7e  lea     r9, [rbp+57h+var_B0]
0x180017d82  lea     rdx, [rbp+57h+var_A8]
0x180017d86  lea     rcx, [rbp+57h+S1]
0x180017d8a  call    ??$emplace@AEAY0P@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0P@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[15],bool>(ushort const (&)[15],bool &&)
0x180017d8f  mov     [rbp+57h+var_B0], sil
0x180017d93  lea     r9, [rbp+57h+var_B0]
0x180017d97  lea     rdx, [rbp+57h+var_A8]
0x180017d9b  lea     rcx, [rbp+57h+S1]
0x180017d9f  call    ??$emplace@AEAY0BA@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0BA@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[16],bool>(ushort const (&)[16],bool &&)
0x180017da4  mov     [rbp+57h+var_B0], sil
0x180017da8  lea     r9, [rbp+57h+var_B0]
0x180017dac  lea     rdx, [rbp+57h+var_A8]
0x180017db0  lea     rcx, [rbp+57h+S1]
0x180017db4  call    ??$emplace@AEAY0BD@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0BD@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[19],bool>(ushort const (&)[19],bool &&)
0x180017db9  mov     [rbp+57h+var_B0], sil
0x180017dbd  lea     r9, [rbp+57h+var_B0]
0x180017dc1  lea     r8, aReconnectendpo; "reconnectEndpoint"
0x180017dc8  lea     rdx, [rbp+57h+var_A8]
0x180017dcc  lea     rcx, [rbp+57h+S1]
0x180017dd0  call    ??$emplace@AEAY0BC@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0BC@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[18],bool>(ushort const (&)[18],bool &&)
0x180017dd5  mov     dl, 1
0x180017dd7  lea     rcx, [rbp+57h+var_A8]; bool
0x180017ddb  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x180017de0  nop
0x180017de1  mov     dword ptr [rbp+57h+var_78+8], 1
0x180017de8  mov     dword ptr [rbp+57h+var_78+0Ch], 7
0x180017def  lea     rax, aSuccess; "success"
0x180017df6  mov     [rbp+57h+var_60], rax
0x180017dfa  lea     rax, [rbp+57h+var_78+8]
0x180017dfe  mov     qword ptr [rbp+57h+var_78], rax
0x180017e02  lea     r8, [rbp+57h+var_A8]
0x180017e06  lea     rdx, [rbp+57h+var_78]
0x180017e0a  mov     rcx, rdi
0x180017e0d  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180017e12  nop
0x180017e13  cmp     qword ptr [rbp+57h+var_A8], rsi
0x180017e17  jz      short loc_180017E22
0x180017e19  lea     rcx, [rbp+57h+var_A8]
0x180017e1d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180017e22  lea     rdx, [rbp+57h+S1]
0x180017e26  mov     rcx, rdi
0x180017e29  call    ?SetConfigurationCommandResponseQueryCapabilities@WindowsMidiServicesInternal@@YAXAEAUJsonObject@Json@Data@Windows@winrt@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@std@@@Z; WindowsMidiServicesInternal::SetConfigurationCommandResponseQueryCapabilities(winrt::Windows::Data::Json::JsonObject &,std::map<std::wstring,bool> &)
0x180017e2e  nop
0x180017e2f  lea     rcx, [rbp+57h+S1]
0x180017e33  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>(void)
0x180017e38  jmp     short loc_180017E69
0x180017e3a  movups  [rbp+57h+var_78], xmm0
0x180017e3e  mov     [rbp+57h+var_68], rsi
0x180017e42  mov     [rbp+57h+var_60], rsi
0x180017e46  mov     r8d, 15h
0x180017e4c  lea     rdx, aUnrecognizedCo; "Unrecognized command."
0x180017e53  lea     rcx, [rbp+57h+var_78]
0x180017e57  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017e5c  lea     rdx, [rbp+57h+var_78]
0x180017e60  mov     rcx, rdi
0x180017e63  call    ?SetConfigurationResponseObjectFail@WindowsMidiServicesInternal@@YAXAEAUJsonObject@Json@Data@Windows@winrt@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::SetConfigurationResponseObjectFail(winrt::Windows::Data::Json::JsonObject &,std::wstring)
0x180017e68  nop
0x180017e69  lea     rcx, [rbp+57h+var_38]
0x180017e6d  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180017e72  lea     rcx, [rbp+57h+var_58]; void *
0x180017e76  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017e7b  xor     eax, eax
0x180017e7d  mov     rcx, [rbp+57h+var_28]
0x180017e81  xor     rcx, rsp; StackCookie
0x180017e84  call    __security_check_cookie
0x180017e89  add     rsp, 0B8h
0x180017e90  pop     rdi
0x180017e91  pop     rsi
0x180017e92  pop     rbx
0x180017e93  pop     rbp
0x180017e94  retn
```
