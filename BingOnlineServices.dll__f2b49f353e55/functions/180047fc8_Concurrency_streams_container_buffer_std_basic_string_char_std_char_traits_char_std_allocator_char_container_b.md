# Concurrency::streams::container_buffer<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>::container_buffer<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>(std::basic_string<char,std::char_traits<char>,std::allocator<char>>,int)

- ea: `0x180047fc8`
- end: `0x18004810b`
- name: `??0?$container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@streams@Concurrency@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@Z`
- size: `323`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800470ac`

## callees

- `0x180004fa0`
- `0x18000529c`
- `0x180009660`
- `0x18000eca4`
- `0x18000fa74`
- `0x1800148ac`
- `0x180042c40`
- `0x180047fc8`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180048042`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180048042`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Concurrency::streams::container_buffer<std::string>::container_buffer<std::string>(
        _QWORD *a1,
        __int64 a2)
{
  _QWORD *v4; // rdi
  __int64 v5; // rbx
  _QWORD *v6; // rax
  std::_Ref_count_base *v7; // r8
  _QWORD v9[2]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v10[8]; // [rsp+30h] [rbp-58h] BYREF
  std::_Ref_count_base *v11; // [rsp+38h] [rbp-50h]
  _BYTE v12[32]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v13; // [rsp+60h] [rbp-28h]

  v13 = a2;
  v4 = operator new(0x58u);
  v9[0] = v4;
  v5 = std::string::string(v12);
  v4[1] = 0;
  v4[2] = 0;
  *v4 = &Concurrency::streams::details::streambuf_state_manager<char>::`vftable';
  v4[3] = 0;
  v4[4] = 0;
  __ExceptionPtrCreate(v4 + 3);
  *((_DWORD *)v4 + 10) = 1;
  *v4 = &Concurrency::streams::details::basic_container_buffer<std::string>::`vftable';
  std::string::string(v4 + 6);
  v4[10] = 0;
  std::string::_Tidy_deallocate(v5);
  v6 = (_QWORD *)std::shared_ptr<Concurrency::streams::details::basic_container_buffer<std::string>>::shared_ptr<Concurrency::streams::details::basic_container_buffer<std::string>>(
                   v10,
                   v4);
  v9[0] = *v6;
  v9[1] = v6[1];
  *v6 = 0;
  v6[1] = 0;
  *a1 = &Concurrency::streams::streambuf<char>::`vftable';
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(a1 + 1, v9);
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  *a1 = &Concurrency::streams::container_buffer<std::string>::`vftable';
  std::string::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x180047fc8  mov     [rsp+arg_10], rbx
0x180047fcd  push    rbp
0x180047fce  push    rsi
0x180047fcf  push    rdi
0x180047fd0  sub     rsp, 70h
0x180047fd4  mov     rax, cs:__security_cookie
0x180047fdb  xor     rax, rsp
0x180047fde  mov     [rsp+88h+var_20], rax
0x180047fe3  mov     rbp, rdx
0x180047fe6  mov     rsi, rcx
0x180047fe9  mov     [rsp+88h+var_28], rcx
0x180047fee  mov     [rsp+88h+var_28], rdx
0x180047ff3  mov     ecx, 58h ; 'X'; Size
0x180047ff8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180047ffd  mov     rdi, rax
0x180048000  mov     [rsp+88h+var_68], rax
0x180048005  mov     rdx, rbp
0x180048008  lea     rcx, [rsp+88h+var_48]
0x18004800d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x180048012  mov     rbx, rax
0x180048015  mov     qword ptr [rdi+8], 0
0x18004801d  mov     qword ptr [rdi+10h], 0
0x180048025  lea     rax, ??_7?$streambuf_state_manager@D@details@streams@Concurrency@@6B@; const Concurrency::streams::details::streambuf_state_manager<char>::`vftable'
0x18004802c  mov     [rdi], rax
0x18004802f  lea     rcx, [rdi+18h]
0x180048033  mov     qword ptr [rcx], 0
0x18004803a  mov     qword ptr [rcx+8], 0
0x180048042  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180048048  mov     dword ptr [rdi+28h], 1
0x18004804f  lea     rax, ??_7?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@6B@; const Concurrency::streams::details::basic_container_buffer<std::string>::`vftable'
0x180048056  mov     [rdi], rax
0x180048059  lea     rcx, [rdi+30h]
0x18004805d  mov     rdx, rbx
0x180048060  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x180048065  mov     qword ptr [rdi+50h], 0
0x18004806d  mov     rcx, rbx
0x180048070  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180048075  mov     rdx, rdi
0x180048078  lea     rcx, [rsp+88h+var_58]
0x18004807d  call    ??$?0V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@$0A@@?$shared_ptr@V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@@std@@QEAA@PEAV?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@@Z; std::shared_ptr<Concurrency::streams::details::basic_container_buffer<std::string>>::shared_ptr<Concurrency::streams::details::basic_container_buffer<std::string>>(Concurrency::streams::details::basic_container_buffer<std::string> *)
0x180048082  mov     rdx, rax
0x180048085  mov     rax, [rax]
0x180048088  mov     [rsp+88h+var_68], rax
0x18004808d  mov     r8, [rdx+8]
0x180048091  mov     [rsp+88h+var_60], r8
0x180048096  mov     qword ptr [rdx], 0
0x18004809d  mov     qword ptr [rdx+8], 0
0x1800480a5  lea     rax, ??_7?$streambuf@D@streams@Concurrency@@6B@; const Concurrency::streams::streambuf<char>::`vftable'
0x1800480ac  mov     [rsi], rax
0x1800480af  lea     rcx, [rsi+8]
0x1800480b3  lea     rdx, [rsp+88h+var_68]
0x1800480b8  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x1800480bd  test    r8, r8
0x1800480c0  jz      short loc_1800480CA
0x1800480c2  mov     rcx, r8; this
0x1800480c5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800480ca  mov     rcx, [rsp+88h+var_50]; this
0x1800480cf  test    rcx, rcx
0x1800480d2  jz      short loc_1800480D9
0x1800480d4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800480d9  lea     rax, ??_7?$container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@streams@Concurrency@@6B@; const Concurrency::streams::container_buffer<std::string>::`vftable'
0x1800480e0  mov     [rsi], rax
0x1800480e3  mov     rcx, rbp
0x1800480e6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800480eb  mov     rax, rsi
0x1800480ee  mov     rcx, [rsp+88h+var_20]
0x1800480f3  xor     rcx, rsp; StackCookie
0x1800480f6  call    __security_check_cookie
0x1800480fb  mov     rbx, [rsp+88h+arg_10]
0x180048103  add     rsp, 70h
0x180048107  pop     rdi
0x180048108  pop     rsi
0x180048109  pop     rbp
0x18004810a  retn
```
