# LogLanguageGroupingState(void *)

- ea: `0x1800407dc`
- end: `0x180040c46`
- name: `?LogLanguageGroupingState@@YAXPEAX@Z`
- size: `1130`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180019390`

## callees

- `0x180003a00`
- `0x180005efa`
- `0x1800085dc`
- `0x18000a024`
- `0x180014ed0`
- `0x18001e224`
- `0x1800263ac`
- `0x180027818`
- `0x18002ca28`
- `0x18003f8cc`
- `0x18003fff4`
- `0x1800407dc`
- `0x180040c4c`
- `0x180041ff0`
- `0x18005f26c`
- `0x18005f504`
- `0x18006142c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040bf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040bf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800408e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800408e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040a9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040a9d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180040c12`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180040c12`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1800409ef`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1800409ef`
- `Bcp47Langs!GetUserLanguages` at `0x18004089b`
- `Bcp47Langs!GetUserLanguages` at `0x18004089b`
- `ext-ms-win-resources-languageoverlay-l1-1-1!IsGroupingUserLanguagesNeeded` at `0x180040844`
- `ext-ms-win-resources-languageoverlay-l1-1-1!IsGroupingUserLanguagesNeeded` at `0x180040844`

## string_xrefs

- `0x1800408b3`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\telemetryutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall LogLanguageGroupingState(void *a1)
{
  char v2; // r13
  unsigned int v3; // r12d
  int UserLanguages; // eax
  int v5; // r15d
  __int64 v6; // r8
  __int128 *v7; // rdi
  __int128 *v8; // rsi
  __int64 v9; // rbx
  unsigned __int64 v10; // rdx
  __int64 v11; // rbx
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  __int64 RegValue; // rax
  char *v15; // rcx
  _QWORD *v16; // rax
  _QWORD *v17; // rdi
  signed __int64 v18; // rsi
  char **v19; // r14
  __int64 v20; // rax
  const wchar_t *v21; // rbx
  __int128 *v22; // r15
  _DWORD *v23; // rax
  __int64 v24; // rcx
  const char *v25; // r9
  char v26; // al
  int v27; // [rsp+20h] [rbp-148h]
  _BYTE v28[8]; // [rsp+50h] [rbp-118h] BYREF
  unsigned __int64 UserSidHash; // [rsp+58h] [rbp-110h]
  char *StringRawBuffer; // [rsp+60h] [rbp-108h] BYREF
  __int64 v31; // [rsp+68h] [rbp-100h]
  char *v32[4]; // [rsp+90h] [rbp-D8h] BYREF
  int v33; // [rsp+B0h] [rbp-B8h] BYREF
  UINT32 length[2]; // [rsp+B8h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+C0h] [rbp-A8h] BYREF
  __int128 v36; // [rsp+C8h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+D8h] [rbp-90h]
  __int128 v38; // [rsp+E0h] [rbp-88h] BYREF
  __m128i si128; // [rsp+F0h] [rbp-78h]
  void **v40[3]; // [rsp+100h] [rbp-68h] BYREF
  char *v41[4]; // [rsp+118h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v2 = 0;
  length[0] = 0;
  try
  {
    raii::ImpersonateLoggedOnUser(v28, a1);
    UserSidHash = GetUserSidHash(a1);
    v33 = 0;
    if ( (int)IsGroupingUserLanguagesNeeded(&v33) < 0 )
      v3 = 2;
    else
      v3 = v33 != 0;
    string = 0;
    v36 = 0;
    v37 = 0;
    WindowsDeleteString(0);
    string = 0;
    UserLanguages = GetUserLanguages(0, &string);
    v5 = UserLanguages;
    if ( UserLanguages >= 0 )
    {
      length[0] = 0;
      StringRawBuffer = (char *)WindowsGetStringRawBuffer(string, length);
      v31 = length[0] + 1;
      v9 = _MultiStringToBcp47Tags(v32, &StringRawBuffer);
      if ( &v36 == (__int128 *)v9 )
      {
        v7 = 0;
        v8 = 0;
      }
      else
      {
        std::vector<std::wstring>::_Tidy(&v36);
        v7 = *(__int128 **)v9;
        *(_QWORD *)&v36 = *(_QWORD *)v9;
        v8 = *(__int128 **)(v9 + 8);
        *((_QWORD *)&v36 + 1) = v8;
        v37 = *(_QWORD *)(v9 + 16);
        *(_QWORD *)v9 = 0;
        *(_QWORD *)(v9 + 8) = 0;
        *(_QWORD *)(v9 + 16) = 0;
      }
      std::vector<std::wstring>::_Tidy(v32);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x198,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\telemetryutils.cpp",
        (const char *)(unsigned int)UserLanguages,
        v27);
      v7 = 0;
      v8 = 0;
    }
    v38 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v38) = 0;
    if ( v7 != v8 && &v38 != v7 )
    {
      v10 = *((_QWORD *)v7 + 2);
      if ( *((_QWORD *)v7 + 3) > 7u )
        v7 = *(__int128 **)v7;
      if ( v10 > 7 )
      {
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::_Reallocate_for<_lambda_64cb28863fdb0756aa96a14b5cb38494_,unsigned short const *>(
          &v38,
          v10,
          v6,
          v7);
      }
      else
      {
        si128.m128i_i64[0] = v10;
        v11 = 2 * v10;
        memmove_0(&v38, v7, 2 * v10);
        *(_WORD *)((char *)&v38 + v11) = 0;
      }
    }
    GetUserDefaultUILanguage();
    v12 = (_QWORD *)bcp47::TryConvertLcidToMuiForm(&StringRawBuffer);
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(
      v41,
      v12);
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(&StringRawBuffer);
    v13 = (_QWORD *)OpenCurrentUserRegKey(length);
    RegValue = GetRegValue(v32, *v13, L"Control Panel\\Desktop", L"PreferredUILanguages");
    if ( *(_QWORD *)(RegValue + 24) <= 7u )
      v15 = (char *)RegValue;
    else
      v15 = *(char **)RegValue;
    StringRawBuffer = v15;
    v31 = *(_QWORD *)(RegValue + 16);
    _MultiStringToBcp47Tags(v40, &StringRawBuffer);
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v32);
    if ( *(_QWORD *)length )
      RegCloseKey(*(HKEY *)length);
    v16 = (_QWORD *)StringSetToCommaDelimitedList<std::vector<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>>(
                      (__int64)&StringRawBuffer,
                      v40);
    v17 = v16;
    if ( v16[3] > 7u )
      v17 = (_QWORD *)*v16;
    v18 = (char *)v40[1] - (char *)v40[0];
    v19 = v41;
    if ( v41[3] > (char *)7 )
      v19 = (char **)v41[0];
    if ( v5 < 0 )
    {
      v21 = L"Unknown";
    }
    else
    {
      v20 = StringSetToCommaDelimitedList<std::vector<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>>(
              (__int64)v32,
              (void ***)&v36);
      v21 = (const wchar_t *)v20;
      v2 = 1;
      if ( *(_QWORD *)(v20 + 24) > 7u )
        v21 = *(const wchar_t **)v20;
    }
    v22 = &v38;
    if ( si128.m128i_i64[1] > 7uLL )
      v22 = (__int128 *)v38;
    v23 = (_DWORD *)*((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
    if ( v23 && *v23 )
    {
      LanguageOverlayTraceProvider::Instance();
      LanguageOverlayTraceProvider::LogLanguageGroupingStateEvent_(
        v24,
        UserSidHash,
        v3,
        v22,
        (__int64)(*((_QWORD *)&v36 + 1) - v36) >> 5,
        v21,
        v19,
        v18 >> 5,
        v17);
    }
    if ( (v2 & 1) != 0 )
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v32);
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(&StringRawBuffer);
    std::vector<std::wstring>::_Tidy(v40);
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v41);
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)&v38);
    std::vector<std::wstring>::_Tidy(&v36);
    WindowsDeleteString(string);
    string = 0;
    v26 = v28[0];
    v28[0] = 0;
    if ( v26 )
      RevertToSelf();
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\telemetryutils.cpp",
      v25);
  }
}

```

## disassembly

```asm
0x1800407dc  mov     [rsp+arg_8], rbx
0x1800407e1  mov     [rsp+arg_10], rsi
0x1800407e6  push    rdi
0x1800407e7  push    r12
0x1800407e9  push    r13
0x1800407eb  push    r14
0x1800407ed  push    r15
0x1800407ef  sub     rsp, 140h
0x1800407f6  mov     rax, cs:__security_cookie
0x1800407fd  xor     rax, rsp
0x180040800  mov     [rsp+168h+var_30], rax
0x180040808  mov     rbx, rcx
0x18004080b  xor     r14d, r14d
0x18004080e  mov     r13d, r14d
0x180040811  mov     [rsp+168h+length], r14d
0x180040819  mov     rdx, rcx
0x18004081c  lea     rcx, [rsp+168h+var_118]
0x180040821  call    ?ImpersonateLoggedOnUser@raii@@YA?AV?$unique_call@P6AHXZ$1?RevertToSelf@@YAHXZ$00@wil@@PEAX@Z; raii::ImpersonateLoggedOnUser(void *)
0x180040826  nop
0x180040827  mov     rcx, rbx; void *
0x18004082a  call    ?GetUserSidHash@@YA_KPEAX@Z; GetUserSidHash(void *)
0x18004082f  mov     [rsp+168h+var_110], rax
0x180040834  mov     [rsp+168h+var_B8], r14d
0x18004083c  lea     rcx, [rsp+168h+var_B8]
0x180040844  call    cs:__imp_IsGroupingUserLanguagesNeeded
0x18004084a  test    eax, eax
0x18004084c  js      short loc_18004085F
0x18004084e  mov     r12d, r14d
0x180040851  cmp     [rsp+168h+var_B8], r14d
0x180040859  setnz   r12b
0x18004085d  jmp     short loc_180040865
0x18004085f  mov     r12d, 2
0x180040865  mov     [rsp+168h+string], r14
0x18004086d  xorps   xmm0, xmm0
0x180040870  movdqu  [rsp+168h+var_A0], xmm0
0x180040879  mov     [rsp+168h+var_90], r14
0x180040881  xor     ecx, ecx; string
0x180040883  call    cs:__imp_WindowsDeleteString
0x180040889  mov     [rsp+168h+string], r14
0x180040891  xor     ecx, ecx
0x180040893  lea     rdx, [rsp+168h+string]
0x18004089b  call    cs:__imp_GetUserLanguages
0x1800408a1  mov     r15d, eax
0x1800408a4  mov     rcx, [rsp+168h]; this
0x1800408ac  test    eax, eax
0x1800408ae  jns     short loc_1800408CF
0x1800408b0  mov     r9d, eax; char *
0x1800408b3  lea     r8, aOnecoreBaseLan_15; "onecore\\base\\languageoverlay\\service"...
0x1800408ba  mov     edx, 198h; void *
0x1800408bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800408c4  mov     rdi, r14
0x1800408c7  mov     rsi, r14
0x1800408ca  jmp     loc_180040972
0x1800408cf  mov     [rsp+168h+length], r14d
0x1800408d7  lea     rdx, [rsp+168h+length]; length
0x1800408df  mov     rcx, [rsp+168h+string]; string
0x1800408e7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800408ed  mov     [rsp+168h+var_108], rax
0x1800408f2  mov     ecx, [rsp+168h+length]
0x1800408f9  inc     ecx
0x1800408fb  mov     [rsp+168h+var_100], rcx
0x180040900  lea     rdx, [rsp+168h+var_108]
0x180040905  lea     rcx, [rsp+168h+var_D8]
0x18004090d  call    ?_MultiStringToBcp47Tags@@YA?AV?$vector@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; _MultiStringToBcp47Tags(std::basic_string_view<ushort>)
0x180040912  mov     rbx, rax
0x180040915  lea     rax, [rsp+168h+var_A0]
0x18004091d  cmp     rax, rbx
0x180040920  jz      short loc_18004095F
0x180040922  lea     rcx, [rsp+168h+var_A0]
0x18004092a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004092f  mov     rdi, [rbx]
0x180040932  mov     qword ptr [rsp+168h+var_A0], rdi
0x18004093a  mov     rsi, [rbx+8]
0x18004093e  mov     qword ptr [rsp+168h+var_A0+8], rsi
0x180040946  mov     rax, [rbx+10h]
0x18004094a  mov     [rsp+168h+var_90], rax
0x180040952  mov     [rbx], r14
0x180040955  mov     [rbx+8], r14
0x180040959  mov     [rbx+10h], r14
0x18004095d  jmp     short loc_180040965
0x18004095f  mov     rdi, r14
0x180040962  mov     rsi, r14
0x180040965  lea     rcx, [rsp+168h+var_D8]
0x18004096d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180040972  xorps   xmm0, xmm0
0x180040975  movups  [rsp+168h+var_88], xmm0
0x18004097d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180040985  movdqu  [rsp+168h+var_78], xmm1
0x18004098e  mov     word ptr [rsp+168h+var_88], r14w
0x180040997  cmp     rdi, rsi
0x18004099a  jz      short loc_1800409EF
0x18004099c  lea     rax, [rsp+168h+var_88]
0x1800409a4  cmp     rax, rdi
0x1800409a7  jz      short loc_1800409EF
0x1800409a9  mov     rdx, [rdi+10h]
0x1800409ad  cmp     qword ptr [rdi+18h], 7
0x1800409b2  jbe     short loc_1800409B7
0x1800409b4  mov     rdi, [rdi]
0x1800409b7  lea     rcx, [rsp+168h+var_88]; void *
0x1800409bf  cmp     rdx, 7
0x1800409c3  ja      short loc_1800409E7
0x1800409c5  mov     qword ptr [rsp+168h+var_78], rdx
0x1800409cd  lea     rbx, [rdx+rdx]
0x1800409d1  mov     r8, rbx; Size
0x1800409d4  mov     rdx, rdi; Src
0x1800409d7  call    memmove_0
0x1800409dc  mov     word ptr [rsp+rbx+168h+var_88], r14w
0x1800409e5  jmp     short loc_1800409EF
0x1800409e7  mov     r9, rdi
0x1800409ea  call    ??$_Reallocate_for@V_lambda_64cb28863fdb0756aa96a14b5cb38494_@@PEBG@?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@AEAAAEAV01@_KV_lambda_64cb28863fdb0756aa96a14b5cb38494_@@PEBG@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::_Reallocate_for<_lambda_64cb28863fdb0756aa96a14b5cb38494_,ushort const *>(unsigned __int64,_lambda_64cb28863fdb0756aa96a14b5cb38494_,ushort const *)
0x1800409ef  call    cs:__imp_GetUserDefaultUILanguage
0x1800409f5  movzx   edx, ax
0x1800409f8  lea     rcx, [rsp+168h+var_108]; void *
0x1800409fd  call    ?TryConvertLcidToMuiForm@bcp47@@YA?AU?$pair@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@_N@std@@K@Z; bcp47::TryConvertLcidToMuiForm(ulong)
0x180040a02  mov     rdx, rax
0x180040a05  lea     rcx, [rsp+168h+var_50]
0x180040a0d  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@$$QEAV01@@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> &&)
0x180040a12  nop
0x180040a13  lea     rcx, [rsp+168h+var_108]; void *
0x180040a18  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180040a1d  lea     rcx, [rsp+168h+length]
0x180040a25  call    ?OpenCurrentUserRegKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; OpenCurrentUserRegKey(ulong)
0x180040a2a  nop
0x180040a2b  mov     dword ptr [rsp+168h+var_148], 20h ; ' '
0x180040a33  lea     r9, aPreferreduilan; "PreferredUILanguages"
0x180040a3a  lea     r8, aControlPanelDe; "Control Panel\\Desktop"
0x180040a41  mov     rdx, [rax]
0x180040a44  lea     rcx, [rsp+168h+var_D8]
0x180040a4c  call    ?GetRegValue@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1K@Z; GetRegValue(HKEY__ *,ushort const *,ushort const *,ulong)
0x180040a51  nop
0x180040a52  cmp     qword ptr [rax+18h], 7
0x180040a57  jbe     short loc_180040A5E
0x180040a59  mov     rcx, [rax]
0x180040a5c  jmp     short loc_180040A61
0x180040a5e  mov     rcx, rax
0x180040a61  mov     [rsp+168h+var_108], rcx
0x180040a66  mov     rax, [rax+10h]
0x180040a6a  mov     [rsp+168h+var_100], rax
0x180040a6f  lea     rdx, [rsp+168h+var_108]
0x180040a74  lea     rcx, [rsp+168h+var_68]
0x180040a7c  call    ?_MultiStringToBcp47Tags@@YA?AV?$vector@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; _MultiStringToBcp47Tags(std::basic_string_view<ushort>)
0x180040a81  nop
0x180040a82  lea     rcx, [rsp+168h+var_D8]; void *
0x180040a8a  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180040a8f  nop
0x180040a90  mov     rcx, qword ptr [rsp+168h+length]; hKey
0x180040a98  test    rcx, rcx
0x180040a9b  jz      short loc_180040AA3
0x180040a9d  call    cs:__imp_RegCloseKey
0x180040aa3  lea     rdx, [rsp+168h+var_68]
0x180040aab  lea     rcx, [rsp+168h+var_108]
0x180040ab0  call    ??$StringSetToCommaDelimitedList@V?$vector@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@1@@Z; StringSetToCommaDelimitedList<std::vector<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>>(std::vector<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>> const &)
0x180040ab5  mov     rdi, rax
0x180040ab8  cmp     qword ptr [rax+18h], 7
0x180040abd  jbe     short loc_180040AC2
0x180040abf  mov     rdi, [rax]
0x180040ac2  mov     rsi, [rsp+168h+var_60]
0x180040aca  sub     rsi, [rsp+168h+var_68]
0x180040ad2  lea     r14, [rsp+168h+var_50]
0x180040ada  cmp     [rsp+168h+var_38], 7
0x180040ae3  cmova   r14, [rsp+168h+var_50]
0x180040aec  test    r15d, r15d
0x180040aef  js      short loc_180040B1B
0x180040af1  lea     rdx, [rsp+168h+var_A0]
0x180040af9  lea     rcx, [rsp+168h+var_D8]
0x180040b01  call    ??$StringSetToCommaDelimitedList@V?$vector@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@1@@Z; StringSetToCommaDelimitedList<std::vector<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>>(std::vector<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>> const &)
0x180040b06  mov     rbx, rax
0x180040b09  mov     r13d, 1
0x180040b0f  cmp     qword ptr [rax+18h], 7
0x180040b14  jbe     short loc_180040B22
0x180040b16  mov     rbx, [rax]
0x180040b19  jmp     short loc_180040B22
0x180040b1b  lea     rbx, aUnknown; "Unknown"
0x180040b22  lea     r15, [rsp+168h+var_88]
0x180040b2a  cmp     qword ptr [rsp+168h+var_78+8], 7
0x180040b33  cmova   r15, qword ptr [rsp+168h+var_88]
0x180040b3c  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180040b41  mov     rax, [rax+8]
0x180040b45  test    rax, rax
0x180040b48  jz      short loc_180040B96
0x180040b4a  mov     eax, [rax]
0x180040b4c  test    eax, eax
0x180040b4e  jz      short loc_180040B96
0x180040b50  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180040b55  sar     rsi, 5
0x180040b59  mov     rax, qword ptr [rsp+168h+var_A0+8]
0x180040b61  sub     rax, qword ptr [rsp+168h+var_A0]
0x180040b69  sar     rax, 5
0x180040b6d  mov     [rsp+168h+var_128], rdi
0x180040b72  mov     [rsp+168h+var_130], rsi
0x180040b77  mov     [rsp+168h+var_138], r14
0x180040b7c  mov     [rsp+168h+var_140], rbx
0x180040b81  mov     [rsp+168h+var_148], rax
0x180040b86  mov     r9, r15
0x180040b89  mov     r8d, r12d
0x180040b8c  mov     rdx, [rsp+168h+var_110]
0x180040b91  call    ?LogLanguageGroupingStateEvent_@LanguageOverlayTraceProvider@@QEAAX_KW4UserPreferredLanguageListState@@PEBG02202@Z; LanguageOverlayTraceProvider::LogLanguageGroupingStateEvent_(unsigned __int64,UserPreferredLanguageListState,ushort const *,unsigned __int64,ushort const *,ushort const *,unsigned __int64,ushort const *)
0x180040b96  test    r13b, 1
0x180040b9a  jz      short loc_180040BA9
0x180040b9c  lea     rcx, [rsp+168h+var_D8]; void *
0x180040ba4  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180040ba9  lea     rcx, [rsp+168h+var_108]; void *
0x180040bae  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180040bb3  lea     rcx, [rsp+168h+var_68]
0x180040bbb  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180040bc0  nop
0x180040bc1  lea     rcx, [rsp+168h+var_50]; void *
0x180040bc9  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180040bce  nop
0x180040bcf  lea     rcx, [rsp+168h+var_88]; void *
0x180040bd7  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180040bdc  nop
0x180040bdd  lea     rcx, [rsp+168h+var_A0]
0x180040be5  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180040bea  nop
0x180040beb  mov     rcx, [rsp+168h+string]; string
0x180040bf3  call    cs:__imp_WindowsDeleteString
0x180040bf9  mov     [rsp+168h+string], 0
0x180040c05  mov     al, [rsp+168h+var_118]
0x180040c09  mov     [rsp+168h+var_118], 0
0x180040c0e  test    al, al
0x180040c10  jz      short loc_180040C19
0x180040c12  call    cs:__imp_RevertToSelf
0x180040c18  nop
0x180040c19  mov     rcx, [rsp+168h+var_30]
0x180040c21  xor     rcx, rsp; StackCookie
0x180040c24  call    __security_check_cookie
0x180040c29  lea     r11, [rsp+168h+var_28]
0x180040c31  mov     rbx, [r11+38h]
0x180040c35  mov     rsi, [r11+40h]
0x180040c39  mov     rsp, r11
0x180040c3c  pop     r15
0x180040c3e  pop     r14
0x180040c40  pop     r13
0x180040c42  pop     r12
0x180040c44  pop     rdi
0x180040c45  retn
```
