# web::http::oauth1::experimental::oauth1_config::token_from_redirected_uri(web::uri const &)

- ea: `0x18004e600`
- end: `0x18004e867`
- name: `?token_from_redirected_uri@oauth1_config@experimental@oauth1@http@web@@QEAA?AV?$task@X@pplx@@AEBVuri@5@@Z`
- size: `615`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002c2c`
- `0x180002ca8`
- `0x180004fa0`
- `0x180009730`
- `0x18000a228`
- `0x18000e5a8`
- `0x180010838`
- `0x18001235c`
- `0x180012cc0`
- `0x1800167f8`
- `0x1800177f8`
- `0x18001a384`
- `0x18001b200`
- `0x18001e604`
- `0x18003c61c`
- `0x18003e270`
- `0x1800472f4`
- `0x1800481d0`
- `0x18004d4a4`
- `0x18004e600`
- `0x18004e870`

## import_xrefs

- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18004e69e`
- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18004e69e`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18004e6af`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18004e6af`

## string_xrefs

- `0x18004e801`: `parameter 'oauth_token' missing from redirected URI.`
- `0x18004e6dd`: `' does not match temporary token='`
- `0x18004e7c6`: `parameter 'oauth_verifier' missing from redirected URI.`
- `0x18004e6bf`: `redirected URI parameter 'oauth_token'='`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall web::http::oauth1::experimental::oauth1_config::token_from_redirected_uri(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v5; // rsi
  __int64 v6; // r14
  char *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  const struct pplx::task_options *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  const struct web::http::oauth1::experimental::oauth1_exception *v16; // rax
  __int64 v17; // rax
  const struct pplx::task_options *v18; // rbx
  __int64 v19; // rax
  const struct web::http::oauth1::experimental::oauth1_exception *v20; // rax
  const struct pplx::task_options *v21; // rbx
  __int64 v22; // rax
  const struct web::http::oauth1::experimental::oauth1_exception *v23; // rax
  _QWORD v25[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v26[3]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v27[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v28[56]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v29[96]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v30; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v31[232]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v32[32]; // [rsp+1F0h] [rbp+F0h] BYREF

  v25[0] = a2;
  web::uri::split_query(v26, a3 + 160);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
    v26,
    v25,
    web::http::oauth1::details::oauth1_strings::token);
  if ( v25[0] == v26[0] )
  {
    v21 = (const struct pplx::task_options *)pplx::task_options::task_options((pplx::task_options *)v29);
    v22 = std::wstring::wstring(v27, L"parameter 'oauth_token' missing from redirected URI.");
    v23 = (const struct web::http::oauth1::experimental::oauth1_exception *)web::http::oauth1::experimental::oauth1_exception::oauth1_exception(
                                                                              v28,
                                                                              v22);
    pplx::task_from_exception<void,web::http::oauth1::experimental::oauth1_exception>(a2, v23, v21);
    goto LABEL_8;
  }
  v5 = v25[0] + 64LL;
  v6 = a1 + 64;
  if ( !(unsigned __int8)std::operator!=<unsigned short>(a1 + 64, v25[0] + 64LL) )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
      v26,
      v25,
      web::http::oauth1::details::oauth1_strings::verifier);
    if ( v25[0] != v26[0] )
    {
      v17 = std::wstring::wstring(v27);
      web::http::oauth1::experimental::oauth1_config::token_from_verifier(a1, a2, v17);
      goto LABEL_9;
    }
    v18 = (const struct pplx::task_options *)pplx::task_options::task_options((pplx::task_options *)v29);
    v19 = std::wstring::wstring(v27, L"parameter 'oauth_verifier' missing from redirected URI.");
    v20 = (const struct web::http::oauth1::experimental::oauth1_exception *)web::http::oauth1::experimental::oauth1_exception::oauth1_exception(
                                                                              v28,
                                                                              v19);
    pplx::task_from_exception<void,web::http::oauth1::experimental::oauth1_exception>(a2, v20, v18);
LABEL_8:
    pplx::task_options::~task_options((pplx::task_options *)v29);
    goto LABEL_9;
  }
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v30);
  v7 = &v31[*(int *)(v30 + 4) - 8];
  v8 = std::locale::classic();
  std::basic_ios<unsigned short>::imbue(v7, v25, v8);
  std::locale::~locale((std::locale *)v25);
  v9 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
         &v30,
         L"redirected URI parameter 'oauth_token'='");
  v10 = std::operator<<<unsigned short>(v9, v5);
  v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v10, L"' does not match temporary token='");
  v12 = std::operator<<<unsigned short>(v11, v6);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, L"'.");
  v13 = (const struct pplx::task_options *)pplx::task_options::task_options((pplx::task_options *)v29);
  std::basic_stringbuf<unsigned short>::str(v31, v32);
  v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
  v15 = std::wstring::wstring(v27, v14);
  v16 = (const struct web::http::oauth1::experimental::oauth1_exception *)web::http::oauth1::experimental::oauth1_exception::oauth1_exception(
                                                                            v28,
                                                                            v15);
  pplx::task_from_exception<void,web::http::oauth1::experimental::oauth1_exception>(a2, v16, v13);
  std::wstring::_Tidy_deallocate(v32);
  pplx::task_options::~task_options((pplx::task_options *)v29);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(&v30);
LABEL_9:
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
    v26,
    v26);
  return a2;
}

```

## disassembly

```asm
0x18004e600  push    rbp
0x18004e602  push    rbx
0x18004e603  push    rsi
0x18004e604  push    rdi
0x18004e605  push    r14
0x18004e607  lea     rbp, [rsp-120h]
0x18004e60f  sub     rsp, 220h
0x18004e616  mov     rax, cs:__security_cookie
0x18004e61d  xor     rax, rsp
0x18004e620  mov     [rbp+140h+var_30], rax
0x18004e627  mov     rdi, rdx
0x18004e62a  mov     rbx, rcx
0x18004e62d  mov     [rsp+240h+var_220], rdx
0x18004e632  lea     rdx, [r8+0A0h]
0x18004e639  lea     rcx, [rsp+240h+var_210]
0x18004e63e  call    ?split_query@uri@web@@SA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; web::uri::split_query(std::wstring const &)
0x18004e643  nop
0x18004e644  lea     r8, ?token@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::oauth1::details::oauth1_strings::token
0x18004e64b  lea     rdx, [rsp+240h+var_220]
0x18004e650  lea     rcx, [rsp+240h+var_210]
0x18004e655  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x18004e65a  mov     rax, [rsp+240h+var_220]
0x18004e65f  cmp     rax, [rsp+240h+var_210]
0x18004e664  jz      loc_18004E7F5
0x18004e66a  lea     rsi, [rax+40h]
0x18004e66e  lea     r14, [rbx+40h]
0x18004e672  mov     rdx, rsi
0x18004e675  mov     rcx, r14
0x18004e678  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator!=<ushort>(std::wstring const &,std::wstring const &)
0x18004e67d  test    al, al
0x18004e67f  jz      loc_18004E77A
0x18004e685  lea     rcx, [rbp+140h+var_140]
0x18004e689  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18004e68e  nop
0x18004e68f  mov     rax, [rbp+140h+var_140]
0x18004e693  movsxd  rcx, dword ptr [rax+4]
0x18004e697  lea     rbx, [rbp+140h+var_140]
0x18004e69b  add     rbx, rcx
0x18004e69e  call    cs:__imp_?classic@locale@std@@SAAEBV12@XZ; std::locale::classic(void)
0x18004e6a4  mov     r8, rax
0x18004e6a7  lea     rdx, [rsp+240h+var_220]
0x18004e6ac  mov     rcx, rbx
0x18004e6af  call    cs:__imp_?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z; std::basic_ios<ushort>::imbue(std::locale const &)
0x18004e6b5  lea     rcx, [rsp+240h+var_220]; this
0x18004e6ba  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18004e6bf  lea     rdx, aRedirectedUriP; "redirected URI parameter 'oauth_token'="...
0x18004e6c6  lea     rcx, [rbp+140h+var_140]
0x18004e6ca  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18004e6cf  mov     rdx, rsi
0x18004e6d2  mov     rcx, rax
0x18004e6d5  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18004e6da  mov     rcx, rax
0x18004e6dd  lea     rdx, aDoesNotMatchTe; "' does not match temporary token='"
0x18004e6e4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18004e6e9  mov     rdx, r14
0x18004e6ec  mov     rcx, rax
0x18004e6ef  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18004e6f4  mov     rcx, rax
0x18004e6f7  lea     rdx, asc_180069DC8; "'."
0x18004e6fe  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18004e703  lea     rcx, [rbp+140h+var_1A0]; this
0x18004e707  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18004e70c  mov     rbx, rax
0x18004e70f  lea     rdx, [rbp+140h+var_50]
0x18004e716  lea     rcx, [rbp+140h+var_138]
0x18004e71a  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18004e71f  nop
0x18004e720  lea     rcx, [rbp+140h+var_50]
0x18004e727  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004e72c  mov     rdx, rax
0x18004e72f  lea     rcx, [rsp+240h+var_1F8]
0x18004e734  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004e739  mov     rdx, rax
0x18004e73c  lea     rcx, [rsp+240h+var_1D8]
0x18004e741  call    ??0oauth1_exception@experimental@oauth1@http@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::oauth1::experimental::oauth1_exception::oauth1_exception(std::wstring)
0x18004e746  mov     r8, rbx
0x18004e749  mov     rdx, rax
0x18004e74c  mov     rcx, rdi
0x18004e74f  call    ??$task_from_exception@XVoauth1_exception@experimental@oauth1@http@web@@@pplx@@YA?AV?$task@X@0@Voauth1_exception@experimental@oauth1@http@web@@AEBVtask_options@0@@Z; pplx::task_from_exception<void,web::http::oauth1::experimental::oauth1_exception>(web::http::oauth1::experimental::oauth1_exception,pplx::task_options const &)
0x18004e754  nop
0x18004e755  lea     rcx, [rbp+140h+var_50]
0x18004e75c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e761  nop
0x18004e762  lea     rcx, [rbp+140h+var_1A0]; this
0x18004e766  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x18004e76b  nop
0x18004e76c  lea     rcx, [rbp+140h+var_140]
0x18004e770  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18004e775  jmp     loc_18004E838
0x18004e77a  lea     r8, ?verifier@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::oauth1::details::oauth1_strings::verifier
0x18004e781  lea     rdx, [rsp+240h+var_220]
0x18004e786  lea     rcx, [rsp+240h+var_210]
0x18004e78b  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x18004e790  mov     rdx, [rsp+240h+var_220]
0x18004e795  cmp     rdx, [rsp+240h+var_210]
0x18004e79a  jz      short loc_18004E7BA
0x18004e79c  add     rdx, 40h ; '@'
0x18004e7a0  lea     rcx, [rsp+240h+var_1F8]
0x18004e7a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e7aa  mov     r8, rax
0x18004e7ad  mov     rdx, rdi
0x18004e7b0  mov     rcx, rbx
0x18004e7b3  call    ?token_from_verifier@oauth1_config@experimental@oauth1@http@web@@QEAA?AV?$task@X@pplx@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::oauth1::experimental::oauth1_config::token_from_verifier(std::wstring)
0x18004e7b8  jmp     short loc_18004E838
0x18004e7ba  lea     rcx, [rbp+140h+var_1A0]; this
0x18004e7be  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18004e7c3  mov     rbx, rax
0x18004e7c6  lea     rdx, aParameterOauth_0; "parameter 'oauth_verifier' missing from"...
0x18004e7cd  lea     rcx, [rsp+240h+var_1F8]
0x18004e7d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004e7d7  mov     rdx, rax
0x18004e7da  lea     rcx, [rsp+240h+var_1D8]
0x18004e7df  call    ??0oauth1_exception@experimental@oauth1@http@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::oauth1::experimental::oauth1_exception::oauth1_exception(std::wstring)
0x18004e7e4  mov     r8, rbx
0x18004e7e7  mov     rdx, rax
0x18004e7ea  mov     rcx, rdi
0x18004e7ed  call    ??$task_from_exception@XVoauth1_exception@experimental@oauth1@http@web@@@pplx@@YA?AV?$task@X@0@Voauth1_exception@experimental@oauth1@http@web@@AEBVtask_options@0@@Z; pplx::task_from_exception<void,web::http::oauth1::experimental::oauth1_exception>(web::http::oauth1::experimental::oauth1_exception,pplx::task_options const &)
0x18004e7f2  nop
0x18004e7f3  jmp     short loc_18004E82E
0x18004e7f5  lea     rcx, [rbp+140h+var_1A0]; this
0x18004e7f9  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18004e7fe  mov     rbx, rax
0x18004e801  lea     rdx, aParameterOauth_3; "parameter 'oauth_token' missing from re"...
0x18004e808  lea     rcx, [rsp+240h+var_1F8]
0x18004e80d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004e812  mov     rdx, rax
0x18004e815  lea     rcx, [rsp+240h+var_1D8]
0x18004e81a  call    ??0oauth1_exception@experimental@oauth1@http@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::oauth1::experimental::oauth1_exception::oauth1_exception(std::wstring)
0x18004e81f  mov     r8, rbx
0x18004e822  mov     rdx, rax
0x18004e825  mov     rcx, rdi
0x18004e828  call    ??$task_from_exception@XVoauth1_exception@experimental@oauth1@http@web@@@pplx@@YA?AV?$task@X@0@Voauth1_exception@experimental@oauth1@http@web@@AEBVtask_options@0@@Z; pplx::task_from_exception<void,web::http::oauth1::experimental::oauth1_exception>(web::http::oauth1::experimental::oauth1_exception,pplx::task_options const &)
0x18004e82d  nop
0x18004e82e  lea     rcx, [rbp+140h+var_1A0]; this
0x18004e832  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x18004e837  nop
0x18004e838  lea     rdx, [rsp+240h+var_210]
0x18004e83d  lea     rcx, [rsp+240h+var_210]
0x18004e842  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x18004e847  mov     rax, rdi
0x18004e84a  mov     rcx, [rbp+140h+var_30]
0x18004e851  xor     rcx, rsp; StackCookie
0x18004e854  call    __security_check_cookie
0x18004e859  add     rsp, 220h
0x18004e860  pop     r14
0x18004e862  pop     rdi
0x18004e863  pop     rsi
0x18004e864  pop     rbx
0x18004e865  pop     rbp
0x18004e866  retn
```
