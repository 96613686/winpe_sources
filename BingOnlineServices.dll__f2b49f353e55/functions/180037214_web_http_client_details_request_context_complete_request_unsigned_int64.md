# web::http::client::details::request_context::complete_request(unsigned __int64)

- ea: `0x180037214`
- end: `0x18003729b`
- name: `?complete_request@request_context@details@client@http@web@@QEAAX_K@Z`
- size: `135`
- prototype: `void __fastcall(web::http::client::details::request_context *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800372b0`
- `0x180039418`

## callees

- `0x18000fa74`
- `0x1800148ac`
- `0x180037214`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003726d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003726d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003724d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003724d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall web::http::client::details::request_context::complete_request(
        web::http::client::details::request_context *this,
        __int64 a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, __int64, __int128 *); // rbx
  __int128 v6; // [rsp+20h] [rbp-48h] BYREF
  __int64 v7; // [rsp+30h] [rbp-38h] BYREF
  std::_Ref_count_base *v8; // [rsp+38h] [rbp-30h]

  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(&v7, (_QWORD *)this + 5);
  v4 = v7;
  v5 = *(void (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v7 + 16LL);
  v6 = 0;
  __ExceptionPtrCreate(&v6);
  v5(v4, a2, &v6);
  __ExceptionPtrDestroy(&v6);
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  (*(void (__fastcall **)(web::http::client::details::request_context *))(*(_QWORD *)this + 24LL))(this);
}

```

## disassembly

```asm
0x180037214  push    rbx
0x180037216  push    rsi
0x180037217  push    rdi
0x180037218  push    r14
0x18003721a  sub     rsp, 48h
0x18003721e  mov     rsi, rdx
0x180037221  mov     r14, rcx
0x180037224  lea     rdx, [rcx+28h]
0x180037228  lea     rcx, [rsp+68h+var_38]
0x18003722d  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x180037232  nop
0x180037233  mov     rdi, [rsp+68h+var_38]
0x180037238  mov     rax, [rdi]
0x18003723b  mov     rbx, [rax+10h]
0x18003723f  xorps   xmm0, xmm0
0x180037242  movdqu  [rsp+68h+var_48], xmm0
0x180037248  lea     rcx, [rsp+68h+var_48]
0x18003724d  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180037253  nop
0x180037254  lea     r8, [rsp+68h+var_48]
0x180037259  mov     rdx, rsi
0x18003725c  mov     rcx, rdi
0x18003725f  mov     rax, rbx
0x180037262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037267  nop
0x180037268  lea     rcx, [rsp+68h+var_48]
0x18003726d  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180037273  nop
0x180037274  mov     rcx, [rsp+68h+var_30]; this
0x180037279  test    rcx, rcx
0x18003727c  jz      short loc_180037283
0x18003727e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037283  mov     rax, [r14]
0x180037286  mov     rcx, r14
0x180037289  mov     rax, [rax+18h]
0x18003728d  add     rsp, 48h
0x180037291  pop     r14
0x180037293  pop     rdi
0x180037294  pop     rsi
0x180037295  pop     rbx
0x180037296  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
