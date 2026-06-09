# web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)

- ea: `0x180047760`
- end: `0x180047bcf`
- name: `?_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@@Z`
- size: `1135`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800492f0`

## callees

- `0x180007270`
- `0x180007640`
- `0x18002a210`
- `0x18002b430`
- `0x18002b5a0`
- `0x18002b650`
- `0x180042f40`
- `0x180047400`
- `0x180047760`
- `0x180048db0`
- `0x180050d83`
- `0x180050d8f`
- `0x180051d48`
- `0x1800522a2`
- `0x18005b73c`
- `0x1800839f8`
- `0x1800849dc`
- `0x180094184`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047944`
- `WINHTTP!WinHttpWriteData` at `0x180047936`
- `WINHTTP!WinHttpWriteData` at `0x180047936`

## string_xrefs

- `0x180047971`: `WinHttpWriteData`
- `0x180047830`: `Error reading outgoing HTTP body from its stream.`

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
0x180047760  push    rbp
0x180047762  push    rbx
0x180047763  push    rsi
0x180047764  push    rdi
0x180047765  push    r14
0x180047767  push    r15
0x180047769  lea     rbp, [rsp-2Fh]
0x18004776e  sub     rsp, 0C8h
0x180047775  mov     rax, cs:__security_cookie
0x18004777c  xor     rax, rsp
0x18004777f  mov     [rbp+57h+var_38], rax
0x180047783  mov     rdi, rcx
0x180047786  xor     r15d, r15d
0x180047789  lea     rdx, [rbp+57h+var_B0]
0x18004778d  call    ?_get_readbuffer@winhttp_request_context@details@client@http@web@@UEAA?AV?$streambuf@E@streams@Concurrency@@XZ; web::http::client::details::winhttp_request_context::_get_readbuffer(void)
0x180047792  nop
0x180047793  mov     rbx, [rdi+90h]
0x18004779a  mov     rcx, [rdi+8]; this
0x18004779e  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x1800477a3  mov     rcx, [rax+1A0h]
0x1800477aa  mov     eax, 10000h
0x1800477af  test    rcx, rcx
0x1800477b2  cmovz   rcx, rax
0x1800477b6  cmp     rbx, rcx
0x1800477b9  cmova   rbx, rcx
0x1800477bd  mov     [rbp+57h+var_B8], r15
0x1800477c1  mov     qword ptr [rbp+57h+dwNumberOfBytesToWrite], r15
0x1800477c5  mov     rsi, [rbp+57h+var_A8]
0x1800477c9  test    rsi, rsi
0x1800477cc  jz      loc_180047BAE
0x1800477d2  mov     rax, [rsi]
0x1800477d5  lea     r8, [rbp+57h+dwNumberOfBytesToWrite]
0x1800477d9  lea     rdx, [rbp+57h+var_B8]
0x1800477dd  mov     rcx, rsi
0x1800477e0  mov     rax, [rax+0F0h]
0x1800477e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477ec  test    al, al
0x1800477ee  jz      loc_180047A3E
0x1800477f4  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x1800477f8  test    rax, rax
0x1800477fb  jnz     loc_1800478C7
0x180047801  mov     rax, [rsi]
0x180047804  lea     rdx, [rbp+57h+Src]
0x180047808  mov     rcx, rsi
0x18004780b  mov     rax, [rax+100h]
0x180047812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047817  lea     rcx, [rbp+57h+Src]; void *
0x18004781b  call    ?__ExceptionPtrToBool@@YA_NPEBX@Z_0; __ExceptionPtrToBool(void const *)
0x180047820  movzx   ebx, al
0x180047823  lea     rcx, [rbp+57h+Src]; void *
0x180047827  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x18004782c  test    bl, bl
0x18004782e  jnz     short loc_1800478A0
0x180047830  lea     rdx, aErrorReadingOu; "Error reading outgoing HTTP body from i"...
0x180047837  lea     rcx, [rbp+57h+var_58]
0x18004783b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180047840  nop
0x180047841  call    cs:__imp_GetLastError
0x180047847  mov     edx, eax
0x180047849  lea     r8, [rbp+57h+var_58]
0x18004784d  mov     rcx, rdi
0x180047850  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::wstring const &)
0x180047855  nop
0x180047856  mov     rdx, [rbp+57h+var_40]
0x18004785a  cmp     rdx, 7
0x18004785e  jbe     loc_180047B89
0x180047864  mov     rax, [rbp+57h+var_58]
0x180047868  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x180047870  cmp     rdx, 1000h
0x180047877  jb      loc_180047A31
0x18004787d  mov     rcx, [rax-8]; void *
0x180047881  sub     rax, rcx
0x180047884  sub     rax, 8
0x180047888  cmp     rax, 1Fh
0x18004788c  ja      loc_180047A2A
0x180047892  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180047896  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004789b  jmp     loc_180047B89
0x1800478a0  mov     rax, [rsi]
0x1800478a3  lea     rdx, [rbp+57h+Src]
0x1800478a7  mov     rcx, rsi
0x1800478aa  mov     rax, [rax+100h]
0x1800478b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478b6  lea     rdx, [rbp+57h+Src]
0x1800478ba  mov     rcx, rdi
0x1800478bd  call    ?report_exception@request_context@details@client@http@web@@UEAAXVexception_ptr@std@@@Z; web::http::client::details::request_context::report_exception(std::exception_ptr)
0x1800478c2  jmp     loc_180047B89
0x1800478c7  mov     rdx, [rbp+57h+var_B8]
0x1800478cb  test    rdx, rdx
0x1800478ce  jnz     short loc_1800478FB
0x1800478d0  mov     rcx, [rdi+0E8h]
0x1800478d7  sub     rcx, [rdi+0E0h]
0x1800478de  cmp     rax, rcx
0x1800478e1  jbe     short loc_1800478F6
0x1800478e3  mov     rdx, rax
0x1800478e6  lea     rcx, [rdi+0E0h]
0x1800478ed  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800478f2  mov     rax, qword ptr [rbp+57h+dwNumberOfBytesToWrite]
0x1800478f6  mov     rdx, r15
0x1800478f9  jmp     short loc_180047902
0x1800478fb  mov     [rdi+0F8h], rax
0x180047902  mov     [rdi+0D8h], rdx
0x180047909  cmp     rbx, rax
0x18004790c  cmova   rbx, rax
0x180047910  sub     [rdi+90h], rbx
0x180047917  jnz     short loc_180047920
0x180047919  mov     [rdi+88h], r15d
0x180047920  test    rdx, rdx
0x180047923  jnz     short loc_18004792C
0x180047925  mov     rdx, [rdi+0E0h]; lpBuffer
0x18004792c  mov     r8d, ebx; dwNumberOfBytesToWrite
0x18004792f  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x180047932  mov     rcx, [rdi+68h]; hRequest
0x180047936  call    cs:__imp_WinHttpWriteData
0x18004793c  test    eax, eax
0x18004793e  jnz     loc_180047B89
0x180047944  call    cs:__imp_GetLastError
0x18004794a  mov     ebx, eax
0x18004794c  xorps   xmm0, xmm0
0x18004794f  movups  [rbp+57h+pExceptionObject], xmm0
0x180047953  mov     ecx, 20h ; ' '; Size
0x180047958  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004795d  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x180047961  mov     [rbp+57h+var_68], 10h
0x180047969  mov     [rbp+57h+var_60], 1Fh
0x180047971  movups  xmm0, xmmword ptr cs:aWinhttpwriteda_0; "WinHttpWriteData"
0x180047978  movups  xmmword ptr [rax], xmm0
0x18004797b  mov     byte ptr [rax+10h], 0
0x18004797f  lea     r8, [rbp+57h+pExceptionObject]
0x180047983  mov     edx, ebx
0x180047985  lea     rcx, [rbp+57h+Src]; Src
0x180047989  call    web__http__client__details__build_error_msg
0x18004798e  nop
0x18004798f  mov     r8, rax
0x180047992  mov     edx, ebx
0x180047994  mov     rcx, rdi
0x180047997  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x18004799c  nop
0x18004799d  mov     rdx, [rbp+57h+var_80]
0x1800479a1  cmp     rdx, 0Fh
0x1800479a5  jbe     short loc_1800479DD
0x1800479a7  mov     rax, [rbp+57h+Src]
0x1800479ab  inc     rdx; struct std::nothrow_t *
0x1800479ae  cmp     rdx, 1000h
0x1800479b5  jb      short loc_1800479D5
0x1800479b7  mov     rcx, [rax-8]
0x1800479bb  sub     rax, rcx
0x1800479be  sub     rax, 8
0x1800479c2  cmp     rax, 1Fh
0x1800479c6  ja      short loc_1800479CE
0x1800479c8  add     rdx, 27h ; '''
0x1800479cc  jmp     short loc_1800479D8
0x1800479ce  mov     ecx, 5
0x1800479d3  int     29h; Win8: RtlFailFast(ecx)
0x1800479d5  mov     rcx, rax; void *
0x1800479d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800479dd  mov     [rbp+57h+var_88], r15
0x1800479e1  mov     [rbp+57h+var_80], 0Fh
0x1800479e9  mov     byte ptr [rbp+57h+Src], 0
0x1800479ed  mov     rdx, [rbp+57h+var_60]
0x1800479f1  cmp     rdx, 0Fh
0x1800479f5  jbe     loc_180047B89
0x1800479fb  mov     rax, qword ptr [rbp+57h+pExceptionObject]
0x1800479ff  inc     rdx
0x180047a02  cmp     rdx, 1000h
0x180047a09  jb      short loc_180047A31
0x180047a0b  mov     rcx, [rax-8]; void *
0x180047a0f  sub     rax, rcx
0x180047a12  sub     rax, 8
0x180047a16  cmp     rax, 1Fh
0x180047a1a  ja      short loc_180047A2A
0x180047a1c  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180047a20  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180047a25  jmp     loc_180047B89
0x180047a2a  mov     ecx, 5
0x180047a2f  int     29h; Win8: RtlFailFast(ecx)
0x180047a31  mov     rcx, rax; void *
0x180047a34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180047a39  jmp     loc_180047B89
0x180047a3e  mov     rax, [rdi+0E8h]
0x180047a45  sub     rax, [rdi+0E0h]
0x180047a4c  cmp     rbx, rax
0x180047a4f  jbe     short loc_180047A60
0x180047a51  mov     rdx, rbx
0x180047a54  lea     rcx, [rdi+0E0h]
0x180047a5b  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180047a60  mov     [rdi+0D8h], r15
0x180047a67  mov     [rbp+57h+var_58], rdi
0x180047a6b  lea     rax, ??_7?$streambuf@E@streams@Concurrency@@6B@; const Concurrency::streams::streambuf<uchar>::`vftable'
0x180047a72  mov     [rbp+57h+var_50], rax
0x180047a76  mov     rax, [rbp+57h+var_A0]
0x180047a7a  test    rax, rax
0x180047a7d  jz      short loc_180047A83
0x180047a7f  lock inc dword ptr [rax+8]
0x180047a83  mov     [rbp+57h+var_48], rsi
0x180047a87  mov     [rbp+57h+var_40], rax
0x180047a8b  mov     r8, [rdi+0D8h]
0x180047a92  test    r8, r8
0x180047a95  jnz     short loc_180047A9E
0x180047a97  mov     r8, [rdi+0E0h]
0x180047a9e  mov     rax, [rsi]
0x180047aa1  mov     r9, rbx
0x180047aa4  lea     rdx, [rbp+57h+Src]
0x180047aa8  mov     rcx, rsi
0x180047aab  mov     rax, [rax+0A8h]
0x180047ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ab7  nop
0x180047ab8  lea     r8, [rbp+57h+var_58]
0x180047abc  lea     rdx, [rbp+57h+pExceptionObject]
0x180047ac0  lea     rcx, [rbp+57h+Src]
0x180047ac4  call    ??$then@V_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@4567@@Z@@?$task@_K@pplx@@QEBA?AV?$task@X@1@$$QEAV_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@6789@@Z@@Z; pplx::task<unsigned __int64>::then<`web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_>(`web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_ &&)
0x180047ac9  mov     rbx, qword ptr [rbp+57h+pExceptionObject+8]
0x180047acd  mov     edi, 0FFFFFFFFh
0x180047ad2  test    rbx, rbx
0x180047ad5  jz      short loc_180047B0D
0x180047ad7  mov     eax, edi
0x180047ad9  lock xadd [rbx+8], eax
0x180047ade  cmp     eax, 1
0x180047ae1  jnz     short loc_180047B0D
0x180047ae3  mov     rax, [rbx]
0x180047ae6  mov     rcx, rbx
0x180047ae9  mov     rax, [rax]
0x180047aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047af1  mov     eax, edi
0x180047af3  lock xadd [rbx+0Ch], eax
0x180047af8  cmp     eax, 1
0x180047afb  jnz     short loc_180047B0D
0x180047afd  mov     rax, [rbx]
0x180047b00  mov     rcx, rbx
0x180047b03  mov     rax, [rax+8]
0x180047b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b0c  nop
0x180047b0d  mov     rbx, [rbp+57h+var_90]
0x180047b11  test    rbx, rbx
0x180047b14  jz      short loc_180047B4C
0x180047b16  mov     eax, edi
0x180047b18  lock xadd [rbx+8], eax
0x180047b1d  cmp     eax, 1
0x180047b20  jnz     short loc_180047B4C
0x180047b22  mov     rax, [rbx]
0x180047b25  mov     rcx, rbx
0x180047b28  mov     rax, [rax]
0x180047b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b30  mov     eax, edi
0x180047b32  lock xadd [rbx+0Ch], eax
0x180047b37  cmp     eax, 1
0x180047b3a  jnz     short loc_180047B4C
0x180047b3c  mov     rax, [rbx]
0x180047b3f  mov     rcx, rbx
0x180047b42  mov     rax, [rax+8]
0x180047b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b4b  nop
0x180047b4c  mov     rbx, [rbp+57h+var_40]
0x180047b50  test    rbx, rbx
0x180047b53  jz      short loc_180047B89
0x180047b55  mov     eax, edi
0x180047b57  lock xadd [rbx+8], eax
0x180047b5c  cmp     eax, 1
0x180047b5f  jnz     short loc_180047B89
0x180047b61  mov     rax, [rbx]
0x180047b64  mov     rcx, rbx
0x180047b67  mov     rax, [rax]
0x180047b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b6f  lock xadd [rbx+0Ch], edi
0x180047b74  cmp     edi, 1
0x180047b77  jnz     short loc_180047B89
0x180047b79  mov     rax, [rbx]
0x180047b7c  mov     rcx, rbx
0x180047b7f  mov     rax, [rax+8]
0x180047b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b88  nop
0x180047b89  lea     rcx, [rbp+57h+var_B0]
0x180047b8d  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x180047b92  mov     rcx, [rbp+57h+var_38]
0x180047b96  xor     rcx, rsp; StackCookie
0x180047b99  call    __security_check_cookie
0x180047b9e  add     rsp, 0C8h
0x180047ba5  pop     r15
0x180047ba7  pop     r14
0x180047ba9  pop     rdi
0x180047baa  pop     rsi
0x180047bab  pop     rbx
0x180047bac  pop     rbp
0x180047bad  retn
0x180047bae  lea     rdx, aInvalidStreamb; "Invalid streambuf object"
0x180047bb5  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180047bb9  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180047bbe  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180047bc5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180047bc9  call    _CxxThrowException_0
```
