# web::http::oauth1::experimental::oauth1_config::_authenticate_request(web::http::http_request &,web::http::oauth1::details::oauth1_state)

- ea: `0x18004b430`
- end: `0x18004b858`
- name: `?_authenticate_request@oauth1_config@experimental@oauth1@http@web@@AEAAXAEAVhttp_request@45@Voauth1_state@details@345@@Z`
- size: `1064`
- prototype: `void __high(struct web::http::http_request *, struct web::http::oauth1::details::oauth1_state)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180035e1c`
- `0x18004cb10`

## callees

- `0x180002c2c`
- `0x180004fa0`
- `0x180009730`
- `0x18000a228`
- `0x18000fa74`
- `0x18000fc54`
- `0x1800167f8`
- `0x1800177f8`
- `0x180019920`
- `0x18001a384`
- `0x18001b200`
- `0x18003416c`
- `0x18003d840`
- `0x18004b430`
- `0x18004c130`

## import_xrefs

- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18004b48c`
- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18004b48c`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18004b49f`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18004b49f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall web::http::oauth1::experimental::oauth1_config::_authenticate_request(
        __int64 a1,
        __int64 *a2,
        web::http::oauth1::details::oauth1_state *a3)
{
  char *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rbx
  __int64 v41; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v42[232]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v43[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v44[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v45[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v46[32]; // [rsp+180h] [rbp+80h] BYREF
  web::http::oauth1::details::oauth1_state *v47; // [rsp+1A0h] [rbp+A0h]
  _QWORD v48[4]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v49[32]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v50[32]; // [rsp+1E8h] [rbp+E8h] BYREF

  v47 = a3;
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v41);
  v6 = &v42[*(int *)(v41 + 4) - 8];
  v7 = std::locale::classic();
  std::basic_ios<unsigned short>::imbue(v6, v48, v7);
  std::locale::~locale((std::locale *)v48);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v41, "OAuth ");
  if ( *(_QWORD *)(a1 + 288) )
  {
    v8 = std::operator<<<unsigned short>(&v41, web::http::oauth1::details::oauth1_strings::realm);
    v9 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, "=\"");
    v10 = web::uri::encode_data_string(v48, a1 + 272);
    v11 = std::operator<<<unsigned short>(v9, v10);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, "\", ");
    std::wstring::_Tidy_deallocate(v48);
  }
  v12 = std::operator<<<unsigned short>(&v41, web::http::oauth1::details::oauth1_strings::version);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, "=\"1.0");
  v13 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v41, "\", ");
  v14 = std::operator<<<unsigned short>(v13, web::http::oauth1::details::oauth1_strings::consumer_key);
  v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v14, "=\"");
  v16 = web::uri::encode_data_string(v48, a1);
  std::operator<<<unsigned short>(v15, v16);
  std::wstring::_Tidy_deallocate(v48);
  if ( *(_QWORD *)(a1 + 80) )
  {
    v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v41, "\", ");
    v18 = std::operator<<<unsigned short>(v17, web::http::oauth1::details::oauth1_strings::token);
    v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, "=\"");
    v20 = web::uri::encode_data_string(v48, a1 + 64);
    std::operator<<<unsigned short>(v19, v20);
    std::wstring::_Tidy_deallocate(v48);
  }
  v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v41, "\", ");
  v22 = std::operator<<<unsigned short>(v21, web::http::oauth1::details::oauth1_strings::signature_method);
  v23 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v22, "=\"");
  std::operator<<<unsigned short>(v23, a1 + 304);
  v24 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v41, "\", ");
  v25 = std::operator<<<unsigned short>(v24, web::http::oauth1::details::oauth1_strings::timestamp);
  v26 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v25, "=\"");
  std::operator<<<unsigned short>(v26, a3);
  v27 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v41, "\", ");
  v28 = std::operator<<<unsigned short>(v27, web::http::oauth1::details::oauth1_strings::nonce);
  v29 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v28, "=\"");
  std::operator<<<unsigned short>(v29, (char *)a3 + 32);
  std::wstring::wstring(v43);
  std::wstring::wstring(v44);
  std::wstring::wstring(v45);
  std::wstring::wstring(v46);
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(v48, a2);
  v30 = web::http::oauth1::experimental::oauth1_config::_build_signature(a1, v49, v48, v43, v43);
  v31 = web::uri::encode_data_string(v50, v30);
  v32 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v41, "\", ");
  v33 = std::operator<<<unsigned short>(v32, web::http::oauth1::details::oauth1_strings::signature);
  v34 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v33, "=\"");
  std::operator<<<unsigned short>(v34, v31);
  std::wstring::_Tidy_deallocate(v50);
  std::wstring::_Tidy_deallocate(v49);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v41, "\"");
  if ( *((_QWORD *)a3 + 10) )
  {
    v35 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v41, ", ");
    v36 = std::operator<<<unsigned short>(v35, (char *)a3 + 64);
    v37 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v36, "=\"");
    v38 = web::uri::encode_data_string(v49, (char *)a3 + 96);
    v39 = std::operator<<<unsigned short>(v37, v38);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v39, "\"");
    std::wstring::_Tidy_deallocate(v49);
  }
  v40 = *a2;
  std::basic_stringbuf<unsigned short>::str(v42, v48);
  web::http::http_headers::add<std::wstring>(v40 + 40, web::http::header_names::authorization, v48);
  std::wstring::_Tidy_deallocate(v48);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(&v41);
  web::http::oauth1::details::oauth1_state::~oauth1_state(a3);
}

```

## disassembly

```asm
0x18004b430  mov     [rsp-8+arg_18], rbx
0x18004b435  push    rbp
0x18004b436  push    rsi
0x18004b437  push    rdi
0x18004b438  push    r12
0x18004b43a  push    r13
0x18004b43c  push    r14
0x18004b43e  push    r15
0x18004b440  lea     rbp, [rsp-110h]
0x18004b448  sub     rsp, 210h
0x18004b44f  mov     rax, cs:__security_cookie
0x18004b456  xor     rax, rsp
0x18004b459  mov     [rbp+140h+var_38], rax
0x18004b460  mov     rdi, r8
0x18004b463  mov     r15, rdx
0x18004b466  mov     rsi, rcx
0x18004b469  mov     [rbp+140h+var_A0], r8
0x18004b470  lea     rcx, [rsp+240h+var_210]
0x18004b475  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x18004b47a  nop
0x18004b47b  mov     rax, [rsp+240h+var_210]
0x18004b480  movsxd  rcx, dword ptr [rax+4]
0x18004b484  lea     rbx, [rsp+240h+var_210]
0x18004b489  add     rbx, rcx
0x18004b48c  call    cs:__imp_?classic@locale@std@@SAAEBV12@XZ
0x18004b492  mov     r8, rax
0x18004b495  lea     rdx, [rbp+140h+var_98]
0x18004b49c  mov     rcx, rbx
0x18004b49f  call    cs:__imp_?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z
0x18004b4a5  lea     rcx, [rbp+140h+var_98]; this
0x18004b4ac  call    ??1locale@std@@QEAA@XZ
0x18004b4b1  lea     rdx, aOauth
0x18004b4b8  lea     rcx, [rsp+240h+var_210]
0x18004b4bd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b4c2  lea     r14, [rsi+110h]
0x18004b4c9  lea     r13, asc_180069CF0
0x18004b4d0  lea     r12, asc_180069CF4
0x18004b4d7  cmp     qword ptr [r14+10h], 0
0x18004b4dc  jz      short loc_18004B530
0x18004b4de  lea     rdx, ?realm@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B
0x18004b4e5  lea     rcx, [rsp+240h+var_210]
0x18004b4ea  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b4ef  mov     rcx, rax
0x18004b4f2  mov     rdx, r13
0x18004b4f5  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b4fa  mov     rbx, rax
0x18004b4fd  mov     rdx, r14
0x18004b500  lea     rcx, [rbp+140h+var_98]
0x18004b507  call    ?encode_data_string@uri@web@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z
0x18004b50c  nop
0x18004b50d  mov     rdx, rax
0x18004b510  mov     rcx, rbx
0x18004b513  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b518  mov     rcx, rax
0x18004b51b  mov     rdx, r12
0x18004b51e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b523  nop
0x18004b524  lea     rcx, [rbp+140h+var_98]
0x18004b52b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ
0x18004b530  lea     rdx, ?version@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B
0x18004b537  lea     rcx, [rsp+240h+var_210]
0x18004b53c  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b541  mov     rcx, rax
0x18004b544  lea     rdx, a10
0x18004b54b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b550  mov     rdx, r12
0x18004b553  lea     rcx, [rsp+240h+var_210]
0x18004b558  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b55d  mov     rcx, rax
0x18004b560  lea     rdx, ?consumer_key@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B
0x18004b567  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b56c  mov     rcx, rax
0x18004b56f  mov     rdx, r13
0x18004b572  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b577  mov     rbx, rax
0x18004b57a  mov     rdx, rsi
0x18004b57d  lea     rcx, [rbp+140h+var_98]
0x18004b584  call    ?encode_data_string@uri@web@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z
0x18004b589  nop
0x18004b58a  mov     rdx, rax
0x18004b58d  mov     rcx, rbx
0x18004b590  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b595  nop
0x18004b596  lea     rcx, [rbp+140h+var_98]
0x18004b59d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ
0x18004b5a2  cmp     qword ptr [rsi+50h], 0
0x18004b5a7  jz      short loc_18004B5FC
0x18004b5a9  mov     rdx, r12
0x18004b5ac  lea     rcx, [rsp+240h+var_210]
0x18004b5b1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b5b6  mov     rcx, rax
0x18004b5b9  lea     rdx, ?token@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B
0x18004b5c0  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b5c5  mov     rcx, rax
0x18004b5c8  mov     rdx, r13
0x18004b5cb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b5d0  mov     rbx, rax
0x18004b5d3  lea     rdx, [rsi+40h]
0x18004b5d7  lea     rcx, [rbp+140h+var_98]
0x18004b5de  call    ?encode_data_string@uri@web@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z
0x18004b5e3  nop
0x18004b5e4  mov     rdx, rax
0x18004b5e7  mov     rcx, rbx
0x18004b5ea  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b5ef  nop
0x18004b5f0  lea     rcx, [rbp+140h+var_98]
0x18004b5f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ
0x18004b5fc  mov     rdx, r12
0x18004b5ff  lea     rcx, [rsp+240h+var_210]
0x18004b604  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b609  mov     rcx, rax
0x18004b60c  lea     rdx, ?signature_method@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B
0x18004b613  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b618  mov     rcx, rax
0x18004b61b  mov     rdx, r13
0x18004b61e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b623  lea     rdx, [rsi+130h]
0x18004b62a  mov     rcx, rax
0x18004b62d  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b632  mov     rdx, r12
0x18004b635  lea     rcx, [rsp+240h+var_210]
0x18004b63a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b63f  mov     rcx, rax
0x18004b642  lea     rdx, ?timestamp@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B
0x18004b649  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b64e  mov     rcx, rax
0x18004b651  mov     rdx, r13
0x18004b654  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b659  mov     rdx, rdi
0x18004b65c  mov     rcx, rax
0x18004b65f  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b664  mov     rdx, r12
0x18004b667  lea     rcx, [rsp+240h+var_210]
0x18004b66c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b671  mov     rcx, rax
0x18004b674  lea     rdx, ?nonce@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B
0x18004b67b  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b680  mov     rcx, rax
0x18004b683  mov     rdx, r13
0x18004b686  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b68b  lea     rdx, [rdi+20h]
0x18004b68f  mov     rcx, rax
0x18004b692  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b697  lea     rax, [rbp+140h+var_120]
0x18004b69b  mov     [rsp+240h+var_220], rax
0x18004b6a0  mov     rdx, rdi
0x18004b6a3  lea     rcx, [rbp+140h+var_120]
0x18004b6a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z
0x18004b6ac  nop
0x18004b6ad  lea     rdx, [rdi+20h]
0x18004b6b1  lea     rcx, [rbp+140h+var_100]
0x18004b6b5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z
0x18004b6ba  nop
0x18004b6bb  lea     rdx, [rdi+40h]
0x18004b6bf  lea     rcx, [rbp+140h+var_E0]
0x18004b6c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z
0x18004b6c8  nop
0x18004b6c9  lea     rdx, [rdi+60h]
0x18004b6cd  lea     rcx, [rbp+140h+var_C0]
0x18004b6d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z
0x18004b6d9  nop
0x18004b6da  mov     rdx, r15
0x18004b6dd  lea     rcx, [rbp+140h+var_98]
0x18004b6e4  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z
0x18004b6e9  lea     r9, [rbp+140h+var_120]
0x18004b6ed  lea     r8, [rbp+140h+var_98]
0x18004b6f4  lea     rdx, [rbp+140h+var_78]
0x18004b6fb  mov     rcx, rsi
0x18004b6fe  call    ?_build_signature@oauth1_config@experimental@oauth1@http@web@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vhttp_request@45@Voauth1_state@details@345@@Z
0x18004b703  nop
0x18004b704  mov     rdx, rax
0x18004b707  lea     rcx, [rbp+140h+var_58]
0x18004b70e  call    ?encode_data_string@uri@web@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z
0x18004b713  mov     rbx, rax
0x18004b716  lea     rdx, asc_180069CF4
0x18004b71d  lea     rcx, [rsp+240h+var_210]
0x18004b722  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b727  mov     rcx, rax
0x18004b72a  lea     rdx, ?signature@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B
0x18004b731  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b736  mov     rcx, rax
0x18004b739  mov     rdx, r13
0x18004b73c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b741  mov     rdx, rbx
0x18004b744  mov     rcx, rax
0x18004b747  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b74c  nop
0x18004b74d  lea     rcx, [rbp+140h+var_58]
0x18004b754  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ
0x18004b759  nop
0x18004b75a  lea     rcx, [rbp+140h+var_78]
0x18004b761  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ
0x18004b766  lea     rdx, asc_180069CF8
0x18004b76d  lea     rcx, [rsp+240h+var_210]
0x18004b772  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b777  cmp     qword ptr [rdi+50h], 0
0x18004b77c  jz      short loc_18004B7E1
0x18004b77e  lea     rdx, asc_180069D7C
0x18004b785  lea     rcx, [rsp+240h+var_210]
0x18004b78a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b78f  lea     rdx, [rdi+40h]
0x18004b793  mov     rcx, rax
0x18004b796  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b79b  mov     rcx, rax
0x18004b79e  mov     rdx, r13
0x18004b7a1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b7a6  mov     rbx, rax
0x18004b7a9  lea     rdx, [rdi+60h]
0x18004b7ad  lea     rcx, [rbp+140h+var_78]
0x18004b7b4  call    ?encode_data_string@uri@web@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z
0x18004b7b9  nop
0x18004b7ba  mov     rdx, rax
0x18004b7bd  mov     rcx, rbx
0x18004b7c0  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z
0x18004b7c5  mov     rcx, rax
0x18004b7c8  lea     rdx, asc_180069CF8
0x18004b7cf  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z
0x18004b7d4  nop
0x18004b7d5  lea     rcx, [rbp+140h+var_78]
0x18004b7dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ
0x18004b7e1  mov     rbx, [r15]
0x18004b7e4  lea     rdx, [rbp+140h+var_98]
0x18004b7eb  lea     rcx, [rsp+240h+var_208]
0x18004b7f0  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ
0x18004b7f5  nop
0x18004b7f6  lea     r8, [rbp+140h+var_98]
0x18004b7fd  lea     rdx, ?authorization@header_names@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B
0x18004b804  lea     rcx, [rbx+28h]
0x18004b808  call    ??$add@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@http_headers@http@web@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z
0x18004b80d  nop
0x18004b80e  lea     rcx, [rbp+140h+var_98]
0x18004b815  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ
0x18004b81a  nop
0x18004b81b  lea     rcx, [rsp+240h+var_210]
0x18004b820  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ
0x18004b825  nop
0x18004b826  mov     rcx, rdi; this
0x18004b829  call    ??1oauth1_state@details@oauth1@http@web@@QEAA@XZ
0x18004b82e  mov     rcx, [rbp+140h+var_38]
0x18004b835  xor     rcx, rsp; StackCookie
0x18004b838  call    __security_check_cookie
0x18004b83d  mov     rbx, [rsp+240h+arg_18]
0x18004b845  add     rsp, 210h
0x18004b84c  pop     r15
0x18004b84e  pop     r14
0x18004b850  pop     r13
0x18004b852  pop     r12
0x18004b854  pop     rdi
0x18004b855  pop     rsi
0x18004b856  pop     rbp
0x18004b857  retn
```
