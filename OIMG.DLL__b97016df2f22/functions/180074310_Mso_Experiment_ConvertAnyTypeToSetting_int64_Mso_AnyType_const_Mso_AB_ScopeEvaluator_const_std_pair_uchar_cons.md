# Mso::Experiment::ConvertAnyTypeToSetting<__int64>(Mso::AnyType const &,Mso::AB::ScopeEvaluator const &,std::pair<uchar const,__int64 const> const &,__int64 const &,uchar,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x180074310`
- end: `0x180074789`
- name: `??$ConvertAnyTypeToSetting@_J@Experiment@Mso@@YA?BU?$pair@$$CBE$$CB_J@std@@AEBVAnyType@1@AEBUScopeEvaluator@AB@1@AEBU23@AEB_JEV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z`
- size: `1145`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003033c`
- `0x18003f77c`
- `0x18006729c`

## callees

- `0x1800127e0`
- `0x180012ccc`
- `0x180013080`
- `0x180019008`
- `0x18002fc5c`
- `0x180037ca4`
- `0x18005d2ec`
- `0x180074310`
- `0x180074800`
- `0x18056bd00`
- `0x18056cd8c`
- `0x18056dc2e`
- `0x18056dce0`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x180074360`
- `VCRUNTIME140!__std_type_info_compare` at `0x18007439c`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800743d8`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800743fc`
- `VCRUNTIME140!__std_type_info_compare` at `0x180074360`
- `VCRUNTIME140!__std_type_info_compare` at `0x18007439c`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800743d8`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800743fc`
- `VCRUNTIME140!__std_type_info_name` at `0x18007447b`
- `VCRUNTIME140!__std_type_info_name` at `0x18007447b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800745c5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180074613`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18007465d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18007469d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800746f9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800745c5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180074613`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18007465d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18007469d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800746f9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800746f2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800746f2`

## pseudocode

```c
__int64 __fastcall Mso::Experiment::ConvertAnyTypeToSetting<__int64>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _OWORD *a4,
        __int64 *a5,
        char a6,
        _QWORD *a7)
{
  __int64 v10; // rax
  __int64 *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // r8
  int v19; // edx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  struct Mso::Experiment::ExperimentationFactory *v28; // rax
  const char *v30; // [rsp+40h] [rbp-C0h] BYREF
  __int128 pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  __m128i v32; // [rsp+58h] [rbp-A8h]
  _QWORD v33[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v34; // [rsp+80h] [rbp-80h]
  __m128i v35; // [rsp+90h] [rbp-70h]
  __int16 v36; // [rsp+A0h] [rbp-60h]
  __int128 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v39; // [rsp+C0h] [rbp-40h]
  _QWORD v40[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v41; // [rsp+E0h] [rbp-20h]
  __m128i v42; // [rsp+F0h] [rbp-10h]
  __int16 v43; // [rsp+100h] [rbp+0h]
  __int128 v44; // [rsp+108h] [rbp+8h]
  __int64 v45; // [rsp+118h] [rbp+18h]
  unsigned __int64 v46; // [rsp+120h] [rbp+20h]
  _QWORD v47[2]; // [rsp+130h] [rbp+30h] BYREF
  char v48; // [rsp+140h] [rbp+40h]
  __int16 v49; // [rsp+142h] [rbp+42h]
  void *Block[2]; // [rsp+148h] [rbp+48h]
  __m128i si128; // [rsp+158h] [rbp+58h]

  v10 = (**(__int64 (__fastcall ***)(_QWORD))*a2)(*a2);
  if ( !(unsigned int)__std_type_info_compare(v10 + 8, &qword_1806A3C28) )
  {
    v11 = (__int64 *)Mso::AnyCast<__int64>(a2);
    *(_BYTE *)a1 = a6;
LABEL_38:
    v13 = *v11;
    goto LABEL_39;
  }
  v12 = (**(__int64 (__fastcall ***)(_QWORD))*a2)(*a2);
  if ( (unsigned int)__std_type_info_compare(v12 + 8, &qword_1806A3978) )
  {
    v14 = (**(__int64 (__fastcall ***)(_QWORD))*a2)(*a2);
    if ( !(unsigned int)__std_type_info_compare(v14 + 8, &qword_1806A3C58) )
    {
      v15 = (**(__int64 (__fastcall ***)(_QWORD))*a2)(*a2);
      if ( (unsigned int)__std_type_info_compare(&qword_1806A3C58, v15 + 8) )
      {
        std::bad_cast::bad_cast((std::bad_cast *)&pExceptionObject);
        throw (std::bad_cast *)&pExceptionObject;
      }
      v16 = *a2;
      if ( v16 )
        _castguard_slow_path_check_user_handled(*(_QWORD *)v16, 816, 0);
      else
        v16 = 0;
      v13 = *(unsigned int *)(v16 + 8);
      goto LABEL_5;
    }
    v47[0] = &Mso::Diagnostics::ClassifiedStructuredEnum<enum Mso::Privacy::ServiceGroupDisabledReason>::`vftable';
    v47[1] = "Expected Source";
    v48 = a6;
    v49 = 4;
    *(_OWORD *)Block = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Block[0]) = 0;
    v17 = __std_type_info_name(&qword_1806A3C28, &__type_info_root_node);
    pExceptionObject = 0;
    v32 = 0;
    v18 = -1;
    do
      ++v18;
    while ( *(_BYTE *)(v17 + v18) );
    std::string::_Construct<1,char const *>(&pExceptionObject, v17);
    v40[0] = &Mso::Diagnostics::ClassifiedStructuredObject<std::string>::`vftable';
    v40[1] = "Expected Type";
    v41 = pExceptionObject;
    v42 = v32;
    v43 = 4;
    v44 = 0;
    v45 = 0;
    v46 = 7;
    LOWORD(v44) = 0;
    pExceptionObject = 0;
    v32 = 0;
    std::wstring::_Construct<1,wchar_t *>(&pExceptionObject, *a7, a7[1]);
    v33[0] = &Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::`vftable';
    v33[1] = "GateName";
    v34 = pExceptionObject;
    v35 = v32;
    v36 = 4;
    v37 = 0;
    v38 = 0;
    v39 = 7;
    LOWORD(v37) = 0;
    v30 = "Incorrect treatment type specified for optimized gate/setting.";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>,Mso::Diagnostics::ClassifiedStructuredObject<std::string>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned char>>(
      v20,
      v19,
      v21,
      v22,
      (__int64)&v30,
      (__int64)v33,
      (__int64)v40,
      (__int64)v47);
    if ( v39 > 7 )
    {
      v23 = (void *)v37;
      if ( 2 * v39 + 2 >= 0x1000 )
      {
        v23 = *(void **)(v37 - 8);
        if ( (unsigned __int64)(v37 - (_QWORD)v23 - 8) > 0x1F )
          goto LABEL_33;
      }
      free(v23);
    }
    *(_QWORD *)&v37 = 19937;
    v38 = 0;
    v39 = 15;
    if ( v35.m128i_i64[1] > 7uLL )
    {
      v24 = (void *)v34;
      if ( (unsigned __int64)(2 * v35.m128i_i64[1] + 2) >= 0x1000 )
      {
        v24 = *(void **)(v34 - 8);
        if ( (unsigned __int64)(v34 - (_QWORD)v24 - 8) > 0x1F )
          goto LABEL_33;
      }
      free(v24);
    }
    *(_QWORD *)&v34 = 19937;
    v35 = _mm_load_si128((const __m128i *)&_xmm);
    if ( v46 > 7 )
    {
      v25 = (void *)v44;
      if ( 2 * v46 + 2 >= 0x1000 )
      {
        v25 = *(void **)(v44 - 8);
        if ( (unsigned __int64)(v44 - (_QWORD)v25 - 8) > 0x1F )
          goto LABEL_33;
      }
      free(v25);
    }
    *(_QWORD *)&v44 = 19937;
    v45 = 0;
    v46 = 15;
    if ( v42.m128i_i64[1] <= 0xFuLL )
      goto LABEL_30;
    v26 = (void *)v41;
    if ( (unsigned __int64)(v42.m128i_i64[1] + 1) < 0x1000
      || (v26 = *(void **)(v41 - 8), (unsigned __int64)(v41 - (_QWORD)v26 - 8) <= 0x1F) )
    {
      free(v26);
LABEL_30:
      *(_QWORD *)&v41 = 19937;
      v42 = _mm_load_si128((const __m128i *)&_xmm);
      if ( si128.m128i_i64[1] > 7uLL )
      {
        v27 = Block[0];
        if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
        {
          v27 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v27 - 8) > 0x1F )
            goto LABEL_33;
        }
        free(v27);
      }
      v28 = Mso::Experiment::ExperimentationFactory::Instance();
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v28 + 4) + 8LL))(*((_QWORD *)v28 + 4), 0) )
        CrashWithRecovery(0x21050011u, 0);
      if ( *(_BYTE *)a4 )
      {
        *(_OWORD *)a1 = *a4;
        return a1;
      }
      *(_BYTE *)a1 = 1;
      v11 = a5;
      goto LABEL_38;
    }
LABEL_33:
    _invoke_watson(0, 0, 0, 0, 0);
  }
  v13 = *(int *)Mso::AnyCast<int>(a2);
LABEL_5:
  *(_BYTE *)a1 = a6;
LABEL_39:
  *(_QWORD *)(a1 + 8) = v13;
  return a1;
}

```

## disassembly

```asm
0x180074310  mov     [rsp-8+arg_10], rbx
0x180074315  push    rbp
0x180074316  push    rsi
0x180074317  push    rdi
0x180074318  push    r14
0x18007431a  push    r15
0x18007431c  lea     rbp, [rsp-70h]
0x180074321  sub     rsp, 170h
0x180074328  mov     rax, cs:__security_cookie
0x18007432f  xor     rax, rsp
0x180074332  mov     [rbp+90h+var_28], rax
0x180074336  mov     rsi, r9
0x180074339  mov     rdi, rdx
0x18007433c  mov     rbx, rcx
0x18007433f  mov     r14, [rbp+90h+arg_30]
0x180074346  mov     rcx, [rdx]
0x180074349  mov     rax, [rcx]
0x18007434c  mov     rax, [rax]
0x18007434f  call    cs:__guard_dispatch_icall_fptr
0x180074355  lea     rcx, [rax+8]
0x180074359  lea     rdx, qword_1806A3C28
0x180074360  call    cs:__imp___std_type_info_compare
0x180074366  xor     r15d, r15d
0x180074369  test    eax, eax
0x18007436b  jnz     short loc_180074382
0x18007436d  mov     rcx, rdi
0x180074370  call    ??$AnyCast@_J@Mso@@YAAEB_JAEBVAnyType@0@@Z; Mso::AnyCast<__int64>(Mso::AnyType const &)
0x180074375  mov     cl, [rbp+90h+arg_28]
0x18007437b  mov     [rbx], cl
0x18007437d  jmp     loc_18007472A
0x180074382  mov     rcx, [rdi]
0x180074385  mov     rax, [rcx]
0x180074388  mov     rax, [rax]
0x18007438b  call    cs:__guard_dispatch_icall_fptr
0x180074391  lea     rcx, [rax+8]
0x180074395  lea     rdx, qword_1806A3978
0x18007439c  call    cs:__imp___std_type_info_compare
0x1800743a2  test    eax, eax
0x1800743a4  jnz     short loc_1800743BE
0x1800743a6  mov     rcx, rdi
0x1800743a9  call    ??$AnyCast@H@Mso@@YAAEAHAEAVAnyType@0@@Z; Mso::AnyCast<int>(Mso::AnyType &)
0x1800743ae  movsxd  rcx, dword ptr [rax]
0x1800743b1  mov     al, [rbp+90h+arg_28]
0x1800743b7  mov     [rbx], al
0x1800743b9  jmp     loc_18007472D
0x1800743be  mov     rcx, [rdi]
0x1800743c1  mov     rax, [rcx]
0x1800743c4  mov     rax, [rax]
0x1800743c7  call    cs:__guard_dispatch_icall_fptr
0x1800743cd  lea     rcx, [rax+8]
0x1800743d1  lea     rdx, qword_1806A3C58
0x1800743d8  call    cs:__imp___std_type_info_compare
0x1800743de  test    eax, eax
0x1800743e0  jnz     short loc_18007442C
0x1800743e2  mov     rcx, [rdi]
0x1800743e5  mov     rax, [rcx]
0x1800743e8  mov     rax, [rax]
0x1800743eb  call    cs:__guard_dispatch_icall_fptr
0x1800743f1  lea     rdx, [rax+8]
0x1800743f5  lea     rcx, qword_1806A3C58
0x1800743fc  call    cs:__imp___std_type_info_compare
0x180074402  test    eax, eax
0x180074404  jnz     loc_18007476D
0x18007440a  mov     rdi, [rdi]
0x18007440d  test    rdi, rdi
0x180074410  jz      short loc_180074424
0x180074412  xor     r8d, r8d
0x180074415  mov     edx, 330h
0x18007441a  mov     rcx, [rdi]
0x18007441d  call    __castguard_slow_path_check_user_handled
0x180074422  jmp     short loc_180074427
0x180074424  mov     rdi, r15
0x180074427  mov     ecx, [rdi+8]
0x18007442a  jmp     short loc_1800743B1
0x18007442c  lea     rax, ??_7?$ClassifiedStructuredEnum@W4ServiceGroupDisabledReason@Privacy@Mso@@@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredEnum<Mso::Privacy::ServiceGroupDisabledReason>::`vftable'
0x180074433  mov     [rbp+90h+var_60], rax
0x180074437  lea     rax, aExpectedSource; "Expected Source"
0x18007443e  mov     [rbp+90h+var_58], rax
0x180074442  mov     al, [rbp+90h+arg_28]
0x180074448  mov     [rbp+90h+var_50], al
0x18007444b  mov     edi, 4
0x180074450  mov     [rbp+90h+var_4E], di
0x180074454  xorps   xmm0, xmm0
0x180074457  movups  xmmword ptr [rbp+90h+Block], xmm0
0x18007445b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180074463  movdqu  [rbp+90h+var_38], xmm1
0x180074468  mov     word ptr [rbp+90h+Block], r15w
0x18007446d  lea     rdx, ?__type_info_root_node@@3U__type_info_node@@A; __type_info_node __type_info_root_node
0x180074474  lea     rcx, qword_1806A3C28
0x18007447b  call    cs:__imp___std_type_info_name
0x180074481  xorps   xmm0, xmm0
0x180074484  movups  [rsp+190h+pExceptionObject], xmm0
0x180074489  xorps   xmm1, xmm1
0x18007448c  movdqu  [rsp+190h+var_138], xmm1
0x180074492  or      r8, 0FFFFFFFFFFFFFFFFh
0x180074496  inc     r8
0x180074499  cmp     [rax+r8], r15b
0x18007449d  jnz     short loc_180074496
0x18007449f  mov     rdx, rax
0x1800744a2  lea     rcx, [rsp+190h+pExceptionObject]
0x1800744a7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800744ac  lea     rax, ??_7?$ClassifiedStructuredObject@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<std::string>::`vftable'
0x1800744b3  mov     [rbp+90h+var_C0], rax
0x1800744b7  lea     rax, aExpectedType; "Expected Type"
0x1800744be  mov     [rbp+90h+var_B8], rax
0x1800744c2  movups  xmm1, [rsp+190h+pExceptionObject]
0x1800744c7  movaps  [rbp+90h+var_B0], xmm1
0x1800744cb  movups  xmm0, [rsp+190h+var_138]
0x1800744d0  movaps  [rbp+90h+var_A0], xmm0
0x1800744d4  mov     [rbp+90h+var_90], di
0x1800744d8  xorps   xmm0, xmm0
0x1800744db  movups  [rbp+90h+var_88], xmm0
0x1800744df  mov     [rbp+90h+var_78], r15
0x1800744e3  mov     [rbp+90h+var_70], 7
0x1800744eb  mov     word ptr [rbp+90h+var_88], r15w
0x1800744f0  movups  [rsp+190h+pExceptionObject], xmm0
0x1800744f5  xorps   xmm1, xmm1
0x1800744f8  movdqu  [rsp+190h+var_138], xmm1
0x1800744fe  mov     r8, [r14+8]
0x180074502  mov     rdx, [r14]
0x180074505  lea     rcx, [rsp+190h+pExceptionObject]
0x18007450a  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18007450f  lea     rax, ??_7?$ClassifiedStructuredObject@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::`vftable'
0x180074516  mov     [rsp+190h+var_120], rax
0x18007451b  lea     rax, aGatename; "GateName"
0x180074522  mov     [rsp+190h+var_118], rax
0x180074527  movups  xmm1, [rsp+190h+pExceptionObject]
0x18007452c  movaps  [rbp+90h+var_110], xmm1
0x180074530  movups  xmm0, [rsp+190h+var_138]
0x180074535  movaps  [rbp+90h+var_100], xmm0
0x180074539  mov     [rbp+90h+var_F0], di
0x18007453d  xorps   xmm0, xmm0
0x180074540  movups  [rbp+90h+var_E8], xmm0
0x180074544  mov     [rbp+90h+var_D8], r15
0x180074548  mov     [rbp+90h+var_D0], 7
0x180074550  mov     word ptr [rbp+90h+var_E8], r15w
0x180074555  lea     rax, aIncorrectTreat; "Incorrect treatment type specified for "...
0x18007455c  mov     [rsp+190h+var_150], rax
0x180074561  lea     rax, [rbp+90h+var_60]
0x180074565  mov     [rsp+190h+var_158], rax
0x18007456a  lea     rax, [rbp+90h+var_C0]
0x18007456e  mov     [rsp+190h+var_160], rax
0x180074573  lea     rax, [rsp+190h+var_120]
0x180074578  mov     [rsp+190h+var_168], rax
0x18007457d  lea     rax, [rsp+190h+var_150]
0x180074582  mov     [rsp+190h+Reserved], rax
0x180074587  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Diagnostics@Mso@@U?$ClassifiedStructuredObject@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$ClassifiedStructuredObject@E@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@01@$$QEAU?$ClassifiedStructuredObject@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@01@$$QEAU?$ClassifiedStructuredObject@E@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>,Mso::Diagnostics::ClassifiedStructuredObject<std::string>,Mso::Diagnostics::ClassifiedStructuredObject<uchar>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<std::wstring> &&,Mso::Diagnostics::ClassifiedStructuredObject<std::string> &&,Mso::Diagnostics::ClassifiedStructuredObject<uchar> &&)
0x18007458c  mov     r14d, 1000h
0x180074592  mov     rax, [rbp+90h+var_D0]
0x180074596  cmp     rax, 7
0x18007459a  jbe     short loc_1800745CB
0x18007459c  mov     rcx, qword ptr [rbp+90h+var_E8]
0x1800745a0  mov     rdx, rcx
0x1800745a3  lea     rax, ds:2[rax*2]
0x1800745ab  cmp     rax, r14
0x1800745ae  jb      short loc_1800745C5
0x1800745b0  mov     rcx, [rcx-8]; Block
0x1800745b4  sub     rdx, rcx
0x1800745b7  lea     rax, [rdx-8]
0x1800745bb  cmp     rax, 1Fh
0x1800745bf  ja      loc_1800746E3
0x1800745c5  call    cs:__imp_free
0x1800745cb  mov     edi, 4DE1h
0x1800745d0  mov     qword ptr [rbp+90h+var_E8], rdi
0x1800745d4  mov     [rbp+90h+var_D8], r15
0x1800745d8  mov     [rbp+90h+var_D0], 0Fh
0x1800745e0  mov     rax, qword ptr [rbp+90h+var_100+8]
0x1800745e4  cmp     rax, 7
0x1800745e8  jbe     short loc_180074619
0x1800745ea  mov     rcx, qword ptr [rbp+90h+var_110]
0x1800745ee  mov     rdx, rcx
0x1800745f1  lea     rax, ds:2[rax*2]
0x1800745f9  cmp     rax, r14
0x1800745fc  jb      short loc_180074613
0x1800745fe  mov     rcx, [rcx-8]; Block
0x180074602  sub     rdx, rcx
0x180074605  lea     rax, [rdx-8]
0x180074609  cmp     rax, 1Fh
0x18007460d  ja      loc_1800746E3
0x180074613  call    cs:__imp_free
0x180074619  mov     qword ptr [rbp+90h+var_110], rdi
0x18007461d  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180074625  movdqa  [rbp+90h+var_100], xmm0
0x18007462a  mov     rax, [rbp+90h+var_70]
0x18007462e  cmp     rax, 7
0x180074632  jbe     short loc_180074663
0x180074634  mov     rcx, qword ptr [rbp+90h+var_88]
0x180074638  mov     rdx, rcx
0x18007463b  lea     rax, ds:2[rax*2]
0x180074643  cmp     rax, r14
0x180074646  jb      short loc_18007465D
0x180074648  mov     rcx, [rcx-8]; Block
0x18007464c  sub     rdx, rcx
0x18007464f  lea     rax, [rdx-8]
0x180074653  cmp     rax, 1Fh
0x180074657  ja      loc_1800746E3
0x18007465d  call    cs:__imp_free
0x180074663  mov     qword ptr [rbp+90h+var_88], rdi
0x180074667  mov     [rbp+90h+var_78], r15
0x18007466b  mov     [rbp+90h+var_70], 0Fh
0x180074673  mov     rax, qword ptr [rbp+90h+var_A0+8]
0x180074677  cmp     rax, 0Fh
0x18007467b  jbe     short loc_1800746A3
0x18007467d  mov     rcx, qword ptr [rbp+90h+var_B0]
0x180074681  mov     rdx, rcx
0x180074684  inc     rax
0x180074687  cmp     rax, r14
0x18007468a  jb      short loc_18007469D
0x18007468c  mov     rcx, [rcx-8]; Block
0x180074690  sub     rdx, rcx
0x180074693  lea     rax, [rdx-8]
0x180074697  cmp     rax, 1Fh
0x18007469b  ja      short loc_1800746E3
0x18007469d  call    cs:__imp_free
0x1800746a3  mov     qword ptr [rbp+90h+var_B0], rdi
0x1800746a7  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x1800746af  movdqa  [rbp+90h+var_A0], xmm0
0x1800746b4  mov     rax, qword ptr [rbp+90h+var_38+8]
0x1800746b8  cmp     rax, 7
0x1800746bc  jbe     short loc_1800746FF
0x1800746be  mov     rcx, [rbp+90h+Block]; Block
0x1800746c2  mov     rdx, rcx
0x1800746c5  lea     rax, ds:2[rax*2]
0x1800746cd  cmp     rax, r14
0x1800746d0  jb      short loc_1800746F9
0x1800746d2  mov     rcx, [rcx-8]
0x1800746d6  sub     rdx, rcx
0x1800746d9  lea     rax, [rdx-8]
0x1800746dd  cmp     rax, 1Fh
0x1800746e1  jbe     short loc_1800746F9
0x1800746e3  mov     [rsp+190h+Reserved], r15; Reserved
0x1800746e8  xor     r9d, r9d; LineNo
0x1800746eb  xor     r8d, r8d; FileName
0x1800746ee  xor     edx, edx; FunctionName
0x1800746f0  xor     ecx, ecx; Expression
0x1800746f2  call    cs:__imp__invoke_watson
0x1800746f9  call    cs:__imp_free
0x1800746ff  call    ?Instance@ExperimentationFactory@Experiment@Mso@@SAAEAV123@XZ; Mso::Experiment::ExperimentationFactory::Instance(void)
0x180074704  mov     rcx, [rax+20h]
0x180074708  mov     rax, [rcx]
0x18007470b  xor     edx, edx
0x18007470d  mov     rax, [rax+8]
0x180074711  call    cs:__guard_dispatch_icall_fptr
0x180074717  test    al, al
0x180074719  jnz     short loc_180074760
0x18007471b  cmp     [rsi], r15b
0x18007471e  jnz     short loc_180074733
0x180074720  mov     byte ptr [rbx], 1
0x180074723  mov     rax, [rbp+90h+arg_20]
0x18007472a  mov     rcx, [rax]
0x18007472d  mov     [rbx+8], rcx
0x180074731  jmp     short loc_18007473A
0x180074733  movups  xmm0, xmmword ptr [rsi]
0x180074736  movdqu  xmmword ptr [rbx], xmm0
0x18007473a  mov     rax, rbx
0x18007473d  mov     rcx, [rbp+90h+var_28]
0x180074741  xor     rcx, rsp; StackCookie
0x180074744  call    __security_check_cookie
0x180074749  mov     rbx, [rsp+190h+arg_10]
0x180074751  add     rsp, 170h
0x180074758  pop     r15
0x18007475a  pop     r14
0x18007475c  pop     rdi
0x18007475d  pop     rsi
0x18007475e  pop     rbp
0x18007475f  retn
0x180074760  xor     edx, edx; struct CrashContext *
0x180074762  mov     ecx, 21050011h; unsigned int
0x180074767  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18007476d  lea     rcx, [rsp+190h+pExceptionObject]; this
0x180074772  call    ??0bad_cast@std@@QEAA@XZ; std::bad_cast::bad_cast(void)
0x180074777  lea     rdx, _TI2?AVbad_cast@std@@; pThrowInfo
0x18007477e  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x180074783  call    _CxxThrowException_0
```
