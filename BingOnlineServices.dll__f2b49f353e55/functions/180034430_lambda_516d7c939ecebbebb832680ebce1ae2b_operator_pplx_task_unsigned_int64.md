# _lambda_516d7c939ecebbebb832680ebce1ae2b_::operator()(pplx::task<unsigned __int64>)

- ea: `0x180034430`
- end: `0x180034590`
- name: `??R_lambda_516d7c939ecebbebb832680ebce1ae2b_@@QEBA@V?$task@_K@pplx@@@Z`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x1800358c0`

## callees

- `0x180002c2c`
- `0x180002ca8`
- `0x180004fa0`
- `0x180009698`
- `0x18000eca4`
- `0x1800148ac`
- `0x180024718`
- `0x18002560c`
- `0x18002dda0`
- `0x180032edc`
- `0x180034430`
- `0x180036bf0`
- `0x1800395a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034501`
- `WINHTTP!WinHttpWriteData` at `0x1800344f7`
- `WINHTTP!WinHttpWriteData` at `0x1800344f7`

## string_xrefs

- `0x18003450c`: `WinHttpWriteData`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall _lambda_516d7c939ecebbebb832680ebce1ae2b_::operator()(__int64 *a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rdx
  std::_Ref_count_base *v7; // rcx
  __int64 v8; // rcx
  const void *v9; // rdx
  DWORD LastError; // edi
  __int64 v11; // rbx
  __int64 v12; // r8
  __int64 v13; // rdi
  void (__fastcall *v14)(__int64, __int64); // rbx
  __int64 v15; // rax
  _QWORD v18[4]; // [rsp+28h] [rbp-B0h] BYREF
  _BYTE v19[40]; // [rsp+48h] [rbp-90h] BYREF
  _BYTE v20[80]; // [rsp+70h] [rbp-68h] BYREF

  try
  {
    v18[0] = a1;
    v4 = pplx::task<unsigned __int64>::get(a2);
  }
  catch ( ... )
  {
    v13 = *(_QWORD *)v18[0];
    v14 = *(void (__fastcall **)(__int64, __int64))(**(_QWORD **)v18[0] + 8LL);
    v15 = std::current_exception(v18);
    v14(v13, v15);
    v7 = *(std::_Ref_count_base **)(a2 + 8);
    goto LABEL_11;
  }
  v5 = *a1;
  if ( v4 )
  {
    *(_QWORD *)(v5 + 112) -= v4;
    if ( !*(_QWORD *)(*a1 + 112) )
      *(_DWORD *)(*a1 + 108) = 0;
    v8 = *a1;
    v9 = *(const void **)(*a1 + 168);
    if ( !v9 )
      v9 = *(const void **)(v8 + 176);
    if ( !WinHttpWriteData(*(HINTERNET *)(v8 + 96), v9, v4, 0) )
    {
      LastError = GetLastError();
      v11 = *a1;
      std::string::string(v18, "WinHttpWriteData");
      v12 = web::http::client::details::build_error_msg(v19, LastError, v18);
      web::http::client::details::request_context::report_error(v11, LastError, v12);
      std::string::_Tidy_deallocate(v19);
      std::string::_Tidy_deallocate(v18);
    }
  }
  else
  {
    std::wstring::wstring(v18, L"Unexpected end of request body stream encountered before Content-Length met.");
    v6 = web::http::http_exception::http_exception(v20, v18);
    web::http::client::details::request_context::report_exception<web::http::http_exception>(v5, v6);
    web::http::http_exception::~http_exception((web::http::http_exception *)v20);
    std::wstring::_Tidy_deallocate(v18);
  }
  v7 = *(std::_Ref_count_base **)(a2 + 8);
LABEL_11:
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
}

```

## disassembly

```asm
0x180034430  mov     [rsp+arg_10], rbx
0x180034435  mov     [rsp+arg_18], rsi
0x18003443a  push    rdi
0x18003443b  sub     rsp, 0D0h
0x180034442  mov     rax, cs:__security_cookie
0x180034449  xor     rax, rsp
0x18003444c  mov     [rsp+0D8h+var_18], rax
0x180034454  mov     rsi, rdx
0x180034457  mov     rbx, rcx
0x18003445a  mov     [rsp+0D8h+var_B0], rcx
0x18003445f  mov     [rsp+0D8h+var_B8], rdx
0x180034464  mov     rcx, rdx
0x180034467  call    ?get@?$task@_K@pplx@@QEBA_KXZ; pplx::task<unsigned __int64>::get(void)
0x18003446c  nop
0x18003446d  mov     rdi, [rbx]
0x180034470  test    rax, rax
0x180034473  jnz     short loc_1800344C2
0x180034475  lea     rdx, aUnexpectedEndO; "Unexpected end of request body stream e"...
0x18003447c  lea     rcx, [rsp+0D8h+var_B0]
0x180034481  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180034486  nop
0x180034487  lea     rdx, [rsp+0D8h+var_B0]
0x18003448c  lea     rcx, [rsp+0D8h+var_68]
0x180034491  call    ??0http_exception@http@web@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::http_exception::http_exception(std::wstring const &)
0x180034496  nop
0x180034497  mov     rdx, rax
0x18003449a  mov     rcx, rdi
0x18003449d  call    ??$report_exception@Vhttp_exception@http@web@@@request_context@details@client@http@web@@QEAAXAEBVhttp_exception@34@@Z; web::http::client::details::request_context::report_exception<web::http::http_exception>(web::http::http_exception const &)
0x1800344a2  nop
0x1800344a3  lea     rcx, [rsp+0D8h+var_68]; this
0x1800344a8  call    ??1http_exception@http@web@@UEAA@XZ; web::http::http_exception::~http_exception(void)
0x1800344ad  nop
0x1800344ae  lea     rcx, [rsp+0D8h+var_B0]
0x1800344b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800344b8  nop
0x1800344b9  mov     rcx, [rsi+8]
0x1800344bd  jmp     loc_180034561
0x1800344c2  sub     [rdi+70h], rax
0x1800344c6  mov     rcx, [rbx]
0x1800344c9  cmp     qword ptr [rcx+70h], 0
0x1800344ce  jnz     short loc_1800344D7
0x1800344d0  mov     dword ptr [rcx+6Ch], 0
0x1800344d7  mov     rcx, [rbx]
0x1800344da  mov     rdx, [rcx+0A8h]
0x1800344e1  test    rdx, rdx
0x1800344e4  jnz     short loc_1800344ED
0x1800344e6  mov     rdx, [rcx+0B0h]; lpBuffer
0x1800344ed  mov     r8d, eax; dwNumberOfBytesToWrite
0x1800344f0  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x1800344f3  mov     rcx, [rcx+60h]; hRequest
0x1800344f7  call    cs:__imp_WinHttpWriteData
0x1800344fd  test    eax, eax
0x1800344ff  jnz     short loc_1800344B9
0x180034501  call    cs:__imp_GetLastError
0x180034507  mov     edi, eax
0x180034509  mov     rbx, [rbx]
0x18003450c  lea     rdx, aWinhttpwriteda; "WinHttpWriteData"
0x180034513  lea     rcx, [rsp+0D8h+var_B0]
0x180034518  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003451d  nop
0x18003451e  lea     r8, [rsp+0D8h+var_B0]
0x180034523  mov     edx, edi
0x180034525  lea     rcx, [rsp+0D8h+var_90]
0x18003452a  call    web__http__client__details__build_error_msg
0x18003452f  nop
0x180034530  mov     r8, rax
0x180034533  mov     edx, edi
0x180034535  mov     rcx, rbx
0x180034538  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x18003453d  nop
0x18003453e  lea     rcx, [rsp+0D8h+var_90]
0x180034543  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180034548  nop
0x180034549  lea     rcx, [rsp+0D8h+var_B0]
0x18003454e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180034553  jmp     loc_1800344B9
0x180034558  mov     rax, [rsp+0D8h+var_B8]
0x18003455d  mov     rcx, [rax+8]; this
0x180034561  test    rcx, rcx
0x180034564  jz      short loc_18003456B
0x180034566  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003456b  mov     rcx, [rsp+0D8h+var_18]
0x180034573  xor     rcx, rsp; StackCookie
0x180034576  call    __security_check_cookie
0x18003457b  lea     r11, [rsp+0D8h+var_8]
0x180034583  mov     rbx, [r11+20h]
0x180034587  mov     rsi, [r11+28h]
0x18003458b  mov     rsp, r11
0x18003458e  pop     rdi
0x18003458f  retn
```
