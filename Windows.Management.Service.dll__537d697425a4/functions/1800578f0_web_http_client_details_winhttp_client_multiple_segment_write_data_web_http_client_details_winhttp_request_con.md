# web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)

- ea: `0x1800578f0`
- end: `0x180057d5f`
- name: `?_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@@Z`
- size: `1135`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180059480`

## callees

- `0x18000b8f0`
- `0x18000bd9c`
- `0x18000bddc`
- `0x18000c510`
- `0x18003dff0`
- `0x18003f210`
- `0x18003f380`
- `0x18003f430`
- `0x1800530d0`
- `0x180057590`
- `0x1800578f0`
- `0x180058f40`
- `0x180063886`
- `0x1800638ce`
- `0x180065aec`
- `0x180084574`
- `0x180139510`
- `0x1801543d4`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800579d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800579d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057ad4`
- `WINHTTP!WinHttpWriteData` at `0x180057ac6`
- `WINHTTP!WinHttpWriteData` at `0x180057ac6`

## string_xrefs

- `0x180057b01`: `WinHttpWriteData`
- `0x1800579c0`: `Error reading outgoing HTTP body from its stream.`

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
0x1800578f0  push    rbp
0x1800578f2  push    rbx
0x1800578f3  push    rsi
0x1800578f4  push    rdi
0x1800578f5  push    r14
0x1800578f7  push    r15
0x1800578f9  lea     rbp, [rsp-2Fh]
0x1800578fe  sub     rsp, 0C8h
0x180057905  mov     rax, cs:__security_cookie
0x18005790c  xor     rax, rsp
0x18005790f  mov     [rbp+57h+var_38], rax
0x180057913  mov     rdi, rcx
0x180057916  xor     r15d, r15d
0x180057919  lea     rdx, [rbp+57h+var_B0]
0x18005791d  call    ?_get_readbuffer@winhttp_request_context@details@client@http@web@@UEAA?AV?$streambuf@E@streams@Concurrency@@XZ; web::http::client::details::winhttp_request_context::_get_readbuffer(void)
0x180057922  nop
0x180057923  mov     rbx, [rdi+90h]
0x18005792a  mov     rcx, [rdi+8]; this
0x18005792e  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x180057933  mov     rcx, [rax+1A0h]
0x18005793a  mov     eax, 10000h
0x18005793f  test    rcx, rcx
0x180057942  cmovz   rcx, rax
0x180057946  cmp     rbx, rcx
0x180057949  cmova   rbx, rcx
0x18005794d  mov     [rbp+57h+var_B8], r15
0x180057951  mov     qword ptr [rbp+57h+dwNumberOfBytesToWrite], r15
0x180057955  mov     rsi, [rbp+57h+var_A8]
0x180057959  test    rsi, rsi
0x18005795c  jz      loc_180057D3E
0x180057962  mov     rax, [rsi]
0x180057965  lea     r8, [rbp+57h+dwNumberOfBytesToWrite]
0x180057969  lea     rdx, [rbp+57h+var_B8]
0x18005796d  mov     rcx, rsi
0x180057970  mov     rax, [rax+0F0h]
0x180057977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005797c  test    al, al
0x18005797e  jz      loc_180057BCE
0x180057984  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x180057988  test    rax, rax
0x18005798b  jnz     loc_180057A57
0x180057991  mov     rax, [rsi]
0x180057994  lea     rdx, [rbp+57h+Src]
0x180057998  mov     rcx, rsi
0x18005799b  mov     rax, [rax+100h]
0x1800579a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800579a7  lea     rcx, [rbp+57h+Src]; void *
0x1800579ab  call    ?__ExceptionPtrToBool@@YA_NPEBX@Z_0; __ExceptionPtrToBool(void const *)
0x1800579b0  movzx   ebx, al
0x1800579b3  lea     rcx, [rbp+57h+Src]; void *
0x1800579b7  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800579bc  test    bl, bl
0x1800579be  jnz     short loc_180057A30
0x1800579c0  lea     rdx, aErrorReadingOu; "Error reading outgoing HTTP body from i"...
0x1800579c7  lea     rcx, [rbp+57h+var_58]
0x1800579cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800579d0  nop
0x1800579d1  call    cs:__imp_GetLastError
0x1800579d7  mov     edx, eax
0x1800579d9  lea     r8, [rbp+57h+var_58]
0x1800579dd  mov     rcx, rdi
0x1800579e0  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::wstring const &)
0x1800579e5  nop
0x1800579e6  mov     rdx, [rbp+57h+var_40]
0x1800579ea  cmp     rdx, 7
0x1800579ee  jbe     loc_180057D19
0x1800579f4  mov     rax, [rbp+57h+var_58]
0x1800579f8  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x180057a00  cmp     rdx, 1000h
0x180057a07  jb      loc_180057BC1
0x180057a0d  mov     rcx, [rax-8]; void *
0x180057a11  sub     rax, rcx
0x180057a14  sub     rax, 8
0x180057a18  cmp     rax, 1Fh
0x180057a1c  ja      loc_180057BBA
0x180057a22  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180057a26  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057a2b  jmp     loc_180057D19
0x180057a30  mov     rax, [rsi]
0x180057a33  lea     rdx, [rbp+57h+Src]
0x180057a37  mov     rcx, rsi
0x180057a3a  mov     rax, [rax+100h]
0x180057a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a46  lea     rdx, [rbp+57h+Src]
0x180057a4a  mov     rcx, rdi
0x180057a4d  call    ?report_exception@request_context@details@client@http@web@@UEAAXVexception_ptr@std@@@Z; web::http::client::details::request_context::report_exception(std::exception_ptr)
0x180057a52  jmp     loc_180057D19
0x180057a57  mov     rdx, [rbp+57h+var_B8]
0x180057a5b  test    rdx, rdx
0x180057a5e  jnz     short loc_180057A8B
0x180057a60  mov     rcx, [rdi+0E8h]
0x180057a67  sub     rcx, [rdi+0E0h]
0x180057a6e  cmp     rax, rcx
0x180057a71  jbe     short loc_180057A86
0x180057a73  mov     rdx, rax
0x180057a76  lea     rcx, [rdi+0E0h]
0x180057a7d  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180057a82  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x180057a86  mov     rdx, r15
0x180057a89  jmp     short loc_180057A92
0x180057a8b  mov     [rdi+0F8h], rax
0x180057a92  mov     [rdi+0D8h], rdx
0x180057a99  cmp     rbx, rax
0x180057a9c  cmova   rbx, rax
0x180057aa0  sub     [rdi+90h], rbx
0x180057aa7  jnz     short loc_180057AB0
0x180057aa9  mov     [rdi+88h], r15d
0x180057ab0  test    rdx, rdx
0x180057ab3  jnz     short loc_180057ABC
0x180057ab5  mov     rdx, [rdi+0E0h]; lpBuffer
0x180057abc  mov     r8d, ebx; dwNumberOfBytesToWrite
0x180057abf  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x180057ac2  mov     rcx, [rdi+68h]; hRequest
0x180057ac6  call    cs:__imp_WinHttpWriteData
0x180057acc  test    eax, eax
0x180057ace  jnz     loc_180057D19
0x180057ad4  call    cs:__imp_GetLastError
0x180057ada  mov     ebx, eax
0x180057adc  xorps   xmm0, xmm0
0x180057adf  movups  [rbp+57h+pExceptionObject], xmm0
0x180057ae3  mov     ecx, 20h ; ' '; Size
0x180057ae8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180057aed  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x180057af1  mov     [rbp+57h+var_68], 10h
0x180057af9  mov     [rbp+57h+var_60], 1Fh
0x180057b01  movups  xmm0, xmmword ptr cs:aWinhttpwriteda_0; "WinHttpWriteData"
0x180057b08  movups  xmmword ptr [rax], xmm0
0x180057b0b  mov     byte ptr [rax+10h], 0
0x180057b0f  lea     r8, [rbp+57h+pExceptionObject]
0x180057b13  mov     edx, ebx
0x180057b15  lea     rcx, [rbp+57h+Src]; Src
0x180057b19  call    web__http__client__details__build_error_msg
0x180057b1e  nop
0x180057b1f  mov     r8, rax
0x180057b22  mov     edx, ebx
0x180057b24  mov     rcx, rdi
0x180057b27  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180057b2c  nop
0x180057b2d  mov     rdx, [rbp+57h+var_80]
0x180057b31  cmp     rdx, 0Fh
0x180057b35  jbe     short loc_180057B6D
0x180057b37  mov     rax, [rbp+57h+Src]
0x180057b3b  inc     rdx; struct std::nothrow_t *
0x180057b3e  cmp     rdx, 1000h
0x180057b45  jb      short loc_180057B65
0x180057b47  mov     rcx, [rax-8]
0x180057b4b  sub     rax, rcx
0x180057b4e  sub     rax, 8
0x180057b52  cmp     rax, 1Fh
0x180057b56  ja      short loc_180057B5E
0x180057b58  add     rdx, 27h ; '''
0x180057b5c  jmp     short loc_180057B68
0x180057b5e  mov     ecx, 5
0x180057b63  int     29h; Win8: RtlFailFast(ecx)
0x180057b65  mov     rcx, rax; void *
0x180057b68  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057b6d  mov     [rbp+57h+var_88], r15
0x180057b71  mov     [rbp+57h+var_80], 0Fh
0x180057b79  mov     byte ptr [rbp+57h+Src], 0
0x180057b7d  mov     rdx, [rbp+57h+var_60]
0x180057b81  cmp     rdx, 0Fh
0x180057b85  jbe     loc_180057D19
0x180057b8b  mov     rax, qword ptr [rbp+57h+pExceptionObject]
0x180057b8f  inc     rdx
0x180057b92  cmp     rdx, 1000h
0x180057b99  jb      short loc_180057BC1
0x180057b9b  mov     rcx, [rax-8]; void *
0x180057b9f  sub     rax, rcx
0x180057ba2  sub     rax, 8
0x180057ba6  cmp     rax, 1Fh
0x180057baa  ja      short loc_180057BBA
0x180057bac  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180057bb0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057bb5  jmp     loc_180057D19
0x180057bba  mov     ecx, 5
0x180057bbf  int     29h; Win8: RtlFailFast(ecx)
0x180057bc1  mov     rcx, rax; void *
0x180057bc4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057bc9  jmp     loc_180057D19
0x180057bce  mov     rax, [rdi+0E8h]
0x180057bd5  sub     rax, [rdi+0E0h]
0x180057bdc  cmp     rbx, rax
0x180057bdf  jbe     short loc_180057BF0
0x180057be1  mov     rdx, rbx
0x180057be4  lea     rcx, [rdi+0E0h]
0x180057beb  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180057bf0  mov     [rdi+0D8h], r15
0x180057bf7  mov     [rbp+57h+var_58], rdi
0x180057bfb  lea     rax, ??_7?$streambuf@E@streams@Concurrency@@6B@; const Concurrency::streams::streambuf<uchar>::`vftable'
0x180057c02  mov     [rbp+57h+var_50], rax
0x180057c06  mov     rax, [rbp+57h+var_A0]
0x180057c0a  test    rax, rax
0x180057c0d  jz      short loc_180057C13
0x180057c0f  lock inc dword ptr [rax+8]
0x180057c13  mov     [rbp+57h+var_48], rsi
0x180057c17  mov     [rbp+57h+var_40], rax
0x180057c1b  mov     r8, [rdi+0D8h]
0x180057c22  test    r8, r8
0x180057c25  jnz     short loc_180057C2E
0x180057c27  mov     r8, [rdi+0E0h]
0x180057c2e  mov     rax, [rsi]
0x180057c31  mov     r9, rbx
0x180057c34  lea     rdx, [rbp+57h+Src]
0x180057c38  mov     rcx, rsi
0x180057c3b  mov     rax, [rax+0A8h]
0x180057c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c47  nop
0x180057c48  lea     r8, [rbp+57h+var_58]
0x180057c4c  lea     rdx, [rbp+57h+pExceptionObject]
0x180057c50  lea     rcx, [rbp+57h+Src]
0x180057c54  call    ??$then@V_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@4567@@Z@@?$task@_K@pplx@@QEBA?AV?$task@X@1@$$QEAV_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@6789@@Z@@Z; pplx::task<unsigned __int64>::then<`web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_>(`web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_ &&)
0x180057c59  mov     rbx, qword ptr [rbp+57h+pExceptionObject+8]
0x180057c5d  mov     edi, 0FFFFFFFFh
0x180057c62  test    rbx, rbx
0x180057c65  jz      short loc_180057C9D
0x180057c67  mov     eax, edi
0x180057c69  lock xadd [rbx+8], eax
0x180057c6e  cmp     eax, 1
0x180057c71  jnz     short loc_180057C9D
0x180057c73  mov     rax, [rbx]
0x180057c76  mov     rcx, rbx
0x180057c79  mov     rax, [rax]
0x180057c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c81  mov     eax, edi
0x180057c83  lock xadd [rbx+0Ch], eax
0x180057c88  cmp     eax, 1
0x180057c8b  jnz     short loc_180057C9D
0x180057c8d  mov     rax, [rbx]
0x180057c90  mov     rcx, rbx
0x180057c93  mov     rax, [rax+8]
0x180057c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c9c  nop
0x180057c9d  mov     rbx, [rbp+57h+var_90]
0x180057ca1  test    rbx, rbx
0x180057ca4  jz      short loc_180057CDC
0x180057ca6  mov     eax, edi
0x180057ca8  lock xadd [rbx+8], eax
0x180057cad  cmp     eax, 1
0x180057cb0  jnz     short loc_180057CDC
0x180057cb2  mov     rax, [rbx]
0x180057cb5  mov     rcx, rbx
0x180057cb8  mov     rax, [rax]
0x180057cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057cc0  mov     eax, edi
0x180057cc2  lock xadd [rbx+0Ch], eax
0x180057cc7  cmp     eax, 1
0x180057cca  jnz     short loc_180057CDC
0x180057ccc  mov     rax, [rbx]
0x180057ccf  mov     rcx, rbx
0x180057cd2  mov     rax, [rax+8]
0x180057cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057cdb  nop
0x180057cdc  mov     rbx, [rbp+57h+var_40]
0x180057ce0  test    rbx, rbx
0x180057ce3  jz      short loc_180057D19
0x180057ce5  mov     eax, edi
0x180057ce7  lock xadd [rbx+8], eax
0x180057cec  cmp     eax, 1
0x180057cef  jnz     short loc_180057D19
0x180057cf1  mov     rax, [rbx]
0x180057cf4  mov     rcx, rbx
0x180057cf7  mov     rax, [rax]
0x180057cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057cff  lock xadd [rbx+0Ch], edi
0x180057d04  cmp     edi, 1
0x180057d07  jnz     short loc_180057D19
0x180057d09  mov     rax, [rbx]
0x180057d0c  mov     rcx, rbx
0x180057d0f  mov     rax, [rax+8]
0x180057d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057d18  nop
0x180057d19  lea     rcx, [rbp+57h+var_B0]
0x180057d1d  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x180057d22  mov     rcx, [rbp+57h+var_38]
0x180057d26  xor     rcx, rsp; StackCookie
0x180057d29  call    __security_check_cookie
0x180057d2e  add     rsp, 0C8h
0x180057d35  pop     r15
0x180057d37  pop     r14
0x180057d39  pop     rdi
0x180057d3a  pop     rsi
0x180057d3b  pop     rbx
0x180057d3c  pop     rbp
0x180057d3d  retn
0x180057d3e  lea     rdx, aInvalidStreamb; "Invalid streambuf object"
0x180057d45  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180057d49  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180057d4e  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180057d55  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180057d59  call    _CxxThrowException_0
```
