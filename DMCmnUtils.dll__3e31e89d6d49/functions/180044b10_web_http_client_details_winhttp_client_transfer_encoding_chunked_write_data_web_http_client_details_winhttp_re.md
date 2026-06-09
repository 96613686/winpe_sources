# `web::http::client::details::winhttp_client::_transfer_encoding_chunked_write_data(web::http::client::details::winhttp_request_context *)'::`2'::_lambda_1_::operator()(pplx::task<unsigned __int64>)

- ea: `0x180044b10`
- end: `0x180045108`
- name: `??R_lambda_1_@?1??_transfer_encoding_chunked_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@3456@@Z@QEBA@V?$task@_K@pplx@@@Z`
- size: `1528`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, service_task`

## callers

- `0x180046fb0`
- `0x180048460`

## callees

- `0x180007270`
- `0x180007640`
- `0x180007b62`
- `0x18000e950`
- `0x180027760`
- `0x18002b430`
- `0x180032550`
- `0x180033470`
- `0x1800434f0`
- `0x180044b10`
- `0x180048db0`
- `0x180050700`
- `0x180051d48`
- `0x1800522a2`
- `0x18005b73c`
- `0x18005b8d0`
- `0x18006f7a0`
- `0x1800839f8`
- `0x1800848e4`
- `0x1800849dc`
- `0x1800927bc`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044f4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044f4c`
- `WINHTTP!WinHttpWriteData` at `0x180044f3e`
- `WINHTTP!WinHttpWriteData` at `0x180044f3e`

## string_xrefs

- `0x180044f89`: `WinHttpWriteData`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall `web::http::client::details::winhttp_client::_transfer_encoding_chunked_write_data'::`2'::_lambda_1_::operator()(
        void **a1,
        _QWORD *a2)
{
  unsigned __int64 v4; // r9
  __int64 v5; // r14
  _QWORD *v6; // rcx
  __int64 v7; // r10
  __int64 v8; // r8
  __int64 v9; // rax
  volatile signed __int32 *v10; // rbx
  web::http::details::chunked_encoding *v11; // rcx
  unsigned __int8 *v12; // rdx
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // r12
  __int64 v15; // rcx
  void *v16; // rcx
  __int64 v17; // r8
  _QWORD *v18; // r8
  __int64 v19; // rdx
  void *v20; // rcx
  void *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  const struct std::nothrow_t *v24; // rdx
  void *v25; // rcx
  void *v26; // rdx
  volatile signed __int32 *v27; // rcx
  volatile signed __int32 *v28; // rbx
  volatile signed __int32 *v29; // rbx
  void (__fastcall ***v30)(_QWORD, __int64); // rcx
  void *v31; // rcx
  __int64 v32; // rax
  DWORD LastError; // ebx
  __int64 v34; // r8
  const struct std::nothrow_t *v35; // rdx
  void *v36; // rcx
  const struct std::nothrow_t *v37; // rdx
  void *v38; // rcx
  volatile signed __int32 *v39; // rbx
  __int64 v40; // rax
  __int64 v41; // [rsp+30h] [rbp-138h] BYREF
  volatile signed __int32 *v42; // [rsp+38h] [rbp-130h]
  void **v43; // [rsp+48h] [rbp-120h]
  void *v44[2]; // [rsp+50h] [rbp-118h] BYREF
  __int64 v45; // [rsp+60h] [rbp-108h]
  void *v46; // [rsp+68h] [rbp-100h]
  void **v47; // [rsp+70h] [rbp-F8h] BYREF
  __int128 v48; // [rsp+78h] [rbp-F0h]
  _BYTE pExceptionObject[24]; // [rsp+88h] [rbp-E0h] BYREF
  void *v50[2]; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-B8h]
  unsigned __int64 v52; // [rsp+B8h] [rbp-B0h]
  void *Src[2]; // [rsp+C0h] [rbp-A8h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-98h]
  unsigned __int64 v55; // [rsp+D8h] [rbp-90h]
  void **v56; // [rsp+E0h] [rbp-88h] BYREF
  __int128 v57; // [rsp+E8h] [rbp-80h] BYREF
  int v58; // [rsp+F8h] [rbp-70h]
  void ***v59; // [rsp+100h] [rbp-68h]
  _BYTE v60[40]; // [rsp+108h] [rbp-60h] BYREF

  v43 = a1;
  v46 = a2;
  try
  {
    v5 = pplx::task<unsigned __int64>::get();
    v6 = *a1;
    v7 = *((_QWORD *)*a1 + 24);
    if ( v7 && !*(_QWORD *)a1[2] )
    {
      v8 = v6[27];
      if ( !v8 )
        v8 = v6[28];
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, __int64))(*(_QWORD *)v7 + 112LL))(
             *((_QWORD *)*a1 + 24),
             &v41,
             v8 + 10,
             v5);
      pplx::task<unsigned __int64>::wait(v9);
      v10 = v42;
      if ( v42 )
      {
        if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
    }
    v11 = (web::http::details::chunked_encoding *)*((_QWORD *)*a1 + 27);
    if ( !v11 )
      v11 = (web::http::details::chunked_encoding *)*((_QWORD *)*a1 + 28);
    v12 = (unsigned __int8 *)a1[1] + 12;
    v13 = v5;
  }
  catch ( ... )
  {
    v40 = std::current_exception(&v41);
    web::http::client::details::request_context::report_exception(*v43, v40);
    v16 = v46;
    goto LABEL_63;
  }
  v14 = web::http::details::chunked_encoding::add_chunked_delimiters(v11, v12, v13, v4);
  if ( !*(_QWORD *)a1[2] )
  {
    v15 = *((_QWORD *)*a1 + 18);
    if ( v15 != -1 )
    {
      if ( !v5 && v15 )
      {
        std::wstring::wstring(v50, L"Unexpected end of request body stream encountered before expected length met.");
        v57 = 0;
        v56 = &web::http::http_exception::`vftable';
        v58 = 0;
        v59 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        utility::conversions::to_utf8string(v60, v50);
        std::wstring::~wstring(v50);
        web::http::client::details::request_context::report_exception<web::http::http_exception>(*a1, &v56);
        std::string::~string(v60);
        v56 = &std::exception::`vftable';
        o___std_exception_destroy_0(&v57);
        v16 = a2;
LABEL_63:
        pplx::task<long>::~task<long>(v16);
        return;
      }
      *((_QWORD *)*a1 + 18) = v15 - v5;
    }
  }
  if ( !v5 )
  {
    *((_DWORD *)*a1 + 34) = 0;
    v17 = *((_QWORD *)*a1 + 24);
    if ( v17 )
    {
      v18 = *(_QWORD **)(v17 + 8);
      if ( !v18 )
      {
        std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "Invalid streambuf object");
        throw (std::invalid_argument *)pExceptionObject;
      }
      v19 = v18[8];
      v18[8] = 0;
      v20 = (void *)v18[7];
      v18[7] = 0;
      v21 = (void *)v18[6];
      v18[6] = 0;
      v43 = v44;
      v45 = 0;
      v44[1] = 0;
      v44[0] = 0;
      Src[0] = v21;
      Src[1] = v20;
      v54 = v19;
      v22 = Concurrency::streams::container_buffer<std::vector<unsigned char>>::container_buffer<std::vector<unsigned char>>(
              v50,
              Src,
              1);
      v47 = &Concurrency::streams::streambuf<unsigned char>::`vftable';
      v48 = 0;
      v23 = *(_QWORD *)(v22 + 16);
      if ( v23 )
        _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
      v48 = *(_OWORD *)(v22 + 8);
      Concurrency::streams::basic_istream<unsigned char>::basic_istream<unsigned char>(&v41, &v47);
      Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v50);
      if ( v44[0] )
      {
        v24 = (const struct std::nothrow_t *)(v45 - (unsigned __int64)v44[0]);
        if ( v45 - (unsigned __int64)v44[0] < 0x1000 )
        {
          v25 = v44[0];
        }
        else
        {
          v25 = (void *)*((_QWORD *)v44[0] - 1);
          if ( (unsigned __int64)((char *)v44[0] - (char *)v25 - 8) > 0x1F )
            goto LABEL_56;
          v24 = (const struct std::nothrow_t *)((char *)v24 + 39);
        }
        operator delete(v25, v24);
        *(_OWORD *)v44 = 0;
        v45 = 0;
      }
      v26 = *a1;
      v27 = v42;
      if ( v42 )
      {
        _InterlockedIncrement(v42 + 2);
        v27 = v42;
      }
      *((_QWORD *)v26 + 22) = v41;
      v28 = (volatile signed __int32 *)*((_QWORD *)v26 + 23);
      *((_QWORD *)v26 + 23) = v27;
      if ( v28 )
      {
        if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
          if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        }
      }
      v29 = v42;
      if ( v42 )
      {
        if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
          if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
        }
      }
      v30 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)*a1 + 24);
      *((_QWORD *)*a1 + 24) = 0;
      if ( v30 )
        (**v30)(v30, 1);
    }
  }
  v31 = *a1;
  v32 = *((_QWORD *)*a1 + 27);
  if ( !v32 )
    v32 = *((_QWORD *)v31 + 28);
  if ( WinHttpWriteData(*((HINTERNET *)v31 + 13), (LPCVOID)(v14 + v32), v5 - v14 + 12, 0) )
    goto LABEL_59;
  LastError = GetLastError();
  *(_OWORD *)v50 = 0;
  v50[0] = operator new(0x20u);
  v51 = 16;
  v52 = 31;
  strcpy((char *)v50[0], "WinHttpWriteData");
  v34 = web::http::client::details::build_error_msg(Src);
  web::http::client::details::request_context::report_error(*a1, LastError, v34);
  if ( v55 > 0xF )
  {
    v35 = (const struct std::nothrow_t *)(v55 + 1);
    if ( v55 + 1 < 0x1000 )
    {
      v36 = Src[0];
    }
    else
    {
      v36 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v36 - 8) > 0x1F )
        __fastfail(5u);
      v35 = (const struct std::nothrow_t *)(v55 + 40);
    }
    operator delete(v36, v35);
  }
  v54 = 0;
  v55 = 15;
  LOBYTE(Src[0]) = 0;
  if ( v52 <= 0xF )
    goto LABEL_59;
  v37 = (const struct std::nothrow_t *)(v52 + 1);
  if ( v52 + 1 < 0x1000 )
  {
    v38 = v50[0];
    goto LABEL_58;
  }
  v38 = (void *)*((_QWORD *)v50[0] - 1);
  if ( (unsigned __int64)((char *)v50[0] - (char *)v38 - 8) > 0x1F )
LABEL_56:
    __fastfail(5u);
  v37 = (const struct std::nothrow_t *)(v52 + 40);
LABEL_58:
  operator delete(v38, v37);
LABEL_59:
  v39 = (volatile signed __int32 *)a2[1];
  if ( v39 )
  {
    if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
      if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
    }
  }
}

```

## disassembly

```asm
0x180044b10  mov     [rsp+arg_10], rbx
0x180044b15  mov     [rsp+arg_18], rsi
0x180044b1a  push    rdi
0x180044b1b  push    r12
0x180044b1d  push    r13
0x180044b1f  push    r14
0x180044b21  push    r15
0x180044b23  sub     rsp, 140h
0x180044b2a  mov     rax, cs:__security_cookie
0x180044b31  xor     rax, rsp
0x180044b34  mov     [rsp+168h+var_38], rax
0x180044b3c  mov     r15, rdx
0x180044b3f  mov     rdi, rcx
0x180044b42  mov     [rsp+168h+var_120], rcx
0x180044b47  mov     [rsp+168h+var_100], rdx
0x180044b4c  xor     r13d, r13d
0x180044b4f  mov     rcx, rdx
0x180044b52  call    ?get@?$task@_K@pplx@@QEBA_KXZ; pplx::task<unsigned __int64>::get(void)
0x180044b57  mov     r14, rax
0x180044b5a  mov     rcx, [rdi]
0x180044b5d  mov     r10, [rcx+0C0h]
0x180044b64  test    r10, r10
0x180044b67  jz      loc_180044BF4
0x180044b6d  mov     rax, [rdi+10h]
0x180044b71  cmp     [rax], r13
0x180044b74  jnz     short loc_180044BF4
0x180044b76  mov     r8, [rcx+0D8h]
0x180044b7d  test    r8, r8
0x180044b80  jnz     short loc_180044B89
0x180044b82  mov     r8, [rcx+0E0h]
0x180044b89  mov     rax, [r10]
0x180044b8c  add     r8, 0Ah
0x180044b90  mov     r9, r14
0x180044b93  lea     rdx, [rsp+168h+var_138]
0x180044b98  mov     rcx, r10
0x180044b9b  mov     rax, [rax+70h]
0x180044b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ba4  nop
0x180044ba5  mov     rcx, rax
0x180044ba8  call    ?wait@?$task@_K@pplx@@QEBA?AW4task_group_status@2@XZ; pplx::task<unsigned __int64>::wait(void)
0x180044bad  nop
0x180044bae  mov     rbx, [rsp+168h+var_130]
0x180044bb3  test    rbx, rbx
0x180044bb6  jz      short loc_180044BF4
0x180044bb8  mov     esi, 0FFFFFFFFh
0x180044bbd  mov     eax, esi
0x180044bbf  lock xadd [rbx+8], eax
0x180044bc4  cmp     eax, 1
0x180044bc7  jnz     short loc_180044BF9
0x180044bc9  mov     rax, [rbx]
0x180044bcc  mov     rcx, rbx
0x180044bcf  mov     rax, [rax]
0x180044bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bd7  mov     eax, esi
0x180044bd9  lock xadd [rbx+0Ch], eax
0x180044bde  cmp     eax, 1
0x180044be1  jnz     short loc_180044BF9
0x180044be3  mov     rax, [rbx]
0x180044be6  mov     rcx, rbx
0x180044be9  mov     rax, [rax+8]
0x180044bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bf2  jmp     short loc_180044BF9
0x180044bf4  mov     esi, 0FFFFFFFFh
0x180044bf9  mov     rax, [rdi]
0x180044bfc  mov     rcx, [rax+0D8h]
0x180044c03  test    rcx, rcx
0x180044c06  jnz     short loc_180044C0F
0x180044c08  mov     rcx, [rax+0E0h]; this
0x180044c0f  mov     rdx, [rdi+8]
0x180044c13  add     rdx, 0Ch; unsigned __int8 *
0x180044c17  mov     r8, r14; unsigned __int64
0x180044c1a  call    ?add_chunked_delimiters@chunked_encoding@details@http@web@@YA_KPEAE_K1@Z; web::http::details::chunked_encoding::add_chunked_delimiters(uchar *,unsigned __int64,unsigned __int64)
0x180044c1f  mov     r12, rax
0x180044c22  mov     rcx, [rdi+10h]
0x180044c26  cmp     qword ptr [rcx], 0
0x180044c2a  jnz     loc_180044D0C
0x180044c30  mov     rdx, [rdi]
0x180044c33  mov     rcx, [rdx+90h]
0x180044c3a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180044c3e  jz      loc_180044D0C
0x180044c44  test    r14, r14
0x180044c47  jnz     loc_180044D02
0x180044c4d  test    rcx, rcx
0x180044c50  jz      loc_180044D02
0x180044c56  lea     rdx, aUnexpectedEndO; "Unexpected end of request body stream e"...
0x180044c5d  lea     rcx, [rsp+168h+var_C8]
0x180044c65  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180044c6a  nop
0x180044c6b  xorps   xmm0, xmm0
0x180044c6e  movups  [rsp+168h+var_80], xmm0
0x180044c76  lea     rax, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x180044c7d  mov     [rsp+168h+var_88], rax
0x180044c85  mov     [rsp+168h+var_70], r13d
0x180044c8d  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180044c94  mov     [rsp+168h+var_68], rax
0x180044c9c  lea     rdx, [rsp+168h+var_C8]
0x180044ca4  lea     rcx, [rsp+168h+var_60]
0x180044cac  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x180044cb1  nop
0x180044cb2  lea     rcx, [rsp+168h+var_C8]; void *
0x180044cba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044cbf  lea     rdx, [rsp+168h+var_88]
0x180044cc7  mov     rcx, [rdi]
0x180044cca  call    ??$report_exception@Vhttp_exception@http@web@@@request_context@details@client@http@web@@QEAAXAEBVhttp_exception@34@@Z; web::http::client::details::request_context::report_exception<web::http::http_exception>(web::http::http_exception const &)
0x180044ccf  nop
0x180044cd0  lea     rcx, [rsp+168h+var_60]
0x180044cd8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180044cdd  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180044ce4  mov     [rsp+168h+var_88], rax
0x180044cec  lea     rcx, [rsp+168h+var_80]
0x180044cf4  call    _o___std_exception_destroy_0
0x180044cf9  nop
0x180044cfa  mov     rcx, r15
0x180044cfd  jmp     loc_1800450AD
0x180044d02  sub     rcx, r14
0x180044d05  mov     [rdx+90h], rcx
0x180044d0c  test    r14, r14
0x180044d0f  jnz     loc_180044F16
0x180044d15  mov     rax, [rdi]
0x180044d18  mov     [rax+88h], r13d
0x180044d1f  mov     rax, [rdi]
0x180044d22  mov     r8, [rax+0C0h]
0x180044d29  test    r8, r8
0x180044d2c  jz      loc_180044F16
0x180044d32  mov     r8, [r8+8]
0x180044d36  test    r8, r8
0x180044d39  jz      loc_1800450DF
0x180044d3f  mov     rdx, [r8+40h]
0x180044d43  mov     [r8+40h], r13
0x180044d47  mov     rcx, [r8+38h]
0x180044d4b  mov     [r8+38h], r13
0x180044d4f  mov     rax, [r8+30h]
0x180044d53  mov     [r8+30h], r13
0x180044d57  lea     r8, [rsp+168h+var_118]
0x180044d5c  mov     [rsp+168h+var_120], r8
0x180044d61  mov     [rsp+168h+var_108], r13
0x180044d66  mov     [rsp+168h+var_118+8], r13
0x180044d6b  mov     [rsp+168h+var_118], r13
0x180044d70  mov     [rsp+168h+Src], rax
0x180044d78  mov     [rsp+168h+var_A0], rcx
0x180044d80  mov     [rsp+168h+var_98], rdx
0x180044d88  mov     r8d, 1
0x180044d8e  lea     rdx, [rsp+168h+Src]
0x180044d96  lea     rcx, [rsp+168h+var_C8]
0x180044d9e  call    ??0?$container_buffer@V?$vector@EV?$allocator@E@std@@@std@@@streams@Concurrency@@QEAA@V?$vector@EV?$allocator@E@std@@@std@@H@Z; Concurrency::streams::container_buffer<std::vector<uchar>>::container_buffer<std::vector<uchar>>(std::vector<uchar>,int)
0x180044da3  mov     rdx, rax
0x180044da6  lea     rax, ??_7?$streambuf@E@streams@Concurrency@@6B@; const Concurrency::streams::streambuf<uchar>::`vftable'
0x180044dad  mov     [rsp+168h+var_F8], rax
0x180044db2  xorps   xmm0, xmm0
0x180044db5  movdqu  [rsp+168h+var_F0], xmm0
0x180044dbb  mov     rcx, [rdx+10h]
0x180044dbf  test    rcx, rcx
0x180044dc2  jz      short loc_180044DC8
0x180044dc4  lock inc dword ptr [rcx+8]
0x180044dc8  mov     rax, [rdx+8]
0x180044dcc  mov     qword ptr [rsp+168h+var_F0], rax
0x180044dd1  mov     rax, [rdx+10h]
0x180044dd5  mov     qword ptr [rsp+168h+var_F0+8], rax
0x180044ddd  lea     rdx, [rsp+168h+var_F8]
0x180044de2  lea     rcx, [rsp+168h+var_138]
0x180044de7  call    ??$?0E@?$basic_istream@E@streams@Concurrency@@QEAA@V?$streambuf@E@12@@Z; Concurrency::streams::basic_istream<uchar>::basic_istream<uchar>(Concurrency::streams::streambuf<uchar>)
0x180044dec  nop
0x180044ded  lea     rcx, [rsp+168h+var_C8]
0x180044df5  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x180044dfa  nop
0x180044dfb  mov     rax, [rsp+168h+var_118]
0x180044e00  test    rax, rax
0x180044e03  jz      short loc_180044E47
0x180044e05  mov     rdx, [rsp+168h+var_108]
0x180044e0a  sub     rdx, rax; struct std::nothrow_t *
0x180044e0d  cmp     rdx, 1000h
0x180044e14  jb      short loc_180044E31
0x180044e16  mov     rcx, [rax-8]
0x180044e1a  sub     rax, rcx
0x180044e1d  sub     rax, 8
0x180044e21  cmp     rax, 1Fh
0x180044e25  ja      loc_18004505A
0x180044e2b  add     rdx, 27h ; '''
0x180044e2f  jmp     short loc_180044E34
0x180044e31  mov     rcx, rax; void *
0x180044e34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180044e39  xorps   xmm0, xmm0
0x180044e3c  movdqu  xmmword ptr [rsp+168h+var_118], xmm0
0x180044e42  mov     [rsp+168h+var_108], r13
0x180044e47  mov     rdx, [rdi]
0x180044e4a  mov     rcx, [rsp+168h+var_130]
0x180044e4f  test    rcx, rcx
0x180044e52  jz      short loc_180044E5D
0x180044e54  lock inc dword ptr [rcx+8]
0x180044e58  mov     rcx, [rsp+168h+var_130]
0x180044e5d  mov     rax, [rsp+168h+var_138]
0x180044e62  mov     [rdx+0B0h], rax
0x180044e69  mov     rbx, [rdx+0B8h]
0x180044e70  mov     [rdx+0B8h], rcx
0x180044e77  test    rbx, rbx
0x180044e7a  jz      short loc_180044EB1
0x180044e7c  mov     eax, esi
0x180044e7e  lock xadd [rbx+8], eax
0x180044e83  cmp     eax, 1
0x180044e86  jnz     short loc_180044EB1
0x180044e88  mov     rax, [rbx]
0x180044e8b  mov     rcx, rbx
0x180044e8e  mov     rax, [rax]
0x180044e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e96  mov     eax, esi
0x180044e98  lock xadd [rbx+0Ch], eax
0x180044e9d  cmp     eax, 1
0x180044ea0  jnz     short loc_180044EB1
0x180044ea2  mov     rax, [rbx]
0x180044ea5  mov     rcx, rbx
0x180044ea8  mov     rax, [rax+8]
0x180044eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044eb1  mov     rbx, [rsp+168h+var_130]
0x180044eb6  test    rbx, rbx
0x180044eb9  jz      short loc_180044EF0
0x180044ebb  mov     eax, esi
0x180044ebd  lock xadd [rbx+8], eax
0x180044ec2  cmp     eax, 1
0x180044ec5  jnz     short loc_180044EF0
0x180044ec7  mov     rax, [rbx]
0x180044eca  mov     rcx, rbx
0x180044ecd  mov     rax, [rax]
0x180044ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ed5  mov     eax, esi
0x180044ed7  lock xadd [rbx+0Ch], eax
0x180044edc  cmp     eax, 1
0x180044edf  jnz     short loc_180044EF0
0x180044ee1  mov     rax, [rbx]
0x180044ee4  mov     rcx, rbx
0x180044ee7  mov     rax, [rax+8]
0x180044eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ef0  mov     rax, [rdi]
0x180044ef3  mov     rcx, [rax+0C0h]
0x180044efa  mov     [rax+0C0h], r13
0x180044f01  test    rcx, rcx
0x180044f04  jz      short loc_180044F16
0x180044f06  mov     rax, [rcx]
0x180044f09  mov     edx, 1
0x180044f0e  mov     rax, [rax]
0x180044f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f16  sub     r14, r12
0x180044f19  lea     r8, [r14+0Ch]; dwNumberOfBytesToWrite
0x180044f1d  mov     rcx, [rdi]
0x180044f20  mov     rax, [rcx+0D8h]
0x180044f27  test    rax, rax
0x180044f2a  jnz     short loc_180044F33
0x180044f2c  mov     rax, [rcx+0E0h]
0x180044f33  lea     rdx, [r12+rax]; lpBuffer
0x180044f37  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x180044f3a  mov     rcx, [rcx+68h]; hRequest
0x180044f3e  call    cs:__imp_WinHttpWriteData
0x180044f44  test    eax, eax
0x180044f46  jnz     loc_18004506A
0x180044f4c  call    cs:__imp_GetLastError
0x180044f52  mov     ebx, eax
0x180044f54  xorps   xmm0, xmm0
0x180044f57  movups  xmmword ptr [rsp+168h+var_C8], xmm0
0x180044f5f  mov     ecx, 20h ; ' '; Size
0x180044f64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044f69  mov     [rsp+168h+var_C8], rax
0x180044f71  mov     [rsp+168h+var_B8], 10h
0x180044f7d  mov     [rsp+168h+var_B0], 1Fh
0x180044f89  movups  xmm0, xmmword ptr cs:aWinhttpwriteda_0; "WinHttpWriteData"
0x180044f90  movups  xmmword ptr [rax], xmm0
0x180044f93  mov     byte ptr [rax+10h], 0
0x180044f97  lea     r8, [rsp+168h+var_C8]
0x180044f9f  mov     edx, ebx
0x180044fa1  lea     rcx, [rsp+168h+Src]; Src
0x180044fa9  call    web__http__client__details__build_error_msg
0x180044fae  nop
0x180044faf  mov     r8, rax
0x180044fb2  mov     edx, ebx
0x180044fb4  mov     rcx, [rdi]
0x180044fb7  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180044fbc  nop
0x180044fbd  mov     rdx, [rsp+168h+var_90]
0x180044fc5  cmp     rdx, 0Fh
0x180044fc9  jbe     short loc_180045005
0x180044fcb  mov     rax, [rsp+168h+Src]
0x180044fd3  inc     rdx; struct std::nothrow_t *
0x180044fd6  cmp     rdx, 1000h
0x180044fdd  jb      short loc_180044FFD
0x180044fdf  mov     rcx, [rax-8]
0x180044fe3  sub     rax, rcx
0x180044fe6  sub     rax, 8
0x180044fea  cmp     rax, 1Fh
0x180044fee  ja      short loc_180044FF6
0x180044ff0  add     rdx, 27h ; '''
0x180044ff4  jmp     short loc_180045000
0x180044ff6  mov     ecx, 5
0x180044ffb  int     29h; Win8: RtlFailFast(ecx)
0x180044ffd  mov     rcx, rax; void *
0x180045000  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180045005  mov     [rsp+168h+var_98], r13
0x18004500d  mov     [rsp+168h+var_90], 0Fh
0x180045019  mov     byte ptr [rsp+168h+Src], 0
0x180045021  mov     rdx, [rsp+168h+var_B0]
0x180045029  cmp     rdx, 0Fh
0x18004502d  jbe     short loc_18004506A
0x18004502f  mov     rax, [rsp+168h+var_C8]
  ... truncated ...
```
