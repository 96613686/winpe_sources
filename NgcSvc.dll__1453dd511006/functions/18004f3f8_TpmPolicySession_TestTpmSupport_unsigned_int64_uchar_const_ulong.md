# TpmPolicySession::TestTpmSupport(unsigned __int64,uchar const *,ulong)

- ea: `0x18004f3f8`
- end: `0x18004fae9`
- name: `?TestTpmSupport@TpmPolicySession@@YAJ_KPEBEK@Z`
- size: `1777`
- prototype: `__int64 __fastcall(TpmPolicySession *__hidden this, unsigned __int64, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004f218`

## callees

- `0x18000782c`
- `0x180010990`
- `0x180011c04`
- `0x180022964`
- `0x180022980`
- `0x180028ca0`
- `0x18002c9d8`
- `0x180031090`
- `0x18004ed74`
- `0x18004f3f8`
- `0x180069998`
- `0x180069c28`
- `0x1800a83ac`
- `0x1800a8604`
- `0x1800a89ac`
- `0x1800a8b00`
- `0x1800a8d4c`
- `0x1800a8dbc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f4b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f5f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f614`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f6ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f6cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f7aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f7ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f8e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f904`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f9fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fa20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fa94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fab8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f4b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f5f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f614`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f6ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f6cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f7aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f7ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f8e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f904`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f9fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fa20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fa94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fab8`

## string_xrefs

- `0x18004f495`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x18004f5cf`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x18004f67c`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x18004f76e`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x18004f890`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x18004f992`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall TpmPolicySession::TestTpmSupport(TpmPolicySession *this, UCHAR *a2, const unsigned __int8 *a3)
{
  ULONG v3; // esi
  int PolicyInfo; // ebx
  HLOCAL v7; // rcx
  __m128i *v8; // rax
  __int64 v9; // rcx
  __m128i si128; // xmm0
  HLOCAL v11; // rcx
  HLOCAL v12; // rcx
  int v13; // eax
  HLOCAL v14; // rcx
  HLOCAL v15; // rcx
  int AuthorizationHmac; // eax
  HLOCAL v17; // rcx
  HLOCAL v18; // rcx
  __int64 v19; // rcx
  TpmPolicySession *v20; // rdx
  HLOCAL v21; // rcx
  HLOCAL v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  void *v25; // rdx
  TpmPolicySession *v26; // rdx
  HLOCAL v27; // rcx
  HLOCAL v28; // rcx
  const char *v29; // r9
  __int64 result; // rax
  void *v31; // rdx
  TpmPolicySession *v32; // rdx
  HLOCAL v33; // rcx
  HLOCAL v34; // rcx
  int v35; // [rsp+20h] [rbp-128h]
  unsigned int *v36; // [rsp+20h] [rbp-128h]
  int v37; // [rsp+20h] [rbp-128h]
  int v38; // [rsp+20h] [rbp-128h]
  int v39; // [rsp+20h] [rbp-128h]
  int v40; // [rsp+20h] [rbp-128h]
  unsigned int *v41; // [rsp+28h] [rbp-120h]
  ULONG v42[2]; // [rsp+28h] [rbp-120h]
  const unsigned __int8 *cbOutput; // [rsp+38h] [rbp-110h]
  HLOCAL hMem; // [rsp+50h] [rbp-F8h] BYREF
  HLOCAL v45; // [rsp+58h] [rbp-F0h] BYREF
  TpmPolicySession *v46; // [rsp+60h] [rbp-E8h] BYREF
  _BYTE *p_hMem; // [rsp+68h] [rbp-E0h] BYREF
  unsigned int v48[2]; // [rsp+70h] [rbp-D8h] BYREF
  char v49; // [rsp+78h] [rbp-D0h]
  UCHAR v50[4]; // [rsp+80h] [rbp-C8h] BYREF
  _BYTE v51[12]; // [rsp+84h] [rbp-C4h] BYREF
  PUCHAR v52; // [rsp+90h] [rbp-B8h] BYREF
  int v53; // [rsp+98h] [rbp-B0h]
  unsigned int v54[4]; // [rsp+A8h] [rbp-A0h] BYREF
  __int64 v55; // [rsp+B8h] [rbp-90h]
  PUCHAR pbInput; // [rsp+C0h] [rbp-88h] BYREF
  int v57; // [rsp+C8h] [rbp-80h]
  PUCHAR v58; // [rsp+D8h] [rbp-70h] BYREF
  int v59; // [rsp+E0h] [rbp-68h]
  unsigned __int8 *v60; // [rsp+F0h] [rbp-58h] BYREF
  const void *v61[10]; // [rsp+F8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]
  unsigned __int8 *v63; // [rsp+168h] [rbp+20h] BYREF

  v3 = (unsigned int)a3;
  LOBYTE(v63) = 2;
  try
  {
    std::vector<unsigned char>::vector<unsigned char>();
    hMem = 0;
    LODWORD(v63) = 0;
    p_hMem = &hMem;
    *(_QWORD *)v48 = 0;
    v49 = 1;
    PolicyInfo = TpmPolicySession::GetPolicyInfo((NCRYPT_HANDLE)this, v52, v53 - (int)v52, (unsigned int)v48, &v63, v41);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
    if ( PolicyInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21A,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)PolicyInfo,
        v35);
      v7 = hMem;
      hMem = 0;
      if ( v7 )
        LocalFree(v7);
LABEL_43:
      std::vector<unsigned char>::_Tidy(&v52);
      return (unsigned int)PolicyInfo;
    }
    LODWORD(v61[0]) = (_DWORD)v63;
    v61[1] = hMem;
    *(_OWORD *)v54 = 0;
    v55 = 0;
    std::vector<unsigned char>::_Buy_nonzero(v54, 32);
    v8 = *(__m128i **)v54;
    v9 = 32;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    **(_OWORD **)v54 = si128;
    v8[1] = si128;
    do
    {
      v8 = (__m128i *)((char *)v8 + 1);
      --v9;
    }
    while ( v9 );
    *(_QWORD *)&v54[2] = v8;
    v63 = 0;
    std::_Tidy_guard<std::vector<unsigned char,wil::secure_allocator<unsigned char>>>::~_Tidy_guard<std::vector<unsigned char,wil::secure_allocator<unsigned char>>>(&v63);
    v45 = 0;
    LODWORD(v63) = 0;
    p_hMem = &v45;
    *(_QWORD *)v48 = 0;
    v49 = 1;
    PolicyInfo = TpmPolicySession::SealWithPolicyInfo(
                   v61,
                   (const struct TpmPolicySession::PolicyInfo *)1,
                   *(BYTE **)v54,
                   (const unsigned __int8 *)(v54[2] - v54[0]),
                   (PBYTE *)v48,
                   &v63);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
    if ( PolicyInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22C,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)PolicyInfo,
        (int)v36);
      v11 = v45;
      v45 = 0;
      if ( v11 )
        LocalFree(v11);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v54);
      v12 = hMem;
      hMem = 0;
      if ( v12 )
        LocalFree(v12);
      goto LABEL_43;
    }
    std::vector<unsigned char>::vector<unsigned char>(&pbInput, 32);
    *(_DWORD *)v50 = 0;
    v13 = TpmPolicySession::OpenSession(
            this,
            (unsigned __int64)pbInput,
            (unsigned __int8 *)(unsigned int)(v57 - (_DWORD)pbInput),
            (unsigned int)v50,
            v36);
    PolicyInfo = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x237,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)v13,
        v37);
      std::vector<unsigned char>::_Tidy(&pbInput);
      v14 = v45;
      v45 = 0;
      if ( v14 )
        LocalFree(v14);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v54);
      v15 = hMem;
      hMem = 0;
      if ( v15 )
        LocalFree(v15);
      goto LABEL_43;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
      &v58,
      32);
    AuthorizationHmac = TpmPolicySession::GenerateAuthorizationHmac(
                          a2,
                          v3,
                          pbInput,
                          v57 - (int)pbInput,
                          v52,
                          v53 - (int)v52,
                          v58,
                          v59 - (int)v58,
                          v50);
    PolicyInfo = AuthorizationHmac;
    if ( AuthorizationHmac < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)AuthorizationHmac,
        v38);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v58);
      std::vector<unsigned char>::_Tidy(&pbInput);
      v17 = v45;
      v45 = 0;
      if ( v17 )
        LocalFree(v17);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v54);
      v18 = hMem;
      hMem = 0;
      if ( v18 )
        LocalFree(v18);
      goto LABEL_43;
    }
    v46 = 0;
    *(_DWORD *)v51 = 0;
    p_hMem = &v46;
    *(_QWORD *)v48 = 0;
    v49 = 1;
    LODWORD(cbOutput) = v59 - (_DWORD)v58;
    v42[0] = v53 - (_DWORD)v52;
    PolicyInfo = TpmPolicySession::GetTpmTicket(
                   (NCRYPT_HANDLE)this,
                   (unsigned __int64)v58,
                   (int)pbInput,
                   (const unsigned __int8 *)(unsigned int)(v57 - (_DWORD)pbInput),
                   v52,
                   *(rsize_t *)v42,
                   v58,
                   cbOutput,
                   (unsigned int)v48,
                   (unsigned __int8 **)v51,
                   (unsigned int *)hMem);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hMem);
    if ( PolicyInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x257,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)PolicyInfo,
        v39);
      v20 = v46;
      v46 = 0;
      if ( v20 )
        wil::hlocal_secure_deleter::operator()<unsigned char>(v19, v20);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v58);
      std::vector<unsigned char>::_Tidy(&pbInput);
      v21 = v45;
      v45 = 0;
      if ( v21 )
        LocalFree(v21);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v54);
      v22 = hMem;
      hMem = 0;
      if ( v22 )
        LocalFree(v22);
      goto LABEL_43;
    }
    *(_QWORD *)&v51[4] = 0;
    p_hMem = &v51[4];
    *(_QWORD *)v48 = 0;
    v49 = 1;
    PolicyInfo = TpmPolicySession::UnSealWithTpmTicket(
                   v46,
                   (const unsigned __int8 *)*(unsigned int *)v51,
                   (BYTE *)v45,
                   (const unsigned __int8 *)(unsigned int)v63,
                   (PBYTE *)v48,
                   &v60);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hMem);
    if ( PolicyInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x264,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)PolicyInfo,
        v40);
      v25 = *(void **)&v51[4];
      *(_QWORD *)&v51[4] = 0;
      if ( v25 )
        wil::hlocal_secure_deleter::operator()<unsigned char>(v24, v25);
      v26 = v46;
      v46 = 0;
      if ( v26 )
        wil::hlocal_secure_deleter::operator()<unsigned char>(v24, v26);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v58);
      std::vector<unsigned char>::_Tidy(&pbInput);
      v27 = v45;
      v45 = 0;
      if ( v27 )
        LocalFree(v27);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v54);
      v28 = hMem;
      hMem = 0;
      if ( v28 )
        LocalFree(v28);
      goto LABEL_43;
    }
    v31 = *(void **)&v51[4];
    *(_QWORD *)&v51[4] = 0;
    if ( v31 )
      wil::hlocal_secure_deleter::operator()<unsigned char>(v23, v31);
    v32 = v46;
    v46 = 0;
    if ( v32 )
      wil::hlocal_secure_deleter::operator()<unsigned char>(v23, v32);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v58);
    std::vector<unsigned char>::_Tidy(&pbInput);
    v33 = v45;
    v45 = 0;
    if ( v33 )
      LocalFree(v33);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v54);
    v34 = hMem;
    hMem = 0;
    if ( v34 )
      LocalFree(v34);
    std::vector<unsigned char>::_Tidy(&v52);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v63) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x266,
                     (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                     v29);
    return (unsigned int)v63;
  }
  return result;
}

```

## disassembly

```asm
0x18004f3f8  mov     rax, rsp
0x18004f3fb  push    rbx
0x18004f3fc  push    rsi
0x18004f3fd  push    rdi
0x18004f3fe  push    r12
0x18004f400  push    r14
0x18004f402  push    r15
0x18004f404  sub     rsp, 118h
0x18004f40b  mov     esi, r8d
0x18004f40e  mov     r14, rdx
0x18004f411  mov     rdi, rcx
0x18004f414  mov     byte ptr [rax+20h], 2
0x18004f418  lea     r8, [rax+20h]
0x18004f41c  lea     rcx, [rax-0B8h]
0x18004f423  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x18004f428  nop
0x18004f429  xor     r15d, r15d
0x18004f42c  mov     [rsp+148h+hMem], r15; unsigned int *
0x18004f431  mov     dword ptr [rsp+148h+arg_18], r15d
0x18004f439  lea     rax, [rsp+148h+hMem]
0x18004f43e  mov     [rsp+148h+var_E0], rax
0x18004f443  mov     qword ptr [rsp+148h+var_D8], r15
0x18004f448  mov     [rsp+148h+var_D0], 1
0x18004f44d  mov     rdx, [rsp+148h+var_B8]; pbInput
0x18004f455  mov     r8d, [rsp+148h+var_B0]
0x18004f45d  sub     r8d, edx; cbInput
0x18004f460  lea     rax, [rsp+148h+arg_18]
0x18004f468  mov     [rsp+148h+var_128], rax; int
0x18004f46d  lea     r9, [rsp+148h+var_D8]; unsigned int
0x18004f472  mov     rcx, rdi; hObject
0x18004f475  call    ?GetPolicyInfo@TpmPolicySession@@YAJ_KPEBEKPEAPEAEPEAK@Z; TpmPolicySession::GetPolicyInfo(unsigned __int64,uchar const *,ulong,uchar * *,ulong *)
0x18004f47a  mov     ebx, eax
0x18004f47c  lea     rcx, [rsp+148h+var_E0]
0x18004f481  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004f486  test    ebx, ebx
0x18004f488  jns     short loc_18004F4D1
0x18004f48a  mov     rcx, [rsp+148h]; this
0x18004f492  mov     r9d, ebx; char *
0x18004f495  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x18004f49c  mov     edx, 21Ah; void *
0x18004f4a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f4a6  nop
0x18004f4a7  mov     rcx, [rsp+148h+hMem]; hMem
0x18004f4ac  mov     [rsp+148h+hMem], r15
0x18004f4b1  test    rcx, rcx
0x18004f4b4  jz      short loc_18004F4BD
0x18004f4b6  call    cs:__imp_LocalFree
0x18004f4bc  nop
0x18004f4bd  lea     rcx, [rsp+148h+var_B8]
0x18004f4c5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004f4ca  mov     eax, ebx
0x18004f4cc  jmp     loc_18004FAD8
0x18004f4d1  mov     eax, dword ptr [rsp+148h+arg_18]
0x18004f4d8  mov     [rsp+148h+var_50], eax
0x18004f4df  mov     rax, [rsp+148h+hMem]
0x18004f4e4  mov     [rsp+148h+var_48], rax
0x18004f4ec  xorps   xmm0, xmm0
0x18004f4ef  movdqu  xmmword ptr [rsp+148h+var_A0], xmm0
0x18004f4f8  mov     [rsp+148h+var_90], r15
0x18004f500  mov     r12d, 20h ; ' '
0x18004f506  mov     edx, r12d
0x18004f509  lea     rcx, [rsp+148h+var_A0]
0x18004f511  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x18004f516  mov     rax, qword ptr [rsp+148h+var_A0]
0x18004f51e  mov     ecx, r12d
0x18004f521  movdqa  xmm0, cs:__xmm@03030303030303030303030303030303
0x18004f529  movups  xmmword ptr [rax], xmm0
0x18004f52c  movups  xmmword ptr [rax+10h], xmm0
0x18004f530  inc     rax
0x18004f533  sub     rcx, 1
0x18004f537  jnz     short loc_18004F530
0x18004f539  mov     qword ptr [rsp+148h+var_A0+8], rax
0x18004f541  mov     [rsp+148h+arg_18], r15
0x18004f549  lea     rcx, [rsp+148h+arg_18]
0x18004f551  call    ??1?$_Tidy_guard@V?$vector@EU?$secure_allocator@E@wil@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar,wil::secure_allocator<uchar>>>::~_Tidy_guard<std::vector<uchar,wil::secure_allocator<uchar>>>(void)
0x18004f556  nop
0x18004f557  mov     [rsp+148h+var_F0], r15
0x18004f55c  mov     dword ptr [rsp+148h+arg_18], r15d
0x18004f564  lea     rax, [rsp+148h+var_F0]
0x18004f569  mov     [rsp+148h+var_E0], rax
0x18004f56e  mov     qword ptr [rsp+148h+var_D8], r15
0x18004f573  mov     [rsp+148h+var_D0], 1
0x18004f578  mov     r8, qword ptr [rsp+148h+var_A0]; unsigned int
0x18004f580  mov     r9d, [rsp+148h+var_A0+8]
0x18004f588  sub     r9d, r8d; unsigned __int8 *
0x18004f58b  lea     rax, [rsp+148h+arg_18]
0x18004f593  mov     qword ptr [rsp+148h+var_120], rax; unsigned __int8 **
0x18004f598  lea     rax, [rsp+148h+var_D8]
0x18004f59d  mov     [rsp+148h+var_128], rax; int
0x18004f5a2  mov     edx, 1; struct TpmPolicySession::PolicyInfo *
0x18004f5a7  lea     rcx, [rsp+148h+var_50]; this
0x18004f5af  call    ?SealWithPolicyInfo@TpmPolicySession@@YAJPEBUPolicyInfo@1@KPEBEKPEAPEAEPEAK@Z; TpmPolicySession::SealWithPolicyInfo(TpmPolicySession::PolicyInfo const *,ulong,uchar const *,ulong,uchar * *,ulong *)
0x18004f5b4  mov     ebx, eax
0x18004f5b6  lea     rcx, [rsp+148h+var_E0]
0x18004f5bb  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004f5c0  test    ebx, ebx
0x18004f5c2  jns     short loc_18004F62F
0x18004f5c4  mov     rcx, [rsp+148h]; this
0x18004f5cc  mov     r9d, ebx; char *
0x18004f5cf  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x18004f5d6  mov     edx, 22Ch; void *
0x18004f5db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f5e0  nop
0x18004f5e1  mov     rcx, [rsp+148h+var_F0]; hMem
0x18004f5e6  mov     [rsp+148h+var_F0], r15
0x18004f5eb  test    rcx, rcx
0x18004f5ee  jz      short loc_18004F5F7
0x18004f5f0  call    cs:__imp_LocalFree
0x18004f5f6  nop
0x18004f5f7  lea     rcx, [rsp+148h+var_A0]
0x18004f5ff  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18004f604  nop
0x18004f605  mov     rcx, [rsp+148h+hMem]; hMem
0x18004f60a  mov     [rsp+148h+hMem], r15
0x18004f60f  test    rcx, rcx
0x18004f612  jz      short loc_18004F61B
0x18004f614  call    cs:__imp_LocalFree
0x18004f61a  nop
0x18004f61b  lea     rcx, [rsp+148h+var_B8]
0x18004f623  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004f628  mov     eax, ebx
0x18004f62a  jmp     loc_18004FAD8
0x18004f62f  mov     rdx, r12
0x18004f632  lea     rcx, [rsp+148h+pbInput]
0x18004f63a  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18004f63f  nop
0x18004f640  mov     dword ptr [rsp+148h+var_C8], r15d
0x18004f648  mov     rdx, [rsp+148h+pbInput]; unsigned __int64
0x18004f650  mov     r8d, [rsp+148h+var_80]
0x18004f658  sub     r8d, edx; unsigned __int8 *
0x18004f65b  lea     r9, [rsp+148h+var_C8]; unsigned int
0x18004f663  mov     rcx, rdi; this
0x18004f666  call    ?OpenSession@TpmPolicySession@@YAJ_KPEAEKPEAK@Z; TpmPolicySession::OpenSession(unsigned __int64,uchar *,ulong,ulong *)
0x18004f66b  mov     ebx, eax
0x18004f66d  test    eax, eax
0x18004f66f  jns     short loc_18004F6EA
0x18004f671  mov     rcx, [rsp+148h]; this
0x18004f679  mov     r9d, eax; char *
0x18004f67c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x18004f683  mov     edx, 237h; void *
0x18004f688  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f68d  nop
0x18004f68e  lea     rcx, [rsp+148h+pbInput]
0x18004f696  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004f69b  nop
0x18004f69c  mov     rcx, [rsp+148h+var_F0]; hMem
0x18004f6a1  mov     [rsp+148h+var_F0], r15
0x18004f6a6  test    rcx, rcx
0x18004f6a9  jz      short loc_18004F6B2
0x18004f6ab  call    cs:__imp_LocalFree
0x18004f6b1  nop
0x18004f6b2  lea     rcx, [rsp+148h+var_A0]
0x18004f6ba  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18004f6bf  nop
0x18004f6c0  mov     rcx, [rsp+148h+hMem]; hMem
0x18004f6c5  mov     [rsp+148h+hMem], r15
0x18004f6ca  test    rcx, rcx
0x18004f6cd  jz      short loc_18004F6D6
0x18004f6cf  call    cs:__imp_LocalFree
0x18004f6d5  nop
0x18004f6d6  lea     rcx, [rsp+148h+var_B8]
0x18004f6de  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004f6e3  mov     eax, ebx
0x18004f6e5  jmp     loc_18004FAD8
0x18004f6ea  mov     rdx, r12
0x18004f6ed  lea     rcx, [rsp+148h+var_70]
0x18004f6f5  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x18004f6fa  mov     rdx, [rsp+148h+var_70]
0x18004f702  mov     r10, [rsp+148h+var_B8]
0x18004f70a  mov     r8, [rsp+148h+pbInput]; pbInput
0x18004f712  mov     ecx, [rsp+148h+var_68]
0x18004f719  sub     ecx, edx
0x18004f71b  mov     eax, [rsp+148h+var_B0]
0x18004f722  sub     eax, r10d
0x18004f725  mov     r9d, [rsp+148h+var_80]
0x18004f72d  sub     r9d, r8d; cbInput
0x18004f730  lea     r11, [rsp+148h+var_C8]
0x18004f738  mov     qword ptr [rsp+148h+var_108], r11; UCHAR
0x18004f73d  mov     dword ptr [rsp+148h+cbOutput], ecx; cbOutput
0x18004f741  mov     [rsp+148h+var_118], rdx; PUCHAR
0x18004f746  mov     [rsp+148h+var_120], eax; ULONG
0x18004f74a  mov     [rsp+148h+var_128], r10; int
0x18004f74f  mov     edx, esi; cbSecret
0x18004f751  mov     rcx, r14; this
0x18004f754  call    ?GenerateAuthorizationHmac@TpmPolicySession@@YAJPEBEK0K0KPEAEKPEAK@Z; TpmPolicySession::GenerateAuthorizationHmac(uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar *,ulong,ulong *)
0x18004f759  mov     ebx, eax
0x18004f75b  test    eax, eax
0x18004f75d  jns     loc_18004F7E9
0x18004f763  mov     rcx, [rsp+148h]; this
0x18004f76b  mov     r9d, eax; char *
0x18004f76e  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x18004f775  mov     edx, 246h; void *
0x18004f77a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f77f  lea     rcx, [rsp+148h+var_70]
0x18004f787  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18004f78c  nop
0x18004f78d  lea     rcx, [rsp+148h+pbInput]
0x18004f795  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004f79a  nop
0x18004f79b  mov     rcx, [rsp+148h+var_F0]; hMem
0x18004f7a0  mov     [rsp+148h+var_F0], r15
0x18004f7a5  test    rcx, rcx
0x18004f7a8  jz      short loc_18004F7B1
0x18004f7aa  call    cs:__imp_LocalFree
0x18004f7b0  nop
0x18004f7b1  lea     rcx, [rsp+148h+var_A0]
0x18004f7b9  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18004f7be  nop
0x18004f7bf  mov     rcx, [rsp+148h+hMem]; hMem
0x18004f7c4  mov     [rsp+148h+hMem], r15
0x18004f7c9  test    rcx, rcx
0x18004f7cc  jz      short loc_18004F7D5
0x18004f7ce  call    cs:__imp_LocalFree
0x18004f7d4  nop
0x18004f7d5  lea     rcx, [rsp+148h+var_B8]
0x18004f7dd  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004f7e2  mov     eax, ebx
0x18004f7e4  jmp     loc_18004FAD8
0x18004f7e9  mov     [rsp+148h+var_E8], r15
0x18004f7ee  mov     dword ptr [rsp+148h+var_C4], r15d
0x18004f7f6  lea     rax, [rsp+148h+var_E8]
0x18004f7fb  mov     [rsp+148h+var_E0], rax
0x18004f800  mov     qword ptr [rsp+148h+var_D8], r15
0x18004f805  mov     [rsp+148h+var_D0], 1
0x18004f80a  mov     rdx, [rsp+148h+var_70]; unsigned __int64
0x18004f812  mov     r10, [rsp+148h+var_B8]
0x18004f81a  mov     r8, [rsp+148h+pbInput]; int
0x18004f822  mov     ecx, [rsp+148h+var_68]
0x18004f829  sub     ecx, edx
0x18004f82b  mov     eax, [rsp+148h+var_B0]
0x18004f832  sub     eax, r10d
0x18004f835  mov     r9d, [rsp+148h+var_80]
0x18004f83d  sub     r9d, r8d; unsigned __int8 *
0x18004f840  lea     r11, [rsp+148h+var_C4]
0x18004f848  mov     [rsp+148h+var_100], r11; unsigned __int8 **
0x18004f84d  lea     r11, [rsp+148h+var_D8]
0x18004f852  mov     qword ptr [rsp+148h+var_108], r11; unsigned int
0x18004f857  mov     dword ptr [rsp+148h+cbOutput], ecx; unsigned __int8 *
0x18004f85b  mov     [rsp+148h+var_118], rdx; unsigned int *
0x18004f860  mov     [rsp+148h+var_120], eax; SourceSize
0x18004f864  mov     [rsp+148h+var_128], r10; int
0x18004f869  mov     rcx, rdi; hObject
0x18004f86c  call    ?GetTpmTicket@TpmPolicySession@@YAJ_KHPEBEK1K1KPEAPEAEPEAK@Z; TpmPolicySession::GetTpmTicket(unsigned __int64,int,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *)
0x18004f871  mov     ebx, eax
0x18004f873  lea     rcx, [rsp+148h+var_E0]
0x18004f878  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x18004f87d  test    ebx, ebx
0x18004f87f  jns     loc_18004F91F
0x18004f885  mov     rcx, [rsp+148h]; this
0x18004f88d  mov     r9d, ebx; char *
0x18004f890  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x18004f897  mov     edx, 257h; void *
0x18004f89c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f8a1  mov     rdx, [rsp+148h+var_E8]
0x18004f8a6  mov     [rsp+148h+var_E8], r15
0x18004f8ab  test    rdx, rdx
0x18004f8ae  jz      short loc_18004F8B5
0x18004f8b0  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x18004f8b5  lea     rcx, [rsp+148h+var_70]
0x18004f8bd  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18004f8c2  nop
0x18004f8c3  lea     rcx, [rsp+148h+pbInput]
0x18004f8cb  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004f8d0  nop
0x18004f8d1  mov     rcx, [rsp+148h+var_F0]; hMem
0x18004f8d6  mov     [rsp+148h+var_F0], r15
0x18004f8db  test    rcx, rcx
0x18004f8de  jz      short loc_18004F8E7
0x18004f8e0  call    cs:__imp_LocalFree
0x18004f8e6  nop
0x18004f8e7  lea     rcx, [rsp+148h+var_A0]
0x18004f8ef  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18004f8f4  nop
0x18004f8f5  mov     rcx, [rsp+148h+hMem]; hMem
0x18004f8fa  mov     [rsp+148h+hMem], r15
0x18004f8ff  test    rcx, rcx
0x18004f902  jz      short loc_18004F90B
0x18004f904  call    cs:__imp_LocalFree
0x18004f90a  nop
0x18004f90b  lea     rcx, [rsp+148h+var_B8]
0x18004f913  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004f918  mov     eax, ebx
0x18004f91a  jmp     loc_18004FAD8
0x18004f91f  mov     qword ptr [rsp+148h+var_C4+4], r15
0x18004f927  lea     rax, [rsp+148h+var_C4+4]
0x18004f92f  mov     [rsp+148h+var_E0], rax
0x18004f934  mov     qword ptr [rsp+148h+var_D8], r15
0x18004f939  mov     [rsp+148h+var_D0], 1
0x18004f93e  lea     rax, [rsp+148h+var_58]
0x18004f946  mov     qword ptr [rsp+148h+var_120], rax; unsigned __int8 **
0x18004f94b  lea     rax, [rsp+148h+var_D8]
0x18004f950  mov     [rsp+148h+var_128], rax; int
0x18004f955  mov     r9d, dword ptr [rsp+148h+arg_18]; unsigned __int8 *
0x18004f95d  mov     r8, [rsp+148h+var_F0]; unsigned int
0x18004f962  mov     edx, dword ptr [rsp+148h+var_C4]; unsigned __int8 *
0x18004f969  mov     rcx, [rsp+148h+var_E8]; this
0x18004f96e  call    ?UnSealWithTpmTicket@TpmPolicySession@@YAJPEBEK0KPEAPEAEPEAK@Z; TpmPolicySession::UnSealWithTpmTicket(uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *)
0x18004f973  mov     ebx, eax
0x18004f975  lea     rcx, [rsp+148h+var_E0]
0x18004f97a  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
  ... truncated ...
```
