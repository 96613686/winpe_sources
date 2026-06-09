# CMidi2KSMidiConfigurationManager::ProcessCommand(winrt::Windows::Data::Json::JsonObject const &,winrt::Windows::Data::Json::JsonObject &)

- ea: `0x180022e38`
- end: `0x180023097`
- name: `?ProcessCommand@CMidi2KSMidiConfigurationManager@@AEAAJAEBUJsonObject@Json@Data@Windows@winrt@@AEAU23456@@Z`
- size: `607`
- prototype: `__int64 __fastcall(CMidi2KSMidiConfigurationManager *__hidden this, const struct winrt::Windows::Data::Json::JsonObject *, struct winrt::Windows::Data::Json::JsonObject *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023ac0`

## callees

- `0x180004410`
- `0x180004460`
- `0x18000c250`
- `0x18000d1c0`
- `0x18000f304`
- `0x1800156e4`
- `0x180017c18`
- `0x18002138c`
- `0x1800214e4`
- `0x180021644`
- `0x18002179c`
- `0x180021cfc`
- `0x180021d6c`
- `0x180022080`
- `0x1800228d0`
- `0x180022e38`
- `0x180023534`
- `0x1800236b8`
- `0x1800237f4`
- `0x180041010`

## string_xrefs

- `0x180022ec9`: `Missing command.`
- `0x180023045`: `Unrecognized command.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMidi2KSMidiConfigurationManager::ProcessCommand(
        CMidi2KSMidiConfigurationManager *this,
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
  char v14[8]; // [rsp+20h] [rbp-39h] BYREF
  bool v15[8]; // [rsp+28h] [rbp-31h] BYREF
  wchar_t *S1[2]; // [rsp+38h] [rbp-21h] BYREF
  __int64 v17; // [rsp+48h] [rbp-11h]
  unsigned __int64 v18; // [rsp+50h] [rbp-9h]
  __int128 v19; // [rsp+58h] [rbp-1h] BYREF
  __int64 v20; // [rsp+68h] [rbp+Fh]
  const wchar_t *v21; // [rsp+70h] [rbp+17h]
  char v22[32]; // [rsp+78h] [rbp+1Fh] BYREF
  _BYTE v23[16]; // [rsp+98h] [rbp+3Fh] BYREF

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
    std::wstring::_Construct<1,unsigned short const *>(S1, L"Missing command.", 16);
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
    std::wstring::_Construct<1,unsigned short const *>(&v19, L"Unrecognized command.", 21);
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
  v14[0] = 1;
  ((void (__fastcall *)(wchar_t **, bool *, const wchar_t *, char *))std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<unsigned short const (&)[18],bool>)(
    S1,
    v15,
    L"customizeEndpoint",
    v14);
  v14[0] = 1;
  ((void (__fastcall *)(wchar_t **, bool *, __int64, char *))std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<unsigned short const (&)[15],bool>)(
    S1,
    v15,
    v10,
    v14);
  v14[0] = 0;
  ((void (__fastcall *)(wchar_t **, bool *, __int64, char *))std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<unsigned short const (&)[16],bool>)(
    S1,
    v15,
    v11,
    v14);
  v14[0] = 0;
  ((void (__fastcall *)(wchar_t **, bool *, __int64, char *))std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<unsigned short const (&)[19],bool>)(
    S1,
    v15,
    v12,
    v14);
  v14[0] = 0;
  ((void (__fastcall *)(wchar_t **, bool *, const wchar_t *, char *))std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<unsigned short const (&)[18],bool>)(
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
0x180022e38  mov     [rsp-8+arg_0], rbx
0x180022e3d  mov     [rsp-8+arg_8], rdi
0x180022e42  push    rbp
0x180022e43  lea     rbp, [rsp-57h]
0x180022e48  sub     rsp, 0B0h
0x180022e4f  mov     rax, cs:__security_cookie
0x180022e56  xor     rax, rsp
0x180022e59  mov     [rbp+57h+var_8], rax
0x180022e5d  mov     rdi, r8
0x180022e60  mov     rcx, [rdx]
0x180022e63  mov     qword ptr [rbp+57h+var_88], rcx
0x180022e67  test    rcx, rcx
0x180022e6a  jz      short loc_180022E78
0x180022e6c  mov     rax, [rcx]
0x180022e6f  mov     rax, [rax+8]
0x180022e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e78  lea     rdx, [rbp+57h+var_88]
0x180022e7c  lea     rcx, [rbp+57h+var_38]
0x180022e80  call    ?ParseCommand@MidiTransportCommandHelper@WindowsMidiServicesInternal@@SA?AV12@UJsonObject@Json@Data@Windows@winrt@@@Z; WindowsMidiServicesInternal::MidiTransportCommandHelper::ParseCommand(winrt::Windows::Data::Json::JsonObject)
0x180022e85  nop
0x180022e86  lea     rdx, [rbp+57h+var_38]
0x180022e8a  lea     rcx, [rbp+57h+var_58]
0x180022e8e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022e93  cmp     [rbp+57h+var_48], 0
0x180022e98  setz    bl
0x180022e9b  lea     rcx, [rbp+57h+var_58]; void *
0x180022e9f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022ea4  lea     rcx, [rbp+57h+S1]
0x180022ea8  test    bl, bl
0x180022eaa  jz      short loc_180022EDE
0x180022eac  xorps   xmm0, xmm0
0x180022eaf  movups  xmmword ptr [rbp+57h+S1], xmm0
0x180022eb3  mov     [rbp+57h+var_68], 0
0x180022ebb  mov     [rbp+57h+var_60], 0
0x180022ec3  mov     r8d, 10h
0x180022ec9  lea     rdx, aMissingCommand; "Missing command."
0x180022ed0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180022ed5  lea     rdx, [rbp+57h+S1]
0x180022ed9  jmp     loc_180023059
0x180022ede  lea     rdx, [rbp+57h+var_38]
0x180022ee2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022ee7  lea     rcx, [rbp+57h+S1]
0x180022eeb  cmp     [rbp+57h+var_60], 7
0x180022ef0  cmova   rcx, [rbp+57h+S1]; S1
0x180022ef5  mov     r8d, 11h; N
0x180022efb  cmp     [rbp+57h+var_68], r8
0x180022eff  jz      short loc_180022F05
0x180022f01  xor     bl, bl
0x180022f03  jmp     short loc_180022F16
0x180022f05  lea     rdx, aQuerycapabilit; "queryCapabilities"
0x180022f0c  call    wmemcmp
0x180022f11  test    eax, eax
0x180022f13  setz    bl
0x180022f16  lea     rcx, [rbp+57h+S1]; void *
0x180022f1a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022f1f  xorps   xmm0, xmm0
0x180022f22  test    bl, bl
0x180022f24  jz      loc_18002302B
0x180022f2a  movdqu  xmmword ptr [rbp+57h+S1], xmm0
0x180022f2f  mov     ecx, 48h ; 'H'; Size
0x180022f34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022f39  mov     [rax], rax
0x180022f3c  mov     [rax+8], rax
0x180022f40  mov     [rax+10h], rax
0x180022f44  mov     word ptr [rax+18h], 101h
0x180022f4a  mov     [rbp+57h+S1], rax
0x180022f4e  mov     [rbp+57h+var_90], 1
0x180022f52  lea     r9, [rbp+57h+var_90]
0x180022f56  lea     r8, aCustomizeendpo; "customizeEndpoint"
0x180022f5d  lea     rdx, [rbp+57h+var_88]
0x180022f61  lea     rcx, [rbp+57h+S1]
0x180022f65  call    ??$emplace@AEAY0BC@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0BC@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[18],bool>(ushort const (&)[18],bool &&)
0x180022f6a  mov     [rbp+57h+var_90], 1
0x180022f6e  lea     r9, [rbp+57h+var_90]
0x180022f72  lea     rdx, [rbp+57h+var_88]
0x180022f76  lea     rcx, [rbp+57h+S1]
0x180022f7a  call    ??$emplace@AEAY0P@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0P@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[15],bool>(ushort const (&)[15],bool &&)
0x180022f7f  mov     [rbp+57h+var_90], 0
0x180022f83  lea     r9, [rbp+57h+var_90]
0x180022f87  lea     rdx, [rbp+57h+var_88]
0x180022f8b  lea     rcx, [rbp+57h+S1]
0x180022f8f  call    ??$emplace@AEAY0BA@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0BA@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[16],bool>(ushort const (&)[16],bool &&)
0x180022f94  mov     [rbp+57h+var_90], 0
0x180022f98  lea     r9, [rbp+57h+var_90]
0x180022f9c  lea     rdx, [rbp+57h+var_88]
0x180022fa0  lea     rcx, [rbp+57h+S1]
0x180022fa4  call    ??$emplace@AEAY0BD@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0BD@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[19],bool>(ushort const (&)[19],bool &&)
0x180022fa9  mov     [rbp+57h+var_90], 0
0x180022fad  lea     r9, [rbp+57h+var_90]
0x180022fb1  lea     r8, aReconnectendpo; "reconnectEndpoint"
0x180022fb8  lea     rdx, [rbp+57h+var_88]
0x180022fbc  lea     rcx, [rbp+57h+S1]
0x180022fc0  call    ??$emplace@AEAY0BC@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0BC@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[18],bool>(ushort const (&)[18],bool &&)
0x180022fc5  mov     dl, 1
0x180022fc7  lea     rcx, [rbp+57h+var_88]; bool
0x180022fcb  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x180022fd0  nop
0x180022fd1  mov     dword ptr [rbp+57h+var_58+8], 1
0x180022fd8  mov     dword ptr [rbp+57h+var_58+0Ch], 7
0x180022fdf  lea     rax, aSuccess; "success"
0x180022fe6  mov     [rbp+57h+var_40], rax
0x180022fea  lea     rax, [rbp+57h+var_58+8]
0x180022fee  mov     qword ptr [rbp+57h+var_58], rax
0x180022ff2  lea     r8, [rbp+57h+var_88]
0x180022ff6  lea     rdx, [rbp+57h+var_58]
0x180022ffa  mov     rcx, rdi
0x180022ffd  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180023002  nop
0x180023003  cmp     qword ptr [rbp+57h+var_88], 0
0x180023008  jz      short loc_180023013
0x18002300a  lea     rcx, [rbp+57h+var_88]
0x18002300e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023013  lea     rdx, [rbp+57h+S1]
0x180023017  mov     rcx, rdi
0x18002301a  call    ?SetConfigurationCommandResponseQueryCapabilities@WindowsMidiServicesInternal@@YAXAEAUJsonObject@Json@Data@Windows@winrt@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@std@@@Z; WindowsMidiServicesInternal::SetConfigurationCommandResponseQueryCapabilities(winrt::Windows::Data::Json::JsonObject &,std::map<std::wstring,bool> &)
0x18002301f  nop
0x180023020  lea     rcx, [rbp+57h+S1]
0x180023024  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>(void)
0x180023029  jmp     short loc_180023062
0x18002302b  movups  [rbp+57h+var_58], xmm0
0x18002302f  mov     [rbp+57h+var_48], 0
0x180023037  mov     [rbp+57h+var_40], 0
0x18002303f  mov     r8d, 15h
0x180023045  lea     rdx, aUnrecognizedCo; "Unrecognized command."
0x18002304c  lea     rcx, [rbp+57h+var_58]
0x180023050  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180023055  lea     rdx, [rbp+57h+var_58]
0x180023059  mov     rcx, rdi
0x18002305c  call    ?SetConfigurationResponseObjectFail@WindowsMidiServicesInternal@@YAXAEAUJsonObject@Json@Data@Windows@winrt@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::SetConfigurationResponseObjectFail(winrt::Windows::Data::Json::JsonObject &,std::wstring)
0x180023061  nop
0x180023062  lea     rcx, [rbp+57h+var_18]
0x180023066  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18002306b  lea     rcx, [rbp+57h+var_38]; void *
0x18002306f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023074  xor     eax, eax
0x180023076  mov     rcx, [rbp+57h+var_8]
0x18002307a  xor     rcx, rsp; StackCookie
0x18002307d  call    __security_check_cookie
0x180023082  lea     r11, [rsp+0B0h+var_s0]
0x18002308a  mov     rbx, [r11+10h]
0x18002308e  mov     rdi, [r11+18h]
0x180023092  mov     rsp, r11
0x180023095  pop     rbp
0x180023096  retn
```
