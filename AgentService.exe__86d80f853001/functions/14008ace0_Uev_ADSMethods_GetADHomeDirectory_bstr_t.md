# Uev::ADSMethods::GetADHomeDirectory(_bstr_t &)

- ea: `0x14008ace0`
- end: `0x14008b421`
- name: `?GetADHomeDirectory@ADSMethods@Uev@@UEBAJAEAV_bstr_t@@@Z`
- size: `1857`
- prototype: `int(Uev::ADSMethods *__hidden this, struct _bstr_t *)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x14000ba60`
- `0x14000bacc`
- `0x14000c1cc`
- `0x14000c2b8`
- `0x140015190`
- `0x1400205f4`
- `0x1400218a0`
- `0x1400231f8`
- `0x140046e04`
- `0x140046f94`
- `0x1400663e4`
- `0x140087a7c`
- `0x140089d54`
- `0x14008ace0`
- `0x14008b428`
- `0x14009b010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x14008ad8b`
- `OLEAUT32!__imp_SysStringLen` at `0x14008b27c`
- `OLEAUT32!__imp_SysStringLen` at `0x14008ad8b`
- `OLEAUT32!__imp_SysStringLen` at `0x14008b27c`
- `ACTIVEDS!__imp_ADsGetObject` at `0x14008af7c`
- `ACTIVEDS!__imp_ADsGetObject` at `0x14008af7c`

## string_xrefs

- `0x14008ad1c`: `ADSMethods::GetADHomeDirectory`
- `0x14008b18f`: `IADsUser::get_HomeDirectory for user DN `
- `0x14008aff0`: `ADsGetObject failed for LDAP path: '`
- `0x14008b2d6`: `AD Home directory is not defined for user DN `

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall Uev::ADSMethods::GetADHomeDirectory(Uev::ADSMethods *this, struct _bstr_t *a2)
{
  HRESULT CurrentUserDN; // edi
  const void **v4; // rbx
  UINT v5; // eax
  const void *v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rcx
  _QWORD *v9; // r12
  __int64 v10; // r8
  __int64 v11; // r14
  __int128 *v12; // rax
  __m128i *v13; // rax
  _QWORD *v14; // r14
  _WORD *v15; // rdx
  unsigned __int64 v16; // r8
  void *v17; // rcx
  const WCHAR *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  _QWORD *v21; // r14
  __int64 v22; // rbx
  __int64 v23; // r8
  LPCWSTR *v24; // rax
  __m128i *v25; // rax
  _QWORD *v26; // rbx
  void *v27; // rbx
  __int64 v28; // rdi
  _QWORD *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  _QWORD *v32; // r14
  __int64 v33; // rbx
  __int64 v34; // r8
  LPCWSTR *v35; // rax
  __m128i *v36; // rax
  _QWORD *v37; // rbx
  OLECHAR *v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rdx
  _QWORD *v42; // rbx
  __int64 v43; // r8
  LPCWSTR *v44; // rax
  __m128i *v45; // rax
  __m128i v46; // xmm6
  __m128i v47; // xmm7
  __m128i *v48; // r9
  _QWORD *v50; // [rsp+48h] [rbp-C0h] BYREF
  BSTR *v51; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v52; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v53; // [rsp+68h] [rbp-A0h]
  __m128i v54; // [rsp+78h] [rbp-90h] BYREF
  __m128i v55; // [rsp+88h] [rbp-80h]
  _QWORD Src[4]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v57[32]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v58[32]; // [rsp+D8h] [rbp-30h] BYREF
  void *ppObject; // [rsp+F8h] [rbp-10h] BYREF
  LPCWSTR lpszPathName[2]; // [rsp+100h] [rbp-8h] BYREF
  __int128 v61; // [rsp+110h] [rbp+8h]
  __int128 v62; // [rsp+120h] [rbp+18h] BYREF
  __int128 v63; // [rsp+130h] [rbp+28h]
  _BYTE v64[128]; // [rsp+148h] [rbp+40h] BYREF

  Uev::ScopeTracker::ScopeTracker((Uev::ScopeTracker *)v64, L"CscChangeManager", L"ADSMethods::GetADHomeDirectory");
  v51 = 0;
  _bstr_t::_Free(a2);
  *(_QWORD *)a2 = 0;
  _bstr_t::_Free((_bstr_t *)&v51);
  v51 = 0;
  CurrentUserDN = Uev::ADSMethods::GetCurrentUserDN((struct _bstr_t *)&v51);
  LODWORD(v50) = CurrentUserDN;
  v4 = (const void **)v51;
  if ( CurrentUserDN < 0 )
  {
    if ( v51 && *v51 )
      v5 = SysStringLen(*v51);
    else
      v5 = 0;
    if ( v4 )
      v6 = *v4;
    else
      v6 = 0;
    v62 = 0;
    v63 = 0;
    std::wstring::_Construct<1,wchar_t *>(&v62, v6, v5);
    if ( (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v7) + 32LL) & 2) != 0 )
    {
      v9 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v8);
      v11 = boost::lexical_cast<std::wstring,long>(v58, &v50);
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v63) < 0x24 )
        std::_Xlen_string();
      v12 = &v62;
      if ( *((_QWORD *)&v63 + 1) > 7u )
        v12 = (__int128 *)v62;
      std::wstring::wstring((char *)Src, v63, v10, L"GetCurrentUserDN failed for userDN: ", 36, v12, v63);
      v13 = (__m128i *)std::wstring::_Append<wchar_t>(Src, L"'. HRESULT: ", 0xCu);
      v54 = *v13;
      v55 = v13[1];
      v13[1].m128i_i64[0] = 0;
      v13[1].m128i_i64[1] = 7;
      v13->m128i_i16[0] = 0;
      v14 = (_QWORD *)std::operator+<wchar_t>(v57, &v54, v11);
      v52 = 0;
      v53 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v52, L"CscChangeManager", 0x10u);
      if ( v14[3] > 7u )
        v14 = (_QWORD *)*v14;
      Uev::LogImpl::Write(*v9, 2, &v52, v14);
      std::wstring::_Tidy_deallocate(&v52);
      std::wstring::_Tidy_deallocate(v57);
      std::wstring::_Tidy_deallocate(&v54);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(v58);
    }
    std::wstring::_Tidy_deallocate(&v62);
  }
  *(_OWORD *)lpszPathName = 0;
  v61 = 0;
  std::wstring::_Construct<1,wchar_t *>(lpszPathName, L"LDAP://", 7u);
  if ( !CurrentUserDN )
  {
    if ( v4 )
      v15 = *v4;
    else
      v15 = 0;
    v16 = -1;
    do
      ++v16;
    while ( v15[v16] );
    std::wstring::_Append<wchar_t>(lpszPathName, v15, v16);
  }
  v17 = 0;
  ppObject = 0;
  if ( !CurrentUserDN )
  {
    v18 = (const WCHAR *)lpszPathName;
    if ( *((_QWORD *)&v61 + 1) > 7u )
      v18 = lpszPathName[0];
    CurrentUserDN = ADsGetObject(v18, &IID_IADsUser, &ppObject);
    LODWORD(v50) = CurrentUserDN;
    if ( CurrentUserDN < 0 && (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v19) + 32LL) & 2) != 0 )
    {
      v21 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v20);
      v22 = boost::lexical_cast<std::wstring,long>(v57, &v50);
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v61) < 0x24 )
        std::_Xlen_string();
      v24 = lpszPathName;
      if ( *((_QWORD *)&v61 + 1) > 7u )
        v24 = (LPCWSTR *)lpszPathName[0];
      std::wstring::wstring((char *)Src, v61, v23, L"ADsGetObject failed for LDAP path: '", 36, v24, v61);
      v25 = (__m128i *)std::wstring::_Append<wchar_t>(Src, L"'. HRESULT: ", 0xCu);
      v54 = *v25;
      v55 = v25[1];
      v25[1].m128i_i64[0] = 0;
      v25[1].m128i_i64[1] = 7;
      v25->m128i_i16[0] = 0;
      v26 = (_QWORD *)std::operator+<wchar_t>(v58, &v54, v22);
      v52 = 0;
      v53 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v52, L"CscChangeManager", 0x10u);
      if ( v26[3] > 7u )
        v26 = (_QWORD *)*v26;
      Uev::LogImpl::Write(*v21, 2, &v52, v26);
      std::wstring::_Tidy_deallocate(&v52);
      std::wstring::_Tidy_deallocate(v58);
      std::wstring::_Tidy_deallocate(&v54);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(v57);
    }
    if ( !CurrentUserDN )
    {
      v27 = ppObject;
      v28 = *(_QWORD *)ppObject;
      _bstr_t::_Free(a2);
      v29 = operator new(0x18u);
      v50 = v29;
      if ( v29 )
      {
        v29[1] = 0;
        *((_DWORD *)v29 + 4) = 1;
        *v29 = 0;
      }
      else
      {
        v29 = 0;
      }
      *(_QWORD *)a2 = v29;
      if ( !v29 )
        _com_issue_error(-2147024882);
      CurrentUserDN = (*(__int64 (__fastcall **)(void *, _QWORD *))(v28 + 768))(v27, v29);
      LODWORD(v50) = CurrentUserDN;
      if ( CurrentUserDN < 0
        && (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v30) + 32LL) & 2) != 0 )
      {
        v32 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v31);
        v33 = boost::lexical_cast<std::wstring,long>(v57, &v50);
        if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v61) < 0x28 )
          std::_Xlen_string();
        v35 = lpszPathName;
        if ( *((_QWORD *)&v61 + 1) > 7u )
          v35 = (LPCWSTR *)lpszPathName[0];
        std::wstring::wstring((char *)Src, v61, v34, L"IADsUser::get_HomeDirectory for user DN ", 40, v35, v61);
        v36 = (__m128i *)std::wstring::_Append<wchar_t>(Src, L" failed. HRESULT: ", 0x12u);
        v54 = *v36;
        v55 = v36[1];
        v36[1].m128i_i64[0] = 0;
        v36[1].m128i_i64[1] = 7;
        v36->m128i_i16[0] = 0;
        v37 = (_QWORD *)std::operator+<wchar_t>(v58, &v54, v33);
        v52 = 0;
        v53 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v52, L"CscChangeManager", 0x10u);
        if ( v37[3] > 7u )
          v37 = (_QWORD *)*v37;
        Uev::LogImpl::Write(*v32, 2, &v52, v37);
        std::wstring::_Tidy_deallocate(&v52);
        std::wstring::_Tidy_deallocate(v58);
        std::wstring::_Tidy_deallocate(&v54);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(v57);
      }
      if ( !CurrentUserDN )
      {
        v38 = *(_QWORD *)a2 ? **(OLECHAR ***)a2 : 0LL;
        if ( !SysStringLen(v38) )
        {
          if ( (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v39) + 32LL) & 2) != 0 )
          {
            v42 = (_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v40);
            if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v61) < 0x2D )
              std::_Xlen_string();
            v44 = lpszPathName;
            if ( *((_QWORD *)&v61 + 1) > 7u )
              v44 = (LPCWSTR *)lpszPathName[0];
            std::wstring::wstring((char *)Src, v41, v43, L"AD Home directory is not defined for user DN ", 45, v44, v61);
            v45 = (__m128i *)std::wstring::_Append<wchar_t>(Src, L". HRESULT: E_FAIL", 0x11u);
            v46 = *v45;
            v54 = *v45;
            v55 = v45[1];
            v47 = v55;
            v45[1].m128i_i64[0] = 0;
            v45[1].m128i_i64[1] = 7;
            v45->m128i_i16[0] = 0;
            v52 = 0;
            v53 = 0;
            std::wstring::_Construct<1,wchar_t *>(&v52, L"CscChangeManager", 0x10u);
            v48 = &v54;
            if ( _mm_srli_si128(v47, 8).m128i_u64[0] > 7 )
              v48 = (__m128i *)v46.m128i_i64[0];
            Uev::LogImpl::Write(*v42, 2, &v52, v48);
            std::wstring::_Tidy_deallocate(&v52);
            std::wstring::_Tidy_deallocate(&v54);
            std::wstring::_Tidy_deallocate(Src);
          }
          CurrentUserDN = -2147467259;
        }
      }
    }
    v17 = ppObject;
  }
  if ( v17 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
  std::wstring::_Tidy_deallocate(lpszPathName);
  _bstr_t::_Free((_bstr_t *)&v51);
  Uev::ScopeTracker::~ScopeTracker((Uev::ScopeTracker *)v64);
  return (unsigned int)CurrentUserDN;
}

```

## disassembly

```asm
0x14008ace0  mov     rax, rsp
0x14008ace3  push    rbp
0x14008ace4  push    rbx
0x14008ace5  push    rsi
0x14008ace6  push    rdi
0x14008ace7  push    r12
0x14008ace9  push    r13
0x14008aceb  push    r14
0x14008aced  push    r15
0x14008acef  lea     rbp, [rax-138h]
0x14008acf6  sub     rsp, 1F8h
0x14008acfd  movaps  xmmword ptr [rax-58h], xmm6
0x14008ad01  movaps  xmmword ptr [rax-68h], xmm7
0x14008ad05  mov     rax, cs:__security_cookie
0x14008ad0c  xor     rax, rsp
0x14008ad0f  mov     [rbp+130h+var_70], rax
0x14008ad16  mov     r15, rdx
0x14008ad19  xor     r13d, r13d
0x14008ad1c  lea     r8, aAdsmethodsGeta; "ADSMethods::GetADHomeDirectory"
0x14008ad23  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008ad2a  lea     rcx, [rbp+130h+var_F0]; this
0x14008ad2e  call    ??0ScopeTracker@Uev@@QEAA@PEB_W0@Z; Uev::ScopeTracker::ScopeTracker(wchar_t const *,wchar_t const *)
0x14008ad33  nop
0x14008ad34  mov     qword ptr [rsp+230h+var_1E8], r13
0x14008ad39  mov     rcx, r15; this
0x14008ad3c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14008ad41  mov     [r15], r13
0x14008ad44  lea     rcx, [rsp+230h+var_1E8]; this
0x14008ad49  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14008ad4e  mov     qword ptr [rsp+230h+var_1E8], r13
0x14008ad53  lea     rcx, [rsp+230h+var_1E8]; this
0x14008ad58  call    ?GetCurrentUserDN@ADSMethods@Uev@@CAJAEAV_bstr_t@@@Z; Uev::ADSMethods::GetCurrentUserDN(_bstr_t &)
0x14008ad5d  mov     edi, eax
0x14008ad5f  mov     dword ptr [rsp+230h+var_1F0], eax
0x14008ad63  mov     rsi, 7FFFFFFFFFFFFFFEh
0x14008ad6d  lea     r12d, [r13+2]
0x14008ad71  mov     rbx, qword ptr [rsp+230h+var_1E8]
0x14008ad76  test    eax, eax
0x14008ad78  jns     loc_14008AF06
0x14008ad7e  test    rbx, rbx
0x14008ad81  jz      short loc_14008AD93
0x14008ad83  mov     rcx, [rbx]; pbstr
0x14008ad86  test    rcx, rcx
0x14008ad89  jz      short loc_14008AD93
0x14008ad8b  call    cs:__imp_SysStringLen
0x14008ad91  jmp     short loc_14008AD96
0x14008ad93  mov     eax, r13d
0x14008ad96  test    rbx, rbx
0x14008ad99  jz      short loc_14008ADA0
0x14008ad9b  mov     rdx, [rbx]
0x14008ad9e  jmp     short loc_14008ADA3
0x14008ada0  mov     rdx, r13
0x14008ada3  xorps   xmm0, xmm0
0x14008ada6  movups  [rbp+130h+var_118], xmm0
0x14008adaa  xorps   xmm1, xmm1
0x14008adad  movdqu  [rbp+130h+var_108], xmm1
0x14008adb2  mov     r8d, eax
0x14008adb5  lea     rcx, [rbp+130h+var_118]
0x14008adb9  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008adbe  nop
0x14008adbf  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008adc4  mov     rax, [rax]
0x14008adc7  test    [rax+20h], r12b
0x14008adcb  jbe     loc_14008AEFD
0x14008add1  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008add6  mov     r12, rax
0x14008add9  lea     rdx, [rsp+230h+var_1F0]
0x14008adde  lea     rcx, [rbp+130h+var_160]
0x14008ade2  call    ??$lexical_cast@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@boost@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBJ@Z; boost::lexical_cast<std::wstring,long>(long const &)
0x14008ade7  mov     r14, rax
0x14008adea  mov     rdx, qword ptr [rbp+130h+var_108]
0x14008adee  mov     rcx, rsi
0x14008adf1  sub     rcx, rdx
0x14008adf4  cmp     rcx, 24h ; '$'
0x14008adf8  jb      loc_14008B404
0x14008adfe  lea     rax, [rbp+130h+var_118]
0x14008ae02  cmp     qword ptr [rbp+130h+var_108+8], 7
0x14008ae07  cmova   rax, qword ptr [rbp+130h+var_118]
0x14008ae0c  mov     [rsp+230h+var_200], rdx
0x14008ae11  mov     [rsp+230h+var_208], rax
0x14008ae16  mov     [rsp+230h+var_210], 24h ; '$'
0x14008ae1f  lea     r9, aGetcurrentuser; "GetCurrentUserDN failed for userDN: "
0x14008ae26  lea     rcx, [rbp+130h+Src]
0x14008ae2a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14008ae2f  nop
0x14008ae30  mov     r8d, 0Ch
0x14008ae36  lea     rdx, aHresult; "'. HRESULT: "
0x14008ae3d  lea     rcx, [rbp+130h+Src]; Src
0x14008ae41  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14008ae46  movups  xmm0, xmmword ptr [rax]
0x14008ae49  movups  xmmword ptr [rsp+230h+var_1C8+8], xmm0
0x14008ae4e  movups  xmm1, xmmword ptr [rax+10h]
0x14008ae52  movups  [rbp+130h+var_1B0], xmm1
0x14008ae56  mov     [rax+10h], r13
0x14008ae5a  mov     qword ptr [rax+18h], 7
0x14008ae62  mov     [rax], r13w
0x14008ae66  mov     r8, r14
0x14008ae69  lea     rdx, [rsp+230h+var_1C8+8]
0x14008ae6e  lea     rcx, [rbp+130h+var_180]
0x14008ae72  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x14008ae77  mov     r14, rax
0x14008ae7a  xorps   xmm0, xmm0
0x14008ae7d  movups  [rsp+230h+var_1E8+8], xmm0
0x14008ae82  xorps   xmm1, xmm1
0x14008ae85  movdqu  [rsp+230h+var_1D8+8], xmm1
0x14008ae8b  mov     r8d, 10h
0x14008ae91  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008ae98  lea     rcx, [rsp+230h+var_1E8+8]
0x14008ae9d  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008aea2  nop
0x14008aea3  cmp     qword ptr [r14+18h], 7
0x14008aea8  jbe     short loc_14008AEAD
0x14008aeaa  mov     r14, [r14]
0x14008aead  mov     r9, r14
0x14008aeb0  lea     r8, [rsp+230h+var_1E8+8]
0x14008aeb5  mov     edx, 2
0x14008aeba  mov     rcx, [r12]
0x14008aebe  call    ?Write@LogImpl@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::LogImpl::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,wchar_t const *)
0x14008aec3  nop
0x14008aec4  lea     rcx, [rsp+230h+var_1E8+8]
0x14008aec9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008aece  nop
0x14008aecf  lea     rcx, [rbp+130h+var_180]
0x14008aed3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008aed8  nop
0x14008aed9  lea     rcx, [rsp+230h+var_1C8+8]
0x14008aede  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008aee3  nop
0x14008aee4  lea     rcx, [rbp+130h+Src]
0x14008aee8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008aeed  nop
0x14008aeee  lea     rcx, [rbp+130h+var_160]
0x14008aef2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008aef7  mov     r12d, 2
0x14008aefd  lea     rcx, [rbp+130h+var_118]
0x14008af01  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008af06  xorps   xmm0, xmm0
0x14008af09  movups  xmmword ptr [rbp+130h+lpszPathName], xmm0
0x14008af0d  xorps   xmm1, xmm1
0x14008af10  movdqu  [rbp+130h+var_128], xmm1
0x14008af15  mov     r8d, 7
0x14008af1b  lea     rdx, aLdap; "LDAP://"
0x14008af22  lea     rcx, [rbp+130h+lpszPathName]
0x14008af26  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008af2b  nop
0x14008af2c  test    edi, edi
0x14008af2e  jnz     short loc_14008AF54
0x14008af30  test    rbx, rbx
0x14008af33  jz      short loc_14008AF3A
0x14008af35  mov     rdx, [rbx]
0x14008af38  jmp     short loc_14008AF3D
0x14008af3a  mov     rdx, r13
0x14008af3d  or      r8, 0FFFFFFFFFFFFFFFFh
0x14008af41  inc     r8
0x14008af44  cmp     [rdx+r8*2], r13w
0x14008af49  jnz     short loc_14008AF41
0x14008af4b  lea     rcx, [rbp+130h+lpszPathName]; Src
0x14008af4f  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14008af54  mov     rcx, r13
0x14008af57  mov     [rbp+130h+ppObject], rcx
0x14008af5b  test    edi, edi
0x14008af5d  jnz     loc_14008B39B
0x14008af63  lea     rcx, [rbp+130h+lpszPathName]
0x14008af67  cmp     qword ptr [rbp+130h+var_128+8], 7
0x14008af6c  cmova   rcx, [rbp+130h+lpszPathName]; lpszPathName
0x14008af71  lea     r8, [rbp+130h+ppObject]; ppObject
0x14008af75  lea     rdx, IID_IADsUser; riid
0x14008af7c  call    cs:__imp_ADsGetObject
0x14008af82  mov     edi, eax
0x14008af84  mov     dword ptr [rsp+230h+var_1F0], eax
0x14008af88  test    eax, eax
0x14008af8a  jns     loc_14008B0C5
0x14008af90  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008af95  mov     rax, [rax]
0x14008af98  test    [rax+20h], r12b
0x14008af9c  jbe     loc_14008B0C5
0x14008afa2  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008afa7  mov     r14, rax
0x14008afaa  lea     rdx, [rsp+230h+var_1F0]
0x14008afaf  lea     rcx, [rbp+130h+var_180]
0x14008afb3  call    ??$lexical_cast@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@boost@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBJ@Z; boost::lexical_cast<std::wstring,long>(long const &)
0x14008afb8  mov     rbx, rax
0x14008afbb  mov     rdx, qword ptr [rbp+130h+var_128]
0x14008afbf  mov     rcx, rsi
0x14008afc2  sub     rcx, rdx
0x14008afc5  cmp     rcx, 24h ; '$'
0x14008afc9  jb      loc_14008B40A
0x14008afcf  lea     rax, [rbp+130h+lpszPathName]
0x14008afd3  cmp     qword ptr [rbp+130h+var_128+8], 7
0x14008afd8  cmova   rax, [rbp+130h+lpszPathName]
0x14008afdd  mov     [rsp+230h+var_200], rdx
0x14008afe2  mov     [rsp+230h+var_208], rax
0x14008afe7  mov     [rsp+230h+var_210], 24h ; '$'
0x14008aff0  lea     r9, aAdsgetobjectFa; "ADsGetObject failed for LDAP path: '"
0x14008aff7  lea     rcx, [rbp+130h+Src]
0x14008affb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14008b000  nop
0x14008b001  mov     r8d, 0Ch
0x14008b007  lea     rdx, aHresult; "'. HRESULT: "
0x14008b00e  lea     rcx, [rbp+130h+Src]; Src
0x14008b012  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14008b017  movups  xmm0, xmmword ptr [rax]
0x14008b01a  movups  xmmword ptr [rsp+230h+var_1C8+8], xmm0
0x14008b01f  movups  xmm1, xmmword ptr [rax+10h]
0x14008b023  movups  [rbp+130h+var_1B0], xmm1
0x14008b027  mov     [rax+10h], r13
0x14008b02b  mov     qword ptr [rax+18h], 7
0x14008b033  mov     [rax], r13w
0x14008b037  mov     r8, rbx
0x14008b03a  lea     rdx, [rsp+230h+var_1C8+8]
0x14008b03f  lea     rcx, [rbp+130h+var_160]
0x14008b043  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x14008b048  mov     rbx, rax
0x14008b04b  xorps   xmm0, xmm0
0x14008b04e  movups  [rsp+230h+var_1E8+8], xmm0
0x14008b053  xorps   xmm1, xmm1
0x14008b056  movdqu  [rsp+230h+var_1D8+8], xmm1
0x14008b05c  mov     r8d, 10h
0x14008b062  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008b069  lea     rcx, [rsp+230h+var_1E8+8]
0x14008b06e  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008b073  nop
0x14008b074  cmp     qword ptr [rbx+18h], 7
0x14008b079  jbe     short loc_14008B07E
0x14008b07b  mov     rbx, [rbx]
0x14008b07e  mov     r9, rbx
0x14008b081  lea     r8, [rsp+230h+var_1E8+8]
0x14008b086  mov     edx, r12d
0x14008b089  mov     rcx, [r14]
0x14008b08c  call    ?Write@LogImpl@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Uev::LogImpl::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,wchar_t const *)
0x14008b091  nop
0x14008b092  lea     rcx, [rsp+230h+var_1E8+8]
0x14008b097  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008b09c  nop
0x14008b09d  lea     rcx, [rbp+130h+var_160]
0x14008b0a1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008b0a6  nop
0x14008b0a7  lea     rcx, [rsp+230h+var_1C8+8]
0x14008b0ac  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008b0b1  nop
0x14008b0b2  lea     rcx, [rbp+130h+Src]
0x14008b0b6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008b0bb  nop
0x14008b0bc  lea     rcx, [rbp+130h+var_180]
0x14008b0c0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008b0c5  test    edi, edi
0x14008b0c7  jnz     loc_14008B397
0x14008b0cd  mov     rbx, [rbp+130h+ppObject]
0x14008b0d1  mov     rdi, [rbx]
0x14008b0d4  mov     rcx, r15; this
0x14008b0d7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14008b0dc  mov     ecx, 18h; Size
0x14008b0e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14008b0e6  mov     [rsp+230h+var_1F0], rax
0x14008b0eb  test    rax, rax
0x14008b0ee  jz      short loc_14008B100
0x14008b0f0  mov     [rax+8], r13
0x14008b0f4  mov     dword ptr [rax+10h], 1
0x14008b0fb  mov     [rax], r13
0x14008b0fe  jmp     short loc_14008B103
0x14008b100  mov     rax, r13
0x14008b103  mov     [r15], rax
0x14008b106  test    rax, rax
0x14008b109  jz      loc_14008B410
0x14008b10f  mov     rdx, rax
0x14008b112  mov     rcx, rbx
0x14008b115  mov     rax, [rdi+300h]
0x14008b11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b121  mov     edi, eax
0x14008b123  mov     dword ptr [rsp+230h+var_1F0], eax
0x14008b127  test    eax, eax
0x14008b129  jns     loc_14008B264
0x14008b12f  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008b134  mov     rax, [rax]
0x14008b137  test    [rax+20h], r12b
0x14008b13b  jbe     loc_14008B264
0x14008b141  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14008b146  mov     r14, rax
0x14008b149  lea     rdx, [rsp+230h+var_1F0]
0x14008b14e  lea     rcx, [rbp+130h+var_180]
0x14008b152  call    ??$lexical_cast@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@J@boost@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBJ@Z; boost::lexical_cast<std::wstring,long>(long const &)
0x14008b157  mov     rbx, rax
0x14008b15a  mov     rdx, qword ptr [rbp+130h+var_128]
0x14008b15e  mov     rcx, rsi
0x14008b161  sub     rcx, rdx
0x14008b164  cmp     rcx, 28h ; '('
0x14008b168  jb      loc_14008B41B
0x14008b16e  lea     rax, [rbp+130h+lpszPathName]
0x14008b172  cmp     qword ptr [rbp+130h+var_128+8], 7
0x14008b177  cmova   rax, [rbp+130h+lpszPathName]
0x14008b17c  mov     [rsp+230h+var_200], rdx
0x14008b181  mov     [rsp+230h+var_208], rax
0x14008b186  mov     [rsp+230h+var_210], 28h ; '('
0x14008b18f  lea     r9, aIadsuserGetHom; "IADsUser::get_HomeDirectory for user DN"...
0x14008b196  lea     rcx, [rbp+130h+Src]
0x14008b19a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14008b19f  nop
0x14008b1a0  mov     r8d, 12h
0x14008b1a6  lea     rdx, aFailedHresult; " failed. HRESULT: "
0x14008b1ad  lea     rcx, [rbp+130h+Src]; Src
  ... truncated ...
```
