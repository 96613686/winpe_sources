# wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::WiFi::WiFiProfile>(Windows::Foundation::Collections::IVectorView<Windows::Internal::Storage::Cloud::CloudStoreItemName *> *)

- ea: `0x180008cb0`
- end: `0x1800091d7`
- name: `??$make_cloud_store_reference_vector@UWiFiProfile@WiFi@Data@Windows@@@cloud_store@wil@@CA?AV?$vector@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@PEAU?$IVectorView@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `1319`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800179f4`

## callees

- `0x180006afc`
- `0x180006cd0`
- `0x180008cb0`
- `0x1800097f4`
- `0x18000a2e8`
- `0x180025308`
- `0x1800277c0`
- `0x180028b1c`
- `0x18002a030`
- `0x18002e2d0`
- `0x18002f1ac`
- `0x18003b6f8`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000910c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000912a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000914a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000910c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000912a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000914a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009137`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008e36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008f8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008fbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008e36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008f8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008fbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000902c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800090bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800090c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009142`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000902c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800090bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800090c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009142`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008e53`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008e53`

## pseudocode

```c
_QWORD *__fastcall wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::WiFi::WiFiProfile>(
        _QWORD *a1,
        __int64 *a2)
{
  int v4; // eax
  _QWORD *v5; // rcx
  unsigned int v6; // edx
  unsigned int v7; // r12d
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
  PCWSTR v28; // rax
  __int64 v29; // r8
  PCWSTR v30; // rax
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rcx
  DWORD LastError; // ebx
  DWORD v36; // ebx
  DWORD v37; // ebx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-B9h]
  HSTRING v39; // [rsp+38h] [rbp-A1h] BYREF
  char v40; // [rsp+40h] [rbp-99h]
  unsigned int v41; // [rsp+48h] [rbp-91h] BYREF
  HSTRING v42; // [rsp+50h] [rbp-89h]
  HSTRING string; // [rsp+58h] [rbp-81h] BYREF
  int v44; // [rsp+60h] [rbp-79h]
  HSTRING v45; // [rsp+68h] [rbp-71h]
  HSTRING v46; // [rsp+70h] [rbp-69h]
  HSTRING v47; // [rsp+78h] [rbp-61h]
  _QWORD *v48; // [rsp+80h] [rbp-59h]
  LPCWCH lpString2[3]; // [rsp+88h] [rbp-51h] BYREF
  unsigned __int64 v50; // [rsp+A0h] [rbp-39h]
  _BYTE v51[32]; // [rsp+B0h] [rbp-29h] BYREF
  _BYTE v52[32]; // [rsp+D0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v48 = a1;
  v44 = 0;
  wil::cloud_store::get_type_name_wide_string<Windows::Data::WiFi::WiFiProfile>(lpString2);
  v41 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*a2 + 56))(a2, &v41);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55E,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v4,
      bIgnoreCase);
  std::vector<bond::blob>::vector<bond::blob>(a1);
  v44 = 1;
  v6 = v41;
  string = (HSTRING)v41;
  if ( v41 > (unsigned __int64)((__int64)(a1[2] - *a1) >> 6) )
  {
    std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>::_Reallocate<0>(v5, &string);
    v6 = v41;
  }
  v7 = 0;
  if ( v6 )
  {
    do
    {
      v42 = 0;
      v8 = *a2;
      v39 = 0;
      v40 = 1;
      v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING *))(v8 + 48))(a2, v7, &v39);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x565,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
          (const char *)(unsigned int)v9,
          bIgnoreCase);
      if ( v40 )
      {
        v10 = v42;
        v42 = v39;
        if ( v10 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v10 + 16LL))(v10);
      }
      string = 0;
      v11 = *(_QWORD *)v42;
      v39 = 0;
      v40 = 1;
      v12 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(v11 + 64))(v42, &v39);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x568,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
          (const char *)(unsigned int)v12,
          bIgnoreCase);
      if ( v40 )
      {
        v13 = v39;
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
      if ( v50 > 7 )
        v15 = lpString2[0];
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, v15, -1, 1) == 2 )
      {
        v47 = 0;
        v17 = *(_QWORD *)v42;
        v39 = 0;
        v40 = 1;
        v18 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(v17 + 48))(v42, &v39);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x56C,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
            (const char *)(unsigned int)v18,
            bIgnoreCase);
        if ( v40 )
        {
          v19 = v47;
          v47 = v39;
          if ( v19 )
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v19 + 16LL))(v19);
        }
        v46 = 0;
        v20 = *(_QWORD *)v47;
        v39 = 0;
        v40 = 1;
        v21 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(v20 + 48))(v47, &v39);
        if ( v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x56F,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
            (const char *)(unsigned int)v21,
            bIgnoreCase);
        if ( v40 )
        {
          v22 = v39;
          v23 = v46;
          if ( v46 )
          {
            v36 = GetLastError();
            WindowsDeleteString(v23);
            SetLastError(v36);
          }
          v46 = v22;
        }
        v45 = 0;
        v24 = *(_QWORD *)v42;
        v39 = 0;
        v40 = 1;
        v25 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(v24 + 56))(v42, &v39);
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x572,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
            (const char *)(unsigned int)v25,
            bIgnoreCase);
        if ( v40 )
        {
          v26 = v39;
          v27 = v45;
          if ( v45 )
          {
            v37 = GetLastError();
            WindowsDeleteString(v27);
            SetLastError(v37);
          }
          v45 = v26;
        }
        std::wstring::wstring(v51);
        std::wstring::wstring(v52);
        v28 = WindowsGetStringRawBuffer(v45, 0);
        v29 = -1;
        do
          ++v29;
        while ( v28[v29] );
        std::wstring::_Assign<unsigned short>(v51);
        v30 = WindowsGetStringRawBuffer(v46, 0);
        v31 = -1;
        do
          ++v31;
        while ( v30[v31] );
        std::wstring::_Assign<unsigned short>(v52);
        v32 = a1[1];
        if ( v32 == a1[2] )
        {
          std::vector<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>::_Emplace_reallocate<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>(
            a1,
            a1[1],
            v51);
        }
        else
        {
          std::wstring::wstring(v32, v51);
          std::wstring::wstring(v33 + 32, v52);
          a1[1] += 64LL;
        }
        std::wstring::_Tidy_deallocate(v52);
        std::wstring::_Tidy_deallocate(v51);
        if ( v45 )
          WindowsDeleteString(v45);
        if ( v46 )
          WindowsDeleteString(v46);
        if ( v47 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v47 + 16LL))(v47);
      }
      if ( string )
        WindowsDeleteString(string);
      if ( v42 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v42 + 16LL))(v42);
      ++v7;
    }
    while ( v7 < v41 );
  }
  if ( v50 > 7 )
    std::_Deallocate<16>((void *)lpString2[0], 2 * v50 + 2);
  return a1;
}

```

## disassembly

```asm
0x180008cb0  mov     [rsp-8+arg_10], rbx
0x180008cb5  push    rbp
0x180008cb6  push    rsi
0x180008cb7  push    rdi
0x180008cb8  push    r12
0x180008cba  push    r13
0x180008cbc  push    r14
0x180008cbe  push    r15
0x180008cc0  lea     rbp, [rsp-27h]
0x180008cc5  sub     rsp, 100h
0x180008ccc  mov     rax, cs:__security_cookie
0x180008cd3  xor     rax, rsp
0x180008cd6  mov     [rbp+57h+var_40], rax
0x180008cda  mov     r13, rdx
0x180008cdd  mov     r15, rcx
0x180008ce0  mov     [rbp+57h+var_B0], rcx
0x180008ce4  xor     ebx, ebx
0x180008ce6  mov     [rbp+57h+var_D0], ebx
0x180008ce9  lea     rcx, [rbp+57h+lpString2]
0x180008ced  call    ??$get_type_name_wide_string@UWiFiProfile@WiFi@Data@Windows@@@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::cloud_store::get_type_name_wide_string<Windows::Data::WiFi::WiFiProfile>(void)
0x180008cf2  nop
0x180008cf3  mov     [rsp+130h+var_E8], ebx
0x180008cf7  mov     rax, [r13+0]
0x180008cfb  lea     rdx, [rsp+130h+var_E8]
0x180008d00  mov     rcx, r13
0x180008d03  mov     rax, [rax+38h]
0x180008d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d0c  mov     rcx, [rbp+5Fh]; this
0x180008d10  test    eax, eax
0x180008d12  js      loc_1800090E4
0x180008d18  mov     rcx, r15
0x180008d1b  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x180008d20  mov     [rbp+57h+var_D0], 1
0x180008d27  mov     edx, [rsp+130h+var_E8]
0x180008d2b  mov     [rsp+130h+string], rdx
0x180008d30  mov     rax, [r15+10h]
0x180008d34  sub     rax, [r15]
0x180008d37  sar     rax, 6
0x180008d3b  cmp     rdx, rax
0x180008d3e  jbe     short loc_180008D4E
0x180008d40  lea     rdx, [rsp+130h+string]
0x180008d45  call    ??$_Reallocate@$0A@@?$vector@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAXAEA_K@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>::_Reallocate<0>(unsigned __int64 &)
0x180008d4a  mov     edx, [rsp+130h+var_E8]
0x180008d4e  mov     r12d, ebx
0x180008d51  test    edx, edx
0x180008d53  jz      loc_180009085
0x180008d59  nop     dword ptr [rax+00000000h]
0x180008d60  mov     [rsp+130h+var_E0], rbx
0x180008d65  mov     rax, [r13+0]
0x180008d69  lea     rcx, [rsp+130h+var_E0]
0x180008d6e  mov     [rsp+130h+var_100], rcx
0x180008d73  mov     [rsp+130h+var_F8], rbx
0x180008d78  mov     [rsp+130h+var_F0], 1
0x180008d7d  lea     r8, [rsp+130h+var_F8]
0x180008d82  mov     edx, r12d
0x180008d85  mov     rcx, r13
0x180008d88  mov     rax, [rax+30h]
0x180008d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d91  mov     rcx, [rbp+5Fh]; this
0x180008d95  test    eax, eax
0x180008d97  js      loc_1800091AB
0x180008d9d  cmp     [rsp+130h+var_F0], 0
0x180008da2  jz      short loc_180008DC6
0x180008da4  mov     rdx, [rsp+130h+var_F8]
0x180008da9  mov     rax, [rsp+130h+var_100]
0x180008dae  mov     rcx, [rax]
0x180008db1  mov     [rax], rdx
0x180008db4  test    rcx, rcx
0x180008db7  jz      short loc_180008DC6
0x180008db9  mov     rax, [rcx]
0x180008dbc  mov     rax, [rax+10h]
0x180008dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dc5  nop
0x180008dc6  mov     [rsp+130h+string], rbx
0x180008dcb  mov     rcx, [rsp+130h+var_E0]
0x180008dd0  mov     rax, [rcx]
0x180008dd3  lea     rdx, [rsp+130h+string]
0x180008dd8  mov     [rsp+130h+var_100], rdx
0x180008ddd  mov     [rsp+130h+var_F8], rbx
0x180008de2  mov     [rsp+130h+var_F0], 1
0x180008de7  lea     rdx, [rsp+130h+var_F8]
0x180008dec  mov     rax, [rax+40h]
0x180008df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008df5  mov     rcx, [rbp+5Fh]; this
0x180008df9  test    eax, eax
0x180008dfb  js      loc_180009196
0x180008e01  cmp     [rsp+130h+var_F0], 0
0x180008e06  jz      short loc_180008E21
0x180008e08  mov     rsi, [rsp+130h+var_F8]
0x180008e0d  mov     rdi, [rsp+130h+var_100]
0x180008e12  mov     r14, [rdi]
0x180008e15  test    r14, r14
0x180008e18  jnz     loc_1800090F9
0x180008e1e  mov     [rdi], rsi
0x180008e21  lea     rbx, [rbp+57h+lpString2]
0x180008e25  cmp     [rbp+57h+var_90], 7
0x180008e2a  cmova   rbx, [rbp+57h+lpString2]
0x180008e2f  xor     edx, edx; length
0x180008e31  mov     rcx, [rsp+130h+string]; string
0x180008e36  call    cs:__imp_WindowsGetStringRawBuffer
0x180008e3c  mov     [rsp+130h+bIgnoreCase], 1; int
0x180008e44  mov     r9d, 0FFFFFFFFh; cchCount2
0x180008e4a  mov     r8, rbx; lpString2
0x180008e4d  mov     edx, r9d; cchCount1
0x180008e50  mov     rcx, rax; lpString1
0x180008e53  call    cs:__imp_CompareStringOrdinal
0x180008e59  xor     ebx, ebx
0x180008e5b  cmp     eax, 2
0x180008e5e  jnz     loc_180009056
0x180008e64  mov     [rbp+57h+var_B8], rbx
0x180008e68  mov     rcx, [rsp+130h+var_E0]
0x180008e6d  mov     rax, [rcx]
0x180008e70  lea     rdx, [rbp+57h+var_B8]
0x180008e74  mov     [rsp+130h+var_100], rdx
0x180008e79  mov     [rsp+130h+var_F8], rbx
0x180008e7e  mov     [rsp+130h+var_F0], 1
0x180008e83  lea     rdx, [rsp+130h+var_F8]
0x180008e88  mov     rax, [rax+30h]
0x180008e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e91  mov     rcx, [rbp+5Fh]; this
0x180008e95  test    eax, eax
0x180008e97  js      loc_180009181
0x180008e9d  cmp     [rsp+130h+var_F0], bl
0x180008ea1  jz      short loc_180008EC5
0x180008ea3  mov     rdx, [rsp+130h+var_F8]
0x180008ea8  mov     rax, [rsp+130h+var_100]
0x180008ead  mov     rcx, [rax]
0x180008eb0  mov     [rax], rdx
0x180008eb3  test    rcx, rcx
0x180008eb6  jz      short loc_180008EC5
0x180008eb8  mov     rax, [rcx]
0x180008ebb  mov     rax, [rax+10h]
0x180008ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ec4  nop
0x180008ec5  mov     [rbp+57h+var_C0], rbx
0x180008ec9  mov     rcx, [rbp+57h+var_B8]
0x180008ecd  mov     rax, [rcx]
0x180008ed0  lea     rdx, [rbp+57h+var_C0]
0x180008ed4  mov     [rsp+130h+var_100], rdx
0x180008ed9  mov     [rsp+130h+var_F8], rbx
0x180008ede  mov     [rsp+130h+var_F0], 1
0x180008ee3  lea     rdx, [rsp+130h+var_F8]
0x180008ee8  mov     rax, [rax+30h]
0x180008eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef1  mov     rcx, [rbp+5Fh]; this
0x180008ef5  test    eax, eax
0x180008ef7  js      loc_18000916C
0x180008efd  cmp     [rsp+130h+var_F0], 0
0x180008f02  jz      short loc_180008F1D
0x180008f04  mov     rsi, [rsp+130h+var_F8]
0x180008f09  mov     rdi, [rsp+130h+var_100]
0x180008f0e  mov     r14, [rdi]
0x180008f11  test    r14, r14
0x180008f14  jnz     loc_180009117
0x180008f1a  mov     [rdi], rsi
0x180008f1d  mov     [rbp+57h+var_C8], rbx
0x180008f21  mov     rcx, [rsp+130h+var_E0]
0x180008f26  mov     rax, [rcx]
0x180008f29  lea     rdx, [rbp+57h+var_C8]
0x180008f2d  mov     [rsp+130h+var_100], rdx
0x180008f32  mov     [rsp+130h+var_F8], rbx
0x180008f37  mov     [rsp+130h+var_F0], 1
0x180008f3c  lea     rdx, [rsp+130h+var_F8]
0x180008f41  mov     rax, [rax+38h]
0x180008f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f4a  mov     rcx, [rbp+5Fh]; this
0x180008f4e  test    eax, eax
0x180008f50  js      loc_180009157
0x180008f56  cmp     [rsp+130h+var_F0], 0
0x180008f5b  jz      short loc_180008F76
0x180008f5d  mov     rsi, [rsp+130h+var_F8]
0x180008f62  mov     rdi, [rsp+130h+var_100]
0x180008f67  mov     r14, [rdi]
0x180008f6a  test    r14, r14
0x180008f6d  jnz     loc_180009137
0x180008f73  mov     [rdi], rsi
0x180008f76  lea     rcx, [rbp+57h+var_80]
0x180008f7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180008f7f  lea     rcx, [rbp+57h+var_60]
0x180008f83  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180008f88  nop
0x180008f89  xor     edx, edx; length
0x180008f8b  mov     rcx, [rbp+57h+var_C8]; string
0x180008f8f  call    cs:__imp_WindowsGetStringRawBuffer
0x180008f95  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180008f9c  nop     dword ptr [rax+00h]
0x180008fa0  inc     r8
0x180008fa3  cmp     word ptr [rax+r8*2], 0
0x180008fa9  jnz     short loc_180008FA0
0x180008fab  mov     rdx, rax
0x180008fae  lea     rcx, [rbp+57h+var_80]
0x180008fb2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180008fb7  xor     edx, edx; length
0x180008fb9  mov     rcx, [rbp+57h+var_C0]; string
0x180008fbd  call    cs:__imp_WindowsGetStringRawBuffer
0x180008fc3  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180008fca  nop     word ptr [rax+rax+00h]
0x180008fd0  inc     r8
0x180008fd3  cmp     word ptr [rax+r8*2], 0
0x180008fd9  jnz     short loc_180008FD0
0x180008fdb  mov     rdx, rax
0x180008fde  lea     rcx, [rbp+57h+var_60]
0x180008fe2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180008fe7  mov     rcx, [r15+8]
0x180008feb  cmp     rcx, [r15+10h]
0x180008fef  jz      loc_1800090D0
0x180008ff5  lea     rdx, [rbp+57h+var_80]
0x180008ff9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180008ffe  add     rcx, 20h ; ' '
0x180009002  lea     rdx, [rbp+57h+var_60]
0x180009006  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000900b  add     qword ptr [r15+8], 40h ; '@'
0x180009010  lea     rcx, [rbp+57h+var_60]
0x180009014  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009019  lea     rcx, [rbp+57h+var_80]
0x18000901d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009022  nop
0x180009023  mov     rcx, [rbp+57h+var_C8]; string
0x180009027  test    rcx, rcx
0x18000902a  jz      short loc_180009033
0x18000902c  call    cs:__imp_WindowsDeleteString
0x180009032  nop
0x180009033  mov     rcx, [rbp+57h+var_C0]; string
0x180009037  test    rcx, rcx
0x18000903a  jnz     loc_1800090C5
0x180009040  mov     rcx, [rbp+57h+var_B8]
0x180009044  test    rcx, rcx
0x180009047  jz      short loc_180009056
0x180009049  mov     rax, [rcx]
0x18000904c  mov     rax, [rax+10h]
0x180009050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009055  nop
0x180009056  mov     rcx, [rsp+130h+string]; string
0x18000905b  test    rcx, rcx
0x18000905e  jnz     short loc_1800090BD
0x180009060  mov     rcx, [rsp+130h+var_E0]
0x180009065  test    rcx, rcx
0x180009068  jz      short loc_180009077
0x18000906a  mov     rax, [rcx]
0x18000906d  mov     rax, [rax+10h]
0x180009071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009076  nop
0x180009077  inc     r12d
0x18000907a  cmp     r12d, [rsp+130h+var_E8]
0x18000907f  jb      loc_180008D60
0x180009085  mov     rdx, [rbp+57h+var_90]
0x180009089  cmp     rdx, 7
0x18000908d  ja      loc_1800091C0
0x180009093  mov     rax, r15
0x180009096  mov     rcx, [rbp+57h+var_40]
0x18000909a  xor     rcx, rsp; StackCookie
0x18000909d  call    __security_check_cookie
0x1800090a2  mov     rbx, [rsp+130h+arg_10]
0x1800090aa  add     rsp, 100h
0x1800090b1  pop     r15
0x1800090b3  pop     r14
0x1800090b5  pop     r13
0x1800090b7  pop     r12
0x1800090b9  pop     rdi
0x1800090ba  pop     rsi
0x1800090bb  pop     rbp
0x1800090bc  retn
0x1800090bd  call    cs:__imp_WindowsDeleteString
0x1800090c3  jmp     short loc_180009060
0x1800090c5  call    cs:__imp_WindowsDeleteString
0x1800090cb  jmp     loc_180009040
0x1800090d0  lea     r8, [rbp+57h+var_80]
0x1800090d4  mov     rdx, rcx
0x1800090d7  mov     rcx, r15
0x1800090da  call    ??$_Emplace_reallocate@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@@?$vector@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAPEAU?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@QEAU2345@$$QEAU2345@@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>::_Emplace_reallocate<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>(Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> * const,Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> &&)
0x1800090df  jmp     loc_180009010
0x1800090e4  mov     r9d, eax; char *
0x1800090e7  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800090ee  mov     edx, 55Eh; void *
0x1800090f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800090f9  call    cs:__imp_GetLastError
0x1800090ff  mov     ebx, eax
0x180009101  mov     rcx, r14; string
0x180009104  call    cs:__imp_WindowsDeleteString
0x18000910a  mov     ecx, ebx; dwErrCode
0x18000910c  call    cs:__imp_SetLastError
0x180009112  jmp     loc_180008E1E
0x180009117  call    cs:__imp_GetLastError
0x18000911d  mov     ebx, eax
0x18000911f  mov     rcx, r14; string
0x180009122  call    cs:__imp_WindowsDeleteString
0x180009128  mov     ecx, ebx; dwErrCode
0x18000912a  call    cs:__imp_SetLastError
0x180009130  xor     ebx, ebx
0x180009132  jmp     loc_180008F1A
0x180009137  call    cs:__imp_GetLastError
0x18000913d  mov     ebx, eax
0x18000913f  mov     rcx, r14; string
0x180009142  call    cs:__imp_WindowsDeleteString
0x180009148  mov     ecx, ebx; dwErrCode
0x18000914a  call    cs:__imp_SetLastError
0x180009150  xor     ebx, ebx
0x180009152  jmp     loc_180008F73
0x180009157  mov     r9d, eax; char *
0x18000915a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
  ... truncated ...
```
