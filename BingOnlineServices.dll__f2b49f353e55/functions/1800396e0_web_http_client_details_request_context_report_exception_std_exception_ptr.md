# web::http::client::details::request_context::report_exception(std::exception_ptr)

- ea: `0x1800396e0`
- end: `0x18003987c`
- name: `?report_exception@request_context@details@client@http@web@@UEAAXVexception_ptr@std@@@Z`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004fa0`
- `0x1800096d4`
- `0x18000eca4`
- `0x18000fa74`
- `0x1800148ac`
- `0x180015084`
- `0x180030ff0`
- `0x180032c78`
- `0x1800342ec`
- `0x1800396e0`
- `0x18003a2bc`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800397a9`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800397a9`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800397b3`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180039813`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180039852`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800397b3`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180039813`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180039852`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800397c8`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800397c8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800397f6`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800397f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall web::http::client::details::request_context::report_exception(__int64 *a1, void *a2)
{
  pplx::details::_CancellationTokenState *v4; // rcx
  __int64 v5; // rax
  const void *v6; // rax
  __int64 v7; // rdi
  void (__fastcall *v8)(__int64, _QWORD, __int128 *); // rbx
  __int128 v9; // [rsp+20h] [rbp-69h] BYREF
  __int64 v10; // [rsp+30h] [rbp-59h] BYREF
  std::_Ref_count_base *v11; // [rsp+38h] [rbp-51h]
  void *v12; // [rsp+40h] [rbp-49h]
  _BYTE v13[16]; // [rsp+48h] [rbp-41h] BYREF
  void **v14; // [rsp+58h] [rbp-31h] BYREF
  __int128 v15; // [rsp+60h] [rbp-29h]
  int v16; // [rsp+70h] [rbp-19h] BYREF
  void ***v17; // [rsp+78h] [rbp-11h]
  _BYTE v18[32]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v19[32]; // [rsp+A0h] [rbp+17h] BYREF

  v12 = a2;
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(&v10, a1 + 5);
  v4 = *(pplx::details::_CancellationTokenState **)(a1[3] + 144);
  if ( v4 && pplx::details::_CancellationTokenState::_IsCanceled(v4) )
  {
    *(_QWORD *)&v9 = &v14;
    v15 = 0;
    v14 = &web::http::http_exception::`vftable';
    v16 = 105;
    v17 = &`std::_Immortalize_memcpy_image<std::_Generic_error_category>'::`2'::_Static;
    std::string::string(v18);
    v5 = std::error_code::message(&v16, v19);
    std::string::operator=(v18, v5);
    std::string::_Tidy_deallocate(v19);
    v6 = (const void *)std::make_exception_ptr<web::http::http_exception>(v13, &v14);
    __ExceptionPtrAssign(a2, v6);
    __ExceptionPtrDestroy(v13);
  }
  v9 = 0;
  __ExceptionPtrCopy(&v9, a2);
  if ( pplx::task_completion_event<web::http::http_response>::set_exception(a1 + 9, &v9) )
  {
    v7 = v10;
    v8 = *(void (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v10 + 16LL);
    v9 = 0;
    __ExceptionPtrCreate(&v9);
    v8(v7, 0, &v9);
    __ExceptionPtrDestroy(&v9);
  }
  else
  {
    (*(void (__fastcall **)(__int64, _QWORD, void *))(*(_QWORD *)v10 + 16LL))(v10, 0, a2);
  }
  (*(void (__fastcall **)(__int64 *))(*a1 + 24))(a1);
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x1800396e0  mov     [rsp-8+arg_10], rbx
0x1800396e5  mov     [rsp-8+arg_18], rsi
0x1800396ea  push    rbp
0x1800396eb  push    rdi
0x1800396ec  push    r14
0x1800396ee  lea     rbp, [rsp-47h]
0x1800396f3  sub     rsp, 0D0h
0x1800396fa  mov     rax, cs:__security_cookie
0x180039701  xor     rax, rsp
0x180039704  mov     [rbp+57h+var_20], rax
0x180039708  mov     rsi, rdx
0x18003970b  mov     r14, rcx
0x18003970e  mov     [rbp+57h+var_A0], rdx
0x180039712  lea     rdx, [rcx+28h]
0x180039716  lea     rcx, [rbp+57h+var_B0]
0x18003971a  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18003971f  nop
0x180039720  mov     rax, [r14+18h]
0x180039724  mov     rcx, [rax+90h]; this
0x18003972b  test    rcx, rcx
0x18003972e  jz      loc_1800397B9
0x180039734  call    ?_IsCanceled@_CancellationTokenState@details@pplx@@QEBA_NXZ; pplx::details::_CancellationTokenState::_IsCanceled(void)
0x180039739  test    al, al
0x18003973b  jz      short loc_1800397B9
0x18003973d  lea     rax, [rbp+57h+var_88]
0x180039741  mov     qword ptr [rbp+57h+var_C0], rax
0x180039745  xorps   xmm0, xmm0
0x180039748  movups  [rbp+57h+var_80], xmm0
0x18003974c  lea     rax, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x180039753  mov     [rbp+57h+var_88], rax
0x180039757  mov     [rbp+57h+var_70], 69h ; 'i'
0x18003975e  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_Generic_error_category@std@@@std@@YAAEBV_Generic_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_Generic_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_Generic_error_category> `std::_Immortalize_memcpy_image<std::_Generic_error_category>(void)'::`2'::_Static
0x180039765  mov     [rbp+57h+var_68], rax
0x180039769  lea     rcx, [rbp+57h+var_60]
0x18003976d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180039772  nop
0x180039773  lea     rdx, [rbp+57h+var_40]
0x180039777  lea     rcx, [rbp+57h+var_70]
0x18003977b  call    ?message@error_code@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::error_code::message(void)
0x180039780  mov     rdx, rax
0x180039783  lea     rcx, [rbp+57h+var_60]
0x180039787  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18003978c  lea     rcx, [rbp+57h+var_40]
0x180039790  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180039795  nop
0x180039796  lea     rdx, [rbp+57h+var_88]
0x18003979a  lea     rcx, [rbp+57h+var_98]
0x18003979e  call    ??$make_exception_ptr@Vhttp_exception@http@web@@@std@@YA?AVexception_ptr@0@Vhttp_exception@http@web@@@Z; std::make_exception_ptr<web::http::http_exception>(web::http::http_exception)
0x1800397a3  mov     rdx, rax
0x1800397a6  mov     rcx, rsi
0x1800397a9  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800397af  lea     rcx, [rbp+57h+var_98]
0x1800397b3  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800397b9  xorps   xmm0, xmm0
0x1800397bc  movdqu  [rbp+57h+var_C0], xmm0
0x1800397c1  mov     rdx, rsi
0x1800397c4  lea     rcx, [rbp+57h+var_C0]
0x1800397c8  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800397ce  lea     rcx, [r14+48h]
0x1800397d2  lea     rdx, [rbp+57h+var_C0]
0x1800397d6  call    ?set_exception@?$task_completion_event@Vhttp_response@http@web@@@pplx@@QEBA_NVexception_ptr@std@@@Z; pplx::task_completion_event<web::http::http_response>::set_exception(std::exception_ptr)
0x1800397db  test    al, al
0x1800397dd  jz      short loc_18003981B
0x1800397df  mov     rdi, [rbp+57h+var_B0]
0x1800397e3  mov     rax, [rdi]
0x1800397e6  mov     rbx, [rax+10h]
0x1800397ea  xorps   xmm0, xmm0
0x1800397ed  movdqu  [rbp+57h+var_C0], xmm0
0x1800397f2  lea     rcx, [rbp+57h+var_C0]
0x1800397f6  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800397fc  nop
0x1800397fd  lea     r8, [rbp+57h+var_C0]
0x180039801  xor     edx, edx
0x180039803  mov     rcx, rdi
0x180039806  mov     rax, rbx
0x180039809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003980e  nop
0x18003980f  lea     rcx, [rbp+57h+var_C0]
0x180039813  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180039819  jmp     short loc_180039830
0x18003981b  mov     rcx, [rbp+57h+var_B0]
0x18003981f  mov     rax, [rcx]
0x180039822  mov     r8, rsi
0x180039825  xor     edx, edx
0x180039827  mov     rax, [rax+10h]
0x18003982b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039830  mov     rax, [r14]
0x180039833  mov     rcx, r14
0x180039836  mov     rax, [rax+18h]
0x18003983a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003983f  nop
0x180039840  mov     rcx, [rbp+57h+var_A8]; this
0x180039844  test    rcx, rcx
0x180039847  jz      short loc_18003984F
0x180039849  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003984e  nop
0x18003984f  mov     rcx, rsi
0x180039852  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180039858  mov     rcx, [rbp+57h+var_20]
0x18003985c  xor     rcx, rsp; StackCookie
0x18003985f  call    __security_check_cookie
0x180039864  lea     r11, [rsp+0E0h+var_10]
0x18003986c  mov     rbx, [r11+30h]
0x180039870  mov     rsi, [r11+38h]
0x180039874  mov     rsp, r11
0x180039877  pop     r14
0x180039879  pop     rdi
0x18003987a  pop     rbp
0x18003987b  retn
```
