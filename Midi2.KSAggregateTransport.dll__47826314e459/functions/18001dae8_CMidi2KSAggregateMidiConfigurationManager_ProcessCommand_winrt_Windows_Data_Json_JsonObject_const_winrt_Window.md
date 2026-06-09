# CMidi2KSAggregateMidiConfigurationManager::ProcessCommand(winrt::Windows::Data::Json::JsonObject const &,winrt::Windows::Data::Json::JsonObject &)

- ea: `0x18001dae8`
- end: `0x18001dd47`
- name: `?ProcessCommand@CMidi2KSAggregateMidiConfigurationManager@@AEAAJAEBUJsonObject@Json@Data@Windows@winrt@@AEAU23456@@Z`
- size: `607`
- prototype: `__int64 __fastcall(CMidi2KSAggregateMidiConfigurationManager *__hidden this, const struct winrt::Windows::Data::Json::JsonObject *, struct winrt::Windows::Data::Json::JsonObject *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e790`

## callees

- `0x180005020`
- `0x180005070`
- `0x18000d430`
- `0x180010b94`
- `0x180013118`
- `0x180014194`
- `0x18001a844`
- `0x18001bf34`
- `0x18001c08c`
- `0x18001c1ec`
- `0x18001c344`
- `0x18001c904`
- `0x18001c974`
- `0x18001cd34`
- `0x18001d580`
- `0x18001dae8`
- `0x18001e1e4`
- `0x18001e368`
- `0x18001e4a4`
- `0x18005e010`

## string_xrefs

- `0x18001db79`: `Missing command.`
- `0x18001dcf5`: `Unrecognized command.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMidi2KSAggregateMidiConfigurationManager::ProcessCommand(
        CMidi2KSAggregateMidiConfigurationManager *this,
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
    std::wstring::_Construct<1,unsigned short const *>(S1);
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
    std::wstring::_Construct<1,unsigned short const *>(&v19);
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
0x18001dae8  mov     [rsp-8+arg_0], rbx
0x18001daed  mov     [rsp-8+arg_8], rdi
0x18001daf2  push    rbp
0x18001daf3  lea     rbp, [rsp-57h]
0x18001daf8  sub     rsp, 0B0h
0x18001daff  mov     rax, cs:__security_cookie
0x18001db06  xor     rax, rsp
0x18001db09  mov     [rbp+57h+var_8], rax
0x18001db0d  mov     rdi, r8
0x18001db10  mov     rcx, [rdx]
0x18001db13  mov     qword ptr [rbp+57h+var_88], rcx
0x18001db17  test    rcx, rcx
0x18001db1a  jz      short loc_18001DB28
0x18001db1c  mov     rax, [rcx]
0x18001db1f  mov     rax, [rax+8]
0x18001db23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db28  lea     rdx, [rbp+57h+var_88]
0x18001db2c  lea     rcx, [rbp+57h+var_38]
0x18001db30  call    ?ParseCommand@MidiTransportCommandHelper@WindowsMidiServicesInternal@@SA?AV12@UJsonObject@Json@Data@Windows@winrt@@@Z; WindowsMidiServicesInternal::MidiTransportCommandHelper::ParseCommand(winrt::Windows::Data::Json::JsonObject)
0x18001db35  nop
0x18001db36  lea     rdx, [rbp+57h+var_38]
0x18001db3a  lea     rcx, [rbp+57h+var_58]
0x18001db3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001db43  cmp     [rbp+57h+var_48], 0
0x18001db48  setz    bl
0x18001db4b  lea     rcx, [rbp+57h+var_58]; void *
0x18001db4f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001db54  lea     rcx, [rbp+57h+S1]
0x18001db58  test    bl, bl
0x18001db5a  jz      short loc_18001DB8E
0x18001db5c  xorps   xmm0, xmm0
0x18001db5f  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18001db63  mov     [rbp+57h+var_68], 0
0x18001db6b  mov     [rbp+57h+var_60], 0
0x18001db73  mov     r8d, 10h
0x18001db79  lea     rdx, aMissingCommand; "Missing command."
0x18001db80  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001db85  lea     rdx, [rbp+57h+S1]
0x18001db89  jmp     loc_18001DD09
0x18001db8e  lea     rdx, [rbp+57h+var_38]
0x18001db92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001db97  lea     rcx, [rbp+57h+S1]
0x18001db9b  cmp     [rbp+57h+var_60], 7
0x18001dba0  cmova   rcx, [rbp+57h+S1]; S1
0x18001dba5  mov     r8d, 11h; N
0x18001dbab  cmp     [rbp+57h+var_68], r8
0x18001dbaf  jz      short loc_18001DBB5
0x18001dbb1  xor     bl, bl
0x18001dbb3  jmp     short loc_18001DBC6
0x18001dbb5  lea     rdx, aQuerycapabilit; "queryCapabilities"
0x18001dbbc  call    wmemcmp
0x18001dbc1  test    eax, eax
0x18001dbc3  setz    bl
0x18001dbc6  lea     rcx, [rbp+57h+S1]; void *
0x18001dbca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001dbcf  xorps   xmm0, xmm0
0x18001dbd2  test    bl, bl
0x18001dbd4  jz      loc_18001DCDB
0x18001dbda  movdqu  xmmword ptr [rbp+57h+S1], xmm0
0x18001dbdf  mov     ecx, 48h ; 'H'; Size
0x18001dbe4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dbe9  mov     [rax], rax
0x18001dbec  mov     [rax+8], rax
0x18001dbf0  mov     [rax+10h], rax
0x18001dbf4  mov     word ptr [rax+18h], 101h
0x18001dbfa  mov     [rbp+57h+S1], rax
0x18001dbfe  mov     [rbp+57h+var_90], 1
0x18001dc02  lea     r9, [rbp+57h+var_90]
0x18001dc06  lea     r8, aCustomizeendpo; "customizeEndpoint"
0x18001dc0d  lea     rdx, [rbp+57h+var_88]
0x18001dc11  lea     rcx, [rbp+57h+S1]
0x18001dc15  call    ??$emplace@AEAY0BC@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0BC@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[18],bool>(ushort const (&)[18],bool &&)
0x18001dc1a  mov     [rbp+57h+var_90], 1
0x18001dc1e  lea     r9, [rbp+57h+var_90]
0x18001dc22  lea     rdx, [rbp+57h+var_88]
0x18001dc26  lea     rcx, [rbp+57h+S1]
0x18001dc2a  call    ??$emplace@AEAY0P@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0P@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[15],bool>(ushort const (&)[15],bool &&)
0x18001dc2f  mov     [rbp+57h+var_90], 0
0x18001dc33  lea     r9, [rbp+57h+var_90]
0x18001dc37  lea     rdx, [rbp+57h+var_88]
0x18001dc3b  lea     rcx, [rbp+57h+S1]
0x18001dc3f  call    ??$emplace@AEAY0BA@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0BA@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[16],bool>(ushort const (&)[16],bool &&)
0x18001dc44  mov     [rbp+57h+var_90], 0
0x18001dc48  lea     r9, [rbp+57h+var_90]
0x18001dc4c  lea     rdx, [rbp+57h+var_88]
0x18001dc50  lea     rcx, [rbp+57h+S1]
0x18001dc54  call    ??$emplace@AEAY0BD@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0BD@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[19],bool>(ushort const (&)[19],bool &&)
0x18001dc59  mov     [rbp+57h+var_90], 0
0x18001dc5d  lea     r9, [rbp+57h+var_90]
0x18001dc61  lea     r8, aReconnectendpo; "reconnectEndpoint"
0x18001dc68  lea     rdx, [rbp+57h+var_88]
0x18001dc6c  lea     rcx, [rbp+57h+S1]
0x18001dc70  call    ??$emplace@AEAY0BC@$$CBG_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@_N@1@AEAY0BC@$$CBG$$QEA_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::emplace<ushort const (&)[18],bool>(ushort const (&)[18],bool &&)
0x18001dc75  mov     dl, 1
0x18001dc77  lea     rcx, [rbp+57h+var_88]; bool
0x18001dc7b  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x18001dc80  nop
0x18001dc81  mov     dword ptr [rbp+57h+var_58+8], 1
0x18001dc88  mov     dword ptr [rbp+57h+var_58+0Ch], 7
0x18001dc8f  lea     rax, aSuccess; "success"
0x18001dc96  mov     [rbp+57h+var_40], rax
0x18001dc9a  lea     rax, [rbp+57h+var_58+8]
0x18001dc9e  mov     qword ptr [rbp+57h+var_58], rax
0x18001dca2  lea     r8, [rbp+57h+var_88]
0x18001dca6  lea     rdx, [rbp+57h+var_58]
0x18001dcaa  mov     rcx, rdi
0x18001dcad  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001dcb2  nop
0x18001dcb3  cmp     qword ptr [rbp+57h+var_88], 0
0x18001dcb8  jz      short loc_18001DCC3
0x18001dcba  lea     rcx, [rbp+57h+var_88]
0x18001dcbe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001dcc3  lea     rdx, [rbp+57h+S1]
0x18001dcc7  mov     rcx, rdi
0x18001dcca  call    ?SetConfigurationCommandResponseQueryCapabilities@WindowsMidiServicesInternal@@YAXAEAUJsonObject@Json@Data@Windows@winrt@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@std@@@Z; WindowsMidiServicesInternal::SetConfigurationCommandResponseQueryCapabilities(winrt::Windows::Data::Json::JsonObject &,std::map<std::wstring,bool> &)
0x18001dccf  nop
0x18001dcd0  lea     rcx, [rbp+57h+S1]
0x18001dcd4  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>(void)
0x18001dcd9  jmp     short loc_18001DD12
0x18001dcdb  movups  [rbp+57h+var_58], xmm0
0x18001dcdf  mov     [rbp+57h+var_48], 0
0x18001dce7  mov     [rbp+57h+var_40], 0
0x18001dcef  mov     r8d, 15h
0x18001dcf5  lea     rdx, aUnrecognizedCo; "Unrecognized command."
0x18001dcfc  lea     rcx, [rbp+57h+var_58]
0x18001dd00  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001dd05  lea     rdx, [rbp+57h+var_58]
0x18001dd09  mov     rcx, rdi
0x18001dd0c  call    ?SetConfigurationResponseObjectFail@WindowsMidiServicesInternal@@YAXAEAUJsonObject@Json@Data@Windows@winrt@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::SetConfigurationResponseObjectFail(winrt::Windows::Data::Json::JsonObject &,std::wstring)
0x18001dd11  nop
0x18001dd12  lea     rcx, [rbp+57h+var_18]
0x18001dd16  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18001dd1b  lea     rcx, [rbp+57h+var_38]; void *
0x18001dd1f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001dd24  xor     eax, eax
0x18001dd26  mov     rcx, [rbp+57h+var_8]
0x18001dd2a  xor     rcx, rsp; StackCookie
0x18001dd2d  call    __security_check_cookie
0x18001dd32  lea     r11, [rsp+0B0h+var_s0]
0x18001dd3a  mov     rbx, [r11+10h]
0x18001dd3e  mov     rdi, [r11+18h]
0x18001dd42  mov     rsp, r11
0x18001dd45  pop     rbp
0x18001dd46  retn
```
