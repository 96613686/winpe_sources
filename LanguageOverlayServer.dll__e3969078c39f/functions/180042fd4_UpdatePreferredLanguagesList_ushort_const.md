# UpdatePreferredLanguagesList(ushort const *)

- ea: `0x180042fd4`
- end: `0x180043263`
- name: `?UpdatePreferredLanguagesList@@YAJPEBG@Z`
- size: `655`
- prototype: `__int64 __fastcall(wchar_t *S2)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180042460`

## callees

- `0x180003a00`
- `0x180009084`
- `0x1800137bc`
- `0x180014ed0`
- `0x18001a570`
- `0x18001fba4`
- `0x1800263ac`
- `0x18002bcc8`
- `0x180034b30`
- `0x180034e50`
- `0x180039480`
- `0x180042fd4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004300c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004300c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004304e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004304e`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18004317f`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18004317f`
- `WinLangdb!SetUserLanguages` at `0x180043206`
- `WinLangdb!SetUserLanguages` at `0x180043206`
- `WinLangdb!SetUserLanguagesCore` at `0x1800431b1`
- `WinLangdb!SetUserLanguagesCore` at `0x1800431b1`
- `Bcp47Langs!GetUserLanguages` at `0x18004301f`
- `Bcp47Langs!GetUserLanguages` at `0x18004301f`

## string_xrefs

- `0x180043032`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x1800431c2`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UpdatePreferredLanguagesList(wchar_t *S2)
{
  int UserLanguages; // eax
  unsigned int v3; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v5; // r14
  __int64 v6; // r8
  wchar_t *v7; // rdi
  wchar_t *v8; // rbx
  __int64 v9; // rax
  size_t v10; // r8
  const wchar_t *v11; // rcx
  wchar_t *v12; // rdi
  wchar_t *v13; // rsi
  int v14; // r9d
  __int64 v15; // rcx
  bool v16; // zf
  _QWORD *v17; // rax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rax
  int v23; // [rsp+20h] [rbp-49h]
  int v24; // [rsp+20h] [rbp-49h]
  _QWORD *v25; // [rsp+30h] [rbp-39h] BYREF
  int v26[4]; // [rsp+38h] [rbp-31h] BYREF
  __int128 v27; // [rsp+48h] [rbp-21h]
  HSTRING string; // [rsp+58h] [rbp-11h] BYREF
  wchar_t *S1; // [rsp+60h] [rbp-9h] BYREF
  wchar_t *v30; // [rsp+68h] [rbp-1h]
  _QWORD Src[3]; // [rsp+78h] [rbp+Fh] BYREF
  unsigned __int64 v32; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  WindowsDeleteString(0);
  string = 0;
  UserLanguages = GetUserLanguages(59, &string);
  v3 = UserLanguages;
  if ( UserLanguages >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    *(_OWORD *)v26 = 0;
    v27 = 0;
    v5 = -1;
    v6 = -1;
    do
      ++v6;
    while ( StringRawBuffer[v6] );
    std::wstring::_Construct<1,unsigned short const *>(v26, StringRawBuffer, v6);
    WstringContainerFromDelimitedString<std::vector<std::wstring>>(&S1, v26);
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v26);
    v7 = v30;
    v8 = S1;
    if ( S1 != v30 )
    {
      do
      {
        v9 = -1;
        do
          ++v9;
        while ( S2[v9] );
        v10 = *((_QWORD *)v8 + 2);
        if ( *((_QWORD *)v8 + 3) <= 7u )
          v11 = v8;
        else
          v11 = *(const wchar_t **)v8;
        if ( v10 == v9 && (!v10 || !wmemcmp(v11, S2, v10)) )
          break;
        v8 += 16;
      }
      while ( v8 != v7 );
      v12 = v30;
      if ( v8 != v30 )
      {
        v13 = v8 + 16;
        if ( v8 + 16 != v30 )
        {
          do
          {
            std::wstring::operator=(v8, v13);
            v8 += 16;
            v13 += 16;
          }
          while ( v13 != v12 );
          v12 = v30;
        }
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v12 - 16);
        v30 -= 16;
      }
    }
    *(_OWORD *)v26 = 0;
    v27 = 0;
    do
      ++v5;
    while ( S2[v5] );
    std::wstring::_Construct<1,unsigned short const *>(v26, S2, v5);
    std::vector<std::wstring>::insert((unsigned int)&S1, (unsigned int)&v25, (_DWORD)S1, v14, (__int64)v26);
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v26);
    DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(Src);
    v16 = (unsigned __int8)RtlIsMultiUsersInSessionSku(v15) == 0;
    v17 = Src;
    if ( v16 )
    {
      if ( v32 > 7 )
        v17 = (_QWORD *)Src[0];
      v25 = v17;
      v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v26, &v25);
      v19 = SetUserLanguages(59, *(_QWORD *)(v21 + 24));
      v3 = v19;
      if ( v19 < 0 )
      {
        v20 = 200;
        goto LABEL_27;
      }
    }
    else
    {
      if ( v32 > 7 )
        v17 = (_QWORD *)Src[0];
      v25 = v17;
      v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v26, &v25);
      v19 = SetUserLanguagesCore(59, *(_QWORD *)(v18 + 24));
      v3 = v19;
      if ( v19 < 0 )
      {
        v20 = 196;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
          (const char *)(unsigned int)v19,
          v24);
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(Src);
        std::vector<std::wstring>::_Tidy(&S1);
        goto LABEL_33;
      }
    }
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(Src);
    std::vector<std::wstring>::_Tidy(&S1);
    v3 = 0;
    goto LABEL_33;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB6,
    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
    (const char *)(unsigned int)UserLanguages,
    v23);
LABEL_33:
  WindowsDeleteString(string);
  return v3;
}

```

## disassembly

```asm
0x180042fd4  mov     [rsp-8+arg_8], rbx
0x180042fd9  mov     [rsp-8+arg_10], rsi
0x180042fde  push    rbp
0x180042fdf  push    rdi
0x180042fe0  push    r12
0x180042fe2  push    r14
0x180042fe4  push    r15
0x180042fe6  lea     rbp, [rsp-37h]
0x180042feb  sub     rsp, 0A0h
0x180042ff2  mov     rax, cs:__security_cookie
0x180042ff9  xor     rax, rsp
0x180042ffc  mov     [rbp+57h+var_28], rax
0x180043000  mov     r15, rcx
0x180043003  xor     r12d, r12d
0x180043006  mov     [rbp+57h+string], r12
0x18004300a  xor     ecx, ecx; string
0x18004300c  call    cs:__imp_WindowsDeleteString
0x180043012  mov     [rbp+57h+string], r12
0x180043016  lea     ecx, [r12+3Bh]
0x18004301b  lea     rdx, [rbp+57h+string]
0x18004301f  call    cs:__imp_GetUserLanguages
0x180043025  mov     ebx, eax
0x180043027  test    eax, eax
0x180043029  jns     short loc_180043048
0x18004302b  mov     rcx, [rbp+5Fh]; this
0x18004302f  mov     r9d, eax; char *
0x180043032  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180043039  mov     edx, 0B6h; void *
0x18004303e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043043  jmp     loc_18004322F
0x180043048  xor     edx, edx; length
0x18004304a  mov     rcx, [rbp+57h+string]; string
0x18004304e  call    cs:__imp_WindowsGetStringRawBuffer
0x180043054  xorps   xmm0, xmm0
0x180043057  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18004305b  xorps   xmm1, xmm1
0x18004305e  movdqu  [rbp+57h+var_78], xmm1
0x180043063  or      r14, 0FFFFFFFFFFFFFFFFh
0x180043067  mov     r8, r14
0x18004306a  inc     r8
0x18004306d  cmp     [rax+r8*2], r12w
0x180043072  jnz     short loc_18004306A
0x180043074  mov     rdx, rax
0x180043077  lea     rcx, [rbp+57h+var_88]
0x18004307b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180043080  nop
0x180043081  lea     rdx, [rbp+57h+var_88]
0x180043085  lea     rcx, [rbp+57h+S1]
0x180043089  call    ??$WstringContainerFromDelimitedString@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@G@Z; WstringContainerFromDelimitedString<std::vector<std::wstring>>(std::wstring const &,ushort)
0x18004308e  nop
0x18004308f  lea     rcx, [rbp+57h+var_88]; void *
0x180043093  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180043098  nop
0x180043099  mov     rdi, [rbp+57h+var_58]
0x18004309d  mov     rbx, [rbp+57h+S1]
0x1800430a1  cmp     rbx, rdi
0x1800430a4  jz      short loc_180043121
0x1800430a6  mov     rax, r14
0x1800430a9  inc     rax
0x1800430ac  cmp     [r15+rax*2], r12w
0x1800430b1  jnz     short loc_1800430A9
0x1800430b3  mov     r8, [rbx+10h]; N
0x1800430b7  cmp     qword ptr [rbx+18h], 7
0x1800430bc  jbe     short loc_1800430C3
0x1800430be  mov     rcx, [rbx]
0x1800430c1  jmp     short loc_1800430C6
0x1800430c3  mov     rcx, rbx; S1
0x1800430c6  cmp     r8, rax
0x1800430c9  jnz     short loc_1800430DC
0x1800430cb  test    r8, r8
0x1800430ce  jz      short loc_1800430E5
0x1800430d0  mov     rdx, r15; S2
0x1800430d3  call    wmemcmp
0x1800430d8  test    eax, eax
0x1800430da  jz      short loc_1800430E5
0x1800430dc  add     rbx, 20h ; ' '
0x1800430e0  cmp     rbx, rdi
0x1800430e3  jnz     short loc_1800430A6
0x1800430e5  mov     rdi, [rbp+57h+var_58]
0x1800430e9  cmp     rbx, rdi
0x1800430ec  jz      short loc_180043121
0x1800430ee  lea     rsi, [rbx+20h]
0x1800430f2  cmp     rsi, rdi
0x1800430f5  jz      short loc_180043113
0x1800430f7  mov     rdx, rsi
0x1800430fa  mov     rcx, rbx
0x1800430fd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180043102  add     rbx, 20h ; ' '
0x180043106  add     rsi, 20h ; ' '
0x18004310a  cmp     rsi, rdi
0x18004310d  jnz     short loc_1800430F7
0x18004310f  mov     rdi, [rbp+57h+var_58]
0x180043113  lea     rcx, [rdi-20h]; void *
0x180043117  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18004311c  sub     [rbp+57h+var_58], 20h ; ' '
0x180043121  xorps   xmm0, xmm0
0x180043124  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x180043128  xorps   xmm1, xmm1
0x18004312b  movdqu  [rbp+57h+var_78], xmm1
0x180043130  inc     r14
0x180043133  cmp     [r15+r14*2], r12w
0x180043138  jnz     short loc_180043130
0x18004313a  mov     r8, r14
0x18004313d  mov     rdx, r15
0x180043140  lea     rcx, [rbp+57h+var_88]
0x180043144  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180043149  nop
0x18004314a  lea     rax, [rbp+57h+var_88]
0x18004314e  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180043153  mov     r8, [rbp+57h+S1]
0x180043157  lea     rdx, [rbp+57h+var_90]
0x18004315b  lea     rcx, [rbp+57h+S1]
0x18004315f  call    ?insert@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,unsigned __int64,std::wstring const &)
0x180043164  nop
0x180043165  lea     rcx, [rbp+57h+var_88]; void *
0x180043169  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18004316e  mov     r8, [rbp+57h+var_58]
0x180043172  mov     rdx, [rbp+57h+S1]
0x180043176  lea     rcx, [rbp+57h+Src]; Src
0x18004317a  call    ??$DelimitedStringFromItems@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@0G@Z; DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,ushort)
0x18004317f  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x180043185  lea     rdx, [rbp+57h+var_90]
0x180043189  lea     rcx, [rbp+57h+var_88]
0x18004318d  test    al, al
0x18004318f  lea     rax, [rbp+57h+Src]
0x180043193  jz      short loc_1800431EA
0x180043195  cmp     [rbp+57h+var_30], 7
0x18004319a  cmova   rax, [rbp+57h+Src]
0x18004319f  mov     [rbp+57h+var_90], rax
0x1800431a3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800431a8  mov     ecx, 3Bh ; ';'
0x1800431ad  mov     rdx, [rax+18h]
0x1800431b1  call    cs:__imp_SetUserLanguagesCore
0x1800431b7  mov     ebx, eax
0x1800431b9  test    eax, eax
0x1800431bb  jns     short loc_180043219
0x1800431bd  mov     edx, 0C4h; void *
0x1800431c2  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x1800431c9  mov     r9d, eax; char *
0x1800431cc  mov     rcx, [rbp+5Fh]; this
0x1800431d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800431d5  lea     rcx, [rbp+57h+Src]; void *
0x1800431d9  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x1800431de  nop
0x1800431df  lea     rcx, [rbp+57h+S1]
0x1800431e3  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800431e8  jmp     short loc_18004322F
0x1800431ea  cmp     [rbp+57h+var_30], 7
0x1800431ef  cmova   rax, [rbp+57h+Src]
0x1800431f4  mov     [rbp+57h+var_90], rax
0x1800431f8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800431fd  mov     ecx, 3Bh ; ';'
0x180043202  mov     rdx, [rax+18h]
0x180043206  call    cs:__imp_SetUserLanguages
0x18004320c  mov     ebx, eax
0x18004320e  test    eax, eax
0x180043210  jns     short loc_180043219
0x180043212  mov     edx, 0C8h
0x180043217  jmp     short loc_1800431C2
0x180043219  lea     rcx, [rbp+57h+Src]; void *
0x18004321d  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180043222  nop
0x180043223  lea     rcx, [rbp+57h+S1]
0x180043227  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004322c  mov     ebx, r12d
0x18004322f  mov     rcx, [rbp+57h+string]; string
0x180043233  call    cs:__imp_WindowsDeleteString
0x180043239  mov     eax, ebx
0x18004323b  mov     rcx, [rbp+57h+var_28]
0x18004323f  xor     rcx, rsp; StackCookie
0x180043242  call    __security_check_cookie
0x180043247  lea     r11, [rsp+0C0h+var_20]
0x18004324f  mov     rbx, [r11+38h]
0x180043253  mov     rsi, [r11+40h]
0x180043257  mov     rsp, r11
0x18004325a  pop     r15
0x18004325c  pop     r14
0x18004325e  pop     r12
0x180043260  pop     rdi
0x180043261  pop     rbp
0x180043262  retn
```
