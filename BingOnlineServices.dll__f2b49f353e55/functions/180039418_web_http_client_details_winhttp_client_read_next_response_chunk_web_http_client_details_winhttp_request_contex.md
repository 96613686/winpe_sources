# web::http::client::details::winhttp_client::read_next_response_chunk(web::http::client::details::winhttp_request_context *,ulong,bool)

- ea: `0x180039418`
- end: `0x180039585`
- name: `?read_next_response_chunk@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@K_N@Z`
- size: `365`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *, unsigned int, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180034598`
- `0x1800372b0`

## callees

- `0x180004fa0`
- `0x180009698`
- `0x18000eca4`
- `0x180025488`
- `0x18002bd70`
- `0x180036144`
- `0x180036a50`
- `0x180036bf0`
- `0x180037214`
- `0x180039418`
- `0x1800395a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003945e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003945e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039519`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180039450`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180039450`
- `WINHTTP!WinHttpReadData` at `0x18003950f`
- `WINHTTP!WinHttpReadData` at `0x18003950f`

## string_xrefs

- `0x180039521`: `WinHttpReadData`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall web::http::client::details::winhttp_client::read_next_response_chunk(
        struct web::http::client::details::winhttp_request_context *a1,
        unsigned int a2,
        char a3)
{
  unsigned __int64 v4; // rsi
  DWORD v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 *v8; // rbx
  void *v9; // rdx
  DWORD LastError; // ebx
  __int64 v11; // rax
  _BYTE v12[32]; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v13[32]; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v14[32]; // [rsp+60h] [rbp+7h] BYREF

  v4 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 656LL);
  if ( v4 )
  {
    if ( a2 >= v4 || a3 )
    {
      web::http::client::details::request_context::_get_writebuffer(a1, v12);
      v7 = Concurrency::streams::streambuf<unsigned char>::alloc(v12, v4);
      v8 = (__int64 *)((char *)a1 + 168);
      if ( v7 )
        *v8 = v7;
      else
        web::http::client::details::memory_holder::allocate_space(
          (struct web::http::client::details::winhttp_request_context *)((char *)a1 + 168),
          v4);
      v9 = (void *)*v8;
      if ( !*v8 )
        v9 = (void *)*((_QWORD *)a1 + 22);
      if ( !WinHttpReadData(*((HINTERNET *)a1 + 12), v9, v4, 0) )
      {
        LastError = GetLastError();
        std::string::string(v13, "WinHttpReadData");
        v11 = web::http::client::details::build_error_msg(v14, LastError, v13);
        web::http::client::details::request_context::report_error(a1, LastError, v11);
        std::string::_Tidy_deallocate(v14);
        std::string::_Tidy_deallocate(v13);
      }
      Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v12);
    }
    else
    {
      web::http::client::details::request_context::complete_request(a1, *((_QWORD *)a1 + 8));
    }
  }
  else if ( !WinHttpQueryDataAvailable(*((HINTERNET *)a1 + 12), 0) )
  {
    v5 = GetLastError();
    std::string::string(v12, "WinHttpQueryDataAvaliable");
    v6 = web::http::client::details::build_error_msg(v13, v5, v12);
    web::http::client::details::request_context::report_error(a1, v5, v6);
    std::string::_Tidy_deallocate(v13);
    std::string::_Tidy_deallocate(v12);
  }
}

```

## disassembly

```asm
0x180039418  push    rbp
0x18003941a  push    rbx
0x18003941b  push    rsi
0x18003941c  push    rdi
0x18003941d  lea     rbp, [rsp-3Fh]
0x180039422  sub     rsp, 98h
0x180039429  mov     rax, cs:__security_cookie
0x180039430  xor     rax, rsp
0x180039433  mov     [rbp+57h+var_30], rax
0x180039437  mov     rdi, rcx
0x18003943a  mov     rax, [rcx+8]
0x18003943e  mov     rsi, [rax+290h]
0x180039445  test    rsi, rsi
0x180039448  jnz     short loc_1800394AD
0x18003944a  xor     edx, edx; lpdwNumberOfBytesAvailable
0x18003944c  mov     rcx, [rcx+60h]; hRequest
0x180039450  call    cs:__imp_WinHttpQueryDataAvailable
0x180039456  test    eax, eax
0x180039458  jnz     loc_18003956D
0x18003945e  call    cs:__imp_GetLastError
0x180039464  mov     ebx, eax
0x180039466  lea     rdx, aWinhttpqueryda; "WinHttpQueryDataAvaliable"
0x18003946d  lea     rcx, [rbp+57h+var_90]
0x180039471  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180039476  nop
0x180039477  lea     r8, [rbp+57h+var_90]
0x18003947b  mov     edx, ebx
0x18003947d  lea     rcx, [rbp+57h+var_70]
0x180039481  call    web__http__client__details__build_error_msg
0x180039486  nop
0x180039487  mov     r8, rax
0x18003948a  mov     edx, ebx
0x18003948c  mov     rcx, rdi
0x18003948f  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180039494  nop
0x180039495  lea     rcx, [rbp+57h+var_70]
0x180039499  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003949e  nop
0x18003949f  lea     rcx, [rbp+57h+var_90]
0x1800394a3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800394a8  jmp     loc_18003956D
0x1800394ad  mov     eax, edx
0x1800394af  cmp     rax, rsi
0x1800394b2  jnb     short loc_1800394C7
0x1800394b4  test    r8b, r8b
0x1800394b7  jnz     short loc_1800394C7
0x1800394b9  mov     rdx, [rcx+40h]; unsigned __int64
0x1800394bd  call    ?complete_request@request_context@details@client@http@web@@QEAAX_K@Z; web::http::client::details::request_context::complete_request(unsigned __int64)
0x1800394c2  jmp     loc_18003956D
0x1800394c7  lea     rdx, [rbp+57h+var_90]
0x1800394cb  call    ?_get_writebuffer@request_context@details@client@http@web@@QEAA?AV?$streambuf@E@streams@Concurrency@@XZ; web::http::client::details::request_context::_get_writebuffer(void)
0x1800394d0  nop
0x1800394d1  mov     rdx, rsi
0x1800394d4  lea     rcx, [rbp+57h+var_90]
0x1800394d8  call    ?alloc@?$streambuf@E@streams@Concurrency@@UEAAPEAE_K@Z; Concurrency::streams::streambuf<uchar>::alloc(unsigned __int64)
0x1800394dd  lea     rbx, [rdi+0A8h]
0x1800394e4  test    rax, rax
0x1800394e7  jnz     short loc_1800394F6
0x1800394e9  mov     rdx, rsi; unsigned __int64
0x1800394ec  mov     rcx, rbx; this
0x1800394ef  call    ?allocate_space@memory_holder@details@client@http@web@@QEAAX_K@Z; web::http::client::details::memory_holder::allocate_space(unsigned __int64)
0x1800394f4  jmp     short loc_1800394F9
0x1800394f6  mov     [rbx], rax
0x1800394f9  mov     rdx, [rbx]
0x1800394fc  test    rdx, rdx
0x1800394ff  jnz     short loc_180039505
0x180039501  mov     rdx, [rbx+8]; lpBuffer
0x180039505  mov     r8d, esi; dwNumberOfBytesToRead
0x180039508  xor     r9d, r9d; lpdwNumberOfBytesRead
0x18003950b  mov     rcx, [rdi+60h]; hRequest
0x18003950f  call    cs:__imp_WinHttpReadData
0x180039515  test    eax, eax
0x180039517  jnz     short loc_180039564
0x180039519  call    cs:__imp_GetLastError
0x18003951f  mov     ebx, eax
0x180039521  lea     rdx, aWinhttpreaddat; "WinHttpReadData"
0x180039528  lea     rcx, [rbp+57h+var_70]
0x18003952c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180039531  nop
0x180039532  lea     r8, [rbp+57h+var_70]
0x180039536  mov     edx, ebx
0x180039538  lea     rcx, [rbp+57h+var_50]
0x18003953c  call    web__http__client__details__build_error_msg
0x180039541  nop
0x180039542  mov     r8, rax
0x180039545  mov     edx, ebx
0x180039547  mov     rcx, rdi
0x18003954a  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x18003954f  nop
0x180039550  lea     rcx, [rbp+57h+var_50]
0x180039554  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180039559  nop
0x18003955a  lea     rcx, [rbp+57h+var_70]
0x18003955e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180039563  nop
0x180039564  lea     rcx, [rbp+57h+var_90]
0x180039568  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x18003956d  mov     rcx, [rbp+57h+var_30]
0x180039571  xor     rcx, rsp; StackCookie
0x180039574  call    __security_check_cookie
0x180039579  add     rsp, 98h
0x180039580  pop     rdi
0x180039581  pop     rsi
0x180039582  pop     rbx
0x180039583  pop     rbp
0x180039584  retn
```
