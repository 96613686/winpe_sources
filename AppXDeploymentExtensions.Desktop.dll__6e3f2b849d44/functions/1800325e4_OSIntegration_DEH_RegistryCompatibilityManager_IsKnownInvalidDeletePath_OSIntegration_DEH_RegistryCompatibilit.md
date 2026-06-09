# OSIntegration::DEH::RegistryCompatibilityManager::IsKnownInvalidDeletePath(OSIntegration::DEH::RegistryCompatibility::KeyPath const &)

- ea: `0x1800325e4`
- end: `0x1800328f3`
- name: `?IsKnownInvalidDeletePath@RegistryCompatibilityManager@DEH@OSIntegration@@CA_NAEBVKeyPath@RegistryCompatibility@23@@Z`
- size: `783`
- prototype: `char __fastcall(WCHAR *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006ee4c`
- `0x18006f2cc`

## callees

- `0x1800325e4`
- `0x180033390`
- `0x180064960`
- `0x180064a4c`
- `0x180066780`
- `0x180078818`
- `0x1800aed10`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180032625`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180032625`
- `ntdll!RtlEqualUnicodeString` at `0x180032787`
- `ntdll!RtlEqualUnicodeString` at `0x180032787`

## string_xrefs

- `0x180032650`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\registrycompatibilitymanager.cpp`
- `0x1800327c4`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x1800327f4`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x18003282d`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x18003285d`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x18003288d`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x1800328ba`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\RegistryCompatibilityTypes.hpp`
- `0x1800327bd`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x1800327ed`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x180032826`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x180032856`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x180032886`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x1800328b3`: `OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath`
- `0x18003263d`: `!InitOnceExecuteOnce(&s_initOnceKnownInvalidDeletePaths, [](PINIT_ONCE, PVOID, PVOID*) { try { static constexpr PCWSTR PathsWithWowNodes[] = { L"SOFTWARE", LR"(SOFTWARE\Classes)", }; static constexpr PCWSTR WowNodeStrings[] = { WOW6432NODE_WSTR, WOWAMD64NODE_WSTR, WOWARMNODE_WSTR, WOWARM64NODE_WSTR }; static constexpr PCWSTR PathsWithoutWowNodes[] = { L"SYSTEM", }; for (auto baseInvalidPath : PathsWithWowNodes) { s_knownInvalidDeletePaths.push_back(baseInvalidPath); for (auto wowNodeString : Wow`
- `0x180032649`: `OSIntegration::DEH::RegistryCompatibilityManager::IsKnownInvalidDeletePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall OSIntegration::DEH::RegistryCompatibilityManager::IsKnownInvalidDeletePath(WCHAR *a1)
{
  _QWORD *i; // rbx
  _QWORD *v3; // r14
  __int64 StringLength; // r8
  _QWORD *v5; // rdx
  unsigned __int64 v6; // rdx
  __int64 v7; // rdi
  _QWORD *v8; // rcx
  __int64 v9; // rax
  WCHAR *v10; // rdx
  WCHAR *v11; // r8
  char *v13; // [rsp+28h] [rbp-58h]
  UNICODE_STRING String2; // [rsp+30h] [rbp-50h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v16[2]; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v17; // [rsp+60h] [rbp-20h]
  unsigned __int64 v18; // [rsp+68h] [rbp-18h]
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+18h]

  if ( !InitOnceExecuteOnce(
          &OSIntegration::DEH::RegistryCompatibilityManager::s_initOnceKnownInvalidDeletePaths,
          _lambda_99e96b87ed952ceeb7816276dfd9e1fe_::_lambda_invoker_cdecl_,
          0,
          0) )
  {
    LODWORD(v13) = -2147024882;
    wil::details::in1diag5::Throw_Hr(
      retaddr,
      (void *)0x40B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\registrycompatibilitymanager.cpp",
      "OSIntegration::DEH::RegistryCompatibilityManager::IsKnownInvalidDeletePath",
      "!InitOnceExecuteOnce(&s_initOnceKnownInvalidDeletePaths, [](PINIT_ONCE, PVOID, PVOID*) { try { static constexpr PC"
      "WSTR PathsWithWowNodes[] = { L\"SOFTWARE\", LR\"(SOFTWARE\\Classes)\", }; static constexpr PCWSTR WowNodeStrings[]"
      " = { WOW6432NODE_WSTR, WOWAMD64NODE_WSTR, WOWARMNODE_WSTR, WOWARM64NODE_WSTR }; static constexpr PCWSTR PathsWitho"
      "utWowNodes[] = { L\"SYSTEM\", }; for (auto baseInvalidPath : PathsWithWowNodes) { s_knownInvalidDeletePaths.push_b"
      "ack(baseInvalidPath); for (auto wowNodeString : WowNodeStrings) { std::wstring invalidPath(baseInvalidPath); inval"
      "idPath += wowNodeString; s_knownInvalidDeletePaths.push_back(std::move(invalidPath)); } } for (auto invalidPath : "
      "PathsWithoutWowNodes) { s_knownInvalidDeletePaths.push_back(invalidPath); } return TRUE; } catch (...) { s_knownIn"
      "validDeletePaths.clear(); return FALSE; } }, nullptr, nullptr)",
      v13,
      *(int *)&String2.Length);
  }
  v3 = *(&OSIntegration::DEH::RegistryCompatibilityManager::s_knownInvalidDeletePaths + 1);
  for ( i = OSIntegration::DEH::RegistryCompatibilityManager::s_knownInvalidDeletePaths; i != v3; i += 4 )
  {
    StringLength = (unsigned int)OSIntegration::DEH::RegistryCompatibility::Details::GetStringLength(i);
    if ( i[3] <= 7u )
      v5 = i;
    else
      v5 = (_QWORD *)*i;
    std::wstring::wstring(v16, v5, StringLength);
    v6 = v17;
    if ( !v17 )
    {
      LODWORD(v13) = -2147024809;
      wil::details::in1diag5::Throw_Hr(
        retaddr,
        (void *)0x3C5,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
        "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
        "m_text.length() == 0",
        v13,
        *(int *)&String2.Length);
    }
    if ( v17 > 0x7FFF )
    {
      LODWORD(v13) = -2147024809;
      wil::details::in1diag5::Throw_Hr(
        retaddr,
        (void *)0x3C8,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
        "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
        "m_text.length() > UNICODE_STRING_MAX_CHARS",
        v13,
        *(int *)&String2.Length);
    }
    v7 = 0;
    while ( 1 )
    {
      v8 = v16;
      if ( v18 > 7 )
        v8 = (_QWORD *)v16[0];
      v9 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v8, v6, v7);
      if ( v9 == -1 )
        break;
      if ( v7 == v9 )
      {
        LODWORD(v13) = -2147024809;
        wil::details::in1diag5::Throw_Hr(
          retaddr,
          (void *)0x3D6,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
          "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
          "currentBegin == currentEnd",
          v13,
          *(int *)&String2.Length);
      }
      if ( (unsigned __int64)(v9 - v7) > 0x100 )
      {
        LODWORD(v13) = -2147024809;
        wil::details::in1diag5::Throw_Hr(
          retaddr,
          (void *)0x3D7,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
          "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
          "(currentEnd - currentBegin) > MaxKeyNameLength",
          v13,
          *(int *)&String2.Length);
      }
      v7 = v9 + 1;
      v6 = v17;
    }
    if ( v7 == v17 )
    {
      LODWORD(v13) = -2147024809;
      wil::details::in1diag5::Throw_Hr(
        retaddr,
        (void *)0x3D0,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
        "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
        "currentBegin == m_text.length()",
        v13,
        *(int *)&String2.Length);
    }
    if ( v17 - v7 > 0x100 )
    {
      LODWORD(v13) = -2147024809;
      wil::details::in1diag5::Throw_Hr(
        retaddr,
        (void *)0x3D1,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\RegistryCompatibilityTypes.hpp",
        "OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath",
        "(m_text.length() - currentBegin) > MaxKeyNameLength",
        v13,
        *(int *)&String2.Length);
    }
    v10 = (WCHAR *)v16;
    if ( v18 > 7 )
      v10 = (WCHAR *)v16[0];
    if ( *((_QWORD *)a1 + 3) <= 7u )
      v11 = a1;
    else
      v11 = *(WCHAR **)a1;
    String1.Length = 2 * a1[8];
    String1.MaximumLength = String1.Length;
    *(_DWORD *)(&String1.MaximumLength + 1) = 0;
    String1.Buffer = v11;
    String2.Length = 2 * v17;
    String2.MaximumLength = 2 * v17;
    *(_DWORD *)(&String2.MaximumLength + 1) = 0;
    String2.Buffer = v10;
    if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
    {
      std::wstring::_Tidy_deallocate(v16);
      return 1;
    }
    std::wstring::_Tidy_deallocate(v16);
  }
  return 0;
}

```

## disassembly

```asm
0x1800325e4  mov     [rsp-18h+arg_8], rbx
0x1800325e9  mov     [rsp-18h+arg_10], rsi
0x1800325ee  push    rbp
0x1800325ef  push    rdi
0x1800325f0  push    r14
0x1800325f2  mov     rbp, rsp
0x1800325f5  sub     rsp, 80h
0x1800325fc  mov     rax, cs:__security_cookie
0x180032603  xor     rax, rsp
0x180032606  mov     [rbp+var_10], rax
0x18003260a  mov     rsi, rcx
0x18003260d  mov     rbx, [rbp+18h]
0x180032611  xor     r9d, r9d; Context
0x180032614  xor     r8d, r8d; Parameter
0x180032617  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_99e96b87ed952ceeb7816276dfd9e1fe_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18003261e  lea     rcx, ?s_initOnceKnownInvalidDeletePaths@RegistryCompatibilityManager@DEH@OSIntegration@@0T_RTL_RUN_ONCE@@A; InitOnce
0x180032625  call    cs:__imp_InitOnceExecuteOnce
0x18003262c  nop     dword ptr [rax+rax+00h]
0x180032631  test    eax, eax
0x180032633  jnz     short loc_180032665
0x180032635  mov     dword ptr [rsp+80h+var_58], 8007000Eh; char *
0x18003263d  lea     rax, aInitonceexecut; "!InitOnceExecuteOnce(&s_initOnceKnownIn"...
0x180032644  mov     [rsp+80h+var_60], rax; char *
0x180032649  lea     r9, aOsintegrationD_22; "OSIntegration::DEH::RegistryCompatibili"...
0x180032650  lea     r8, aOnecoreAdminAp_44; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180032657  mov     edx, 40Bh; void *
0x18003265c  mov     rcx, rbx; this
0x18003265f  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x180032665  mov     rbx, qword ptr cs:?s_knownInvalidDeletePaths@RegistryCompatibilityManager@DEH@OSIntegration@@0V?$vector@VKeyPath@RegistryCompatibility@DEH@OSIntegration@@V?$allocator@VKeyPath@RegistryCompatibility@DEH@OSIntegration@@@std@@@std@@A; std::vector<OSIntegration::DEH::RegistryCompatibility::KeyPath> OSIntegration::DEH::RegistryCompatibilityManager::s_knownInvalidDeletePaths
0x18003266c  mov     r14, qword ptr cs:?s_knownInvalidDeletePaths@RegistryCompatibilityManager@DEH@OSIntegration@@0V?$vector@VKeyPath@RegistryCompatibility@DEH@OSIntegration@@V?$allocator@VKeyPath@RegistryCompatibility@DEH@OSIntegration@@@std@@@std@@A+8; std::vector<OSIntegration::DEH::RegistryCompatibility::KeyPath> OSIntegration::DEH::RegistryCompatibilityManager::s_knownInvalidDeletePaths
0x180032673  cmp     rbx, r14
0x180032676  jz      loc_1800328CC
0x18003267c  mov     rcx, rbx
0x18003267f  call    ?GetStringLength@Details@RegistryCompatibility@DEH@OSIntegration@@YAIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; OSIntegration::DEH::RegistryCompatibility::Details::GetStringLength(std::wstring const &)
0x180032684  mov     r8d, eax
0x180032687  cmp     qword ptr [rbx+18h], 7
0x18003268c  jbe     short loc_180032693
0x18003268e  mov     rdx, [rbx]
0x180032691  jmp     short loc_180032696
0x180032693  mov     rdx, rbx
0x180032696  lea     rcx, [rbp+var_30]
0x18003269a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18003269f  nop
0x1800326a0  mov     rdx, [rbp+var_20]
0x1800326a4  mov     rcx, [rbp+18h]; this
0x1800326a8  test    rdx, rdx
0x1800326ab  jz      loc_18003289F
0x1800326b1  mov     rcx, [rbp+18h]; this
0x1800326b5  cmp     rdx, 7FFFh
0x1800326bc  ja      loc_180032872
0x1800326c2  xor     edi, edi
0x1800326c4  lea     rcx, [rbp+var_30]
0x1800326c8  cmp     [rbp+var_18], 7
0x1800326cd  cmova   rcx, [rbp+var_30]
0x1800326d2  mov     r8, rdi
0x1800326d5  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1800326da  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800326de  jz      short loc_18003270E
0x1800326e0  mov     rcx, [rbp+18h]; this
0x1800326e4  cmp     rdi, rax
0x1800326e7  jz      loc_1800327D9
0x1800326ed  mov     r10, [rbp+18h]
0x1800326f1  mov     rcx, rax
0x1800326f4  sub     rcx, rdi
0x1800326f7  cmp     rcx, 100h
0x1800326fe  ja      loc_1800327A9
0x180032704  lea     rdi, [rax+1]
0x180032708  mov     rdx, [rbp+var_20]
0x18003270c  jmp     short loc_1800326C4
0x18003270e  mov     rcx, [rbp+var_20]
0x180032712  mov     rax, [rbp+18h]
0x180032716  cmp     rdi, rcx
0x180032719  jz      loc_180032842
0x18003271f  mov     r10, [rbp+18h]
0x180032723  mov     rax, rcx
0x180032726  sub     rax, rdi
0x180032729  cmp     rax, 100h
0x18003272f  ja      loc_180032812
0x180032735  lea     rdx, [rbp+var_30]
0x180032739  cmp     [rbp+var_18], 7
0x18003273e  cmova   rdx, [rbp+var_30]
0x180032743  cmp     qword ptr [rsi+18h], 7
0x180032748  jbe     short loc_18003274F
0x18003274a  mov     r8, [rsi]
0x18003274d  jmp     short loc_180032752
0x18003274f  mov     r8, rsi
0x180032752  movzx   eax, word ptr [rsi+10h]
0x180032756  add     ax, ax
0x180032759  mov     [rbp+String1.Length], ax
0x18003275d  mov     [rbp+String1.MaximumLength], ax
0x180032761  xor     eax, eax
0x180032763  mov     dword ptr [rbp+String1+4], eax
0x180032766  mov     [rbp+String1.Buffer], r8
0x18003276a  add     cx, cx
0x18003276d  mov     [rbp+String2.Length], cx
0x180032771  mov     [rbp+String2.MaximumLength], cx
0x180032775  mov     dword ptr [rbp+String2+4], eax
0x180032778  mov     [rbp+String2.Buffer], rdx
0x18003277c  mov     r8b, 1; CaseInsensitive
0x18003277f  lea     rdx, [rbp+String2]; String2
0x180032783  lea     rcx, [rbp+String1]; String1
0x180032787  call    cs:__imp_RtlEqualUnicodeString
0x18003278e  nop     dword ptr [rax+rax+00h]
0x180032793  lea     rcx, [rbp+var_30]
0x180032797  test    al, al
0x180032799  jnz     short loc_180032806
0x18003279b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800327a0  add     rbx, 20h ; ' '
0x1800327a4  jmp     loc_180032673
0x1800327a9  mov     dword ptr [rsp+80h+var_58], 80070057h; char *
0x1800327b1  lea     rax, aCurrentendCurr; "(currentEnd - currentBegin) > MaxKeyNam"...
0x1800327b8  mov     [rsp+80h+var_60], rax; char *
0x1800327bd  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x1800327c4  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800327cb  mov     edx, 3D7h; void *
0x1800327d0  mov     rcx, r10; this
0x1800327d3  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800327d9  mov     dword ptr [rsp+80h+var_58], 80070057h; char *
0x1800327e1  lea     rax, aCurrentbeginCu; "currentBegin == currentEnd"
0x1800327e8  mov     [rsp+80h+var_60], rax; char *
0x1800327ed  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x1800327f4  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800327fb  mov     edx, 3D6h; void *
0x180032800  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x180032806  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003280b  mov     al, 1
0x18003280d  jmp     loc_1800328CE
0x180032812  mov     dword ptr [rsp+80h+var_58], 80070057h; char *
0x18003281a  lea     rax, aMTextLengthCur; "(m_text.length() - currentBegin) > MaxK"...
0x180032821  mov     [rsp+80h+var_60], rax; char *
0x180032826  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x18003282d  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180032834  mov     edx, 3D1h; void *
0x180032839  mov     rcx, r10; this
0x18003283c  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x180032842  mov     dword ptr [rsp+80h+var_58], 80070057h; char *
0x18003284a  lea     rcx, aCurrentbeginMT; "currentBegin == m_text.length()"
0x180032851  mov     [rsp+80h+var_60], rcx; char *
0x180032856  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x18003285d  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180032864  mov     edx, 3D0h; void *
0x180032869  mov     rcx, rax; this
0x18003286c  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x180032872  mov     dword ptr [rsp+80h+var_58], 80070057h; char *
0x18003287a  lea     rax, aMTextLengthUni; "m_text.length() > UNICODE_STRING_MAX_CH"...
0x180032881  mov     [rsp+80h+var_60], rax; char *
0x180032886  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x18003288d  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180032894  mov     edx, 3C8h; void *
0x180032899  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003289f  mov     dword ptr [rsp+80h+var_58], 80070057h; char *
0x1800328a7  lea     rax, aMTextLength0; "m_text.length() == 0"
0x1800328ae  mov     [rsp+80h+var_60], rax; char *
0x1800328b3  lea     r9, aOsintegrationD_64; "OSIntegration::DEH::RegistryCompatibili"...
0x1800328ba  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800328c1  mov     edx, 3C5h; void *
0x1800328c6  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800328cc  xor     al, al
0x1800328ce  mov     rcx, [rbp+var_10]
0x1800328d2  xor     rcx, rsp; StackCookie
0x1800328d5  call    __security_check_cookie
0x1800328da  lea     r11, [rsp+80h+var_s0]
0x1800328e2  mov     rbx, [r11+28h]
0x1800328e6  mov     rsi, [r11+30h]
0x1800328ea  mov     rsp, r11
0x1800328ed  pop     r14
0x1800328ef  pop     rdi
0x1800328f0  pop     rbp
0x1800328f1  retn
```
