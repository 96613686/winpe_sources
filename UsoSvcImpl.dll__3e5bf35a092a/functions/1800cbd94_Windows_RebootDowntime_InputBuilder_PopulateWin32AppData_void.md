# Windows::RebootDowntime::InputBuilder::PopulateWin32AppData(void)

- ea: `0x1800cbd94`
- end: `0x1800cc514`
- name: `?PopulateWin32AppData@InputBuilder@RebootDowntime@Windows@@AEAAXXZ`
- size: `1920`
- prototype: `void __fastcall(Windows::RebootDowntime::InputBuilder *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800cae90`

## callees

- `0x18000f3a8`
- `0x180010890`
- `0x1800108b4`
- `0x1800109f4`
- `0x180011320`
- `0x180011484`
- `0x18001151c`
- `0x180011680`
- `0x18002dfe4`
- `0x1800420e0`
- `0x180079c6c`
- `0x18008fa18`
- `0x1800cbd94`
- `0x1800cc5bc`
- `0x1800d0ad0`
- `0x1800d0c90`
- `0x1800dd930`
- `0x1800e4630`
- `0x1800e46b0`

## string_xrefs

- `0x1800cc4cb`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800cc4e4`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800cc035`: `DidMostCommonAppChangeVersion`
- `0x1800cc212`: `DidMostCommonAppChangeVersion`
- `0x1800cc273`: `DidMostCommonAppChangeVersion`
- `0x1800cbef0`: `DidNumberOfInstalledWin32AppChange`
- `0x1800cbf3f`: `DidNumberOfInstalledWin32AppChange`
- `0x1800cbe0e`: `NumberOfInstalledWin32`
- `0x1800cc40b`: `NumberOfCommonApps`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall Windows::RebootDowntime::InputBuilder::PopulateWin32AppData(
        Windows::RebootDowntime::InputBuilder *this)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rax
  void (__fastcall *v5)(__int64, _QWORD *, __int128 *); // rbx
  __int16 *traits_2_unsigned_short; // rax
  const char *v7; // r9
  __int64 v8; // r11
  __int64 v9; // rax
  BOOL v10; // ebx
  __int64 v11; // rax
  __int128 *v12; // rcx
  void (__fastcall *v13)(__int64, __int128 *, _QWORD *); // rbx
  __int16 *v14; // rax
  const char *v15; // r9
  __int64 v16; // r11
  __int64 v17; // rax
  __int64 v18; // rsi
  char v19; // r12
  __int64 v20; // rax
  _QWORD *v21; // rbx
  _QWORD *v22; // rdx
  __int64 v23; // r9
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rdi
  __int64 v28; // r14
  void (__fastcall *v29)(__int64, _BYTE *, __int128 *); // r15
  __int64 v30; // rcx
  _QWORD *v31; // rdx
  char v32; // al
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // r14
  void (__fastcall *v36)(__int64, __int128 *, _QWORD *); // r15
  __int64 v37; // rcx
  __int128 *v38; // rdx
  __int64 v39; // rax
  int v40; // [rsp+28h] [rbp-E0h]
  __int128 v41; // [rsp+48h] [rbp-C0h]
  __int128 v42; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v43; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v44; // [rsp+78h] [rbp-90h]
  unsigned __int64 v45; // [rsp+80h] [rbp-88h]
  __int128 v46; // [rsp+88h] [rbp-80h] BYREF
  __int64 v47; // [rsp+98h] [rbp-70h]
  __int64 v48; // [rsp+A0h] [rbp-68h]
  __int128 v49; // [rsp+A8h] [rbp-60h]
  __int128 v50; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-40h]
  __int64 v52; // [rsp+D0h] [rbp-38h]
  __int128 v53; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v54; // [rsp+E8h] [rbp-20h]
  __int64 v55; // [rsp+F0h] [rbp-18h]
  __int128 v56; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v57; // [rsp+108h] [rbp+0h]
  __int64 v58; // [rsp+110h] [rbp+8h]
  _QWORD v59[4]; // [rsp+118h] [rbp+10h] BYREF
  __int128 v60; // [rsp+138h] [rbp+30h] BYREF
  __int64 v61; // [rsp+148h] [rbp+40h]
  __int64 v62; // [rsp+150h] [rbp+48h]
  __int128 v63; // [rsp+158h] [rbp+50h] BYREF
  __int64 v64; // [rsp+168h] [rbp+60h]
  __int64 v65; // [rsp+170h] [rbp+68h]
  _BYTE v66[16]; // [rsp+178h] [rbp+70h] BYREF
  _QWORD v67[4]; // [rsp+188h] [rbp+80h] BYREF
  char v68; // [rsp+1A8h] [rbp+A0h]
  _QWORD v69[8]; // [rsp+1B8h] [rbp+B0h] BYREF
  _BYTE v70[32]; // [rsp+1F8h] [rbp+F0h] BYREF
  char v71; // [rsp+218h] [rbp+110h]
  char v72; // [rsp+220h] [rbp+118h]
  _QWORD v73[4]; // [rsp+228h] [rbp+120h] BYREF
  char v74; // [rsp+248h] [rbp+140h]
  char v75; // [rsp+250h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+290h] [rbp+188h]

  memset(v69, 0, sizeof(v69));
  Windows::RebootDowntime::InputBuilder::QueryWin32Apps(v2, v69);
  v3 = v69[2];
  v46 = 0;
  v47 = 0;
  v48 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v46);
  v4 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[]((char *)this + 24, &v46);
  if ( *(_BYTE *)(v4 + 8) != 1 )
    *(_BYTE *)(v4 + 8) = 1;
  *(_QWORD *)v4 = v3;
  std::wstring::~wstring(&v46);
  v5 = *(void (__fastcall **)(__int64, _QWORD *, __int128 *))(**((_QWORD **)this + 25) + 64LL);
  traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                         L"UXDowntimeNumWin32Apps",
                                         &word_180129FA6,
                                         0);
  if ( traits_2_unsigned_short == &word_180129FA6
    || (v9 = ((char *)traits_2_unsigned_short - (char *)L"UXDowntimeNumWin32Apps") >> 1, v9 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v7);
  }
  *(_QWORD *)&v41 = L"UXDowntimeNumWin32Apps";
  *((_QWORD *)&v41 + 1) = v9;
  v42 = v41;
  v5(v8, v73, &v42);
  if ( v75 )
  {
    if ( v74 != 3 )
      std::_Throw_bad_variant_access();
    v10 = v73[0] != v69[2];
    v50 = 0;
    v51 = 0;
    v52 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v50);
    v11 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](
            (char *)this + 24,
            &v50);
    if ( *(_BYTE *)(v11 + 8) )
      *(_BYTE *)(v11 + 8) = 0;
    v12 = &v50;
  }
  else
  {
    v10 = v69[2] != 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v53);
    v11 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](
            (char *)this + 24,
            &v53);
    if ( *(_BYTE *)(v11 + 8) )
      *(_BYTE *)(v11 + 8) = 0;
    v12 = &v53;
  }
  *(_DWORD *)v11 = v10;
  std::wstring::~wstring(v12);
  v13 = *(void (__fastcall **)(__int64, __int128 *, _QWORD *))(**((_QWORD **)this + 25) + 56LL);
  v67[0] = v69[2];
  v68 = 3;
  v14 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"UXDowntimeNumWin32Apps",
                     &word_180129FA6,
                     0);
  if ( v14 == &word_180129FA6 || (v17 = ((char *)v14 - (char *)L"UXDowntimeNumWin32Apps") >> 1, v17 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v15);
  *(_QWORD *)&v41 = L"UXDowntimeNumWin32Apps";
  *((_QWORD *)&v41 + 1) = v17;
  v42 = v41;
  v13(v16, &v42, v67);
  if ( v68 != -1 && v68 && v68 != 1 && (unsigned __int64)(v68 - 2LL) >= 2 )
    std::wstring::~wstring(v67);
  v18 = 0;
  v19 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v56);
  v20 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](
          (char *)this + 24,
          &v56);
  if ( *(_BYTE *)(v20 + 8) )
    *(_BYTE *)(v20 + 8) = 0;
  *(_DWORD *)v20 = 0;
  std::wstring::~wstring(&v56);
  v21 = (_QWORD *)Windows::RebootDowntime::InputBuilder::m_topAppNames;
  *(_QWORD *)&v41 = qword_180151178;
  if ( Windows::RebootDowntime::InputBuilder::m_topAppNames != qword_180151178 )
  {
    do
    {
      v22 = v21;
      if ( v21[3] > 7u )
        v22 = (_QWORD *)*v21;
      v23 = 0xCBF29CE484222325uLL;
      v24 = 0;
      v25 = 2LL * v21[2];
      if ( v25 )
      {
        do
          v23 = 0x100000001B3LL * (*((unsigned __int8 *)v22 + v24++) ^ (unsigned __int64)v23);
        while ( v24 < v25 );
      }
      v26 = std::_Hash<std::_Umap_traits<std::wstring,double,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,double>>,0>>::_Find_last<std::wstring>(
              v69,
              v66,
              v21,
              v23,
              v40);
      v27 = v69[1];
      if ( *(_QWORD *)(v26 + 8) )
        v27 = *(_QWORD *)(v26 + 8);
      if ( v27 != v69[1] )
      {
        ++v18;
        if ( *(_BYTE *)(v27 + 80) )
        {
          v28 = *((_QWORD *)this + 25);
          v29 = *(void (__fastcall **)(__int64, _BYTE *, __int128 *))(*(_QWORD *)v28 + 64LL);
          v30 = v21[2];
          if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v30) < 0x11 )
            std::_Xlen_string();
          std::wstring::wstring(v59, v30, L"UXDowntimeVersion", 17);
          v31 = v59;
          if ( v59[3] > 7u )
            v31 = (_QWORD *)v59[0];
          *(_QWORD *)&v49 = v31;
          *((_QWORD *)&v49 + 1) = v59[2];
          v46 = v49;
          v29(v28, v70, &v46);
          std::wstring::~wstring(v59);
          if ( v72 )
          {
            if ( !v19 )
            {
              if ( v71 != 4 )
                std::_Throw_bad_variant_access();
              std::wstring::wstring(v67, v70);
              if ( *(_BYTE *)(v27 + 80) )
                v32 = std::operator==<wchar_t>(v67) ^ 1;
              else
                v32 = 1;
              if ( v32 )
              {
                v43 = 0;
                v44 = 0;
                v45 = 0;
                std::wstring::_Construct<1,wchar_t const *>(&v43);
                v33 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](
                        (char *)this + 24,
                        &v43);
                if ( *(_BYTE *)(v33 + 8) )
                  *(_BYTE *)(v33 + 8) = 0;
                *(_DWORD *)v33 = 1;
                std::wstring::~wstring(&v43);
                v19 = 1;
              }
              std::wstring::~wstring(v67);
            }
          }
          else
          {
            v60 = 0;
            v61 = 0;
            v62 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v60);
            v34 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](
                    (char *)this + 24,
                    &v60);
            if ( *(_BYTE *)(v34 + 8) )
              *(_BYTE *)(v34 + 8) = 0;
            *(_DWORD *)v34 = 1;
            std::wstring::~wstring(&v60);
            v19 = 1;
          }
          v35 = *((_QWORD *)this + 25);
          v36 = *(void (__fastcall **)(__int64, __int128 *, _QWORD *))(*(_QWORD *)v35 + 56LL);
          if ( !*(_BYTE *)(v27 + 80) )
            std::_Throw_bad_optional_access();
          std::wstring::wstring(v67, v27 + 48);
          v68 = 4;
          v37 = v21[2];
          if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v37) < 0x11 )
            std::_Xlen_string();
          std::wstring::wstring(&v43, v37, L"UXDowntimeVersion", 17);
          v38 = &v43;
          if ( v45 > 7 )
            v38 = (__int128 *)v43;
          *(_QWORD *)&v42 = v38;
          *((_QWORD *)&v42 + 1) = v44;
          v46 = v42;
          v36(v35, &v46, v67);
          std::wstring::~wstring(&v43);
          if ( v68 != -1 && v68 && v68 != 1 && (unsigned __int64)(v68 - 2LL) >= 2 )
            std::wstring::~wstring(v67);
          if ( v72 && v71 != -1 && v71 && v71 != 1 && (unsigned __int64)(v71 - 2LL) >= 2 )
            std::wstring::~wstring(v70);
        }
      }
      v21 += 4;
    }
    while ( v21 != (_QWORD *)v41 );
  }
  v63 = 0;
  v64 = 0;
  v65 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v63);
  v39 = std::unordered_map<std::wstring,std::variant<unsigned int,unsigned __int64>>::operator[](
          (char *)this + 24,
          &v63);
  if ( *(_BYTE *)(v39 + 8) != 1 )
    *(_BYTE *)(v39 + 8) = 1;
  *(_QWORD *)v39 = v18;
  std::wstring::~wstring(&v63);
  if ( v75 && v74 != -1 && v74 && v74 != 1 && (unsigned __int64)(v74 - 2LL) >= 2 )
    std::wstring::~wstring(v73);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(&v69[3]);
  std::list<std::pair<std::wstring const,std::optional<std::wstring>>>::~list<std::pair<std::wstring const,std::optional<std::wstring>>>(&v69[1]);
}

```

## disassembly

```asm
0x1800cbd94  mov     rax, rsp
0x1800cbd97  mov     [rax+10h], rbx
0x1800cbd9b  mov     [rax+18h], rsi
0x1800cbd9f  mov     [rax+20h], rdi
0x1800cbda3  push    rbp
0x1800cbda4  push    r12
0x1800cbda6  push    r13
0x1800cbda8  push    r14
0x1800cbdaa  push    r15
0x1800cbdac  lea     rbp, [rax-188h]
0x1800cbdb3  sub     rsp, 260h
0x1800cbdba  mov     rax, cs:__security_cookie
0x1800cbdc1  xor     rax, rsp
0x1800cbdc4  mov     [rbp+180h+var_30], rax
0x1800cbdcb  mov     r13, rcx
0x1800cbdce  xor     r14d, r14d
0x1800cbdd1  xor     edx, edx; Val
0x1800cbdd3  lea     r8d, [r14+40h]; Size
0x1800cbdd7  lea     rcx, [rbp+180h+var_D0]; void *
0x1800cbdde  call    memset
0x1800cbde3  lea     rdx, [rbp+180h+var_D0]
0x1800cbdea  call    ?QueryWin32Apps@InputBuilder@RebootDowntime@Windows@@AEAA?AV?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@@std@@XZ; Windows::RebootDowntime::InputBuilder::QueryWin32Apps(void)
0x1800cbdef  nop
0x1800cbdf0  mov     rbx, [rbp+180h+var_C0]
0x1800cbdf7  lea     rdi, [r13+18h]
0x1800cbdfb  xorps   xmm0, xmm0
0x1800cbdfe  movups  [rbp+180h+var_200], xmm0
0x1800cbe02  mov     [rbp+180h+var_1F0], r14
0x1800cbe06  mov     [rbp+180h+var_1E8], r14
0x1800cbe0a  lea     r8d, [r14+16h]
0x1800cbe0e  lea     rdx, aNumberofinstal; "NumberOfInstalledWin32"
0x1800cbe15  lea     rcx, [rbp+180h+var_200]
0x1800cbe19  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800cbe1e  nop
0x1800cbe1f  lea     rdx, [rbp+180h+var_200]
0x1800cbe23  mov     rcx, rdi
0x1800cbe26  call    ??A?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_K@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_K@2@@std@@@2@@std@@QEAAAEAV?$variant@I_K@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::unordered_map<std::wstring,std::variant<uint,unsigned __int64>>::operator[](std::wstring &&)
0x1800cbe2b  cmp     byte ptr [rax+8], 1
0x1800cbe2f  jz      short loc_1800CBE35
0x1800cbe31  mov     byte ptr [rax+8], 1
0x1800cbe35  mov     [rax], rbx
0x1800cbe38  lea     rcx, [rbp+180h+var_200]; void *
0x1800cbe3c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cbe41  mov     r11, [r13+0C8h]
0x1800cbe48  mov     rax, [r11]
0x1800cbe4b  mov     rbx, [rax+40h]
0x1800cbe4f  xor     r8d, r8d
0x1800cbe52  lea     r15, word_180129FA6
0x1800cbe59  mov     rdx, r15
0x1800cbe5c  lea     rsi, aUxdowntimenumw; "UXDowntimeNumWin32Apps"
0x1800cbe63  mov     rcx, rsi
0x1800cbe66  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800cbe6b  cmp     rax, r15
0x1800cbe6e  jz      loc_1800CC4DD
0x1800cbe74  sub     rax, rsi
0x1800cbe77  sar     rax, 1
0x1800cbe7a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800cbe7e  jz      loc_1800CC4DD
0x1800cbe84  mov     qword ptr [rsp+280h+var_248+8], rsi
0x1800cbe89  mov     qword ptr [rsp+280h+var_238], rax
0x1800cbe8e  movaps  xmm0, [rsp+280h+var_248+8]
0x1800cbe93  movdqa  [rsp+280h+var_238+8], xmm0
0x1800cbe99  lea     r8, [rsp+280h+var_238+8]
0x1800cbe9e  lea     rdx, [rbp+180h+var_60]
0x1800cbea5  mov     rcx, r11
0x1800cbea8  mov     rax, rbx
0x1800cbeab  call    _guard_dispatch_icall
0x1800cbeb0  nop
0x1800cbeb1  cmp     [rbp+180h+var_38], r14b
0x1800cbeb8  jz      short loc_1800CBF1D
0x1800cbeba  cmp     [rbp+180h+var_40], 3
0x1800cbec1  jnz     loc_1800CC4F6
0x1800cbec7  mov     ebx, r14d
0x1800cbeca  mov     rax, [rbp+180h+var_C0]
0x1800cbed1  cmp     [rbp+180h+var_60], rax
0x1800cbed8  setnz   bl
0x1800cbedb  xorps   xmm0, xmm0
0x1800cbede  movups  [rbp+180h+var_1D0], xmm0
0x1800cbee2  mov     [rbp+180h+var_1C0], r14
0x1800cbee6  mov     [rbp+180h+var_1B8], r14
0x1800cbeea  mov     r8d, 22h ; '"'
0x1800cbef0  lea     rdx, aDidnumberofins; "DidNumberOfInstalledWin32AppChange"
0x1800cbef7  lea     rcx, [rbp+180h+var_1D0]
0x1800cbefb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800cbf00  nop
0x1800cbf01  lea     rdx, [rbp+180h+var_1D0]
0x1800cbf05  mov     rcx, rdi
0x1800cbf08  call    ??A?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_K@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_K@2@@std@@@2@@std@@QEAAAEAV?$variant@I_K@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::unordered_map<std::wstring,std::variant<uint,unsigned __int64>>::operator[](std::wstring &&)
0x1800cbf0d  cmp     [rax+8], r14b
0x1800cbf11  jz      short loc_1800CBF17
0x1800cbf13  mov     [rax+8], r14b
0x1800cbf17  lea     rcx, [rbp+180h+var_1D0]
0x1800cbf1b  jmp     short loc_1800CBF6A
0x1800cbf1d  mov     ebx, r14d
0x1800cbf20  cmp     [rbp+180h+var_C0], r14
0x1800cbf27  setnz   bl
0x1800cbf2a  xorps   xmm0, xmm0
0x1800cbf2d  movups  [rbp+180h+var_1B0], xmm0
0x1800cbf31  mov     [rbp+180h+var_1A0], r14
0x1800cbf35  mov     [rbp+180h+var_198], r14
0x1800cbf39  mov     r8d, 22h ; '"'
0x1800cbf3f  lea     rdx, aDidnumberofins; "DidNumberOfInstalledWin32AppChange"
0x1800cbf46  lea     rcx, [rbp+180h+var_1B0]
0x1800cbf4a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800cbf4f  nop
0x1800cbf50  lea     rdx, [rbp+180h+var_1B0]
0x1800cbf54  mov     rcx, rdi
0x1800cbf57  call    ??A?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_K@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_K@2@@std@@@2@@std@@QEAAAEAV?$variant@I_K@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::unordered_map<std::wstring,std::variant<uint,unsigned __int64>>::operator[](std::wstring &&)
0x1800cbf5c  cmp     [rax+8], r14b
0x1800cbf60  jz      short loc_1800CBF66
0x1800cbf62  mov     [rax+8], r14b
0x1800cbf66  lea     rcx, [rbp+180h+var_1B0]; void *
0x1800cbf6a  mov     [rax], ebx
0x1800cbf6c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cbf71  mov     r11, [r13+0C8h]
0x1800cbf78  mov     rax, [r11]
0x1800cbf7b  mov     rbx, [rax+38h]
0x1800cbf7f  mov     rax, [rbp+180h+var_C0]
0x1800cbf86  mov     [rbp+180h+var_100], rax
0x1800cbf8d  mov     [rbp+180h+var_E0], 3
0x1800cbf94  xor     r8d, r8d
0x1800cbf97  mov     rdx, r15
0x1800cbf9a  mov     rcx, rsi
0x1800cbf9d  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800cbfa2  cmp     rax, r15
0x1800cbfa5  jz      loc_1800CC4C4
0x1800cbfab  sub     rax, rsi
0x1800cbfae  sar     rax, 1
0x1800cbfb1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800cbfb5  jz      loc_1800CC4C4
0x1800cbfbb  mov     qword ptr [rsp+280h+var_248+8], rsi
0x1800cbfc0  mov     qword ptr [rsp+280h+var_238], rax
0x1800cbfc5  movaps  xmm0, [rsp+280h+var_248+8]
0x1800cbfca  movdqa  [rsp+280h+var_238+8], xmm0
0x1800cbfd0  lea     r8, [rbp+180h+var_100]
0x1800cbfd7  lea     rdx, [rsp+280h+var_238+8]
0x1800cbfdc  mov     rcx, r11
0x1800cbfdf  mov     rax, rbx
0x1800cbfe2  call    _guard_dispatch_icall
0x1800cbfe7  nop
0x1800cbfe8  movsx   rax, [rbp+180h+var_E0]
0x1800cbff0  add     rax, 1
0x1800cbff4  jz      short loc_1800CC01A
0x1800cbff6  sub     rax, 1
0x1800cbffa  jz      short loc_1800CC01A
0x1800cbffc  sub     rax, 1
0x1800cc000  jz      short loc_1800CC01A
0x1800cc002  sub     rax, 1
0x1800cc006  jz      short loc_1800CC01A
0x1800cc008  cmp     rax, 1
0x1800cc00c  jz      short loc_1800CC01A
0x1800cc00e  lea     rcx, [rbp+180h+var_100]; void *
0x1800cc015  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cc01a  mov     rsi, r14
0x1800cc01d  mov     r12b, r14b
0x1800cc020  xorps   xmm0, xmm0
0x1800cc023  movups  [rbp+180h+var_190], xmm0
0x1800cc027  mov     [rbp+180h+var_180], r14
0x1800cc02b  mov     [rbp+180h+var_178], r14
0x1800cc02f  mov     r8d, 1Dh
0x1800cc035  lea     rdx, aDidmostcommona; "DidMostCommonAppChangeVersion"
0x1800cc03c  lea     rcx, [rbp+180h+var_190]
0x1800cc040  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800cc045  nop
0x1800cc046  lea     rdx, [rbp+180h+var_190]
0x1800cc04a  mov     rcx, rdi
0x1800cc04d  call    ??A?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_K@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_K@2@@std@@@2@@std@@QEAAAEAV?$variant@I_K@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::unordered_map<std::wstring,std::variant<uint,unsigned __int64>>::operator[](std::wstring &&)
0x1800cc052  mov     ecx, r14d
0x1800cc055  cmp     [rax+8], r14b
0x1800cc059  jz      short loc_1800CC05F
0x1800cc05b  mov     [rax+8], r14b
0x1800cc05f  mov     [rax], ecx
0x1800cc061  lea     rcx, [rbp+180h+var_190]; void *
0x1800cc065  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cc06a  mov     rbx, cs:?m_topAppNames@InputBuilder@RebootDowntime@Windows@@0V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@B; std::vector<std::wstring> const Windows::RebootDowntime::InputBuilder::m_topAppNames
0x1800cc071  mov     rax, cs:qword_180151178
0x1800cc078  mov     qword ptr [rsp+280h+var_248+8], rax
0x1800cc07d  cmp     rbx, rax
0x1800cc080  jz      loc_1800CC3F6
0x1800cc086  mov     r8, [rbx+10h]
0x1800cc08a  mov     rdx, rbx
0x1800cc08d  cmp     qword ptr [rbx+18h], 7
0x1800cc092  jbe     short loc_1800CC097
0x1800cc094  mov     rdx, [rbx]
0x1800cc097  mov     r9, 0CBF29CE484222325h
0x1800cc0a1  mov     rcx, r14
0x1800cc0a4  add     r8, r8
0x1800cc0a7  jz      short loc_1800CC0C6
0x1800cc0a9  movzx   eax, byte ptr [rdx+rcx]
0x1800cc0ad  xor     r9, rax
0x1800cc0b0  mov     r10, 100000001B3h
0x1800cc0ba  imul    r9, r10
0x1800cc0be  inc     rcx
0x1800cc0c1  cmp     rcx, r8
0x1800cc0c4  jb      short loc_1800CC0A9
0x1800cc0c6  mov     r8, rbx
0x1800cc0c9  lea     rdx, [rbp+180h+var_110]
0x1800cc0cd  lea     rcx, [rbp+180h+var_D0]
0x1800cc0d4  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@NV?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@N@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@N@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,double,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,double>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1800cc0d9  mov     rdi, [rbp+180h+var_C8]
0x1800cc0e0  cmp     [rax+8], r14
0x1800cc0e4  cmovnz  rdi, [rax+8]
0x1800cc0e9  cmp     rdi, [rbp+180h+var_C8]
0x1800cc0f0  jz      loc_1800CC3E7
0x1800cc0f6  inc     rsi
0x1800cc0f9  cmp     [rdi+50h], r14b
0x1800cc0fd  jz      loc_1800CC3E7
0x1800cc103  mov     r14, [r13+0C8h]
0x1800cc10a  mov     rax, [r14]
0x1800cc10d  mov     r15, [rax+40h]
0x1800cc111  mov     rcx, [rbx+10h]
0x1800cc115  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800cc11f  sub     rax, rcx
0x1800cc122  cmp     rax, 11h
0x1800cc126  jb      loc_1800CC50E
0x1800cc12c  mov     r9, rbx
0x1800cc12f  cmp     qword ptr [rbx+18h], 7
0x1800cc134  jbe     short loc_1800CC139
0x1800cc136  mov     r9, [rbx]
0x1800cc139  mov     [rsp+280h+var_250], 11h; __int64
0x1800cc142  lea     rax, aUxdowntimevers; "UXDowntimeVersion"
0x1800cc149  mov     [rsp+280h+Src], rax; Src
0x1800cc14e  mov     [rsp+280h+var_260], rcx; __int64
0x1800cc153  lea     rcx, [rbp+180h+var_170]; void *
0x1800cc157  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800cc15c  nop
0x1800cc15d  lea     rdx, [rbp+180h+var_170]
0x1800cc161  cmp     [rbp+180h+var_158], 7
0x1800cc166  cmova   rdx, [rbp+180h+var_170]
0x1800cc16b  mov     qword ptr [rbp+180h+var_1E0], rdx
0x1800cc16f  mov     rdx, [rbp+180h+var_160]
0x1800cc173  mov     qword ptr [rbp+180h+var_1E0+8], rdx
0x1800cc177  movaps  xmm0, [rbp+180h+var_1E0]
0x1800cc17b  movdqa  [rbp+180h+var_200], xmm0
0x1800cc180  lea     r8, [rbp+180h+var_200]
0x1800cc184  lea     rdx, [rbp+180h+var_90]
0x1800cc18b  mov     rcx, r14
0x1800cc18e  mov     rax, r15
0x1800cc191  call    _guard_dispatch_icall
0x1800cc196  nop
0x1800cc197  lea     rcx, [rbp+180h+var_170]; void *
0x1800cc19b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cc1a0  xor     r14d, r14d
0x1800cc1a3  cmp     [rbp+180h+var_68], r14b
0x1800cc1aa  jz      loc_1800CC25E
0x1800cc1b0  test    r12b, r12b
0x1800cc1b3  jnz     loc_1800CC2AE
0x1800cc1b9  cmp     [rbp+180h+var_70], 4
0x1800cc1c0  jnz     loc_1800CC4FC
0x1800cc1c6  lea     rdx, [rbp+180h+var_90]
0x1800cc1cd  lea     rcx, [rbp+180h+var_100]
0x1800cc1d4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800cc1d9  nop
0x1800cc1da  lea     rdx, [rdi+30h]
0x1800cc1de  cmp     [rdx+20h], r14b
0x1800cc1e2  jz      short loc_1800CC1F4
0x1800cc1e4  lea     rcx, [rbp+180h+var_100]
0x1800cc1eb  call    ??$?8_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator==<wchar_t>(std::wstring const &,std::wstring const &)
0x1800cc1f0  xor     al, 1
0x1800cc1f2  jmp     short loc_1800CC1F6
0x1800cc1f4  mov     al, 1
0x1800cc1f6  test    al, al
0x1800cc1f8  jz      short loc_1800CC250
0x1800cc1fa  xorps   xmm0, xmm0
0x1800cc1fd  movups  xmmword ptr [rsp+280h+var_228+8], xmm0
0x1800cc202  mov     [rsp+280h+var_210], r14
0x1800cc207  mov     [rsp+280h+var_208], r14
0x1800cc20c  mov     r8d, 1Dh
0x1800cc212  lea     rdx, aDidmostcommona; "DidMostCommonAppChangeVersion"
0x1800cc219  lea     rcx, [rsp+280h+var_228+8]
0x1800cc21e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800cc223  nop
0x1800cc224  lea     rdx, [rsp+280h+var_228+8]
0x1800cc229  lea     rcx, [r13+18h]
0x1800cc22d  call    ??A?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_K@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_K@2@@std@@@2@@std@@QEAAAEAV?$variant@I_K@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::unordered_map<std::wstring,std::variant<uint,unsigned __int64>>::operator[](std::wstring &&)
0x1800cc232  mov     ecx, 1
0x1800cc237  cmp     [rax+8], r14b
0x1800cc23b  jz      short loc_1800CC241
0x1800cc23d  mov     [rax+8], r14b
0x1800cc241  mov     [rax], ecx
0x1800cc243  lea     rcx, [rsp+280h+var_228+8]; void *
0x1800cc248  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cc24d  mov     r12b, 1
0x1800cc250  lea     rcx, [rbp+180h+var_100]; void *
0x1800cc257  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cc25c  jmp     short loc_1800CC2AE
0x1800cc25e  xorps   xmm0, xmm0
0x1800cc261  movups  [rbp+180h+var_150], xmm0
0x1800cc265  mov     [rbp+180h+var_140], r14
0x1800cc269  mov     [rbp+180h+var_138], r14
0x1800cc26d  mov     r8d, 1Dh
0x1800cc273  lea     rdx, aDidmostcommona; "DidMostCommonAppChangeVersion"
0x1800cc27a  lea     rcx, [rbp+180h+var_150]
0x1800cc27e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800cc283  nop
0x1800cc284  lea     rdx, [rbp+180h+var_150]
0x1800cc288  lea     rcx, [r13+18h]
0x1800cc28c  call    ??A?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_K@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_K@2@@std@@@2@@std@@QEAAAEAV?$variant@I_K@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::unordered_map<std::wstring,std::variant<uint,unsigned __int64>>::operator[](std::wstring &&)
0x1800cc291  mov     ecx, 1
0x1800cc296  cmp     [rax+8], r14b
  ... truncated ...
```
