# RunToCompletionAsyncOperationImpl::ValidateExeFileName(void)

- ea: `0x18001bad0`
- end: `0x18001bdb2`
- name: `?ValidateExeFileName@RunToCompletionAsyncOperationImpl@@AEAAJXZ`
- size: `738`
- prototype: `__int64 __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001b854`

## callees

- `0x180002dc0`
- `0x180008a80`
- `0x180008adc`
- `0x180009034`
- `0x180016c48`
- `0x180017348`
- `0x180018ce0`
- `0x180018d40`
- `0x180018fb4`
- `0x1800191a8`
- `0x18001a9c0`
- `0x18001bad0`
- `0x18001be88`
- `0x1800274a4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001bb0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001bb0a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18001bb54`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18001bb54`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18001bc05`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18001bce9`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18001bc05`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18001bce9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RunToCompletionAsyncOperationImpl::ValidateExeFileName(HSTRING *this)
{
  Microsoft::WRL::Wrappers::HString *v1; // rsi
  PCWSTR StringRawBuffer; // rax
  _WORD *v3; // rax
  _WORD *v4; // rdx
  const WCHAR *v5; // rax
  unsigned __int64 v6; // rbx
  unsigned __int16 **v7; // rdx
  HRESULT CallingProcessPackageInstallPath; // edi
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  const WCHAR *v16; // rax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // rax
  int v21; // eax
  const unsigned __int16 *v22; // r9
  unsigned int v23; // r8d
  const unsigned __int16 *v24; // rdx
  const WCHAR *v25; // rax
  HRESULT v26; // eax
  RunToCompletionAsyncOperationImpl *v27; // rcx
  RunToCompletionAsyncOperationImpl *v28; // rcx
  unsigned __int64 v29; // rbx
  int v30; // ebx
  unsigned int v31; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+40h] [rbp-C0h]
  __int64 v34; // [rsp+48h] [rbp-B8h]
  _BYTE v35[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h]
  WCHAR pszPathOut[264]; // [rsp+70h] [rbp-90h] BYREF

  v1 = (Microsoft::WRL::Wrappers::HString *)(this + 22);
  StringRawBuffer = WindowsGetStringRawBuffer(this[22], 0);
  std::wstring::wstring(v35, StringRawBuffer);
  v3 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
  v4 = &v3[v36];
  while ( v3 != v4 )
  {
    if ( *v3 == 47 )
      *v3 = 92;
    ++v3;
  }
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
  if ( PathIsRelativeW(v5) )
  {
    v32 = 0;
    v33 = 0;
    v34 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v32);
    v6 = -1;
    v33 = -1;
    v34 = -1;
    CallingProcessPackageInstallPath = CallerIdentity::GetCallingProcessPackageInstallPath((CallerIdentity *)&v32, v7);
    if ( CallingProcessPackageInstallPath < 0 )
      goto LABEL_8;
    v10 = std::_WChar_traits<unsigned short>::length(L"\\");
    std::wstring::_Insert<unsigned short>(v35, v11, v12, v10);
    v13 = std::_WChar_traits<unsigned short>::length(v32);
    std::wstring::_Insert<unsigned short>(v35, v14, v15, v13);
    v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
    CallingProcessPackageInstallPath = PathCchCanonicalize(pszPathOut, 0x104u, v16);
    if ( CallingProcessPackageInstallPath < 0 )
      goto LABEL_8;
    v17 = std::_WChar_traits<unsigned short>::length(pszPathOut);
    std::wstring::_Assign<unsigned short>(v35, pszPathOut, v17);
    std::_WChar_traits<unsigned short>::length(v32);
    v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
    if ( std::_Traits_find<std::char_traits<unsigned short>>(v18, v36, v19, v32, v19) )
    {
      CallingProcessPackageInstallPath = -2147024891;
LABEL_8:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v32);
LABEL_9:
      std::wstring::_Tidy_deallocate(v35);
      return (unsigned int)CallingProcessPackageInstallPath;
    }
    v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
    if ( v20 )
    {
      v31 = 0;
      do
        ++v6;
      while ( *(_WORD *)(v20 + 2 * v6) );
      v21 = ULongLongToUInt(v6, &v31);
      if ( v21 < 0 )
        goto LABEL_20;
      v23 = v31;
      v24 = v22;
    }
    else
    {
      v23 = 0;
      v24 = &qword_180034A88;
    }
    v21 = Microsoft::WRL::Wrappers::HString::Set(v1, v24, v23);
    if ( v21 < 0 )
    {
LABEL_20:
      CallingProcessPackageInstallPath = v21;
      goto LABEL_8;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v32);
    goto LABEL_31;
  }
  v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
  v26 = PathCchCanonicalize(pszPathOut, 0x104u, v25);
  if ( v26 < 0 )
  {
    CallingProcessPackageInstallPath = v26;
    goto LABEL_9;
  }
  if ( !RunToCompletionAsyncOperationImpl::IsAllowedExePath(v27, pszPathOut, L"AllowedExecutableFilesList")
    && !RunToCompletionAsyncOperationImpl::IsAllowedExePath(v28, pszPathOut, L"DefaultAllowedExecutableFilesList") )
  {
    CallingProcessPackageInstallPath = -2147024891;
    goto LABEL_9;
  }
  v31 = 0;
  v29 = -1;
  do
    ++v29;
  while ( pszPathOut[v29] );
  v30 = ULongLongToUInt(v29, &v31);
  if ( v30 >= 0 )
  {
    v30 = Microsoft::WRL::Wrappers::HString::Set(v1, pszPathOut, v31);
    if ( v30 >= 0 )
    {
LABEL_31:
      std::wstring::_Tidy_deallocate(v35);
      return 0;
    }
  }
  std::wstring::_Tidy_deallocate(v35);
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x18001bad0  mov     [rsp-8+arg_8], rbx
0x18001bad5  mov     [rsp-8+arg_10], rsi
0x18001bada  push    rbp
0x18001badb  push    rdi
0x18001badc  push    r15
0x18001bade  lea     rbp, [rsp-190h]
0x18001bae6  sub     rsp, 290h
0x18001baed  mov     rax, cs:__security_cookie
0x18001baf4  xor     rax, rsp
0x18001baf7  mov     [rbp+1A0h+var_20], rax
0x18001bafe  lea     rsi, [rcx+0B0h]
0x18001bb05  xor     edx, edx; length
0x18001bb07  mov     rcx, [rsi]; string
0x18001bb0a  call    cs:__imp_WindowsGetStringRawBuffer
0x18001bb10  mov     rdx, rax
0x18001bb13  lea     rcx, [rsp+2A0h+var_250]
0x18001bb18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001bb1d  nop
0x18001bb1e  lea     rcx, [rsp+2A0h+var_250]
0x18001bb23  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bb28  mov     rcx, [rsp+2A0h+var_240]
0x18001bb2d  lea     rdx, [rax+rcx*2]
0x18001bb31  jmp     short loc_18001BB42
0x18001bb33  cmp     word ptr [rax], 2Fh ; '/'
0x18001bb37  jnz     short loc_18001BB3E
0x18001bb39  mov     word ptr [rax], 5Ch ; '\'
0x18001bb3e  add     rax, 2
0x18001bb42  cmp     rax, rdx
0x18001bb45  jnz     short loc_18001BB33
0x18001bb47  lea     rcx, [rsp+2A0h+var_250]
0x18001bb4c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bb51  mov     rcx, rax; pszPath
0x18001bb54  call    cs:__imp_PathIsRelativeW
0x18001bb5a  xor     r15d, r15d
0x18001bb5d  test    eax, eax
0x18001bb5f  jz      loc_18001BCD2
0x18001bb65  mov     [rsp+2A0h+var_268], r15
0x18001bb6a  mov     [rsp+2A0h+var_260], r15
0x18001bb6f  mov     [rsp+2A0h+var_258], r15
0x18001bb74  lea     rcx, [rsp+2A0h+var_268]
0x18001bb79  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001bb7e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001bb82  mov     [rsp+2A0h+var_260], rbx
0x18001bb87  mov     [rsp+2A0h+var_258], rbx
0x18001bb8c  lea     rcx, [rsp+2A0h+var_268]; this
0x18001bb91  call    ?GetCallingProcessPackageInstallPath@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageInstallPath(ushort * *)
0x18001bb96  mov     edi, eax
0x18001bb98  test    eax, eax
0x18001bb9a  jns     short loc_18001BBB8
0x18001bb9c  lea     rcx, [rsp+2A0h+var_268]
0x18001bba1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001bba6  nop
0x18001bba7  lea     rcx, [rsp+2A0h+var_250]
0x18001bbac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bbb1  mov     eax, edi
0x18001bbb3  jmp     loc_18001BD8B
0x18001bbb8  lea     rcx, asc_180034A80; "\\"
0x18001bbbf  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001bbc4  mov     r9, rax
0x18001bbc7  mov     r8, rcx
0x18001bbca  lea     rcx, [rsp+2A0h+var_250]
0x18001bbcf  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x18001bbd4  mov     rcx, [rsp+2A0h+var_268]
0x18001bbd9  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001bbde  mov     r9, rax
0x18001bbe1  mov     r8, rcx
0x18001bbe4  lea     rcx, [rsp+2A0h+var_250]
0x18001bbe9  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x18001bbee  lea     rcx, [rsp+2A0h+var_250]
0x18001bbf3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bbf8  mov     r8, rax; pszPathIn
0x18001bbfb  mov     edx, 104h; cchPathOut
0x18001bc00  lea     rcx, [rsp+2A0h+pszPathOut]; pszPathOut
0x18001bc05  call    cs:__imp_PathCchCanonicalize
0x18001bc0b  mov     edi, eax
0x18001bc0d  test    eax, eax
0x18001bc0f  js      short loc_18001BB9C
0x18001bc11  lea     rcx, [rsp+2A0h+pszPathOut]
0x18001bc16  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001bc1b  mov     r8, rax
0x18001bc1e  lea     rdx, [rsp+2A0h+pszPathOut]
0x18001bc23  lea     rcx, [rsp+2A0h+var_250]
0x18001bc28  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001bc2d  mov     rcx, [rsp+2A0h+var_268]
0x18001bc32  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001bc37  mov     r8, rax
0x18001bc3a  lea     rcx, [rsp+2A0h+var_250]
0x18001bc3f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bc44  mov     rcx, rax
0x18001bc47  mov     [rsp+2A0h+var_280], r8
0x18001bc4c  mov     r9, [rsp+2A0h+var_268]
0x18001bc51  mov     rdx, [rsp+2A0h+var_240]
0x18001bc56  call    ??$_Traits_find@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18001bc5b  test    rax, rax
0x18001bc5e  jz      short loc_18001BC6A
0x18001bc60  mov     edi, 80070005h
0x18001bc65  jmp     loc_18001BB9C
0x18001bc6a  lea     rcx, [rsp+2A0h+var_250]
0x18001bc6f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bc74  mov     r9, rax
0x18001bc77  test    rax, rax
0x18001bc7a  jz      short loc_18001BCA6
0x18001bc7c  mov     [rsp+2A0h+var_270], r15d
0x18001bc81  inc     rbx
0x18001bc84  cmp     [rax+rbx*2], r15w
0x18001bc89  jnz     short loc_18001BC81
0x18001bc8b  lea     rdx, [rsp+2A0h+var_270]; unsigned int *
0x18001bc90  mov     rcx, rbx; unsigned __int64
0x18001bc93  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18001bc98  test    eax, eax
0x18001bc9a  js      short loc_18001BCBC
0x18001bc9c  mov     r8d, [rsp+2A0h+var_270]
0x18001bca1  mov     rdx, r9
0x18001bca4  jmp     short loc_18001BCB0
0x18001bca6  xor     r8d, r8d; unsigned int
0x18001bca9  lea     rdx, qword_180034A88; unsigned __int16 *
0x18001bcb0  mov     rcx, rsi; this
0x18001bcb3  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18001bcb8  test    eax, eax
0x18001bcba  jns     short loc_18001BCC3
0x18001bcbc  mov     edi, eax
0x18001bcbe  jmp     loc_18001BB9C
0x18001bcc3  lea     rcx, [rsp+2A0h+var_268]
0x18001bcc8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001bccd  jmp     loc_18001BD71
0x18001bcd2  lea     rcx, [rsp+2A0h+var_250]
0x18001bcd7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bcdc  mov     r8, rax; pszPathIn
0x18001bcdf  mov     edx, 104h; cchPathOut
0x18001bce4  lea     rcx, [rsp+2A0h+pszPathOut]; pszPathOut
0x18001bce9  call    cs:__imp_PathCchCanonicalize
0x18001bcef  test    eax, eax
0x18001bcf1  jns     short loc_18001BCFA
0x18001bcf3  mov     edi, eax
0x18001bcf5  jmp     loc_18001BBA7
0x18001bcfa  lea     r8, aAllowedexecuta; "AllowedExecutableFilesList"
0x18001bd01  lea     rdx, [rsp+2A0h+pszPathOut]; unsigned __int16 *
0x18001bd06  call    ?IsAllowedExePath@RunToCompletionAsyncOperationImpl@@AEAAHPEBG0@Z; RunToCompletionAsyncOperationImpl::IsAllowedExePath(ushort const *,ushort const *)
0x18001bd0b  test    eax, eax
0x18001bd0d  jnz     short loc_18001BD2E
0x18001bd0f  lea     r8, aDefaultallowed; "DefaultAllowedExecutableFilesList"
0x18001bd16  lea     rdx, [rsp+2A0h+pszPathOut]; unsigned __int16 *
0x18001bd1b  call    ?IsAllowedExePath@RunToCompletionAsyncOperationImpl@@AEAAHPEBG0@Z; RunToCompletionAsyncOperationImpl::IsAllowedExePath(ushort const *,ushort const *)
0x18001bd20  test    eax, eax
0x18001bd22  jnz     short loc_18001BD2E
0x18001bd24  mov     edi, 80070005h
0x18001bd29  jmp     loc_18001BBA7
0x18001bd2e  mov     [rsp+2A0h+var_270], r15d
0x18001bd33  lea     rax, [rsp+2A0h+pszPathOut]
0x18001bd38  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001bd3c  inc     rbx
0x18001bd3f  cmp     [rax+rbx*2], r15w
0x18001bd44  jnz     short loc_18001BD3C
0x18001bd46  lea     rdx, [rsp+2A0h+var_270]; unsigned int *
0x18001bd4b  mov     rcx, rbx; unsigned __int64
0x18001bd4e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18001bd53  mov     ebx, eax
0x18001bd55  test    eax, eax
0x18001bd57  js      short loc_18001BD7F
0x18001bd59  mov     r8d, [rsp+2A0h+var_270]; unsigned int
0x18001bd5e  lea     rdx, [rsp+2A0h+pszPathOut]; unsigned __int16 *
0x18001bd63  mov     rcx, rsi; this
0x18001bd66  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18001bd6b  mov     ebx, eax
0x18001bd6d  test    eax, eax
0x18001bd6f  js      short loc_18001BD7F
0x18001bd71  lea     rcx, [rsp+2A0h+var_250]
0x18001bd76  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bd7b  xor     eax, eax
0x18001bd7d  jmp     short loc_18001BD8B
0x18001bd7f  lea     rcx, [rsp+2A0h+var_250]
0x18001bd84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bd89  mov     eax, ebx
0x18001bd8b  mov     rcx, [rbp+1A0h+var_20]
0x18001bd92  xor     rcx, rsp; StackCookie
0x18001bd95  call    __security_check_cookie
0x18001bd9a  lea     r11, [rsp+2A0h+var_10]
0x18001bda2  mov     rbx, [r11+28h]
0x18001bda6  mov     rsi, [r11+30h]
0x18001bdaa  mov     rsp, r11
0x18001bdad  pop     r15
0x18001bdaf  pop     rdi
0x18001bdb0  pop     rbp
0x18001bdb1  retn
```
