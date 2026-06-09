# web::http::http_pipeline::append(std::shared_ptr<web::http::http_pipeline_stage> const &)

- ea: `0x180036abc`
- end: `0x180036b9c`
- name: `?append@http_pipeline@http@web@@QEAAXAEBV?$shared_ptr@Vhttp_pipeline_stage@http@web@@@std@@@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180036e20`

## callees

- `0x18000fa74`
- `0x1800104a0`
- `0x1800106f8`
- `0x180012d88`
- `0x1800148ac`
- `0x180036abc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036aed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036aed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036b8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036b8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036ad4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036ad4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall web::http::http_pipeline::append(__int64 *a1, _QWORD *a2)
{
  __int64 *v4; // rbx
  DWORD CurrentThreadId; // ebp
  __int64 v6; // rax
  _QWORD *v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-38h] BYREF
  std::_Ref_count_base *v10; // [rsp+28h] [rbp-30h]

  v4 = a1 + 5;
  CurrentThreadId = GetCurrentThreadId();
  if ( *((_DWORD *)v4 + 17) == CurrentThreadId )
  {
    ++*((_DWORD *)v4 + 16);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)v4);
    *((_DWORD *)v4 + 17) = CurrentThreadId;
    *((_DWORD *)v4 + 16) = 1;
  }
  v6 = (a1[1] - *a1) >> 4;
  if ( v6 )
  {
    std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(
      &v9,
      (_QWORD *)(16 * v6 + *a1 - 16));
    std::shared_ptr<web::http::http_pipeline_stage>::operator=(v9 + 24, a2);
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
  }
  std::shared_ptr<web::http::http_pipeline_stage>::operator=(*a2 + 24LL, a1 + 3);
  v7 = (_QWORD *)a1[1];
  if ( v7 == (_QWORD *)a1[2] )
  {
    std::vector<std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>>>::_Emplace_reallocate<std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &>(
      a1,
      a1[1],
      a2);
  }
  else
  {
    std::_Construct_in_place<std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::CopyrightData>>,std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::CopyrightData>> const &>(
      v7,
      a2);
    a1[1] += 16;
  }
  if ( (*((_DWORD *)v4 + 16))-- == 1 )
  {
    *((_DWORD *)v4 + 17) = -1;
    LeaveCriticalSection((LPCRITICAL_SECTION)v4);
  }
}

```

## disassembly

```asm
0x180036abc  push    rbx
0x180036abe  push    rbp
0x180036abf  push    rsi
0x180036ac0  push    rdi
0x180036ac1  sub     rsp, 38h
0x180036ac5  mov     rsi, rdx
0x180036ac8  mov     rdi, rcx
0x180036acb  lea     rbx, [rcx+28h]
0x180036acf  mov     [rsp+58h+arg_0], rbx
0x180036ad4  call    cs:__imp_GetCurrentThreadId
0x180036ada  mov     ebp, eax
0x180036adc  mov     r8d, [rbx+44h]
0x180036ae0  cmp     r8d, eax
0x180036ae3  jnz     short loc_180036AEA
0x180036ae5  inc     dword ptr [rbx+40h]
0x180036ae8  jmp     short loc_180036AFD
0x180036aea  mov     rcx, rbx; lpCriticalSection
0x180036aed  call    cs:__imp_EnterCriticalSection
0x180036af3  mov     [rbx+44h], ebp
0x180036af6  mov     dword ptr [rbx+40h], 1
0x180036afd  mov     rcx, [rdi]
0x180036b00  mov     rax, [rdi+8]
0x180036b04  sub     rax, rcx
0x180036b07  sar     rax, 4
0x180036b0b  test    rax, rax
0x180036b0e  jz      short loc_180036B45
0x180036b10  shl     rax, 4
0x180036b14  lea     rdx, [rcx-10h]
0x180036b18  add     rdx, rax
0x180036b1b  lea     rcx, [rsp+58h+var_38]
0x180036b20  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x180036b25  mov     rcx, [rsp+58h+var_38]
0x180036b2a  add     rcx, 18h
0x180036b2e  mov     rdx, rsi
0x180036b31  call    ??4?$shared_ptr@Vhttp_pipeline_stage@http@web@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<web::http::http_pipeline_stage>::operator=(std::shared_ptr<web::http::http_pipeline_stage> const &)
0x180036b36  mov     rcx, [rsp+58h+var_30]; this
0x180036b3b  test    rcx, rcx
0x180036b3e  jz      short loc_180036B45
0x180036b40  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036b45  lea     rdx, [rdi+18h]
0x180036b49  mov     rcx, [rsi]
0x180036b4c  add     rcx, 18h
0x180036b50  call    ??4?$shared_ptr@Vhttp_pipeline_stage@http@web@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<web::http::http_pipeline_stage>::operator=(std::shared_ptr<web::http::http_pipeline_stage> const &)
0x180036b55  mov     rcx, [rdi+8]
0x180036b59  cmp     rcx, [rdi+10h]
0x180036b5d  jz      short loc_180036B6E
0x180036b5f  mov     rdx, rsi
0x180036b62  call    ??$_Construct_in_place@V?$shared_ptr@U?$_Task_impl@VCopyrightData@BingOnlineServices@@@details@pplx@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@U?$_Task_impl@VCopyrightData@BingOnlineServices@@@details@pplx@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::CopyrightData>>,std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::CopyrightData>> const &>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::CopyrightData>> &,std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::CopyrightData>> const &)
0x180036b67  add     qword ptr [rdi+8], 10h
0x180036b6c  jmp     short loc_180036B7D
0x180036b6e  mov     r8, rsi
0x180036b71  mov     rdx, rcx
0x180036b74  mov     rcx, rdi
0x180036b77  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@std@@@?$vector@V?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@std@@V?$allocator@V?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>>>::_Emplace_reallocate<std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> * const,std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x180036b7c  nop
0x180036b7d  sub     dword ptr [rbx+40h], 1
0x180036b81  jnz     short loc_180036B93
0x180036b83  mov     dword ptr [rbx+44h], 0FFFFFFFFh
0x180036b8a  mov     rcx, rbx; lpCriticalSection
0x180036b8d  call    cs:__imp_LeaveCriticalSection
0x180036b93  add     rsp, 38h
0x180036b97  pop     rdi
0x180036b98  pop     rsi
0x180036b99  pop     rbp
0x180036b9a  pop     rbx
0x180036b9b  retn
```
