# BingOnlineServices::ServiceRequestHelper::ProcessResponse(web::http::http_response const &)

- ea: `0x180002980`
- end: `0x180002c23`
- name: `?ProcessResponse@ServiceRequestHelper@BingOnlineServices@@SA?AV?$task@UOnlineServiceResponse@BingOnlineServices@@@pplx@@AEBVhttp_response@http@web@@@Z`
- size: `675`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task`

## callers

- `0x18001b024`

## callees

- `0x180002980`
- `0x180002c2c`
- `0x180002c6c`
- `0x180002ca8`
- `0x180002cec`
- `0x180002d50`
- `0x180002db0`
- `0x180002dfc`
- `0x180002e60`
- `0x180004fa0`
- `0x180009f14`
- `0x18000a2f4`
- `0x180011ad4`
- `0x180011c10`
- `0x18001235c`
- `0x180012990`
- `0x180012cc0`
- `0x1800148ac`
- `0x1800197a8`
- `0x180019f44`
- `0x18001a058`
- `0x18001af14`
- `0x18001b740`
- `0x18001d84c`
- `0x180040120`
- `0x180040450`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180002b28`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180002b96`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180002b28`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180002b96`

## string_xrefs

- `0x180002b16`: `[ServiceRequestHelper::ExtractJsonData] Extracting JSON data from HTTP response`
- `0x180002b08`: `BingOnlineServices::ServiceRequestHelper::ProcessResponse`
- `0x180002b84`: `[ServiceRequestHelper::ExtractJsonData] HTTP Error: Status: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall BingOnlineServices::ServiceRequestHelper::ProcessResponse(_QWORD *a1, __int64 *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 Cookies; // rax
  _QWORD *v10; // rbx
  _QWORD *v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  const struct pplx::task_options *v15; // rbx
  const struct BingOnlineServices::OnlineServiceResponse *v16; // rax
  _QWORD *v18; // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v19; // [rsp+38h] [rbp-C8h]
  char v20[136]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v21[32]; // [rsp+D0h] [rbp-30h] BYREF
  int v22; // [rsp+F0h] [rbp-10h] BYREF
  char v23[16]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD *v24; // [rsp+108h] [rbp+8h]
  char v25[32]; // [rsp+110h] [rbp+10h] BYREF
  char v26[32]; // [rsp+130h] [rbp+30h] BYREF
  char v27[32]; // [rsp+150h] [rbp+50h] BYREF
  char v28[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v29[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v30[112]; // [rsp+1A0h] [rbp+A0h] BYREF

  v18 = a1;
  BingOnlineServices::OnlineServiceResponse::OnlineServiceResponse((BingOnlineServices::OnlineServiceResponse *)&v22);
  v4 = *a2;
  v22 = *(unsigned __int16 *)(*a2 + 88);
  v18 = 0;
  web::http::http_headers::match<unsigned __int64>(v4 + 40, v5, &v18);
  v24 = v18;
  v6 = web::http::http_headers::content_type(*a2 + 40, v21);
  std::wstring::operator=(v25, v6);
  std::wstring::_Tidy_deallocate(v21);
  v7 = web::http::http_headers::cache_control(*a2 + 40, v21);
  std::wstring::operator=(v27, v7);
  std::wstring::_Tidy_deallocate(v21);
  v8 = *a2;
  std::wstring::wstring(v21, L"Set-Cookie");
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,web::http::http_headers::_case_insensitive_cmp,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
    v8 + 40,
    &v18,
    v21);
  std::wstring::_Tidy_deallocate(v21);
  if ( v18 != *(_QWORD **)(*a2 + 40) )
  {
    Cookies = BingOnlineServices::ServiceRequestHelper::ExtractCookies(v21, v18 + 8);
    std::wstring::operator=(v26, Cookies);
    std::wstring::_Tidy_deallocate(v21);
  }
  v10 = *(_QWORD **)(*a2 + 40);
  v11 = (_QWORD *)*v10;
  v18 = (_QWORD *)*v10;
  while ( v11 != v10 )
  {
    std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(v29, v11 + 4);
    v12 = (_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(v23, v21, v29);
    std::wstring::operator=(*v12 + 64LL, v30);
    std::wstring::_Tidy_deallocate(v30);
    std::wstring::_Tidy_deallocate(v29);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(&v18);
    v11 = v18;
  }
  if ( v22 == 200 )
  {
    ZTraceHelperNoThis(
      5,
      "BingOnlineServices::ServiceRequestHelper::ProcessResponse",
      166,
      "[ServiceRequestHelper::ExtractJsonData] Extracting JSON data from HTTP response");
    v13 = web::http::http_response::extract_json(a2, &v18);
    BingOnlineServices::OnlineServiceResponse::OnlineServiceResponse(
      (BingOnlineServices::OnlineServiceResponse *)v29,
      (const struct BingOnlineServices::OnlineServiceResponse *)&v22);
    pplx::task_web::json::value_::then__lambda_2928cf0dfdb8953a0e15861cab0d651e___(v13, a1, v29);
    BingOnlineServices::OnlineServiceResponse::~OnlineServiceResponse((BingOnlineServices::OnlineServiceResponse *)v29);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
  }
  else
  {
    ZTraceHelperNoThis(
      2,
      "BingOnlineServices::ServiceRequestHelper::ProcessResponse",
      177,
      "[ServiceRequestHelper::ExtractJsonData] HTTP Error: Status: %d",
      v22);
    v14 = web::json::value::value((web::json::value *)&v18);
    web::json::value::operator=(v28, v14);
    std::unique_ptr<web::json::details::_Number>::~unique_ptr<web::json::details::_Number>(&v18);
    v15 = (const struct pplx::task_options *)pplx::task_options::task_options((pplx::task_options *)v29);
    v16 = (const struct BingOnlineServices::OnlineServiceResponse *)BingOnlineServices::OnlineServiceResponse::OnlineServiceResponse(
                                                                      (BingOnlineServices::OnlineServiceResponse *)v20,
                                                                      (const struct BingOnlineServices::OnlineServiceResponse *)&v22);
    pplx::task_from_result<BingOnlineServices::OnlineServiceResponse>(a1, v16, v15);
    pplx::task_options::~task_options((pplx::task_options *)v29);
  }
  BingOnlineServices::OnlineServiceResponse::~OnlineServiceResponse((BingOnlineServices::OnlineServiceResponse *)&v22);
  return a1;
}

```

## disassembly

```asm
0x180002980  mov     [rsp-8+arg_10], rbx
0x180002985  push    rbp
0x180002986  push    rsi
0x180002987  push    rdi
0x180002988  lea     rbp, [rsp-120h]
0x180002990  sub     rsp, 220h
0x180002997  mov     rax, cs:__security_cookie
0x18000299e  xor     rax, rsp
0x1800029a1  mov     [rbp+130h+var_20], rax
0x1800029a8  mov     rdi, rdx
0x1800029ab  mov     rsi, rcx
0x1800029ae  mov     [rsp+230h+var_200], rcx
0x1800029b3  xor     ebx, ebx
0x1800029b5  lea     rcx, [rbp+130h+var_140]; this
0x1800029b9  call    ??0OnlineServiceResponse@BingOnlineServices@@QEAA@XZ; BingOnlineServices::OnlineServiceResponse::OnlineServiceResponse(void)
0x1800029be  nop
0x1800029bf  mov     rcx, [rdi]
0x1800029c2  movzx   eax, word ptr [rcx+58h]
0x1800029c6  mov     [rbp+130h+var_140], eax
0x1800029c9  mov     [rsp+230h+var_200], rbx
0x1800029ce  add     rcx, 28h ; '('
0x1800029d2  lea     r8, [rsp+230h+var_200]
0x1800029d7  call    ??$match@_K@http_headers@http@web@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_K@Z; web::http::http_headers::match<unsigned __int64>(std::wstring const &,unsigned __int64 &)
0x1800029dc  mov     rax, [rsp+230h+var_200]
0x1800029e1  mov     [rbp+130h+var_128], rax
0x1800029e5  mov     rcx, [rdi]
0x1800029e8  add     rcx, 28h ; '('
0x1800029ec  lea     rdx, [rbp+130h+var_160]
0x1800029f0  call    ?content_type@http_headers@http@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::http::http_headers::content_type(void)
0x1800029f5  mov     rdx, rax
0x1800029f8  lea     rcx, [rbp+130h+var_120]
0x1800029fc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180002a01  lea     rcx, [rbp+130h+var_160]
0x180002a05  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180002a0a  mov     rcx, [rdi]
0x180002a0d  add     rcx, 28h ; '('
0x180002a11  lea     rdx, [rbp+130h+var_160]
0x180002a15  call    ?cache_control@http_headers@http@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::http::http_headers::cache_control(void)
0x180002a1a  mov     rdx, rax
0x180002a1d  lea     rcx, [rbp+130h+var_E0]
0x180002a21  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180002a26  lea     rcx, [rbp+130h+var_160]
0x180002a2a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180002a2f  mov     rbx, [rdi]
0x180002a32  lea     rdx, aSetCookie; "Set-Cookie"
0x180002a39  lea     rcx, [rbp+130h+var_160]
0x180002a3d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180002a42  lea     r8, [rbp+130h+var_160]
0x180002a46  lea     rdx, [rsp+230h+var_200]
0x180002a4b  lea     rcx, [rbx+28h]
0x180002a4f  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U_case_insensitive_cmp@http_headers@http@web@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,web::http::http_headers::_case_insensitive_cmp,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180002a54  lea     rcx, [rbp+130h+var_160]
0x180002a58  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180002a5d  mov     rax, [rdi]
0x180002a60  mov     rdx, [rsp+230h+var_200]
0x180002a65  cmp     rdx, [rax+28h]
0x180002a69  jz      short loc_180002A8F
0x180002a6b  add     rdx, 40h ; '@'
0x180002a6f  lea     rcx, [rbp+130h+var_160]
0x180002a73  call    ?ExtractCookies@ServiceRequestHelper@BingOnlineServices@@SA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; BingOnlineServices::ServiceRequestHelper::ExtractCookies(std::wstring const &)
0x180002a78  nop
0x180002a79  mov     rdx, rax
0x180002a7c  lea     rcx, [rbp+130h+var_100]
0x180002a80  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180002a85  nop
0x180002a86  lea     rcx, [rbp+130h+var_160]
0x180002a8a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180002a8f  mov     rbx, [rdi]
0x180002a92  mov     rbx, [rbx+28h]
0x180002a96  mov     rdx, [rbx]
0x180002a99  mov     [rsp+230h+var_200], rdx
0x180002a9e  cmp     rdx, rbx
0x180002aa1  jz      short loc_180002B05
0x180002aa3  add     rdx, 20h ; ' '
0x180002aa7  lea     rcx, [rbp+130h+var_B0]
0x180002aae  call    ??0?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@AEBU01@@Z; std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(std::pair<std::wstring const,std::wstring> const &)
0x180002ab3  nop
0x180002ab4  lea     r8, [rbp+130h+var_B0]
0x180002abb  lea     rdx, [rbp+130h+var_160]
0x180002abf  lea     rcx, [rbp+130h+var_138]
0x180002ac3  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180002ac8  mov     rcx, [rax]
0x180002acb  add     rcx, 40h ; '@'
0x180002acf  lea     rdx, [rbp+130h+var_90]
0x180002ad6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180002adb  nop
0x180002adc  lea     rcx, [rbp+130h+var_90]
0x180002ae3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180002ae8  lea     rcx, [rbp+130h+var_B0]
0x180002aef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180002af4  lea     rcx, [rsp+230h+var_200]
0x180002af9  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x180002afe  mov     rdx, [rsp+230h+var_200]
0x180002b03  jmp     short loc_180002A9E
0x180002b05  mov     eax, [rbp+130h+var_140]
0x180002b08  lea     rdx, aBingonlineserv_3; "BingOnlineServices::ServiceRequestHelpe"...
0x180002b0f  cmp     eax, 0C8h
0x180002b14  jnz     short loc_180002B80
0x180002b16  lea     r9, aServicerequest; "[ServiceRequestHelper::ExtractJsonData]"...
0x180002b1d  mov     r8d, 0A6h
0x180002b23  mov     ecx, 5
0x180002b28  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180002b2e  lea     rdx, [rsp+230h+var_200]
0x180002b33  mov     rcx, rdi
0x180002b36  call    ?extract_json@http_response@http@web@@QEBA?AV?$task@Vvalue@json@web@@@pplx@@_N@Z; web::http::http_response::extract_json(bool)
0x180002b3b  mov     rbx, rax
0x180002b3e  lea     rdx, [rbp+130h+var_140]; struct BingOnlineServices::OnlineServiceResponse *
0x180002b42  lea     rcx, [rbp+130h+var_B0]; this
0x180002b49  call    ??0OnlineServiceResponse@BingOnlineServices@@QEAA@AEBU01@@Z; BingOnlineServices::OnlineServiceResponse::OnlineServiceResponse(BingOnlineServices::OnlineServiceResponse const &)
0x180002b4e  nop
0x180002b4f  lea     r8, [rbp+130h+var_B0]
0x180002b56  mov     rdx, rsi
0x180002b59  mov     rcx, rbx
0x180002b5c  call    pplx__task_web__json__value___then__lambda_2928cf0dfdb8953a0e15861cab0d651e___
0x180002b61  nop
0x180002b62  lea     rcx, [rbp+130h+var_B0]; this
0x180002b69  call    ??1OnlineServiceResponse@BingOnlineServices@@QEAA@XZ; BingOnlineServices::OnlineServiceResponse::~OnlineServiceResponse(void)
0x180002b6e  nop
0x180002b6f  mov     rcx, [rsp+230h+var_1F8]; this
0x180002b74  test    rcx, rcx
0x180002b77  jz      short loc_180002BF5
0x180002b79  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180002b7e  jmp     short loc_180002BF5
0x180002b80  mov     [rsp+230h+var_210], eax
0x180002b84  lea     r9, aServicerequest_1; "[ServiceRequestHelper::ExtractJsonData]"...
0x180002b8b  mov     r8d, 0B1h
0x180002b91  mov     ecx, 2
0x180002b96  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180002b9c  lea     rcx, [rsp+230h+var_200]; this
0x180002ba1  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x180002ba6  mov     rdx, rax
0x180002ba9  lea     rcx, [rbp+130h+var_C0]
0x180002bad  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180002bb2  lea     rcx, [rsp+230h+var_200]
0x180002bb7  call    ??1?$unique_ptr@V_Number@details@json@web@@U?$default_delete@V_Number@details@json@web@@@std@@@std@@QEAA@XZ; std::unique_ptr<web::json::details::_Number>::~unique_ptr<web::json::details::_Number>(void)
0x180002bbc  lea     rcx, [rbp+130h+var_B0]; this
0x180002bc3  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x180002bc8  mov     rbx, rax
0x180002bcb  lea     rdx, [rbp+130h+var_140]; struct BingOnlineServices::OnlineServiceResponse *
0x180002bcf  lea     rcx, [rsp+230h+var_1E8]; this
0x180002bd4  call    ??0OnlineServiceResponse@BingOnlineServices@@QEAA@AEBU01@@Z; BingOnlineServices::OnlineServiceResponse::OnlineServiceResponse(BingOnlineServices::OnlineServiceResponse const &)
0x180002bd9  mov     r8, rbx
0x180002bdc  mov     rdx, rax
0x180002bdf  mov     rcx, rsi
0x180002be2  call    ??$task_from_result@UOnlineServiceResponse@BingOnlineServices@@@pplx@@YA?AV?$task@UOnlineServiceResponse@BingOnlineServices@@@0@UOnlineServiceResponse@BingOnlineServices@@AEBVtask_options@0@@Z; pplx::task_from_result<BingOnlineServices::OnlineServiceResponse>(BingOnlineServices::OnlineServiceResponse,pplx::task_options const &)
0x180002be7  nop
0x180002be8  lea     rcx, [rbp+130h+var_B0]; this
0x180002bef  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x180002bf4  nop
0x180002bf5  lea     rcx, [rbp+130h+var_140]; this
0x180002bf9  call    ??1OnlineServiceResponse@BingOnlineServices@@QEAA@XZ; BingOnlineServices::OnlineServiceResponse::~OnlineServiceResponse(void)
0x180002bfe  mov     rax, rsi
0x180002c01  mov     rcx, [rbp+130h+var_20]
0x180002c08  xor     rcx, rsp; StackCookie
0x180002c0b  call    __security_check_cookie
0x180002c10  mov     rbx, [rsp+230h+arg_10]
0x180002c18  add     rsp, 220h
0x180002c1f  pop     rdi
0x180002c20  pop     rsi
0x180002c21  pop     rbp
0x180002c22  retn
```
