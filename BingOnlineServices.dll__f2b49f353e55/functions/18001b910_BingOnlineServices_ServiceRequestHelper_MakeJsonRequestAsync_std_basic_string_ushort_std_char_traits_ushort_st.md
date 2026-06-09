# BingOnlineServices::ServiceRequestHelper::MakeJsonRequestAsync(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &)

- ea: `0x18001b910`
- end: `0x18001bd38`
- name: `?MakeJsonRequestAsync@ServiceRequestHelper@BingOnlineServices@@SA?AV?$task@UOnlineServiceResponse@BingOnlineServices@@@pplx@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@1@Z`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001bd40`

## callees

- `0x180002c2c`
- `0x180002ca8`
- `0x180004fa0`
- `0x180009730`
- `0x180009778`
- `0x18000a020`
- `0x18000e5a8`
- `0x18000fa74`
- `0x180011ad4`
- `0x180014368`
- `0x1800148ac`
- `0x180019920`
- `0x180019a1c`
- `0x18001a1b8`
- `0x18001a268`
- `0x18001a510`
- `0x18001a534`
- `0x18001a5fc`
- `0x18001a6ac`
- `0x18001a6ec`
- `0x18001a778`
- `0x18001a820`
- `0x18001ad68`
- `0x18001adbc`
- `0x18001adf0`
- `0x18001ae40`
- `0x18001af14`
- `0x18001b910`
- `0x18001d828`
- `0x18001deec`
- `0x180030070`
- `0x180033650`
- `0x180034384`
- `0x18003cc20`
- `0x18003cd00`
- `0x18004f010`
- `0x180050b60`
- `0x180056f20`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001bab2`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001bab2`

## string_xrefs

- `0x18001baeb`: `application/json`
- `0x18001ba9a`: `[ServiceRequestHelper::MakeJsonRequestAsync] HTTP Request: %ls`
- `0x18001baa7`: `BingOnlineServices::ServiceRequestHelper::MakeJsonRequestAsync`
- `0x18001bb26`: ` MapsBroker`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall BingOnlineServices::ServiceRequestHelper::MakeJsonRequestAsync(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 **a4,
        __int64 **a5)
{
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  const wchar_t *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  _QWORD v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v24; // [rsp+48h] [rbp-B8h]
  _BYTE v25[8]; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v26; // [rsp+58h] [rbp-A8h]
  _BYTE v27[8]; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v28; // [rsp+70h] [rbp-90h]
  _QWORD v29[4]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v30[40]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v31[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v32[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v33[272]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v34[208]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v35[232]; // [rsp+310h] [rbp+210h] BYREF
  int v36; // [rsp+3F8h] [rbp+2F8h]
  _BYTE v37[64]; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v38[240]; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v39[240]; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v40[512]; // [rsp+620h] [rbp+520h] BYREF

  v22[0] = a1;
  web::uri::uri((web::uri *)v35, &word_18006739C);
  v36 = 0;
  web::credentials::credentials((web::credentials *)v37);
  web::http::client::http_client_config::http_client_config((web::http::client::http_client_config *)v40);
  v9 = web::web_proxy::web_proxy((web::web_proxy *)v32, (const struct web::web_proxy *)v35);
  web::http::client::http_client_config::set_proxy(v40, v9);
  web::uri::uri(v38, a2);
  web::http::client::http_client::http_client(
    (web::http::client::http_client *)v25,
    (const struct web::uri *)v38,
    (const struct web::http::client::http_client_config *)v40);
  web::uri::~uri((web::uri *)v38);
  web::uri::uri(v32, a3);
  web::details::uri_components::uri_components(
    (web::details::uri_components *)v34,
    (const struct web::details::uri_components *)v33);
  web::uri::~uri((web::uri *)v32);
  v10 = **a4;
  v22[0] = v10;
  while ( !*(_BYTE *)(v10 + 25) )
  {
    std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(v31, v10 + 32);
    std::wstring::wstring(v29);
    std::wstring::wstring(v27);
    web::uri_builder::append_query<std::wstring>((__int64)v34, (__int64)v29, (__int64)v27);
    std::wstring::_Tidy_deallocate(v27);
    std::wstring::_Tidy_deallocate(v29);
    std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v31);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(v22);
    v10 = v22[0];
  }
  v11 = web::uri_builder::to_string(v34, v27);
  v12 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
  ZTraceHelperNoThis(
    5,
    "BingOnlineServices::ServiceRequestHelper::MakeJsonRequestAsync",
    75,
    "[ServiceRequestHelper::MakeJsonRequestAsync] HTTP Request: %ls",
    v12);
  std::wstring::_Tidy_deallocate(v27);
  v13 = std::wstring::wstring(v27);
  web::http::http_request::http_request(&v23, v13);
  v14 = v23;
  v15 = v23 + 40;
  v16 = std::wstring::wstring(v29, L"application/json");
  web::http::http_headers::set_content_type(v15, v16);
  std::wstring::wstring(v30);
  if ( (int)MapPlatformConfig::GetHttpUserAgent(v30) >= 0 )
  {
    if ( BingOnlineServices::ServiceRequestHelper::s_runningInService )
      std::wstring::append(v30, L" MapsBroker");
    web::http::http_headers::add<std::wstring>(v15, web::http::header_names::user_agent, v30);
  }
  v17 = **a5;
  v22[0] = v17;
  while ( !*(_BYTE *)(v17 + 25) )
  {
    std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(v31, v17 + 32);
    std::wstring::wstring(v29);
    std::wstring::wstring(v27);
    web::http::http_headers::add<std::wstring>(v15, v29, v27);
    std::wstring::_Tidy_deallocate(v27);
    std::wstring::_Tidy_deallocate(v29);
    std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v31);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(v22);
    v17 = v22[0];
  }
  v18 = web::uri_builder::to_string(v34, v27);
  web::uri::uri(v32, v18);
  web::uri::operator=(v14 + 384);
  web::uri::~uri((web::uri *)v32);
  std::wstring::_Tidy_deallocate(v27);
  web::uri::uri((web::uri *)v39, (const struct web::uri *)(v14 + 384));
  v22[0] = BingOnlineServices::ServiceRequestHelper::s_cancellationToken;
  if ( BingOnlineServices::ServiceRequestHelper::s_cancellationToken == 2 )
  {
    v22[0] = 0;
  }
  else if ( BingOnlineServices::ServiceRequestHelper::s_cancellationToken )
  {
    _InterlockedIncrement((volatile signed __int32 *)(BingOnlineServices::ServiceRequestHelper::s_cancellationToken + 8LL));
  }
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(v29, &v23);
  v19 = web::http::client::http_client::request((web::http::client::http_client *)v25);
  v20 = lambda_b050aac3426548293d09736fe94d5921_::_lambda_b050aac3426548293d09736fe94d5921_(v32, a2, v39);
  pplx::task_web::http::http_response_::then__lambda_b050aac3426548293d09736fe94d5921___(v19, a1, v20);
  lambda_b050aac3426548293d09736fe94d5921_::__lambda_b050aac3426548293d09736fe94d5921_(v32);
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  pplx::cancellation_token_registration::_Clear((pplx::cancellation_token_registration *)v22);
  web::uri::~uri((web::uri *)v39);
  std::wstring::_Tidy_deallocate(v30);
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  web::details::uri_components::~uri_components((web::details::uri_components *)v34);
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v40);
  web::web_proxy::~web_proxy((web::web_proxy *)v35);
  return a1;
}

```

## disassembly

```asm
0x18001b910  push    rbp
0x18001b912  push    rbx
0x18001b913  push    rsi
0x18001b914  push    rdi
0x18001b915  push    r14
0x18001b917  lea     rbp, [rsp-730h]
0x18001b91f  sub     rsp, 830h
0x18001b926  mov     rax, cs:__security_cookie
0x18001b92d  xor     rax, rsp
0x18001b930  mov     [rbp+750h+var_30], rax
0x18001b937  mov     rdi, r9
0x18001b93a  mov     rbx, r8
0x18001b93d  mov     r14, rdx
0x18001b940  mov     rsi, rcx
0x18001b943  mov     [rsp+850h+var_820], rcx
0x18001b948  lea     rdx, word_18006739C; unsigned __int16 *
0x18001b94f  lea     rcx, [rbp+750h+var_540]; this
0x18001b956  call    ??0uri@web@@QEAA@PEBG@Z; web::uri::uri(ushort const *)
0x18001b95b  mov     [rbp+750h+var_458], 0
0x18001b965  lea     rcx, [rbp+750h+var_450]; this
0x18001b96c  call    ??0credentials@web@@QEAA@XZ; web::credentials::credentials(void)
0x18001b971  nop
0x18001b972  lea     rcx, [rbp+750h+var_230]; this
0x18001b979  call    ??0http_client_config@client@http@web@@QEAA@XZ; web::http::client::http_client_config::http_client_config(void)
0x18001b97e  nop
0x18001b97f  lea     rdx, [rbp+750h+var_540]; struct web::web_proxy *
0x18001b986  lea     rcx, [rbp+750h+var_740]; this
0x18001b98a  call    ??0web_proxy@web@@QEAA@AEBV01@@Z; web::web_proxy::web_proxy(web::web_proxy const &)
0x18001b98f  mov     rdx, rax
0x18001b992  lea     rcx, [rbp+750h+var_230]
0x18001b999  call    ?set_proxy@http_client_config@client@http@web@@QEAAXVweb_proxy@4@@Z; web::http::client::http_client_config::set_proxy(web::web_proxy)
0x18001b99e  mov     rdx, r14
0x18001b9a1  lea     rcx, [rbp+750h+var_410]
0x18001b9a8  call    ??0uri@web@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::uri::uri(std::wstring const &)
0x18001b9ad  nop
0x18001b9ae  lea     r8, [rbp+750h+var_230]; struct web::http::client::http_client_config *
0x18001b9b5  lea     rdx, [rbp+750h+var_410]; struct web::uri *
0x18001b9bc  lea     rcx, [rsp+850h+var_800]; this
0x18001b9c1  call    ??0http_client@client@http@web@@QEAA@AEBVuri@3@AEBVhttp_client_config@123@@Z; web::http::client::http_client::http_client(web::uri const &,web::http::client::http_client_config const &)
0x18001b9c6  nop
0x18001b9c7  lea     rcx, [rbp+750h+var_410]; this
0x18001b9ce  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x18001b9d3  mov     rdx, rbx
0x18001b9d6  lea     rcx, [rbp+750h+var_740]
0x18001b9da  call    ??0uri@web@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::uri::uri(std::wstring const &)
0x18001b9df  nop
0x18001b9e0  lea     rdx, [rbp+750h+var_720]; struct web::details::uri_components *
0x18001b9e4  lea     rcx, [rbp+750h+var_610]; this
0x18001b9eb  call    ??0uri_components@details@web@@QEAA@AEBU012@@Z; web::details::uri_components::uri_components(web::details::uri_components const &)
0x18001b9f0  nop
0x18001b9f1  lea     rcx, [rbp+750h+var_740]; this
0x18001b9f5  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x18001b9fa  mov     rdx, [rdi]
0x18001b9fd  mov     rdx, [rdx]
0x18001ba00  mov     [rsp+850h+var_820], rdx
0x18001ba05  cmp     byte ptr [rdx+19h], 0
0x18001ba09  jnz     short loc_18001BA7B
0x18001ba0b  add     rdx, 20h ; ' '
0x18001ba0f  lea     rcx, [rbp+750h+var_780]
0x18001ba13  call    ??0?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@AEBU01@@Z; std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(std::pair<std::wstring const,std::wstring> const &)
0x18001ba18  nop
0x18001ba19  lea     rdx, [rbp+750h+var_780]
0x18001ba1d  lea     rcx, [rbp+750h+var_7C8]
0x18001ba21  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ba26  nop
0x18001ba27  lea     rdx, [rbp+750h+var_760]
0x18001ba2b  lea     rcx, [rsp+850h+var_7E8]
0x18001ba30  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ba35  nop
0x18001ba36  lea     r8, [rsp+850h+var_7E8]
0x18001ba3b  lea     rdx, [rbp+750h+var_7C8]
0x18001ba3f  lea     rcx, [rbp+750h+var_610]
0x18001ba46  call    ??$append_query@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@uri_builder@web@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; web::uri_builder::append_query<std::wstring>(std::wstring const &,std::wstring const &,bool)
0x18001ba4b  nop
0x18001ba4c  lea     rcx, [rsp+850h+var_7E8]
0x18001ba51  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ba56  nop
0x18001ba57  lea     rcx, [rbp+750h+var_7C8]
0x18001ba5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ba60  nop
0x18001ba61  lea     rcx, [rbp+750h+var_780]
0x18001ba65  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x18001ba6a  lea     rcx, [rsp+850h+var_820]
0x18001ba6f  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x18001ba74  mov     rdx, [rsp+850h+var_820]
0x18001ba79  jmp     short loc_18001BA05
0x18001ba7b  lea     rdx, [rsp+850h+var_7E8]
0x18001ba80  lea     rcx, [rbp+750h+var_610]
0x18001ba87  call    ?to_string@uri_builder@web@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::uri_builder::to_string(void)
0x18001ba8c  nop
0x18001ba8d  mov     rcx, rax
0x18001ba90  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ba95  mov     [rsp+850h+var_830], rax
0x18001ba9a  lea     r9, aServicerequest_0; "[ServiceRequestHelper::MakeJsonRequestA"...
0x18001baa1  mov     r8d, 4Bh ; 'K'
0x18001baa7  lea     rdx, aBingonlineserv_2; "BingOnlineServices::ServiceRequestHelpe"...
0x18001baae  lea     ecx, [r8-46h]
0x18001bab2  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18001bab8  nop
0x18001bab9  lea     rcx, [rsp+850h+var_7E8]
0x18001babe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bac3  lea     rdx, ?GET@methods@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::methods::GET
0x18001baca  lea     rcx, [rsp+850h+var_7E8]
0x18001bacf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001bad4  mov     rdx, rax
0x18001bad7  lea     rcx, [rsp+850h+var_810]
0x18001badc  call    ??0http_request@http@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::http_request::http_request(std::wstring)
0x18001bae1  nop
0x18001bae2  mov     rdi, [rsp+850h+var_810]
0x18001bae7  lea     rbx, [rdi+28h]
0x18001baeb  lea     rdx, aApplicationJso_0; "application/json"
0x18001baf2  lea     rcx, [rbp+750h+var_7C8]
0x18001baf6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001bafb  mov     rdx, rax
0x18001bafe  mov     rcx, rbx
0x18001bb01  call    ?set_content_type@http_headers@http@web@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::http_headers::set_content_type(std::wstring)
0x18001bb06  lea     rcx, [rbp+750h+var_7A8]
0x18001bb0a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001bb0f  nop
0x18001bb10  lea     rcx, [rbp+750h+var_7A8]
0x18001bb14  call    ?GetHttpUserAgent@MapPlatformConfig@@SAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapPlatformConfig::GetHttpUserAgent(std::wstring *)
0x18001bb19  test    eax, eax
0x18001bb1b  js      short loc_18001BB49
0x18001bb1d  cmp     cs:?s_runningInService@ServiceRequestHelper@BingOnlineServices@@0_NA, 0; bool BingOnlineServices::ServiceRequestHelper::s_runningInService
0x18001bb24  jz      short loc_18001BB36
0x18001bb26  lea     rdx, aMapsbroker; " MapsBroker"
0x18001bb2d  lea     rcx, [rbp+750h+var_7A8]
0x18001bb31  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001bb36  lea     r8, [rbp+750h+var_7A8]
0x18001bb3a  lea     rdx, ?user_agent@header_names@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::header_names::user_agent
0x18001bb41  mov     rcx, rbx
0x18001bb44  call    ??$add@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@http_headers@http@web@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; web::http::http_headers::add<std::wstring>(std::wstring const &,std::wstring const &)
0x18001bb49  mov     rax, [rbp+750h+arg_20]
0x18001bb50  mov     rdx, [rax]
0x18001bb53  mov     rdx, [rdx]
0x18001bb56  mov     [rsp+850h+var_820], rdx
0x18001bb5b  cmp     byte ptr [rdx+19h], 0
0x18001bb5f  jnz     short loc_18001BBCD
0x18001bb61  add     rdx, 20h ; ' '
0x18001bb65  lea     rcx, [rbp+750h+var_780]
0x18001bb69  call    ??0?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@AEBU01@@Z; std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(std::pair<std::wstring const,std::wstring> const &)
0x18001bb6e  nop
0x18001bb6f  lea     rdx, [rbp+750h+var_780]
0x18001bb73  lea     rcx, [rbp+750h+var_7C8]
0x18001bb77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001bb7c  nop
0x18001bb7d  lea     rdx, [rbp+750h+var_760]
0x18001bb81  lea     rcx, [rsp+850h+var_7E8]
0x18001bb86  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001bb8b  nop
0x18001bb8c  lea     r8, [rsp+850h+var_7E8]
0x18001bb91  lea     rdx, [rbp+750h+var_7C8]
0x18001bb95  mov     rcx, rbx
0x18001bb98  call    ??$add@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@http_headers@http@web@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; web::http::http_headers::add<std::wstring>(std::wstring const &,std::wstring const &)
0x18001bb9d  nop
0x18001bb9e  lea     rcx, [rsp+850h+var_7E8]
0x18001bba3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bba8  nop
0x18001bba9  lea     rcx, [rbp+750h+var_7C8]
0x18001bbad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bbb2  nop
0x18001bbb3  lea     rcx, [rbp+750h+var_780]
0x18001bbb7  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x18001bbbc  lea     rcx, [rsp+850h+var_820]
0x18001bbc1  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x18001bbc6  mov     rdx, [rsp+850h+var_820]
0x18001bbcb  jmp     short loc_18001BB5B
0x18001bbcd  lea     rdx, [rsp+850h+var_7E8]
0x18001bbd2  lea     rcx, [rbp+750h+var_610]
0x18001bbd9  call    ?to_string@uri_builder@web@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::uri_builder::to_string(void)
0x18001bbde  nop
0x18001bbdf  mov     rdx, rax
0x18001bbe2  lea     rcx, [rbp+750h+var_740]
0x18001bbe6  call    ??0uri@web@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::uri::uri(std::wstring const &)
0x18001bbeb  nop
0x18001bbec  lea     rbx, [rdi+180h]
0x18001bbf3  lea     rdx, [rbp+750h+var_740]
0x18001bbf7  mov     rcx, rbx
0x18001bbfa  call    ??4uri@web@@QEAAAEAV01@AEBV01@@Z; web::uri::operator=(web::uri const &)
0x18001bbff  nop
0x18001bc00  lea     rcx, [rbp+750h+var_740]; this
0x18001bc04  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x18001bc09  nop
0x18001bc0a  lea     rcx, [rsp+850h+var_7E8]
0x18001bc0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bc14  mov     rdx, rbx; struct web::uri *
0x18001bc17  lea     rcx, [rbp+750h+var_320]; this
0x18001bc1e  call    ??0uri@web@@QEAA@AEBV01@@Z; web::uri::uri(web::uri const &)
0x18001bc23  nop
0x18001bc24  mov     rax, cs:?s_cancellationToken@ServiceRequestHelper@BingOnlineServices@@0Vcancellation_token_source@pplx@@A; pplx::cancellation_token_source BingOnlineServices::ServiceRequestHelper::s_cancellationToken
0x18001bc2b  mov     [rsp+850h+var_820], rax
0x18001bc30  cmp     rax, 2
0x18001bc34  jnz     short loc_18001BC41
0x18001bc36  mov     [rsp+850h+var_820], 0
0x18001bc3f  jmp     short loc_18001BC4A
0x18001bc41  test    rax, rax
0x18001bc44  jz      short loc_18001BC4A
0x18001bc46  lock inc dword ptr [rax+8]
0x18001bc4a  lea     rdx, [rsp+850h+var_810]
0x18001bc4f  lea     rcx, [rbp+750h+var_7C8]
0x18001bc53  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18001bc58  lea     r9, [rsp+850h+var_820]
0x18001bc5d  lea     r8, [rbp+750h+var_7C8]
0x18001bc61  lea     rdx, [rsp+850h+var_7E8]
0x18001bc66  lea     rcx, [rsp+850h+var_800]; this
0x18001bc6b  call    ?request@http_client@client@http@web@@QEAA?AV?$task@Vhttp_response@http@web@@@pplx@@Vhttp_request@34@AEBVcancellation_token@6@@Z; web::http::client::http_client::request(web::http::http_request,pplx::cancellation_token const &)
0x18001bc70  mov     rbx, rax
0x18001bc73  lea     r8, [rbp+750h+var_320]
0x18001bc7a  mov     rdx, r14
0x18001bc7d  lea     rcx, [rbp+750h+var_740]
0x18001bc81  call    _lambda_b050aac3426548293d09736fe94d5921____lambda_b050aac3426548293d09736fe94d5921_
0x18001bc86  nop
0x18001bc87  mov     r8, rax
0x18001bc8a  mov     rdx, rsi
0x18001bc8d  mov     rcx, rbx
0x18001bc90  call    pplx__task_web__http__http_response___then__lambda_b050aac3426548293d09736fe94d5921___
0x18001bc95  nop
0x18001bc96  lea     rcx, [rbp+750h+var_740]
0x18001bc9a  call    _lambda_b050aac3426548293d09736fe94d5921_____lambda_b050aac3426548293d09736fe94d5921_
0x18001bc9f  nop
0x18001bca0  mov     rcx, [rsp+850h+var_7E0]; this
0x18001bca5  test    rcx, rcx
0x18001bca8  jz      short loc_18001BCB0
0x18001bcaa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bcaf  nop
0x18001bcb0  lea     rcx, [rsp+850h+var_820]; this
0x18001bcb5  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x18001bcba  nop
0x18001bcbb  lea     rcx, [rbp+750h+var_320]; this
0x18001bcc2  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x18001bcc7  nop
0x18001bcc8  lea     rcx, [rbp+750h+var_7A8]
0x18001bccc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bcd1  nop
0x18001bcd2  mov     rcx, [rsp+850h+var_808]; this
0x18001bcd7  test    rcx, rcx
0x18001bcda  jz      short loc_18001BCE2
0x18001bcdc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bce1  nop
0x18001bce2  lea     rcx, [rbp+750h+var_610]; this
0x18001bce9  call    ??1uri_components@details@web@@QEAA@XZ; web::details::uri_components::~uri_components(void)
0x18001bcee  nop
0x18001bcef  mov     rcx, [rsp+850h+var_7F8]; this
0x18001bcf4  test    rcx, rcx
0x18001bcf7  jz      short loc_18001BCFF
0x18001bcf9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bcfe  nop
0x18001bcff  lea     rcx, [rbp+750h+var_230]; this
0x18001bd06  call    ??1http_client_config@client@http@web@@QEAA@XZ; web::http::client::http_client_config::~http_client_config(void)
0x18001bd0b  nop
0x18001bd0c  lea     rcx, [rbp+750h+var_540]; this
0x18001bd13  call    ??1web_proxy@web@@QEAA@XZ; web::web_proxy::~web_proxy(void)
0x18001bd18  mov     rax, rsi
0x18001bd1b  mov     rcx, [rbp+750h+var_30]
0x18001bd22  xor     rcx, rsp; StackCookie
0x18001bd25  call    __security_check_cookie
0x18001bd2a  add     rsp, 830h
0x18001bd31  pop     r14
0x18001bd33  pop     rdi
0x18001bd34  pop     rsi
0x18001bd35  pop     rbx
0x18001bd36  pop     rbp
0x18001bd37  retn
```
