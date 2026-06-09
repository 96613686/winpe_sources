# _lambda_a41ba00357f0b11d9ebcc79441882396_::operator()(pplx::task<unsigned __int64>)

- ea: `0x180034690`
- end: `0x18003497b`
- name: `??R_lambda_a41ba00357f0b11d9ebcc79441882396_@@QEBA@V?$task@_K@pplx@@@Z`
- size: `747`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task`

## callers

- `0x180035940`

## callees

- `0x180004fa0`
- `0x180005e9c`
- `0x180007330`
- `0x180009698`
- `0x1800097b4`
- `0x18000eca4`
- `0x18000fa74`
- `0x180012034`
- `0x1800148ac`
- `0x18001588c`
- `0x180023ef0`
- `0x180024118`
- `0x180025488`
- `0x18002dda0`
- `0x18002deb8`
- `0x180033368`
- `0x180034690`
- `0x1800349c4`
- `0x180036bf0`
- `0x1800395a0`
- `0x18004f3e0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348d6`
- `WINHTTP!WinHttpWriteData` at `0x1800348cc`
- `WINHTTP!WinHttpWriteData` at `0x1800348cc`

## string_xrefs

- `0x1800348e1`: `WinHttpWriteData`
- `0x180034718`: `wait() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall _lambda_a41ba00357f0b11d9ebcc79441882396_::operator()(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rax
  unsigned __int64 v5; // r9
  unsigned __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // r10
  __int64 v9; // r8
  _QWORD *v10; // rax
  unsigned __int8 *v11; // rdx
  web::http::details::chunked_encoding *v12; // rcx
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // r12
  _QWORD *base; // rax
  __int64 v16; // r14
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rax
  __int64 *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rax
  DWORD LastError; // edi
  __int64 v30; // rbx
  __int64 v31; // r8
  std::_Ref_count_base *v32; // rcx
  __int64 v33; // rdi
  void (__fastcall *v34)(__int64, __int64); // rbx
  __int64 v35; // rax
  _QWORD *v36; // [rsp+30h] [rbp-F8h] BYREF
  std::_Ref_count_base *v37; // [rsp+38h] [rbp-F0h]
  __int64 v38; // [rsp+40h] [rbp-E8h] BYREF
  std::_Ref_count_base *v39; // [rsp+48h] [rbp-E0h]
  __int64 v40; // [rsp+58h] [rbp-D0h]
  _BYTE v41[24]; // [rsp+60h] [rbp-C8h] BYREF
  _BYTE v42[24]; // [rsp+78h] [rbp-B0h] BYREF
  _BYTE v43[32]; // [rsp+90h] [rbp-98h] BYREF
  _BYTE v44[32]; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+D0h] [rbp-58h] BYREF

  v36 = a1;
  v40 = a2;
  try
  {
    v4 = pplx::task<unsigned __int64>::get();
    v6 = v4;
    v7 = *a1;
    v8 = *(_QWORD *)(*a1 + 160LL);
    if ( v8 )
    {
      v9 = *(_QWORD *)(v7 + 168);
      if ( !v9 )
        v9 = *(_QWORD *)(v7 + 176);
      v10 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, __int64))(*(_QWORD *)v8 + 112LL))(
                        *(_QWORD *)(*a1 + 160LL),
                        &v38,
                        v9 + 10,
                        v4);
      if ( !*v10 )
      {
        pplx::invalid_operation::invalid_operation(
          (pplx::invalid_operation *)pExceptionObject,
          "wait() cannot be called on a default constructed task.");
        throw (pplx::invalid_operation *)pExceptionObject;
      }
      pplx::details::_Task_impl_base::_Wait(*v10);
      if ( v39 )
        std::_Ref_count_base::_Decref(v39);
    }
    v11 = (unsigned __int8 *)(a1[1] + 12LL);
    v12 = *(web::http::details::chunked_encoding **)(*a1 + 168LL);
    if ( !v12 )
      v12 = *(web::http::details::chunked_encoding **)(*a1 + 176LL);
    v13 = v6;
  }
  catch ( ... )
  {
    v33 = *v36;
    v34 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)*v36 + 8LL);
    v35 = std::current_exception(&v38);
    v34(v33, v35);
    v32 = *(std::_Ref_count_base **)(v40 + 8);
    goto LABEL_27;
  }
  v14 = web::http::details::chunked_encoding::add_chunked_delimiters(v12, v11, v13, v5);
  if ( !v6 )
  {
    *(_DWORD *)(*a1 + 108LL) = 0;
    if ( *(_QWORD *)(*a1 + 160LL) )
    {
      base = (_QWORD *)Concurrency::streams::streambuf<char>::get_base();
      v16 = std::vector<std::pair<std::wstring,web::json::value>>::vector<std::pair<std::wstring,web::json::value>>(
              v41,
              *base + 48LL);
      v36 = (_QWORD *)v16;
      v17 = std::vector<std::pair<std::wstring,web::json::value>>::vector<std::pair<std::wstring,web::json::value>>(
              v42,
              v16);
      v18 = Concurrency::streams::container_buffer<std::vector<unsigned char>>::container_buffer<std::vector<unsigned char>>(
              v43,
              v17);
      v21 = Concurrency::streams::streambuf<unsigned char>::streambuf<unsigned char>(v44, v18, v19, v20);
      Concurrency::streams::basic_istream<unsigned char>::basic_istream<unsigned char>(&v38, v21);
      Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v43);
      if ( *(_QWORD *)v16 )
      {
        std::_Deallocate<16>(*(void **)v16, *(_QWORD *)(v16 + 16) - *(_QWORD *)v16);
        *(_QWORD *)v16 = 0;
        *(_QWORD *)(v16 + 8) = 0;
        *(_QWORD *)(v16 + 16) = 0;
      }
      v22 = std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(&v36, &v38);
      v23 = *v22;
      *v22 = *(_QWORD *)(v24 + 144);
      *(_QWORD *)(v24 + 144) = v23;
      v25 = v22[1];
      v22[1] = *(_QWORD *)(v24 + 152);
      *(_QWORD *)(v24 + 152) = v25;
      if ( v37 )
        std::_Ref_count_base::_Decref(v37);
      if ( v39 )
        std::_Ref_count_base::_Decref(v39);
      v26 = *(_QWORD *)(*a1 + 160LL);
      *(_QWORD *)(*a1 + 160LL) = 0;
      if ( v26 )
        std::default_delete<Concurrency::streams::container_buffer<std::vector<unsigned char>>>::operator()();
    }
  }
  v27 = *a1;
  v28 = *(_QWORD *)(*a1 + 168LL);
  if ( !v28 )
    v28 = *(_QWORD *)(v27 + 176);
  if ( !WinHttpWriteData(*(HINTERNET *)(v27 + 96), (LPCVOID)(v28 + v14), v6 - v14 + 12, 0) )
  {
    LastError = GetLastError();
    v30 = *a1;
    std::string::string(v43, "WinHttpWriteData");
    v31 = web::http::client::details::build_error_msg(v44, LastError, v43);
    web::http::client::details::request_context::report_error(v30, LastError, v31);
    std::string::_Tidy_deallocate(v44);
    std::string::_Tidy_deallocate(v43);
  }
  v32 = *(std::_Ref_count_base **)(a2 + 8);
LABEL_27:
  if ( v32 )
    std::_Ref_count_base::_Decref(v32);
}

```

## disassembly

```asm
0x180034690  mov     [rsp+arg_10], rbx
0x180034695  mov     [rsp+arg_18], rdi
0x18003469a  push    r12
0x18003469c  push    r14
0x18003469e  push    r15
0x1800346a0  sub     rsp, 110h
0x1800346a7  mov     rax, cs:__security_cookie
0x1800346ae  xor     rax, rsp
0x1800346b1  mov     [rsp+128h+var_20], rax
0x1800346b9  mov     r15, rdx
0x1800346bc  mov     rbx, rcx
0x1800346bf  mov     [rsp+128h+var_F8], rcx
0x1800346c4  mov     [rsp+128h+var_D0], rdx
0x1800346c9  mov     rcx, rdx
0x1800346cc  call    ?get@?$task@_K@pplx@@QEBA_KXZ; pplx::task<unsigned __int64>::get(void)
0x1800346d1  mov     rdi, rax
0x1800346d4  mov     rcx, [rbx]
0x1800346d7  mov     r10, [rcx+0A0h]
0x1800346de  test    r10, r10
0x1800346e1  jz      short loc_180034759
0x1800346e3  mov     rax, [r10]
0x1800346e6  mov     r8, [rcx+0A8h]
0x1800346ed  test    r8, r8
0x1800346f0  jnz     short loc_1800346F9
0x1800346f2  mov     r8, [rcx+0B0h]
0x1800346f9  add     r8, 0Ah
0x1800346fd  mov     r9, rdi
0x180034700  lea     rdx, [rsp+128h+var_E8]
0x180034705  mov     rcx, r10
0x180034708  mov     rax, [rax+70h]
0x18003470c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034711  nop
0x180034712  cmp     qword ptr [rax], 0
0x180034716  jnz     short loc_180034740
0x180034718  lea     rdx, aWaitCannotBeCa; "wait() cannot be called on a default co"...
0x18003471f  lea     rcx, [rsp+128h+pExceptionObject]; this
0x180034727  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x18003472c  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x180034733  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18003473b  call    _CxxThrowException_0
0x180034740  mov     rcx, [rax]
0x180034743  call    ?_Wait@_Task_impl_base@details@pplx@@QEAA?AW4task_group_status@3@XZ; pplx::details::_Task_impl_base::_Wait(void)
0x180034748  nop
0x180034749  mov     rcx, [rsp+128h+var_E0]; this
0x18003474e  test    rcx, rcx
0x180034751  jz      short loc_180034759
0x180034753  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034758  nop
0x180034759  mov     rdx, [rbx+8]
0x18003475d  add     rdx, 0Ch; unsigned __int8 *
0x180034761  mov     rax, [rbx]
0x180034764  mov     rcx, [rax+0A8h]
0x18003476b  test    rcx, rcx
0x18003476e  jnz     short loc_180034777
0x180034770  mov     rcx, [rax+0B0h]; this
0x180034777  mov     r8, rdi; unsigned __int64
0x18003477a  call    ?add_chunked_delimiters@chunked_encoding@details@http@web@@YA_KPEAE_K1@Z; web::http::details::chunked_encoding::add_chunked_delimiters(uchar *,unsigned __int64,unsigned __int64)
0x18003477f  mov     r12, rax
0x180034782  test    rdi, rdi
0x180034785  jnz     loc_1800348A4
0x18003478b  mov     rcx, [rbx]
0x18003478e  mov     [rcx+6Ch], edi
0x180034791  mov     rcx, [rbx]
0x180034794  mov     rcx, [rcx+0A0h]
0x18003479b  test    rcx, rcx
0x18003479e  jz      loc_1800348A4
0x1800347a4  call    ?get_base@?$streambuf@D@streams@Concurrency@@QEBAAEBV?$shared_ptr@V?$basic_streambuf@D@details@streams@Concurrency@@@std@@XZ; Concurrency::streams::streambuf<char>::get_base(void)
0x1800347a9  mov     rdx, [rax]
0x1800347ac  add     rdx, 30h ; '0'
0x1800347b0  lea     rcx, [rsp+128h+var_C8]
0x1800347b5  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::vector<std::pair<std::wstring,web::json::value>>::vector<std::pair<std::wstring,web::json::value>>(std::vector<std::pair<std::wstring,web::json::value>> &&)
0x1800347ba  mov     r14, rax
0x1800347bd  mov     [rsp+128h+var_F8], rax
0x1800347c2  mov     rdx, rax
0x1800347c5  lea     rcx, [rsp+128h+var_B0]
0x1800347ca  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::vector<std::pair<std::wstring,web::json::value>>::vector<std::pair<std::wstring,web::json::value>>(std::vector<std::pair<std::wstring,web::json::value>> &&)
0x1800347cf  mov     rdx, rax
0x1800347d2  lea     rcx, [rsp+128h+var_98]
0x1800347da  call    ??0?$container_buffer@V?$vector@EV?$allocator@E@std@@@std@@@streams@Concurrency@@QEAA@V?$vector@EV?$allocator@E@std@@@std@@H@Z; Concurrency::streams::container_buffer<std::vector<uchar>>::container_buffer<std::vector<uchar>>(std::vector<uchar>,int)
0x1800347df  nop
0x1800347e0  mov     rdx, rax
0x1800347e3  lea     rcx, [rsp+128h+var_78]
0x1800347eb  call    ??0?$streambuf@E@streams@Concurrency@@QEAA@AEBV012@@Z; Concurrency::streams::streambuf<uchar>::streambuf<uchar>(Concurrency::streams::streambuf<uchar> const &)
0x1800347f0  mov     rdx, rax
0x1800347f3  lea     rcx, [rsp+128h+var_E8]
0x1800347f8  call    ??0?$basic_istream@E@streams@Concurrency@@QEAA@V?$streambuf@E@12@@Z; Concurrency::streams::basic_istream<uchar>::basic_istream<uchar>(Concurrency::streams::streambuf<uchar>)
0x1800347fd  nop
0x1800347fe  lea     rcx, [rsp+128h+var_98]
0x180034806  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x18003480b  nop
0x18003480c  cmp     [r14], rdi
0x18003480f  jz      short loc_18003482B
0x180034811  mov     rdx, [r14+10h]
0x180034815  sub     rdx, [r14]
0x180034818  mov     rcx, [r14]
0x18003481b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180034820  mov     [r14], rdi
0x180034823  mov     [r14+8], rdi
0x180034827  mov     [r14+10h], rdi
0x18003482b  mov     r8, [rbx]
0x18003482e  lea     rdx, [rsp+128h+var_E8]
0x180034833  lea     rcx, [rsp+128h+var_F8]
0x180034838  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18003483d  mov     rdx, [rax]
0x180034840  mov     rcx, [r8+90h]
0x180034847  mov     [rax], rcx
0x18003484a  mov     [r8+90h], rdx
0x180034851  mov     rdx, [rax+8]
0x180034855  mov     rcx, [r8+98h]
0x18003485c  mov     [rax+8], rcx
0x180034860  mov     [r8+98h], rdx
0x180034867  mov     rcx, [rsp+128h+var_F0]; this
0x18003486c  test    rcx, rcx
0x18003486f  jz      short loc_180034876
0x180034871  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034876  mov     rcx, [rsp+128h+var_E0]; this
0x18003487b  test    rcx, rcx
0x18003487e  jz      short loc_180034885
0x180034880  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034885  mov     rax, [rbx]
0x180034888  mov     rdx, [rax+0A0h]
0x18003488f  mov     qword ptr [rax+0A0h], 0
0x18003489a  test    rdx, rdx
0x18003489d  jz      short loc_1800348A4
0x18003489f  call    ??R?$default_delete@V?$container_buffer@V?$vector@EV?$allocator@E@std@@@std@@@streams@Concurrency@@@std@@QEBAXPEAV?$container_buffer@V?$vector@EV?$allocator@E@std@@@std@@@streams@Concurrency@@@Z; std::default_delete<Concurrency::streams::container_buffer<std::vector<uchar>>>::operator()(Concurrency::streams::container_buffer<std::vector<uchar>> *)
0x1800348a4  mov     rcx, [rbx]
0x1800348a7  mov     rax, [rcx+0A8h]
0x1800348ae  test    rax, rax
0x1800348b1  jnz     short loc_1800348BA
0x1800348b3  mov     rax, [rcx+0B0h]
0x1800348ba  sub     edi, r12d
0x1800348bd  lea     r8d, [rdi+0Ch]; dwNumberOfBytesToWrite
0x1800348c1  lea     rdx, [rax+r12]; lpBuffer
0x1800348c5  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x1800348c8  mov     rcx, [rcx+60h]; hRequest
0x1800348cc  call    cs:__imp_WinHttpWriteData
0x1800348d2  test    eax, eax
0x1800348d4  jnz     short loc_180034938
0x1800348d6  call    cs:__imp_GetLastError
0x1800348dc  mov     edi, eax
0x1800348de  mov     rbx, [rbx]
0x1800348e1  lea     rdx, aWinhttpwriteda; "WinHttpWriteData"
0x1800348e8  lea     rcx, [rsp+128h+var_98]
0x1800348f0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800348f5  nop
0x1800348f6  lea     r8, [rsp+128h+var_98]
0x1800348fe  mov     edx, edi
0x180034900  lea     rcx, [rsp+128h+var_78]
0x180034908  call    web__http__client__details__build_error_msg
0x18003490d  nop
0x18003490e  mov     r8, rax
0x180034911  mov     edx, edi
0x180034913  mov     rcx, rbx
0x180034916  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x18003491b  nop
0x18003491c  lea     rcx, [rsp+128h+var_78]
0x180034924  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180034929  nop
0x18003492a  lea     rcx, [rsp+128h+var_98]
0x180034932  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180034937  nop
0x180034938  mov     rcx, [r15+8]
0x18003493c  jmp     short loc_180034947
0x18003493e  mov     rax, [rsp+128h+var_D0]
0x180034943  mov     rcx, [rax+8]; this
0x180034947  test    rcx, rcx
0x18003494a  jz      short loc_180034951
0x18003494c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034951  mov     rcx, [rsp+128h+var_20]
0x180034959  xor     rcx, rsp; StackCookie
0x18003495c  call    __security_check_cookie
0x180034961  lea     r11, [rsp+128h+var_18]
0x180034969  mov     rbx, [r11+30h]
0x18003496d  mov     rdi, [r11+38h]
0x180034971  mov     rsp, r11
0x180034974  pop     r15
0x180034976  pop     r14
0x180034978  pop     r12
0x18003497a  retn
```
