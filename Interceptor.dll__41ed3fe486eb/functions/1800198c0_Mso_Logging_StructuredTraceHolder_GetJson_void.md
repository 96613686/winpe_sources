# Mso::Logging::StructuredTraceHolder::GetJson(void)

- ea: `0x1800198c0`
- end: `0x180019f1a`
- name: `?GetJson@StructuredTraceHolder@Logging@Mso@@UEAAPEB_WXZ`
- size: `1626`
- prototype: `const wchar_t *__fastcall(Mso::Logging::StructuredTraceHolder *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800041d4`
- `0x1800045ec`
- `0x18000465c`
- `0x18000a580`
- `0x180012318`
- `0x1800129fc`
- `0x180012b18`
- `0x180013e24`
- `0x180013fb0`
- `0x180019830`
- `0x1800198c0`
- `0x18001bed0`
- `0x1800266e0`
- `0x1800282a0`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180019a52`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180019bc4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180019e2b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180019a52`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180019bc4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180019e2b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180019bcb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180019e32`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180019bcb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180019e32`

## string_xrefs

- `0x180019dbe`: `structuredTraceAsJson length is larger than MAX_TRACE_MESSAGE_LENGTH.`
- `0x180019ef1`: `StructuredTraceJsonSerializer::GetResult failed to get serialized result.`
- `0x180019eb5`: `StructuredTraceJsonSerializer::EndObject failed to write EndObject token.`
- `0x180019e79`: `StructuredTraceJsonSerializer::StartObject failed to write StartObject token.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
const wchar_t *__fastcall Mso::Logging::StructuredTraceHolder::GetJson(Mso::Logging::StructuredTraceHolder *this)
{
  Mso::Logging::StructuredTraceHolder *v1; // r14
  Mso::Logging::StructuredTraceHolder *v2; // r13
  void **v3; // rsi
  _WORD *v4; // rax
  char v5; // r15
  __int64 v6; // r12
  __int64 v7; // rbx
  __int64 v8; // rcx
  void ***v9; // rbx
  void *v10; // rcx
  void *v11; // rcx
  void ***v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v16; // rax
  void ***v17; // [rsp+30h] [rbp-168h] BYREF
  void ***v18; // [rsp+38h] [rbp-160h] BYREF
  void ***v19; // [rsp+40h] [rbp-158h]
  void ***v20; // [rsp+48h] [rbp-150h] BYREF
  void **v21; // [rsp+50h] [rbp-148h] BYREF
  void ****v22; // [rsp+58h] [rbp-140h]
  void ****v23; // [rsp+60h] [rbp-138h]
  Mso::Logging::StructuredTraceHolder *v24; // [rsp+68h] [rbp-130h]
  void **v25; // [rsp+70h] [rbp-128h]
  const std::runtime_error *v26; // [rsp+78h] [rbp-120h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+80h] [rbp-118h] BYREF
  _BYTE v28[24]; // [rsp+98h] [rbp-100h] BYREF
  _BYTE v29[24]; // [rsp+B0h] [rbp-E8h] BYREF
  __int64 v30; // [rsp+C8h] [rbp-D0h] BYREF
  int v31; // [rsp+D0h] [rbp-C8h]
  void *Src[2]; // [rsp+D8h] [rbp-C0h] BYREF
  __int128 v33; // [rsp+E8h] [rbp-B0h]
  void *Block[2]; // [rsp+F8h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+108h] [rbp-90h]
  void **v36; // [rsp+120h] [rbp-78h] BYREF
  const char *v37; // [rsp+128h] [rbp-70h]
  __int64 *v38; // [rsp+130h] [rbp-68h]
  __int16 v39; // [rsp+138h] [rbp-60h]
  __int128 v40; // [rsp+140h] [rbp-58h] BYREF
  __int64 v41; // [rsp+150h] [rbp-48h]
  __int64 v42; // [rsp+158h] [rbp-40h]

  v1 = this;
  v2 = this;
  v24 = this;
  LODWORD(v17) = 0;
  v3 = (void **)((char *)this + 56);
  v25 = (void **)((char *)this + 56);
  if ( !Mso::Logging::StructuredTraceHolder::IsValid(this) || v3[2] )
  {
    if ( (unsigned __int64)v3[3] > 7 )
      return (const wchar_t *)*v3;
    return (const wchar_t *)v3;
  }
  v4 = (_WORD *)*((_QWORD *)v1 + 2);
  if ( !v4 || (v5 = 1, !*v4) )
    v5 = 0;
  v6 = *((_QWORD *)v1 + 6);
  *(_OWORD *)Src = 0;
  *(_QWORD *)&v33 = 0;
  *((_QWORD *)&v33 + 1) = 7;
  LOWORD(Src[0]) = 0;
  v7 = -1;
  if ( v5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v4[v8] );
  }
  else
  {
    v8 = 0;
  }
  if ( (unsigned __int64)(v8 + 50 * v6) > 7 )
  {
    _mm_lfence();
    ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_K_Z___V___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(Src);
    *(_QWORD *)&v33 = 0;
  }
  if ( v5 )
  {
    do
      ++v7;
    while ( *(_WORD *)(*((_QWORD *)v1 + 2) + 2 * v7) );
    std::wstring::append(Src);
  }
  if ( v6 )
  {
    LODWORD(v17) = 1;
    Mso::Make<Mso::Json::Unicode::StringWriter,Mso::Json::IJsonWriter,enum Mso::Json::PrettyPrint>(&v20, &v17);
    v9 = v20;
    if ( !v20 )
    {
      if ( (unsigned __int64)v3[3] > 7 )
        v3 = (void **)*v3;
      if ( *((_QWORD *)&v33 + 1) > 7u )
      {
        v10 = Src[0];
        if ( (unsigned __int64)(2LL * *((_QWORD *)&v33 + 1) + 2) >= 0x1000 )
        {
          v10 = (void *)*((_QWORD *)Src[0] - 1);
          if ( (unsigned __int64)((char *)Src[0] - (char *)v10 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
LABEL_59:
        free(v10);
        return (const wchar_t *)v3;
      }
      return (const wchar_t *)v3;
    }
    v18 = (void ***)&Mso::Logging::StructuredTraceJsonSerializer::`vftable';
    v19 = v20;
    ((void (__fastcall *)(void ***))**v20)(v20);
    if ( !v19 )
      CrashWithRecovery(0x1E3C3840u, 0);
    if ( !((unsigned __int8 (__fastcall *)(void ***))(*v19)[2])(v19) )
    {
      std::runtime_error::runtime_error(
        (std::runtime_error *)pExceptionObject,
        "StructuredTraceJsonSerializer::StartObject failed to write StartObject token.");
      throw (std::runtime_error *)pExceptionObject;
    }
    (***((void (__fastcall ****)(_QWORD, void ****))v1 + 3))(*((_QWORD *)v1 + 3), &v18);
    if ( !v19 )
      CrashWithRecovery(0x1E3C3840u, 0);
    if ( !((unsigned __int8 (__fastcall *)(void ***))(*v19)[3])(v19) )
    {
      std::runtime_error::runtime_error(
        (std::runtime_error *)v28,
        "StructuredTraceJsonSerializer::EndObject failed to write EndObject token.");
      throw (std::runtime_error *)v28;
    }
    if ( v5 )
      std::wstring::append(Src);
    try
    {
      *(_OWORD *)Block = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(Block[0]) = 0;
      LODWORD(v17) = 1;
      if ( !v19 )
        CrashWithRecovery(0x1E3C3840u, 0);
      if ( !((unsigned __int8 (__fastcall *)(void ***, void **))(*v19)[15])(v19, Block) )
      {
        std::runtime_error::runtime_error(
          (std::runtime_error *)v29,
          "StructuredTraceJsonSerializer::GetResult failed to get serialized result.");
        throw (std::runtime_error *)v29;
      }
      std::wstring::append(Src);
      if ( si128.m128i_i64[1] > 7uLL )
      {
        v11 = Block[0];
        if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
        {
          v11 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v11 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v11);
      }
    }
    catch ( const std::runtime_error *v26 )
    {
      v16 = (*(__int64 (__fastcall **)(const std::runtime_error *))(*(_QWORD *)v26 + 8LL))(v26);
      v36 = &Mso::Diagnostics::ClassifiedStructuredObject<char const *>::`vftable';
      v37 = "ExceptionMessage";
      v38 = (__int64 *)v16;
      v39 = 4;
      v40 = 0;
      v41 = 0;
      v42 = 7;
      LOWORD(v40) = 0;
      if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(507602384, 138, 10, 2) )
      {
        v17 = &v36;
        v21 = &Mso::Logging::CompositeStructuredTrace::`vftable';
        v22 = &v17;
        v23 = &v18;
        Mso::Logging::MsoSendStructuredTraceTag(507602384, 138, 10);
      }
      std::wstring::_Tidy_deallocate(&v40);
      v9 = v20;
      v2 = v24;
      v3 = v25;
      v1 = v24;
    }
    v12 = v19;
    if ( v19 )
    {
      v19 = 0;
      ((void (__fastcall *)(void ***))(*v12)[1])(v12);
    }
    ((void (__fastcall *)(void ***))(*v9)[1])(v9);
  }
  if ( v3 != Src )
  {
    std::wstring::_Tidy_deallocate(v3);
    *(_OWORD *)v3 = *(_OWORD *)Src;
    *((_OWORD *)v3 + 1) = v33;
    *(_QWORD *)&v33 = 0;
    *((_QWORD *)&v33 + 1) = 7;
    LOWORD(Src[0]) = 0;
  }
  if ( *((_QWORD *)v2 + 9) > 0xE000u )
  {
    v13 = *((unsigned int *)v1 + 2);
    v30 = 0;
    v31 = 0;
    if ( (unsigned int)v13 > 0xFFFF )
    {
      if ( BYTE3(v13) < 0x24u )
      {
        TaggingUtilities::FiveCharTagToString<wchar_t>(v13, &v30);
      }
      else
      {
        LOWORD(v30) = BYTE3(v13);
        WORD1(v30) = BYTE2(v13);
        WORD2(v30) = BYTE1(v13);
        HIWORD(v30) = (unsigned __int8)v13;
        LOWORD(v31) = 0;
      }
    }
    else
    {
      TaggingUtilities::NumericTagToString<wchar_t>(v13, &v30);
    }
    v36 = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
    v37 = (const char *)L"Tag";
    v38 = &v30;
    v39 = 0;
    v14 = *((_DWORD *)v2 + 18);
    v21 = &Mso::Logging::StructuredObject<unsigned int,1>::`vftable';
    v22 = (void ****)L"Length";
    LODWORD(v23) = v14;
    WORD2(v23) = 0;
    if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(8249345, 138, 15, 0) )
    {
      v18 = &v21;
      v19 = &v36;
      Block[0] = &Mso::Logging::CompositeStructuredTrace::`vftable';
      Block[1] = &v18;
      si128.m128i_i64[0] = (__int64)&v20;
      Mso::Logging::MsoSendStructuredTraceTag(
        8249345,
        138,
        15,
        0,
        L"structuredTraceAsJson length is larger than MAX_TRACE_MESSAGE_LENGTH.",
        Block);
    }
  }
  if ( (unsigned __int64)v3[3] > 7 )
    v3 = (void **)*v3;
  if ( *((_QWORD *)&v33 + 1) > 7u )
  {
    v10 = Src[0];
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v33 + 1) + 2) >= 0x1000 )
    {
      v10 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v10 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    goto LABEL_59;
  }
  return (const wchar_t *)v3;
}

```

## disassembly

```asm
0x1800198c0  mov     [rsp+arg_8], rbx
0x1800198c5  mov     [rsp+arg_10], rsi
0x1800198ca  push    rdi
0x1800198cb  push    r12
0x1800198cd  push    r13
0x1800198cf  push    r14
0x1800198d1  push    r15
0x1800198d3  sub     rsp, 170h
0x1800198da  mov     rax, cs:__security_cookie
0x1800198e1  xor     rax, rsp
0x1800198e4  mov     [rsp+198h+var_38], rax
0x1800198ec  mov     r14, rcx
0x1800198ef  mov     r13, rcx
0x1800198f2  mov     [rsp+198h+var_130], rcx
0x1800198f7  xor     edi, edi
0x1800198f9  mov     dword ptr [rsp+198h+var_168], edi
0x1800198fd  lea     rsi, [rcx+38h]
0x180019901  mov     [rsp+198h+var_128], rsi
0x180019906  call    ?IsValid@StructuredTraceHolder@Logging@Mso@@UEAA_NXZ; Mso::Logging::StructuredTraceHolder::IsValid(void)
0x18001990b  test    al, al
0x18001990d  jnz     short loc_180019922
0x18001990f  cmp     qword ptr [rsi+18h], 7
0x180019914  jbe     loc_180019E38
0x18001991a  mov     rsi, [rsi]
0x18001991d  jmp     loc_180019E38
0x180019922  cmp     [rsi+10h], rdi
0x180019926  jnz     short loc_18001990F
0x180019928  mov     rax, [r14+10h]
0x18001992c  test    rax, rax
0x18001992f  jz      short loc_180019939
0x180019931  cmp     [rax], di
0x180019934  mov     r15b, 1
0x180019937  jnz     short loc_18001993C
0x180019939  mov     r15b, dil
0x18001993c  mov     r12, [r14+30h]
0x180019940  xorps   xmm0, xmm0
0x180019943  movups  xmmword ptr [rsp+198h+Src], xmm0
0x18001994b  mov     qword ptr [rsp+198h+var_B0], rdi
0x180019953  mov     qword ptr [rsp+198h+var_B0+8], 7
0x18001995f  mov     word ptr [rsp+198h+Src], di
0x180019967  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001996b  test    r15b, r15b
0x18001996e  jz      short loc_18001997E
0x180019970  mov     rcx, rbx
0x180019973  inc     rcx
0x180019976  cmp     [rax+rcx*2], di
0x18001997a  jnz     short loc_180019973
0x18001997c  jmp     short loc_180019981
0x18001997e  mov     rcx, rdi
0x180019981  imul    rdx, r12, 32h ; '2'
0x180019985  add     rdx, rcx
0x180019988  cmp     rdx, 7
0x18001998c  jbe     short loc_1800199A6
0x18001998e  lfence
0x180019991  lea     rcx, [rsp+198h+Src]; Src
0x180019999  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x18001999e  mov     qword ptr [rsp+198h+var_B0], rdi
0x1800199a6  test    r15b, r15b
0x1800199a9  jz      short loc_1800199C8
0x1800199ab  mov     rdx, [r14+10h]
0x1800199af  inc     rbx
0x1800199b2  cmp     [rdx+rbx*2], di
0x1800199b6  jnz     short loc_1800199AF
0x1800199b8  mov     r8, rbx
0x1800199bb  lea     rcx, [rsp+198h+Src]; Src
0x1800199c3  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800199c8  test    r12, r12
0x1800199cb  jz      loc_180019C15
0x1800199d1  mov     dword ptr [rsp+198h+var_168], 1
0x1800199d9  lea     rdx, [rsp+198h+var_168]
0x1800199de  lea     rcx, [rsp+198h+var_150]
0x1800199e3  call    ??$Make@VStringWriter@Unicode@Json@Mso@@UIJsonWriter@34@W4PrettyPrint@34@@Mso@@YA?AV?$TCntPtr@UIJsonWriter@Json@Mso@@@0@$$QEAW4PrettyPrint@Json@0@@Z; Mso::Make<Mso::Json::Unicode::StringWriter,Mso::Json::IJsonWriter,Mso::Json::PrettyPrint>(Mso::Json::PrettyPrint &&)
0x1800199e8  nop
0x1800199e9  mov     rbx, [rsp+198h+var_150]
0x1800199ee  test    rbx, rbx
0x1800199f1  jnz     short loc_180019A59
0x1800199f3  cmp     qword ptr [rsi+18h], 7
0x1800199f8  jbe     short loc_1800199FD
0x1800199fa  mov     rsi, [rsi]
0x1800199fd  mov     rax, qword ptr [rsp+198h+var_B0+8]
0x180019a05  cmp     rax, 7
0x180019a09  jbe     loc_180019E38
0x180019a0f  mov     rcx, [rsp+198h+Src]; Block
0x180019a17  mov     rdx, rcx
0x180019a1a  lea     rax, ds:2[rax*2]
0x180019a22  cmp     rax, 1000h
0x180019a28  jb      loc_180019E32
0x180019a2e  mov     rcx, [rcx-8]
0x180019a32  sub     rdx, rcx
0x180019a35  lea     rax, [rdx-8]
0x180019a39  cmp     rax, 1Fh
0x180019a3d  jbe     loc_180019E32
0x180019a43  mov     [rsp+198h+Reserved], rdi; Reserved
0x180019a48  xor     r9d, r9d; LineNo
0x180019a4b  xor     r8d, r8d; FileName
0x180019a4e  xor     edx, edx; FunctionName
0x180019a50  xor     ecx, ecx; Expression
0x180019a52  call    cs:__imp__invoke_watson
0x180019a59  lea     rax, ??_7StructuredTraceJsonSerializer@Logging@Mso@@6B@; const Mso::Logging::StructuredTraceJsonSerializer::`vftable'
0x180019a60  mov     [rsp+198h+var_160], rax
0x180019a65  mov     [rsp+198h+var_158], rbx
0x180019a6a  mov     rax, [rbx]
0x180019a6d  mov     rcx, rbx
0x180019a70  mov     rax, [rax]
0x180019a73  call    cs:__guard_dispatch_icall_fptr
0x180019a79  mov     rcx, [rsp+198h+var_158]
0x180019a7e  test    rcx, rcx
0x180019a81  jz      loc_180019E68
0x180019a87  mov     rax, [rcx]
0x180019a8a  mov     rax, [rax+10h]
0x180019a8e  call    cs:__guard_dispatch_icall_fptr
0x180019a94  test    al, al
0x180019a96  jz      loc_180019E79
0x180019a9c  mov     rcx, [r14+18h]
0x180019aa0  mov     rax, [rcx]
0x180019aa3  lea     rdx, [rsp+198h+var_160]
0x180019aa8  mov     rax, [rax]
0x180019aab  call    cs:__guard_dispatch_icall_fptr
0x180019ab1  mov     rcx, [rsp+198h+var_158]
0x180019ab6  test    rcx, rcx
0x180019ab9  jz      loc_180019EA5
0x180019abf  mov     rax, [rcx]
0x180019ac2  mov     rax, [rax+18h]
0x180019ac6  call    cs:__guard_dispatch_icall_fptr
0x180019acc  test    al, al
0x180019ace  jz      loc_180019EB5
0x180019ad4  test    r15b, r15b
0x180019ad7  jz      short loc_180019AF4
0x180019ad9  mov     r8d, 1
0x180019adf  lea     rdx, asc_180032928; " "
0x180019ae6  lea     rcx, [rsp+198h+Src]; Src
0x180019aee  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180019af3  nop
0x180019af4  xorps   xmm0, xmm0
0x180019af7  movups  xmmword ptr [rsp+198h+Block], xmm0
0x180019aff  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180019b07  movdqu  [rsp+198h+var_90], xmm1
0x180019b10  mov     word ptr [rsp+198h+Block], di
0x180019b18  mov     dword ptr [rsp+198h+var_168], 1
0x180019b20  mov     rcx, [rsp+198h+var_158]
0x180019b25  test    rcx, rcx
0x180019b28  jz      loc_180019EE1
0x180019b2e  mov     rax, [rcx]
0x180019b31  lea     rdx, [rsp+198h+Block]
0x180019b39  mov     rax, [rax+78h]
0x180019b3d  call    cs:__guard_dispatch_icall_fptr
0x180019b43  test    al, al
0x180019b45  jz      loc_180019EF1
0x180019b4b  lea     rdx, [rsp+198h+Block]
0x180019b53  cmp     qword ptr [rsp+198h+var_90+8], 7
0x180019b5c  cmova   rdx, [rsp+198h+Block]
0x180019b65  mov     r8, qword ptr [rsp+198h+var_90]
0x180019b6d  lea     rcx, [rsp+198h+Src]; Src
0x180019b75  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180019b7a  nop
0x180019b7b  mov     rax, qword ptr [rsp+198h+var_90+8]
0x180019b83  cmp     rax, 7
0x180019b87  jbe     short loc_180019BD2
0x180019b89  mov     rcx, [rsp+198h+Block]; Block
0x180019b91  mov     rdx, rcx
0x180019b94  lea     rax, ds:2[rax*2]
0x180019b9c  cmp     rax, 1000h
0x180019ba2  jb      short loc_180019BCB
0x180019ba4  mov     rcx, [rcx-8]
0x180019ba8  sub     rdx, rcx
0x180019bab  lea     rax, [rdx-8]
0x180019baf  cmp     rax, 1Fh
0x180019bb3  jbe     short loc_180019BCB
0x180019bb5  mov     [rsp+198h+Reserved], rdi; Reserved
0x180019bba  xor     r9d, r9d; LineNo
0x180019bbd  xor     r8d, r8d; FileName
0x180019bc0  xor     edx, edx; FunctionName
0x180019bc2  xor     ecx, ecx; Expression
0x180019bc4  call    cs:__imp__invoke_watson
0x180019bcb  call    cs:__imp_free
0x180019bd1  nop
0x180019bd2  jmp     short loc_180019BE8
0x180019bd4  xor     edi, edi
0x180019bd6  mov     rbx, [rsp+198h+var_150]
0x180019bdb  mov     r13, [rsp+198h+var_130]
0x180019be0  mov     rsi, [rsp+198h+var_128]
0x180019be5  mov     r14, r13
0x180019be8  mov     rcx, [rsp+198h+var_158]
0x180019bed  test    rcx, rcx
0x180019bf0  jz      short loc_180019C05
0x180019bf2  mov     [rsp+198h+var_158], rdi
0x180019bf7  mov     rax, [rcx]
0x180019bfa  mov     rax, [rax+8]
0x180019bfe  call    cs:__guard_dispatch_icall_fptr
0x180019c04  nop
0x180019c05  mov     rax, [rbx]
0x180019c08  mov     rcx, rbx
0x180019c0b  mov     rax, [rax+8]
0x180019c0f  call    cs:__guard_dispatch_icall_fptr
0x180019c15  lea     rax, [rsp+198h+Src]
0x180019c1d  cmp     rsi, rax
0x180019c20  jz      short loc_180019C5D
0x180019c22  mov     rcx, rsi
0x180019c25  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019c2a  movups  xmm0, xmmword ptr [rsp+198h+Src]
0x180019c32  movups  xmmword ptr [rsi], xmm0
0x180019c35  movups  xmm1, [rsp+198h+var_B0]
0x180019c3d  movups  xmmword ptr [rsi+10h], xmm1
0x180019c41  mov     qword ptr [rsp+198h+var_B0], rdi
0x180019c49  mov     qword ptr [rsp+198h+var_B0+8], 7
0x180019c55  mov     word ptr [rsp+198h+Src], di
0x180019c5d  cmp     qword ptr [r13+48h], 0E000h
0x180019c65  jbe     loc_180019DD8
0x180019c6b  mov     ecx, [r14+8]
0x180019c6f  xor     eax, eax
0x180019c71  mov     [rsp+198h+var_D0], rax
0x180019c79  mov     [rsp+198h+var_C8], eax
0x180019c80  cmp     ecx, 0FFFFh
0x180019c86  ja      short loc_180019C97
0x180019c88  lea     rdx, [rsp+198h+var_D0]
0x180019c90  call    ??$NumericTagToString@_W@TaggingUtilities@@YA_NIPEA_W@Z; TaggingUtilities::NumericTagToString<wchar_t>(uint,wchar_t *)
0x180019c95  jmp     short loc_180019CF0
0x180019c97  mov     eax, ecx
0x180019c99  shr     eax, 18h
0x180019c9c  cmp     eax, 24h ; '$'
0x180019c9f  jb      short loc_180019CE3
0x180019ca1  mov     word ptr [rsp+198h+var_D0], ax
0x180019ca9  mov     eax, ecx
0x180019cab  shr     eax, 10h
0x180019cae  mov     edx, 0FFh
0x180019cb3  and     ax, dx
0x180019cb6  mov     word ptr [rsp+198h+var_D0+2], ax
0x180019cbe  mov     eax, ecx
0x180019cc0  shr     eax, 8
0x180019cc3  and     ax, dx
0x180019cc6  mov     word ptr [rsp+198h+var_D0+4], ax
0x180019cce  and     cx, dx
0x180019cd1  mov     word ptr [rsp+198h+var_D0+6], cx
0x180019cd9  mov     word ptr [rsp+198h+var_C8], di
0x180019ce1  jmp     short loc_180019CF0
0x180019ce3  lea     rdx, [rsp+198h+var_D0]
0x180019ceb  call    ??$FiveCharTagToString@_W@TaggingUtilities@@YA_NIPEA_W@Z; TaggingUtilities::FiveCharTagToString<wchar_t>(uint,wchar_t *)
0x180019cf0  lea     rax, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x180019cf7  mov     [rsp+198h+var_78], rax
0x180019cff  lea     rax, aTag; "Tag"
0x180019d06  mov     [rsp+198h+var_70], rax
0x180019d0e  lea     rax, [rsp+198h+var_D0]
0x180019d16  mov     [rsp+198h+var_68], rax
0x180019d1e  mov     [rsp+198h+var_60], di
0x180019d26  mov     eax, [r13+48h]
0x180019d2a  lea     rcx, ??_7?$StructuredObject@I$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<uint,1>::`vftable'
0x180019d31  mov     [rsp+198h+var_148], rcx
0x180019d36  lea     rcx, aLength; "Length"
0x180019d3d  mov     [rsp+198h+var_140], rcx
0x180019d42  mov     [rsp+198h+var_138], eax
0x180019d46  mov     [rsp+198h+var_134], di
0x180019d4b  xor     r9d, r9d
0x180019d4e  lea     ebx, [r9+0Fh]
0x180019d52  mov     r8d, ebx
0x180019d55  lea     r14d, [rbx+7Bh]
0x180019d59  mov     edx, r14d
0x180019d5c  mov     r15d, 7DE001h
0x180019d62  mov     ecx, r15d
0x180019d65  call    ?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x180019d6a  test    al, al
0x180019d6c  jz      short loc_180019DD8
0x180019d6e  lea     rax, [rsp+198h+var_148]
0x180019d73  mov     [rsp+198h+var_160], rax
0x180019d78  lea     rax, [rsp+198h+var_78]
0x180019d80  mov     [rsp+198h+var_158], rax
0x180019d85  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x180019d8c  mov     [rsp+198h+Block], rax
0x180019d94  lea     rax, [rsp+198h+var_160]
0x180019d99  mov     [rsp+198h+Block+8], rax
0x180019da1  lea     rax, [rsp+198h+var_150]
0x180019da6  mov     qword ptr [rsp+198h+var_90], rax
0x180019dae  xor     r9d, r9d
0x180019db1  lea     rax, [rsp+198h+Block]
0x180019db9  mov     [rsp+198h+var_170], rax
0x180019dbe  lea     rax, aStructuredtrac_2; "structuredTraceAsJson length is larger "...
0x180019dc5  mov     [rsp+198h+Reserved], rax
0x180019dca  mov     r8d, ebx
0x180019dcd  mov     edx, r14d
0x180019dd0  mov     ecx, r15d
0x180019dd3  call    ?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,Mso::Logging::IStructuredTrace const &)
0x180019dd8  cmp     qword ptr [rsi+18h], 7
0x180019ddd  jbe     short loc_180019DE2
0x180019ddf  mov     rsi, [rsi]
0x180019de2  mov     rax, qword ptr [rsp+198h+var_B0+8]
0x180019dea  cmp     rax, 7
0x180019dee  jbe     short loc_180019E38
0x180019df0  mov     rcx, [rsp+198h+Src]
0x180019df8  mov     rdx, rcx
0x180019dfb  lea     rax, ds:2[rax*2]
0x180019e03  cmp     rax, 1000h
0x180019e09  jb      short loc_180019E32
0x180019e0b  mov     rcx, [rcx-8]
0x180019e0f  sub     rdx, rcx
0x180019e12  lea     rax, [rdx-8]
0x180019e16  cmp     rax, 1Fh
0x180019e1a  jbe     short loc_180019E32
0x180019e1c  mov     [rsp+198h+Reserved], rdi; Reserved
0x180019e21  xor     r9d, r9d; LineNo
0x180019e24  xor     r8d, r8d; FileName
0x180019e27  xor     edx, edx; FunctionName
  ... truncated ...
```
