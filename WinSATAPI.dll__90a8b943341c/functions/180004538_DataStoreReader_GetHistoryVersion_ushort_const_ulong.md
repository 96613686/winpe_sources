# DataStoreReader::GetHistoryVersion(ushort const *,ulong &)

- ea: `0x180004538`
- end: `0x180004984`
- name: `?GetHistoryVersion@DataStoreReader@@CAJPEBGAEAK@Z`
- size: `1100`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180003970`

## callees

- `0x1800015d0`
- `0x180001ed0`
- `0x180004538`
- `0x180007080`
- `0x180008490`
- `0x1800110f8`
- `0x180011e70`
- `0x180011ee0`
- `0x180012bf3`
- `0x180012c06`
- `0x18002e380`
- `0x180033010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180004628`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18000476d`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180004628`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18000476d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000488d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000489c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004934`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004943`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000488d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000489c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004934`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004943`

## string_xrefs

- `0x1800046da`: `HistoryVersionRead`
- `0x1800046e8`: `HistoryVersionRead`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall DataStoreReader::GetHistoryVersion(const unsigned __int16 *a1, unsigned int *a2)
{
  __int64 *v3; // rax
  __int64 *v4; // rdi
  __int64 v5; // rsi
  __int64 v6; // rcx
  const wchar_t *i; // rax
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  void *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 *v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rbx
  const wchar_t *j; // rax
  __int64 v17; // rax
  unsigned __int64 v18; // rcx
  void *v19; // rax
  __int64 v20; // r8
  const wchar_t *v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rdx
  bool v25; // zf
  void *v26; // rcx
  void *v27; // rcx
  __int64 *v29; // [rsp+30h] [rbp-61h] BYREF
  _QWORD v30[2]; // [rsp+38h] [rbp-59h] BYREF
  char v31[8]; // [rsp+48h] [rbp-49h] BYREF
  char v32[8]; // [rsp+50h] [rbp-41h] BYREF
  __m128i si128; // [rsp+58h] [rbp-39h] BYREF
  _BYTE v34[16]; // [rsp+68h] [rbp-29h] BYREF
  __int16 v35; // [rsp+78h] [rbp-19h]
  char v36; // [rsp+7Ah] [rbp-17h]
  __int64 v37; // [rsp+80h] [rbp-11h]
  __int64 *v38; // [rsp+88h] [rbp-9h]
  _QWORD pExceptionObject[11]; // [rsp+90h] [rbp-1h] BYREF
  const unsigned __int16 *v40; // [rsp+F8h] [rbp+67h] BYREF
  const char *v41; // [rsp+108h] [rbp+77h] BYREF
  __int64 *v42; // [rsp+110h] [rbp+7Fh]

  v40 = a1;
  pExceptionObject[3] = -2;
  v3 = (__int64 *)operator new(0x28u);
  v4 = v3;
  if ( !v3 )
    std::_Xbad_alloc();
  v42 = v3;
  *v3 = 0;
  v3[1] = 0;
  v3[2] = 1;
  v3[3] = 0;
  v5 = 0x10000;
  v6 = 0x10000;
  for ( i = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSAT"; ; ++i )
  {
    if ( !v6 )
      goto LABEL_56;
    if ( !*i )
      break;
    --v6;
  }
  if ( !i )
LABEL_56:
    throw (mlib::CStringTooBig *)&v40;
  v8 = i - L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSAT";
  *v4 = v8;
  v4[1] = v8;
  v9 = v8 + 1;
  v10 = 0;
  v11 = 0x7FFFFFFFFFFFFFFFLL;
  if ( v9 )
  {
    if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
      std::_Xbad_alloc();
  }
  v4[3] = (__int64)v10;
  if ( !v10 )
  {
    v41 = "bad allocation";
    exception::exception((exception *)pExceptionObject, &v41, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  if ( *v4 )
    memcpy_0(v10, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSAT", 2 * *v4);
  v12 = v4[3];
  if ( v12 )
    *(_WORD *)(v12 + 2 * *v4) = 0;
  v42 = v4;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v29,
    v11);
  if ( v29 )
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v29);
  v29 = v4;
  ++v4[2];
  mlib::RegistryBaseKey::cleanup(&v29);
  v13 = (__int64 *)operator new(0x28u);
  v15 = v13;
  if ( !v13 )
    std::_Xbad_alloc();
  v38 = v13;
  *v13 = 0;
  v13[1] = 0;
  v13[2] = 1;
  v13[3] = 0;
  if ( aHistoryversion[0] )
  {
    for ( j = L"HistoryVersionRead"; ; ++j )
    {
      if ( !v5 )
        goto LABEL_36;
      if ( !*j )
        break;
      --v5;
    }
    if ( !j )
LABEL_36:
      throw (mlib::CStringTooBig *)&v40;
    v17 = j - L"HistoryVersionRead";
    *v15 = v17;
    v15[1] = v17;
    v18 = v17 + 1;
    v19 = 0;
    if ( v18 )
    {
      if ( v18 > 0x7FFFFFFFFFFFFFFFLL || (v19 = operator new(2 * v18)) == 0 )
        std::_Xbad_alloc();
    }
    v15[3] = (__int64)v19;
    if ( !v19 )
    {
      v41 = "bad allocation";
      exception::exception((exception *)pExceptionObject, &v41, 1);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    v20 = *v15;
    if ( *v15 )
    {
      v21 = L"HistoryVersionRead";
LABEL_40:
      memcpy_0(v19, v21, 2 * v20);
    }
  }
  else
  {
    v19 = operator new(2u);
    if ( !v19 )
      std::_Xbad_alloc();
    v15[3] = (__int64)v19;
    v20 = *v15;
    if ( *v15 )
    {
      v21 = 0;
      goto LABEL_40;
    }
  }
  v22 = v15[3];
  if ( v22 )
    *(_WORD *)(v22 + 2 * *v15) = 0;
  v38 = v15;
  v30[0] = &mlib::RegistryKey::`vftable';
  v30[1] = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v31,
    v14);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v32,
    v23);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &si128.m128i_u64[1],
    v29);
  v30[0] = &mlib::RegistryValue::`vftable';
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v34,
    v24);
  v40 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &v40,
    v15);
  mlib::RegistryValue::parse_names(v30, &v40);
  v35 = 256;
  v36 = 0;
  v30[0] = &mlib::DWORDReg::`vftable';
  v37 = 0;
  v25 = v15[2]-- == 1;
  if ( v25 )
  {
    v26 = (void *)v15[3];
    if ( v26 )
      operator delete(v26);
    operator delete(v15);
  }
  v37 = (_BYTE)v35 != 0 ? (unsigned int)v37 : 0;
  (*(void (__fastcall **)(_QWORD *))(v30[0] + 8LL))(v30);
  *a2 = v37;
  v30[0] = &mlib::DWORDReg::`vftable';
  if ( !HIBYTE(v35) || v36 )
    mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v30);
  v30[0] = &mlib::RegistryValue::`vftable';
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v34);
  v30[0] = &mlib::RegistryKey::`vftable';
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&si128.m128i_u64[1]);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v32);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v31);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v29);
  v25 = v4[2]-- == 1;
  if ( v25 )
  {
    v27 = (void *)v4[3];
    if ( v27 )
      operator delete(v27);
    operator delete(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180004538  mov     rax, rsp
0x18000453b  mov     [rax+8], rcx
0x18000453f  push    rbp
0x180004540  push    rsi
0x180004541  push    rdi
0x180004542  push    r12
0x180004544  push    r13
0x180004546  push    r14
0x180004548  push    r15
0x18000454a  lea     rbp, [rax-5Fh]
0x18000454e  sub     rsp, 0B0h
0x180004555  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x18000455d  mov     [rax+10h], rbx
0x180004561  mov     r14, rdx
0x180004564  mov     r13d, 28h ; '('
0x18000456a  mov     ecx, r13d; Size
0x18000456d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004572  mov     rdi, rax
0x180004575  xor     r15d, r15d
0x180004578  test    rax, rax
0x18000457b  jnz     short loc_180004583
0x18000457d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180004583  mov     [rbp+57h+arg_18], rdi
0x180004587  mov     [rax], r15
0x18000458a  mov     [rax+8], r15
0x18000458e  mov     r12d, 1
0x180004594  mov     [rax+10h], r12
0x180004598  mov     [rax+18h], r15
0x18000459c  mov     esi, 10000h
0x1800045a1  mov     ecx, esi
0x1800045a3  lea     rbx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800045aa  mov     rax, rbx
0x1800045ad  test    rcx, rcx
0x1800045b0  jz      loc_180004973
0x1800045b6  cmp     [rax], r15w
0x1800045ba  jz      short loc_1800045C5
0x1800045bc  add     rax, 2
0x1800045c0  sub     rcx, r12
0x1800045c3  jmp     short loc_1800045AD
0x1800045c5  test    rax, rax
0x1800045c8  jz      loc_180004973
0x1800045ce  sub     rax, rbx
0x1800045d1  sar     rax, 1
0x1800045d4  mov     [rdi], rax
0x1800045d7  mov     [rdi+8], rax
0x1800045db  lea     rcx, [rax+1]
0x1800045df  mov     rax, r15
0x1800045e2  mov     rdx, 7FFFFFFFFFFFFFFFh
0x1800045ec  test    rcx, rcx
0x1800045ef  jz      short loc_180004609
0x1800045f1  cmp     rcx, rdx
0x1800045f4  ja      short loc_180004603
0x1800045f6  add     rcx, rcx; Size
0x1800045f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045fe  test    rax, rax
0x180004601  jnz     short loc_180004609
0x180004603  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180004609  mov     [rdi+18h], rax
0x18000460d  test    rax, rax
0x180004610  jnz     short loc_180004650
0x180004612  lea     rax, aBadAllocation; "bad allocation"
0x180004619  mov     [rbp+57h+arg_10], rax
0x18000461d  mov     r8d, r12d
0x180004620  lea     rdx, [rbp+57h+arg_10]
0x180004624  lea     rcx, [rbp+57h+pExceptionObject]
0x180004628  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18000462f  nop     dword ptr [rax+rax+00h]
0x180004634  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000463b  mov     [rbp+57h+pExceptionObject], rax
0x18000463f  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180004646  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000464a  call    _CxxThrowException_0
0x180004650  mov     r8, [rdi]
0x180004653  test    r8, r8
0x180004656  jz      short loc_180004666
0x180004658  add     r8, r8; Size
0x18000465b  mov     rdx, rbx; Src
0x18000465e  mov     rcx, rax; void *
0x180004661  call    memcpy_0
0x180004666  mov     rcx, [rdi+18h]
0x18000466a  test    rcx, rcx
0x18000466d  jz      short loc_180004677
0x18000466f  mov     rax, [rdi]
0x180004672  mov     [rcx+rax*2], r15w
0x180004677  mov     [rbp+57h+arg_18], rdi
0x18000467b  mov     [rbp+57h+var_C0], r15
0x18000467f  lea     rcx, [rbp+57h+var_B8]
0x180004683  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x180004688  nop
0x180004689  cmp     [rbp+57h+var_B8], r15
0x18000468d  jz      short loc_180004698
0x18000468f  lea     rcx, [rbp+57h+var_B8]
0x180004693  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180004698  mov     [rbp+57h+var_B8], rdi
0x18000469c  add     [rdi+10h], r12
0x1800046a0  lea     rcx, [rbp+57h+var_B8]
0x1800046a4  call    ?cleanup@RegistryBaseKey@mlib@@SAXAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::RegistryBaseKey::cleanup(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x1800046a9  mov     [rbp+57h+var_C0], 0FFFFFFFF80000002h
0x1800046b1  mov     rcx, r13; Size
0x1800046b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800046b9  mov     rbx, rax
0x1800046bc  test    rax, rax
0x1800046bf  jnz     short loc_1800046C7
0x1800046c1  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800046c7  mov     [rbp+57h+var_60], rbx
0x1800046cb  mov     [rax], r15
0x1800046ce  mov     [rax+8], r15
0x1800046d2  mov     [rax+10h], r12
0x1800046d6  mov     [rax+18h], r15
0x1800046da  cmp     word ptr cs:aHistoryversion, r15w; "HistoryVersionRead"
0x1800046e2  jz      loc_1800047B3
0x1800046e8  lea     r13, aHistoryversion; "HistoryVersionRead"
0x1800046ef  mov     rax, r13
0x1800046f2  test    rsi, rsi
0x1800046f5  jz      loc_1800047A2
0x1800046fb  cmp     [rax], r15w
0x1800046ff  jz      short loc_18000470A
0x180004701  add     rax, 2
0x180004705  sub     rsi, r12
0x180004708  jmp     short loc_1800046F2
0x18000470a  test    rax, rax
0x18000470d  jz      loc_1800047A2
0x180004713  sub     rax, r13
0x180004716  sar     rax, 1
0x180004719  mov     [rbx], rax
0x18000471c  mov     [rbx+8], rax
0x180004720  lea     rcx, [rax+1]
0x180004724  mov     rax, r15
0x180004727  test    rcx, rcx
0x18000472a  jz      short loc_18000474E
0x18000472c  mov     rax, 7FFFFFFFFFFFFFFFh
0x180004736  cmp     rcx, rax
0x180004739  ja      short loc_180004748
0x18000473b  add     rcx, rcx; Size
0x18000473e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004743  test    rax, rax
0x180004746  jnz     short loc_18000474E
0x180004748  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000474e  mov     [rbx+18h], rax
0x180004752  test    rax, rax
0x180004755  jnz     short loc_180004795
0x180004757  lea     rax, aBadAllocation; "bad allocation"
0x18000475e  mov     [rbp+57h+arg_10], rax
0x180004762  mov     r8d, r12d
0x180004765  lea     rdx, [rbp+57h+arg_10]
0x180004769  lea     rcx, [rbp+57h+pExceptionObject]
0x18000476d  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180004774  nop     dword ptr [rax+rax+00h]
0x180004779  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180004780  mov     [rbp+57h+pExceptionObject], rax
0x180004784  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000478b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000478f  call    _CxxThrowException_0
0x180004795  mov     r8, [rbx]
0x180004798  test    r8, r8
0x18000479b  jz      short loc_1800047DF
0x18000479d  mov     rdx, r13
0x1800047a0  jmp     short loc_1800047D4
0x1800047a2  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x1800047a9  lea     rcx, [rbp+57h+arg_0]; pExceptionObject
0x1800047ad  call    _CxxThrowException_0
0x1800047b3  mov     ecx, 2; Size
0x1800047b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800047bd  test    rax, rax
0x1800047c0  jz      loc_18000496D
0x1800047c6  mov     [rbx+18h], rax
0x1800047ca  mov     r8, [rbx]
0x1800047cd  test    r8, r8
0x1800047d0  jz      short loc_1800047DF
0x1800047d2  xor     edx, edx; Src
0x1800047d4  add     r8, r8; Size
0x1800047d7  mov     rcx, rax; void *
0x1800047da  call    memcpy_0
0x1800047df  mov     rcx, [rbx+18h]
0x1800047e3  test    rcx, rcx
0x1800047e6  jz      short loc_1800047F0
0x1800047e8  mov     rax, [rbx]
0x1800047eb  mov     [rcx+rax*2], r15w
0x1800047f0  mov     [rbp+57h+var_60], rbx
0x1800047f4  lea     r13, ??_7RegistryKey@mlib@@6B@; const mlib::RegistryKey::`vftable'
0x1800047fb  mov     [rbp+57h+var_B0], r13
0x1800047ff  mov     [rbp+57h+var_A8], r15
0x180004803  lea     rcx, [rbp+57h+var_A0]
0x180004807  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x18000480c  nop
0x18000480d  lea     rcx, [rbp+57h+var_98]
0x180004811  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x180004816  movdqa  xmm0, cs:__xmm@0000000000000000ffffffff80000002
0x18000481e  movdqa  [rbp+57h+var_90], xmm0
0x180004823  mov     rdx, [rbp+57h+var_B8]
0x180004827  lea     rcx, [rbp+57h+var_90+8]
0x18000482b  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180004830  nop
0x180004831  lea     rax, ??_7RegistryValue@mlib@@6B@; const mlib::RegistryValue::`vftable'
0x180004838  mov     [rbp+57h+var_B0], rax
0x18000483c  lea     rcx, [rbp+57h+var_80]
0x180004840  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x180004845  nop
0x180004846  mov     [rbp+57h+arg_0], r15
0x18000484a  mov     rdx, rbx
0x18000484d  lea     rcx, [rbp+57h+arg_0]
0x180004851  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180004856  lea     rdx, [rbp+57h+arg_0]
0x18000485a  lea     rcx, [rbp+57h+var_B0]
0x18000485e  call    ?parse_names@RegistryValue@mlib@@IEAAHV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::RegistryValue::parse_names(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>)
0x180004863  nop
0x180004864  mov     [rbp+57h+var_70], 100h
0x18000486a  mov     [rbp+57h+var_6E], r15b
0x18000486e  lea     rsi, ??_7DWORDReg@mlib@@6B@; const mlib::DWORDReg::`vftable'
0x180004875  mov     [rbp+57h+var_B0], rsi
0x180004879  mov     [rbp+57h+var_68], r15
0x18000487d  sub     qword ptr [rbx+10h], 1
0x180004882  jnz     short loc_1800048A8
0x180004884  mov     rcx, [rbx+18h]
0x180004888  test    rcx, rcx
0x18000488b  jz      short loc_180004899
0x18000488d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004894  nop     dword ptr [rax+rax+00h]
0x180004899  mov     rcx, rbx
0x18000489c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800048a3  nop     dword ptr [rax+rax+00h]
0x1800048a8  mov     dword ptr [rbp+57h+var_68+4], r15d
0x1800048ac  mov     al, byte ptr [rbp+57h+var_70]
0x1800048af  neg     al
0x1800048b1  sbb     ecx, ecx
0x1800048b3  and     dword ptr [rbp+57h+var_68], ecx
0x1800048b6  mov     rax, [rbp+57h+var_B0]
0x1800048ba  lea     rcx, [rbp+57h+var_B0]
0x1800048be  mov     rax, [rax+8]
0x1800048c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048c7  mov     eax, dword ptr [rbp+57h+var_68]
0x1800048ca  mov     [r14], eax
0x1800048cd  mov     [rbp+57h+var_B0], rsi
0x1800048d1  cmp     byte ptr [rbp+57h+var_70+1], r15b
0x1800048d5  jz      short loc_1800048DD
0x1800048d7  cmp     [rbp+57h+var_6E], r15b
0x1800048db  jz      short loc_1800048E6
0x1800048dd  lea     rcx, [rbp+57h+var_B0]; this
0x1800048e1  call    ?write@MRegistryRWBase@mlib@@UEAAHXZ; mlib::MRegistryRWBase::write(void)
0x1800048e6  lea     rax, ??_7RegistryValue@mlib@@6B@; const mlib::RegistryValue::`vftable'
0x1800048ed  mov     [rbp+57h+var_B0], rax
0x1800048f1  lea     rcx, [rbp+57h+var_80]
0x1800048f5  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800048fa  mov     [rbp+57h+var_B0], r13
0x1800048fe  lea     rcx, [rbp+57h+var_90+8]
0x180004902  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180004907  lea     rcx, [rbp+57h+var_98]
0x18000490b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180004910  lea     rcx, [rbp+57h+var_A0]
0x180004914  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180004919  nop
0x18000491a  lea     rcx, [rbp+57h+var_B8]
0x18000491e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180004923  nop
0x180004924  sub     qword ptr [rdi+10h], 1
0x180004929  jnz     short loc_18000494F
0x18000492b  mov     rcx, [rdi+18h]
0x18000492f  test    rcx, rcx
0x180004932  jz      short loc_180004940
0x180004934  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000493b  nop     dword ptr [rax+rax+00h]
0x180004940  mov     rcx, rdi
0x180004943  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000494a  nop     dword ptr [rax+rax+00h]
0x18000494f  xor     eax, eax
0x180004951  mov     rbx, [rsp+0E0h+arg_8]
0x180004959  add     rsp, 0B0h
0x180004960  pop     r15
0x180004962  pop     r14
0x180004964  pop     r13
0x180004966  pop     r12
0x180004968  pop     rdi
0x180004969  pop     rsi
0x18000496a  pop     rbp
0x18000496b  retn
0x18000496d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180004973  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x18000497a  lea     rcx, [rbp+57h+arg_0]; pExceptionObject
0x18000497e  call    _CxxThrowException_0
```
