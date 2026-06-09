# web::http::oauth1::experimental::oauth1_config::_build_normalized_parameters(web::uri,web::http::oauth1::details::oauth1_state const &)

- ea: `0x18004bb6c`
- end: `0x18004c127`
- name: `?_build_normalized_parameters@oauth1_config@experimental@oauth1@http@web@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vuri@5@AEBVoauth1_state@details@345@@Z`
- size: `1467`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18004c280`

## callees

- `0x180002c2c`
- `0x180004fa0`
- `0x18000979c`
- `0x18000a228`
- `0x18000ec54`
- `0x18000fc54`
- `0x180010838`
- `0x1800167f8`
- `0x1800177f8`
- `0x18001a384`
- `0x18001adbc`
- `0x18001af14`
- `0x18001b200`
- `0x18001e604`
- `0x18003d840`
- `0x18003e270`
- `0x180042e70`
- `0x180042ed8`
- `0x180043c74`
- `0x180047e2c`
- `0x18004bb6c`
- `0x18004dde0`

## import_xrefs

- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18004bc03`
- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18004bcd8`
- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18004c04a`
- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18004bc03`
- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18004bcd8`
- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18004c04a`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18004bc16`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18004bceb`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18004c05d`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18004bc16`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18004bceb`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18004c05d`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall web::http::oauth1::experimental::oauth1_config::_build_normalized_parameters(
        __int64 a1,
        __int64 a2,
        web::uri *a3,
        __int64 a4)
{
  __int64 v8; // rax
  __int64 v9; // rdi
  _BYTE *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdi
  _BYTE *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // r9
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v36; // rdx
  char *v37; // rbx
  __int64 v38; // rax
  __int64 i; // rbx
  __int64 v40; // rax
  __int64 v42; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v43; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v44; // [rsp+30h] [rbp-D0h]
  _QWORD v45[3]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v47[232]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v49[232]; // [rsp+158h] [rbp+58h] BYREF
  web::uri *v50; // [rsp+240h] [rbp+140h]
  _BYTE v51[32]; // [rsp+248h] [rbp+148h] BYREF
  _BYTE v52[32]; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v53[32]; // [rsp+288h] [rbp+188h] BYREF

  v42 = a2;
  v50 = a3;
  web::uri::split_query(v45, (char *)a3 + 160);
  std::vector<std::shared_ptr<pplx::details::_Task_impl<unsigned char>>>::vector<std::shared_ptr<pplx::details::_Task_impl<unsigned char>>>(&v43);
  v8 = *(_QWORD *)v45[0];
  v42 = *(_QWORD *)v45[0];
  while ( !*(_BYTE *)(v8 + 25) )
  {
    v9 = v8 + 32;
    std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v46);
    v10 = &v47[*(int *)(v46 + 4) - 8];
    v11 = std::locale::classic();
    std::basic_ios<unsigned short>::imbue(v10, v52, v11);
    std::locale::~locale((std::locale *)v52);
    v12 = std::operator<<<unsigned short>(&v46, v9);
    v13 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, "=");
    std::operator<<<unsigned short>(v13, v9 + 32);
    std::basic_stringbuf<unsigned short>::str(v47, v51);
    std::vector<std::wstring>::push_back(&v43, v51);
    std::wstring::_Tidy_deallocate(v51);
    std::basic_ostringstream<unsigned short>::`vbase destructor'(&v46);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(&v42);
    v8 = v42;
  }
  v14 = **(_QWORD **)(a1 + 336);
  v42 = v14;
  while ( !*(_BYTE *)(v14 + 25) )
  {
    v15 = v14 + 32;
    std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v46);
    v16 = &v47[*(int *)(v46 + 4) - 8];
    v17 = std::locale::classic();
    std::basic_ios<unsigned short>::imbue(v16, v52, v17);
    std::locale::~locale((std::locale *)v52);
    v18 = std::operator<<<unsigned short>(&v46, v15);
    v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, "=");
    std::operator<<<unsigned short>(v19, v15 + 32);
    std::basic_stringbuf<unsigned short>::str(v47, v51);
    std::vector<std::wstring>::push_back(&v43, v51);
    std::wstring::_Tidy_deallocate(v51);
    std::basic_ostringstream<unsigned short>::`vbase destructor'(&v46);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(&v42);
    v14 = v42;
  }
  v20 = std::operator+<unsigned short>(v51, web::http::oauth1::details::oauth1_strings::version, L"=1.0");
  std::vector<std::wstring>::push_back(&v43, v20);
  std::wstring::_Tidy_deallocate(v51);
  v21 = web::uri::encode_data_string(v53, a1);
  v22 = std::operator+<unsigned short>(v52, web::http::oauth1::details::oauth1_strings::consumer_key, L"=");
  std::wstring::wstring(v51, v23, v22, v21);
  std::vector<std::wstring>::push_back(&v43, v51);
  std::wstring::_Tidy_deallocate(v51);
  std::wstring::_Tidy_deallocate(v52);
  std::wstring::_Tidy_deallocate(v53);
  if ( *(_QWORD *)(a1 + 80) )
  {
    v24 = web::uri::encode_data_string(v52, a1 + 64);
    v25 = std::operator+<unsigned short>(v53, web::http::oauth1::details::oauth1_strings::token, L"=");
    std::wstring::wstring(v51, v26, v25, v24);
    std::vector<std::wstring>::push_back(&v43, v51);
    std::wstring::_Tidy_deallocate(v51);
    std::wstring::_Tidy_deallocate(v53);
    std::wstring::_Tidy_deallocate(v52);
  }
  v27 = std::operator+<unsigned short>(v51, web::http::oauth1::details::oauth1_strings::signature_method, L"=");
  v28 = std::operator+<unsigned short>(v53, v27, a1 + 304);
  std::vector<std::wstring>::push_back(&v43, v28);
  std::wstring::_Tidy_deallocate(v53);
  std::wstring::_Tidy_deallocate(v51);
  v29 = std::operator+<unsigned short>(v51, web::http::oauth1::details::oauth1_strings::timestamp, L"=");
  v30 = std::operator+<unsigned short>(v53, v29, a4);
  std::vector<std::wstring>::push_back(&v43, v30);
  std::wstring::_Tidy_deallocate(v53);
  std::wstring::_Tidy_deallocate(v51);
  v31 = std::operator+<unsigned short>(v51, web::http::oauth1::details::oauth1_strings::nonce, L"=");
  v32 = std::operator+<unsigned short>(v53, v31, a4 + 32);
  std::vector<std::wstring>::push_back(&v43, v32);
  std::wstring::_Tidy_deallocate(v53);
  std::wstring::_Tidy_deallocate(v51);
  if ( *(_QWORD *)(a4 + 80) )
  {
    v34 = web::uri::encode_data_string(v52, a4 + 96);
    v35 = std::operator+<unsigned short>(v53, a4 + 64, L"=");
    std::wstring::wstring(v51, v36, v35, v34);
    std::vector<std::wstring>::push_back(&v43, v51);
    std::wstring::_Tidy_deallocate(v51);
    std::wstring::_Tidy_deallocate(v53);
    std::wstring::_Tidy_deallocate(v52);
  }
  LOBYTE(v33) = 0;
  std::_Sort_unchecked<std::wstring *,std::less<void>>(v43, v44, (v44 - v43) >> 5, v33);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v48);
  v37 = &v49[*(int *)(v48 + 4) - 8];
  v38 = std::locale::classic();
  std::basic_ios<unsigned short>::imbue(v37, v52, v38);
  std::locale::~locale((std::locale *)v52);
  for ( i = v43; i != v44 - 32; i += 32 )
  {
    v40 = std::operator<<<unsigned short>(&v48, i);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v40, L"&");
  }
  std::operator<<<unsigned short>(&v48, v44 - 32);
  std::basic_stringbuf<unsigned short>::str(v49, v51);
  web::uri::encode_data_string(a2, v51);
  std::wstring::_Tidy_deallocate(v51);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(&v48);
  std::vector<std::wstring>::_Tidy(&v43);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
    v45,
    v45);
  web::uri::~uri(a3);
  return a2;
}

```

## disassembly

```asm
0x18004bb6c  push    rbp
0x18004bb6e  push    rbx
0x18004bb6f  push    rsi
0x18004bb70  push    rdi
0x18004bb71  push    r13
0x18004bb73  push    r14
0x18004bb75  push    r15
0x18004bb77  lea     rbp, [rsp-1B0h]
0x18004bb7f  sub     rsp, 2B0h
0x18004bb86  mov     rax, cs:__security_cookie
0x18004bb8d  xor     rax, rsp
0x18004bb90  mov     [rbp+1E0h+var_38], rax
0x18004bb97  mov     r13, r9
0x18004bb9a  mov     r14, r8
0x18004bb9d  mov     rsi, rdx
0x18004bba0  mov     r15, rcx
0x18004bba3  mov     [rsp+2E0h+var_2C0], rdx
0x18004bba8  mov     [rbp+1E0h+var_A0], r8
0x18004bbaf  lea     rdx, [r8+0A0h]
0x18004bbb6  lea     rcx, [rsp+2E0h+var_298]
0x18004bbbb  call    ?split_query@uri@web@@SA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; web::uri::split_query(std::wstring const &)
0x18004bbc0  nop
0x18004bbc1  lea     rcx, [rsp+2E0h+var_2B8]
0x18004bbc6  call    ??0?$vector@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@V?$allocator@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<pplx::details::_Task_impl<uchar>>>::vector<std::shared_ptr<pplx::details::_Task_impl<uchar>>>(void)
0x18004bbcb  nop
0x18004bbcc  mov     rax, [rsp+2E0h+var_298]
0x18004bbd1  mov     rax, [rax]
0x18004bbd4  mov     [rsp+2E0h+var_2C0], rax
0x18004bbd9  cmp     byte ptr [rax+19h], 0
0x18004bbdd  jnz     loc_18004BC9F
0x18004bbe3  lea     rdi, [rax+20h]
0x18004bbe7  lea     rcx, [rsp+2E0h+var_280]
0x18004bbec  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18004bbf1  nop
0x18004bbf2  mov     rax, [rsp+2E0h+var_280]
0x18004bbf7  movsxd  rcx, dword ptr [rax+4]
0x18004bbfb  lea     rbx, [rsp+2E0h+var_280]
0x18004bc00  add     rbx, rcx
0x18004bc03  call    cs:__imp_?classic@locale@std@@SAAEBV12@XZ; std::locale::classic(void)
0x18004bc09  mov     r8, rax
0x18004bc0c  lea     rdx, [rbp+1E0h+var_78]
0x18004bc13  mov     rcx, rbx
0x18004bc16  call    cs:__imp_?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z; std::basic_ios<ushort>::imbue(std::locale const &)
0x18004bc1c  lea     rcx, [rbp+1E0h+var_78]; this
0x18004bc23  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18004bc28  mov     rdx, rdi
0x18004bc2b  lea     rcx, [rsp+2E0h+var_280]
0x18004bc30  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18004bc35  mov     rcx, rax
0x18004bc38  lea     rdx, asc_180069AA4; "="
0x18004bc3f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18004bc44  mov     rcx, rax
0x18004bc47  lea     rdx, [rdi+20h]
0x18004bc4b  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18004bc50  lea     rdx, [rbp+1E0h+var_98]
0x18004bc57  lea     rcx, [rsp+2E0h+var_278]
0x18004bc5c  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18004bc61  nop
0x18004bc62  lea     rdx, [rbp+1E0h+var_98]
0x18004bc69  lea     rcx, [rsp+2E0h+var_2B8]
0x18004bc6e  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004bc73  nop
0x18004bc74  lea     rcx, [rbp+1E0h+var_98]
0x18004bc7b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bc80  nop
0x18004bc81  lea     rcx, [rsp+2E0h+var_280]
0x18004bc86  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18004bc8b  lea     rcx, [rsp+2E0h+var_2C0]
0x18004bc90  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x18004bc95  mov     rax, [rsp+2E0h+var_2C0]
0x18004bc9a  jmp     loc_18004BBD9
0x18004bc9f  mov     rax, [r15+150h]
0x18004bca6  mov     rax, [rax]
0x18004bca9  mov     [rsp+2E0h+var_2C0], rax
0x18004bcae  cmp     byte ptr [rax+19h], 0
0x18004bcb2  jnz     loc_18004BD74
0x18004bcb8  lea     rdi, [rax+20h]
0x18004bcbc  lea     rcx, [rsp+2E0h+var_280]
0x18004bcc1  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18004bcc6  nop
0x18004bcc7  mov     rax, [rsp+2E0h+var_280]
0x18004bccc  movsxd  rcx, dword ptr [rax+4]
0x18004bcd0  lea     rbx, [rsp+2E0h+var_280]
0x18004bcd5  add     rbx, rcx
0x18004bcd8  call    cs:__imp_?classic@locale@std@@SAAEBV12@XZ; std::locale::classic(void)
0x18004bcde  mov     r8, rax
0x18004bce1  lea     rdx, [rbp+1E0h+var_78]
0x18004bce8  mov     rcx, rbx
0x18004bceb  call    cs:__imp_?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z; std::basic_ios<ushort>::imbue(std::locale const &)
0x18004bcf1  lea     rcx, [rbp+1E0h+var_78]; this
0x18004bcf8  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18004bcfd  mov     rdx, rdi
0x18004bd00  lea     rcx, [rsp+2E0h+var_280]
0x18004bd05  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18004bd0a  mov     rcx, rax
0x18004bd0d  lea     rdx, asc_180069AA4; "="
0x18004bd14  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18004bd19  mov     rcx, rax
0x18004bd1c  lea     rdx, [rdi+20h]
0x18004bd20  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18004bd25  lea     rdx, [rbp+1E0h+var_98]
0x18004bd2c  lea     rcx, [rsp+2E0h+var_278]
0x18004bd31  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18004bd36  nop
0x18004bd37  lea     rdx, [rbp+1E0h+var_98]
0x18004bd3e  lea     rcx, [rsp+2E0h+var_2B8]
0x18004bd43  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004bd48  nop
0x18004bd49  lea     rcx, [rbp+1E0h+var_98]
0x18004bd50  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bd55  nop
0x18004bd56  lea     rcx, [rsp+2E0h+var_280]
0x18004bd5b  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18004bd60  lea     rcx, [rsp+2E0h+var_2C0]
0x18004bd65  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x18004bd6a  mov     rax, [rsp+2E0h+var_2C0]
0x18004bd6f  jmp     loc_18004BCAE
0x18004bd74  lea     r8, a10_0; "=1.0"
0x18004bd7b  lea     rdx, ?version@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::oauth1::details::oauth1_strings::version
0x18004bd82  lea     rcx, [rbp+1E0h+var_98]
0x18004bd89  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18004bd8e  nop
0x18004bd8f  mov     rdx, rax
0x18004bd92  lea     rcx, [rsp+2E0h+var_2B8]
0x18004bd97  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004bd9c  nop
0x18004bd9d  lea     rcx, [rbp+1E0h+var_98]
0x18004bda4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bda9  mov     rdx, r15
0x18004bdac  lea     rcx, [rbp+1E0h+var_58]
0x18004bdb3  call    ?encode_data_string@uri@web@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; web::uri::encode_data_string(std::wstring const &)
0x18004bdb8  mov     rbx, rax
0x18004bdbb  lea     rdi, asc_180067CB0; "="
0x18004bdc2  mov     r8, rdi
0x18004bdc5  lea     rdx, ?consumer_key@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::oauth1::details::oauth1_strings::consumer_key
0x18004bdcc  lea     rcx, [rbp+1E0h+var_78]
0x18004bdd3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18004bdd8  nop
0x18004bdd9  mov     r9, rbx
0x18004bddc  mov     r8, rax
0x18004bddf  lea     rcx, [rbp+1E0h+var_98]
0x18004bde6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x18004bdeb  nop
0x18004bdec  lea     rdx, [rbp+1E0h+var_98]
0x18004bdf3  lea     rcx, [rsp+2E0h+var_2B8]
0x18004bdf8  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004bdfd  nop
0x18004bdfe  lea     rcx, [rbp+1E0h+var_98]
0x18004be05  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004be0a  nop
0x18004be0b  lea     rcx, [rbp+1E0h+var_78]
0x18004be12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004be17  nop
0x18004be18  lea     rcx, [rbp+1E0h+var_58]
0x18004be1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004be24  lea     rdx, [r15+40h]
0x18004be28  cmp     qword ptr [rdx+10h], 0
0x18004be2d  jz      short loc_18004BEA0
0x18004be2f  lea     rcx, [rbp+1E0h+var_78]
0x18004be36  call    ?encode_data_string@uri@web@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; web::uri::encode_data_string(std::wstring const &)
0x18004be3b  mov     rbx, rax
0x18004be3e  mov     r8, rdi
0x18004be41  lea     rdx, ?token@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::oauth1::details::oauth1_strings::token
0x18004be48  lea     rcx, [rbp+1E0h+var_58]
0x18004be4f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18004be54  nop
0x18004be55  mov     r9, rbx
0x18004be58  mov     r8, rax
0x18004be5b  lea     rcx, [rbp+1E0h+var_98]
0x18004be62  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x18004be67  nop
0x18004be68  lea     rdx, [rbp+1E0h+var_98]
0x18004be6f  lea     rcx, [rsp+2E0h+var_2B8]
0x18004be74  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004be79  nop
0x18004be7a  lea     rcx, [rbp+1E0h+var_98]
0x18004be81  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004be86  nop
0x18004be87  lea     rcx, [rbp+1E0h+var_58]
0x18004be8e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004be93  nop
0x18004be94  lea     rcx, [rbp+1E0h+var_78]
0x18004be9b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bea0  mov     r8, rdi
0x18004bea3  lea     rdx, ?signature_method@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::oauth1::details::oauth1_strings::signature_method
0x18004beaa  lea     rcx, [rbp+1E0h+var_98]
0x18004beb1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18004beb6  nop
0x18004beb7  lea     r8, [r15+130h]
0x18004bebe  mov     rdx, rax
0x18004bec1  lea     rcx, [rbp+1E0h+var_58]
0x18004bec8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18004becd  nop
0x18004bece  mov     rdx, rax
0x18004bed1  lea     rcx, [rsp+2E0h+var_2B8]
0x18004bed6  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004bedb  nop
0x18004bedc  lea     rcx, [rbp+1E0h+var_58]
0x18004bee3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bee8  nop
0x18004bee9  lea     rcx, [rbp+1E0h+var_98]
0x18004bef0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bef5  mov     r8, rdi
0x18004bef8  lea     rdx, ?timestamp@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::oauth1::details::oauth1_strings::timestamp
0x18004beff  lea     rcx, [rbp+1E0h+var_98]
0x18004bf06  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18004bf0b  nop
0x18004bf0c  mov     r8, r13
0x18004bf0f  mov     rdx, rax
0x18004bf12  lea     rcx, [rbp+1E0h+var_58]
0x18004bf19  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18004bf1e  nop
0x18004bf1f  mov     rdx, rax
0x18004bf22  lea     rcx, [rsp+2E0h+var_2B8]
0x18004bf27  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004bf2c  nop
0x18004bf2d  lea     rcx, [rbp+1E0h+var_58]
0x18004bf34  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bf39  nop
0x18004bf3a  lea     rcx, [rbp+1E0h+var_98]
0x18004bf41  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bf46  mov     r8, rdi
0x18004bf49  lea     rdx, ?nonce@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::oauth1::details::oauth1_strings::nonce
0x18004bf50  lea     rcx, [rbp+1E0h+var_98]
0x18004bf57  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18004bf5c  nop
0x18004bf5d  lea     r8, [r13+20h]
0x18004bf61  mov     rdx, rax
0x18004bf64  lea     rcx, [rbp+1E0h+var_58]
0x18004bf6b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18004bf70  nop
0x18004bf71  mov     rdx, rax
0x18004bf74  lea     rcx, [rsp+2E0h+var_2B8]
0x18004bf79  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004bf7e  nop
0x18004bf7f  lea     rcx, [rbp+1E0h+var_58]
0x18004bf86  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bf8b  nop
0x18004bf8c  lea     rcx, [rbp+1E0h+var_98]
0x18004bf93  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bf98  cmp     qword ptr [r13+50h], 0
0x18004bf9d  jz      short loc_18004C015
0x18004bf9f  lea     rdx, [r13+60h]
0x18004bfa3  lea     rcx, [rbp+1E0h+var_78]
0x18004bfaa  call    ?encode_data_string@uri@web@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; web::uri::encode_data_string(std::wstring const &)
0x18004bfaf  mov     rbx, rax
0x18004bfb2  lea     r8, asc_180067CB0; "="
0x18004bfb9  lea     rdx, [r13+40h]
0x18004bfbd  lea     rcx, [rbp+1E0h+var_58]
0x18004bfc4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18004bfc9  nop
0x18004bfca  mov     r9, rbx
0x18004bfcd  mov     r8, rax
0x18004bfd0  lea     rcx, [rbp+1E0h+var_98]
0x18004bfd7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x18004bfdc  nop
0x18004bfdd  lea     rdx, [rbp+1E0h+var_98]
0x18004bfe4  lea     rcx, [rsp+2E0h+var_2B8]
0x18004bfe9  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004bfee  nop
0x18004bfef  lea     rcx, [rbp+1E0h+var_98]
0x18004bff6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bffb  nop
0x18004bffc  lea     rcx, [rbp+1E0h+var_58]
0x18004c003  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004c008  nop
0x18004c009  lea     rcx, [rbp+1E0h+var_78]
0x18004c010  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004c015  mov     rdx, [rsp+2E0h+var_2B0]
0x18004c01a  mov     rcx, [rsp+2E0h+var_2B8]
0x18004c01f  xor     r9b, r9b
0x18004c022  mov     r8, rdx
0x18004c025  sub     r8, rcx
0x18004c028  sar     r8, 5
0x18004c02c  call    ??$_Sort_unchecked@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@X@2@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0_JU?$less@X@0@@Z; std::_Sort_unchecked<std::wstring *,std::less<void>>(std::wstring *,std::wstring *,__int64,std::less<void>)
0x18004c031  lea     rcx, [rbp+1E0h+var_190]
0x18004c035  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18004c03a  nop
0x18004c03b  mov     rax, [rbp+1E0h+var_190]
0x18004c03f  movsxd  rcx, dword ptr [rax+4]
0x18004c043  lea     rbx, [rbp+1E0h+var_190]
0x18004c047  add     rbx, rcx
0x18004c04a  call    cs:__imp_?classic@locale@std@@SAAEBV12@XZ; std::locale::classic(void)
0x18004c050  mov     r8, rax
0x18004c053  lea     rdx, [rbp+1E0h+var_78]
0x18004c05a  mov     rcx, rbx
0x18004c05d  call    cs:__imp_?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z; std::basic_ios<ushort>::imbue(std::locale const &)
0x18004c063  lea     rcx, [rbp+1E0h+var_78]; this
0x18004c06a  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18004c06f  mov     rbx, [rsp+2E0h+var_2B8]
0x18004c074  mov     rdx, [rsp+2E0h+var_2B0]
0x18004c079  add     rdx, 0FFFFFFFFFFFFFFE0h
0x18004c07d  lea     rcx, [rbp+1E0h+var_190]
0x18004c081  cmp     rbx, rdx
0x18004c084  jz      short loc_18004C0A3
0x18004c086  mov     rdx, rbx
0x18004c089  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18004c08e  mov     rcx, rax
0x18004c091  lea     rdx, asc_1800698D0; "&"
0x18004c098  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
  ... truncated ...
```
