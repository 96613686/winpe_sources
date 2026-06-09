# OSIntegration::DEH::RegistryCompatibilityManager::GetPackageEntriesPath(ushort const *)

- ea: `0x180032f10`
- end: `0x180033388`
- name: `?GetPackageEntriesPath@RegistryCompatibilityManager@DEH@OSIntegration@@CA?AVKeyPath@RegistryCompatibility@23@PEBG@Z`
- size: `1144`
- prototype: `OSIntegration::DEH::RegistryCompatibility::KeyPath *__fastcall(OSIntegration::DEH::RegistryCompatibility::KeyPath *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031c54`
- `0x1800337e0`
- `0x180066ce0`
- `0x18010890c`
- `0x180108bdc`

## callees

- `0x180032b38`
- `0x180032f10`
- `0x180033390`
- `0x180064994`
- `0x180065acc`
- `0x180066780`
- `0x180078818`
- `0x1800aed10`

## string_xrefs

- `0x18003317b`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x1800331a8`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x1800331d5`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x180033205`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x180033235`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x180033262`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x18003328f`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x1800332bc`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x1800332e9`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x180033319`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x180033349`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x180033376`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x180033174`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x1800331a1`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x1800331ce`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x1800331fe`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x18003322e`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x18003325b`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x180033288`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x1800332b5`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x1800332e2`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x180033312`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x180033342`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x18003336f`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`

## pseudocode

```c
OSIntegration::DEH::RegistryCompatibility::KeyPath *__fastcall OSIntegration::DEH::RegistryCompatibilityManager::GetPackageEntriesPath(
        OSIntegration::DEH::RegistryCompatibility::KeyPath *a1,
        const unsigned __int16 *a2)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rbx
  __int128 *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rbx
  __int128 *v12; // rcx
  __int64 v13; // rax
  char *v15; // [rsp+28h] [rbp-48h]
  __int128 v16; // [rsp+40h] [rbp-30h] BYREF
  __int128 v17; // [rsp+50h] [rbp-20h]
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+28h]

  OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath(a1, (const unsigned __int16 (*)[45])a2);
  v16 = 0;
  v17 = 0;
  v4 = -1;
  do
    ++v4;
  while ( OSIntegration::DEH::RegistryCompatibility::PackageKeyName[v4] );
  std::wstring::_Construct<1,unsigned short const *>(&v16, L"Package", v4);
  v5 = v17;
  if ( !(_QWORD)v17 )
  {
    LODWORD(v15) = -2147024809;
    wil::details::in1diag5::Throw_Hr(
      retaddr,
      (void *)0x3C5,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
      "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
      "m_text.length() == 0",
      v15,
      1);
  }
  if ( (unsigned __int64)v17 > 0x7FFF )
  {
    LODWORD(v15) = -2147024809;
    wil::details::in1diag5::Throw_Hr(
      retaddr,
      (void *)0x3C8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
      "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
      "m_text.length() > UNICODE_STRING_MAX_CHARS",
      v15,
      1);
  }
  v6 = 0;
  while ( 1 )
  {
    v7 = &v16;
    if ( *((_QWORD *)&v17 + 1) > 7u )
      v7 = (__int128 *)v16;
    v8 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v7, v5, v6);
    if ( v8 == -1 )
      break;
    if ( v6 == v8 )
    {
      LODWORD(v15) = -2147024809;
      wil::details::in1diag5::Throw_Hr(
        retaddr,
        (void *)0x3D6,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
        "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
        "currentBegin == currentEnd",
        v15,
        1);
    }
    if ( (unsigned __int64)(v8 - v6) > 0x100 )
    {
      LODWORD(v15) = -2147024809;
      wil::details::in1diag5::Throw_Hr(
        retaddr,
        (void *)0x3D7,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
        "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
        "(currentEnd - currentBegin) > MaxKeyNameLength",
        v15,
        1);
    }
    v6 = v8 + 1;
    v5 = v17;
  }
  if ( v6 == (_QWORD)v17 )
  {
    LODWORD(v15) = -2147024809;
    wil::details::in1diag5::Throw_Hr(
      retaddr,
      (void *)0x3D0,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
      "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
      "currentBegin == m_text.length()",
      v15,
      1);
  }
  if ( (unsigned __int64)(v17 - v6) > 0x100 )
  {
    LODWORD(v15) = -2147024809;
    wil::details::in1diag5::Throw_Hr(
      retaddr,
      (void *)0x3D1,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
      "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
      "(m_text.length() - currentBegin) > MaxKeyNameLength",
      v15,
      1);
  }
  std::wstring::_Append<unsigned short>(a1);
  std::wstring::_Append<unsigned short>(a1);
  std::wstring::_Tidy_deallocate(&v16);
  v16 = 0;
  v17 = 0;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  std::wstring::_Construct<1,unsigned short const *>(&v16, a2, v9);
  v10 = v17;
  if ( !(_QWORD)v17 )
  {
    LODWORD(v15) = -2147024809;
    wil::details::in1diag5::Throw_Hr(
      retaddr,
      (void *)0x3C5,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
      "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
      "m_text.length() == 0",
      v15,
      1);
  }
  if ( (unsigned __int64)v17 > 0x7FFF )
  {
    LODWORD(v15) = -2147024809;
    wil::details::in1diag5::Throw_Hr(
      retaddr,
      (void *)0x3C8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
      "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
      "m_text.length() > UNICODE_STRING_MAX_CHARS",
      v15,
      1);
  }
  v11 = 0;
  while ( 1 )
  {
    v12 = &v16;
    if ( *((_QWORD *)&v17 + 1) > 7u )
      v12 = (__int128 *)v16;
    v13 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v12, v10, v11);
    if ( v13 == -1 )
      break;
    if ( v11 == v13 )
    {
      LODWORD(v15) = -2147024809;
      wil::details::in1diag5::Throw_Hr(
        retaddr,
        (void *)0x3D6,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
        "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
        "currentBegin == currentEnd",
        v15,
        1);
    }
    if ( (unsigned __int64)(v13 - v11) > 0x100 )
    {
      LODWORD(v15) = -2147024809;
      wil::details::in1diag5::Throw_Hr(
        retaddr,
        (void *)0x3D7,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
        "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
        "(currentEnd - currentBegin) > MaxKeyNameLength",
        v15,
        1);
    }
    v11 = v13 + 1;
    v10 = v17;
  }
  if ( v11 == (_QWORD)v17 )
  {
    LODWORD(v15) = -2147024809;
    wil::details::in1diag5::Throw_Hr(
      retaddr,
      (void *)0x3D0,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
      "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
      "currentBegin == m_text.length()",
      v15,
      1);
  }
  if ( (unsigned __int64)(v17 - v11) > 0x100 )
  {
    LODWORD(v15) = -2147024809;
    wil::details::in1diag5::Throw_Hr(
      retaddr,
      (void *)0x3D1,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
      "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
      "(m_text.length() - currentBegin) > MaxKeyNameLength",
      v15,
      1);
  }
  std::wstring::_Append<unsigned short>(a1);
  std::wstring::_Append<unsigned short>(a1);
  std::wstring::_Tidy_deallocate(&v16);
  return a1;
}

```

## disassembly

```asm
0x180032f10  mov     [rsp-28h+arg_10], rbx
0x180032f15  push    rbp
0x180032f16  push    rsi
0x180032f17  push    rdi
0x180032f18  push    r14
0x180032f1a  push    r15
0x180032f1c  mov     rbp, rsp
0x180032f1f  sub     rsp, 70h
0x180032f23  mov     rax, cs:__security_cookie
0x180032f2a  xor     rax, rsp
0x180032f2d  mov     [rbp+var_10], rax
0x180032f31  mov     rsi, rdx
0x180032f34  mov     rdi, rcx
0x180032f37  mov     [rbp+var_38], rcx
0x180032f3b  xor     r14d, r14d
0x180032f3e  mov     [rbp+var_40], r14d
0x180032f42  call    ??$?0AEAY0CN@$$CBG@KeyPath@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0CN@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath(ushort const (&)[45])
0x180032f47  mov     [rbp+var_40], 1
0x180032f4e  xorps   xmm0, xmm0
0x180032f51  movups  [rbp+var_30], xmm0
0x180032f55  xorps   xmm1, xmm1
0x180032f58  movdqu  [rbp+var_20], xmm1
0x180032f5d  lea     rdx, ?PackageKeyName@RegistryCompatibility@DEH@OSIntegration@@3QBGB; "Package"
0x180032f64  or      r8, 0FFFFFFFFFFFFFFFFh
0x180032f68  inc     r8
0x180032f6b  cmp     [rdx+r8*2], r14w
0x180032f70  jnz     short loc_180032F68
0x180032f72  lea     rcx, [rbp+var_30]
0x180032f76  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180032f7b  nop
0x180032f7c  mov     rdx, qword ptr [rbp+var_20]
0x180032f80  mov     rcx, [rbp+28h]; this
0x180032f84  test    rdx, rdx
0x180032f87  jz      loc_180033160
0x180032f8d  mov     rcx, [rbp+28h]; this
0x180032f91  cmp     rdx, 7FFFh
0x180032f98  ja      loc_18003318D
0x180032f9e  mov     rbx, r14
0x180032fa1  mov     r15d, 100h
0x180032fa7  lea     rcx, [rbp+var_30]
0x180032fab  cmp     qword ptr [rbp+var_20+8], 7
0x180032fb0  cmova   rcx, qword ptr [rbp+var_30]
0x180032fb5  mov     r8, rbx
0x180032fb8  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180032fbd  mov     rcx, rax
0x180032fc0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032fc4  jnz     loc_18003313A
0x180032fca  mov     rax, qword ptr [rbp+var_20]
0x180032fce  mov     rcx, [rbp+28h]; this
0x180032fd2  cmp     rbx, rax
0x180032fd5  jz      loc_18003321A
0x180032fdb  mov     rcx, [rbp+28h]; this
0x180032fdf  sub     rax, rbx
0x180032fe2  cmp     rax, r15
0x180032fe5  ja      loc_180033247
0x180032feb  mov     r8d, 1
0x180032ff1  lea     rdx, asc_1801C82A8; "\\"
0x180032ff8  mov     rcx, rdi; Src
0x180032ffb  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180033000  lea     rdx, [rbp+var_30]
0x180033004  cmp     qword ptr [rbp+var_20+8], 7
0x180033009  cmova   rdx, qword ptr [rbp+var_30]
0x18003300e  mov     r8, qword ptr [rbp+var_20]
0x180033012  mov     rcx, rdi; Src
0x180033015  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003301a  nop
0x18003301b  lea     rcx, [rbp+var_30]
0x18003301f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033024  xorps   xmm0, xmm0
0x180033027  movups  [rbp+var_30], xmm0
0x18003302b  xorps   xmm1, xmm1
0x18003302e  movdqu  [rbp+var_20], xmm1
0x180033033  or      r8, 0FFFFFFFFFFFFFFFFh
0x180033037  inc     r8
0x18003303a  cmp     [rsi+r8*2], r14w
0x18003303f  jnz     short loc_180033037
0x180033041  mov     rdx, rsi
0x180033044  lea     rcx, [rbp+var_30]
0x180033048  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003304d  nop
0x18003304e  mov     rdx, qword ptr [rbp+var_20]
0x180033052  mov     rcx, [rbp+28h]; this
0x180033056  test    rdx, rdx
0x180033059  jz      loc_180033274
0x18003305f  mov     rcx, [rbp+28h]; this
0x180033063  cmp     rdx, 7FFFh
0x18003306a  ja      loc_1800332A1
0x180033070  mov     rbx, r14
0x180033073  lea     rcx, [rbp+var_30]
0x180033077  cmp     qword ptr [rbp+var_20+8], 7
0x18003307c  cmova   rcx, qword ptr [rbp+var_30]
0x180033081  mov     r8, rbx
0x180033084  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180033089  mov     rcx, rax
0x18003308c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033090  jnz     short loc_180033110
0x180033092  mov     rax, qword ptr [rbp+var_20]
0x180033096  mov     rcx, [rbp+28h]; this
0x18003309a  cmp     rbx, rax
0x18003309d  jz      loc_18003332E
0x1800330a3  mov     rcx, [rbp+28h]; this
0x1800330a7  sub     rax, rbx
0x1800330aa  cmp     rax, r15
0x1800330ad  ja      loc_18003335B
0x1800330b3  mov     r8d, 1
0x1800330b9  lea     rdx, asc_1801C82A8; "\\"
0x1800330c0  mov     rcx, rdi; Src
0x1800330c3  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800330c8  lea     rdx, [rbp+var_30]
0x1800330cc  cmp     qword ptr [rbp+var_20+8], 7
0x1800330d1  cmova   rdx, qword ptr [rbp+var_30]
0x1800330d6  mov     r8, qword ptr [rbp+var_20]
0x1800330da  mov     rcx, rdi; Src
0x1800330dd  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800330e2  nop
0x1800330e3  lea     rcx, [rbp+var_30]
0x1800330e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800330ec  mov     rax, rdi
0x1800330ef  mov     rcx, [rbp+var_10]
0x1800330f3  xor     rcx, rsp; StackCookie
0x1800330f6  call    __security_check_cookie
0x1800330fb  mov     rbx, [rsp+70h+arg_10]
0x180033103  add     rsp, 70h
0x180033107  pop     r15
0x180033109  pop     r14
0x18003310b  pop     rdi
0x18003310c  pop     rsi
0x18003310d  pop     rbp
0x18003310e  retn
0x180033110  mov     r10, [rbp+28h]
0x180033114  cmp     rbx, rcx
0x180033117  jz      loc_1800332FE
0x18003311d  mov     r10, [rbp+28h]
0x180033121  sub     rax, rbx
0x180033124  cmp     rax, r15
0x180033127  ja      loc_1800332CE
0x18003312d  lea     rbx, [rcx+1]
0x180033131  mov     rdx, qword ptr [rbp+var_20]
0x180033135  jmp     loc_180033073
0x18003313a  mov     r10, [rbp+28h]
0x18003313e  cmp     rbx, rcx
0x180033141  jz      loc_1800331EA
0x180033147  mov     r10, [rbp+28h]
0x18003314b  sub     rax, rbx
0x18003314e  cmp     rax, r15
0x180033151  ja      short loc_1800331BA
0x180033153  lea     rbx, [rcx+1]
0x180033157  mov     rdx, qword ptr [rbp+var_20]
0x18003315b  jmp     loc_180032FA7
0x180033160  mov     dword ptr [rsp+70h+var_48], 80070057h; char *
0x180033168  lea     rax, aMTextLength0; "m_text.length() == 0"
0x18003316f  mov     [rsp+70h+var_50], rax; char *
0x180033174  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x18003317b  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180033182  mov     edx, 3C5h; void *
0x180033187  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003318d  mov     dword ptr [rsp+70h+var_48], 80070057h; char *
0x180033195  lea     rax, aMTextLengthUni; "m_text.length() > UNICODE_STRING_MAX_CH"...
0x18003319c  mov     [rsp+70h+var_50], rax; char *
0x1800331a1  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x1800331a8  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800331af  mov     edx, 3C8h; void *
0x1800331b4  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800331ba  mov     dword ptr [rsp+70h+var_48], 80070057h; char *
0x1800331c2  lea     rax, aCurrentendCurr; "(currentEnd - currentBegin) > MaxKeyNam"...
0x1800331c9  mov     [rsp+70h+var_50], rax; char *
0x1800331ce  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x1800331d5  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800331dc  mov     edx, 3D7h; void *
0x1800331e1  mov     rcx, r10; this
0x1800331e4  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800331ea  mov     dword ptr [rsp+70h+var_48], 80070057h; char *
0x1800331f2  lea     rax, aCurrentbeginCu; "currentBegin == currentEnd"
0x1800331f9  mov     [rsp+70h+var_50], rax; char *
0x1800331fe  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x180033205  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003320c  mov     edx, 3D6h; void *
0x180033211  mov     rcx, r10; this
0x180033214  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003321a  mov     dword ptr [rsp+70h+var_48], 80070057h; char *
0x180033222  lea     rax, aCurrentbeginMT; "currentBegin == m_text.length()"
0x180033229  mov     [rsp+70h+var_50], rax; char *
0x18003322e  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x180033235  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003323c  mov     edx, 3D0h; void *
0x180033241  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x180033247  mov     dword ptr [rsp+70h+var_48], 80070057h; char *
0x18003324f  lea     rax, aMTextLengthCur; "(m_text.length() - currentBegin) > MaxK"...
0x180033256  mov     [rsp+70h+var_50], rax; char *
0x18003325b  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x180033262  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180033269  mov     edx, 3D1h; void *
0x18003326e  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x180033274  mov     dword ptr [rsp+70h+var_48], 80070057h; char *
0x18003327c  lea     rax, aMTextLength0; "m_text.length() == 0"
0x180033283  mov     [rsp+70h+var_50], rax; char *
0x180033288  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x18003328f  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180033296  mov     edx, 3C5h; void *
0x18003329b  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800332a1  mov     dword ptr [rsp+70h+var_48], 80070057h; char *
0x1800332a9  lea     rax, aMTextLengthUni; "m_text.length() > UNICODE_STRING_MAX_CH"...
0x1800332b0  mov     [rsp+70h+var_50], rax; char *
0x1800332b5  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x1800332bc  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800332c3  mov     edx, 3C8h; void *
0x1800332c8  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800332ce  mov     dword ptr [rsp+70h+var_48], 80070057h; char *
0x1800332d6  lea     rax, aCurrentendCurr; "(currentEnd - currentBegin) > MaxKeyNam"...
0x1800332dd  mov     [rsp+70h+var_50], rax; char *
0x1800332e2  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x1800332e9  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800332f0  mov     edx, 3D7h; void *
0x1800332f5  mov     rcx, r10; this
0x1800332f8  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800332fe  mov     dword ptr [rsp+70h+var_48], 80070057h; char *
0x180033306  lea     rax, aCurrentbeginCu; "currentBegin == currentEnd"
0x18003330d  mov     [rsp+70h+var_50], rax; char *
0x180033312  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x180033319  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180033320  mov     edx, 3D6h; void *
0x180033325  mov     rcx, r10; this
0x180033328  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003332e  mov     dword ptr [rsp+70h+var_48], 80070057h; char *
0x180033336  lea     rax, aCurrentbeginMT; "currentBegin == m_text.length()"
0x18003333d  mov     [rsp+70h+var_50], rax; char *
0x180033342  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x180033349  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180033350  mov     edx, 3D0h; void *
0x180033355  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003335b  mov     dword ptr [rsp+70h+var_48], 80070057h; char *
0x180033363  lea     rax, aMTextLengthCur; "(m_text.length() - currentBegin) > MaxK"...
0x18003336a  mov     [rsp+70h+var_50], rax; char *
0x18003336f  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x180033376  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003337d  mov     edx, 3D1h; void *
0x180033382  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
```
