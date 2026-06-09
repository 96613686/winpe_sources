# wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Nlm::NlmSignature>(Windows::Foundation::Collections::IVectorView<Windows::Internal::Storage::Cloud::CloudStoreItemName *> *)

- ea: `0x180009240`
- end: `0x1800097ee`
- name: `??$make_cloud_store_reference_vector@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@CA?AV?$vector@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@PEAU?$IVectorView@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `1454`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001aed8`

## callees

- `0x180005ac0`
- `0x180006afc`
- `0x180009240`
- `0x1800097f4`
- `0x180025308`
- `0x1800277f0`
- `0x18002a030`
- `0x18002e2d0`
- `0x18002f1ac`
- `0x18003ab80`
- `0x18003b6f8`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009701`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009721`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009701`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000970e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000970e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800093c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000956e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800093c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000956e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800095f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000962e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000969a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800096db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800096f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009719`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800095f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000962e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000969a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800096db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800096f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009719`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800093e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800093e5`

## pseudocode

```c
_QWORD *__fastcall wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Nlm::NlmSignature>(
        _QWORD *a1,
        __int64 *a2)
{
  int v4; // eax
  unsigned int v5; // edx
  unsigned int v6; // r15d
  __m128i si128; // xmm6
  __int64 v8; // rax
  int v9; // eax
  HSTRING v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  HSTRING v13; // rsi
  HSTRING v14; // r14
  const WCHAR *v15; // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 v17; // rax
  int v18; // eax
  HSTRING v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  HSTRING v22; // rsi
  HSTRING v23; // r14
  __int64 v24; // rax
  int v25; // eax
  HSTRING v26; // rsi
  HSTRING v27; // r14
  __int128 v28; // xmm0
  PCWSTR v29; // rax
  __int64 v30; // r8
  PCWSTR v31; // rax
  __int64 v32; // r8
  __int64 v33; // rcx
  __int64 v34; // rcx
  DWORD LastError; // ebx
  DWORD v37; // ebx
  DWORD v38; // ebx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  HSTRING v40; // [rsp+38h] [rbp-C8h] BYREF
  char v41; // [rsp+40h] [rbp-C0h]
  unsigned int v42; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v43; // [rsp+50h] [rbp-B0h]
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  int v45; // [rsp+60h] [rbp-A0h]
  HSTRING v46; // [rsp+68h] [rbp-98h]
  HSTRING v47; // [rsp+70h] [rbp-90h]
  HSTRING v48; // [rsp+78h] [rbp-88h]
  _QWORD *v49; // [rsp+80h] [rbp-80h]
  __int128 v50; // [rsp+90h] [rbp-70h] BYREF
  __m128i v51; // [rsp+A0h] [rbp-60h]
  __int128 v52; // [rsp+B0h] [rbp-50h] BYREF
  __m128i v53; // [rsp+C0h] [rbp-40h]
  LPCWCH lpString2[3]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v55; // [rsp+E8h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v49 = a1;
  v45 = 0;
  wil::cloud_store::get_type_name_wide_string<Windows::Data::Nlm::NlmSignature>((__int64)lpString2);
  v42 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*a2 + 56))(a2, &v42);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55E,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v4,
      bIgnoreCase);
  std::vector<bond::blob>::vector<bond::blob>(a1);
  v45 = 1;
  v5 = v42;
  string = (HSTRING)v42;
  if ( v42 > (unsigned __int64)((__int64)(a1[2] - *a1) >> 6) )
  {
    std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>::_Reallocate<0>(a1, &string);
    v5 = v42;
  }
  v6 = 0;
  if ( v5 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      v43 = 0;
      v8 = *a2;
      v40 = 0;
      v41 = 1;
      v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING *))(v8 + 48))(a2, v6, &v40);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x565,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
          (const char *)(unsigned int)v9,
          bIgnoreCase);
      if ( v41 )
      {
        v10 = v43;
        v43 = v40;
        if ( v10 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v10 + 16LL))(v10);
      }
      string = 0;
      v11 = *(_QWORD *)v43;
      v40 = 0;
      v41 = 1;
      v12 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(v11 + 64))(v43, &v40);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x568,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
          (const char *)(unsigned int)v12,
          bIgnoreCase);
      if ( v41 )
      {
        v13 = v40;
        v14 = string;
        if ( string )
        {
          LastError = GetLastError();
          WindowsDeleteString(v14);
          SetLastError(LastError);
        }
        string = v13;
      }
      v15 = (const WCHAR *)lpString2;
      if ( v55 > 7 )
        v15 = lpString2[0];
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, v15, -1, 1) == 2 )
      {
        v48 = 0;
        v17 = *(_QWORD *)v43;
        v40 = 0;
        v41 = 1;
        v18 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(v17 + 48))(v43, &v40);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x56C,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
            (const char *)(unsigned int)v18,
            bIgnoreCase);
        if ( v41 )
        {
          v19 = v48;
          v48 = v40;
          if ( v19 )
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v19 + 16LL))(v19);
        }
        v47 = 0;
        v20 = *(_QWORD *)v48;
        v40 = 0;
        v41 = 1;
        v21 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(v20 + 48))(v48, &v40);
        if ( v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x56F,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
            (const char *)(unsigned int)v21,
            bIgnoreCase);
        if ( v41 )
        {
          v22 = v40;
          v23 = v47;
          if ( v47 )
          {
            v37 = GetLastError();
            WindowsDeleteString(v23);
            SetLastError(v37);
          }
          v47 = v22;
        }
        v46 = 0;
        v24 = *(_QWORD *)v43;
        v40 = 0;
        v41 = 1;
        v25 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(v24 + 56))(v43, &v40);
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x572,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
            (const char *)(unsigned int)v25,
            bIgnoreCase);
        if ( v41 )
        {
          v26 = v40;
          v27 = v46;
          if ( v46 )
          {
            v38 = GetLastError();
            WindowsDeleteString(v27);
            SetLastError(v38);
          }
          v46 = v26;
        }
        v28 = 0;
        v50 = 0;
        v51 = 0;
        *(double *)&v28 = std::wstring::_Construct_empty(&v50);
        v52 = v28;
        v53 = 0;
        std::wstring::_Construct_empty(&v52);
        v29 = WindowsGetStringRawBuffer(v46, 0);
        v30 = -1;
        do
          ++v30;
        while ( v29[v30] );
        std::wstring::_Assign<unsigned short>(&v50);
        v31 = WindowsGetStringRawBuffer(v47, 0);
        v32 = -1;
        do
          ++v32;
        while ( v31[v32] );
        std::wstring::_Assign<unsigned short>(&v52);
        v33 = a1[1];
        if ( v33 == a1[2] )
        {
          std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>::_Emplace_reallocate<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>(
            a1,
            a1[1],
            (__int64)&v50);
        }
        else
        {
          std::wstring::wstring(v33, &v50);
          std::wstring::wstring(v34 + 32, &v52);
          a1[1] += 64LL;
        }
        if ( v53.m128i_i64[1] > 7uLL )
          std::_Deallocate<16>((void *)v52, 2 * v53.m128i_i64[1] + 2);
        v53 = si128;
        LOWORD(v52) = 0;
        if ( v51.m128i_i64[1] > 7uLL )
          std::_Deallocate<16>((void *)v50, 2 * v51.m128i_i64[1] + 2);
        v51 = si128;
        LOWORD(v50) = 0;
        if ( v46 )
          WindowsDeleteString(v46);
        if ( v47 )
          WindowsDeleteString(v47);
        if ( v48 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v48 + 16LL))(v48);
      }
      if ( string )
        WindowsDeleteString(string);
      if ( v43 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v43 + 16LL))(v43);
      ++v6;
    }
    while ( v6 < v42 );
  }
  if ( v55 > 7 )
    std::_Deallocate<16>((void *)lpString2[0], 2 * v55 + 2);
  return a1;
}

```

## disassembly

```asm
0x180009240  mov     [rsp-8+arg_10], rbx
0x180009245  push    rbp
0x180009246  push    rsi
0x180009247  push    rdi
0x180009248  push    r12
0x18000924a  push    r13
0x18000924c  push    r14
0x18000924e  push    r15
0x180009250  lea     rbp, [rsp-10h]
0x180009255  sub     rsp, 110h
0x18000925c  movaps  [rsp+140h+var_40], xmm6
0x180009264  mov     rax, cs:__security_cookie
0x18000926b  xor     rax, rsp
0x18000926e  mov     [rbp+40h+var_50], rax
0x180009272  mov     r12, rdx
0x180009275  mov     r13, rcx
0x180009278  mov     [rbp+40h+var_C0], rcx
0x18000927c  xor     ebx, ebx
0x18000927e  mov     [rsp+140h+var_E0], ebx
0x180009282  lea     rcx, [rbp+40h+lpString2]
0x180009286  call    ??$get_type_name_wide_string@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::cloud_store::get_type_name_wide_string<Windows::Data::Nlm::NlmSignature>(void)
0x18000928b  nop
0x18000928c  mov     [rsp+140h+var_F8], ebx
0x180009290  mov     rax, [r12]
0x180009294  lea     rdx, [rsp+140h+var_F8]
0x180009299  mov     rcx, r12
0x18000929c  mov     rax, [rax+38h]
0x1800092a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092a5  mov     rcx, [rbp+48h]; this
0x1800092a9  test    eax, eax
0x1800092ab  js      loc_1800096A5
0x1800092b1  mov     rcx, r13
0x1800092b4  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x1800092b9  mov     [rsp+140h+var_E0], 1
0x1800092c1  mov     edx, [rsp+140h+var_F8]
0x1800092c5  mov     [rsp+140h+string], rdx
0x1800092ca  mov     rax, [r13+10h]
0x1800092ce  sub     rax, [r13+0]
0x1800092d2  sar     rax, 6
0x1800092d6  cmp     rdx, rax
0x1800092d9  ja      loc_1800096BA
0x1800092df  mov     r15d, ebx
0x1800092e2  test    edx, edx
0x1800092e4  jz      loc_18000965A
0x1800092ea  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800092f2  mov     [rsp+140h+var_F0], rbx
0x1800092f7  mov     rax, [r12]
0x1800092fb  lea     rcx, [rsp+140h+var_F0]
0x180009300  mov     [rsp+140h+var_110], rcx
0x180009305  mov     [rsp+140h+var_108], rbx
0x18000930a  mov     [rsp+140h+var_100], 1
0x18000930f  lea     r8, [rsp+140h+var_108]
0x180009314  mov     edx, r15d
0x180009317  mov     rcx, r12
0x18000931a  mov     rax, [rax+30h]
0x18000931e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009323  mov     rcx, [rbp+48h]; this
0x180009327  test    eax, eax
0x180009329  js      loc_1800097C2
0x18000932f  cmp     [rsp+140h+var_100], 0
0x180009334  jz      short loc_180009358
0x180009336  mov     rdx, [rsp+140h+var_108]
0x18000933b  mov     rax, [rsp+140h+var_110]
0x180009340  mov     rcx, [rax]
0x180009343  mov     [rax], rdx
0x180009346  test    rcx, rcx
0x180009349  jz      short loc_180009358
0x18000934b  mov     rax, [rcx]
0x18000934e  mov     rax, [rax+10h]
0x180009352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009357  nop
0x180009358  mov     [rsp+140h+string], rbx
0x18000935d  mov     rcx, [rsp+140h+var_F0]
0x180009362  mov     rax, [rcx]
0x180009365  lea     rdx, [rsp+140h+string]
0x18000936a  mov     [rsp+140h+var_110], rdx
0x18000936f  mov     [rsp+140h+var_108], rbx
0x180009374  mov     [rsp+140h+var_100], 1
0x180009379  lea     rdx, [rsp+140h+var_108]
0x18000937e  mov     rax, [rax+40h]
0x180009382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009387  mov     rcx, [rbp+48h]; this
0x18000938b  test    eax, eax
0x18000938d  js      loc_1800097AD
0x180009393  cmp     [rsp+140h+var_100], 0
0x180009398  jz      short loc_1800093B3
0x18000939a  mov     rsi, [rsp+140h+var_108]
0x18000939f  mov     rdi, [rsp+140h+var_110]
0x1800093a4  mov     r14, [rdi]
0x1800093a7  test    r14, r14
0x1800093aa  jnz     loc_1800096D0
0x1800093b0  mov     [rdi], rsi
0x1800093b3  lea     rbx, [rbp+40h+lpString2]
0x1800093b7  cmp     [rbp+40h+var_58], 7
0x1800093bc  cmova   rbx, [rbp+40h+lpString2]
0x1800093c1  xor     edx, edx; length
0x1800093c3  mov     rcx, [rsp+140h+string]; string
0x1800093c8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800093ce  mov     [rsp+140h+bIgnoreCase], 1; int
0x1800093d6  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800093dc  mov     r8, rbx; lpString2
0x1800093df  mov     edx, r9d; cchCount1
0x1800093e2  mov     rcx, rax; lpString1
0x1800093e5  call    cs:__imp_CompareStringOrdinal
0x1800093eb  xor     ebx, ebx
0x1800093ed  cmp     eax, 2
0x1800093f0  jnz     loc_180009624
0x1800093f6  mov     [rsp+140h+var_C8], rbx
0x1800093fb  mov     rcx, [rsp+140h+var_F0]
0x180009400  mov     rax, [rcx]
0x180009403  lea     rdx, [rsp+140h+var_C8]
0x180009408  mov     [rsp+140h+var_110], rdx
0x18000940d  mov     [rsp+140h+var_108], rbx
0x180009412  mov     [rsp+140h+var_100], 1
0x180009417  lea     rdx, [rsp+140h+var_108]
0x18000941c  mov     rax, [rax+30h]
0x180009420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009425  mov     rcx, [rbp+48h]; this
0x180009429  test    eax, eax
0x18000942b  js      loc_180009798
0x180009431  cmp     [rsp+140h+var_100], bl
0x180009435  jz      short loc_180009459
0x180009437  mov     rdx, [rsp+140h+var_108]
0x18000943c  mov     rax, [rsp+140h+var_110]
0x180009441  mov     rcx, [rax]
0x180009444  mov     [rax], rdx
0x180009447  test    rcx, rcx
0x18000944a  jz      short loc_180009459
0x18000944c  mov     rax, [rcx]
0x18000944f  mov     rax, [rax+10h]
0x180009453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009458  nop
0x180009459  mov     [rsp+140h+var_D0], rbx
0x18000945e  mov     rcx, [rsp+140h+var_C8]
0x180009463  mov     rax, [rcx]
0x180009466  lea     rdx, [rsp+140h+var_D0]
0x18000946b  mov     [rsp+140h+var_110], rdx
0x180009470  mov     [rsp+140h+var_108], rbx
0x180009475  mov     [rsp+140h+var_100], 1
0x18000947a  lea     rdx, [rsp+140h+var_108]
0x18000947f  mov     rax, [rax+30h]
0x180009483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009488  mov     rcx, [rbp+48h]; this
0x18000948c  test    eax, eax
0x18000948e  js      loc_180009783
0x180009494  cmp     [rsp+140h+var_100], 0
0x180009499  jz      short loc_1800094B4
0x18000949b  mov     rsi, [rsp+140h+var_108]
0x1800094a0  mov     rdi, [rsp+140h+var_110]
0x1800094a5  mov     r14, [rdi]
0x1800094a8  test    r14, r14
0x1800094ab  jnz     loc_1800096EE
0x1800094b1  mov     [rdi], rsi
0x1800094b4  mov     [rsp+140h+var_D8], rbx
0x1800094b9  mov     rcx, [rsp+140h+var_F0]
0x1800094be  mov     rax, [rcx]
0x1800094c1  lea     rdx, [rsp+140h+var_D8]
0x1800094c6  mov     [rsp+140h+var_110], rdx
0x1800094cb  mov     [rsp+140h+var_108], rbx
0x1800094d0  mov     [rsp+140h+var_100], 1
0x1800094d5  lea     rdx, [rsp+140h+var_108]
0x1800094da  mov     rax, [rax+38h]
0x1800094de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094e3  mov     rcx, [rbp+48h]; this
0x1800094e7  test    eax, eax
0x1800094e9  js      loc_18000976E
0x1800094ef  cmp     [rsp+140h+var_100], 0
0x1800094f4  jz      short loc_18000950F
0x1800094f6  mov     rsi, [rsp+140h+var_108]
0x1800094fb  mov     rdi, [rsp+140h+var_110]
0x180009500  mov     r14, [rdi]
0x180009503  test    r14, r14
0x180009506  jnz     loc_18000970E
0x18000950c  mov     [rdi], rsi
0x18000950f  xorps   xmm0, xmm0
0x180009512  movups  [rbp+40h+var_B0], xmm0
0x180009516  xorps   xmm1, xmm1
0x180009519  movdqa  [rbp+40h+var_A0], xmm1
0x18000951e  lea     rcx, [rbp+40h+var_B0]
0x180009522  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180009527  movups  [rbp+40h+var_90], xmm0
0x18000952b  movdqa  [rbp+40h+var_80], xmm1
0x180009530  lea     rcx, [rbp+40h+var_90]
0x180009534  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180009539  nop
0x18000953a  xor     edx, edx; length
0x18000953c  mov     rcx, [rsp+140h+var_D8]; string
0x180009541  call    cs:__imp_WindowsGetStringRawBuffer
0x180009547  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000954e  xchg    ax, ax
0x180009550  inc     r8
0x180009553  cmp     word ptr [rax+r8*2], 0
0x180009559  jnz     short loc_180009550
0x18000955b  mov     rdx, rax
0x18000955e  lea     rcx, [rbp+40h+var_B0]
0x180009562  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180009567  xor     edx, edx; length
0x180009569  mov     rcx, [rsp+140h+var_D0]; string
0x18000956e  call    cs:__imp_WindowsGetStringRawBuffer
0x180009574  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000957b  nop     dword ptr [rax+rax+00h]
0x180009580  inc     r8
0x180009583  cmp     word ptr [rax+r8*2], 0
0x180009589  jnz     short loc_180009580
0x18000958b  mov     rdx, rax
0x18000958e  lea     rcx, [rbp+40h+var_90]
0x180009592  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180009597  mov     rcx, [r13+8]
0x18000959b  cmp     rcx, [r13+10h]
0x18000959f  jz      loc_18000972E
0x1800095a5  lea     rdx, [rbp+40h+var_B0]
0x1800095a9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800095ae  add     rcx, 20h ; ' '
0x1800095b2  lea     rdx, [rbp+40h+var_90]
0x1800095b6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800095bb  add     qword ptr [r13+8], 40h ; '@'
0x1800095c0  mov     rdx, qword ptr [rbp+40h+var_80+8]
0x1800095c4  cmp     rdx, 7
0x1800095c8  ja      loc_180009742
0x1800095ce  movdqa  [rbp+40h+var_80], xmm6
0x1800095d3  mov     word ptr [rbp+40h+var_90], bx
0x1800095d7  mov     rdx, qword ptr [rbp+40h+var_A0+8]
0x1800095db  cmp     rdx, 7
0x1800095df  ja      loc_180009758
0x1800095e5  movdqa  [rbp+40h+var_A0], xmm6
0x1800095ea  mov     word ptr [rbp+40h+var_B0], bx
0x1800095ee  mov     rcx, [rsp+140h+var_D8]; string
0x1800095f3  test    rcx, rcx
0x1800095f6  jz      short loc_1800095FF
0x1800095f8  call    cs:__imp_WindowsDeleteString
0x1800095fe  nop
0x1800095ff  mov     rcx, [rsp+140h+var_D0]; string
0x180009604  test    rcx, rcx
0x180009607  jnz     loc_18000969A
0x18000960d  mov     rcx, [rsp+140h+var_C8]
0x180009612  test    rcx, rcx
0x180009615  jz      short loc_180009624
0x180009617  mov     rax, [rcx]
0x18000961a  mov     rax, [rax+10h]
0x18000961e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009623  nop
0x180009624  mov     rcx, [rsp+140h+string]; string
0x180009629  test    rcx, rcx
0x18000962c  jz      short loc_180009635
0x18000962e  call    cs:__imp_WindowsDeleteString
0x180009634  nop
0x180009635  mov     rcx, [rsp+140h+var_F0]
0x18000963a  test    rcx, rcx
0x18000963d  jz      short loc_18000964C
0x18000963f  mov     rax, [rcx]
0x180009642  mov     rax, [rax+10h]
0x180009646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000964b  nop
0x18000964c  inc     r15d
0x18000964f  cmp     r15d, [rsp+140h+var_F8]
0x180009654  jb      loc_1800092F2
0x18000965a  mov     rdx, [rbp+40h+var_58]
0x18000965e  cmp     rdx, 7
0x180009662  ja      loc_1800097D7
0x180009668  mov     rax, r13
0x18000966b  mov     rcx, [rbp+40h+var_50]
0x18000966f  xor     rcx, rsp; StackCookie
0x180009672  call    __security_check_cookie
0x180009677  mov     rbx, [rsp+140h+arg_10]
0x18000967f  movaps  xmm6, [rsp+140h+var_40]
0x180009687  add     rsp, 110h
0x18000968e  pop     r15
0x180009690  pop     r14
0x180009692  pop     r13
0x180009694  pop     r12
0x180009696  pop     rdi
0x180009697  pop     rsi
0x180009698  pop     rbp
0x180009699  retn
0x18000969a  call    cs:__imp_WindowsDeleteString
0x1800096a0  jmp     loc_18000960D
0x1800096a5  mov     r9d, eax; char *
0x1800096a8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800096af  mov     edx, 55Eh; void *
0x1800096b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800096ba  lea     rdx, [rsp+140h+string]
0x1800096bf  mov     rcx, r13
0x1800096c2  call    ??$_Reallocate@$0A@@?$vector@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAXAEA_K@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>::_Reallocate<0>(unsigned __int64 &)
0x1800096c7  mov     edx, [rsp+140h+var_F8]
0x1800096cb  jmp     loc_1800092DF
0x1800096d0  call    cs:__imp_GetLastError
0x1800096d6  mov     ebx, eax
0x1800096d8  mov     rcx, r14; string
0x1800096db  call    cs:__imp_WindowsDeleteString
0x1800096e1  mov     ecx, ebx; dwErrCode
0x1800096e3  call    cs:__imp_SetLastError
0x1800096e9  jmp     loc_1800093B0
0x1800096ee  call    cs:__imp_GetLastError
0x1800096f4  mov     ebx, eax
0x1800096f6  mov     rcx, r14; string
0x1800096f9  call    cs:__imp_WindowsDeleteString
0x1800096ff  mov     ecx, ebx; dwErrCode
0x180009701  call    cs:__imp_SetLastError
0x180009707  xor     ebx, ebx
0x180009709  jmp     loc_1800094B1
  ... truncated ...
```
