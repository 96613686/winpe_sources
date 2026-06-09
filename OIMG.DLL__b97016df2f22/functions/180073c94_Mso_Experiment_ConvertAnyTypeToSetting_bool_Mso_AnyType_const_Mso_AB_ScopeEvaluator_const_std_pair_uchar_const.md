# Mso::Experiment::ConvertAnyTypeToSetting<bool>(Mso::AnyType const &,Mso::AB::ScopeEvaluator const &,std::pair<uchar const,bool const> const &,bool const &,uchar,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x180073c94`
- end: `0x180074310`
- name: `??$ConvertAnyTypeToSetting@_N@Experiment@Mso@@YA?BU?$pair@$$CBE$$CB_N@std@@AEBVAnyType@1@AEBUScopeEvaluator@AB@1@AEBU23@AEB_NEV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z`
- size: `1660`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002fcc8`
- `0x18003f130`
- `0x180067058`

## callees

- `0x1800124f0`
- `0x1800125c0`
- `0x1800127e0`
- `0x180012940`
- `0x180012aa0`
- `0x180012ccc`
- `0x180013080`
- `0x180013cfc`
- `0x180031338`
- `0x1800379ec`
- `0x180037ca4`
- `0x18003a2d4`
- `0x18005d2ec`
- `0x180073c94`
- `0x18007478c`
- `0x180074800`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x180073cee`
- `VCRUNTIME140!__std_type_info_compare` at `0x18007403b`
- `VCRUNTIME140!__std_type_info_compare` at `0x18007407f`
- `VCRUNTIME140!__std_type_info_compare` at `0x18007419d`
- `VCRUNTIME140!__std_type_info_compare` at `0x180073cee`
- `VCRUNTIME140!__std_type_info_compare` at `0x18007403b`
- `VCRUNTIME140!__std_type_info_compare` at `0x18007407f`
- `VCRUNTIME140!__std_type_info_compare` at `0x18007419d`
- `VCRUNTIME140!__std_type_info_name` at `0x180073d75`
- `VCRUNTIME140!__std_type_info_name` at `0x180073d75`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180073eb0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180073f01`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180073f51`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180073f93`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180073ffb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180073eb0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180073f01`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180073f51`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180073f93`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180073ffb`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x1800740e0`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x1800741fd`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x1800740e0`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x1800741fd`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180073ff4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180073ff4`

## pseudocode

```c
_BYTE *__fastcall Mso::Experiment::ConvertAnyTypeToSetting<bool>(
        _BYTE *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        _QWORD *a7)
{
  __int64 v10; // rax
  bool v11; // bl
  _BYTE *v12; // rax
  __int64 v13; // rax
  __int64 v14; // r8
  int v15; // edx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  struct Mso::Experiment::ExperimentationFactory *v24; // rax
  __int64 v25; // rax
  _QWORD *v26; // rax
  __int64 v27; // r8
  bool v28; // zf
  __int64 v29; // rax
  __int64 v30; // rax
  char *v31; // r14
  _DWORD *v32; // rdx
  unsigned __int64 v33; // r8
  _QWORD *v34; // r12
  __int64 v35; // r9
  unsigned __int8 *v36; // r12
  char *v37; // rsi
  signed __int64 v38; // r14
  _DWORD *v39; // rax
  _QWORD *v40; // rax
  int v41; // ecx
  _DWORD *v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  wchar_t **v45; // r14
  wchar_t *v46; // rcx
  unsigned __int64 v47; // rdx
  wchar_t **v48; // rax
  size_t v49; // r8
  wchar_t **v50; // r12
  wchar_t **v51; // rsi
  signed __int64 v52; // r14
  wchar_t **v53; // rax
  wchar_t **v54; // rax
  const wchar_t *v55; // rcx
  const char *v57; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *S1[2]; // [rsp+48h] [rbp-B8h] BYREF
  size_t N; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v60; // [rsp+60h] [rbp-A0h]
  _QWORD v61[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v62; // [rsp+78h] [rbp-88h]
  unsigned __int64 v63; // [rsp+80h] [rbp-80h]
  __int128 v64; // [rsp+88h] [rbp-78h] BYREF
  __m128i v65; // [rsp+98h] [rbp-68h]
  _QWORD v66[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v67; // [rsp+C0h] [rbp-40h]
  __m128i v68; // [rsp+D0h] [rbp-30h]
  __int16 v69; // [rsp+E0h] [rbp-20h]
  __int128 v70; // [rsp+E8h] [rbp-18h]
  __int64 v71; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v72; // [rsp+100h] [rbp+0h]
  _QWORD v73[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v74; // [rsp+120h] [rbp+20h]
  __m128i v75; // [rsp+130h] [rbp+30h]
  __int16 v76; // [rsp+140h] [rbp+40h]
  __int128 v77; // [rsp+148h] [rbp+48h]
  __int64 v78; // [rsp+158h] [rbp+58h]
  unsigned __int64 v79; // [rsp+160h] [rbp+60h]
  _QWORD v80[2]; // [rsp+170h] [rbp+70h] BYREF
  char v81; // [rsp+180h] [rbp+80h]
  __int16 v82; // [rsp+182h] [rbp+82h]
  void *Block[2]; // [rsp+188h] [rbp+88h]
  __m128i si128; // [rsp+198h] [rbp+98h]

  v10 = (**(__int64 (__fastcall ***)(_QWORD))*a2)(*a2);
  v11 = 0;
  if ( !(unsigned int)__std_type_info_compare(v10 + 8, &qword_1806A3A70) )
  {
    v12 = (_BYTE *)Mso::AnyCast<bool>(a2);
    *a1 = a6;
    a1[1] = *v12;
    return a1;
  }
  v80[0] = &Mso::Diagnostics::ClassifiedStructuredEnum<enum Mso::Privacy::ServiceGroupDisabledReason>::`vftable';
  v80[1] = "Expected Source";
  v81 = a6;
  v82 = 4;
  *(_OWORD *)Block = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Block[0]) = 0;
  v13 = __std_type_info_name(&qword_1806A3A70, &__type_info_root_node);
  v64 = 0;
  v65 = 0;
  v14 = -1;
  do
    ++v14;
  while ( *(_BYTE *)(v13 + v14) );
  std::string::_Construct<1,char const *>(&v64, v13);
  v73[0] = &Mso::Diagnostics::ClassifiedStructuredObject<std::string>::`vftable';
  v73[1] = "Expected Type";
  v74 = v64;
  v75 = v65;
  v76 = 4;
  v77 = 0;
  v78 = 0;
  v79 = 7;
  LOWORD(v77) = 0;
  v64 = 0;
  v65 = 0;
  std::wstring::_Construct<1,wchar_t *>(&v64, *a7, a7[1]);
  v66[0] = &Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::`vftable';
  v66[1] = "GateName";
  v67 = v64;
  v68 = v65;
  v69 = 4;
  v70 = 0;
  v71 = 0;
  v72 = 7;
  LOWORD(v70) = 0;
  v57 = "Incorrect treatment type specified for optimized gate/setting.";
  Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>,Mso::Diagnostics::ClassifiedStructuredObject<std::string>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned char>>(
    v16,
    v15,
    v17,
    v18,
    (__int64)&v57,
    (__int64)v66,
    (__int64)v73,
    (__int64)v80);
  if ( v72 > 7 )
  {
    v19 = (void *)v70;
    if ( 2 * v72 + 2 >= 0x1000 )
    {
      v19 = *(void **)(v70 - 8);
      if ( (unsigned __int64)(v70 - (_QWORD)v19 - 8) > 0x1F )
        goto LABEL_24;
    }
    free(v19);
  }
  *(_QWORD *)&v70 = 19937;
  v71 = 0;
  v72 = 15;
  if ( v68.m128i_i64[1] > 7uLL )
  {
    v20 = (void *)v67;
    if ( (unsigned __int64)(2 * v68.m128i_i64[1] + 2) >= 0x1000 )
    {
      v20 = *(void **)(v67 - 8);
      if ( (unsigned __int64)(v67 - (_QWORD)v20 - 8) > 0x1F )
        goto LABEL_24;
    }
    free(v20);
  }
  *(_QWORD *)&v67 = 19937;
  v68 = _mm_load_si128((const __m128i *)&_xmm);
  if ( v79 > 7 )
  {
    v21 = (void *)v77;
    if ( 2 * v79 + 2 >= 0x1000 )
    {
      v21 = *(void **)(v77 - 8);
      if ( (unsigned __int64)(v77 - (_QWORD)v21 - 8) > 0x1F )
        goto LABEL_24;
    }
    free(v21);
  }
  *(_QWORD *)&v77 = 19937;
  v78 = 0;
  v79 = 15;
  if ( v75.m128i_i64[1] <= 0xFuLL )
    goto LABEL_21;
  v22 = (void *)v74;
  if ( (unsigned __int64)(v75.m128i_i64[1] + 1) >= 0x1000 )
  {
    v22 = *(void **)(v74 - 8);
    if ( (unsigned __int64)(v74 - (_QWORD)v22 - 8) > 0x1F )
LABEL_24:
      _invoke_watson(0, 0, 0, 0, 0);
  }
  free(v22);
LABEL_21:
  *(_QWORD *)&v74 = 19937;
  v75 = _mm_load_si128((const __m128i *)&_xmm);
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v23 = Block[0];
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v23 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v23 - 8) > 0x1F )
        goto LABEL_24;
    }
    free(v23);
  }
  v24 = Mso::Experiment::ExperimentationFactory::Instance();
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v24 + 4) + 8LL))(*((_QWORD *)v24 + 4), 0) )
    CrashWithRecovery(0x21050011u, 0);
  v25 = (**(__int64 (__fastcall ***)(_QWORD))*a2)(*a2);
  if ( !(unsigned int)__std_type_info_compare(v25 + 8, &qword_1806A3C28) )
  {
    v26 = (_QWORD *)Mso::AnyCast<__int64>(a2);
    v28 = *v26 == 1;
    if ( *v26 <= 1u )
    {
      *a1 = a6;
      a1[1] = v28;
      return a1;
    }
LABEL_83:
    Mso::Experiment::EvaluateScopes<bool>(a1, a3, v27, a5);
    return a1;
  }
  v29 = (**(__int64 (__fastcall ***)(_QWORD))*a2)(*a2);
  if ( (unsigned int)__std_type_info_compare(v29 + 8, &qword_1806A39E8) )
  {
    v43 = (**(__int64 (__fastcall ***)(_QWORD))*a2)(*a2);
    if ( (unsigned int)__std_type_info_compare(v43 + 8, &qword_1806A3A88) )
      goto LABEL_83;
    v44 = Mso::AnyCast<std::wstring>(a2);
    std::wstring::wstring(S1, v44);
    v45 = S1;
    v46 = S1[0];
    v47 = v60;
    if ( v60 > 7 )
      v45 = (wchar_t **)S1[0];
    v48 = S1;
    if ( v60 > 7 )
      v48 = (wchar_t **)S1[0];
    v49 = N;
    v50 = (wchar_t **)((char *)v48 + 2 * N);
    v51 = S1;
    if ( v60 > 7 )
      v51 = (wchar_t **)S1[0];
    if ( v51 != v50 )
    {
      v52 = (char *)v45 - (char *)v51;
      do
      {
        *(_WORD *)((char *)v51 + v52) = tolower(*(unsigned __int16 *)v51);
        v51 = (wchar_t **)((char *)v51 + 2);
      }
      while ( v51 != v50 );
      v47 = v60;
      v49 = N;
      v46 = S1[0];
    }
    v53 = S1;
    if ( v47 > 7 )
      v53 = (wchar_t **)v46;
    if ( v49 == 4 )
    {
      if ( !wmemcmp((const wchar_t *)v53, L"true", 4u) )
      {
LABEL_77:
        v55 = (const wchar_t *)S1;
        if ( v60 > 7 )
          v55 = S1[0];
        if ( N == 4 )
          v11 = wmemcmp(v55, L"true", 4u) == 0;
        *a1 = a6;
        a1[1] = v11;
        std::wstring::~wstring(S1);
        return a1;
      }
      v47 = v60;
      v49 = N;
      v46 = S1[0];
    }
    v54 = S1;
    if ( v47 > 7 )
      v54 = (wchar_t **)v46;
    if ( v49 != 5 || wmemcmp((const wchar_t *)v54, L"false", 5u) )
    {
      std::wstring::~wstring(S1);
      goto LABEL_83;
    }
    goto LABEL_77;
  }
  v30 = Mso::AnyCast<std::string>(a2);
  std::string::string(v61, v30);
  v31 = (char *)v61;
  v32 = (_DWORD *)v61[0];
  v33 = v63;
  if ( v63 > 0xF )
    v31 = (char *)v61[0];
  v34 = v61;
  if ( v63 > 0xF )
    v34 = (_QWORD *)v61[0];
  v35 = v62;
  v36 = (unsigned __int8 *)v34 + v62;
  v37 = (char *)v61;
  if ( v63 > 0xF )
    v37 = (char *)v61[0];
  if ( v37 != (char *)v36 )
  {
    v38 = v31 - v37;
    do
    {
      v37[v38] = tolower((unsigned __int8)*v37);
      ++v37;
    }
    while ( v37 != (char *)v36 );
    v33 = v63;
    v35 = v62;
    v32 = (_DWORD *)v61[0];
  }
  v39 = v61;
  if ( v33 > 0xF )
    v39 = v32;
  if ( v35 != 4 || *v39 != 1702195828 )
  {
    v40 = v61;
    if ( v33 > 0xF )
      v40 = v32;
    if ( v35 != 5 )
      goto LABEL_56;
    v41 = *(_DWORD *)v40 - 1936482662;
    if ( *(_DWORD *)v40 == 1936482662 )
      v41 = *((unsigned __int8 *)v40 + 4) - 101;
    if ( v41 )
    {
LABEL_56:
      std::string::~string(v61);
      goto LABEL_83;
    }
  }
  v42 = v61;
  if ( v33 > 0xF )
    v42 = v32;
  if ( v35 == 4 )
    v11 = *v42 == 1702195828;
  *a1 = a6;
  a1[1] = v11;
  std::string::~string(v61);
  return a1;
}

```

## disassembly

```asm
0x180073c94  mov     [rsp-8+arg_18], rbx
0x180073c99  push    rbp
0x180073c9a  push    rsi
0x180073c9b  push    rdi
0x180073c9c  push    r12
0x180073c9e  push    r13
0x180073ca0  push    r14
0x180073ca2  push    r15
0x180073ca4  lea     rbp, [rsp-0B0h]
0x180073cac  sub     rsp, 1B0h
0x180073cb3  mov     rax, cs:__security_cookie
0x180073cba  xor     rax, rsp
0x180073cbd  mov     [rbp+0E0h+var_38], rax
0x180073cc4  mov     r13, r8
0x180073cc7  mov     rsi, rdx
0x180073cca  mov     rdi, rcx
0x180073ccd  mov     r14, [rbp+0E0h+arg_30]
0x180073cd4  mov     rcx, [rdx]
0x180073cd7  mov     rax, [rcx]
0x180073cda  mov     rax, [rax]
0x180073cdd  call    cs:__guard_dispatch_icall_fptr
0x180073ce3  lea     rcx, [rax+8]
0x180073ce7  lea     rdx, qword_1806A3A70
0x180073cee  call    cs:__imp___std_type_info_compare
0x180073cf4  xor     ebx, ebx
0x180073cf6  test    eax, eax
0x180073cf8  jnz     short loc_180073D14
0x180073cfa  mov     rcx, rsi
0x180073cfd  call    ??$AnyCast@_N@Mso@@YAAEA_NAEAVAnyType@0@@Z; Mso::AnyCast<bool>(Mso::AnyType &)
0x180073d02  mov     cl, [rbp+0E0h+arg_28]
0x180073d08  mov     [rdi], cl
0x180073d0a  mov     cl, [rax]
0x180073d0c  mov     [rdi+1], cl
0x180073d0f  jmp     loc_1800742D6
0x180073d14  lea     rax, ??_7?$ClassifiedStructuredEnum@W4ServiceGroupDisabledReason@Privacy@Mso@@@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredEnum<Mso::Privacy::ServiceGroupDisabledReason>::`vftable'
0x180073d1b  mov     [rbp+0E0h+var_70], rax
0x180073d1f  lea     rax, aExpectedSource; "Expected Source"
0x180073d26  mov     [rbp+0E0h+var_68], rax
0x180073d2a  mov     r15b, [rbp+0E0h+arg_28]
0x180073d31  mov     [rbp+0E0h+var_60], r15b
0x180073d38  mov     r12d, 4
0x180073d3e  mov     [rbp+0E0h+var_5E], r12w
0x180073d46  xorps   xmm0, xmm0
0x180073d49  movups  xmmword ptr [rbp+0E0h+Block], xmm0
0x180073d50  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180073d58  movdqu  [rbp+0E0h+var_48], xmm1
0x180073d60  mov     word ptr [rbp+0E0h+Block], bx
0x180073d67  lea     rdx, ?__type_info_root_node@@3U__type_info_node@@A; __type_info_node __type_info_root_node
0x180073d6e  lea     rcx, qword_1806A3A70
0x180073d75  call    cs:__imp___std_type_info_name
0x180073d7b  xorps   xmm0, xmm0
0x180073d7e  movups  [rbp+0E0h+var_158], xmm0
0x180073d82  xorps   xmm1, xmm1
0x180073d85  movdqu  [rbp+0E0h+var_148], xmm1
0x180073d8a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180073d8e  inc     r8
0x180073d91  cmp     [rax+r8], bl
0x180073d95  jnz     short loc_180073D8E
0x180073d97  mov     rdx, rax
0x180073d9a  lea     rcx, [rbp+0E0h+var_158]
0x180073d9e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180073da3  lea     rax, ??_7?$ClassifiedStructuredObject@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<std::string>::`vftable'
0x180073daa  mov     [rbp+0E0h+var_D0], rax
0x180073dae  lea     rax, aExpectedType; "Expected Type"
0x180073db5  mov     [rbp+0E0h+var_C8], rax
0x180073db9  movups  xmm1, [rbp+0E0h+var_158]
0x180073dbd  movaps  [rbp+0E0h+var_C0], xmm1
0x180073dc1  movups  xmm0, [rbp+0E0h+var_148]
0x180073dc5  movaps  [rbp+0E0h+var_B0], xmm0
0x180073dc9  mov     [rbp+0E0h+var_A0], r12w
0x180073dce  xorps   xmm0, xmm0
0x180073dd1  movups  [rbp+0E0h+var_98], xmm0
0x180073dd5  mov     [rbp+0E0h+var_88], rbx
0x180073dd9  mov     [rbp+0E0h+var_80], 7
0x180073de1  mov     word ptr [rbp+0E0h+var_98], bx
0x180073de5  movups  [rbp+0E0h+var_158], xmm0
0x180073de9  xorps   xmm1, xmm1
0x180073dec  movdqu  [rbp+0E0h+var_148], xmm1
0x180073df1  mov     r8, [r14+8]
0x180073df5  mov     rdx, [r14]
0x180073df8  lea     rcx, [rbp+0E0h+var_158]
0x180073dfc  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180073e01  lea     rax, ??_7?$ClassifiedStructuredObject@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::`vftable'
0x180073e08  mov     [rbp+0E0h+var_130], rax
0x180073e0c  lea     rax, aGatename; "GateName"
0x180073e13  mov     [rbp+0E0h+var_128], rax
0x180073e17  movups  xmm1, [rbp+0E0h+var_158]
0x180073e1b  movaps  [rbp+0E0h+var_120], xmm1
0x180073e1f  movups  xmm0, [rbp+0E0h+var_148]
0x180073e23  movaps  [rbp+0E0h+var_110], xmm0
0x180073e27  mov     [rbp+0E0h+var_100], r12w
0x180073e2c  xorps   xmm0, xmm0
0x180073e2f  movups  [rbp+0E0h+var_F8], xmm0
0x180073e33  mov     [rbp+0E0h+var_E8], rbx
0x180073e37  mov     r14d, 7
0x180073e3d  mov     [rbp+0E0h+var_E0], r14
0x180073e41  mov     word ptr [rbp+0E0h+var_F8], bx
0x180073e45  lea     rax, aIncorrectTreat; "Incorrect treatment type specified for "...
0x180073e4c  mov     [rsp+1E0h+var_1A0], rax
0x180073e51  lea     rax, [rbp+0E0h+var_70]
0x180073e55  mov     [rsp+1E0h+var_1A8], rax
0x180073e5a  lea     rax, [rbp+0E0h+var_D0]
0x180073e5e  mov     [rsp+1E0h+var_1B0], rax
0x180073e63  lea     rax, [rbp+0E0h+var_130]
0x180073e67  mov     [rsp+1E0h+var_1B8], rax
0x180073e6c  lea     rax, [rsp+1E0h+var_1A0]
0x180073e71  mov     [rsp+1E0h+Reserved], rax
0x180073e76  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Diagnostics@Mso@@U?$ClassifiedStructuredObject@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$ClassifiedStructuredObject@E@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@01@$$QEAU?$ClassifiedStructuredObject@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@01@$$QEAU?$ClassifiedStructuredObject@E@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>,Mso::Diagnostics::ClassifiedStructuredObject<std::string>,Mso::Diagnostics::ClassifiedStructuredObject<uchar>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<std::wstring> &&,Mso::Diagnostics::ClassifiedStructuredObject<std::string> &&,Mso::Diagnostics::ClassifiedStructuredObject<uchar> &&)
0x180073e7b  mov     rax, [rbp+0E0h+var_E0]
0x180073e7f  cmp     rax, r14
0x180073e82  jbe     short loc_180073EB6
0x180073e84  mov     rcx, qword ptr [rbp+0E0h+var_F8]
0x180073e88  mov     rdx, rcx
0x180073e8b  lea     rax, ds:2[rax*2]
0x180073e93  cmp     rax, 1000h
0x180073e99  jb      short loc_180073EB0
0x180073e9b  mov     rcx, [rcx-8]; Block
0x180073e9f  sub     rdx, rcx
0x180073ea2  lea     rax, [rdx-8]
0x180073ea6  cmp     rax, 1Fh
0x180073eaa  ja      loc_180073FE5
0x180073eb0  call    cs:__imp_free
0x180073eb6  mov     qword ptr [rbp+0E0h+var_F8], 4DE1h
0x180073ebe  mov     [rbp+0E0h+var_E8], rbx
0x180073ec2  mov     r12d, 0Fh
0x180073ec8  mov     [rbp+0E0h+var_E0], r12
0x180073ecc  mov     rax, qword ptr [rbp+0E0h+var_110+8]
0x180073ed0  cmp     rax, r14
0x180073ed3  jbe     short loc_180073F07
0x180073ed5  mov     rcx, qword ptr [rbp+0E0h+var_120]
0x180073ed9  mov     rdx, rcx
0x180073edc  lea     rax, ds:2[rax*2]
0x180073ee4  cmp     rax, 1000h
0x180073eea  jb      short loc_180073F01
0x180073eec  mov     rcx, [rcx-8]; Block
0x180073ef0  sub     rdx, rcx
0x180073ef3  lea     rax, [rdx-8]
0x180073ef7  cmp     rax, 1Fh
0x180073efb  ja      loc_180073FE5
0x180073f01  call    cs:__imp_free
0x180073f07  mov     qword ptr [rbp+0E0h+var_120], 4DE1h
0x180073f0f  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180073f17  movdqa  [rbp+0E0h+var_110], xmm0
0x180073f1c  mov     rax, [rbp+0E0h+var_80]
0x180073f20  cmp     rax, r14
0x180073f23  jbe     short loc_180073F57
0x180073f25  mov     rcx, qword ptr [rbp+0E0h+var_98]
0x180073f29  mov     rdx, rcx
0x180073f2c  lea     rax, ds:2[rax*2]
0x180073f34  cmp     rax, 1000h
0x180073f3a  jb      short loc_180073F51
0x180073f3c  mov     rcx, [rcx-8]; Block
0x180073f40  sub     rdx, rcx
0x180073f43  lea     rax, [rdx-8]
0x180073f47  cmp     rax, 1Fh
0x180073f4b  ja      loc_180073FE5
0x180073f51  call    cs:__imp_free
0x180073f57  mov     qword ptr [rbp+0E0h+var_98], 4DE1h
0x180073f5f  mov     [rbp+0E0h+var_88], rbx
0x180073f63  mov     [rbp+0E0h+var_80], r12
0x180073f67  mov     rax, qword ptr [rbp+0E0h+var_B0+8]
0x180073f6b  cmp     rax, r12
0x180073f6e  jbe     short loc_180073F99
0x180073f70  mov     rcx, qword ptr [rbp+0E0h+var_C0]
0x180073f74  mov     rdx, rcx
0x180073f77  inc     rax
0x180073f7a  cmp     rax, 1000h
0x180073f80  jb      short loc_180073F93
0x180073f82  mov     rcx, [rcx-8]; Block
0x180073f86  sub     rdx, rcx
0x180073f89  lea     rax, [rdx-8]
0x180073f8d  cmp     rax, 1Fh
0x180073f91  ja      short loc_180073FE5
0x180073f93  call    cs:__imp_free
0x180073f99  mov     qword ptr [rbp+0E0h+var_C0], 4DE1h
0x180073fa1  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x180073fa9  movdqa  [rbp+0E0h+var_B0], xmm0
0x180073fae  mov     rax, qword ptr [rbp+0E0h+var_48+8]
0x180073fb5  cmp     rax, r14
0x180073fb8  jbe     short loc_180074001
0x180073fba  mov     rcx, [rbp+0E0h+Block]; Block
0x180073fc1  mov     rdx, rcx
0x180073fc4  lea     rax, ds:2[rax*2]
0x180073fcc  cmp     rax, 1000h
0x180073fd2  jb      short loc_180073FFB
0x180073fd4  mov     rcx, [rcx-8]
0x180073fd8  sub     rdx, rcx
0x180073fdb  lea     rax, [rdx-8]
0x180073fdf  cmp     rax, 1Fh
0x180073fe3  jbe     short loc_180073FFB
0x180073fe5  mov     [rsp+1E0h+Reserved], rbx; Reserved
0x180073fea  xor     r9d, r9d; LineNo
0x180073fed  xor     r8d, r8d; FileName
0x180073ff0  xor     edx, edx; FunctionName
0x180073ff2  xor     ecx, ecx; Expression
0x180073ff4  call    cs:__imp__invoke_watson
0x180073ffb  call    cs:__imp_free
0x180074001  call    ?Instance@ExperimentationFactory@Experiment@Mso@@SAAEAV123@XZ; Mso::Experiment::ExperimentationFactory::Instance(void)
0x180074006  mov     rcx, [rax+20h]
0x18007400a  mov     rax, [rcx]
0x18007400d  xor     edx, edx
0x18007400f  mov     rax, [rax+8]
0x180074013  call    cs:__guard_dispatch_icall_fptr
0x180074019  test    al, al
0x18007401b  jnz     loc_180074303
0x180074021  mov     rcx, [rsi]
0x180074024  mov     rax, [rcx]
0x180074027  mov     rax, [rax]
0x18007402a  call    cs:__guard_dispatch_icall_fptr
0x180074030  lea     rcx, [rax+8]
0x180074034  lea     rdx, qword_1806A3C28
0x18007403b  call    cs:__imp___std_type_info_compare
0x180074041  test    eax, eax
0x180074043  jnz     short loc_180074065
0x180074045  mov     rcx, rsi
0x180074048  call    ??$AnyCast@_J@Mso@@YAAEB_JAEBVAnyType@0@@Z; Mso::AnyCast<__int64>(Mso::AnyType const &)
0x18007404d  cmp     qword ptr [rax], 1
0x180074051  ja      loc_1800742C4
0x180074057  mov     [rdi], r15b
0x18007405a  setz    al
0x18007405d  mov     [rdi+1], al
0x180074060  jmp     loc_1800742D6
0x180074065  mov     rcx, [rsi]
0x180074068  mov     rax, [rcx]
0x18007406b  mov     rax, [rax]
0x18007406e  call    cs:__guard_dispatch_icall_fptr
0x180074074  lea     rcx, [rax+8]
0x180074078  lea     rdx, qword_1806A39E8
0x18007407f  call    cs:__imp___std_type_info_compare
0x180074085  test    eax, eax
0x180074087  jnz     loc_180074183
0x18007408d  mov     rcx, rsi
0x180074090  call    ??$AnyCast@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Mso@@YAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVAnyType@0@@Z; Mso::AnyCast<std::string>(Mso::AnyType const &)
0x180074095  mov     rdx, rax
0x180074098  lea     rcx, [rsp+1E0h+var_178]
0x18007409d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800740a2  lea     r14, [rsp+1E0h+var_178]
0x1800740a7  mov     rdx, [rsp+1E0h+var_178]
0x1800740ac  mov     r8, [rbp+0E0h+var_160]
0x1800740b0  cmp     r8, r12
0x1800740b3  cmova   r14, rdx
0x1800740b7  lea     r12, [rsp+1E0h+var_178]
0x1800740bc  cmova   r12, rdx
0x1800740c0  mov     r9, [rsp+1E0h+var_168]
0x1800740c5  add     r12, r9
0x1800740c8  lea     rsi, [rsp+1E0h+var_178]
0x1800740cd  cmp     r8, 0Fh
0x1800740d1  cmova   rsi, rdx
0x1800740d5  cmp     rsi, r12
0x1800740d8  jz      short loc_180074100
0x1800740da  sub     r14, rsi
0x1800740dd  movzx   ecx, byte ptr [rsi]; C
0x1800740e0  call    cs:__imp_tolower
0x1800740e6  mov     [rsi+r14], al
0x1800740ea  inc     rsi
0x1800740ed  cmp     rsi, r12
0x1800740f0  jnz     short loc_1800740DD
0x1800740f2  mov     r8, [rbp+0E0h+var_160]
0x1800740f6  mov     r9, [rsp+1E0h+var_168]
0x1800740fb  mov     rdx, [rsp+1E0h+var_178]
0x180074100  lea     rax, [rsp+1E0h+var_178]
0x180074105  cmp     r8, 0Fh
0x180074109  cmova   rax, rdx
0x18007410d  mov     r10d, 65757274h
0x180074113  cmp     r9, 4
0x180074117  jnz     short loc_18007411E
0x180074119  cmp     [rax], r10d
0x18007411c  jz      short loc_180074146
0x18007411e  lea     rax, [rsp+1E0h+var_178]
0x180074123  cmp     r8, 0Fh
0x180074127  cmova   rax, rdx
0x18007412b  cmp     r9, 5
0x18007412f  jnz     short loc_180074174
0x180074131  mov     ecx, [rax]
0x180074133  sub     ecx, 736C6166h
0x180074139  jnz     short loc_180074142
0x18007413b  movzx   ecx, byte ptr [rax+4]
0x18007413f  sub     ecx, 65h ; 'e'
0x180074142  test    ecx, ecx
0x180074144  jnz     short loc_180074174
0x180074146  lea     rax, [rsp+1E0h+var_178]
0x18007414b  cmp     r8, 0Fh
0x18007414f  cmova   rax, rdx
0x180074153  cmp     r9, 4
0x180074157  jnz     short loc_18007415F
0x180074159  cmp     [rax], r10d
0x18007415c  setz    bl
0x18007415f  mov     [rdi], r15b
0x180074162  mov     [rdi+1], bl
0x180074165  lea     rcx, [rsp+1E0h+var_178]; void *
0x18007416a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18007416f  jmp     loc_1800742D6
0x180074174  lea     rcx, [rsp+1E0h+var_178]; void *
0x180074179  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18007417e  jmp     loc_1800742C4
0x180074183  mov     rcx, [rsi]
0x180074186  mov     rax, [rcx]
0x180074189  mov     rax, [rax]
0x18007418c  call    cs:__guard_dispatch_icall_fptr
0x180074192  lea     rcx, [rax+8]
  ... truncated ...
```
