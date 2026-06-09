# web::http::client::details::winhttp_client::read_next_response_chunk(web::http::client::details::winhttp_request_context *,ulong,bool)

- ea: `0x18004e370`
- end: `0x18004e6b9`
- name: `?read_next_response_chunk@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@K_N@Z`
- size: `841`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *this, unsigned int, bool)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180045410`
- `0x180045e50`
- `0x1800492f0`

## callees

- `0x180007270`
- `0x180007640`
- `0x180029c30`
- `0x18002a210`
- `0x18002a360`
- `0x18002b430`
- `0x180048db0`
- `0x18004e370`
- `0x18004e6d0`
- `0x180051d48`
- `0x1800522a2`
- `0x1800839f8`
- `0x1800849dc`
- `0x180094184`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e3c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e3c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e586`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18004e3b5`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18004e3b5`
- `WINHTTP!WinHttpReadData` at `0x18004e578`
- `WINHTTP!WinHttpReadData` at `0x18004e578`

## string_xrefs

- `0x18004e5a2`: `WinHttpReadData`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall web::http::client::details::winhttp_client::read_next_response_chunk(
        struct web::http::client::details::winhttp_request_context *this,
        unsigned int a2,
        char a3)
{
  unsigned __int64 v4; // r15
  DWORD LastError; // ebx
  __int64 v7; // rax
  const struct std::nothrow_t *v8; // rdx
  _BYTE *v9; // rcx
  unsigned __int64 v10; // rbx
  __int64 v11; // rax
  void *v12; // rsi
  DWORD v13; // ebx
  __int64 v14; // rax
  const struct std::nothrow_t *v15; // rdx
  _BYTE *v16; // rcx
  const struct std::nothrow_t *v17; // rdx
  void *v18; // rcx
  __int128 pExceptionObject; // [rsp+20h] [rbp-58h] BYREF
  __int64 v20; // [rsp+30h] [rbp-48h]
  unsigned __int64 v21; // [rsp+38h] [rbp-40h]
  void *Src; // [rsp+40h] [rbp-38h] BYREF
  __int64 v23; // [rsp+48h] [rbp-30h]
  __int64 v24; // [rsp+50h] [rbp-28h]
  unsigned __int64 v25; // [rsp+58h] [rbp-20h]

  v4 = a2;
  if ( !*((_QWORD *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)this
                                                                                         + 1))
        + 52) )
  {
    if ( WinHttpQueryDataAvailable(*((HINTERNET *)this + 13), 0) )
      return;
    LastError = GetLastError();
    pExceptionObject = 0;
    *(_QWORD *)&pExceptionObject = operator new(0x20u);
    v20 = 25;
    v21 = 31;
    strcpy((char *)pExceptionObject, "WinHttpQueryDataAvaliable");
    v7 = web::http::client::details::build_error_msg(&Src);
    web::http::client::details::request_context::report_error(this, LastError, v7);
    if ( v25 > 0xF )
    {
      v8 = (const struct std::nothrow_t *)(v25 + 1);
      if ( v25 + 1 < 0x1000 )
      {
        v9 = Src;
      }
      else
      {
        v9 = (_BYTE *)*((_QWORD *)Src - 1);
        if ( (unsigned __int64)((_BYTE *)Src - v9 - 8) > 0x1F )
          __fastfail(5u);
        v8 = (const struct std::nothrow_t *)(v25 + 40);
      }
      operator delete(v9, v8);
    }
    v24 = 0;
    v25 = 15;
    LOBYTE(Src) = 0;
    goto LABEL_36;
  }
  v10 = *((_QWORD *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)this
                                                                                         + 1))
        + 52);
  if ( !v10 )
    v10 = 0x10000;
  if ( *((_QWORD *)this + 12) )
  {
    if ( *((_QWORD *)this + 34) - *((_QWORD *)this + 32) < v10 )
      std::vector<unsigned char>::reserve((char *)this + 256, v10);
    v12 = (void *)*((_QWORD *)this + 32);
  }
  else
  {
    if ( v4 < v10 && !a3 )
    {
      web::http::client::details::request_context::complete_request(this, *((_QWORD *)this + 8));
      return;
    }
    web::http::client::details::request_context::_get_writebuffer(this, &Src);
    if ( !v23 )
    {
      std::invalid_argument::invalid_argument((std::invalid_argument *)&pExceptionObject, "Invalid streambuf object");
      throw (std::invalid_argument *)&pExceptionObject;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v23 + 224LL))(v23, v10);
    v12 = (void *)v11;
    if ( v11 )
    {
      *((_QWORD *)this + 31) = v10;
      *((_QWORD *)this + 27) = v11;
    }
    else
    {
      if ( v10 > *((_QWORD *)this + 29) - *((_QWORD *)this + 28) )
        std::vector<unsigned char>::resize((char *)this + 224, v10);
      *((_QWORD *)this + 27) = 0;
      v12 = (void *)*((_QWORD *)this + 28);
    }
    Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(&Src);
  }
  if ( !WinHttpReadData(*((HINTERNET *)this + 13), v12, v10, 0) )
  {
    v13 = GetLastError();
    v20 = 15;
    v21 = 15;
    qmemcpy(&pExceptionObject, "WinHttpReadDat", 14);
    HIWORD(pExceptionObject) = (unsigned __int8)aWinhttpreaddat_0[14];
    v14 = web::http::client::details::build_error_msg(&Src);
    web::http::client::details::request_context::report_error(this, v13, v14);
    if ( v25 > 0xF )
    {
      v15 = (const struct std::nothrow_t *)(v25 + 1);
      if ( v25 + 1 < 0x1000 )
      {
        v16 = Src;
      }
      else
      {
        v16 = (_BYTE *)*((_QWORD *)Src - 1);
        if ( (unsigned __int64)((_BYTE *)Src - v16 - 8) > 0x1F )
          __fastfail(5u);
        v15 = (const struct std::nothrow_t *)(v25 + 40);
      }
      operator delete(v16, v15);
    }
    v24 = 0;
    v25 = 15;
    LOBYTE(Src) = 0;
LABEL_36:
    if ( v21 > 0xF )
    {
      v17 = (const struct std::nothrow_t *)(v21 + 1);
      if ( v21 + 1 < 0x1000 )
      {
        v18 = (void *)pExceptionObject;
      }
      else
      {
        v18 = *(void **)(pExceptionObject - 8);
        if ( (unsigned __int64)(pExceptionObject - (_QWORD)v18 - 8) > 0x1F )
          __fastfail(5u);
        v17 = (const struct std::nothrow_t *)(v21 + 40);
      }
      operator delete(v18, v17);
    }
  }
}

```

## disassembly

```asm
0x18004e370  push    rbp
0x18004e372  push    rbx
0x18004e373  push    rsi
0x18004e374  push    rdi
0x18004e375  push    r14
0x18004e377  push    r15
0x18004e379  mov     rbp, rsp
0x18004e37c  sub     rsp, 78h
0x18004e380  mov     rax, cs:__security_cookie
0x18004e387  xor     rax, rsp
0x18004e38a  mov     [rbp+var_18], rax
0x18004e38e  movzx   esi, r8b
0x18004e392  mov     r15d, edx
0x18004e395  mov     rdi, rcx
0x18004e398  mov     rcx, [rcx+8]; this
0x18004e39c  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x18004e3a1  cmp     qword ptr [rax+1A0h], 0
0x18004e3a9  jnz     loc_18004E47F
0x18004e3af  xor     edx, edx; lpdwNumberOfBytesAvailable
0x18004e3b1  mov     rcx, [rdi+68h]; hRequest
0x18004e3b5  call    cs:__imp_WinHttpQueryDataAvailable
0x18004e3bb  test    eax, eax
0x18004e3bd  jnz     loc_18004E67F
0x18004e3c3  call    cs:__imp_GetLastError
0x18004e3c9  mov     ebx, eax
0x18004e3cb  xorps   xmm0, xmm0
0x18004e3ce  movups  [rbp+pExceptionObject], xmm0
0x18004e3d2  xor     r14d, r14d
0x18004e3d5  mov     ecx, 20h ; ' '; Size
0x18004e3da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004e3df  mov     qword ptr [rbp+pExceptionObject], rax
0x18004e3e3  mov     [rbp+var_48], 19h
0x18004e3eb  mov     [rbp+var_40], 1Fh
0x18004e3f3  movups  xmm0, xmmword ptr cs:aWinhttpqueryda_0; "WinHttpQueryDataAvaliable"
0x18004e3fa  movups  xmmword ptr [rax], xmm0
0x18004e3fd  movups  xmm1, xmmword ptr cs:aWinhttpqueryda_0+9; "eryDataAvaliable"
0x18004e404  movups  xmmword ptr [rax+9], xmm1
0x18004e408  mov     [rax+19h], r14b
0x18004e40c  lea     r8, [rbp+pExceptionObject]
0x18004e410  mov     edx, ebx
0x18004e412  lea     rcx, [rbp+Src]; Src
0x18004e416  call    web__http__client__details__build_error_msg
0x18004e41b  nop
0x18004e41c  mov     r8, rax
0x18004e41f  mov     edx, ebx
0x18004e421  mov     rcx, rdi
0x18004e424  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x18004e429  nop
0x18004e42a  mov     rdx, [rbp+var_20]
0x18004e42e  cmp     rdx, 0Fh
0x18004e432  jbe     short loc_18004E46A
0x18004e434  mov     rax, [rbp+Src]
0x18004e438  inc     rdx; struct std::nothrow_t *
0x18004e43b  cmp     rdx, 1000h
0x18004e442  jb      short loc_18004E462
0x18004e444  mov     rcx, [rax-8]
0x18004e448  sub     rax, rcx
0x18004e44b  sub     rax, 8
0x18004e44f  cmp     rax, 1Fh
0x18004e453  ja      short loc_18004E45B
0x18004e455  add     rdx, 27h ; '''
0x18004e459  jmp     short loc_18004E465
0x18004e45b  mov     ecx, 5
0x18004e460  int     29h; Win8: RtlFailFast(ecx)
0x18004e462  mov     rcx, rax; void *
0x18004e465  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004e46a  mov     [rbp+var_28], r14
0x18004e46e  mov     [rbp+var_20], 0Fh
0x18004e476  mov     byte ptr [rbp+Src], 0
0x18004e47a  jmp     loc_18004E63F
0x18004e47f  mov     rcx, [rdi+8]; this
0x18004e483  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x18004e488  mov     rbx, [rax+1A0h]
0x18004e48f  mov     eax, 10000h
0x18004e494  test    rbx, rbx
0x18004e497  cmovz   rbx, rax
0x18004e49b  xor     r14d, r14d
0x18004e49e  cmp     [rdi+60h], r14
0x18004e4a2  jnz     loc_18004E542
0x18004e4a8  cmp     r15, rbx
0x18004e4ab  jnb     short loc_18004E4C3
0x18004e4ad  test    sil, sil
0x18004e4b0  jnz     short loc_18004E4C3
0x18004e4b2  mov     rdx, [rdi+40h]; unsigned __int64
0x18004e4b6  mov     rcx, rdi; this
0x18004e4b9  call    ?complete_request@request_context@details@client@http@web@@QEAAX_K@Z; web::http::client::details::request_context::complete_request(unsigned __int64)
0x18004e4be  jmp     loc_18004E67F
0x18004e4c3  lea     rdx, [rbp+Src]
0x18004e4c7  mov     rcx, rdi
0x18004e4ca  call    ?_get_writebuffer@request_context@details@client@http@web@@QEAA?AV?$streambuf@E@streams@Concurrency@@XZ; web::http::client::details::request_context::_get_writebuffer(void)
0x18004e4cf  nop
0x18004e4d0  mov     rcx, [rbp+var_30]
0x18004e4d4  test    rcx, rcx
0x18004e4d7  jz      loc_18004E698
0x18004e4dd  mov     rax, [rcx]
0x18004e4e0  mov     rdx, rbx
0x18004e4e3  mov     rax, [rax+0E0h]
0x18004e4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4ef  mov     rsi, rax
0x18004e4f2  test    rax, rax
0x18004e4f5  jnz     short loc_18004E529
0x18004e4f7  mov     rax, [rdi+0E8h]
0x18004e4fe  sub     rax, [rdi+0E0h]
0x18004e505  cmp     rbx, rax
0x18004e508  jbe     short loc_18004E519
0x18004e50a  mov     rdx, rbx
0x18004e50d  lea     rcx, [rdi+0E0h]
0x18004e514  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18004e519  mov     [rdi+0D8h], r14
0x18004e520  mov     rsi, [rdi+0E0h]
0x18004e527  jmp     short loc_18004E537
0x18004e529  mov     [rdi+0F8h], rbx
0x18004e530  mov     [rdi+0D8h], rax
0x18004e537  lea     rcx, [rbp+Src]
0x18004e53b  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x18004e540  jmp     short loc_18004E56B
0x18004e542  mov     rax, [rdi+110h]
0x18004e549  sub     rax, [rdi+100h]
0x18004e550  cmp     rax, rbx
0x18004e553  jnb     short loc_18004E564
0x18004e555  mov     rdx, rbx
0x18004e558  lea     rcx, [rdi+100h]
0x18004e55f  call    ?reserve@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::reserve(unsigned __int64)
0x18004e564  mov     rsi, [rdi+100h]
0x18004e56b  mov     r8d, ebx; dwNumberOfBytesToRead
0x18004e56e  xor     r9d, r9d; lpdwNumberOfBytesRead
0x18004e571  mov     rdx, rsi; lpBuffer
0x18004e574  mov     rcx, [rdi+68h]; hRequest
0x18004e578  call    cs:__imp_WinHttpReadData
0x18004e57e  test    eax, eax
0x18004e580  jnz     loc_18004E67F
0x18004e586  call    cs:__imp_GetLastError
0x18004e58c  mov     ebx, eax
0x18004e58e  mov     byte ptr [rbp+pExceptionObject+0Fh], 0
0x18004e592  mov     [rbp+var_48], 0Fh
0x18004e59a  mov     [rbp+var_40], 0Fh
0x18004e5a2  movsd   xmm0, qword ptr cs:aWinhttpreaddat_0; "WinHttpReadData"
0x18004e5aa  movsd   qword ptr [rbp+pExceptionObject], xmm0
0x18004e5af  mov     ecx, dword ptr cs:aWinhttpreaddat_0+8; "eadData"
0x18004e5b5  mov     dword ptr [rbp+pExceptionObject+8], ecx
0x18004e5b8  movzx   ecx, word ptr cs:aWinhttpreaddat_0+0Ch; "ata"
0x18004e5bf  mov     word ptr [rbp+pExceptionObject+0Ch], cx
0x18004e5c3  movzx   eax, byte ptr cs:aWinhttpreaddat_0+0Eh; "a"
0x18004e5ca  mov     byte ptr [rbp+pExceptionObject+0Eh], al
0x18004e5cd  mov     byte ptr [rbp+pExceptionObject+0Fh], 0
0x18004e5d1  lea     r8, [rbp+pExceptionObject]
0x18004e5d5  mov     edx, ebx
0x18004e5d7  lea     rcx, [rbp+Src]; Src
0x18004e5db  call    web__http__client__details__build_error_msg
0x18004e5e0  nop
0x18004e5e1  mov     r8, rax
0x18004e5e4  mov     edx, ebx
0x18004e5e6  mov     rcx, rdi
0x18004e5e9  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x18004e5ee  nop
0x18004e5ef  mov     rdx, [rbp+var_20]
0x18004e5f3  cmp     rdx, 0Fh
0x18004e5f7  jbe     short loc_18004E62F
0x18004e5f9  mov     rax, [rbp+Src]
0x18004e5fd  inc     rdx; struct std::nothrow_t *
0x18004e600  cmp     rdx, 1000h
0x18004e607  jb      short loc_18004E627
0x18004e609  mov     rcx, [rax-8]
0x18004e60d  sub     rax, rcx
0x18004e610  sub     rax, 8
0x18004e614  cmp     rax, 1Fh
0x18004e618  ja      short loc_18004E620
0x18004e61a  add     rdx, 27h ; '''
0x18004e61e  jmp     short loc_18004E62A
0x18004e620  mov     ecx, 5
0x18004e625  int     29h; Win8: RtlFailFast(ecx)
0x18004e627  mov     rcx, rax; void *
0x18004e62a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004e62f  mov     [rbp+var_28], r14
0x18004e633  mov     [rbp+var_20], 0Fh
0x18004e63b  mov     byte ptr [rbp+Src], 0
0x18004e63f  mov     rdx, [rbp+var_40]
0x18004e643  cmp     rdx, 0Fh
0x18004e647  jbe     short loc_18004E67F
0x18004e649  mov     rax, qword ptr [rbp+pExceptionObject]
0x18004e64d  inc     rdx; struct std::nothrow_t *
0x18004e650  cmp     rdx, 1000h
0x18004e657  jb      short loc_18004E677
0x18004e659  mov     rcx, [rax-8]
0x18004e65d  sub     rax, rcx
0x18004e660  sub     rax, 8
0x18004e664  cmp     rax, 1Fh
0x18004e668  ja      short loc_18004E670
0x18004e66a  add     rdx, 27h ; '''
0x18004e66e  jmp     short loc_18004E67A
0x18004e670  mov     ecx, 5
0x18004e675  int     29h; Win8: RtlFailFast(ecx)
0x18004e677  mov     rcx, rax; void *
0x18004e67a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004e67f  mov     rcx, [rbp+var_18]
0x18004e683  xor     rcx, rsp; StackCookie
0x18004e686  call    __security_check_cookie
0x18004e68b  add     rsp, 78h
0x18004e68f  pop     r15
0x18004e691  pop     r14
0x18004e693  pop     rdi
0x18004e694  pop     rsi
0x18004e695  pop     rbx
0x18004e696  pop     rbp
0x18004e697  retn
0x18004e698  lea     rdx, aInvalidStreamb; "Invalid streambuf object"
0x18004e69f  lea     rcx, [rbp+pExceptionObject]; this
0x18004e6a3  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18004e6a8  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18004e6af  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004e6b3  call    _CxxThrowException_0
```
