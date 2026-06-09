# web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)

- ea: `0x180057710`
- end: `0x180057b7f`
- name: `?_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@@Z`
- size: `1135`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800592a0`

## callees

- `0x18000b820`
- `0x18000bccc`
- `0x18000bd0c`
- `0x18000c420`
- `0x18003de40`
- `0x18003f060`
- `0x18003f1d0`
- `0x18003f280`
- `0x180052f20`
- `0x1800573b0`
- `0x180057710`
- `0x180058d60`
- `0x1800636a6`
- `0x1800636ee`
- `0x1800658b0`
- `0x1800839bc`
- `0x18013560c`
- `0x180150384`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800577f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800578f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800577f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800578f4`
- `WINHTTP!WinHttpWriteData` at `0x1800578e6`
- `WINHTTP!WinHttpWriteData` at `0x1800578e6`

## string_xrefs

- `0x180057921`: `WinHttpWriteData`
- `0x1800577e0`: `Error reading outgoing HTTP body from its stream.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall web::http::client::details::winhttp_client::_multiple_segment_write_data(
        struct web::http::client::details::winhttp_request_context *a1)
{
  unsigned __int64 v2; // rbx
  unsigned __int64 v3; // rcx
  void *v4; // rsi
  unsigned __int64 v5; // rax
  bool v6; // bl
  DWORD v7; // eax
  void *v8; // rax
  unsigned __int64 v9; // rdx
  void *v10; // rcx
  const void *v11; // rdx
  bool v12; // zf
  DWORD LastError; // ebx
  __int64 v14; // rax
  const struct std::nothrow_t *v15; // rdx
  _BYTE *v16; // rcx
  unsigned __int64 v17; // rax
  __int64 v18; // r8
  volatile signed __int32 *v19; // rbx
  volatile signed __int32 *v20; // rbx
  volatile signed __int32 *v21; // rbx
  DWORD dwNumberOfBytesToWrite[2]; // [rsp+30h] [rbp-69h] BYREF
  const void *v23; // [rsp+38h] [rbp-61h] BYREF
  char v24[8]; // [rsp+40h] [rbp-59h] BYREF
  void *v25; // [rsp+48h] [rbp-51h]
  unsigned __int64 v26; // [rsp+50h] [rbp-49h]
  void *Src; // [rsp+58h] [rbp-41h] BYREF
  volatile signed __int32 *v28; // [rsp+60h] [rbp-39h]
  __int64 v29; // [rsp+68h] [rbp-31h]
  unsigned __int64 v30; // [rsp+70h] [rbp-29h]
  __int128 pExceptionObject; // [rsp+78h] [rbp-21h] BYREF
  __int64 v32; // [rsp+88h] [rbp-11h]
  unsigned __int64 v33; // [rsp+90h] [rbp-9h]
  void *v34[3]; // [rsp+98h] [rbp-1h] BYREF
  unsigned __int64 v35; // [rsp+B0h] [rbp+17h]

  web::http::client::details::winhttp_request_context::_get_readbuffer(a1, v24);
  v2 = *((_QWORD *)a1 + 18);
  v3 = *((_QWORD *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)a1
                                                                                        + 1))
       + 52);
  if ( !v3 )
    v3 = 0x10000;
  if ( v2 > v3 )
    v2 = v3;
  v23 = 0;
  *(_QWORD *)dwNumberOfBytesToWrite = 0;
  v4 = v25;
  if ( !v25 )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)&pExceptionObject, "Invalid streambuf object");
    throw (std::invalid_argument *)&pExceptionObject;
  }
  if ( (*(unsigned __int8 (__fastcall **)(void *, const void **, DWORD *))(*(_QWORD *)v25 + 240LL))(
         v25,
         &v23,
         dwNumberOfBytesToWrite) )
  {
    v5 = *(_QWORD *)dwNumberOfBytesToWrite;
    if ( *(_QWORD *)dwNumberOfBytesToWrite )
    {
      v11 = v23;
      if ( v23 )
      {
        *((_QWORD *)a1 + 31) = *(_QWORD *)dwNumberOfBytesToWrite;
      }
      else
      {
        if ( *(_QWORD *)dwNumberOfBytesToWrite > *((_QWORD *)a1 + 29) - *((_QWORD *)a1 + 28) )
        {
          std::vector<unsigned char>::resize((char *)a1 + 224, *(_QWORD *)dwNumberOfBytesToWrite);
          v5 = *(_QWORD *)dwNumberOfBytesToWrite;
        }
        v11 = 0;
      }
      *((_QWORD *)a1 + 27) = v11;
      if ( v2 > v5 )
        v2 = v5;
      v12 = *((_QWORD *)a1 + 18) == v2;
      *((_QWORD *)a1 + 18) -= v2;
      if ( v12 )
        *((_DWORD *)a1 + 34) = 0;
      if ( !v11 )
        v11 = (const void *)*((_QWORD *)a1 + 28);
      if ( !WinHttpWriteData(*((HINTERNET *)a1 + 13), v11, v2, 0) )
      {
        LastError = GetLastError();
        pExceptionObject = 0;
        *(_QWORD *)&pExceptionObject = operator new(0x20u);
        v32 = 16;
        v33 = 31;
        strcpy((char *)pExceptionObject, "WinHttpWriteData");
        v14 = web::http::client::details::build_error_msg(&Src);
        web::http::client::details::request_context::report_error(a1, LastError, v14);
        if ( v30 > 0xF )
        {
          v15 = (const struct std::nothrow_t *)(v30 + 1);
          if ( v30 + 1 < 0x1000 )
          {
            v16 = Src;
          }
          else
          {
            v16 = (_BYTE *)*((_QWORD *)Src - 1);
            if ( (unsigned __int64)((_BYTE *)Src - v16 - 8) > 0x1F )
              __fastfail(5u);
            v15 = (const struct std::nothrow_t *)(v30 + 40);
          }
          operator delete(v16, v15);
        }
        v29 = 0;
        v30 = 15;
        LOBYTE(Src) = 0;
        if ( v33 > 0xF )
        {
          v8 = (void *)pExceptionObject;
          v9 = v33 + 1;
          if ( v33 + 1 >= 0x1000 )
          {
            v10 = *(void **)(pExceptionObject - 8);
            if ( (unsigned __int64)(pExceptionObject - (_QWORD)v10 - 8) <= 0x1F )
              goto LABEL_12;
            goto LABEL_36;
          }
LABEL_37:
          operator delete(v8, (const struct std::nothrow_t *)v9);
        }
      }
    }
    else
    {
      (*(void (__fastcall **)(void *, void **))(*(_QWORD *)v4 + 256LL))(v4, &Src);
      v6 = __ExceptionPtrToBool(&Src);
      __ExceptionPtrDestroy(&Src);
      if ( v6 )
      {
        (*(void (__fastcall **)(void *, void **))(*(_QWORD *)v4 + 256LL))(v4, &Src);
        web::http::client::details::request_context::report_exception(a1, &Src);
        goto LABEL_56;
      }
      std::wstring::wstring(v34, L"Error reading outgoing HTTP body from its stream.");
      v7 = GetLastError();
      web::http::client::details::request_context::report_error(a1, v7, v34);
      if ( v35 > 7 )
      {
        v8 = v34[0];
        v9 = 2 * v35 + 2;
        if ( v9 >= 0x1000 )
        {
          v10 = (void *)*((_QWORD *)v34[0] - 1);
          if ( (unsigned __int64)((char *)v34[0] - (char *)v10 - 8) <= 0x1F )
          {
LABEL_12:
            operator delete(v10, (const struct std::nothrow_t *)(v9 + 39));
            goto LABEL_56;
          }
LABEL_36:
          __fastfail(5u);
        }
        goto LABEL_37;
      }
    }
  }
  else
  {
    if ( v2 > *((_QWORD *)a1 + 29) - *((_QWORD *)a1 + 28) )
      std::vector<unsigned char>::resize((char *)a1 + 224, v2);
    *((_QWORD *)a1 + 27) = 0;
    v34[0] = a1;
    v34[1] = &Concurrency::streams::streambuf<unsigned char>::`vftable';
    v17 = v26;
    if ( v26 )
      _InterlockedIncrement((volatile signed __int32 *)(v26 + 8));
    v34[2] = v4;
    v35 = v17;
    v18 = *((_QWORD *)a1 + 27);
    if ( !v18 )
      v18 = *((_QWORD *)a1 + 28);
    (*(void (__fastcall **)(void *, void **, __int64, unsigned __int64))(*(_QWORD *)v4 + 168LL))(v4, &Src, v18, v2);
    ___then_V_lambda_1___BF____multiple_segment_write_data_winhttp_client_details_client_http_web__CAXPEAVwinhttp_request_context_4567__Z____task__K_pplx__QEBA_AV__task_X_1___QEAV_lambda_1___BF____multiple_segment_write_data_winhttp_client_details_client_http_web__CAXPEAVwinhttp_request_context_6789__Z__Z(
      &Src,
      &pExceptionObject,
      v34);
    v19 = (volatile signed __int32 *)*((_QWORD *)&pExceptionObject + 1);
    if ( *((_QWORD *)&pExceptionObject + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&pExceptionObject + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    v20 = v28;
    if ( v28 )
    {
      if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    v21 = (volatile signed __int32 *)v35;
    if ( v35 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v35 + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
  }
LABEL_56:
  Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v24);
}

```

## disassembly

```asm
0x180057710  push    rbp
0x180057712  push    rbx
0x180057713  push    rsi
0x180057714  push    rdi
0x180057715  push    r14
0x180057717  push    r15
0x180057719  lea     rbp, [rsp-2Fh]
0x18005771e  sub     rsp, 0C8h
0x180057725  mov     rax, cs:__security_cookie
0x18005772c  xor     rax, rsp
0x18005772f  mov     [rbp+57h+var_38], rax
0x180057733  mov     rdi, rcx
0x180057736  xor     r15d, r15d
0x180057739  lea     rdx, [rbp+57h+var_B0]
0x18005773d  call    ?_get_readbuffer@winhttp_request_context@details@client@http@web@@UEAA?AV?$streambuf@E@streams@Concurrency@@XZ; web::http::client::details::winhttp_request_context::_get_readbuffer(void)
0x180057742  nop
0x180057743  mov     rbx, [rdi+90h]
0x18005774a  mov     rcx, [rdi+8]; this
0x18005774e  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x180057753  mov     rcx, [rax+1A0h]
0x18005775a  mov     eax, 10000h
0x18005775f  test    rcx, rcx
0x180057762  cmovz   rcx, rax
0x180057766  cmp     rbx, rcx
0x180057769  cmova   rbx, rcx
0x18005776d  mov     [rbp+57h+var_B8], r15
0x180057771  mov     qword ptr [rbp+57h+dwNumberOfBytesToWrite], r15
0x180057775  mov     rsi, [rbp+57h+var_A8]
0x180057779  test    rsi, rsi
0x18005777c  jz      loc_180057B5E
0x180057782  mov     rax, [rsi]
0x180057785  lea     r8, [rbp+57h+dwNumberOfBytesToWrite]
0x180057789  lea     rdx, [rbp+57h+var_B8]
0x18005778d  mov     rcx, rsi
0x180057790  mov     rax, [rax+0F0h]
0x180057797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005779c  test    al, al
0x18005779e  jz      loc_1800579EE
0x1800577a4  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x1800577a8  test    rax, rax
0x1800577ab  jnz     loc_180057877
0x1800577b1  mov     rax, [rsi]
0x1800577b4  lea     rdx, [rbp+57h+Src]
0x1800577b8  mov     rcx, rsi
0x1800577bb  mov     rax, [rax+100h]
0x1800577c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800577c7  lea     rcx, [rbp+57h+Src]; void *
0x1800577cb  call    ?__ExceptionPtrToBool@@YA_NPEBX@Z_0; __ExceptionPtrToBool(void const *)
0x1800577d0  movzx   ebx, al
0x1800577d3  lea     rcx, [rbp+57h+Src]; void *
0x1800577d7  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800577dc  test    bl, bl
0x1800577de  jnz     short loc_180057850
0x1800577e0  lea     rdx, aErrorReadingOu; "Error reading outgoing HTTP body from i"...
0x1800577e7  lea     rcx, [rbp+57h+var_58]
0x1800577eb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800577f0  nop
0x1800577f1  call    cs:__imp_GetLastError
0x1800577f7  mov     edx, eax
0x1800577f9  lea     r8, [rbp+57h+var_58]
0x1800577fd  mov     rcx, rdi
0x180057800  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::wstring const &)
0x180057805  nop
0x180057806  mov     rdx, [rbp+57h+var_40]
0x18005780a  cmp     rdx, 7
0x18005780e  jbe     loc_180057B39
0x180057814  mov     rax, [rbp+57h+var_58]
0x180057818  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x180057820  cmp     rdx, 1000h
0x180057827  jb      loc_1800579E1
0x18005782d  mov     rcx, [rax-8]; void *
0x180057831  sub     rax, rcx
0x180057834  sub     rax, 8
0x180057838  cmp     rax, 1Fh
0x18005783c  ja      loc_1800579DA
0x180057842  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180057846  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005784b  jmp     loc_180057B39
0x180057850  mov     rax, [rsi]
0x180057853  lea     rdx, [rbp+57h+Src]
0x180057857  mov     rcx, rsi
0x18005785a  mov     rax, [rax+100h]
0x180057861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057866  lea     rdx, [rbp+57h+Src]
0x18005786a  mov     rcx, rdi
0x18005786d  call    ?report_exception@request_context@details@client@http@web@@UEAAXVexception_ptr@std@@@Z; web::http::client::details::request_context::report_exception(std::exception_ptr)
0x180057872  jmp     loc_180057B39
0x180057877  mov     rdx, [rbp+57h+var_B8]
0x18005787b  test    rdx, rdx
0x18005787e  jnz     short loc_1800578AB
0x180057880  mov     rcx, [rdi+0E8h]
0x180057887  sub     rcx, [rdi+0E0h]
0x18005788e  cmp     rax, rcx
0x180057891  jbe     short loc_1800578A6
0x180057893  mov     rdx, rax
0x180057896  lea     rcx, [rdi+0E0h]
0x18005789d  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800578a2  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x1800578a6  mov     rdx, r15
0x1800578a9  jmp     short loc_1800578B2
0x1800578ab  mov     [rdi+0F8h], rax
0x1800578b2  mov     [rdi+0D8h], rdx
0x1800578b9  cmp     rbx, rax
0x1800578bc  cmova   rbx, rax
0x1800578c0  sub     [rdi+90h], rbx
0x1800578c7  jnz     short loc_1800578D0
0x1800578c9  mov     [rdi+88h], r15d
0x1800578d0  test    rdx, rdx
0x1800578d3  jnz     short loc_1800578DC
0x1800578d5  mov     rdx, [rdi+0E0h]; lpBuffer
0x1800578dc  mov     r8d, ebx; dwNumberOfBytesToWrite
0x1800578df  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x1800578e2  mov     rcx, [rdi+68h]; hRequest
0x1800578e6  call    cs:__imp_WinHttpWriteData
0x1800578ec  test    eax, eax
0x1800578ee  jnz     loc_180057B39
0x1800578f4  call    cs:__imp_GetLastError
0x1800578fa  mov     ebx, eax
0x1800578fc  xorps   xmm0, xmm0
0x1800578ff  movups  [rbp+57h+pExceptionObject], xmm0
0x180057903  mov     ecx, 20h ; ' '; Size
0x180057908  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005790d  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x180057911  mov     [rbp+57h+var_68], 10h
0x180057919  mov     [rbp+57h+var_60], 1Fh
0x180057921  movups  xmm0, xmmword ptr cs:aWinhttpwriteda_0; "WinHttpWriteData"
0x180057928  movups  xmmword ptr [rax], xmm0
0x18005792b  mov     byte ptr [rax+10h], 0
0x18005792f  lea     r8, [rbp+57h+pExceptionObject]
0x180057933  mov     edx, ebx
0x180057935  lea     rcx, [rbp+57h+Src]; Src
0x180057939  call    web__http__client__details__build_error_msg
0x18005793e  nop
0x18005793f  mov     r8, rax
0x180057942  mov     edx, ebx
0x180057944  mov     rcx, rdi
0x180057947  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x18005794c  nop
0x18005794d  mov     rdx, [rbp+57h+var_80]
0x180057951  cmp     rdx, 0Fh
0x180057955  jbe     short loc_18005798D
0x180057957  mov     rax, [rbp+57h+Src]
0x18005795b  inc     rdx; struct std::nothrow_t *
0x18005795e  cmp     rdx, 1000h
0x180057965  jb      short loc_180057985
0x180057967  mov     rcx, [rax-8]
0x18005796b  sub     rax, rcx
0x18005796e  sub     rax, 8
0x180057972  cmp     rax, 1Fh
0x180057976  ja      short loc_18005797E
0x180057978  add     rdx, 27h ; '''
0x18005797c  jmp     short loc_180057988
0x18005797e  mov     ecx, 5
0x180057983  int     29h; Win8: RtlFailFast(ecx)
0x180057985  mov     rcx, rax; void *
0x180057988  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005798d  mov     [rbp+57h+var_88], r15
0x180057991  mov     [rbp+57h+var_80], 0Fh
0x180057999  mov     byte ptr [rbp+57h+Src], 0
0x18005799d  mov     rdx, [rbp+57h+var_60]
0x1800579a1  cmp     rdx, 0Fh
0x1800579a5  jbe     loc_180057B39
0x1800579ab  mov     rax, qword ptr [rbp+57h+pExceptionObject]
0x1800579af  inc     rdx
0x1800579b2  cmp     rdx, 1000h
0x1800579b9  jb      short loc_1800579E1
0x1800579bb  mov     rcx, [rax-8]; void *
0x1800579bf  sub     rax, rcx
0x1800579c2  sub     rax, 8
0x1800579c6  cmp     rax, 1Fh
0x1800579ca  ja      short loc_1800579DA
0x1800579cc  add     rdx, 27h ; '''; struct std::nothrow_t *
0x1800579d0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800579d5  jmp     loc_180057B39
0x1800579da  mov     ecx, 5
0x1800579df  int     29h; Win8: RtlFailFast(ecx)
0x1800579e1  mov     rcx, rax; void *
0x1800579e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800579e9  jmp     loc_180057B39
0x1800579ee  mov     rax, [rdi+0E8h]
0x1800579f5  sub     rax, [rdi+0E0h]
0x1800579fc  cmp     rbx, rax
0x1800579ff  jbe     short loc_180057A10
0x180057a01  mov     rdx, rbx
0x180057a04  lea     rcx, [rdi+0E0h]
0x180057a0b  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180057a10  mov     [rdi+0D8h], r15
0x180057a17  mov     [rbp+57h+var_58], rdi
0x180057a1b  lea     rax, ??_7?$streambuf@E@streams@Concurrency@@6B@; const Concurrency::streams::streambuf<uchar>::`vftable'
0x180057a22  mov     [rbp+57h+var_50], rax
0x180057a26  mov     rax, [rbp+57h+var_A0]
0x180057a2a  test    rax, rax
0x180057a2d  jz      short loc_180057A33
0x180057a2f  lock inc dword ptr [rax+8]
0x180057a33  mov     [rbp+57h+var_48], rsi
0x180057a37  mov     [rbp+57h+var_40], rax
0x180057a3b  mov     r8, [rdi+0D8h]
0x180057a42  test    r8, r8
0x180057a45  jnz     short loc_180057A4E
0x180057a47  mov     r8, [rdi+0E0h]
0x180057a4e  mov     rax, [rsi]
0x180057a51  mov     r9, rbx
0x180057a54  lea     rdx, [rbp+57h+Src]
0x180057a58  mov     rcx, rsi
0x180057a5b  mov     rax, [rax+0A8h]
0x180057a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a67  nop
0x180057a68  lea     r8, [rbp+57h+var_58]
0x180057a6c  lea     rdx, [rbp+57h+pExceptionObject]
0x180057a70  lea     rcx, [rbp+57h+Src]
0x180057a74  call    ??$then@V_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@4567@@Z@@?$task@_K@pplx@@QEBA?AV?$task@X@1@$$QEAV_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@6789@@Z@@Z; pplx::task<unsigned __int64>::then<`web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_>(`web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_ &&)
0x180057a79  mov     rbx, qword ptr [rbp+57h+pExceptionObject+8]
0x180057a7d  mov     edi, 0FFFFFFFFh
0x180057a82  test    rbx, rbx
0x180057a85  jz      short loc_180057ABD
0x180057a87  mov     eax, edi
0x180057a89  lock xadd [rbx+8], eax
0x180057a8e  cmp     eax, 1
0x180057a91  jnz     short loc_180057ABD
0x180057a93  mov     rax, [rbx]
0x180057a96  mov     rcx, rbx
0x180057a99  mov     rax, [rax]
0x180057a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057aa1  mov     eax, edi
0x180057aa3  lock xadd [rbx+0Ch], eax
0x180057aa8  cmp     eax, 1
0x180057aab  jnz     short loc_180057ABD
0x180057aad  mov     rax, [rbx]
0x180057ab0  mov     rcx, rbx
0x180057ab3  mov     rax, [rax+8]
0x180057ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057abc  nop
0x180057abd  mov     rbx, [rbp+57h+var_90]
0x180057ac1  test    rbx, rbx
0x180057ac4  jz      short loc_180057AFC
0x180057ac6  mov     eax, edi
0x180057ac8  lock xadd [rbx+8], eax
0x180057acd  cmp     eax, 1
0x180057ad0  jnz     short loc_180057AFC
0x180057ad2  mov     rax, [rbx]
0x180057ad5  mov     rcx, rbx
0x180057ad8  mov     rax, [rax]
0x180057adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057ae0  mov     eax, edi
0x180057ae2  lock xadd [rbx+0Ch], eax
0x180057ae7  cmp     eax, 1
0x180057aea  jnz     short loc_180057AFC
0x180057aec  mov     rax, [rbx]
0x180057aef  mov     rcx, rbx
0x180057af2  mov     rax, [rax+8]
0x180057af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057afb  nop
0x180057afc  mov     rbx, [rbp+57h+var_40]
0x180057b00  test    rbx, rbx
0x180057b03  jz      short loc_180057B39
0x180057b05  mov     eax, edi
0x180057b07  lock xadd [rbx+8], eax
0x180057b0c  cmp     eax, 1
0x180057b0f  jnz     short loc_180057B39
0x180057b11  mov     rax, [rbx]
0x180057b14  mov     rcx, rbx
0x180057b17  mov     rax, [rax]
0x180057b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b1f  lock xadd [rbx+0Ch], edi
0x180057b24  cmp     edi, 1
0x180057b27  jnz     short loc_180057B39
0x180057b29  mov     rax, [rbx]
0x180057b2c  mov     rcx, rbx
0x180057b2f  mov     rax, [rax+8]
0x180057b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b38  nop
0x180057b39  lea     rcx, [rbp+57h+var_B0]
0x180057b3d  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x180057b42  mov     rcx, [rbp+57h+var_38]
0x180057b46  xor     rcx, rsp; StackCookie
0x180057b49  call    __security_check_cookie
0x180057b4e  add     rsp, 0C8h
0x180057b55  pop     r15
0x180057b57  pop     r14
0x180057b59  pop     rdi
0x180057b5a  pop     rsi
0x180057b5b  pop     rbx
0x180057b5c  pop     rbp
0x180057b5d  retn
0x180057b5e  lea     rdx, aInvalidStreamb; "Invalid streambuf object"
0x180057b65  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180057b69  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180057b6e  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180057b75  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180057b79  call    _CxxThrowException_0
```
