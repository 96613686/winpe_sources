# web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)

- ea: `0x1800362a8`
- end: `0x1800364f1`
- name: `?_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@@Z`
- size: `585`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task`

## callers

- `0x1800372b0`

## callees

- `0x180002c2c`
- `0x180002ca8`
- `0x180004fa0`
- `0x180009698`
- `0x18000eca4`
- `0x180012430`
- `0x1800148ac`
- `0x180024118`
- `0x180025488`
- `0x18002bd20`
- `0x18002cfc0`
- `0x18002dff0`
- `0x180032f64`
- `0x1800362a8`
- `0x180036a50`
- `0x180036bf0`
- `0x1800395a0`
- `0x180039654`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180036341`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180036341`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003634d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003634d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003640e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003640e`
- `WINHTTP!WinHttpWriteData` at `0x180036400`
- `WINHTTP!WinHttpWriteData` at `0x180036400`

## string_xrefs

- `0x180036416`: `WinHttpWriteData`
- `0x180036357`: `Error reading outgoing HTTP body from its stream.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall web::http::client::details::winhttp_client::_multiple_segment_write_data(
        struct web::http::client::details::winhttp_request_context *a1)
{
  unsigned __int64 v2; // rbx
  unsigned __int64 v3; // rax
  const void *v4; // rax
  bool v5; // bl
  DWORD v6; // eax
  void (__fastcall *v7)(struct web::http::client::details::winhttp_request_context *, __int64); // rbx
  __int64 v8; // rax
  const void **v9; // rsi
  bool v10; // zf
  const void *v11; // rdx
  DWORD LastError; // ebx
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  DWORD dwNumberOfBytesToWrite[2]; // [rsp+20h] [rbp-49h] BYREF
  _BYTE v19[16]; // [rsp+28h] [rbp-41h] BYREF
  const void *v20; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v21[24]; // [rsp+40h] [rbp-29h] BYREF
  struct web::http::client::details::winhttp_request_context *v22; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v23[24]; // [rsp+60h] [rbp-9h] BYREF
  char v24[8]; // [rsp+78h] [rbp+Fh] BYREF
  std::_Ref_count_base *v25; // [rsp+80h] [rbp+17h]

  (*(void (__fastcall **)(struct web::http::client::details::winhttp_request_context *, _BYTE *))(*(_QWORD *)a1 + 16LL))(
    a1,
    v21);
  v2 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 656LL);
  if ( !v2 )
    v2 = 0x10000;
  if ( *((_QWORD *)a1 + 14) <= v2 )
    v2 = *((_QWORD *)a1 + 14);
  v20 = 0;
  *(_QWORD *)dwNumberOfBytesToWrite = 0;
  if ( (unsigned __int8)Concurrency::streams::streambuf<unsigned char>::acquire(v21, &v20, dwNumberOfBytesToWrite) )
  {
    v3 = *(_QWORD *)dwNumberOfBytesToWrite;
    if ( *(_QWORD *)dwNumberOfBytesToWrite )
    {
      v9 = (const void **)((char *)a1 + 168);
      if ( v20 )
      {
        *v9 = v20;
      }
      else
      {
        web::http::client::details::memory_holder::allocate_space(
          (struct web::http::client::details::winhttp_request_context *)((char *)a1 + 168),
          *(unsigned __int64 *)dwNumberOfBytesToWrite);
        v3 = *(_QWORD *)dwNumberOfBytesToWrite;
      }
      if ( v2 > v3 )
        v2 = v3;
      v10 = *((_QWORD *)a1 + 14) == v2;
      *((_QWORD *)a1 + 14) -= v2;
      if ( v10 )
        *((_DWORD *)a1 + 27) = 0;
      v11 = *v9;
      if ( !*v9 )
        v11 = (const void *)*((_QWORD *)a1 + 22);
      if ( !WinHttpWriteData(*((HINTERNET *)a1 + 12), v11, v2, 0) )
      {
        LastError = GetLastError();
        std::string::string(&v22, "WinHttpWriteData");
        v13 = web::http::client::details::build_error_msg(v24, LastError, &v22);
        web::http::client::details::request_context::report_error(a1, LastError, v13);
        std::string::_Tidy_deallocate(v24);
        std::string::_Tidy_deallocate(&v22);
      }
    }
    else
    {
      v4 = (const void *)Concurrency::streams::streambuf<unsigned char>::exception(v21, v19);
      v5 = __ExceptionPtrToBool(v4);
      __ExceptionPtrDestroy(v19);
      if ( v5 )
      {
        v7 = *(void (__fastcall **)(struct web::http::client::details::winhttp_request_context *, __int64))(*(_QWORD *)a1 + 8LL);
        v8 = Concurrency::streams::streambuf<unsigned char>::exception(v21, v19);
        v7(a1, v8);
      }
      else
      {
        std::wstring::wstring(&v22, L"Error reading outgoing HTTP body from its stream.");
        v6 = GetLastError();
        web::http::client::details::request_context::report_error(a1, v6, &v22);
        std::wstring::_Tidy_deallocate(&v22);
      }
    }
  }
  else
  {
    web::http::client::details::memory_holder::allocate_space(
      (struct web::http::client::details::winhttp_request_context *)((char *)a1 + 168),
      v2);
    v14 = *((_QWORD *)a1 + 21);
    if ( !v14 )
      v14 = *((_QWORD *)a1 + 22);
    v15 = Concurrency::streams::streambuf<char>::getn(v21, v24, v14, v2);
    v22 = a1;
    Concurrency::streams::streambuf<unsigned char>::streambuf<unsigned char>(v23, v21, v16, v15);
    pplx::task<unsigned __int64>::then<_lambda_516d7c939ecebbebb832680ebce1ae2b_>(v17, v19, &v22);
    pplx::task<long>::~task<long>(v19);
    Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v23);
    if ( v25 )
      std::_Ref_count_base::_Decref(v25);
  }
  Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v21);
}

```

## disassembly

```asm
0x1800362a8  push    rbp
0x1800362aa  push    rbx
0x1800362ab  push    rsi
0x1800362ac  push    rdi
0x1800362ad  lea     rbp, [rsp-3Fh]
0x1800362b2  sub     rsp, 0A8h
0x1800362b9  mov     rax, cs:__security_cookie
0x1800362c0  xor     rax, rsp
0x1800362c3  mov     [rbp+57h+var_28], rax
0x1800362c7  mov     rdi, rcx
0x1800362ca  mov     rax, [rcx]
0x1800362cd  lea     rdx, [rbp+57h+var_80]
0x1800362d1  mov     rax, [rax+10h]
0x1800362d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362da  nop
0x1800362db  mov     rax, [rdi+8]
0x1800362df  mov     rbx, [rax+290h]
0x1800362e6  mov     eax, 10000h
0x1800362eb  test    rbx, rbx
0x1800362ee  cmovz   rbx, rax
0x1800362f2  cmp     [rdi+70h], rbx
0x1800362f6  cmovbe  rbx, [rdi+70h]
0x1800362fb  mov     [rbp+57h+var_88], 0
0x180036303  mov     qword ptr [rbp+57h+dwNumberOfBytesToWrite], 0
0x18003630b  lea     r8, [rbp+57h+dwNumberOfBytesToWrite]
0x18003630f  lea     rdx, [rbp+57h+var_88]
0x180036313  lea     rcx, [rbp+57h+var_80]
0x180036317  call    ?acquire@?$streambuf@E@streams@Concurrency@@UEAA_NAEAPEAEAEA_K@Z; Concurrency::streams::streambuf<uchar>::acquire(uchar * &,unsigned __int64 &)
0x18003631c  test    al, al
0x18003631e  jz      loc_18003645A
0x180036324  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x180036328  test    rax, rax
0x18003632b  jnz     loc_1800363B2
0x180036331  lea     rdx, [rbp+57h+var_98]
0x180036335  lea     rcx, [rbp+57h+var_80]
0x180036339  call    ?exception@?$streambuf@E@streams@Concurrency@@UEBA?AVexception_ptr@std@@XZ; Concurrency::streams::streambuf<uchar>::exception(void)
0x18003633e  mov     rcx, rax
0x180036341  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180036347  mov     bl, al
0x180036349  lea     rcx, [rbp+57h+var_98]
0x18003634d  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180036353  test    bl, bl
0x180036355  jnz     short loc_18003638B
0x180036357  lea     rdx, aErrorReadingOu; "Error reading outgoing HTTP body from i"...
0x18003635e  lea     rcx, [rbp+57h+var_68]
0x180036362  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180036367  nop
0x180036368  call    cs:__imp_GetLastError
0x18003636e  lea     r8, [rbp+57h+var_68]
0x180036372  mov     edx, eax
0x180036374  mov     rcx, rdi
0x180036377  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::wstring const &)
0x18003637c  nop
0x18003637d  lea     rcx, [rbp+57h+var_68]
0x180036381  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036386  jmp     loc_1800364D0
0x18003638b  mov     rax, [rdi]
0x18003638e  mov     rbx, [rax+8]
0x180036392  lea     rdx, [rbp+57h+var_98]
0x180036396  lea     rcx, [rbp+57h+var_80]
0x18003639a  call    ?exception@?$streambuf@E@streams@Concurrency@@UEBA?AVexception_ptr@std@@XZ; Concurrency::streams::streambuf<uchar>::exception(void)
0x18003639f  mov     rdx, rax
0x1800363a2  mov     rcx, rdi
0x1800363a5  mov     rax, rbx
0x1800363a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363ad  jmp     loc_1800364D0
0x1800363b2  mov     rcx, [rbp+57h+var_88]
0x1800363b6  lea     rsi, [rdi+0A8h]
0x1800363bd  test    rcx, rcx
0x1800363c0  jnz     short loc_1800363D3
0x1800363c2  mov     rdx, rax; unsigned __int64
0x1800363c5  mov     rcx, rsi; this
0x1800363c8  call    ?allocate_space@memory_holder@details@client@http@web@@QEAAX_K@Z; web::http::client::details::memory_holder::allocate_space(unsigned __int64)
0x1800363cd  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x1800363d1  jmp     short loc_1800363D6
0x1800363d3  mov     [rsi], rcx
0x1800363d6  cmp     rbx, rax
0x1800363d9  cmova   rbx, rax
0x1800363dd  sub     [rdi+70h], rbx
0x1800363e1  jnz     short loc_1800363EA
0x1800363e3  mov     dword ptr [rdi+6Ch], 0
0x1800363ea  mov     rdx, [rsi]
0x1800363ed  test    rdx, rdx
0x1800363f0  jnz     short loc_1800363F6
0x1800363f2  mov     rdx, [rsi+8]; lpBuffer
0x1800363f6  mov     r8d, ebx; dwNumberOfBytesToWrite
0x1800363f9  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x1800363fc  mov     rcx, [rdi+60h]; hRequest
0x180036400  call    cs:__imp_WinHttpWriteData
0x180036406  test    eax, eax
0x180036408  jnz     loc_1800364D0
0x18003640e  call    cs:__imp_GetLastError
0x180036414  mov     ebx, eax
0x180036416  lea     rdx, aWinhttpwriteda; "WinHttpWriteData"
0x18003641d  lea     rcx, [rbp+57h+var_68]
0x180036421  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180036426  nop
0x180036427  lea     r8, [rbp+57h+var_68]
0x18003642b  mov     edx, ebx
0x18003642d  lea     rcx, [rbp+57h+var_48]
0x180036431  call    web__http__client__details__build_error_msg
0x180036436  nop
0x180036437  mov     r8, rax
0x18003643a  mov     edx, ebx
0x18003643c  mov     rcx, rdi
0x18003643f  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180036444  nop
0x180036445  lea     rcx, [rbp+57h+var_48]
0x180036449  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003644e  nop
0x18003644f  lea     rcx, [rbp+57h+var_68]
0x180036453  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180036458  jmp     short loc_1800364D0
0x18003645a  lea     rsi, [rdi+0A8h]
0x180036461  mov     rdx, rbx; unsigned __int64
0x180036464  mov     rcx, rsi; this
0x180036467  call    ?allocate_space@memory_holder@details@client@http@web@@QEAAX_K@Z; web::http::client::details::memory_holder::allocate_space(unsigned __int64)
0x18003646c  mov     r8, [rsi]
0x18003646f  test    r8, r8
0x180036472  jnz     short loc_180036478
0x180036474  mov     r8, [rsi+8]
0x180036478  mov     r9, rbx
0x18003647b  lea     rdx, [rbp+57h+var_48]
0x18003647f  lea     rcx, [rbp+57h+var_80]
0x180036483  call    ?getn@?$streambuf@D@streams@Concurrency@@UEAA?AV?$task@_K@pplx@@PEAD_K@Z; Concurrency::streams::streambuf<char>::getn(char *,unsigned __int64)
0x180036488  mov     r9, rax
0x18003648b  mov     [rbp+57h+var_68], rdi
0x18003648f  lea     rdx, [rbp+57h+var_80]
0x180036493  lea     rcx, [rbp+57h+var_60]
0x180036497  call    ??0?$streambuf@E@streams@Concurrency@@QEAA@AEBV012@@Z; Concurrency::streams::streambuf<uchar>::streambuf<uchar>(Concurrency::streams::streambuf<uchar> const &)
0x18003649c  nop
0x18003649d  lea     r8, [rbp+57h+var_68]
0x1800364a1  lea     rdx, [rbp+57h+var_98]
0x1800364a5  mov     rcx, r9
0x1800364a8  call    ??$then@V_lambda_516d7c939ecebbebb832680ebce1ae2b_@@@?$task@_K@pplx@@QEBA?AV?$task@X@1@AEBV_lambda_516d7c939ecebbebb832680ebce1ae2b_@@@Z; pplx::task<unsigned __int64>::then<_lambda_516d7c939ecebbebb832680ebce1ae2b_>(_lambda_516d7c939ecebbebb832680ebce1ae2b_ const &)
0x1800364ad  lea     rcx, [rbp+57h+var_98]; void *
0x1800364b1  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x1800364b6  nop
0x1800364b7  lea     rcx, [rbp+57h+var_60]
0x1800364bb  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x1800364c0  nop
0x1800364c1  mov     rcx, [rbp+57h+var_40]; this
0x1800364c5  test    rcx, rcx
0x1800364c8  jz      short loc_1800364D0
0x1800364ca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800364cf  nop
0x1800364d0  lea     rcx, [rbp+57h+var_80]
0x1800364d4  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x1800364d9  mov     rcx, [rbp+57h+var_28]
0x1800364dd  xor     rcx, rsp; StackCookie
0x1800364e0  call    __security_check_cookie
0x1800364e5  add     rsp, 0A8h
0x1800364ec  pop     rdi
0x1800364ed  pop     rsi
0x1800364ee  pop     rbx
0x1800364ef  pop     rbp
0x1800364f0  retn
```
