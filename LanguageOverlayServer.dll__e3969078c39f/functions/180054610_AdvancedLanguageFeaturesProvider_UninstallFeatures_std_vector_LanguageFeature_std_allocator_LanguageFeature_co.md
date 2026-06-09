# AdvancedLanguageFeaturesProvider::UninstallFeatures(std::vector<LanguageFeature,std::allocator<LanguageFeature>> const &)

- ea: `0x180054610`
- end: `0x18005501b`
- name: `?UninstallFeatures@AdvancedLanguageFeaturesProvider@@UEAAJAEBV?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@@Z`
- size: `2571`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180003a00`
- `0x180009084`
- `0x180014ed0`
- `0x18001e2a4`
- `0x180034b30`
- `0x18003771c`
- `0x18004b0bc`
- `0x180054610`
- `0x18005515c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054b8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054bdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054d11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054e34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054f1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054b8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054bdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054d11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054e34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054f1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800546e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800546e2`

## string_xrefs

- `0x180054710`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x1800547ca`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x18005486b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x18005491e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x1800549e1`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180054ab5`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180054bc1`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180054cd5`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180054df8`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18 #try_helpers=1
__int64 __fastcall AdvancedLanguageFeaturesProvider::UninstallFeatures(__int64 a1, __int64 *a2)
{
  __int64 v3; // rsi
  __int64 v4; // r14
  __m128i si128; // xmm6
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  int v9; // eax
  unsigned int v10; // r8d
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, PVOID, __int64 *); // rbx
  const WCHAR *v15; // rdx
  HSTRING_HEADER *v16; // rax
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  const WCHAR *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // rcx
  const WCHAR *v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, HSTRING *); // rbx
  int v41; // eax
  __int64 v42; // rcx
  const WCHAR *v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  int v47; // eax
  __int64 v48; // rcx
  __int64 v49; // rcx
  const WCHAR *v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  int v54; // eax
  __int64 v55; // rcx
  __int64 v56; // rcx
  const WCHAR *v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  const WCHAR *v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  int v68; // [rsp+20h] [rbp-F8h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-E8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-D0h] BYREF
  _BYTE v71[8]; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v72; // [rsp+58h] [rbp-C0h] BYREF
  __int64 v73; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v74; // [rsp+68h] [rbp-B0h] BYREF
  const WCHAR *v75; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v76; // [rsp+78h] [rbp-A0h] BYREF
  HSTRING v77; // [rsp+80h] [rbp-98h] BYREF
  __int64 v78; // [rsp+88h] [rbp-90h] BYREF
  __int128 v79; // [rsp+90h] [rbp-88h] BYREF
  __m128i v80; // [rsp+A0h] [rbp-78h]
  char *v81[4]; // [rsp+B0h] [rbp-68h] BYREF
  int v82; // [rsp+D0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v3 = *a2;
  v4 = a2[1];
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( v3 != v4 )
  {
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(
      (__int64)v81,
      v3);
    v82 = *(_DWORD *)(v3 + 32);
    v79 = 0;
    v80 = si128;
    LOWORD(v79) = 0;
    if ( ((v82 - 512) & 0xFFFFFDFF) == 0
      && (int)AdvancedLanguageFeaturesProvider::_GetPackageFamilyName(a1, (__int64)v81, (void **)&v79) >= 0 )
    {
      v72 = 0;
      string = 0;
      v6 = WindowsCreateStringReference(L"Windows.Management.Deployment.PackageManager", 0x2Cu, &hstringHeader, &string);
      if ( v6 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
        JUMPOUT(0x180055019LL);
      }
      v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
             (__int64)string,
             &v72);
      v11 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x192,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
          (const char *)(unsigned int)v9,
          v68);
        v12 = v72;
        if ( v72 )
        {
          v72 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
LABEL_96:
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)&v79);
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v81);
        return v11;
      }
      v74 = 0;
      v13 = v72;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, PVOID, __int64 *))(*(_QWORD *)v72 + 160LL);
      v15 = (const WCHAR *)&v79;
      if ( v80.m128i_i64[1] > 7uLL )
        v15 = (const WCHAR *)v79;
      v75 = v15;
      v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v75, v10);
      v17 = v14(v13, 0, v16[1].Reserved.Reserved1, &v74);
      v11 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x198,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
          (const char *)(unsigned int)v17,
          v68);
        v18 = v74;
        if ( v74 )
        {
          v74 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        v19 = v72;
        if ( v72 )
        {
          v72 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        goto LABEL_96;
      }
      v73 = 0;
      v71[0] = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v74 + 48LL))(v74, &v73);
      v11 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19C,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
          (const char *)(unsigned int)v20,
          v68);
        v21 = v73;
        if ( v73 )
        {
          v73 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        v22 = v74;
        if ( v74 )
        {
          v74 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        v23 = v72;
        if ( v72 )
        {
          v72 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        goto LABEL_96;
      }
      v24 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v73 + 56LL))(v73, v71);
      v11 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19D,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
          (const char *)(unsigned int)v24,
          v68);
        v25 = v73;
        if ( v73 )
        {
          v73 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
        v26 = v74;
        if ( v74 )
        {
          v74 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        v27 = v72;
        if ( v72 )
        {
          v72 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        goto LABEL_96;
      }
      while ( v71[0] )
      {
        v75 = 0;
        v28 = (*(__int64 (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)v73 + 48LL))(v73, &v75);
        v11 = v28;
        if ( v28 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A1,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
            (const char *)(unsigned int)v28,
            v68);
          v29 = v75;
          if ( v75 )
          {
            v75 = 0;
            (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v29 + 16LL))(v29);
          }
          v30 = v73;
          if ( v73 )
          {
            v73 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          }
          v31 = v74;
          if ( v74 )
          {
            v74 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          }
          v32 = v72;
          if ( v72 )
          {
            v72 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
          }
          goto LABEL_96;
        }
        v76 = 0;
        v33 = (*(__int64 (__fastcall **)(const WCHAR *, __int64 *))(*(_QWORD *)v75 + 48LL))(v75, &v76);
        v11 = v33;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A3,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
            (const char *)(unsigned int)v33,
            v68);
          v34 = v76;
          if ( v76 )
          {
            v76 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          }
          v35 = v75;
          if ( v75 )
          {
            v75 = 0;
            (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v35 + 16LL))(v35);
          }
          v36 = v73;
          if ( v73 )
          {
            v73 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          }
          v37 = v74;
          if ( v74 )
          {
            v74 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
          }
          v38 = v72;
          if ( v72 )
          {
            v72 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
          }
          goto LABEL_96;
        }
        v77 = 0;
        v39 = v76;
        v40 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v76 + 96LL);
        WindowsDeleteString(0);
        v77 = 0;
        v41 = v40(v39, &v77);
        v11 = v41;
        if ( v41 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A6,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
            (const char *)(unsigned int)v41,
            v68);
          WindowsDeleteString(v77);
          v77 = 0;
          v42 = v76;
          if ( v76 )
          {
            v76 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
          }
          v43 = v75;
          if ( v75 )
          {
            v75 = 0;
            (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v43 + 16LL))(v43);
          }
          v44 = v73;
          if ( v73 )
          {
            v73 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          }
          v45 = v74;
          if ( v74 )
          {
            v74 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
          }
          v46 = v72;
          if ( v72 )
          {
            v72 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
          }
          goto LABEL_96;
        }
        v78 = 0;
        v47 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v72 + 64LL))(v72, v77, &v78);
        v11 = v47;
        if ( v47 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AB,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
            (const char *)(unsigned int)v47,
            v68);
          v48 = v78;
          if ( v78 )
          {
            v78 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
          }
          WindowsDeleteString(v77);
          v77 = 0;
          v49 = v76;
          if ( v76 )
          {
            v76 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
          }
          v50 = v75;
          if ( v75 )
          {
            v75 = 0;
            (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v50 + 16LL))(v50);
          }
          v51 = v73;
          if ( v73 )
          {
            v73 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
          }
          v52 = v74;
          if ( v74 )
          {
            v74 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
          }
          v53 = v72;
          if ( v72 )
          {
            v72 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
          }
          goto LABEL_96;
        }
        v54 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v73 + 64LL))(v73, v71);
        v11 = v54;
        if ( v54 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AD,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
            (const char *)(unsigned int)v54,
            v68);
          v55 = v78;
          if ( v78 )
          {
            v78 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
          }
          WindowsDeleteString(v77);
          v77 = 0;
          v56 = v76;
          if ( v76 )
          {
            v76 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
          }
          v57 = v75;
          if ( v75 )
          {
            v75 = 0;
            (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v57 + 16LL))(v57);
          }
          v58 = v73;
          if ( v73 )
          {
            v73 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
          }
          v59 = v74;
          if ( v74 )
          {
            v74 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
          }
          v60 = v72;
          if ( v72 )
          {
            v72 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          }
          goto LABEL_96;
        }
        v62 = v78;
        if ( v78 )
        {
          v78 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
        }
        WindowsDeleteString(v77);
        v77 = 0;
        v63 = v76;
        if ( v76 )
        {
          v76 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
        }
        v64 = v75;
        if ( v75 )
        {
          v75 = 0;
          (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v64 + 16LL))(v64);
        }
      }
      v65 = v73;
      if ( v73 )
      {
        v73 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
      }
      v66 = v74;
      if ( v74 )
      {
        v74 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
      }
      v67 = v72;
      if ( v72 )
      {
        v72 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      }
    }
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)&v79);
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v81);
    v3 += 40;
  }
  return 0;
}

```

## disassembly

```asm
0x180054610  mov     rax, rsp
0x180054613  mov     [rax+18h], rbx
0x180054617  push    rsi
0x180054618  push    rdi
0x180054619  push    r12
0x18005461b  push    r14
0x18005461d  push    r15
0x18005461f  sub     rsp, 0F0h
0x180054626  movaps  xmmword ptr [rax-38h], xmm6
0x18005462a  mov     rax, cs:__security_cookie
0x180054631  xor     rax, rsp
0x180054634  mov     [rsp+118h+var_40], rax
0x18005463c  mov     r15, rcx
0x18005463f  mov     rsi, [rdx]
0x180054642  mov     r14, [rdx+8]
0x180054646  xor     r12d, r12d
0x180054649  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180054651  cmp     rsi, r14
0x180054654  jz      loc_180054FDD
0x18005465a  mov     rdx, rsi
0x18005465d  lea     rcx, [rsp+118h+var_68]
0x180054665  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@AEBV01@@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &)
0x18005466a  mov     ecx, [rsi+20h]
0x18005466d  mov     [rsp+118h+var_48], ecx
0x180054674  xorps   xmm0, xmm0
0x180054677  movups  [rsp+118h+var_88], xmm0
0x18005467f  movdqu  [rsp+118h+var_78], xmm6
0x180054688  mov     word ptr [rsp+118h+var_88], r12w
0x180054691  lea     eax, [rcx-200h]
0x180054697  test    eax, 0FFFFFDFFh
0x18005469c  jnz     loc_180054FB9
0x1800546a2  lea     r8, [rsp+118h+var_88]
0x1800546aa  lea     rdx, [rsp+118h+var_68]
0x1800546b2  mov     rcx, r15
0x1800546b5  call    ?_GetPackageFamilyName@AdvancedLanguageFeaturesProvider@@AEAAJAEBULanguageFeature@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AdvancedLanguageFeaturesProvider::_GetPackageFamilyName(LanguageFeature const &,std::wstring *)
0x1800546ba  test    eax, eax
0x1800546bc  js      loc_180054FB9
0x1800546c2  mov     [rsp+118h+var_C0], r12
0x1800546c7  mov     [rsp+118h+string], r12
0x1800546cc  lea     r9, [rsp+118h+string]; string
0x1800546d1  lea     r8, [rsp+118h+hstringHeader]; hstringHeader
0x1800546d6  mov     edx, 2Ch ; ','; length
0x1800546db  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x1800546e2  call    cs:__imp_WindowsCreateStringReference
0x1800546e8  test    eax, eax
0x1800546ea  js      loc_180055012
0x1800546f0  lea     rdx, [rsp+118h+var_C0]
0x1800546f5  mov     rcx, [rsp+118h+string]
0x1800546fa  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x1800546ff  mov     ebx, eax
0x180054701  test    eax, eax
0x180054703  jns     short loc_180054760
0x180054705  mov     rcx, [rsp+118h]; this
0x18005470d  mov     r9d, eax; char *
0x180054710  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180054717  mov     edx, 192h; void *
0x18005471c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054721  nop
0x180054722  mov     rcx, [rsp+118h+var_C0]
0x180054727  test    rcx, rcx
0x18005472a  jz      short loc_18005473E
0x18005472c  mov     [rsp+118h+var_C0], r12
0x180054731  mov     rax, [rcx]
0x180054734  mov     rax, [rax+10h]
0x180054738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005473d  nop
0x18005473e  lea     rcx, [rsp+118h+var_88]; void *
0x180054746  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18005474b  nop
0x18005474c  lea     rcx, [rsp+118h+var_68]; void *
0x180054754  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180054759  mov     eax, ebx
0x18005475b  jmp     loc_180054FE5
0x180054760  mov     [rsp+118h+var_B0], r12
0x180054765  mov     rdi, [rsp+118h+var_C0]
0x18005476a  mov     rax, [rdi]
0x18005476d  mov     rbx, [rax+0A0h]
0x180054774  lea     rdx, [rsp+118h+var_88]
0x18005477c  cmp     qword ptr [rsp+118h+var_78+8], 7
0x180054785  cmova   rdx, qword ptr [rsp+118h+var_88]
0x18005478e  mov     [rsp+118h+var_A8], rdx
0x180054793  lea     rdx, [rsp+118h+var_A8]
0x180054798  lea     rcx, [rsp+118h+hstringHeader]
0x18005479d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800547a2  nop
0x1800547a3  lea     r9, [rsp+118h+var_B0]
0x1800547a8  mov     r8, [rax+18h]
0x1800547ac  xor     edx, edx
0x1800547ae  mov     rcx, rdi
0x1800547b1  mov     rax, rbx
0x1800547b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800547b9  mov     ebx, eax
0x1800547bb  test    eax, eax
0x1800547bd  jns     short loc_180054836
0x1800547bf  mov     rcx, [rsp+118h]; this
0x1800547c7  mov     r9d, eax; char *
0x1800547ca  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x1800547d1  mov     edx, 198h; void *
0x1800547d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800547db  nop
0x1800547dc  mov     rcx, [rsp+118h+var_B0]
0x1800547e1  test    rcx, rcx
0x1800547e4  jz      short loc_1800547F8
0x1800547e6  mov     [rsp+118h+var_B0], r12
0x1800547eb  mov     rax, [rcx]
0x1800547ee  mov     rax, [rax+10h]
0x1800547f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800547f7  nop
0x1800547f8  mov     rcx, [rsp+118h+var_C0]
0x1800547fd  test    rcx, rcx
0x180054800  jz      short loc_180054814
0x180054802  mov     [rsp+118h+var_C0], r12
0x180054807  mov     rax, [rcx]
0x18005480a  mov     rax, [rax+10h]
0x18005480e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054813  nop
0x180054814  lea     rcx, [rsp+118h+var_88]; void *
0x18005481c  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180054821  nop
0x180054822  lea     rcx, [rsp+118h+var_68]; void *
0x18005482a  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18005482f  mov     eax, ebx
0x180054831  jmp     loc_180054FE5
0x180054836  mov     [rsp+118h+var_B8], r12
0x18005483b  mov     [rsp+118h+var_C8], r12b
0x180054840  mov     rcx, [rsp+118h+var_B0]
0x180054845  mov     rax, [rcx]
0x180054848  lea     rdx, [rsp+118h+var_B8]
0x18005484d  mov     rax, [rax+30h]
0x180054851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054856  mov     ebx, eax
0x180054858  test    eax, eax
0x18005485a  jns     loc_1800548F3
0x180054860  mov     rcx, [rsp+118h]; this
0x180054868  mov     r9d, eax; char *
0x18005486b  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180054872  mov     edx, 19Ch; void *
0x180054877  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005487c  nop
0x18005487d  mov     rcx, [rsp+118h+var_B8]
0x180054882  test    rcx, rcx
0x180054885  jz      short loc_180054899
0x180054887  mov     [rsp+118h+var_B8], r12
0x18005488c  mov     rax, [rcx]
0x18005488f  mov     rax, [rax+10h]
0x180054893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054898  nop
0x180054899  mov     rcx, [rsp+118h+var_B0]
0x18005489e  test    rcx, rcx
0x1800548a1  jz      short loc_1800548B5
0x1800548a3  mov     [rsp+118h+var_B0], r12
0x1800548a8  mov     rax, [rcx]
0x1800548ab  mov     rax, [rax+10h]
0x1800548af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548b4  nop
0x1800548b5  mov     rcx, [rsp+118h+var_C0]
0x1800548ba  test    rcx, rcx
0x1800548bd  jz      short loc_1800548D1
0x1800548bf  mov     [rsp+118h+var_C0], r12
0x1800548c4  mov     rax, [rcx]
0x1800548c7  mov     rax, [rax+10h]
0x1800548cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548d0  nop
0x1800548d1  lea     rcx, [rsp+118h+var_88]; void *
0x1800548d9  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x1800548de  nop
0x1800548df  lea     rcx, [rsp+118h+var_68]; void *
0x1800548e7  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x1800548ec  mov     eax, ebx
0x1800548ee  jmp     loc_180054FE5
0x1800548f3  mov     rcx, [rsp+118h+var_B8]
0x1800548f8  mov     rax, [rcx]
0x1800548fb  lea     rdx, [rsp+118h+var_C8]
0x180054900  mov     rax, [rax+38h]
0x180054904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054909  mov     ebx, eax
0x18005490b  test    eax, eax
0x18005490d  jns     loc_1800549A6
0x180054913  mov     rcx, [rsp+118h]; this
0x18005491b  mov     r9d, eax; char *
0x18005491e  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180054925  mov     edx, 19Dh; void *
0x18005492a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005492f  nop
0x180054930  mov     rcx, [rsp+118h+var_B8]
0x180054935  test    rcx, rcx
0x180054938  jz      short loc_18005494C
0x18005493a  mov     [rsp+118h+var_B8], r12
0x18005493f  mov     rax, [rcx]
0x180054942  mov     rax, [rax+10h]
0x180054946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005494b  nop
0x18005494c  mov     rcx, [rsp+118h+var_B0]
0x180054951  test    rcx, rcx
0x180054954  jz      short loc_180054968
0x180054956  mov     [rsp+118h+var_B0], r12
0x18005495b  mov     rax, [rcx]
0x18005495e  mov     rax, [rax+10h]
0x180054962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054967  nop
0x180054968  mov     rcx, [rsp+118h+var_C0]
0x18005496d  test    rcx, rcx
0x180054970  jz      short loc_180054984
0x180054972  mov     [rsp+118h+var_C0], r12
0x180054977  mov     rax, [rcx]
0x18005497a  mov     rax, [rax+10h]
0x18005497e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054983  nop
0x180054984  lea     rcx, [rsp+118h+var_88]; void *
0x18005498c  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180054991  nop
0x180054992  lea     rcx, [rsp+118h+var_68]; void *
0x18005499a  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18005499f  mov     eax, ebx
0x1800549a1  jmp     loc_180054FE5
0x1800549a6  cmp     [rsp+118h+var_C8], r12b
0x1800549ab  jz      loc_180054F65
0x1800549b1  mov     [rsp+118h+var_A8], r12
0x1800549b6  mov     rcx, [rsp+118h+var_B8]
0x1800549bb  mov     rax, [rcx]
0x1800549be  lea     rdx, [rsp+118h+var_A8]
0x1800549c3  mov     rax, [rax+30h]
0x1800549c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549cc  mov     ebx, eax
0x1800549ce  test    eax, eax
0x1800549d0  jns     loc_180054A85
0x1800549d6  mov     rcx, [rsp+118h]; this
0x1800549de  mov     r9d, eax; char *
0x1800549e1  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x1800549e8  mov     edx, 1A1h; void *
0x1800549ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800549f2  nop
0x1800549f3  mov     rcx, [rsp+118h+var_A8]
0x1800549f8  test    rcx, rcx
0x1800549fb  jz      short loc_180054A0F
0x1800549fd  mov     [rsp+118h+var_A8], r12
0x180054a02  mov     rax, [rcx]
0x180054a05  mov     rax, [rax+10h]
0x180054a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a0e  nop
0x180054a0f  mov     rcx, [rsp+118h+var_B8]
0x180054a14  test    rcx, rcx
0x180054a17  jz      short loc_180054A2B
0x180054a19  mov     [rsp+118h+var_B8], r12
0x180054a1e  mov     rax, [rcx]
0x180054a21  mov     rax, [rax+10h]
0x180054a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a2a  nop
0x180054a2b  mov     rcx, [rsp+118h+var_B0]
0x180054a30  test    rcx, rcx
0x180054a33  jz      short loc_180054A47
0x180054a35  mov     [rsp+118h+var_B0], r12
0x180054a3a  mov     rax, [rcx]
0x180054a3d  mov     rax, [rax+10h]
0x180054a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a46  nop
0x180054a47  mov     rcx, [rsp+118h+var_C0]
0x180054a4c  test    rcx, rcx
0x180054a4f  jz      short loc_180054A63
0x180054a51  mov     [rsp+118h+var_C0], r12
0x180054a56  mov     rax, [rcx]
0x180054a59  mov     rax, [rax+10h]
0x180054a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a62  nop
0x180054a63  lea     rcx, [rsp+118h+var_88]; void *
0x180054a6b  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180054a70  nop
0x180054a71  lea     rcx, [rsp+118h+var_68]; void *
0x180054a79  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180054a7e  mov     eax, ebx
0x180054a80  jmp     loc_180054FE5
0x180054a85  mov     [rsp+118h+var_A0], r12
0x180054a8a  mov     rcx, [rsp+118h+var_A8]
0x180054a8f  mov     rax, [rcx]
0x180054a92  lea     rdx, [rsp+118h+var_A0]
0x180054a97  mov     rax, [rax+30h]
0x180054a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054aa0  mov     ebx, eax
0x180054aa2  test    eax, eax
0x180054aa4  jns     loc_180054B75
0x180054aaa  mov     rcx, [rsp+118h]; this
0x180054ab2  mov     r9d, eax; char *
0x180054ab5  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180054abc  mov     edx, 1A3h; void *
0x180054ac1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054ac6  nop
0x180054ac7  mov     rcx, [rsp+118h+var_A0]
0x180054acc  test    rcx, rcx
0x180054acf  jz      short loc_180054AE3
0x180054ad1  mov     [rsp+118h+var_A0], r12
0x180054ad6  mov     rax, [rcx]
0x180054ad9  mov     rax, [rax+10h]
0x180054add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ae2  nop
0x180054ae3  mov     rcx, [rsp+118h+var_A8]
0x180054ae8  test    rcx, rcx
0x180054aeb  jz      short loc_180054AFF
0x180054aed  mov     [rsp+118h+var_A8], r12
0x180054af2  mov     rax, [rcx]
0x180054af5  mov     rax, [rax+10h]
  ... truncated ...
```
