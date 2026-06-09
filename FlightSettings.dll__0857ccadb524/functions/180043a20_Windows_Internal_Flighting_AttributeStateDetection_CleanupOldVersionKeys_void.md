# Windows::Internal::Flighting::AttributeStateDetection::CleanupOldVersionKeys(void)

- ea: `0x180043a20`
- end: `0x180043d26`
- name: `?CleanupOldVersionKeys@AttributeStateDetection@Flighting@Internal@Windows@@AEAAJXZ`
- size: `774`
- prototype: `__int64 __fastcall(Windows::Internal::Flighting::AttributeStateDetection *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180044da8`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x1800175b4`
- `0x18001c6f4`
- `0x18001cff8`
- `0x18002035c`
- `0x180022718`
- `0x180023fa8`
- `0x1800240a0`
- `0x1800240f0`
- `0x18002bd98`
- `0x18003402c`
- `0x180043a20`
- `0x180046560`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180043b77`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180043b77`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180043c70`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180043c70`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180043b44`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180043bea`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180043b44`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180043bea`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180043abb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180043abb`

## string_xrefs

- `0x180043adb`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x180043c0f`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x180043c94`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`
- `0x180043cfe`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Flighting::AttributeStateDetection::CleanupOldVersionKeys(
        Windows::Internal::Flighting::AttributeStateDetection *this)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  DWORD v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  WCHAR *v8; // rax
  int i; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  const WCHAR *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rax
  WCHAR *v18; // rax
  __int128 j; // rdi
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  bool v23; // sf
  int lpcSubKeys; // [rsp+20h] [rbp-89h]
  int lpcSubKeysa; // [rsp+20h] [rbp-89h]
  DWORD cchName; // [rsp+60h] [rbp-49h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-45h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-41h] BYREF
  __int128 v30; // [rsp+70h] [rbp-39h] BYREF
  __int64 v31; // [rsp+80h] [rbp-29h]
  LPCWSTR lpSubKey[3]; // [rsp+88h] [rbp-21h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-9h] BYREF
  _BYTE v34[16]; // [rsp+A8h] [rbp-1h] BYREF
  DWORD v35; // [rsp+B8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  hKey = 0;
  if ( (int)wil::reg::open_unique_key_nothrow(
              *((HKEY *)this + 33),
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CTAC") < 0 )
    goto LABEL_31;
  v30 = 0;
  v31 = 0;
  cbMaxSubKeyLen = 0;
  v2 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( (v3 & 0x80000000) == 0 )
  {
    if ( cbMaxSubKeyLen )
    {
      std::wstring::wstring(v34, cbMaxSubKeyLen + 1);
      v4 = 0;
      cchName = v35;
      v8 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34, v5, v6, v7);
      for ( i = RegEnumKeyExW(hKey, 0, v8, &cchName, 0, 0, 0, 0);
            i != 259;
            i = RegEnumKeyExW(hKey, v4, v18, &cchName, 0, 0, 0, 0) )
      {
        if ( i )
        {
          if ( i > 0 )
            i = (unsigned __int16)i | 0x80070000;
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2D5,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
            (const char *)(unsigned int)i,
            lpcSubKeysa);
          break;
        }
        v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34, v10, v11, v12);
        if ( CompareStringOrdinal(v13, cchName, *((LPCWCH *)this + 3), -1, 1) != 2 )
        {
          v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34, v14, v15, v16);
          v33 = v17;
          if ( *((_QWORD *)&v30 + 1) == v31 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<unsigned short const *>(&v30, *((_QWORD *)&v30 + 1), &v33);
          }
          else
          {
            std::wstring::wstring(*((_QWORD *)&v30 + 1), v17);
            *((_QWORD *)&v30 + 1) += 32LL;
          }
        }
        ++v4;
        cchName = v35;
        v18 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34, v14, v15, v16);
      }
      for ( j = v30; ; *(_QWORD *)&j = j + 32 )
      {
        if ( (_QWORD)j == *((_QWORD *)&j + 1) )
        {
          std::wstring::_Tidy_deallocate(v34);
          goto LABEL_30;
        }
        memset(lpSubKey, 0, sizeof(lpSubKey));
        v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(j, v10, v11, v12);
        v21 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                lpSubKey,
                L"%s\\%s",
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CTAC",
                v20);
        v3 = v21;
        if ( v21 < 0 )
          break;
        v22 = RegDeleteTreeW(*((HKEY *)this + 33), lpSubKey[0]);
        if ( (v22 & 0xFFFFFFFD) != 0 )
        {
          v23 = v22 < 0;
          if ( v22 > 0 )
          {
            v22 = (unsigned __int16)v22 | 0x80070000;
            v23 = v22 < 0;
          }
          if ( v23 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2EA,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
              (const char *)(unsigned int)v22,
              lpcSubKeysa);
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E4,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
        (const char *)(unsigned int)v21,
        lpcSubKeysa);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
      std::wstring::_Tidy_deallocate(v34);
      goto LABEL_6;
    }
LABEL_30:
    std::vector<std::wstring>::_Tidy(&v30);
LABEL_31:
    v3 = 0;
    goto LABEL_32;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2BE,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
    (const char *)v3,
    lpcSubKeys);
LABEL_6:
  std::vector<std::wstring>::_Tidy(&v30);
LABEL_32:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v3;
}

```

## disassembly

```asm
0x180043a20  push    rbp
0x180043a22  push    rbx
0x180043a23  push    rsi
0x180043a24  push    rdi
0x180043a25  push    r14
0x180043a27  push    r15
0x180043a29  lea     rbp, [rsp-2Fh]
0x180043a2e  sub     rsp, 0D8h
0x180043a35  mov     rax, cs:__security_cookie
0x180043a3c  xor     rax, rsp
0x180043a3f  mov     [rbp+57h+var_38], rax
0x180043a43  mov     r14, rcx
0x180043a46  xor     r15d, r15d
0x180043a49  mov     [rbp+57h+hKey], r15
0x180043a4d  lea     edi, [r15+1]
0x180043a51  mov     r9d, edi
0x180043a54  lea     r8, [rbp+57h+hKey]
0x180043a58  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180043a5f  mov     rcx, [rcx+108h]; hKey
0x180043a66  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180043a6b  test    eax, eax
0x180043a6d  js      loc_180043CCD
0x180043a73  xorps   xmm0, xmm0
0x180043a76  movdqu  [rbp+57h+var_90], xmm0
0x180043a7b  mov     [rbp+57h+var_80], r15
0x180043a7f  mov     [rbp+57h+cbMaxSubKeyLen], r15d
0x180043a83  mov     [rsp+100h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180043a88  mov     [rsp+100h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180043a8d  mov     [rsp+100h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180043a92  mov     [rsp+100h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180043a97  mov     [rsp+100h+lpcValues], r15; lpcValues
0x180043a9c  mov     [rsp+100h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180043aa1  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180043aa5  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180043aaa  mov     [rsp+100h+lpcSubKeys], r15; int
0x180043aaf  xor     r9d, r9d; lpReserved
0x180043ab2  xor     r8d, r8d; lpcchClass
0x180043ab5  xor     edx, edx; lpClass
0x180043ab7  mov     rcx, [rbp+57h+hKey]; hKey
0x180043abb  call    cs:__imp_RegQueryInfoKeyW
0x180043ac1  mov     ebx, eax
0x180043ac3  test    eax, eax
0x180043ac5  jle     short loc_180043AD0
0x180043ac7  movzx   ebx, ax
0x180043aca  or      ebx, 80070000h
0x180043ad0  test    ebx, ebx
0x180043ad2  jns     short loc_180043AFA
0x180043ad4  mov     rcx, [rbp+5Fh]; this
0x180043ad8  mov     r9d, ebx; char *
0x180043adb  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x180043ae2  mov     edx, 2BEh; void *
0x180043ae7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043aec  lea     rcx, [rbp+57h+var_90]
0x180043af0  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180043af5  jmp     loc_180043CD0
0x180043afa  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180043afd  test    eax, eax
0x180043aff  jz      loc_180043CC4
0x180043b05  lea     edx, [rax+1]
0x180043b08  lea     rcx, [rbp+57h+var_58]
0x180043b0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180043b11  mov     ebx, r15d
0x180043b14  mov     eax, [rbp+57h+var_48]
0x180043b17  mov     [rbp+57h+cchName], eax
0x180043b1a  lea     rcx, [rbp+57h+var_58]
0x180043b1e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043b23  mov     r8, rax; lpName
0x180043b26  mov     [rsp+100h+lpcValues], r15; lpftLastWriteTime
0x180043b2b  mov     [rsp+100h+lpcbMaxClassLen], r15; lpcchClass
0x180043b30  mov     [rsp+100h+lpcbMaxSubKeyLen], r15; lpClass
0x180043b35  mov     [rsp+100h+lpcSubKeys], r15; lpReserved
0x180043b3a  lea     r9, [rbp+57h+cchName]; lpcchName
0x180043b3e  xor     edx, edx; dwIndex
0x180043b40  mov     rcx, [rbp+57h+hKey]; hKey
0x180043b44  call    cs:__imp_RegEnumKeyExW
0x180043b4a  mov     esi, 103h
0x180043b4f  jmp     loc_180043BF0
0x180043b54  test    eax, eax
0x180043b56  jnz     loc_180043BFA
0x180043b5c  lea     rcx, [rbp+57h+var_58]
0x180043b60  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043b65  mov     rcx, rax; lpString1
0x180043b68  mov     dword ptr [rsp+100h+lpcSubKeys], edi; bIgnoreCase
0x180043b6c  or      r9d, 0FFFFFFFFh; cchCount2
0x180043b70  mov     r8, [r14+18h]; lpString2
0x180043b74  mov     edx, [rbp+57h+cchName]; cchCount1
0x180043b77  call    cs:__imp_CompareStringOrdinal
0x180043b7d  cmp     eax, 2
0x180043b80  jz      short loc_180043BB8
0x180043b82  lea     rcx, [rbp+57h+var_58]
0x180043b86  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043b8b  mov     [rbp+57h+var_60], rax
0x180043b8f  mov     rcx, qword ptr [rbp+57h+var_90+8]
0x180043b93  cmp     rcx, [rbp+57h+var_80]
0x180043b97  jz      short loc_180043BA8
0x180043b99  mov     rdx, rax
0x180043b9c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043ba1  add     qword ptr [rbp+57h+var_90+8], 20h ; ' '
0x180043ba6  jmp     short loc_180043BB8
0x180043ba8  lea     r8, [rbp+57h+var_60]
0x180043bac  mov     rdx, rcx
0x180043baf  lea     rcx, [rbp+57h+var_90]
0x180043bb3  call    ??$_Emplace_reallocate@PEBG@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAPEBG@Z; std::vector<std::wstring>::_Emplace_reallocate<ushort const *>(std::wstring * const,ushort const * &&)
0x180043bb8  add     ebx, edi
0x180043bba  mov     eax, [rbp+57h+var_48]
0x180043bbd  mov     [rbp+57h+cchName], eax
0x180043bc0  lea     rcx, [rbp+57h+var_58]
0x180043bc4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043bc9  mov     r8, rax; lpName
0x180043bcc  mov     [rsp+100h+lpcValues], r15; lpftLastWriteTime
0x180043bd1  mov     [rsp+100h+lpcbMaxClassLen], r15; lpcchClass
0x180043bd6  mov     [rsp+100h+lpcbMaxSubKeyLen], r15; lpClass
0x180043bdb  mov     [rsp+100h+lpcSubKeys], r15; int
0x180043be0  lea     r9, [rbp+57h+cchName]; lpcchName
0x180043be4  mov     edx, ebx; dwIndex
0x180043be6  mov     rcx, [rbp+57h+hKey]; hKey
0x180043bea  call    cs:__imp_RegEnumKeyExW
0x180043bf0  cmp     eax, esi
0x180043bf2  jnz     loc_180043B54
0x180043bf8  jmp     short loc_180043C20
0x180043bfa  jle     short loc_180043C04
0x180043bfc  movzx   eax, ax
0x180043bff  or      eax, 80070000h
0x180043c04  test    eax, eax
0x180043c06  jns     short loc_180043C20
0x180043c08  mov     rcx, [rbp+5Fh]; this
0x180043c0c  mov     r9d, eax; char *
0x180043c0f  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x180043c16  mov     edx, 2D5h; void *
0x180043c1b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043c20  mov     rdi, qword ptr [rbp+57h+var_90]
0x180043c24  mov     rsi, qword ptr [rbp+57h+var_90+8]
0x180043c28  jmp     loc_180043CB2
0x180043c2d  mov     [rbp+57h+lpSubKey], r15
0x180043c31  mov     [rbp+57h+var_70], r15
0x180043c35  mov     [rbp+57h+var_68], r15
0x180043c39  mov     rcx, rdi
0x180043c3c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043c41  mov     r9, rax
0x180043c44  lea     r8, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180043c4b  lea     rdx, aSS_2; "%s\\%s"
0x180043c52  lea     rcx, [rbp+57h+lpSubKey]
0x180043c56  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180043c5b  mov     ebx, eax
0x180043c5d  test    eax, eax
0x180043c5f  js      loc_180043CF7
0x180043c65  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180043c69  mov     rcx, [r14+108h]; hKey
0x180043c70  call    cs:__imp_RegDeleteTreeW
0x180043c76  test    eax, 0FFFFFFFDh
0x180043c7b  jz      short loc_180043CA5
0x180043c7d  test    eax, eax
0x180043c7f  jle     short loc_180043C8B
0x180043c81  movzx   eax, ax
0x180043c84  or      eax, 80070000h
0x180043c89  test    eax, eax
0x180043c8b  jns     short loc_180043CA5
0x180043c8d  mov     rcx, [rbp+5Fh]; this
0x180043c91  mov     r9d, eax; char *
0x180043c94  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x180043c9b  mov     edx, 2EAh; void *
0x180043ca0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043ca5  lea     rcx, [rbp+57h+lpSubKey]
0x180043ca9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180043cae  add     rdi, 20h ; ' '
0x180043cb2  cmp     rdi, rsi
0x180043cb5  jnz     loc_180043C2D
0x180043cbb  lea     rcx, [rbp+57h+var_58]
0x180043cbf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043cc4  lea     rcx, [rbp+57h+var_90]
0x180043cc8  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180043ccd  mov     ebx, r15d
0x180043cd0  lea     rcx, [rbp+57h+hKey]
0x180043cd4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180043cd9  mov     eax, ebx
0x180043cdb  mov     rcx, [rbp+57h+var_38]
0x180043cdf  xor     rcx, rsp; StackCookie
0x180043ce2  call    __security_check_cookie
0x180043ce7  add     rsp, 0D8h
0x180043cee  pop     r15
0x180043cf0  pop     r14
0x180043cf2  pop     rdi
0x180043cf3  pop     rsi
0x180043cf4  pop     rbx
0x180043cf5  pop     rbp
0x180043cf6  retn
0x180043cf7  mov     rcx, [rbp+5Fh]; this
0x180043cfb  mov     r9d, eax; char *
0x180043cfe  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x180043d05  mov     edx, 2E4h; void *
0x180043d0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043d0f  lea     rcx, [rbp+57h+lpSubKey]
0x180043d13  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180043d18  lea     rcx, [rbp+57h+var_58]
0x180043d1c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043d21  jmp     loc_180043AEC
```
