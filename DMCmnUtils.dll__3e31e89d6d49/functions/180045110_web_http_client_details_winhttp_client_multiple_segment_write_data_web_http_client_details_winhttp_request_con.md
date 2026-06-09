# `web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)'::`21'::_lambda_1_::operator()(pplx::task<unsigned __int64>)

- ea: `0x180045110`
- end: `0x1800453fe`
- name: `??R_lambda_1_@?BF@??_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@3456@@Z@QEBA@V?$task@_K@pplx@@@Z`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task`

## callers

- `0x180046ff0`

## callees

- `0x180007270`
- `0x180007640`
- `0x180007b62`
- `0x180027760`
- `0x18002b430`
- `0x180032550`
- `0x180045110`
- `0x180048db0`
- `0x180051d48`
- `0x18005b73c`
- `0x18006f7a0`
- `0x1800848e4`
- `0x1800927bc`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800452c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800452c0`
- `WINHTTP!WinHttpWriteData` at `0x1800452b2`
- `WINHTTP!WinHttpWriteData` at `0x1800452b2`

## string_xrefs

- `0x180045303`: `WinHttpWriteData`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall `web::http::client::details::winhttp_client::_multiple_segment_write_data'::`21'::_lambda_1_::operator()(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v4; // rax
  void *v5; // rax
  const struct std::nothrow_t *v6; // rdx
  void *v7; // rcx
  volatile signed __int32 *v8; // rdi
  __int64 v9; // rcx
  const void *v10; // rdx
  DWORD LastError; // ebx
  __int64 v12; // r8
  const struct std::nothrow_t *v13; // rdx
  void *v14; // rcx
  __int64 v15; // rax
  __int128 v18; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-98h]
  __int64 v20; // [rsp+48h] [rbp-90h]
  void *Src[3]; // [rsp+50h] [rbp-88h] BYREF
  unsigned __int64 v22; // [rsp+68h] [rbp-70h]
  void **v23; // [rsp+70h] [rbp-68h] BYREF
  __int128 v24; // [rsp+78h] [rbp-60h] BYREF
  int v25; // [rsp+88h] [rbp-50h]
  void ***v26; // [rsp+90h] [rbp-48h]
  _BYTE v27[40]; // [rsp+98h] [rbp-40h] BYREF

  try
  {
    v4 = pplx::task<unsigned __int64>::get(a2);
  }
  catch ( ... )
  {
    v15 = std::current_exception(&v18);
    web::http::client::details::request_context::report_exception(*a1, v15);
    pplx::task<long>::~task<long>(a2);
    return;
  }
  if ( v4 )
  {
    *(_QWORD *)(*a1 + 144LL) -= v4;
    if ( !*(_QWORD *)(*a1 + 144LL) )
      *(_DWORD *)(*a1 + 136LL) = 0;
    v9 = *a1;
    v10 = *(const void **)(*a1 + 216LL);
    if ( !v10 )
      v10 = *(const void **)(v9 + 224);
    if ( WinHttpWriteData(*(HINTERNET *)(v9 + 104), v10, v4, 0) )
      goto LABEL_9;
    LastError = GetLastError();
    v18 = 0;
    *(_QWORD *)&v18 = operator new(0x20u);
    v19 = 16;
    v20 = 31;
    strcpy((char *)v18, "WinHttpWriteData");
    v12 = web::http::client::details::build_error_msg(Src);
    web::http::client::details::request_context::report_error(*a1, LastError, v12);
    if ( v22 > 0xF )
    {
      v13 = (const struct std::nothrow_t *)(v22 + 1);
      if ( v22 + 1 < 0x1000 )
      {
        v14 = Src[0];
      }
      else
      {
        v14 = (void *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v14 - 8) > 0x1F )
          __fastfail(5u);
        v13 = (const struct std::nothrow_t *)(v22 + 40);
      }
      operator delete(v14, v13);
    }
    Src[2] = 0;
    v22 = 15;
    LOBYTE(Src[0]) = 0;
    v5 = (void *)v18;
    v6 = (const struct std::nothrow_t *)(v20 + 1);
    if ( (unsigned __int64)(v20 + 1) >= 0x1000 )
    {
      v7 = *(void **)(v18 - 8);
      if ( (unsigned __int64)(v18 - (_QWORD)v7 - 8) <= 0x1F )
      {
        v6 = (const struct std::nothrow_t *)(v20 + 40);
        goto LABEL_8;
      }
      goto LABEL_29;
    }
LABEL_7:
    v7 = v5;
    goto LABEL_8;
  }
  std::wstring::wstring(Src, L"Unexpected end of request body stream encountered before Content-Length met.");
  v24 = 0;
  v23 = &web::http::http_exception::`vftable';
  v25 = 0;
  v26 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  utility::conversions::to_utf8string(v27, Src);
  web::http::client::details::request_context::report_exception<web::http::http_exception>(*a1, &v23);
  std::string::~string(v27);
  v23 = &std::exception::`vftable';
  o___std_exception_destroy_0(&v24);
  if ( v22 > 7 )
  {
    v5 = Src[0];
    v6 = (const struct std::nothrow_t *)(2 * v22 + 2);
    if ( (unsigned __int64)v6 >= 0x1000 )
    {
      v7 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v7 - 8) <= 0x1F )
      {
        v6 = (const struct std::nothrow_t *)(2 * v22 + 41);
LABEL_8:
        operator delete(v7, v6);
        goto LABEL_9;
      }
LABEL_29:
      __fastfail(5u);
    }
    goto LABEL_7;
  }
LABEL_9:
  v8 = (volatile signed __int32 *)a2[1];
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
}

```

## disassembly

```asm
0x180045110  mov     [rsp+arg_10], rbx
0x180045115  mov     [rsp+arg_18], rsi
0x18004511a  push    rdi
0x18004511b  sub     rsp, 0D0h
0x180045122  mov     rax, cs:__security_cookie
0x180045129  xor     rax, rsp
0x18004512c  mov     [rsp+0D8h+var_18], rax
0x180045134  mov     rsi, rdx
0x180045137  mov     rdi, rcx
0x18004513a  mov     [rsp+0D8h+var_B8], rcx
0x18004513f  mov     [rsp+0D8h+var_B0], rdx
0x180045144  mov     rcx, rdx
0x180045147  call    ?get@?$task@_K@pplx@@QEBA_KXZ; pplx::task<unsigned __int64>::get(void)
0x18004514c  mov     r8, rax; dwNumberOfBytesToWrite
0x18004514f  test    r8, r8
0x180045152  jnz     loc_180045274
0x180045158  lea     rdx, aUnexpectedEndO_0; "Unexpected end of request body stream e"...
0x18004515f  lea     rcx, [rsp+0D8h+Src]
0x180045164  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180045169  nop
0x18004516a  xorps   xmm0, xmm0
0x18004516d  movups  [rsp+0D8h+var_60], xmm0
0x180045172  lea     rax, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x180045179  mov     [rsp+0D8h+var_68], rax
0x18004517e  mov     [rsp+0D8h+var_50], 0
0x180045189  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180045190  mov     [rsp+0D8h+var_48], rax
0x180045198  lea     rdx, [rsp+0D8h+Src]
0x18004519d  lea     rcx, [rsp+0D8h+var_40]
0x1800451a5  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x1800451aa  nop
0x1800451ab  lea     rdx, [rsp+0D8h+var_68]
0x1800451b0  mov     rcx, [rdi]
0x1800451b3  call    ??$report_exception@Vhttp_exception@http@web@@@request_context@details@client@http@web@@QEAAXAEBVhttp_exception@34@@Z; web::http::client::details::request_context::report_exception<web::http::http_exception>(web::http::http_exception const &)
0x1800451b8  nop
0x1800451b9  lea     rcx, [rsp+0D8h+var_40]
0x1800451c1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800451c6  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800451cd  mov     [rsp+0D8h+var_68], rax
0x1800451d2  lea     rcx, [rsp+0D8h+var_60]
0x1800451d7  call    _o___std_exception_destroy_0
0x1800451dc  nop
0x1800451dd  mov     rdx, [rsp+0D8h+var_70]
0x1800451e2  cmp     rdx, 7
0x1800451e6  jbe     short loc_180045222
0x1800451e8  mov     rax, [rsp+0D8h+Src]
0x1800451ed  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x1800451f5  cmp     rdx, 1000h
0x1800451fc  jb      short loc_180045219
0x1800451fe  mov     rcx, [rax-8]
0x180045202  sub     rax, rcx
0x180045205  sub     rax, 8
0x180045209  cmp     rax, 1Fh
0x18004520d  ja      loc_1800453C8
0x180045213  add     rdx, 27h ; '''
0x180045217  jmp     short loc_18004521C
0x180045219  mov     rcx, rax; void *
0x18004521c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180045221  nop
0x180045222  mov     rdi, [rsi+8]
0x180045226  test    rdi, rdi
0x180045229  jz      loc_1800453D9
0x18004522f  mov     ebx, 0FFFFFFFFh
0x180045234  mov     eax, ebx
0x180045236  lock xadd [rdi+8], eax
0x18004523b  cmp     eax, 1
0x18004523e  jnz     loc_1800453D9
0x180045244  mov     rax, [rdi]
0x180045247  mov     rcx, rdi
0x18004524a  mov     rax, [rax]
0x18004524d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045252  lock xadd [rdi+0Ch], ebx
0x180045257  cmp     ebx, 1
0x18004525a  jnz     loc_1800453D9
0x180045260  mov     rax, [rdi]
0x180045263  mov     rcx, rdi
0x180045266  mov     rax, [rax+8]
0x18004526a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004526f  jmp     loc_1800453D9
0x180045274  mov     rax, [rdi]
0x180045277  sub     [rax+90h], r8
0x18004527e  mov     rax, [rdi]
0x180045281  cmp     qword ptr [rax+90h], 0
0x180045289  jnz     short loc_180045295
0x18004528b  mov     dword ptr [rax+88h], 0
0x180045295  mov     rcx, [rdi]
0x180045298  mov     rdx, [rcx+0D8h]
0x18004529f  test    rdx, rdx
0x1800452a2  jnz     short loc_1800452AB
0x1800452a4  mov     rdx, [rcx+0E0h]; lpBuffer
0x1800452ab  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x1800452ae  mov     rcx, [rcx+68h]; hRequest
0x1800452b2  call    cs:__imp_WinHttpWriteData
0x1800452b8  test    eax, eax
0x1800452ba  jnz     loc_180045222
0x1800452c0  call    cs:__imp_GetLastError
0x1800452c6  mov     ebx, eax
0x1800452c8  xorps   xmm0, xmm0
0x1800452cb  movups  [rsp+0D8h+var_A8], xmm0
0x1800452d0  mov     [rsp+0D8h+var_98], 0
0x1800452d9  mov     [rsp+0D8h+var_90], 0
0x1800452e2  mov     ecx, 20h ; ' '; Size
0x1800452e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800452ec  mov     qword ptr [rsp+0D8h+var_A8], rax
0x1800452f1  mov     [rsp+0D8h+var_98], 10h
0x1800452fa  mov     [rsp+0D8h+var_90], 1Fh
0x180045303  movups  xmm0, xmmword ptr cs:aWinhttpwriteda_0; "WinHttpWriteData"
0x18004530a  movups  xmmword ptr [rax], xmm0
0x18004530d  mov     byte ptr [rax+10h], 0
0x180045311  lea     r8, [rsp+0D8h+var_A8]
0x180045316  mov     edx, ebx
0x180045318  lea     rcx, [rsp+0D8h+Src]; Src
0x18004531d  call    web__http__client__details__build_error_msg
0x180045322  nop
0x180045323  mov     r8, rax
0x180045326  mov     edx, ebx
0x180045328  mov     rcx, [rdi]
0x18004532b  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180045330  nop
0x180045331  mov     rdx, [rsp+0D8h+var_70]
0x180045336  cmp     rdx, 0Fh
0x18004533a  jbe     short loc_180045373
0x18004533c  mov     rax, [rsp+0D8h+Src]
0x180045341  inc     rdx; struct std::nothrow_t *
0x180045344  cmp     rdx, 1000h
0x18004534b  jb      short loc_18004536B
0x18004534d  mov     rcx, [rax-8]
0x180045351  sub     rax, rcx
0x180045354  sub     rax, 8
0x180045358  cmp     rax, 1Fh
0x18004535c  ja      short loc_180045364
0x18004535e  add     rdx, 27h ; '''
0x180045362  jmp     short loc_18004536E
0x180045364  mov     ecx, 5
0x180045369  int     29h; Win8: RtlFailFast(ecx)
0x18004536b  mov     rcx, rax; void *
0x18004536e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180045373  mov     [rsp+0D8h+var_78], 0
0x18004537c  mov     [rsp+0D8h+var_70], 0Fh
0x180045385  mov     byte ptr [rsp+0D8h+Src], 0
0x18004538a  mov     rdx, [rsp+0D8h+var_90]
0x18004538f  cmp     rdx, 0Fh
0x180045393  jbe     loc_180045222
0x180045399  mov     rax, qword ptr [rsp+0D8h+var_A8]
0x18004539e  inc     rdx
0x1800453a1  cmp     rdx, 1000h
0x1800453a8  jb      loc_180045219
0x1800453ae  mov     rcx, [rax-8]
0x1800453b2  sub     rax, rcx
0x1800453b5  sub     rax, 8
0x1800453b9  cmp     rax, 1Fh
0x1800453bd  ja      short loc_1800453C8
0x1800453bf  add     rdx, 27h ; '''
0x1800453c3  jmp     loc_18004521C
0x1800453c8  mov     ecx, 5
0x1800453cd  int     29h; Win8: RtlFailFast(ecx)
0x1800453cf  mov     rcx, [rsp+0D8h+var_B0]; void *
0x1800453d4  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x1800453d9  mov     rcx, [rsp+0D8h+var_18]
0x1800453e1  xor     rcx, rsp; StackCookie
0x1800453e4  call    __security_check_cookie
0x1800453e9  lea     r11, [rsp+0D8h+var_8]
0x1800453f1  mov     rbx, [r11+20h]
0x1800453f5  mov     rsi, [r11+28h]
0x1800453f9  mov     rsp, r11
0x1800453fc  pop     rdi
0x1800453fd  retn
```
