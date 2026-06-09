# `web::http::client::details::winhttp_client::_transfer_encoding_chunked_write_data(web::http::client::details::winhttp_request_context *)'::`2'::_lambda_1_::operator()(pplx::task<unsigned __int64>)

- ea: `0x1800d4450`
- end: `0x1800d4a48`
- name: `??R_lambda_1_@?1??_transfer_encoding_chunked_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@3456@@Z@QEBA@V?$task@_K@pplx@@@Z`
- size: `1528`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800d67d0`
- `0x1800d7220`

## callees

- `0x180019000`
- `0x180019024`
- `0x180019508`
- `0x180019e4e`
- `0x180019ff4`
- `0x180020470`
- `0x1800223e0`
- `0x180024650`
- `0x180045f20`
- `0x180048b10`
- `0x18004c230`
- `0x180065d10`
- `0x180071be0`
- `0x1800bad10`
- `0x1800be450`
- `0x1800c73f0`
- `0x1800d4450`
- `0x1800d79d0`
- `0x1800e66dc`
- `0x1800e79d4`
- `0x1800e79e0`
- `0x180191010`

## import_xrefs

- `WINHTTP!WinHttpWriteData` at `0x1800d487e`
- `WINHTTP!WinHttpWriteData` at `0x1800d487e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d488c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d488c`

## string_xrefs

- `0x1800d48c9`: `WinHttpWriteData`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall `web::http::client::details::winhttp_client::_transfer_encoding_chunked_write_data'::`2'::_lambda_1_::operator()(
        void **a1,
        __int64 a2)
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
  __int64 v16; // rcx
  __int64 v17; // r8
  _QWORD *v18; // r8
  __int64 v19; // rdx
  void *v20; // rcx
  void *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  void *v24; // rcx
  void *v25; // rdx
  volatile signed __int32 *v26; // rcx
  volatile signed __int32 *v27; // rbx
  volatile signed __int32 *v28; // rbx
  void (__fastcall ***v29)(_QWORD, __int64); // rcx
  void *v30; // rcx
  __int64 v31; // rax
  DWORD LastError; // ebx
  __int64 v33; // r8
  void *v34; // rcx
  void *v35; // rcx
  volatile signed __int32 *v36; // rbx
  __int64 v37; // rax
  __int64 v38; // [rsp+30h] [rbp-138h] BYREF
  volatile signed __int32 *v39; // [rsp+38h] [rbp-130h]
  void **v40; // [rsp+48h] [rbp-120h]
  void *Block[2]; // [rsp+50h] [rbp-118h] BYREF
  __int64 v42; // [rsp+60h] [rbp-108h]
  __int64 v43; // [rsp+68h] [rbp-100h]
  void **v44; // [rsp+70h] [rbp-F8h] BYREF
  __int128 v45; // [rsp+78h] [rbp-F0h]
  _BYTE pExceptionObject[24]; // [rsp+88h] [rbp-E0h] BYREF
  void *v47[2]; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v48; // [rsp+B0h] [rbp-B8h]
  unsigned __int64 v49; // [rsp+B8h] [rbp-B0h]
  void *Src[2]; // [rsp+C0h] [rbp-A8h] BYREF
  __int64 v51; // [rsp+D0h] [rbp-98h]
  unsigned __int64 v52; // [rsp+D8h] [rbp-90h]
  void **v53; // [rsp+E0h] [rbp-88h] BYREF
  __int128 v54; // [rsp+E8h] [rbp-80h] BYREF
  int v55; // [rsp+F8h] [rbp-70h]
  void ***v56; // [rsp+100h] [rbp-68h]
  _BYTE v57[40]; // [rsp+108h] [rbp-60h] BYREF

  v40 = a1;
  v43 = a2;
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
             &v38,
             v8 + 10,
             v5);
      pplx::task<unsigned __int64>::wait(v9);
      v10 = v39;
      if ( v39 )
      {
        if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
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
    v37 = std::current_exception(&v38);
    web::http::client::details::request_context::report_exception(*v40, v37);
    v16 = v43;
    goto LABEL_61;
  }
  v14 = web::http::details::chunked_encoding::add_chunked_delimiters(v11, v12, v13, v4);
  if ( !*(_QWORD *)a1[2] )
  {
    v15 = *((_QWORD *)*a1 + 18);
    if ( v15 != -1 )
    {
      if ( !v5 && v15 )
      {
        std::wstring::wstring(v47, L"Unexpected end of request body stream encountered before expected length met.");
        v54 = 0;
        v53 = &web::http::http_exception::`vftable';
        v55 = 0;
        v56 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        utility::conversions::to_utf8string(v57, v47);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId((Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId *)v47);
        web::http::client::details::request_context::report_exception<web::http::http_exception>(*a1, &v53);
        std::string::~string(v57);
        v53 = &std::exception::`vftable';
        o___std_exception_destroy_0(&v54);
        v16 = a2;
LABEL_61:
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
      v40 = Block;
      v42 = 0;
      Block[1] = 0;
      Block[0] = 0;
      Src[0] = v21;
      Src[1] = v20;
      v51 = v19;
      v22 = Concurrency::streams::container_buffer<std::vector<unsigned char>>::container_buffer<std::vector<unsigned char>>(
              v47,
              Src,
              1);
      v44 = &Concurrency::streams::streambuf<unsigned char>::`vftable';
      v45 = 0;
      v23 = *(_QWORD *)(v22 + 16);
      if ( v23 )
        _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
      v45 = *(_OWORD *)(v22 + 8);
      Concurrency::streams::basic_istream<unsigned char>::basic_istream<unsigned char>(&v38, &v44);
      Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v47);
      if ( Block[0] )
      {
        if ( v42 - (unsigned __int64)Block[0] < 0x1000 )
        {
          v24 = Block[0];
        }
        else
        {
          v24 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v24 - 8) > 0x1F )
            goto LABEL_54;
        }
        operator delete(v24);
        *(_OWORD *)Block = 0;
        v42 = 0;
      }
      v25 = *a1;
      v26 = v39;
      if ( v39 )
      {
        _InterlockedIncrement(v39 + 2);
        v26 = v39;
      }
      *((_QWORD *)v25 + 22) = v38;
      v27 = (volatile signed __int32 *)*((_QWORD *)v25 + 23);
      *((_QWORD *)v25 + 23) = v26;
      if ( v27 )
      {
        if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
      }
      v28 = v39;
      if ( v39 )
      {
        if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
          if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        }
      }
      v29 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)*a1 + 24);
      *((_QWORD *)*a1 + 24) = 0;
      if ( v29 )
        (**v29)(v29, 1);
    }
  }
  v30 = *a1;
  v31 = *((_QWORD *)*a1 + 27);
  if ( !v31 )
    v31 = *((_QWORD *)v30 + 28);
  if ( !WinHttpWriteData(*((HINTERNET *)v30 + 13), (LPCVOID)(v14 + v31), v5 - v14 + 12, 0) )
  {
    LastError = GetLastError();
    *(_OWORD *)v47 = 0;
    v47[0] = operator new(0x20u);
    v48 = 16;
    v49 = 31;
    strcpy((char *)v47[0], "WinHttpWriteData");
    v33 = web::http::client::details::build_error_msg(Src);
    web::http::client::details::request_context::report_error(*a1, LastError, v33);
    if ( v52 > 0xF )
    {
      if ( v52 + 1 < 0x1000 )
      {
        v34 = Src[0];
      }
      else
      {
        v34 = (void *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v34 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v34);
    }
    v51 = 0;
    v52 = 15;
    LOBYTE(Src[0]) = 0;
    if ( v49 > 0xF )
    {
      if ( v49 + 1 < 0x1000 )
      {
        v35 = v47[0];
      }
      else
      {
        v35 = (void *)*((_QWORD *)v47[0] - 1);
        if ( (unsigned __int64)((char *)v47[0] - (char *)v35 - 8) > 0x1F )
LABEL_54:
          __fastfail(5u);
      }
      operator delete(v35);
    }
  }
  v36 = *(volatile signed __int32 **)(a2 + 8);
  if ( v36 )
  {
    if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
      if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
    }
  }
}

```

## disassembly

```asm
0x1800d4450  mov     [rsp+arg_10], rbx
0x1800d4455  mov     [rsp+arg_18], rsi
0x1800d445a  push    rdi
0x1800d445b  push    r12
0x1800d445d  push    r13
0x1800d445f  push    r14
0x1800d4461  push    r15
0x1800d4463  sub     rsp, 140h
0x1800d446a  mov     rax, cs:__security_cookie
0x1800d4471  xor     rax, rsp
0x1800d4474  mov     [rsp+168h+var_38], rax
0x1800d447c  mov     r15, rdx
0x1800d447f  mov     rdi, rcx
0x1800d4482  mov     [rsp+168h+var_120], rcx
0x1800d4487  mov     [rsp+168h+var_100], rdx
0x1800d448c  xor     r13d, r13d
0x1800d448f  mov     rcx, rdx
0x1800d4492  call    ?get@?$task@_K@pplx@@QEBA_KXZ; pplx::task<unsigned __int64>::get(void)
0x1800d4497  mov     r14, rax
0x1800d449a  mov     rcx, [rdi]
0x1800d449d  mov     r10, [rcx+0C0h]
0x1800d44a4  test    r10, r10
0x1800d44a7  jz      loc_1800D4534
0x1800d44ad  mov     rax, [rdi+10h]
0x1800d44b1  cmp     [rax], r13
0x1800d44b4  jnz     short loc_1800D4534
0x1800d44b6  mov     r8, [rcx+0D8h]
0x1800d44bd  test    r8, r8
0x1800d44c0  jnz     short loc_1800D44C9
0x1800d44c2  mov     r8, [rcx+0E0h]
0x1800d44c9  mov     rax, [r10]
0x1800d44cc  add     r8, 0Ah
0x1800d44d0  mov     r9, r14
0x1800d44d3  lea     rdx, [rsp+168h+var_138]
0x1800d44d8  mov     rcx, r10
0x1800d44db  mov     rax, [rax+70h]
0x1800d44df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d44e4  nop
0x1800d44e5  mov     rcx, rax
0x1800d44e8  call    ?wait@?$task@_K@pplx@@QEBA?AW4task_group_status@2@XZ; pplx::task<unsigned __int64>::wait(void)
0x1800d44ed  nop
0x1800d44ee  mov     rbx, [rsp+168h+var_130]
0x1800d44f3  test    rbx, rbx
0x1800d44f6  jz      short loc_1800D4534
0x1800d44f8  mov     esi, 0FFFFFFFFh
0x1800d44fd  mov     eax, esi
0x1800d44ff  lock xadd [rbx+8], eax
0x1800d4504  cmp     eax, 1
0x1800d4507  jnz     short loc_1800D4539
0x1800d4509  mov     rax, [rbx]
0x1800d450c  mov     rcx, rbx
0x1800d450f  mov     rax, [rax]
0x1800d4512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4517  mov     eax, esi
0x1800d4519  lock xadd [rbx+0Ch], eax
0x1800d451e  cmp     eax, 1
0x1800d4521  jnz     short loc_1800D4539
0x1800d4523  mov     rax, [rbx]
0x1800d4526  mov     rcx, rbx
0x1800d4529  mov     rax, [rax+8]
0x1800d452d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4532  jmp     short loc_1800D4539
0x1800d4534  mov     esi, 0FFFFFFFFh
0x1800d4539  mov     rax, [rdi]
0x1800d453c  mov     rcx, [rax+0D8h]
0x1800d4543  test    rcx, rcx
0x1800d4546  jnz     short loc_1800D454F
0x1800d4548  mov     rcx, [rax+0E0h]; this
0x1800d454f  mov     rdx, [rdi+8]
0x1800d4553  add     rdx, 0Ch; unsigned __int8 *
0x1800d4557  mov     r8, r14; unsigned __int64
0x1800d455a  call    ?add_chunked_delimiters@chunked_encoding@details@http@web@@YA_KPEAE_K1@Z; web::http::details::chunked_encoding::add_chunked_delimiters(uchar *,unsigned __int64,unsigned __int64)
0x1800d455f  mov     r12, rax
0x1800d4562  mov     rcx, [rdi+10h]
0x1800d4566  cmp     qword ptr [rcx], 0
0x1800d456a  jnz     loc_1800D464C
0x1800d4570  mov     rdx, [rdi]
0x1800d4573  mov     rcx, [rdx+90h]
0x1800d457a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800d457e  jz      loc_1800D464C
0x1800d4584  test    r14, r14
0x1800d4587  jnz     loc_1800D4642
0x1800d458d  test    rcx, rcx
0x1800d4590  jz      loc_1800D4642
0x1800d4596  lea     rdx, aUnexpectedEndO; "Unexpected end of request body stream e"...
0x1800d459d  lea     rcx, [rsp+168h+var_C8]
0x1800d45a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d45aa  nop
0x1800d45ab  xorps   xmm0, xmm0
0x1800d45ae  movups  [rsp+168h+var_80], xmm0
0x1800d45b6  lea     rax, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x1800d45bd  mov     [rsp+168h+var_88], rax
0x1800d45c5  mov     [rsp+168h+var_70], r13d
0x1800d45cd  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1800d45d4  mov     [rsp+168h+var_68], rax
0x1800d45dc  lea     rdx, [rsp+168h+var_C8]
0x1800d45e4  lea     rcx, [rsp+168h+var_60]
0x1800d45ec  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x1800d45f1  nop
0x1800d45f2  lea     rcx, [rsp+168h+var_C8]; this
0x1800d45fa  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x1800d45ff  lea     rdx, [rsp+168h+var_88]
0x1800d4607  mov     rcx, [rdi]
0x1800d460a  call    ??$report_exception@Vhttp_exception@http@web@@@request_context@details@client@http@web@@QEAAXAEBVhttp_exception@34@@Z; web::http::client::details::request_context::report_exception<web::http::http_exception>(web::http::http_exception const &)
0x1800d460f  nop
0x1800d4610  lea     rcx, [rsp+168h+var_60]
0x1800d4618  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800d461d  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800d4624  mov     [rsp+168h+var_88], rax
0x1800d462c  lea     rcx, [rsp+168h+var_80]
0x1800d4634  call    _o___std_exception_destroy_0
0x1800d4639  nop
0x1800d463a  mov     rcx, r15
0x1800d463d  jmp     loc_1800D49ED
0x1800d4642  sub     rcx, r14
0x1800d4645  mov     [rdx+90h], rcx
0x1800d464c  test    r14, r14
0x1800d464f  jnz     loc_1800D4856
0x1800d4655  mov     rax, [rdi]
0x1800d4658  mov     [rax+88h], r13d
0x1800d465f  mov     rax, [rdi]
0x1800d4662  mov     r8, [rax+0C0h]
0x1800d4669  test    r8, r8
0x1800d466c  jz      loc_1800D4856
0x1800d4672  mov     r8, [r8+8]
0x1800d4676  test    r8, r8
0x1800d4679  jz      loc_1800D4A1F
0x1800d467f  mov     rdx, [r8+40h]
0x1800d4683  mov     [r8+40h], r13
0x1800d4687  mov     rcx, [r8+38h]
0x1800d468b  mov     [r8+38h], r13
0x1800d468f  mov     rax, [r8+30h]
0x1800d4693  mov     [r8+30h], r13
0x1800d4697  lea     r8, [rsp+168h+Block]
0x1800d469c  mov     [rsp+168h+var_120], r8
0x1800d46a1  mov     [rsp+168h+var_108], r13
0x1800d46a6  mov     [rsp+168h+Block+8], r13
0x1800d46ab  mov     [rsp+168h+Block], r13
0x1800d46b0  mov     [rsp+168h+Src], rax
0x1800d46b8  mov     [rsp+168h+var_A0], rcx
0x1800d46c0  mov     [rsp+168h+var_98], rdx
0x1800d46c8  mov     r8d, 1
0x1800d46ce  lea     rdx, [rsp+168h+Src]
0x1800d46d6  lea     rcx, [rsp+168h+var_C8]
0x1800d46de  call    ??0?$container_buffer@V?$vector@EV?$allocator@E@std@@@std@@@streams@Concurrency@@QEAA@V?$vector@EV?$allocator@E@std@@@std@@H@Z; Concurrency::streams::container_buffer<std::vector<uchar>>::container_buffer<std::vector<uchar>>(std::vector<uchar>,int)
0x1800d46e3  mov     rdx, rax
0x1800d46e6  lea     rax, ??_7?$streambuf@E@streams@Concurrency@@6B@; const Concurrency::streams::streambuf<uchar>::`vftable'
0x1800d46ed  mov     [rsp+168h+var_F8], rax
0x1800d46f2  xorps   xmm0, xmm0
0x1800d46f5  movdqu  [rsp+168h+var_F0], xmm0
0x1800d46fb  mov     rcx, [rdx+10h]
0x1800d46ff  test    rcx, rcx
0x1800d4702  jz      short loc_1800D4708
0x1800d4704  lock inc dword ptr [rcx+8]
0x1800d4708  mov     rax, [rdx+8]
0x1800d470c  mov     qword ptr [rsp+168h+var_F0], rax
0x1800d4711  mov     rax, [rdx+10h]
0x1800d4715  mov     qword ptr [rsp+168h+var_F0+8], rax
0x1800d471d  lea     rdx, [rsp+168h+var_F8]
0x1800d4722  lea     rcx, [rsp+168h+var_138]
0x1800d4727  call    ??$?0E@?$basic_istream@E@streams@Concurrency@@QEAA@V?$streambuf@E@12@@Z; Concurrency::streams::basic_istream<uchar>::basic_istream<uchar>(Concurrency::streams::streambuf<uchar>)
0x1800d472c  nop
0x1800d472d  lea     rcx, [rsp+168h+var_C8]
0x1800d4735  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x1800d473a  nop
0x1800d473b  mov     rax, [rsp+168h+Block]
0x1800d4740  test    rax, rax
0x1800d4743  jz      short loc_1800D4787
0x1800d4745  mov     rdx, [rsp+168h+var_108]
0x1800d474a  sub     rdx, rax
0x1800d474d  cmp     rdx, 1000h
0x1800d4754  jb      short loc_1800D4771
0x1800d4756  mov     rcx, [rax-8]
0x1800d475a  sub     rax, rcx
0x1800d475d  sub     rax, 8
0x1800d4761  cmp     rax, 1Fh
0x1800d4765  ja      loc_1800D499A
0x1800d476b  add     rdx, 27h ; '''
0x1800d476f  jmp     short loc_1800D4774
0x1800d4771  mov     rcx, rax; Block
0x1800d4774  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d4779  xorps   xmm0, xmm0
0x1800d477c  movdqu  xmmword ptr [rsp+168h+Block], xmm0
0x1800d4782  mov     [rsp+168h+var_108], r13
0x1800d4787  mov     rdx, [rdi]
0x1800d478a  mov     rcx, [rsp+168h+var_130]
0x1800d478f  test    rcx, rcx
0x1800d4792  jz      short loc_1800D479D
0x1800d4794  lock inc dword ptr [rcx+8]
0x1800d4798  mov     rcx, [rsp+168h+var_130]
0x1800d479d  mov     rax, [rsp+168h+var_138]
0x1800d47a2  mov     [rdx+0B0h], rax
0x1800d47a9  mov     rbx, [rdx+0B8h]
0x1800d47b0  mov     [rdx+0B8h], rcx
0x1800d47b7  test    rbx, rbx
0x1800d47ba  jz      short loc_1800D47F1
0x1800d47bc  mov     eax, esi
0x1800d47be  lock xadd [rbx+8], eax
0x1800d47c3  cmp     eax, 1
0x1800d47c6  jnz     short loc_1800D47F1
0x1800d47c8  mov     rax, [rbx]
0x1800d47cb  mov     rcx, rbx
0x1800d47ce  mov     rax, [rax]
0x1800d47d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d47d6  mov     eax, esi
0x1800d47d8  lock xadd [rbx+0Ch], eax
0x1800d47dd  cmp     eax, 1
0x1800d47e0  jnz     short loc_1800D47F1
0x1800d47e2  mov     rax, [rbx]
0x1800d47e5  mov     rcx, rbx
0x1800d47e8  mov     rax, [rax+8]
0x1800d47ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d47f1  mov     rbx, [rsp+168h+var_130]
0x1800d47f6  test    rbx, rbx
0x1800d47f9  jz      short loc_1800D4830
0x1800d47fb  mov     eax, esi
0x1800d47fd  lock xadd [rbx+8], eax
0x1800d4802  cmp     eax, 1
0x1800d4805  jnz     short loc_1800D4830
0x1800d4807  mov     rax, [rbx]
0x1800d480a  mov     rcx, rbx
0x1800d480d  mov     rax, [rax]
0x1800d4810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4815  mov     eax, esi
0x1800d4817  lock xadd [rbx+0Ch], eax
0x1800d481c  cmp     eax, 1
0x1800d481f  jnz     short loc_1800D4830
0x1800d4821  mov     rax, [rbx]
0x1800d4824  mov     rcx, rbx
0x1800d4827  mov     rax, [rax+8]
0x1800d482b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4830  mov     rax, [rdi]
0x1800d4833  mov     rcx, [rax+0C0h]
0x1800d483a  mov     [rax+0C0h], r13
0x1800d4841  test    rcx, rcx
0x1800d4844  jz      short loc_1800D4856
0x1800d4846  mov     rax, [rcx]
0x1800d4849  mov     edx, 1
0x1800d484e  mov     rax, [rax]
0x1800d4851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4856  sub     r14, r12
0x1800d4859  lea     r8, [r14+0Ch]; dwNumberOfBytesToWrite
0x1800d485d  mov     rcx, [rdi]
0x1800d4860  mov     rax, [rcx+0D8h]
0x1800d4867  test    rax, rax
0x1800d486a  jnz     short loc_1800D4873
0x1800d486c  mov     rax, [rcx+0E0h]
0x1800d4873  lea     rdx, [r12+rax]; lpBuffer
0x1800d4877  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x1800d487a  mov     rcx, [rcx+68h]; hRequest
0x1800d487e  call    cs:__imp_WinHttpWriteData
0x1800d4884  test    eax, eax
0x1800d4886  jnz     loc_1800D49AA
0x1800d488c  call    cs:__imp_GetLastError
0x1800d4892  mov     ebx, eax
0x1800d4894  xorps   xmm0, xmm0
0x1800d4897  movups  xmmword ptr [rsp+168h+var_C8], xmm0
0x1800d489f  mov     ecx, 20h ; ' '; Size
0x1800d48a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d48a9  mov     [rsp+168h+var_C8], rax
0x1800d48b1  mov     [rsp+168h+var_B8], 10h
0x1800d48bd  mov     [rsp+168h+var_B0], 1Fh
0x1800d48c9  movups  xmm0, xmmword ptr cs:aWinhttpwriteda; "WinHttpWriteData"
0x1800d48d0  movups  xmmword ptr [rax], xmm0
0x1800d48d3  mov     byte ptr [rax+10h], 0
0x1800d48d7  lea     r8, [rsp+168h+var_C8]
0x1800d48df  mov     edx, ebx
0x1800d48e1  lea     rcx, [rsp+168h+Src]; Src
0x1800d48e9  call    web__http__client__details__build_error_msg
0x1800d48ee  nop
0x1800d48ef  mov     r8, rax
0x1800d48f2  mov     edx, ebx
0x1800d48f4  mov     rcx, [rdi]
0x1800d48f7  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x1800d48fc  nop
0x1800d48fd  mov     rdx, [rsp+168h+var_90]
0x1800d4905  cmp     rdx, 0Fh
0x1800d4909  jbe     short loc_1800D4945
0x1800d490b  mov     rax, [rsp+168h+Src]
0x1800d4913  inc     rdx
0x1800d4916  cmp     rdx, 1000h
0x1800d491d  jb      short loc_1800D493D
0x1800d491f  mov     rcx, [rax-8]
0x1800d4923  sub     rax, rcx
0x1800d4926  sub     rax, 8
0x1800d492a  cmp     rax, 1Fh
0x1800d492e  ja      short loc_1800D4936
0x1800d4930  add     rdx, 27h ; '''
0x1800d4934  jmp     short loc_1800D4940
0x1800d4936  mov     ecx, 5
0x1800d493b  int     29h; Win8: RtlFailFast(ecx)
0x1800d493d  mov     rcx, rax; Block
0x1800d4940  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d4945  mov     [rsp+168h+var_98], r13
0x1800d494d  mov     [rsp+168h+var_90], 0Fh
0x1800d4959  mov     byte ptr [rsp+168h+Src], 0
0x1800d4961  mov     rdx, [rsp+168h+var_B0]
0x1800d4969  cmp     rdx, 0Fh
0x1800d496d  jbe     short loc_1800D49AA
0x1800d496f  mov     rax, [rsp+168h+var_C8]
  ... truncated ...
```
