# asg::SemanticIndex::DbLock::TryAccessDb(std::basic_string<char16_t,std::char_traits<char16_t>,std::allocator<char16_t>>)

- ea: `0x1801c75f0`
- end: `0x1801c7b5a`
- name: `?TryAccessDb@DbLock@SemanticIndex@asg@@QEAA?AW4AccessDbErrorCode@123@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@Z`
- size: `1386`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18019c000`
- `0x1801a4740`

## callees

- `0x180007de0`
- `0x1800178d0`
- `0x1800450e0`
- `0x180078ed0`
- `0x18007aef0`
- `0x18007c5e0`
- `0x1801c7350`
- `0x1801c75f0`
- `0x1801f7110`
- `0x1801f7160`
- `0x180206ec0`
- `0x1802421a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801c78a1`
- `KERNEL32!GetLastError` at `0x1801c7947`
- `KERNEL32!GetLastError` at `0x1801c78a1`
- `KERNEL32!GetLastError` at `0x1801c7947`
- `KERNEL32!WaitForSingleObject` at `0x1801c793f`
- `KERNEL32!WaitForSingleObject` at `0x1801c793f`
- `KERNEL32!CreateSemaphoreW` at `0x1801c77e9`
- `KERNEL32!CreateSemaphoreW` at `0x1801c77e9`

## string_xrefs

- `0x1801c767a`: `enum asg::SemanticIndex::DbLock::AccessDbErrorCode __cdecl asg::SemanticIndex::DbLock::TryAccessDb(class std::basic_string<char16_t,struct std::char_traits<char16_t>,class std::allocator<char16_t> >)`
- `0x1801c78d2`: `enum asg::SemanticIndex::DbLock::AccessDbErrorCode __cdecl asg::SemanticIndex::DbLock::TryAccessDb(class std::basic_string<char16_t,struct std::char_traits<char16_t>,class std::allocator<char16_t> >)`
- `0x1801c798f`: `enum asg::SemanticIndex::DbLock::AccessDbErrorCode __cdecl asg::SemanticIndex::DbLock::TryAccessDb(class std::basic_string<char16_t,struct std::char_traits<char16_t>,class std::allocator<char16_t> >)`
- `0x1801c7b03`: `enum asg::SemanticIndex::DbLock::AccessDbErrorCode __cdecl asg::SemanticIndex::DbLock::TryAccessDb(class std::basic_string<char16_t,struct std::char_traits<char16_t>,class std::allocator<char16_t> >)`
- `0x1801c78fb`: `CreateSemaphore failed in DbLock::TryAccessDb; GetLastError() = %d`
- `0x1801c79d5`: `WaitForSingleObject failed in DbLock::TryAccessDb; GetLastError() = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall asg::SemanticIndex::DbLock::TryAccessDb(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rdi
  _QWORD *v4; // rcx
  const wchar_t *v5; // rcx
  size_t v6; // r8
  _QWORD *v7; // rax
  __m128i *inserted; // r14
  __int64 v9; // r8
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // r15
  __int64 v12; // rsi
  const WCHAR *v13; // r9
  unsigned int v14; // r14d
  WCHAR *v15; // rcx
  __m128i si128; // xmm0
  void *v17; // rcx
  char LastError; // dl
  DWORD v20; // esi
  char v21; // cl
  __int64 v22; // rbx
  unsigned __int64 v23; // rdx
  _QWORD *v24; // rcx
  __int128 v25; // [rsp+40h] [rbp-C0h] BYREF
  __m128i v26; // [rsp+50h] [rbp-B0h]
  int v27[4]; // [rsp+60h] [rbp-A0h] BYREF
  __m128i v28; // [rsp+70h] [rbp-90h]
  LPCWSTR lpName[2]; // [rsp+80h] [rbp-80h] BYREF
  __m128i v30; // [rsp+90h] [rbp-70h]
  char v31; // [rsp+A0h] [rbp-60h]
  int v32[4]; // [rsp+C0h] [rbp-40h] BYREF
  __m128i v33; // [rsp+D0h] [rbp-30h]
  char v34; // [rsp+E0h] [rbp-20h]
  HANDLE hHandle[3]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v36[8]; // [rsp+110h] [rbp+10h] BYREF
  int v37; // [rsp+150h] [rbp+50h]
  int v38; // [rsp+154h] [rbp+54h]
  const char *v39; // [rsp+158h] [rbp+58h]
  const char *v40; // [rsp+160h] [rbp+60h]

  v2 = a2;
  hHandle[1] = a2;
  v4 = *(_QWORD **)a1;
  if ( *v4 )
  {
    v5 = (const wchar_t *)(v4 + 2);
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    v6 = *((_QWORD *)v5 + 2);
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(const wchar_t **)v5;
    if ( v6 == v2[2] )
    {
      if ( !v6
        || (*(_QWORD *)&v25 = 0xD0000006CLL,
            *((_QWORD *)&v25 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DbLock.cpp",
            v26.m128i_i64[0] = (__int64)"enum asg::SemanticIndex::DbLock::AccessDbErrorCode __cdecl asg::SemanticIndex::D"
                                        "bLock::TryAccessDb(class std::basic_string<char16_t,struct std::char_traits<char"
                                        "16_t>,class std::allocator<char16_t> >)",
            !wmemcmp(v5, (const wchar_t *)a2, v6)) )
      {
LABEL_50:
        std::basic_string<char16_t>::_Tidy_deallocate(v2);
        return 0;
      }
    }
    else
    {
      *(_QWORD *)&v25 = 0xD0000006CLL;
      *((_QWORD *)&v25 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DbLock.cpp";
      v26.m128i_i64[0] = (__int64)"enum asg::SemanticIndex::DbLock::AccessDbErrorCode __cdecl asg::SemanticIndex::DbLock:"
                                  ":TryAccessDb(class std::basic_string<char16_t,struct std::char_traits<char16_t>,class "
                                  "std::allocator<char16_t> >)";
    }
    *(_OWORD *)lpName = v25;
    v30.m128i_i64[0] = v26.m128i_i64[0];
    asg::details::AsgAssertFail(lpName);
  }
  v7 = a2;
  if ( a2[3] > 7u )
    v7 = (_QWORD *)*a2;
  *(_QWORD *)&v25 = v7;
  *((_QWORD *)&v25 + 1) = a2[2];
  inserted = (__m128i *)asg::utf16ToWide(v27, &v25);
  v9 = inserted[1].m128i_i64[0];
  v10 = inserted[1].m128i_u64[1];
  if ( v10 - v9 < 7 )
  {
    inserted = (__m128i *)____Reallocate_grow_by_V_lambda_1___1__insert___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__KQEB_W0_Z__KPEB_W_K___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__insert_01_QEAAAEAV01_0QEB_W0_Z__KPEB_W3_Z(
                            inserted,
                            (__int64)L"Global\\",
                            7);
  }
  else
  {
    inserted[1].m128i_i64[0] = v9 + 7;
    v11 = (unsigned __int64)inserted;
    if ( v10 > 7 )
      v11 = inserted->m128i_i64[0];
    if ( (unsigned __int64)L"" <= v11 || (unsigned __int64)L"Global\\" > v11 + 2 * v9 )
    {
      v12 = 7;
    }
    else if ( v11 > (unsigned __int64)L"Global\\" )
    {
      v12 = (__int64)(v11 - (_QWORD)L"Global\\") >> 1;
    }
    else
    {
      v12 = 0;
    }
    memmove((void *)(v11 + 14), (const void *)v11, 2 * v9 + 2);
    memmove((void *)v11, L"Global\\", 2 * v12);
    memmove((void *)(2 * v12 + v11), &aGlobal[2 * v12 + 14], 2 * (7 - v12));
  }
  *(_OWORD *)lpName = 0;
  v30 = 0;
  *(__m128i *)lpName = *inserted;
  v30 = inserted[1];
  inserted->m128i_i16[0] = 0;
  inserted[1].m128i_i64[0] = 0;
  inserted[1].m128i_i64[1] = 7;
  v13 = (const WCHAR *)lpName;
  if ( v30.m128i_i64[1] > 7uLL )
    v13 = lpName[0];
  v14 = 1;
  hHandle[0] = CreateSemaphoreW(0, 1, 1, v13);
  if ( v30.m128i_i64[1] > 7uLL )
  {
    v15 = (WCHAR *)lpName[0];
    if ( (unsigned __int64)(2 * v30.m128i_i64[1] + 2) >= 0x1000 )
    {
      v15 = (WCHAR *)*((_QWORD *)lpName[0] - 1);
      if ( (unsigned __int64)((char *)lpName[0] - (char *)v15 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v15);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v30 = si128;
  LOWORD(lpName[0]) = 0;
  if ( v28.m128i_i64[1] > 7uLL )
  {
    v17 = *(void **)v27;
    if ( (unsigned __int64)(2 * v28.m128i_i64[1] + 2) >= 0x1000 )
    {
      v17 = *(void **)(*(_QWORD *)v27 - 8LL);
      if ( (unsigned __int64)(*(_QWORD *)v27 - (_QWORD)v17 - 8LL) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v17);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  v28 = si128;
  LOWORD(v27[0]) = 0;
  LastError = GetLastError();
  if ( hHandle[0] )
  {
    v20 = WaitForSingleObject(hHandle[0], *(_DWORD *)(*(_QWORD *)a1 + 8LL));
    v21 = GetLastError();
    if ( (v20 & 0xFFFFFF7F) == 0 )
    {
      v22 = *(_QWORD *)a1 + 16LL;
      if ( (_QWORD *)v22 != v2 )
      {
        v23 = *(_QWORD *)(*(_QWORD *)a1 + 40LL);
        if ( v23 > 7 )
        {
          v24 = *(_QWORD **)v22;
          if ( 2 * v23 + 2 >= 0x1000 )
          {
            if ( (unsigned __int64)v24 - *(v24 - 1) - 8 > 0x1F )
              invoke_watson(0, 0, 0, 0, 0);
            v24 = (_QWORD *)*(v24 - 1);
          }
          _mm_lfence();
          operator delete(v24);
        }
        *(_QWORD *)(v22 + 16) = 0;
        *(_QWORD *)(v22 + 24) = 7;
        *(_WORD *)v22 = 0;
        *(_OWORD *)v22 = *(_OWORD *)v2;
        *(_OWORD *)(v22 + 16) = *((_OWORD *)v2 + 1);
        v2[2] = 0;
        v2[3] = 7;
        *(_WORD *)v2 = 0;
      }
      **(HANDLE **)a1 = hHandle[0];
      goto LABEL_50;
    }
    v36[0] = ___7___Func_impl_no_alloc_V_lambda_1___1__TryAccessDb_DbLock_SemanticIndex_asg__QEAA_AW4AccessDbErrorCode_345_V__basic_string__SU__char_traits__S_std__V__allocator__S_2__std___Z_X__V_std__6B_;
    v36[1] = hHandle;
    v36[7] = v36;
    v37 = 131;
    v38 = 35;
    v39 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DbLock.cpp";
    v40 = "enum asg::SemanticIndex::DbLock::AccessDbErrorCode __cdecl asg::SemanticIndex::DbLock::TryAccessDb(class std::"
          "basic_string<char16_t,struct std::char_traits<char16_t>,class std::allocator<char16_t> >)";
    if ( v20 != -1 )
    {
      v14 = 3;
      v32[0] = 137;
      v32[1] = 13;
      *(_QWORD *)&v32[2] = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DbLock.cpp";
      v33.m128i_i64[0] = (__int64)"enum asg::SemanticIndex::DbLock::AccessDbErrorCode __cdecl asg::SemanticIndex::DbLock:"
                                  ":TryAccessDb(class std::basic_string<char16_t,struct std::char_traits<char16_t>,class "
                                  "std::allocator<char16_t> >)";
      v33.m128i_i8[8] = 1;
      *(_OWORD *)v27 = *(_OWORD *)v32;
      v28 = v33;
      asg::details::_asg_Log<std::integral_constant<bool,1>>(
        (int)lpName,
        (int)v27,
        4,
        (int)L"WaitForSingleObject failed in DbLock::TryAccessDb; GetLastError() = %d",
        v21);
      if ( v31 )
        std::basic_string<char16_t>::_Tidy_deallocate(lpName);
    }
    asg::OnScopeExit::~OnScopeExit((asg::OnScopeExit *)v36);
    std::basic_string<char16_t>::_Tidy_deallocate(v2);
    return v14;
  }
  else
  {
    *(_QWORD *)&v25 = 0xD00000076LL;
    *((_QWORD *)&v25 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DbLock.cpp";
    v26.m128i_i64[0] = (__int64)"enum asg::SemanticIndex::DbLock::AccessDbErrorCode __cdecl asg::SemanticIndex::DbLock::T"
                                "ryAccessDb(class std::basic_string<char16_t,struct std::char_traits<char16_t>,class std:"
                                ":allocator<char16_t> >)";
    v26.m128i_i8[8] = 1;
    *(_OWORD *)v27 = v25;
    v28 = v26;
    asg::details::_asg_Log<std::integral_constant<bool,1>>(
      (int)v32,
      (int)v27,
      4,
      (int)L"CreateSemaphore failed in DbLock::TryAccessDb; GetLastError() = %d",
      LastError);
    if ( v34 )
      std::basic_string<char16_t>::_Tidy_deallocate(v32);
    std::basic_string<char16_t>::_Tidy_deallocate(v2);
    return 2;
  }
}

```

## disassembly

```asm
0x1801c75f0  mov     [rsp-8+arg_10], rbx
0x1801c75f5  push    rbp
0x1801c75f6  push    rsi
0x1801c75f7  push    rdi
0x1801c75f8  push    r12
0x1801c75fa  push    r13
0x1801c75fc  push    r14
0x1801c75fe  push    r15
0x1801c7600  lea     rbp, [rsp-80h]
0x1801c7605  sub     rsp, 180h
0x1801c760c  mov     rax, cs:__security_cookie
0x1801c7613  xor     rax, rsp
0x1801c7616  mov     [rbp+0B0h+var_40], rax
0x1801c761a  mov     rdi, rdx
0x1801c761d  mov     r13, rcx
0x1801c7620  mov     [rbp+0B0h+var_B0], rdx
0x1801c7624  xor     r15d, r15d
0x1801c7627  mov     rcx, [rcx]
0x1801c762a  cmp     [rcx], r15
0x1801c762d  jz      short loc_1801C7698
0x1801c762f  add     rcx, 10h
0x1801c7633  cmp     qword ptr [rdx+18h], 7
0x1801c7638  jbe     short loc_1801C763D
0x1801c763a  mov     rdx, [rdx]; S2
0x1801c763d  mov     r8, [rcx+10h]; N
0x1801c7641  cmp     qword ptr [rcx+18h], 7
0x1801c7646  jbe     short loc_1801C764B
0x1801c7648  mov     rcx, [rcx]; S1
0x1801c764b  cmp     r8, [rdi+10h]
0x1801c764f  jnz     loc_1801C7AE7
0x1801c7655  test    r8, r8
0x1801c7658  jz      loc_1801C7AA1
0x1801c765e  mov     dword ptr [rsp+1B0h+var_170], 6Ch ; 'l'
0x1801c7666  mov     dword ptr [rsp+1B0h+var_170+4], 0Dh
0x1801c766e  lea     rax, aCW1SSrcSemanti_38; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1801c7675  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x1801c767a  lea     rbx, aEnumAsgSemanti_0; "enum asg::SemanticIndex::DbLock::Access"...
0x1801c7681  mov     qword ptr [rsp+1B0h+var_160], rbx
0x1801c7686  call    wmemcmp
0x1801c768b  test    eax, eax
0x1801c768d  jnz     loc_1801C7B0F
0x1801c7693  jmp     loc_1801C7AA1
0x1801c7698  mov     rax, rdi
0x1801c769b  cmp     qword ptr [rdx+18h], 7
0x1801c76a0  jbe     short loc_1801C76A5
0x1801c76a2  mov     rax, [rdx]
0x1801c76a5  mov     qword ptr [rsp+1B0h+var_170], rax
0x1801c76aa  mov     rax, [rdx+10h]
0x1801c76ae  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x1801c76b3  lea     rdx, [rsp+1B0h+var_170]
0x1801c76b8  lea     rcx, [rsp+1B0h+var_150]
0x1801c76bd  call    ?utf16ToWide@asg@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@3@@Z; asg::utf16ToWide(std::u16string_view)
0x1801c76c2  mov     r14, rax
0x1801c76c5  mov     r8, [rax+10h]
0x1801c76c9  mov     rcx, [rax+18h]
0x1801c76cd  mov     rax, rcx
0x1801c76d0  sub     rax, r8
0x1801c76d3  cmp     rax, 7
0x1801c76d7  jb      loc_1801C776F
0x1801c76dd  lea     rax, [r8+7]
0x1801c76e1  mov     [r14+10h], rax
0x1801c76e5  mov     r15, r14
0x1801c76e8  cmp     rcx, 7
0x1801c76ec  jbe     short loc_1801C76F1
0x1801c76ee  mov     r15, [r14]
0x1801c76f1  lea     rax, aGlobal+0Eh; ""
0x1801c76f8  lea     r12, aGlobal; "Global\\"
0x1801c76ff  cmp     rax, r15
0x1801c7702  jbe     short loc_1801C7721
0x1801c7704  lea     rax, [r15+r8*2]
0x1801c7708  cmp     r12, rax
0x1801c770b  ja      short loc_1801C7721
0x1801c770d  cmp     r15, r12
0x1801c7710  ja      short loc_1801C7716
0x1801c7712  xor     esi, esi
0x1801c7714  jmp     short loc_1801C7726
0x1801c7716  mov     rsi, r15
0x1801c7719  sub     rsi, r12
0x1801c771c  sar     rsi, 1
0x1801c771f  jmp     short loc_1801C7726
0x1801c7721  mov     esi, 7
0x1801c7726  lea     r8, ds:2[r8*2]; Size
0x1801c772e  lea     rcx, [r15+0Eh]; void *
0x1801c7732  mov     rdx, r15; Src
0x1801c7735  call    memmove
0x1801c773a  lea     rbx, [rsi+rsi]
0x1801c773e  mov     r8, rbx; Size
0x1801c7741  mov     rdx, r12; Src
0x1801c7744  mov     rcx, r15; void *
0x1801c7747  call    memmove
0x1801c774c  mov     r8d, 7
0x1801c7752  sub     r8, rsi
0x1801c7755  add     r8, r8; Size
0x1801c7758  lea     rdx, [r12+0Eh]
0x1801c775d  lea     rdx, [rdx+rsi*2]; Src
0x1801c7761  lea     rcx, [rbx+r15]; void *
0x1801c7765  call    memmove
0x1801c776a  xor     r15d, r15d
0x1801c776d  jmp     short loc_1801C779D
0x1801c776f  mov     [rsp+1B0h+var_188], 7; __int64
0x1801c7778  lea     r12, aGlobal; "Global\\"
0x1801c777f  mov     [rsp+1B0h+Reserved], r12; __int64
0x1801c7784  xor     r9d, r9d
0x1801c7787  movzx   r8d, [rsp+1B0h+var_180]
0x1801c778d  mov     edx, 7
0x1801c7792  mov     rcx, r14; Src
0x1801c7795  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_KQEB_W0@Z@_KPEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??insert@01@QEAAAEAV01@0QEB_W0@Z@_KPEB_W3@Z; std::wstring::_Reallocate_grow_by<`std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,unsigned __int64,wchar_t const *,unsigned __int64>(unsigned __int64,`std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,unsigned __int64,wchar_t const *,unsigned __int64)
0x1801c779a  mov     r14, rax
0x1801c779d  xorps   xmm0, xmm0
0x1801c77a0  movups  xmmword ptr [rbp+0B0h+lpName], xmm0
0x1801c77a4  xorps   xmm1, xmm1
0x1801c77a7  movdqu  [rbp+0B0h+var_120], xmm1
0x1801c77ac  movups  xmm0, xmmword ptr [r14]
0x1801c77b0  movups  xmmword ptr [rbp+0B0h+lpName], xmm0
0x1801c77b4  movups  xmm1, xmmword ptr [r14+10h]
0x1801c77b9  movups  [rbp+0B0h+var_120], xmm1
0x1801c77bd  mov     [r14], r15w
0x1801c77c1  mov     [r14+10h], r15
0x1801c77c5  mov     qword ptr [r14+18h], 7
0x1801c77cd  lea     r9, [rbp+0B0h+lpName]
0x1801c77d1  cmp     qword ptr [rbp+0B0h+var_120+8], 7
0x1801c77d6  cmova   r9, [rbp+0B0h+lpName]; lpName
0x1801c77db  mov     r14d, 1
0x1801c77e1  mov     r8d, r14d; lMaximumCount
0x1801c77e4  mov     edx, r14d; lInitialCount
0x1801c77e7  xor     ecx, ecx; lpSemaphoreAttributes
0x1801c77e9  call    cs:__imp_CreateSemaphoreW
0x1801c77ef  mov     [rbp+0B0h+hHandle], rax
0x1801c77f3  mov     rdx, qword ptr [rbp+0B0h+var_120+8]
0x1801c77f7  cmp     rdx, 7
0x1801c77fb  jbe     short loc_1801C7836
0x1801c77fd  lea     rdx, ds:2[rdx*2]
0x1801c7805  mov     rcx, [rbp+0B0h+lpName]
0x1801c7809  mov     rax, rcx
0x1801c780c  cmp     rdx, 1000h
0x1801c7813  jb      short loc_1801C782E
0x1801c7815  add     rdx, 27h ; '''
0x1801c7819  mov     rcx, [rcx-8]; Block
0x1801c781d  sub     rax, rcx
0x1801c7820  sub     rax, 8
0x1801c7824  cmp     rax, 1Fh
0x1801c7828  ja      loc_1801C7B45
0x1801c782e  lfence
0x1801c7831  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801c7836  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1801c783e  movdqu  [rbp+0B0h+var_120], xmm0
0x1801c7843  mov     word ptr [rbp+0B0h+lpName], r15w
0x1801c7848  mov     rdx, [rsp+1B0h+var_138]
0x1801c784d  cmp     rdx, 7
0x1801c7851  jbe     short loc_1801C7895
0x1801c7853  lea     rdx, ds:2[rdx*2]
0x1801c785b  mov     rcx, qword ptr [rsp+1B0h+var_150]
0x1801c7860  mov     rax, rcx
0x1801c7863  cmp     rdx, 1000h
0x1801c786a  jb      short loc_1801C7885
0x1801c786c  add     rdx, 27h ; '''
0x1801c7870  mov     rcx, [rcx-8]; Block
0x1801c7874  sub     rax, rcx
0x1801c7877  sub     rax, 8
0x1801c787b  cmp     rax, 1Fh
0x1801c787f  ja      loc_1801C7AD2
0x1801c7885  lfence
0x1801c7888  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801c788d  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1801c7895  movdqu  xmmword ptr [rsp+70h], xmm0
0x1801c789b  mov     word ptr [rsp+1B0h+var_150], r15w
0x1801c78a1  call    cs:__imp_GetLastError
0x1801c78a7  mov     edx, eax
0x1801c78a9  mov     rcx, [rbp+0B0h+hHandle]; hHandle
0x1801c78ad  test    rcx, rcx
0x1801c78b0  jnz     loc_1801C7938
0x1801c78b6  mov     dword ptr [rsp+1B0h+var_170], 76h ; 'v'
0x1801c78be  mov     dword ptr [rsp+1B0h+var_170+4], 0Dh
0x1801c78c6  lea     rax, aCW1SSrcSemanti_38; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1801c78cd  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x1801c78d2  lea     rbx, aEnumAsgSemanti_0; "enum asg::SemanticIndex::DbLock::Access"...
0x1801c78d9  mov     qword ptr [rsp+1B0h+var_160], rbx
0x1801c78de  mov     byte ptr [rsp+1B0h+var_160+8], 1
0x1801c78e3  movups  xmm0, [rsp+1B0h+var_170]
0x1801c78e8  movaps  xmmword ptr [rsp+1B0h+var_150], xmm0
0x1801c78ed  movups  xmm1, [rsp+1B0h+var_160]
0x1801c78f2  movaps  xmmword ptr [rsp+70h], xmm1
0x1801c78f7  mov     dword ptr [rsp+1B0h+Reserved], edx; ArgList
0x1801c78fb  lea     r9, aCreatesemaphor; "CreateSemaphore failed in DbLock::TryAc"...
0x1801c7902  mov     r8d, 4; int
0x1801c7908  lea     rdx, [rsp+1B0h+var_150]; int
0x1801c790d  lea     rcx, [rbp+0B0h+var_F0]; int
0x1801c7911  call    ??$_asg_Log@U?$integral_constant@_N$00@std@@@details@asg@@YA?AULogStringView@1@V?$optional@Usource_location@std@@@std@@W4LogLevel@1@PEB_SZZ; asg::details::_asg_Log<std::integral_constant<bool,1>>(std::optional<std::source_location>,asg::LogLevel,char16_t const *,...)
0x1801c7916  cmp     [rbp+0B0h+var_D0], 0
0x1801c791a  jz      short loc_1801C7926
0x1801c791c  lea     rcx, [rbp+0B0h+var_F0]
0x1801c7920  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1801c7925  nop
0x1801c7926  mov     rcx, rdi
0x1801c7929  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1801c792e  mov     eax, 2
0x1801c7933  jmp     loc_1801C7AAB
0x1801c7938  mov     rdx, [r13+0]
0x1801c793c  mov     edx, [rdx+8]; dwMilliseconds
0x1801c793f  call    cs:__imp_WaitForSingleObject
0x1801c7945  mov     esi, eax
0x1801c7947  call    cs:__imp_GetLastError
0x1801c794d  mov     ecx, eax
0x1801c794f  test    esi, 0FFFFFF7Fh
0x1801c7955  jz      loc_1801C7A19
0x1801c795b  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1??TryAccessDb@DbLock@SemanticIndex@asg@@QEAA?AW4AccessDbErrorCode@345@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@Z@X$$V@std@@6B@; const std::_Func_impl_no_alloc<`asg::SemanticIndex::DbLock::TryAccessDb(std::basic_string<char16_t>)'::`2'::_lambda_1_,void,>::`vftable'
0x1801c7962  mov     [rbp+0B0h+var_A0], rax
0x1801c7966  lea     rax, [rbp+0B0h+hHandle]
0x1801c796a  mov     [rbp+0B0h+var_98], rax
0x1801c796e  lea     rax, [rbp+0B0h+var_A0]
0x1801c7972  mov     [rbp+0B0h+var_68], rax
0x1801c7976  mov     [rbp+0B0h+var_60], 83h
0x1801c797d  mov     [rbp+0B0h+var_5C], 23h ; '#'
0x1801c7984  lea     rax, aCW1SSrcSemanti_38; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1801c798b  mov     [rbp+0B0h+var_58], rax
0x1801c798f  lea     rbx, aEnumAsgSemanti_0; "enum asg::SemanticIndex::DbLock::Access"...
0x1801c7996  mov     [rbp+0B0h+var_50], rbx
0x1801c799a  cmp     esi, 0FFFFFFFFh
0x1801c799d  jz      short loc_1801C79FF
0x1801c799f  mov     r14d, 3
0x1801c79a5  mov     [rbp+0B0h+var_F0], 89h
0x1801c79ac  mov     [rbp+0B0h+var_F0+4], 0Dh
0x1801c79b3  mov     qword ptr [rbp+0B0h+var_F0+8], rax
0x1801c79b7  mov     qword ptr [rbp+0B0h+var_E0], rbx
0x1801c79bb  mov     byte ptr [rbp+0B0h+var_E0+8], 1
0x1801c79bf  movups  xmm0, xmmword ptr [rbp+0B0h+var_F0]
0x1801c79c3  movaps  xmmword ptr [rsp+1B0h+var_150], xmm0
0x1801c79c8  movups  xmm1, [rbp+0B0h+var_E0]
0x1801c79cc  movaps  xmmword ptr [rsp+70h], xmm1
0x1801c79d1  mov     dword ptr [rsp+1B0h+Reserved], ecx; ArgList
0x1801c79d5  lea     r9, aWaitforsingleo_2; "WaitForSingleObject failed in DbLock::T"...
0x1801c79dc  mov     r8d, 4; int
0x1801c79e2  lea     rdx, [rsp+1B0h+var_150]; int
0x1801c79e7  lea     rcx, [rbp+0B0h+lpName]; int
0x1801c79eb  call    ??$_asg_Log@U?$integral_constant@_N$00@std@@@details@asg@@YA?AULogStringView@1@V?$optional@Usource_location@std@@@std@@W4LogLevel@1@PEB_SZZ; asg::details::_asg_Log<std::integral_constant<bool,1>>(std::optional<std::source_location>,asg::LogLevel,char16_t const *,...)
0x1801c79f0  cmp     [rbp+0B0h+var_110], 0
0x1801c79f4  jz      short loc_1801C79FF
0x1801c79f6  lea     rcx, [rbp+0B0h+lpName]
0x1801c79fa  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1801c79ff  lea     rcx, [rbp+0B0h+var_A0]; this
0x1801c7a03  call    ??1OnScopeExit@asg@@QEAA@XZ; asg::OnScopeExit::~OnScopeExit(void)
0x1801c7a08  nop
0x1801c7a09  mov     rcx, rdi
0x1801c7a0c  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1801c7a11  mov     eax, r14d
0x1801c7a14  jmp     loc_1801C7AAB
0x1801c7a19  mov     rbx, [r13+0]
0x1801c7a1d  add     rbx, 10h
0x1801c7a21  cmp     rbx, rdi
0x1801c7a24  jz      short loc_1801C7A96
0x1801c7a26  mov     rdx, [rbx+18h]
0x1801c7a2a  cmp     rdx, 7
0x1801c7a2e  jbe     short loc_1801C7A68
0x1801c7a30  mov     rcx, [rbx]
0x1801c7a33  lea     rdx, ds:2[rdx*2]
0x1801c7a3b  cmp     rdx, 1000h
0x1801c7a42  jb      short loc_1801C7A60
0x1801c7a44  add     rdx, 27h ; '''
0x1801c7a48  mov     rax, [rcx-8]
0x1801c7a4c  sub     rcx, rax
0x1801c7a4f  sub     rcx, 8
0x1801c7a53  cmp     rcx, 1Fh
0x1801c7a57  ja      loc_1801C7B30
0x1801c7a5d  mov     rcx, rax; Block
0x1801c7a60  lfence
0x1801c7a63  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801c7a68  mov     [rbx+10h], r15
0x1801c7a6c  mov     qword ptr [rbx+18h], 7
0x1801c7a74  mov     [rbx], r15w
0x1801c7a78  movups  xmm0, xmmword ptr [rdi]
0x1801c7a7b  movups  xmmword ptr [rbx], xmm0
0x1801c7a7e  movups  xmm1, xmmword ptr [rdi+10h]
0x1801c7a82  movups  xmmword ptr [rbx+10h], xmm1
0x1801c7a86  mov     [rdi+10h], r15
0x1801c7a8a  mov     qword ptr [rdi+18h], 7
0x1801c7a92  mov     [rdi], r15w
0x1801c7a96  mov     rcx, [r13+0]
0x1801c7a9a  mov     rax, [rbp+0B0h+hHandle]
0x1801c7a9e  mov     [rcx], rax
0x1801c7aa1  mov     rcx, rdi
0x1801c7aa4  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1801c7aa9  xor     eax, eax
0x1801c7aab  mov     rcx, [rbp+0B0h+var_40]
0x1801c7aaf  xor     rcx, rsp; StackCookie
0x1801c7ab2  call    __security_check_cookie
0x1801c7ab7  mov     rbx, [rsp+1B0h+arg_10]
0x1801c7abf  add     rsp, 180h
0x1801c7ac6  pop     r15
0x1801c7ac8  pop     r14
0x1801c7aca  pop     r13
0x1801c7acc  pop     r12
0x1801c7ace  pop     rdi
0x1801c7acf  pop     rsi
0x1801c7ad0  pop     rbp
0x1801c7ad1  retn
0x1801c7ad2  mov     [rsp+1B0h+Reserved], r15; Reserved
0x1801c7ad7  xor     r9d, r9d; LineNo
0x1801c7ada  xor     r8d, r8d; FileName
0x1801c7add  xor     edx, edx; FunctionName
0x1801c7adf  xor     ecx, ecx; Expression
  ... truncated ...
```
