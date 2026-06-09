# win_musl::consumption::ZipConsumptionContext::GetZipFileContext(win_musl::ZipFileCentral const &)

- ea: `0x1800248fc`
- end: `0x180024bc8`
- name: `?GetZipFileContext@ZipConsumptionContext@consumption@win_musl@@QEAA?AV?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@AEBVZipFileCentral@3@@Z`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022648`

## callees

- `0x1800016b0`
- `0x180004668`
- `0x180015114`
- `0x180018c2c`
- `0x1800248fc`
- `0x180024bd0`
- `0x180024d3c`
- `0x180024e18`
- `0x18002587c`
- `0x1800262d8`
- `0x1800517a0`
- `0x18009c21c`
- `0x1800cd38c`
- `0x1800d04d8`
- `0x180117716`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024965`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024965`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024a70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024a70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024952`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024952`

## string_xrefs

- `0x180024b82`: `mismatch between central directory and actual files.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall win_musl::consumption::ZipConsumptionContext::GetZipFileContext(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  bool v7; // dl
  win_dox *v8; // rcx
  __int64 *v9; // r15
  __int64 *v10; // rdi
  __int64 *v11; // rbp
  size_t v12; // r12
  const void *v13; // rdx
  size_t v14; // r8
  _QWORD *v15; // rcx
  int v16; // eax
  win_musl::consumption::ZipFileContext *v17; // rax
  int v18; // edx
  const char *v19; // r8
  unsigned int v20; // r9d
  void *v23; // rax
  __m128i v24; // xmm0
  __int64 v25; // rdi
  __m128i v26; // [rsp+48h] [rbp-110h] BYREF
  __int64 v27; // [rsp+58h] [rbp-100h]
  _QWORD *v28; // [rsp+60h] [rbp-F8h]
  __int64 v29; // [rsp+68h] [rbp-F0h]
  _BYTE pExceptionObject[160]; // [rsp+70h] [rbp-E8h] BYREF

  v27 = -2;
  v28 = a2;
  v6 = a1 + 40;
  v29 = a1 + 40;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v8 = (win_dox *)*(unsigned int *)(v6 + 44);
  *(_DWORD *)(v6 + 44) = (_DWORD)v8 + 1;
  if ( !(_DWORD)v8 )
    *(_DWORD *)(v6 + 40) = GetCurrentThreadId();
  LOBYTE(v8) = *(_BYTE *)(a1 + 96);
  win_dox::ThrowIfFailed(v8, v7);
  *a2 = 0;
  a2[1] = 0;
  v9 = *(__int64 **)(a1 + 24);
  v10 = (__int64 *)v9[1];
  v11 = v9;
  if ( *((_BYTE *)v10 + 81) )
  {
LABEL_18:
    v11 = v9;
    goto LABEL_19;
  }
  v12 = a3[4];
  do
  {
    if ( a3[5] < 0x10u )
      v13 = a3 + 2;
    else
      v13 = (const void *)a3[2];
    v14 = v12;
    if ( v10[6] < v12 )
      v14 = v10[6];
    v15 = v10 + 4;
    if ( (unsigned __int64)v10[7] >= 0x10 )
      v15 = (_QWORD *)*v15;
    v16 = memcmp_0(v15, v13, v14);
    if ( v16 )
    {
      if ( v16 < 0 )
        goto LABEL_13;
    }
    else if ( v10[6] < v12 )
    {
LABEL_13:
      v10 = (__int64 *)v10[2];
      continue;
    }
    v11 = v10;
    v10 = (__int64 *)*v10;
  }
  while ( !*((_BYTE *)v10 + 81) );
  v6 = a1 + 40;
  if ( v11 == v9 )
    goto LABEL_18;
  if ( (int)std::string::compare(a3 + 1, v11 + 3) < 0 )
  {
    v9 = *(__int64 **)(a1 + 24);
    goto LABEL_18;
  }
LABEL_19:
  if ( *(__int64 **)(a1 + 24) == v11 )
  {
    if ( !win_dox::ByteCollection::CanPosition((win_dox::ByteCollection *)(a1 + 104))
      || !win_dox::ByteCollection::HasSize((win_dox::ByteCollection *)(a1 + 104)) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x29Au,
        0x80511006,
        (struct win_musl::TStringEllipseBase *)L"mismatch between central directory and actual files.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v17 = (win_musl::consumption::ZipFileContext *)operator new(0x1F0u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v17 )
      SplException::RealThrowFromHR((SplException *)0x8007000ELL, v18, v19, v20);
    v25 = win_musl::consumption::ZipFileContext::ZipFileContext(v17);
    v26.m128i_i64[0] = v25;
    if ( v25 )
    {
      v23 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v23 )
      {
        win_scope::close_delete::close<win_musl::consumption::ZipFileContext>(&v26);
        win_scope::report_policy_throw::report_init_failure();
      }
      *((_QWORD *)v23 + 1) = 0;
      *(_QWORD *)v23 = &win_scope::counted_strong_weak<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
      *((_QWORD *)v23 + 2) = v25;
      if ( _InterlockedIncrement((volatile signed __int32 *)v23 + 2) == 1 )
        _InterlockedAdd((volatile signed __int32 *)v23 + 3, 1u);
    }
    else
    {
      v25 = 0;
      v23 = 0;
    }
    v26 = *(__m128i *)a2;
    v24 = v26;
    *a2 = v23;
    a2[1] = v25;
    if ( v24.m128i_i64[0] && _mm_srli_si128(v24, 8).m128i_u64[0] )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v26);
  }
  else
  {
    win_scope::scope<unsigned char *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>::operator=(
      a2,
      v11 + 8);
  }
  if ( v6 )
  {
    if ( (*(_DWORD *)(v6 + 44))-- == 1 )
      *(_DWORD *)(v6 + 40) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  }
  return a2;
}

```

## disassembly

```asm
0x1800248fc  mov     rax, rsp
0x1800248ff  push    rbp
0x180024900  push    rsi
0x180024901  push    rdi
0x180024902  push    r12
0x180024904  push    r13
0x180024906  push    r14
0x180024908  push    r15
0x18002490a  sub     rsp, 120h
0x180024911  mov     [rsp+158h+var_100], 0FFFFFFFFFFFFFFFEh
0x18002491a  mov     [rax+20h], rbx
0x18002491e  mov     rax, cs:__security_cookie
0x180024925  xor     rax, rsp
0x180024928  mov     [rsp+158h+var_48], rax
0x180024930  mov     r13, r8
0x180024933  mov     rsi, rdx
0x180024936  mov     r14, rcx
0x180024939  mov     [rsp+158h+var_F8], rdx
0x18002493e  xor     r12d, r12d
0x180024941  mov     [rsp+158h+var_118], r12d
0x180024946  lea     rbx, [rcx+28h]
0x18002494a  mov     [rsp+158h+var_F0], rbx
0x18002494f  mov     rcx, rbx; lpCriticalSection
0x180024952  call    cs:__imp_EnterCriticalSection
0x180024958  mov     ecx, [rbx+2Ch]
0x18002495b  lea     eax, [rcx+1]
0x18002495e  mov     [rbx+2Ch], eax
0x180024961  test    ecx, ecx
0x180024963  jnz     short loc_18002496E
0x180024965  call    cs:__imp_GetCurrentThreadId
0x18002496b  mov     [rbx+28h], eax
0x18002496e  mov     cl, [r14+60h]; this
0x180024972  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x180024977  mov     [rsi], r12
0x18002497a  mov     [rsi+8], r12
0x18002497e  mov     [rsp+158h+var_118], 1
0x180024986  mov     r15, [r14+18h]
0x18002498a  mov     rdi, [r15+8]
0x18002498e  mov     rbp, r15
0x180024991  cmp     [rdi+51h], r12b
0x180024995  jnz     short loc_1800249F7
0x180024997  mov     r12, [r13+20h]
0x18002499b  cmp     qword ptr [r13+28h], 10h
0x1800249a0  jb      loc_180024A47
0x1800249a6  mov     rdx, [r13+10h]; Buf2
0x1800249aa  mov     r8, r12
0x1800249ad  cmp     [rdi+30h], r12
0x1800249b1  cmovb   r8, [rdi+30h]; Size
0x1800249b6  lea     rcx, [rdi+20h]
0x1800249ba  cmp     qword ptr [rdi+38h], 10h
0x1800249bf  jb      short loc_1800249C4
0x1800249c1  mov     rcx, [rcx]; Buf1
0x1800249c4  call    memcmp_0
0x1800249c9  test    eax, eax
0x1800249cb  jz      short loc_1800249D5
0x1800249cd  jns     short loc_1800249DB
0x1800249cf  mov     rdi, [rdi+10h]
0x1800249d3  jmp     short loc_1800249E1
0x1800249d5  cmp     [rdi+30h], r12
0x1800249d9  jb      short loc_1800249CF
0x1800249db  mov     rbp, rdi
0x1800249de  mov     rdi, [rdi]
0x1800249e1  cmp     byte ptr [rdi+51h], 0
0x1800249e5  jz      short loc_18002499B
0x1800249e7  cmp     rbp, r15
0x1800249ea  lea     rbx, [r14+28h]
0x1800249ee  jnz     loc_180024AA4
0x1800249f4  xor     r12d, r12d
0x1800249f7  mov     rbp, r15
0x1800249fa  cmp     [r14+18h], rbp
0x1800249fe  jnz     short loc_180024A50
0x180024a00  lea     rcx, [r14+68h]; this
0x180024a04  call    ?CanPosition@ByteCollection@win_dox@@QEBA_NXZ; win_dox::ByteCollection::CanPosition(void)
0x180024a09  test    al, al
0x180024a0b  jz      loc_180024B82
0x180024a11  lea     rcx, [r14+68h]; this
0x180024a15  call    ?HasSize@ByteCollection@win_dox@@QEBA_NXZ; win_dox::ByteCollection::HasSize(void)
0x180024a1a  test    al, al
0x180024a1c  jz      loc_180024B82
0x180024a22  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024a29  mov     ecx, 1F0h; unsigned __int64
0x180024a2e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180024a33  test    rax, rax
0x180024a36  jnz     loc_180024B4C
0x180024a3c  mov     ecx, 8007000Eh; this
0x180024a41  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x180024a47  lea     rdx, [r13+10h]
0x180024a4b  jmp     loc_1800249AA
0x180024a50  lea     rdx, [rbp+40h]
0x180024a54  mov     rcx, rsi
0x180024a57  call    ??4?$scope@PEAEU?$const_policies@U?$shared_close_policies@Uclose_delete_array@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAAAEAV01@AEBV01@@Z; win_scope::scope<uchar *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>::operator=(win_scope::scope<uchar *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>> const &)
0x180024a5c  jmp     short $+2
0x180024a5e  test    rbx, rbx
0x180024a61  jz      short loc_180024A76
0x180024a63  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x180024a67  jnz     short loc_180024A6D
0x180024a69  mov     [rbx+28h], r12d
0x180024a6d  mov     rcx, rbx; lpCriticalSection
0x180024a70  call    cs:__imp_LeaveCriticalSection
0x180024a76  mov     rax, rsi
0x180024a79  mov     rcx, [rsp+158h+var_48]
0x180024a81  xor     rcx, rsp; StackCookie
0x180024a84  call    __security_check_cookie
0x180024a89  mov     rbx, [rsp+158h+arg_18]
0x180024a91  add     rsp, 120h
0x180024a98  pop     r15
0x180024a9a  pop     r14
0x180024a9c  pop     r13
0x180024a9e  pop     r12
0x180024aa0  pop     rdi
0x180024aa1  pop     rsi
0x180024aa2  pop     rbp
0x180024aa3  retn
0x180024aa4  lea     rdx, [rbp+18h]
0x180024aa8  lea     rcx, [r13+8]
0x180024aac  call    ?compare@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEBAHAEBV12@@Z; std::string::compare(std::string const &)
0x180024ab1  xor     r12d, r12d
0x180024ab4  test    eax, eax
0x180024ab6  jns     loc_1800249FA
0x180024abc  mov     r15, [r14+18h]
0x180024ac0  jmp     loc_1800249F7
0x180024ac5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024acc  mov     ecx, 18h; unsigned __int64
0x180024ad1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180024ad6  test    rax, rax
0x180024ad9  jz      loc_180024B72
0x180024adf  mov     qword ptr [rax+8], 0
0x180024ae7  lea     rcx, ??_7?$counted_strong_weak@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x180024aee  mov     [rax], rcx
0x180024af1  mov     [rax+10h], rdi
0x180024af5  mov     edx, 1
0x180024afa  mov     ecx, edx
0x180024afc  lock xadd [rax+8], ecx
0x180024b01  add     ecx, edx
0x180024b03  cmp     ecx, edx
0x180024b05  jz      short loc_180024B46
0x180024b07  movups  xmm0, xmmword ptr [rsi]
0x180024b0a  movups  [rsp+158h+var_110], xmm0
0x180024b0f  mov     [rsi], rax
0x180024b12  mov     [rsi+8], rdi
0x180024b16  movq    rax, xmm0
0x180024b1b  test    rax, rax
0x180024b1e  jz      loc_180024A5E
0x180024b24  psrldq  xmm0, 8
0x180024b29  movq    rax, xmm0
0x180024b2e  test    rax, rax
0x180024b31  jz      loc_180024A5E
0x180024b37  lea     rcx, [rsp+158h+var_110]
0x180024b3c  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180024b41  jmp     loc_180024A5E
0x180024b46  lock add [rax+0Ch], edx
0x180024b4a  jmp     short loc_180024B07
0x180024b4c  mov     qword ptr [rsp+158h+var_110], rax
0x180024b51  mov     rcx, rax; this
0x180024b54  call    ??0ZipFileContext@consumption@win_musl@@QEAA@XZ; win_musl::consumption::ZipFileContext::ZipFileContext(void)
0x180024b59  mov     rdi, rax
0x180024b5c  mov     qword ptr [rsp+158h+var_110], rax
0x180024b61  test    rax, rax
0x180024b64  jnz     loc_180024AC5
0x180024b6a  mov     rdi, r12
0x180024b6d  mov     rax, r12
0x180024b70  jmp     short loc_180024B07
0x180024b72  lea     rcx, [rsp+158h+var_110]
0x180024b77  call    ??$close@UZipFileContext@consumption@win_musl@@@close_delete@win_scope@@SAXPEAPEAUZipFileContext@consumption@win_musl@@@Z; win_scope::close_delete::close<win_musl::consumption::ZipFileContext>(win_musl::consumption::ZipFileContext * *)
0x180024b7c  call    ?report_init_failure@report_policy_throw@win_scope@@SAXXZ; win_scope::report_policy_throw::report_init_failure(void)
0x180024b82  lea     rax, aMismatchBetwee; "mismatch between central directory and "...
0x180024b89  mov     [rsp+158h+var_128], rax; struct win_musl::TStringEllipseBase *
0x180024b8e  mov     [rsp+158h+var_130], 80511006h; unsigned int
0x180024b96  mov     [rsp+158h+var_138], 29Ah; unsigned int
0x180024b9e  lea     r9, word_18013A0B6
0x180024ba5  lea     r8, aNoFilename; "(no filename)"
0x180024bac  lea     rcx, [rsp+158h+pExceptionObject]; this
0x180024bb1  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180024bb6  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180024bbd  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180024bc2  call    _CxxThrowException_0
```
