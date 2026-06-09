# web::http::oauth1::experimental::oauth1_config::_build_signature_base_string(web::http::http_request,web::http::oauth1::details::oauth1_state)

- ea: `0x18004c280`
- end: `0x18004c58a`
- name: `?_build_signature_base_string@oauth1_config@experimental@oauth1@http@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vhttp_request@45@Voauth1_state@details@345@@Z`
- size: `778`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18004b998`

## callees

- `0x180002c2c`
- `0x180004fa0`
- `0x180009730`
- `0x18000a228`
- `0x18000fc54`
- `0x1800148ac`
- `0x1800167f8`
- `0x1800177f8`
- `0x180019858`
- `0x18001a384`
- `0x18001a6ec`
- `0x18001adbc`
- `0x18001adf0`
- `0x18001b200`
- `0x18001d928`
- `0x180033b04`
- `0x18003416c`
- `0x18004b860`
- `0x18004bb6c`
- `0x18004c280`
- `0x18004d2ec`
- `0x18004d4fc`
- `0x18004e2e0`
- `0x18004eca0`
- `0x180050940`
- `0x180050bd0`

## import_xrefs

- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18004c2f2`
- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18004c2f2`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18004c303`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18004c303`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall web::http::oauth1::experimental::oauth1_config::_build_signature_base_string(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        web::http::oauth1::details::oauth1_state *a4)
{
  char *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rbx
  _QWORD *string; // rax
  __int64 v14; // rax
  __int64 appended; // rax
  web::uri *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  _BYTE *v19; // rcx
  web::uri *v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  std::_Ref_count_base *v23; // rcx
  _BYTE v25[24]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD *v26; // [rsp+38h] [rbp-C8h]
  _BYTE v27[8]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v30[232]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v31[232]; // [rsp+140h] [rbp+40h] BYREF
  web::http::oauth1::details::oauth1_state *v32; // [rsp+228h] [rbp+128h]
  _BYTE v33[32]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v34[32]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v35[240]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v36[208]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v37[32]; // [rsp+430h] [rbp+330h] BYREF
  _BYTE v38[208]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v39[240]; // [rsp+520h] [rbp+420h] BYREF

  v26 = a3;
  v32 = a4;
  web::http::details::_http_request::absolute_uri(*a3, v35);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v29);
  v8 = &v30[*(int *)(v29 + 4) - 8];
  v9 = std::locale::classic();
  std::basic_ios<unsigned short>::imbue(v8, v25, v9);
  std::locale::~locale((std::locale *)v25);
  std::operator<<<unsigned short>(&v29, *a3 + 96LL);
  v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v29, "&");
  v11 = web::http::oauth1::experimental::oauth1_config::_build_base_string_uri(v33, v35);
  std::operator<<<unsigned short>(v10, v11);
  std::wstring::_Tidy_deallocate(v33);
  std::map<std::wstring,std::wstring,web::http::http_headers::_case_insensitive_cmp,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring const &,>(
    *a3 + 40LL,
    v27,
    web::http::header_names::content_type);
  std::wstring::wstring(v33);
  v12 = std::wstring::find(v33, web::http::details::mime_types::application_x_www_form_urlencoded, 0);
  std::wstring::_Tidy_deallocate(v33);
  if ( v12 )
  {
    v20 = (web::uri *)web::uri::uri(v31, v35);
    v21 = web::http::oauth1::experimental::oauth1_config::_build_normalized_parameters(
            a1,
            (__int64)v34,
            v20,
            (__int64)a4);
    v22 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v29, "&");
    std::operator<<<unsigned short>(v22, v21);
    v19 = v34;
  }
  else
  {
    string = (_QWORD *)web::http::http_request::extract_string(a3, v27);
    pplx::task<std::wstring>::get(string, (__int64)v33);
    if ( v28 )
      std::_Ref_count_base::_Decref(v28);
    v14 = std::wstring::wstring(v34);
    web::http::http_request::set_body(a3, v33, v14);
    web::http::details::_http_request::absolute_uri(*a3, v37);
    web::details::uri_components::uri_components(
      (web::details::uri_components *)v36,
      (const struct web::details::uri_components *)v38);
    appended = web::uri_builder::append_query(v36, v33, 0);
    web::uri_builder::to_uri(appended, v39);
    web::details::uri_components::~uri_components((web::details::uri_components *)v36);
    web::uri::~uri((web::uri *)v37);
    v16 = (web::uri *)web::uri::uri(v31, v39);
    v17 = web::http::oauth1::experimental::oauth1_config::_build_normalized_parameters(
            a1,
            (__int64)v34,
            v16,
            (__int64)a4);
    v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v29, "&");
    std::operator<<<unsigned short>(v18, v17);
    std::wstring::_Tidy_deallocate(v34);
    web::uri::~uri((web::uri *)v39);
    v19 = v33;
  }
  std::wstring::_Tidy_deallocate(v19);
  std::basic_stringbuf<unsigned short>::str(v30, a2);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(&v29);
  web::uri::~uri((web::uri *)v35);
  v23 = (std::_Ref_count_base *)a3[1];
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  web::http::oauth1::details::oauth1_state::~oauth1_state(a4);
  return a2;
}

```

## disassembly

```asm
0x18004c280  push    rbp
0x18004c282  push    rbx
0x18004c283  push    rsi
0x18004c284  push    rdi
0x18004c285  push    r14
0x18004c287  push    r15
0x18004c289  lea     rbp, [rsp-528h]
0x18004c291  sub     rsp, 628h
0x18004c298  mov     rax, cs:__security_cookie
0x18004c29f  xor     rax, rsp
0x18004c2a2  mov     [rbp+550h+var_40], rax
0x18004c2a9  mov     rsi, r9
0x18004c2ac  mov     rdi, r8
0x18004c2af  mov     r14, rdx
0x18004c2b2  mov     r15, rcx
0x18004c2b5  mov     [rsp+650h+var_618], rdx
0x18004c2ba  mov     [rsp+650h+var_618], r8
0x18004c2bf  mov     [rbp+550h+var_428], r9
0x18004c2c6  lea     rdx, [rbp+550h+var_3E0]
0x18004c2cd  mov     rcx, [r8]
0x18004c2d0  call    ?absolute_uri@_http_request@details@http@web@@QEBA?AVuri@4@XZ; web::http::details::_http_request::absolute_uri(void)
0x18004c2d5  nop
0x18004c2d6  lea     rcx, [rsp+650h+var_600]
0x18004c2db  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18004c2e0  nop
0x18004c2e1  mov     rax, [rsp+650h+var_600]
0x18004c2e6  movsxd  rcx, dword ptr [rax+4]
0x18004c2ea  lea     rbx, [rsp+650h+var_600]
0x18004c2ef  add     rbx, rcx
0x18004c2f2  call    cs:__imp_?classic@locale@std@@SAAEBV12@XZ; std::locale::classic(void)
0x18004c2f8  mov     r8, rax
0x18004c2fb  lea     rdx, [rsp+650h+var_630]
0x18004c300  mov     rcx, rbx
0x18004c303  call    cs:__imp_?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z; std::basic_ios<ushort>::imbue(std::locale const &)
0x18004c309  lea     rcx, [rsp+650h+var_630]; this
0x18004c30e  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18004c313  mov     rdx, [rdi]
0x18004c316  add     rdx, 60h ; '`'
0x18004c31a  lea     rcx, [rsp+650h+var_600]
0x18004c31f  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18004c324  lea     rdx, asc_180069AAC; "&"
0x18004c32b  lea     rcx, [rsp+650h+var_600]
0x18004c330  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18004c335  mov     rbx, rax
0x18004c338  lea     rdx, [rbp+550h+var_3E0]
0x18004c33f  lea     rcx, [rbp+550h+var_420]
0x18004c346  call    ?_build_base_string_uri@oauth1_config@experimental@oauth1@http@web@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVuri@5@@Z; web::http::oauth1::experimental::oauth1_config::_build_base_string_uri(web::uri const &)
0x18004c34b  nop
0x18004c34c  mov     rdx, rax
0x18004c34f  mov     rcx, rbx
0x18004c352  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18004c357  nop
0x18004c358  lea     rcx, [rbp+550h+var_420]
0x18004c35f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004c364  mov     rcx, [rdi]
0x18004c367  add     rcx, 28h ; '('
0x18004c36b  lea     r8, ?content_type@header_names@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::header_names::content_type
0x18004c372  lea     rdx, [rsp+650h+var_610]
0x18004c377  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U_case_insensitive_cmp@http_headers@http@web@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring,web::http::http_headers::_case_insensitive_cmp,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18004c37c  mov     rdx, [rax]
0x18004c37f  add     rdx, 40h ; '@'
0x18004c383  lea     rcx, [rbp+550h+var_420]
0x18004c38a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004c38f  xor     r8d, r8d
0x18004c392  lea     rdx, ?application_x_www_form_urlencoded@mime_types@details@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::details::mime_types::application_x_www_form_urlencoded
0x18004c399  lea     rcx, [rbp+550h+var_420]
0x18004c3a0  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x18004c3a5  mov     rbx, rax
0x18004c3a8  lea     rcx, [rbp+550h+var_420]
0x18004c3af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004c3b4  test    rbx, rbx
0x18004c3b7  jnz     loc_18004C4DA
0x18004c3bd  lea     rdx, [rsp+650h+var_610]
0x18004c3c2  mov     rcx, rdi
0x18004c3c5  call    ?extract_string@http_request@http@web@@QEAA?AV?$task@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@pplx@@_N@Z; web::http::http_request::extract_string(bool)
0x18004c3ca  nop
0x18004c3cb  lea     rdx, [rbp+550h+var_420]
0x18004c3d2  mov     rcx, rax
0x18004c3d5  call    ?get@?$task@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@pplx@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; pplx::task<std::wstring>::get(void)
0x18004c3da  nop
0x18004c3db  mov     rcx, [rsp+650h+var_608]; this
0x18004c3e0  test    rcx, rcx
0x18004c3e3  jz      short loc_18004C3EA
0x18004c3e5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004c3ea  lea     rdx, ?application_x_www_form_urlencoded@mime_types@details@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::details::mime_types::application_x_www_form_urlencoded
0x18004c3f1  lea     rcx, [rbp+550h+var_400]
0x18004c3f8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004c3fd  mov     r8, rax
0x18004c400  lea     rdx, [rbp+550h+var_420]
0x18004c407  mov     rcx, rdi
0x18004c40a  call    ?set_body@http_request@http@web@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@@Z; web::http::http_request::set_body(std::wstring const &,std::wstring)
0x18004c40f  lea     rdx, [rbp+550h+var_220]
0x18004c416  mov     rcx, [rdi]
0x18004c419  call    ?absolute_uri@_http_request@details@http@web@@QEBA?AVuri@4@XZ; web::http::details::_http_request::absolute_uri(void)
0x18004c41e  nop
0x18004c41f  lea     rdx, [rbp+550h+var_200]; struct web::details::uri_components *
0x18004c426  lea     rcx, [rbp+550h+var_2F0]; this
0x18004c42d  call    ??0uri_components@details@web@@QEAA@AEBU012@@Z; web::details::uri_components::uri_components(web::details::uri_components const &)
0x18004c432  nop
0x18004c433  xor     r8d, r8d
0x18004c436  lea     rdx, [rbp+550h+var_420]
0x18004c43d  lea     rcx, [rbp+550h+var_2F0]
0x18004c444  call    ?append_query@uri_builder@web@@QEAAAEAV12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; web::uri_builder::append_query(std::wstring const &,bool)
0x18004c449  lea     rdx, [rbp+550h+var_130]
0x18004c450  mov     rcx, rax
0x18004c453  call    ?to_uri@uri_builder@web@@QEAA?AVuri@2@XZ; web::uri_builder::to_uri(void)
0x18004c458  nop
0x18004c459  lea     rcx, [rbp+550h+var_2F0]; this
0x18004c460  call    ??1uri_components@details@web@@QEAA@XZ; web::details::uri_components::~uri_components(void)
0x18004c465  nop
0x18004c466  lea     rcx, [rbp+550h+var_220]; this
0x18004c46d  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x18004c472  lea     rdx, [rbp+550h+var_130]
0x18004c479  lea     rcx, [rbp+550h+var_510]
0x18004c47d  call    ??0uri@web@@QEAA@$$QEAV01@@Z; web::uri::uri(web::uri &&)
0x18004c482  mov     r9, rsi
0x18004c485  mov     r8, rax
0x18004c488  lea     rdx, [rbp+550h+var_400]
0x18004c48f  mov     rcx, r15
0x18004c492  call    ?_build_normalized_parameters@oauth1_config@experimental@oauth1@http@web@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vuri@5@AEBVoauth1_state@details@345@@Z; web::http::oauth1::experimental::oauth1_config::_build_normalized_parameters(web::uri,web::http::oauth1::details::oauth1_state const &)
0x18004c497  mov     rbx, rax
0x18004c49a  lea     rdx, asc_180069AAC; "&"
0x18004c4a1  lea     rcx, [rsp+650h+var_600]
0x18004c4a6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18004c4ab  mov     rdx, rbx
0x18004c4ae  mov     rcx, rax
0x18004c4b1  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18004c4b6  nop
0x18004c4b7  lea     rcx, [rbp+550h+var_400]
0x18004c4be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004c4c3  nop
0x18004c4c4  lea     rcx, [rbp+550h+var_130]; this
0x18004c4cb  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x18004c4d0  nop
0x18004c4d1  lea     rcx, [rbp+550h+var_420]
0x18004c4d8  jmp     short loc_18004C526
0x18004c4da  lea     rdx, [rbp+550h+var_3E0]
0x18004c4e1  lea     rcx, [rbp+550h+var_510]
0x18004c4e5  call    ??0uri@web@@QEAA@$$QEAV01@@Z; web::uri::uri(web::uri &&)
0x18004c4ea  mov     r9, rsi
0x18004c4ed  mov     r8, rax
0x18004c4f0  lea     rdx, [rbp+550h+var_400]
0x18004c4f7  mov     rcx, r15
0x18004c4fa  call    ?_build_normalized_parameters@oauth1_config@experimental@oauth1@http@web@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vuri@5@AEBVoauth1_state@details@345@@Z; web::http::oauth1::experimental::oauth1_config::_build_normalized_parameters(web::uri,web::http::oauth1::details::oauth1_state const &)
0x18004c4ff  mov     rbx, rax
0x18004c502  lea     rdx, asc_180069AAC; "&"
0x18004c509  lea     rcx, [rsp+650h+var_600]
0x18004c50e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18004c513  mov     rdx, rbx
0x18004c516  mov     rcx, rax
0x18004c519  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18004c51e  nop
0x18004c51f  lea     rcx, [rbp+550h+var_400]
0x18004c526  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004c52b  mov     rdx, r14
0x18004c52e  lea     rcx, [rsp+650h+var_5F8]
0x18004c533  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18004c538  nop
0x18004c539  lea     rcx, [rsp+650h+var_600]
0x18004c53e  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18004c543  nop
0x18004c544  lea     rcx, [rbp+550h+var_3E0]; this
0x18004c54b  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x18004c550  nop
0x18004c551  mov     rcx, [rdi+8]; this
0x18004c555  test    rcx, rcx
0x18004c558  jz      short loc_18004C560
0x18004c55a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004c55f  nop
0x18004c560  mov     rcx, rsi; this
0x18004c563  call    ??1oauth1_state@details@oauth1@http@web@@QEAA@XZ; web::http::oauth1::details::oauth1_state::~oauth1_state(void)
0x18004c568  mov     rax, r14
0x18004c56b  mov     rcx, [rbp+550h+var_40]
0x18004c572  xor     rcx, rsp; StackCookie
0x18004c575  call    __security_check_cookie
0x18004c57a  add     rsp, 628h
0x18004c581  pop     r15
0x18004c583  pop     r14
0x18004c585  pop     rdi
0x18004c586  pop     rsi
0x18004c587  pop     rbx
0x18004c588  pop     rbp
0x18004c589  retn
```
