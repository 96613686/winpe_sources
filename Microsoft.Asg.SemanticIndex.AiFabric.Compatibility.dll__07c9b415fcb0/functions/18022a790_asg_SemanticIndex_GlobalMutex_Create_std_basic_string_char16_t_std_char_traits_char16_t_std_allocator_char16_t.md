# asg::SemanticIndex::GlobalMutex::Create(std::basic_string<char16_t,std::char_traits<char16_t>,std::allocator<char16_t>>,uint)

- ea: `0x18022a790`
- end: `0x18022abd1`
- name: `?Create@GlobalMutex@SemanticIndex@asg@@SA?AV?$tuple@V?$unique_ptr@VGlobalMutex@SemanticIndex@asg@@U?$default_delete@VGlobalMutex@SemanticIndex@asg@@@std@@@std@@W4CreateErrorCode@GlobalMutex@SemanticIndex@asg@@@std@@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@5@I@Z`
- size: `1089`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1801a21c0`

## callees

- `0x180007e60`
- `0x1800178d0`
- `0x18007aef0`
- `0x18007c5e0`
- `0x1801c7350`
- `0x1801d3160`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x180206ec0`
- `0x18022a790`
- `0x1802421a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18022a9bc`
- `KERNEL32!GetLastError` at `0x18022aa54`
- `KERNEL32!GetLastError` at `0x18022a9bc`
- `KERNEL32!GetLastError` at `0x18022aa54`
- `KERNEL32!WaitForSingleObject` at `0x18022aa4b`
- `KERNEL32!WaitForSingleObject` at `0x18022aa4b`
- `KERNEL32!CreateMutexW` at `0x18022a918`
- `KERNEL32!CreateMutexW` at `0x18022a918`

## string_xrefs

- `0x18022aa10`: `CreateMutex failed in GlobalMutex::Create; GetLastError() = %d`
- `0x18022a9e7`: `class std::tuple<class std::unique_ptr<class asg::SemanticIndex::GlobalMutex,struct std::default_delete<class asg::SemanticIndex::GlobalMutex> >,enum asg::SemanticIndex::GlobalMutex::CreateErrorCode> __cdecl asg::SemanticIndex::GlobalMutex::Create(class std::basic_string<char16_t,struct std::char_traits<char16_t>,class std::allocator<char16_t> >,unsigned int)`
- `0x18022aa9b`: `class std::tuple<class std::unique_ptr<class asg::SemanticIndex::GlobalMutex,struct std::default_delete<class asg::SemanticIndex::GlobalMutex> >,enum asg::SemanticIndex::GlobalMutex::CreateErrorCode> __cdecl asg::SemanticIndex::GlobalMutex::Create(class std::basic_string<char16_t,struct std::char_traits<char16_t>,class std::allocator<char16_t> >,unsigned int)`
- `0x18022aae6`: `WaitForSingleObject failed in GlobalMutex::Create; GetLastError() = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall asg::SemanticIndex::GlobalMutex::Create(_QWORD *a1, _QWORD *a2, DWORD a3)
{
  DWORD v3; // ebx
  __int64 v6; // r15
  _QWORD *v7; // rax
  __m128i *inserted; // r14
  __int64 v9; // r8
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // r12
  const WCHAR *v12; // r8
  WCHAR *v13; // rcx
  void *v14; // rcx
  char LastError; // al
  DWORD v16; // r14d
  char v17; // al
  int v18; // ebx
  _QWORD *v19; // rbx
  _OWORD *v20; // rax
  __int128 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v24; // [rsp+50h] [rbp-B0h]
  int v25[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v26; // [rsp+70h] [rbp-90h]
  LPCWSTR lpName[2]; // [rsp+88h] [rbp-78h] BYREF
  __m128i si128; // [rsp+98h] [rbp-68h]
  char v29; // [rsp+A8h] [rbp-58h]
  int v30[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v31; // [rsp+D0h] [rbp-30h]
  char v32; // [rsp+E0h] [rbp-20h]
  HANDLE hHandle[3]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v34[8]; // [rsp+110h] [rbp+10h] BYREF
  int v35; // [rsp+150h] [rbp+50h]
  int v36; // [rsp+154h] [rbp+54h]
  const char *v37; // [rsp+158h] [rbp+58h]
  const char *v38; // [rsp+160h] [rbp+60h]

  v3 = a3;
  hHandle[0] = a1;
  hHandle[1] = a2;
  v6 = 0;
  v7 = a2;
  if ( a2[3] > 7u )
    v7 = (_QWORD *)*a2;
  *(_QWORD *)&v23 = v7;
  *((_QWORD *)&v23 + 1) = a2[2];
  inserted = (__m128i *)asg::utf16ToWide(v25, &v23);
  v9 = inserted[1].m128i_i64[0];
  v10 = inserted[1].m128i_u64[1];
  if ( v10 - v9 < 0x1D )
  {
    inserted = (__m128i *)____Reallocate_grow_by_V_lambda_1___1__insert___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__KQEB_W0_Z__KPEB_W_K___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__insert_01_QEAAAEAV01_0QEB_W0_Z__KPEB_W3_Z(
                            inserted,
                            (__int64)L"Global\\AsgSemanticIndexMutex_",
                            29);
  }
  else
  {
    inserted[1].m128i_i64[0] = v9 + 29;
    v11 = (unsigned __int64)inserted;
    if ( v10 > 7 )
      v11 = inserted->m128i_i64[0];
    if ( (unsigned __int64)L"" <= v11 || (unsigned __int64)L"Global\\AsgSemanticIndexMutex_" > v11 + 2 * v9 )
    {
      v6 = 29;
    }
    else if ( v11 > (unsigned __int64)L"Global\\AsgSemanticIndexMutex_" )
    {
      v6 = (__int64)(v11 - (_QWORD)L"Global\\AsgSemanticIndexMutex_") >> 1;
    }
    memmove((void *)(v11 + 58), (const void *)v11, 2 * v9 + 2);
    memmove((void *)v11, L"Global\\AsgSemanticIndexMutex_", 2 * v6);
    memmove((void *)(2 * v6 + v11), &aGlobalAsgseman[2 * v6 + 58], 2 * (29 - v6));
    v3 = a3;
  }
  *(_OWORD *)lpName = 0;
  si128 = 0;
  *(__m128i *)lpName = *inserted;
  si128 = inserted[1];
  inserted->m128i_i16[0] = 0;
  inserted[1].m128i_i64[0] = 0;
  inserted[1].m128i_i64[1] = 7;
  v12 = (const WCHAR *)lpName;
  if ( si128.m128i_i64[1] > 7uLL )
    v12 = lpName[0];
  hHandle[0] = CreateMutexW(0, 0, v12);
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v13 = (WCHAR *)lpName[0];
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v13 = (WCHAR *)*((_QWORD *)lpName[0] - 1);
      if ( (unsigned __int64)((char *)lpName[0] - (char *)v13 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v13);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpName[0]) = 0;
  if ( *((_QWORD *)&v26 + 1) > 7u )
  {
    v14 = *(void **)v25;
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v26 + 1) + 2) >= 0x1000 )
    {
      v14 = *(void **)(*(_QWORD *)v25 - 8LL);
      if ( (unsigned __int64)(*(_QWORD *)v25 - (_QWORD)v14 - 8LL) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v14);
  }
  LastError = GetLastError();
  if ( hHandle[0] )
  {
    v16 = WaitForSingleObject(hHandle[0], v3);
    v17 = GetLastError();
    if ( (v16 & 0xFFFFFF7F) != 0 )
    {
      v34[0] = ___7___Func_impl_no_alloc_V_lambda_1___1__Create_GlobalMutex_SemanticIndex_asg__SA_AV__tuple_V__unique_ptr_VGlobalMutex_SemanticIndex_asg__U__default_delete_VGlobalMutex_SemanticIndex_asg___std___std__W4CreateErrorCode_GlobalMutex_SemanticIndex_asg___std__V__basic_string__SU__char_traits__S_std__V__allocator__S_2__7_I_Z_X__V_std__6B_;
      v34[1] = hHandle;
      v34[7] = v34;
      v35 = 91;
      v36 = 40;
      v37 = "C:\\__w\\1\\s\\src\\Shared\\internal\\libSemanticShared\\GlobalMutex.cpp";
      v38 = "class std::tuple<class std::unique_ptr<class asg::SemanticIndex::GlobalMutex,struct std::default_delete<clas"
            "s asg::SemanticIndex::GlobalMutex> >,enum asg::SemanticIndex::GlobalMutex::CreateErrorCode> __cdecl asg::Sem"
            "anticIndex::GlobalMutex::Create(class std::basic_string<char16_t,struct std::char_traits<char16_t>,class std"
            "::allocator<char16_t> >,unsigned int)";
      v18 = 1;
      if ( v16 != -1 )
      {
        v18 = 3;
        v30[0] = 97;
        v30[1] = 13;
        *(_QWORD *)&v30[2] = "C:\\__w\\1\\s\\src\\Shared\\internal\\libSemanticShared\\GlobalMutex.cpp";
        *(_QWORD *)&v31 = "class std::tuple<class std::unique_ptr<class asg::SemanticIndex::GlobalMutex,struct std::defau"
                          "lt_delete<class asg::SemanticIndex::GlobalMutex> >,enum asg::SemanticIndex::GlobalMutex::Creat"
                          "eErrorCode> __cdecl asg::SemanticIndex::GlobalMutex::Create(class std::basic_string<char16_t,s"
                          "truct std::char_traits<char16_t>,class std::allocator<char16_t> >,unsigned int)";
        BYTE8(v31) = 1;
        *(_OWORD *)v25 = *(_OWORD *)v30;
        v26 = v31;
        asg::details::_asg_Log<std::integral_constant<bool,1>>(
          (int)lpName,
          (int)v25,
          4,
          (int)L"WaitForSingleObject failed in GlobalMutex::Create; GetLastError() = %d",
          v17);
        if ( v29 )
          asg::SemanticPipelines::RegionId::~RegionId((asg::SemanticPipelines::RegionId *)lpName);
      }
      *(_DWORD *)a1 = v18;
      a1[1] = 0;
      asg::OnScopeExit::~OnScopeExit((asg::OnScopeExit *)v34);
    }
    else
    {
      v19 = operator new(8u);
      if ( v19 )
      {
        *v19 = 0;
        *(HANDLE *)&v23 = hHandle[0];
        DWORD2(v23) = Thrd_id();
        v20 = operator new(0x10u);
        if ( v20 )
          *v20 = v23;
        else
          v20 = 0;
        *v19 = v20;
      }
      else
      {
        v19 = 0;
      }
      *(_DWORD *)a1 = 0;
      a1[1] = v19;
    }
  }
  else
  {
    *(_QWORD *)&v23 = 0xD00000048LL;
    *((_QWORD *)&v23 + 1) = "C:\\__w\\1\\s\\src\\Shared\\internal\\libSemanticShared\\GlobalMutex.cpp";
    *(_QWORD *)&v24 = "class std::tuple<class std::unique_ptr<class asg::SemanticIndex::GlobalMutex,struct std::default_d"
                      "elete<class asg::SemanticIndex::GlobalMutex> >,enum asg::SemanticIndex::GlobalMutex::CreateErrorCo"
                      "de> __cdecl asg::SemanticIndex::GlobalMutex::Create(class std::basic_string<char16_t,struct std::c"
                      "har_traits<char16_t>,class std::allocator<char16_t> >,unsigned int)";
    BYTE8(v24) = 1;
    *(_OWORD *)v25 = v23;
    v26 = v24;
    asg::details::_asg_Log<std::integral_constant<bool,1>>(
      (int)v30,
      (int)v25,
      4,
      (int)L"CreateMutex failed in GlobalMutex::Create; GetLastError() = %d",
      LastError);
    if ( v32 )
      asg::SemanticPipelines::RegionId::~RegionId((asg::SemanticPipelines::RegionId *)v30);
    *(_DWORD *)a1 = 2;
    a1[1] = 0;
  }
  asg::SemanticPipelines::RegionId::~RegionId((asg::SemanticPipelines::RegionId *)a2);
  return a1;
}

```

## disassembly

```asm
0x18022a790  mov     [rsp-8+arg_18], rbx
0x18022a795  push    rbp
0x18022a796  push    rsi
0x18022a797  push    rdi
0x18022a798  push    r12
0x18022a79a  push    r13
0x18022a79c  push    r14
0x18022a79e  push    r15
0x18022a7a0  lea     rbp, [rsp-80h]
0x18022a7a5  sub     rsp, 180h
0x18022a7ac  mov     rax, cs:__security_cookie
0x18022a7b3  xor     rax, rsp
0x18022a7b6  mov     [rbp+0B0h+var_40], rax
0x18022a7ba  mov     ebx, r8d
0x18022a7bd  mov     [rsp+1B0h+dwMilliseconds], ebx
0x18022a7c1  mov     rsi, rdx
0x18022a7c4  mov     rdi, rcx
0x18022a7c7  mov     [rbp+0B0h+hHandle], rcx
0x18022a7cb  mov     [rbp+0B0h+var_B0], rdx
0x18022a7cf  xor     r15d, r15d
0x18022a7d2  mov     rax, rdx
0x18022a7d5  cmp     qword ptr [rdx+18h], 7
0x18022a7da  jbe     short loc_18022A7DF
0x18022a7dc  mov     rax, [rdx]
0x18022a7df  mov     qword ptr [rsp+1B0h+var_170], rax
0x18022a7e4  mov     rax, [rdx+10h]
0x18022a7e8  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x18022a7ed  lea     rdx, [rsp+1B0h+var_170]
0x18022a7f2  lea     rcx, [rsp+1B0h+var_150]
0x18022a7f7  call    ?utf16ToWide@asg@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@3@@Z; asg::utf16ToWide(std::u16string_view)
0x18022a7fc  mov     r14, rax
0x18022a7ff  mov     r8, [rax+10h]
0x18022a803  mov     rcx, [rax+18h]
0x18022a807  mov     rax, rcx
0x18022a80a  sub     rax, r8
0x18022a80d  cmp     rax, 1Dh
0x18022a811  jb      loc_18022A8AC
0x18022a817  lea     rax, [r8+1Dh]
0x18022a81b  mov     [r14+10h], rax
0x18022a81f  mov     r12, r14
0x18022a822  cmp     rcx, 7
0x18022a826  jbe     short loc_18022A82B
0x18022a828  mov     r12, [r14]
0x18022a82b  lea     rax, aGlobalAsgseman+3Ah; ""
0x18022a832  mov     edx, 1Dh
0x18022a837  lea     r13, aGlobalAsgseman; "Global\\AsgSemanticIndexMutex_"
0x18022a83e  cmp     rax, r12
0x18022a841  jbe     short loc_18022A85C
0x18022a843  lea     rax, [r12+r8*2]
0x18022a847  cmp     r13, rax
0x18022a84a  ja      short loc_18022A85C
0x18022a84c  cmp     r12, r13
0x18022a84f  jbe     short loc_18022A85F
0x18022a851  mov     r15, r12
0x18022a854  sub     r15, r13
0x18022a857  sar     r15, 1
0x18022a85a  jmp     short loc_18022A85F
0x18022a85c  mov     r15, rdx
0x18022a85f  lea     r8, ds:2[r8*2]; Size
0x18022a867  lea     rcx, [r12+3Ah]; void *
0x18022a86c  mov     rdx, r12; Src
0x18022a86f  call    memmove
0x18022a874  lea     rbx, [r15+r15]
0x18022a878  mov     r8, rbx; Size
0x18022a87b  mov     rdx, r13; Src
0x18022a87e  mov     rcx, r12; void *
0x18022a881  call    memmove
0x18022a886  mov     eax, 1Dh
0x18022a88b  sub     rax, r15
0x18022a88e  lea     r8, [rax+rax]; Size
0x18022a892  lea     rdx, [r13+3Ah]
0x18022a896  lea     rdx, [rdx+r15*2]; Src
0x18022a89a  lea     rcx, [rbx+r12]; void *
0x18022a89e  call    memmove
0x18022a8a3  mov     ebx, [rsp+1B0h+dwMilliseconds]
0x18022a8a7  xor     r15d, r15d
0x18022a8aa  jmp     short loc_18022A8D6
0x18022a8ac  mov     edx, 1Dh
0x18022a8b1  mov     [rsp+1B0h+var_188], rdx; __int64
0x18022a8b6  lea     r13, aGlobalAsgseman; "Global\\AsgSemanticIndexMutex_"
0x18022a8bd  mov     [rsp+1B0h+Reserved], r13; __int64
0x18022a8c2  xor     r9d, r9d
0x18022a8c5  movzx   r8d, [rsp+1B0h+var_180]
0x18022a8cb  mov     rcx, r14; Src
0x18022a8ce  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_KQEB_W0@Z@_KPEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??insert@01@QEAAAEAV01@0QEB_W0@Z@_KPEB_W3@Z; std::wstring::_Reallocate_grow_by<`std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,unsigned __int64,wchar_t const *,unsigned __int64>(unsigned __int64,`std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,unsigned __int64,wchar_t const *,unsigned __int64)
0x18022a8d3  mov     r14, rax
0x18022a8d6  xorps   xmm0, xmm0
0x18022a8d9  movups  xmmword ptr [rbp+0B0h+lpName], xmm0
0x18022a8dd  xorps   xmm1, xmm1
0x18022a8e0  movdqu  [rbp+0B0h+var_118], xmm1
0x18022a8e5  movups  xmm0, xmmword ptr [r14]
0x18022a8e9  movups  xmmword ptr [rbp+0B0h+lpName], xmm0
0x18022a8ed  movups  xmm1, xmmword ptr [r14+10h]
0x18022a8f2  movups  [rbp+0B0h+var_118], xmm1
0x18022a8f6  mov     [r14], r15w
0x18022a8fa  mov     [r14+10h], r15
0x18022a8fe  mov     qword ptr [r14+18h], 7
0x18022a906  lea     r8, [rbp+0B0h+lpName]
0x18022a90a  cmp     qword ptr [rbp+0B0h+var_118+8], 7
0x18022a90f  cmova   r8, [rbp+0B0h+lpName]; lpName
0x18022a914  xor     edx, edx; bInitialOwner
0x18022a916  xor     ecx, ecx; lpMutexAttributes
0x18022a918  call    cs:__imp_CreateMutexW
0x18022a91e  mov     [rbp+0B0h+hHandle], rax
0x18022a922  mov     rdx, qword ptr [rbp+0B0h+var_118+8]
0x18022a926  cmp     rdx, 7
0x18022a92a  jbe     short loc_18022A965
0x18022a92c  lea     rdx, ds:2[rdx*2]
0x18022a934  mov     rcx, [rbp+0B0h+lpName]
0x18022a938  mov     rax, rcx
0x18022a93b  cmp     rdx, 1000h
0x18022a942  jb      short loc_18022A95D
0x18022a944  add     rdx, 27h ; '''
0x18022a948  mov     rcx, [rcx-8]; Block
0x18022a94c  sub     rax, rcx
0x18022a94f  sub     rax, 8
0x18022a953  cmp     rax, 1Fh
0x18022a957  ja      loc_18022ABBC
0x18022a95d  lfence
0x18022a960  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18022a965  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18022a96d  movdqu  [rbp+0B0h+var_118], xmm0
0x18022a972  mov     word ptr [rbp+0B0h+lpName], r15w
0x18022a977  mov     rdx, [rsp+1B0h+var_138]
0x18022a97c  cmp     rdx, 7
0x18022a980  jbe     short loc_18022A9BC
0x18022a982  lea     rdx, ds:2[rdx*2]
0x18022a98a  mov     rcx, qword ptr [rsp+1B0h+var_150]
0x18022a98f  mov     rax, rcx
0x18022a992  cmp     rdx, 1000h
0x18022a999  jb      short loc_18022A9B4
0x18022a99b  add     rdx, 27h ; '''
0x18022a99f  mov     rcx, [rcx-8]; Block
0x18022a9a3  sub     rax, rcx
0x18022a9a6  sub     rax, 8
0x18022a9aa  cmp     rax, 1Fh
0x18022a9ae  ja      loc_18022ABA7
0x18022a9b4  lfence
0x18022a9b7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18022a9bc  call    cs:__imp_GetLastError
0x18022a9c2  mov     rcx, [rbp+0B0h+hHandle]; hHandle
0x18022a9c6  test    rcx, rcx
0x18022a9c9  jnz     short loc_18022AA49
0x18022a9cb  mov     dword ptr [rsp+1B0h+var_170], 48h ; 'H'
0x18022a9d3  mov     dword ptr [rsp+1B0h+var_170+4], 0Dh
0x18022a9db  lea     rcx, aCW1SSrcSharedI_4; "C:\\__w\\1\\s\\src\\Shared\\internal\\l"...
0x18022a9e2  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x18022a9e7  lea     rdx, aClassStdTupleC; "class std::tuple<class std::unique_ptr<"...
0x18022a9ee  mov     qword ptr [rsp+1B0h+var_160], rdx
0x18022a9f3  mov     byte ptr [rsp+1B0h+var_160+8], 1
0x18022a9f8  movups  xmm0, [rsp+1B0h+var_170]
0x18022a9fd  movaps  xmmword ptr [rsp+1B0h+var_150], xmm0
0x18022aa02  movups  xmm1, [rsp+1B0h+var_160]
0x18022aa07  movaps  xmmword ptr [rsp+70h], xmm1
0x18022aa0c  mov     dword ptr [rsp+1B0h+Reserved], eax; ArgList
0x18022aa10  lea     r9, aCreatemutexFai; "CreateMutex failed in GlobalMutex::Crea"...
0x18022aa17  mov     r8d, 4; int
0x18022aa1d  lea     rdx, [rsp+1B0h+var_150]; int
0x18022aa22  lea     rcx, [rbp+0B0h+var_F0]; int
0x18022aa26  call    ??$_asg_Log@U?$integral_constant@_N$00@std@@@details@asg@@YA?AULogStringView@1@V?$optional@Usource_location@std@@@std@@W4LogLevel@1@PEB_SZZ; asg::details::_asg_Log<std::integral_constant<bool,1>>(std::optional<std::source_location>,asg::LogLevel,char16_t const *,...)
0x18022aa2b  cmp     [rbp+0B0h+var_D0], 0
0x18022aa2f  jz      short loc_18022AA3A
0x18022aa31  lea     rcx, [rbp+0B0h+var_F0]; this
0x18022aa35  call    ??1RegionId@SemanticPipelines@asg@@QEAA@XZ; asg::SemanticPipelines::RegionId::~RegionId(void)
0x18022aa3a  mov     dword ptr [rdi], 2
0x18022aa40  mov     [rdi+8], r15
0x18022aa44  jmp     loc_18022AB75
0x18022aa49  mov     edx, ebx; dwMilliseconds
0x18022aa4b  call    cs:__imp_WaitForSingleObject
0x18022aa51  mov     r14d, eax
0x18022aa54  call    cs:__imp_GetLastError
0x18022aa5a  test    r14d, 0FFFFFF7Fh
0x18022aa61  jz      loc_18022AB21
0x18022aa67  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1??Create@GlobalMutex@SemanticIndex@asg@@SA?AV?$tuple@V?$unique_ptr@VGlobalMutex@SemanticIndex@asg@@U?$default_delete@VGlobalMutex@SemanticIndex@asg@@@std@@@std@@W4CreateErrorCode@GlobalMutex@SemanticIndex@asg@@@std@@V?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@7@I@Z@X$$V@std@@6B@; const std::_Func_impl_no_alloc<`asg::SemanticIndex::GlobalMutex::Create(std::basic_string<char16_t>,uint)'::`2'::_lambda_1_,void,>::`vftable'
0x18022aa6e  mov     [rbp+0B0h+var_A0], rcx
0x18022aa72  lea     rcx, [rbp+0B0h+hHandle]
0x18022aa76  mov     [rbp+0B0h+var_98], rcx
0x18022aa7a  lea     rcx, [rbp+0B0h+var_A0]
0x18022aa7e  mov     [rbp+0B0h+var_68], rcx
0x18022aa82  mov     [rbp+0B0h+var_60], 5Bh ; '['
0x18022aa89  mov     [rbp+0B0h+var_5C], 28h ; '('
0x18022aa90  lea     rcx, aCW1SSrcSharedI_4; "C:\\__w\\1\\s\\src\\Shared\\internal\\l"...
0x18022aa97  mov     [rbp+0B0h+var_58], rcx
0x18022aa9b  lea     rdx, aClassStdTupleC; "class std::tuple<class std::unique_ptr<"...
0x18022aaa2  mov     [rbp+0B0h+var_50], rdx
0x18022aaa6  mov     ebx, 1
0x18022aaab  cmp     r14d, 0FFFFFFFFh
0x18022aaaf  jz      short loc_18022AB10
0x18022aab1  mov     ebx, 3
0x18022aab6  mov     [rbp+0B0h+var_F0], 61h ; 'a'
0x18022aabd  mov     [rbp+0B0h+var_F0+4], 0Dh
0x18022aac4  mov     qword ptr [rbp+0B0h+var_F0+8], rcx
0x18022aac8  mov     qword ptr [rbp+0B0h+var_E0], rdx
0x18022aacc  mov     byte ptr [rbp+0B0h+var_E0+8], 1
0x18022aad0  movups  xmm0, xmmword ptr [rbp+0B0h+var_F0]
0x18022aad4  movaps  xmmword ptr [rsp+1B0h+var_150], xmm0
0x18022aad9  movups  xmm1, [rbp+0B0h+var_E0]
0x18022aadd  movaps  xmmword ptr [rsp+70h], xmm1
0x18022aae2  mov     dword ptr [rsp+1B0h+Reserved], eax; ArgList
0x18022aae6  lea     r9, aWaitforsingleo_0; "WaitForSingleObject failed in GlobalMut"...
0x18022aaed  mov     r8d, 4; int
0x18022aaf3  lea     rdx, [rsp+1B0h+var_150]; int
0x18022aaf8  lea     rcx, [rbp+0B0h+lpName]; int
0x18022aafc  call    ??$_asg_Log@U?$integral_constant@_N$00@std@@@details@asg@@YA?AULogStringView@1@V?$optional@Usource_location@std@@@std@@W4LogLevel@1@PEB_SZZ; asg::details::_asg_Log<std::integral_constant<bool,1>>(std::optional<std::source_location>,asg::LogLevel,char16_t const *,...)
0x18022ab01  cmp     [rbp+0B0h+var_108], 0
0x18022ab05  jz      short loc_18022AB10
0x18022ab07  lea     rcx, [rbp+0B0h+lpName]; this
0x18022ab0b  call    ??1RegionId@SemanticPipelines@asg@@QEAA@XZ; asg::SemanticPipelines::RegionId::~RegionId(void)
0x18022ab10  mov     [rdi], ebx
0x18022ab12  mov     [rdi+8], r15
0x18022ab16  lea     rcx, [rbp+0B0h+var_A0]; this
0x18022ab1a  call    ??1OnScopeExit@asg@@QEAA@XZ; asg::OnScopeExit::~OnScopeExit(void)
0x18022ab1f  jmp     short loc_18022AB75
0x18022ab21  mov     ecx, 8; Size
0x18022ab26  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18022ab2b  mov     rbx, rax
0x18022ab2e  test    rax, rax
0x18022ab31  jz      short loc_18022AB6B
0x18022ab33  xor     eax, eax
0x18022ab35  mov     [rbx], rax
0x18022ab38  mov     rcx, [rbp+0B0h+hHandle]
0x18022ab3c  mov     qword ptr [rsp+1B0h+var_170], rcx
0x18022ab41  call    _Thrd_id
0x18022ab46  mov     dword ptr [rsp+1B0h+var_170+8], eax
0x18022ab4a  mov     ecx, 10h; Size
0x18022ab4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18022ab54  test    rax, rax
0x18022ab57  jz      short loc_18022AB63
0x18022ab59  movups  xmm0, [rsp+1B0h+var_170]
0x18022ab5e  movups  xmmword ptr [rax], xmm0
0x18022ab61  jmp     short loc_18022AB66
0x18022ab63  mov     rax, r15
0x18022ab66  mov     [rbx], rax
0x18022ab69  jmp     short loc_18022AB6E
0x18022ab6b  mov     rbx, r15
0x18022ab6e  mov     [rdi], r15d
0x18022ab71  mov     [rdi+8], rbx
0x18022ab75  mov     rcx, rsi; this
0x18022ab78  call    ??1RegionId@SemanticPipelines@asg@@QEAA@XZ; asg::SemanticPipelines::RegionId::~RegionId(void)
0x18022ab7d  mov     rax, rdi
0x18022ab80  mov     rcx, [rbp+0B0h+var_40]
0x18022ab84  xor     rcx, rsp; StackCookie
0x18022ab87  call    __security_check_cookie
0x18022ab8c  mov     rbx, [rsp+1B0h+arg_18]
0x18022ab94  add     rsp, 180h
0x18022ab9b  pop     r15
0x18022ab9d  pop     r14
0x18022ab9f  pop     r13
0x18022aba1  pop     r12
0x18022aba3  pop     rdi
0x18022aba4  pop     rsi
0x18022aba5  pop     rbp
0x18022aba6  retn
0x18022aba7  mov     [rsp+1B0h+Reserved], r15; Reserved
0x18022abac  xor     r9d, r9d; LineNo
0x18022abaf  xor     r8d, r8d; FileName
0x18022abb2  xor     edx, edx; FunctionName
0x18022abb4  xor     ecx, ecx; Expression
0x18022abb6  call    _invoke_watson
0x18022abbc  mov     [rsp+1B0h+Reserved], r15; Reserved
0x18022abc1  xor     r9d, r9d; LineNo
0x18022abc4  xor     r8d, r8d; FileName
0x18022abc7  xor     edx, edx; FunctionName
0x18022abc9  xor     ecx, ecx; Expression
0x18022abcb  call    _invoke_watson
```
