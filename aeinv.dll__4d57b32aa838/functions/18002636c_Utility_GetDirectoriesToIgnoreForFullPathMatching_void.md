# Utility::GetDirectoriesToIgnoreForFullPathMatching(void)

- ea: `0x18002636c`
- end: `0x180026bd5`
- name: `?GetDirectoriesToIgnoreForFullPathMatching@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `2153`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800260f4`

## callees

- `0x18000e458`
- `0x180018300`
- `0x180018a60`
- `0x18001e0d0`
- `0x18002636c`
- `0x1800404c4`
- `0x180044c44`
- `0x180044c88`
- `0x18004869c`
- `0x1800493b8`
- `0x18004f380`
- `0x180050128`
- `0x180053020`
- `0x180059920`
- `0x180059cd0`
- `0x180059f2c`
- `0x180059f94`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18002640e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002640e`
- `SHELL32!SHGetKnownFolderPath` at `0x18002644c`
- `SHELL32!SHGetKnownFolderPath` at `0x180026519`
- `SHELL32!SHGetKnownFolderPath` at `0x18002644c`
- `SHELL32!SHGetKnownFolderPath` at `0x180026519`

## string_xrefs

- `0x1800268fb`: `\Temp`

## pseudocode

```c
// Hidden C++ exception states: #wind=54
__int64 *Utility::GetDirectoriesToIgnoreForFullPathMatching()
{
  __int64 v0; // rdx
  __int64 v1; // rax
  __int64 v2; // rdx
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 UserProfilePaths; // rax
  __int64 *v10; // rbx
  __int64 *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rdx
  PWSTR v44; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v46[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v47[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v48[32]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v49[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 Src[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v51[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v52[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v53[4]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v54[4]; // [rsp+120h] [rbp+20h] BYREF

  v46[1] = -2;
  if ( dword_180184180 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180184180);
    if ( dword_180184180 == -1 )
    {
      std::vector<enum tagMSIINSTALLCONTEXT>::vector<enum tagMSIINSTALLCONTEXT>(qword_180184188);
      atexit(Utility::GetDirectoriesToIgnoreForFullPathMatching_::_2_::_dynamic_atexit_destructor_for__folderList__);
      Init_thread_footer(&dword_180184180);
    }
  }
  if ( byte_1801817E9 )
  {
    AcquireSRWLockExclusive(&stru_180183E70);
    v46[0] = &stru_180183E70;
    if ( byte_1801817E9 )
    {
      ppszPath = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &ppszPath,
        0);
      if ( SHGetKnownFolderPath(&FOLDERID_ProgramFilesX86, 0, 0, &ppszPath) >= 0 )
      {
        std::wstring::wstring(Src, ppszPath);
        v0 = Utility::ToLower((__int64)v49, Src);
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v0);
        std::wstring::~wstring(v49);
        std::wstring::~wstring(Src);
        std::wstring::wstring(Src, ppszPath);
        v1 = Utility::ToLower((__int64)v51, Src);
        v2 = std::operator+<unsigned short>(v49, v1, L"\\");
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v2);
        std::wstring::~wstring(v49);
        std::wstring::~wstring(v51);
        std::wstring::~wstring(Src);
      }
      v44 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v44,
        0);
      if ( SHGetKnownFolderPath(&FOLDERID_ProgramFiles, 0, 0, &v44) >= 0 )
      {
        std::wstring::wstring(v49, v44);
        v3 = Utility::ToLower((__int64)v51, v49);
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v3);
        std::wstring::~wstring(v51);
        std::wstring::~wstring(v49);
        std::wstring::wstring(v49, v44);
        v4 = Utility::ToLower((__int64)v53, v49);
        v5 = std::operator+<unsigned short>(v51, v4, L"\\");
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v5);
        std::wstring::~wstring(v51);
        std::wstring::~wstring(v53);
        std::wstring::~wstring(v49);
        std::wstring::wstring(Src, v44);
        std::wstring::_Append<unsigned short>(Src);
        v6 = Utility::ToLower((__int64)v49, Src);
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v6);
        std::wstring::~wstring(v49);
        v7 = Utility::ToLower((__int64)v51, Src);
        v8 = std::operator+<unsigned short>(v49, v7, L"\\");
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v8);
        std::wstring::~wstring(v49);
        std::wstring::~wstring(v51);
        std::wstring::~wstring(Src);
      }
      UserProfilePaths = Utility::GetUserProfilePaths();
      v10 = *(__int64 **)UserProfilePaths;
      v11 = *(__int64 **)(UserProfilePaths + 8);
      if ( *(__int64 **)UserProfilePaths != v11 )
      {
        do
        {
          v12 = Utility::ToLower((__int64)v48, v10);
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v12);
          std::wstring::~wstring(v48);
          v13 = Utility::ToLower((__int64)v47, v10);
          v14 = std::operator+<unsigned short>(v48, v13, L"\\");
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v14);
          std::wstring::~wstring(v48);
          std::wstring::~wstring(v47);
          std::wstring::wstring(Src, v10);
          std::wstring::_Append<unsigned short>(Src);
          v15 = Utility::ToLower((__int64)v47, Src);
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v15);
          std::wstring::~wstring(v47);
          v16 = Utility::ToLower((__int64)v48, Src);
          v17 = std::operator+<unsigned short>(v47, v16, L"\\");
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v17);
          std::wstring::~wstring(v47);
          std::wstring::~wstring(v48);
          std::wstring::wstring(v52, Src);
          std::wstring::_Append<unsigned short>(v52);
          v18 = Utility::ToLower((__int64)v47, v52);
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v18);
          std::wstring::~wstring(v47);
          v19 = Utility::ToLower((__int64)v48, v52);
          v20 = std::operator+<unsigned short>(v47, v19, L"\\");
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v20);
          std::wstring::~wstring(v47);
          std::wstring::~wstring(v48);
          v21 = Utility::ToLower((__int64)v48, v52);
          v22 = std::operator+<unsigned short>(v47, v21, L"\\.");
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v22);
          std::wstring::~wstring(v47);
          std::wstring::~wstring(v48);
          std::wstring::wstring(v49, v52);
          std::wstring::_Append<unsigned short>(v49);
          v23 = Utility::ToLower((__int64)v47, v49);
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v23);
          std::wstring::~wstring(v47);
          v24 = Utility::ToLower((__int64)v48, v49);
          v25 = std::operator+<unsigned short>(v47, v24, L"\\");
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v25);
          std::wstring::~wstring(v47);
          std::wstring::~wstring(v48);
          v26 = Utility::ToLower((__int64)v48, v49);
          v27 = std::operator+<unsigned short>(v47, v26, L"\\.");
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v27);
          std::wstring::~wstring(v47);
          std::wstring::~wstring(v48);
          std::wstring::wstring(v51, v52);
          std::wstring::_Append<unsigned short>(v51);
          v28 = Utility::ToLower((__int64)v47, v51);
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v28);
          std::wstring::~wstring(v47);
          v29 = Utility::ToLower((__int64)v48, v51);
          v30 = std::operator+<unsigned short>(v47, v29, L"\\");
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v30);
          std::wstring::~wstring(v47);
          std::wstring::~wstring(v48);
          v31 = Utility::ToLower((__int64)v48, v51);
          v32 = std::operator+<unsigned short>(v47, v31, L"\\.");
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v32);
          std::wstring::~wstring(v47);
          std::wstring::~wstring(v48);
          std::wstring::wstring(v53, v10);
          std::wstring::_Append<unsigned short>(v53);
          v33 = Utility::ToLower((__int64)v47, v53);
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v33);
          std::wstring::~wstring(v47);
          v34 = Utility::ToLower((__int64)v48, v53);
          v35 = std::operator+<unsigned short>(v47, v34, L"\\");
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v35);
          std::wstring::~wstring(v47);
          std::wstring::~wstring(v48);
          v36 = Utility::ToLower((__int64)v48, v53);
          v37 = std::operator+<unsigned short>(v47, v36, L"\\.");
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v37);
          std::wstring::~wstring(v47);
          std::wstring::~wstring(v48);
          std::wstring::wstring(v54, v10);
          std::wstring::_Append<unsigned short>(v54);
          v38 = Utility::ToLower((__int64)v47, v54);
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v38);
          std::wstring::~wstring(v47);
          v39 = Utility::ToLower((__int64)v48, v54);
          v40 = std::operator+<unsigned short>(v47, v39, L"\\");
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v40);
          std::wstring::~wstring(v47);
          std::wstring::~wstring(v48);
          v41 = Utility::ToLower((__int64)v48, v54);
          v42 = std::operator+<unsigned short>(v47, v41, L"\\.");
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184188, v42);
          std::wstring::~wstring(v47);
          std::wstring::~wstring(v48);
          std::wstring::~wstring(v54);
          std::wstring::~wstring(v53);
          std::wstring::~wstring(v51);
          std::wstring::~wstring(v49);
          std::wstring::~wstring(v52);
          std::wstring::~wstring(Src);
          v10 += 4;
        }
        while ( v10 != v11 );
      }
      byte_1801817E9 = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v44);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v46);
  }
  return qword_180184188;
}

```

## disassembly

```asm
0x18002636c  push    rbp
0x18002636e  push    rbx
0x18002636f  push    rsi
0x180026370  push    rdi
0x180026371  push    r12
0x180026373  push    r15
0x180026375  lea     rbp, [rsp-58h]
0x18002637a  sub     rsp, 158h
0x180026381  mov     [rsp+180h+var_148], 0FFFFFFFFFFFFFFFEh
0x18002638a  mov     rax, cs:__security_cookie
0x180026391  xor     rax, rsp
0x180026394  mov     [rbp+80h+var_40], rax
0x180026398  mov     ecx, cs:_tls_index
0x18002639e  mov     rax, gs:58h
0x1800263a7  mov     edx, 4
0x1800263ac  mov     rax, [rax+rcx*8]
0x1800263b0  lea     rsi, qword_180184188
0x1800263b7  mov     eax, [rdx+rax]
0x1800263ba  cmp     cs:dword_180184180, eax
0x1800263c0  jle     short loc_1800263F7
0x1800263c2  lea     rcx, dword_180184180
0x1800263c9  call    _Init_thread_header
0x1800263ce  cmp     cs:dword_180184180, 0FFFFFFFFh
0x1800263d5  jnz     short loc_1800263F7
0x1800263d7  mov     rcx, rsi
0x1800263da  call    ??0?$vector@W4tagMSIINSTALLCONTEXT@@V?$allocator@W4tagMSIINSTALLCONTEXT@@@std@@@std@@QEAA@XZ; std::vector<tagMSIINSTALLCONTEXT>::vector<tagMSIINSTALLCONTEXT>(void)
0x1800263df  lea     rcx, _Utility__GetDirectoriesToIgnoreForFullPathMatching____2____dynamic_atexit_destructor_for__folderList__; void (__cdecl *)()
0x1800263e6  call    atexit
0x1800263eb  lea     rcx, dword_180184180
0x1800263f2  call    _Init_thread_footer
0x1800263f7  cmp     cs:byte_1801817E9, 0
0x1800263fe  jz      loc_180026BB6
0x180026404  lea     rbx, stru_180183E70
0x18002640b  mov     rcx, rbx; SRWLock
0x18002640e  call    cs:__imp_AcquireSRWLockExclusive
0x180026414  mov     [rsp+180h+var_150], rbx
0x180026419  cmp     cs:byte_1801817E9, 0
0x180026420  jz      loc_180026BAC
0x180026426  mov     [rsp+180h+ppszPath], 0
0x18002642f  xor     edx, edx
0x180026431  lea     rcx, [rsp+180h+ppszPath]
0x180026436  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002643b  lea     r9, [rsp+180h+ppszPath]; ppszPath
0x180026440  xor     r8d, r8d; hToken
0x180026443  xor     edx, edx; dwFlags
0x180026445  lea     rcx, FOLDERID_ProgramFilesX86; rfid
0x18002644c  call    cs:__imp_SHGetKnownFolderPath
0x180026452  lea     r15, SubBlock; "\\"
0x180026459  test    eax, eax
0x18002645b  js      loc_1800264F3
0x180026461  mov     rdx, [rsp+180h+ppszPath]
0x180026466  lea     rcx, [rbp+80h+Src]
0x18002646a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002646f  nop
0x180026470  lea     rdx, [rbp+80h+Src]
0x180026474  lea     rcx, [rbp+80h+var_100]
0x180026478  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x18002647d  nop
0x18002647e  mov     rdx, rax
0x180026481  mov     rcx, rsi
0x180026484  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x180026489  nop
0x18002648a  lea     rcx, [rbp+80h+var_100]
0x18002648e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026493  nop
0x180026494  lea     rcx, [rbp+80h+Src]
0x180026498  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002649d  mov     rdx, [rsp+180h+ppszPath]
0x1800264a2  lea     rcx, [rbp+80h+Src]
0x1800264a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800264ab  nop
0x1800264ac  lea     rdx, [rbp+80h+Src]
0x1800264b0  lea     rcx, [rbp+80h+var_C0]
0x1800264b4  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800264b9  nop
0x1800264ba  mov     r8, r15
0x1800264bd  mov     rdx, rax
0x1800264c0  lea     rcx, [rbp+80h+var_100]
0x1800264c4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800264c9  nop
0x1800264ca  mov     rdx, rax
0x1800264cd  mov     rcx, rsi
0x1800264d0  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x1800264d5  nop
0x1800264d6  lea     rcx, [rbp+80h+var_100]
0x1800264da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800264df  nop
0x1800264e0  lea     rcx, [rbp+80h+var_C0]
0x1800264e4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800264e9  nop
0x1800264ea  lea     rcx, [rbp+80h+Src]
0x1800264ee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800264f3  mov     [rsp+180h+var_160], 0
0x1800264fc  xor     edx, edx
0x1800264fe  lea     rcx, [rsp+180h+var_160]
0x180026503  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180026508  lea     r9, [rsp+180h+var_160]; ppszPath
0x18002650d  xor     r8d, r8d; hToken
0x180026510  xor     edx, edx; dwFlags
0x180026512  lea     rcx, FOLDERID_ProgramFiles; rfid
0x180026519  call    cs:__imp_SHGetKnownFolderPath
0x18002651f  test    eax, eax
0x180026521  js      loc_180026648
0x180026527  mov     rdx, [rsp+180h+var_160]
0x18002652c  lea     rcx, [rbp+80h+var_100]
0x180026530  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180026535  nop
0x180026536  lea     rdx, [rbp+80h+var_100]
0x18002653a  lea     rcx, [rbp+80h+var_C0]
0x18002653e  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x180026543  nop
0x180026544  mov     rdx, rax
0x180026547  mov     rcx, rsi
0x18002654a  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18002654f  nop
0x180026550  lea     rcx, [rbp+80h+var_C0]
0x180026554  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026559  nop
0x18002655a  lea     rcx, [rbp+80h+var_100]
0x18002655e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026563  mov     rdx, [rsp+180h+var_160]
0x180026568  lea     rcx, [rbp+80h+var_100]
0x18002656c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180026571  nop
0x180026572  lea     rdx, [rbp+80h+var_100]
0x180026576  lea     rcx, [rbp+80h+var_80]
0x18002657a  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x18002657f  nop
0x180026580  mov     r8, r15
0x180026583  mov     rdx, rax
0x180026586  lea     rcx, [rbp+80h+var_C0]
0x18002658a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002658f  nop
0x180026590  mov     rdx, rax
0x180026593  mov     rcx, rsi
0x180026596  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18002659b  nop
0x18002659c  lea     rcx, [rbp+80h+var_C0]
0x1800265a0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800265a5  nop
0x1800265a6  lea     rcx, [rbp+80h+var_80]
0x1800265aa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800265af  nop
0x1800265b0  lea     rcx, [rbp+80h+var_100]
0x1800265b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800265b9  mov     rdx, [rsp+180h+var_160]
0x1800265be  lea     rcx, [rbp+80h+Src]
0x1800265c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800265c7  nop
0x1800265c8  mov     r8d, 0Ch
0x1800265ce  lea     rdx, aWindowsapps; "\\WindowsApps"
0x1800265d5  lea     rcx, [rbp+80h+Src]; Src
0x1800265d9  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800265de  lea     rdx, [rbp+80h+Src]
0x1800265e2  lea     rcx, [rbp+80h+var_100]
0x1800265e6  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800265eb  nop
0x1800265ec  mov     rdx, rax
0x1800265ef  mov     rcx, rsi
0x1800265f2  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x1800265f7  nop
0x1800265f8  lea     rcx, [rbp+80h+var_100]
0x1800265fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026601  lea     rdx, [rbp+80h+Src]
0x180026605  lea     rcx, [rbp+80h+var_C0]
0x180026609  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x18002660e  nop
0x18002660f  mov     r8, r15
0x180026612  mov     rdx, rax
0x180026615  lea     rcx, [rbp+80h+var_100]
0x180026619  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002661e  nop
0x18002661f  mov     rdx, rax
0x180026622  mov     rcx, rsi
0x180026625  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18002662a  nop
0x18002662b  lea     rcx, [rbp+80h+var_100]
0x18002662f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026634  nop
0x180026635  lea     rcx, [rbp+80h+var_C0]
0x180026639  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002663e  nop
0x18002663f  lea     rcx, [rbp+80h+Src]
0x180026643  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026648  call    ?GetUserProfilePaths@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Utility::GetUserProfilePaths(void)
0x18002664d  mov     rbx, [rax]
0x180026650  mov     rdi, [rax+8]
0x180026654  cmp     rbx, rdi
0x180026657  jz      loc_180026B8F
0x18002665d  lea     r12, asc_1801530DC; "\\."
0x180026664  mov     rdx, rbx
0x180026667  lea     rcx, [rsp+180h+var_120]
0x18002666c  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x180026671  nop
0x180026672  mov     rdx, rax
0x180026675  mov     rcx, rsi
0x180026678  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18002667d  nop
0x18002667e  lea     rcx, [rsp+180h+var_120]
0x180026683  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026688  mov     rdx, rbx
0x18002668b  lea     rcx, [rsp+180h+var_140]
0x180026690  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x180026695  nop
0x180026696  mov     r8, r15
0x180026699  mov     rdx, rax
0x18002669c  lea     rcx, [rsp+180h+var_120]
0x1800266a1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800266a6  nop
0x1800266a7  mov     rdx, rax
0x1800266aa  mov     rcx, rsi
0x1800266ad  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x1800266b2  nop
0x1800266b3  lea     rcx, [rsp+180h+var_120]
0x1800266b8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800266bd  nop
0x1800266be  lea     rcx, [rsp+180h+var_140]
0x1800266c3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800266c8  mov     rdx, rbx
0x1800266cb  lea     rcx, [rbp+80h+Src]
0x1800266cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800266d4  nop
0x1800266d5  mov     r8d, 8
0x1800266db  lea     rdx, aAppdata; "\\AppData"
0x1800266e2  lea     rcx, [rbp+80h+Src]; Src
0x1800266e6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800266eb  lea     rdx, [rbp+80h+Src]
0x1800266ef  lea     rcx, [rsp+180h+var_140]
0x1800266f4  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800266f9  nop
0x1800266fa  mov     rdx, rax
0x1800266fd  mov     rcx, rsi
0x180026700  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x180026705  nop
0x180026706  lea     rcx, [rsp+180h+var_140]
0x18002670b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026710  lea     rdx, [rbp+80h+Src]
0x180026714  lea     rcx, [rsp+180h+var_120]
0x180026719  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x18002671e  nop
0x18002671f  mov     r8, r15
0x180026722  mov     rdx, rax
0x180026725  lea     rcx, [rsp+180h+var_140]
0x18002672a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002672f  nop
0x180026730  mov     rdx, rax
0x180026733  mov     rcx, rsi
0x180026736  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18002673b  nop
0x18002673c  lea     rcx, [rsp+180h+var_140]
0x180026741  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026746  nop
0x180026747  lea     rcx, [rsp+180h+var_120]
0x18002674c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026751  lea     rdx, [rbp+80h+Src]
0x180026755  lea     rcx, [rbp+80h+var_A0]
0x180026759  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002675e  nop
0x18002675f  mov     r8d, 6
0x180026765  lea     rdx, aLocal; "\\Local"
0x18002676c  lea     rcx, [rbp+80h+var_A0]; Src
0x180026770  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180026775  lea     rdx, [rbp+80h+var_A0]
0x180026779  lea     rcx, [rsp+180h+var_140]
0x18002677e  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x180026783  nop
0x180026784  mov     rdx, rax
0x180026787  mov     rcx, rsi
0x18002678a  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18002678f  nop
0x180026790  lea     rcx, [rsp+180h+var_140]
0x180026795  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002679a  lea     rdx, [rbp+80h+var_A0]
0x18002679e  lea     rcx, [rsp+180h+var_120]
0x1800267a3  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800267a8  nop
0x1800267a9  mov     r8, r15
0x1800267ac  mov     rdx, rax
0x1800267af  lea     rcx, [rsp+180h+var_140]
0x1800267b4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800267b9  nop
0x1800267ba  mov     rdx, rax
0x1800267bd  mov     rcx, rsi
0x1800267c0  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x1800267c5  nop
0x1800267c6  lea     rcx, [rsp+180h+var_140]
0x1800267cb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800267d0  nop
0x1800267d1  lea     rcx, [rsp+180h+var_120]
0x1800267d6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800267db  lea     rdx, [rbp+80h+var_A0]
0x1800267df  lea     rcx, [rsp+180h+var_120]
0x1800267e4  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800267e9  nop
0x1800267ea  mov     r8, r12
0x1800267ed  mov     rdx, rax
0x1800267f0  lea     rcx, [rsp+180h+var_140]
0x1800267f5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800267fa  nop
0x1800267fb  mov     rdx, rax
  ... truncated ...
```
