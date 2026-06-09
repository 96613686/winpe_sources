# SystemSettings::StorageSenseHandlers::FileRecommendationSetting::Initialize(unsigned __int64,_FILETIME)

- ea: `0x1800c2b64`
- end: `0x1800c2dc1`
- name: `?Initialize@FileRecommendationSetting@StorageSenseHandlers@SystemSettings@@QEAAJ_KU_FILETIME@@@Z`
- size: `605`
- prototype: `int(SystemSettings::StorageSenseHandlers::FileRecommendationSetting *__hidden this, unsigned __int64, struct _FILETIME)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c27c8`

## callees

- `0x180006e50`
- `0x180012374`
- `0x180016ef4`
- `0x180023928`
- `0x1800259ac`
- `0x180029a38`
- `0x1800352b4`
- `0x1800c1ed0`
- `0x1800c2b64`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800c2c17`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800c2c17`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x1800c2ba8`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x1800c2ba8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800c2c4d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800c2c4d`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x1800c2cee`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x1800c2cee`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x1800c2ca4`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x1800c2ca4`

## string_xrefs

- `0x1800c2bb4`: `CleanupRecommendations`
- `0x1800c2c21`: `CleanupRecommendations`
- `0x1800c2c57`: `CleanupRecommendations`
- `0x1800c2cae`: `CleanupRecommendations`
- `0x1800c2cf8`: `CleanupRecommendations`
- `0x1800c2bdb`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationsetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::StorageSenseHandlers::FileRecommendationSetting::Initialize(
        SystemSettings::StorageSenseHandlers::FileRecommendationSetting *this,
        ULONGLONG a2,
        FILETIME a3)
{
  unsigned int v5; // ebx
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  FILETIME FileTime; // [rsp+30h] [rbp-D0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v15[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v16[32]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR pszBuf[32]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR TimeStr[256]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR DateStr[256]; // [rsp+310h] [rbp+210h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  FileTime = a3;
  v5 = StrFormatByteSizeEx(a2, 2, pszBuf, 0x20u);
  if ( (v5 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationsetting.cpp",
      (const char *)v5,
      (int)"%hs",
      "CleanupRecommendations",
      FileTime);
    return v5;
  }
  std::wstring::assign((char *)this + 368, pszBuf);
  *((_QWORD *)this + 50) = a2;
  SystemTime = 0;
  if ( !FileTimeToLocalFileTime(&FileTime, &FileTime) )
  {
    v5 = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationsetting.cpp",
      (const char *)0x80004005LL,
      (int)"%hs",
      "CleanupRecommendations",
      FileTime);
    return v5;
  }
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
  {
    v5 = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationsetting.cpp",
      (const char *)0x80004005LL,
      (int)"%hs",
      "CleanupRecommendations",
      FileTime);
    return v5;
  }
  if ( !GetDateFormatW(0x400u, 1u, &SystemTime, 0, DateStr, 255) )
  {
    v5 = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationsetting.cpp",
      (const char *)0x80004005LL,
      (int)"%hs",
      "CleanupRecommendations",
      FileTime);
    return v5;
  }
  if ( !GetTimeFormatW(0x400u, 2u, &SystemTime, 0, TimeStr, 255) )
  {
    v5 = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationsetting.cpp",
      (const char *)0x80004005LL,
      (int)"%hs",
      "CleanupRecommendations",
      FileTime);
    return v5;
  }
  v7 = std::wstring::wstring(v16);
  v8 = std::wstring::wstring(v15);
  v9 = std::operator+<unsigned short>(v14, v8, L" ");
  std::wstring::wstring(v13, v10, v9, v7);
  std::wstring::operator=((char *)this + 336, v13);
  std::wstring::_Tidy_deallocate(v13);
  std::wstring::_Tidy_deallocate(v14);
  std::wstring::_Tidy_deallocate(v15);
  std::wstring::_Tidy_deallocate(v16);
  return 0;
}

```

## disassembly

```asm
0x1800c2b64  mov     [rsp-8+arg_18], rbx
0x1800c2b69  push    rbp
0x1800c2b6a  push    rsi
0x1800c2b6b  push    rdi
0x1800c2b6c  lea     rbp, [rsp-420h]
0x1800c2b74  sub     rsp, 520h
0x1800c2b7b  mov     rax, cs:__security_cookie
0x1800c2b82  xor     rax, rsp
0x1800c2b85  mov     [rbp+430h+var_20], rax
0x1800c2b8c  mov     rsi, rdx
0x1800c2b8f  mov     rdi, rcx
0x1800c2b92  mov     qword ptr [rsp+530h+FileTime.dwLowDateTime], r8
0x1800c2b97  mov     r9d, 20h ; ' '; cchBuf
0x1800c2b9d  lea     r8, [rbp+430h+pszBuf]; pszBuf
0x1800c2ba1  lea     edx, [r9-1Eh]; flags
0x1800c2ba5  mov     rcx, rsi; ull
0x1800c2ba8  call    cs:__imp_StrFormatByteSizeEx
0x1800c2bae  mov     ebx, eax
0x1800c2bb0  test    eax, eax
0x1800c2bb2  jns     short loc_1800C2BEE
0x1800c2bb4  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x1800c2bbb  mov     qword ptr [rsp+530h+cchDate], rdx; char *
0x1800c2bc0  lea     rdx, aHs; "%hs"
0x1800c2bc7  mov     [rsp+530h+lpDateStr], rdx; int
0x1800c2bcc  mov     edx, 29h ; ')'; void *
0x1800c2bd1  mov     rcx, [rbp+438h]; this
0x1800c2bd8  mov     r9d, ebx; char *
0x1800c2bdb  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\coresettinghandlers"...
0x1800c2be2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800c2be7  mov     eax, ebx
0x1800c2be9  jmp     loc_1800C2D9F
0x1800c2bee  lea     rcx, [rdi+170h]
0x1800c2bf5  lea     rdx, [rbp+430h+pszBuf]
0x1800c2bf9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800c2bfe  mov     [rdi+190h], rsi
0x1800c2c05  xorps   xmm0, xmm0
0x1800c2c08  movups  xmmword ptr [rsp+530h+SystemTime.wYear], xmm0
0x1800c2c0d  lea     rdx, [rsp+530h+FileTime]; lpLocalFileTime
0x1800c2c12  lea     rcx, [rsp+530h+FileTime]; lpFileTime
0x1800c2c17  call    cs:__imp_FileTimeToLocalFileTime
0x1800c2c1d  test    eax, eax
0x1800c2c1f  jnz     short loc_1800C2C43
0x1800c2c21  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x1800c2c28  mov     qword ptr [rsp+530h+cchDate], rdx
0x1800c2c2d  lea     rdx, aHs; "%hs"
0x1800c2c34  mov     [rsp+530h+lpDateStr], rdx
0x1800c2c39  mov     ebx, 80004005h
0x1800c2c3e  lea     edx, [rax+30h]
0x1800c2c41  jmp     short loc_1800C2BD1
0x1800c2c43  lea     rdx, [rsp+530h+SystemTime]; lpSystemTime
0x1800c2c48  lea     rcx, [rsp+530h+FileTime]; lpFileTime
0x1800c2c4d  call    cs:__imp_FileTimeToSystemTime
0x1800c2c53  test    eax, eax
0x1800c2c55  jnz     short loc_1800C2C7C
0x1800c2c57  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x1800c2c5e  mov     qword ptr [rsp+530h+cchDate], rdx
0x1800c2c63  lea     rdx, aHs; "%hs"
0x1800c2c6a  mov     [rsp+530h+lpDateStr], rdx
0x1800c2c6f  mov     ebx, 80004005h
0x1800c2c74  lea     edx, [rax+31h]
0x1800c2c77  jmp     loc_1800C2BD1
0x1800c2c7c  mov     ebx, 0FFh
0x1800c2c81  mov     [rsp+530h+cchDate], ebx; cchDate
0x1800c2c85  lea     rax, [rbp+430h+DateStr]
0x1800c2c8c  mov     [rsp+530h+lpDateStr], rax; lpDateStr
0x1800c2c91  xor     r9d, r9d; lpFormat
0x1800c2c94  lea     r8, [rsp+530h+SystemTime]; lpDate
0x1800c2c99  lea     edx, [r9+1]; dwFlags
0x1800c2c9d  mov     esi, 400h
0x1800c2ca2  mov     ecx, esi; Locale
0x1800c2ca4  call    cs:__imp_GetDateFormatW
0x1800c2caa  test    eax, eax
0x1800c2cac  jnz     short loc_1800C2CD3
0x1800c2cae  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x1800c2cb5  mov     qword ptr [rsp+530h+cchDate], rdx
0x1800c2cba  lea     rdx, aHs; "%hs"
0x1800c2cc1  mov     [rsp+530h+lpDateStr], rdx
0x1800c2cc6  mov     ebx, 80004005h
0x1800c2ccb  lea     edx, [rax+34h]
0x1800c2cce  jmp     loc_1800C2BD1
0x1800c2cd3  mov     [rsp+530h+cchDate], ebx; cchTime
0x1800c2cd7  lea     rax, [rbp+430h+TimeStr]
0x1800c2cdb  mov     [rsp+530h+lpDateStr], rax; lpTimeStr
0x1800c2ce0  xor     r9d, r9d; lpFormat
0x1800c2ce3  lea     r8, [rsp+530h+SystemTime]; lpTime
0x1800c2ce8  lea     edx, [r9+2]; dwFlags
0x1800c2cec  mov     ecx, esi; Locale
0x1800c2cee  call    cs:__imp_GetTimeFormatW
0x1800c2cf4  test    eax, eax
0x1800c2cf6  jnz     short loc_1800C2D1D
0x1800c2cf8  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x1800c2cff  mov     qword ptr [rsp+530h+cchDate], rdx
0x1800c2d04  lea     rdx, aHs; "%hs"
0x1800c2d0b  mov     [rsp+530h+lpDateStr], rdx
0x1800c2d10  mov     ebx, 80004005h
0x1800c2d15  lea     edx, [rax+36h]
0x1800c2d18  jmp     loc_1800C2BD1
0x1800c2d1d  lea     rdx, [rbp+430h+TimeStr]
0x1800c2d21  lea     rcx, [rbp+430h+var_480]
0x1800c2d25  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c2d2a  mov     rbx, rax
0x1800c2d2d  lea     rdx, [rbp+430h+DateStr]
0x1800c2d34  lea     rcx, [rbp+430h+var_4A0]
0x1800c2d38  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c2d3d  nop
0x1800c2d3e  lea     r8, asc_180108014; " "
0x1800c2d45  mov     rdx, rax
0x1800c2d48  lea     rcx, [rsp+530h+var_4C0]
0x1800c2d4d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800c2d52  nop
0x1800c2d53  mov     r9, rbx
0x1800c2d56  mov     r8, rax
0x1800c2d59  lea     rcx, [rsp+530h+var_4E0]
0x1800c2d5e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1800c2d63  lea     rcx, [rdi+150h]
0x1800c2d6a  lea     rdx, [rsp+530h+var_4E0]
0x1800c2d6f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800c2d74  lea     rcx, [rsp+530h+var_4E0]
0x1800c2d79  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c2d7e  nop
0x1800c2d7f  lea     rcx, [rsp+530h+var_4C0]
0x1800c2d84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c2d89  nop
0x1800c2d8a  lea     rcx, [rbp+430h+var_4A0]
0x1800c2d8e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c2d93  nop
0x1800c2d94  lea     rcx, [rbp+430h+var_480]
0x1800c2d98  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c2d9d  xor     eax, eax
0x1800c2d9f  mov     rcx, [rbp+430h+var_20]
0x1800c2da6  xor     rcx, rsp; StackCookie
0x1800c2da9  call    __security_check_cookie
0x1800c2dae  mov     rbx, [rsp+530h+arg_18]
0x1800c2db6  add     rsp, 520h
0x1800c2dbd  pop     rdi
0x1800c2dbe  pop     rsi
0x1800c2dbf  pop     rbp
0x1800c2dc0  retn
```
