# Utility::GetDirectoriesToIgnoreForFullPathMatching(void)

- ea: `0x1800cbed4`
- end: `0x1800cc74f`
- name: `?GetDirectoriesToIgnoreForFullPathMatching@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `2171`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ce818`

## callees

- `0x180005890`
- `0x180005d10`
- `0x180005ec0`
- `0x180005f28`
- `0x180008570`
- `0x18000eb38`
- `0x18000ed74`
- `0x18000faac`
- `0x18000faf0`
- `0x18001c5f0`
- `0x1800c993c`
- `0x1800ca4f8`
- `0x1800cbed4`
- `0x1800cd894`
- `0x1800cea08`
- `0x1800d006c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cbf3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cbf3d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800cbf7b`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800cc04c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800cbf7b`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800cc04c`

## string_xrefs

- `0x1800cc43d`: `\Temp`

## pseudocode

```c
// Hidden C++ exception states: #wind=41
__int64 *Utility::GetDirectoriesToIgnoreForFullPathMatching()
{
  __int64 v0; // rax
  __int64 v1; // rax
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 *UserProfilePaths; // rax
  __int64 v10; // rbx
  __int64 v11; // rdi
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
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  PWSTR v44; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-D8h] BYREF
  RTL_SRWLOCK *v46; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v47[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v48[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v49[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE Src[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v51[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v52[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v53[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v54[32]; // [rsp+118h] [rbp+18h] BYREF

  if ( dword_180122E20 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180122E20);
    if ( dword_180122E20 == -1 )
    {
      atexit(Utility::GetDirectoriesToIgnoreForFullPathMatching_::_2_::_dynamic_atexit_destructor_for__folderList__);
      Init_thread_footer(&dword_180122E20);
    }
  }
  if ( byte_180120D9C )
  {
    AcquireSRWLockExclusive(&stru_180122B70);
    v46 = &stru_180122B70;
    if ( byte_180120D9C )
    {
      ppszPath = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &ppszPath,
        0);
      if ( SHGetKnownFolderPath(&FOLDERID_ProgramFilesX86, 0, 0, &ppszPath) >= 0 )
      {
        std::wstring::wstring(Src, ppszPath);
        v0 = Utility::ToLower(v49, Src);
        std::vector<std::wstring>::push_back(qword_180122E28, v0);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::wstring(Src, ppszPath);
        v1 = Utility::ToLower(v51, Src);
        v2 = std::operator+<unsigned short>(v49, v1, L"\\");
        std::vector<std::wstring>::push_back(qword_180122E28, v2);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::_Tidy_deallocate(v51);
        std::wstring::_Tidy_deallocate(Src);
      }
      v44 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v44,
        0);
      if ( SHGetKnownFolderPath(&FOLDERID_ProgramFiles, 0, 0, &v44) >= 0 )
      {
        std::wstring::wstring(v49, v44);
        v3 = Utility::ToLower(v51, v49);
        std::vector<std::wstring>::push_back(qword_180122E28, v3);
        std::wstring::_Tidy_deallocate(v51);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::wstring(v49, v44);
        v4 = Utility::ToLower(v53, v49);
        v5 = std::operator+<unsigned short>(v51, v4, L"\\");
        std::vector<std::wstring>::push_back(qword_180122E28, v5);
        std::wstring::_Tidy_deallocate(v51);
        std::wstring::_Tidy_deallocate(v53);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::wstring(Src, v44);
        std::wstring::_Append<unsigned short>(Src);
        v6 = Utility::ToLower(v49, Src);
        std::vector<std::wstring>::push_back(qword_180122E28, v6);
        std::wstring::_Tidy_deallocate(v49);
        v7 = Utility::ToLower(v51, Src);
        v8 = std::operator+<unsigned short>(v49, v7, L"\\");
        std::vector<std::wstring>::push_back(qword_180122E28, v8);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::_Tidy_deallocate(v51);
        std::wstring::_Tidy_deallocate(Src);
      }
      UserProfilePaths = (__int64 *)Utility::GetUserProfilePaths();
      v10 = *UserProfilePaths;
      v11 = UserProfilePaths[1];
      if ( *UserProfilePaths != v11 )
      {
        do
        {
          v12 = Utility::ToLower(v48, v10);
          std::vector<std::wstring>::push_back(qword_180122E28, v12);
          std::wstring::_Tidy_deallocate(v48);
          v13 = Utility::ToLower(v47, v10);
          v14 = std::operator+<unsigned short>(v48, v13, L"\\");
          std::vector<std::wstring>::push_back(qword_180122E28, v14);
          std::wstring::_Tidy_deallocate(v48);
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::wstring(Src, v10);
          std::wstring::_Append<unsigned short>(Src);
          v15 = Utility::ToLower(v47, Src);
          std::vector<std::wstring>::push_back(qword_180122E28, v15);
          std::wstring::_Tidy_deallocate(v47);
          v16 = Utility::ToLower(v48, Src);
          v17 = std::operator+<unsigned short>(v47, v16, L"\\");
          std::vector<std::wstring>::push_back(qword_180122E28, v17);
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::_Tidy_deallocate(v48);
          std::wstring::wstring(v52, Src);
          std::wstring::_Append<unsigned short>(v52);
          v18 = Utility::ToLower(v47, v52);
          std::vector<std::wstring>::push_back(qword_180122E28, v18);
          std::wstring::_Tidy_deallocate(v47);
          v19 = Utility::ToLower(v48, v52);
          v20 = std::operator+<unsigned short>(v47, v19, L"\\");
          std::vector<std::wstring>::push_back(qword_180122E28, v20);
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::_Tidy_deallocate(v48);
          v21 = Utility::ToLower(v48, v52);
          v22 = std::operator+<unsigned short>(v47, v21, L"\\.");
          std::vector<std::wstring>::push_back(qword_180122E28, v22);
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::_Tidy_deallocate(v48);
          std::wstring::wstring(v49, v52);
          std::wstring::_Append<unsigned short>(v49);
          v23 = Utility::ToLower(v47, v49);
          std::vector<std::wstring>::push_back(qword_180122E28, v23);
          std::wstring::_Tidy_deallocate(v47);
          v24 = Utility::ToLower(v48, v49);
          v25 = std::operator+<unsigned short>(v47, v24, L"\\");
          std::vector<std::wstring>::push_back(qword_180122E28, v25);
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::_Tidy_deallocate(v48);
          v26 = Utility::ToLower(v48, v49);
          v27 = std::operator+<unsigned short>(v47, v26, L"\\.");
          std::vector<std::wstring>::push_back(qword_180122E28, v27);
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::_Tidy_deallocate(v48);
          std::wstring::wstring(v51, v52);
          std::wstring::_Append<unsigned short>(v51);
          v28 = Utility::ToLower(v47, v51);
          std::vector<std::wstring>::push_back(qword_180122E28, v28);
          std::wstring::_Tidy_deallocate(v47);
          v29 = Utility::ToLower(v48, v51);
          v30 = std::operator+<unsigned short>(v47, v29, L"\\");
          std::vector<std::wstring>::push_back(qword_180122E28, v30);
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::_Tidy_deallocate(v48);
          v31 = Utility::ToLower(v48, v51);
          v32 = std::operator+<unsigned short>(v47, v31, L"\\.");
          std::vector<std::wstring>::push_back(qword_180122E28, v32);
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::_Tidy_deallocate(v48);
          std::wstring::wstring(v53, v10);
          std::wstring::_Append<unsigned short>(v53);
          v33 = Utility::ToLower(v47, v53);
          std::vector<std::wstring>::push_back(qword_180122E28, v33);
          std::wstring::_Tidy_deallocate(v47);
          v34 = Utility::ToLower(v48, v53);
          v35 = std::operator+<unsigned short>(v47, v34, L"\\");
          std::vector<std::wstring>::push_back(qword_180122E28, v35);
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::_Tidy_deallocate(v48);
          v36 = Utility::ToLower(v48, v53);
          v37 = std::operator+<unsigned short>(v47, v36, L"\\.");
          std::vector<std::wstring>::push_back(qword_180122E28, v37);
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::_Tidy_deallocate(v48);
          std::wstring::wstring(v54, v10);
          std::wstring::_Append<unsigned short>(v54);
          v38 = Utility::ToLower(v47, v54);
          std::vector<std::wstring>::push_back(qword_180122E28, v38);
          std::wstring::_Tidy_deallocate(v47);
          v39 = Utility::ToLower(v48, v54);
          v40 = std::operator+<unsigned short>(v47, v39, L"\\");
          std::vector<std::wstring>::push_back(qword_180122E28, v40);
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::_Tidy_deallocate(v48);
          v41 = Utility::ToLower(v48, v54);
          v42 = std::operator+<unsigned short>(v47, v41, L"\\.");
          std::vector<std::wstring>::push_back(qword_180122E28, v42);
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::_Tidy_deallocate(v48);
          std::wstring::_Tidy_deallocate(v54);
          std::wstring::_Tidy_deallocate(v53);
          std::wstring::_Tidy_deallocate(v51);
          std::wstring::_Tidy_deallocate(v49);
          std::wstring::_Tidy_deallocate(v52);
          std::wstring::_Tidy_deallocate(Src);
          v10 += 32;
        }
        while ( v10 != v11 );
      }
      byte_180120D9C = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v46);
  }
  return qword_180122E28;
}

```

## disassembly

```asm
0x1800cbed4  push    rbp
0x1800cbed6  push    rbx
0x1800cbed7  push    rdi
0x1800cbed8  push    r12
0x1800cbeda  push    r14
0x1800cbedc  push    r15
0x1800cbede  lea     rbp, [rsp-48h]
0x1800cbee3  sub     rsp, 148h
0x1800cbeea  mov     rax, cs:__security_cookie
0x1800cbef1  xor     rax, rsp
0x1800cbef4  mov     [rbp+70h+var_38], rax
0x1800cbef8  mov     ecx, cs:_tls_index
0x1800cbefe  mov     rax, gs:58h
0x1800cbf07  mov     edx, 4
0x1800cbf0c  mov     rax, [rax+rcx*8]
0x1800cbf10  mov     eax, [rdx+rax]
0x1800cbf13  cmp     cs:dword_180122E20, eax
0x1800cbf19  jg      loc_1800CC719
0x1800cbf1f  lea     r14, qword_180122E28
0x1800cbf26  cmp     cs:byte_180120D9C, 0
0x1800cbf2d  jz      loc_1800CC6F9
0x1800cbf33  lea     rbx, stru_180122B70
0x1800cbf3a  mov     rcx, rbx; SRWLock
0x1800cbf3d  call    cs:__imp_AcquireSRWLockExclusive
0x1800cbf43  mov     [rsp+170h+var_140], rbx
0x1800cbf48  cmp     cs:byte_180120D9C, 0
0x1800cbf4f  jz      loc_1800CC6EF
0x1800cbf55  mov     [rsp+170h+ppszPath], 0
0x1800cbf5e  xor     edx, edx
0x1800cbf60  lea     rcx, [rsp+170h+ppszPath]
0x1800cbf65  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800cbf6a  lea     r9, [rsp+170h+ppszPath]; ppszPath
0x1800cbf6f  xor     r8d, r8d; hToken
0x1800cbf72  xor     edx, edx; dwFlags
0x1800cbf74  lea     rcx, FOLDERID_ProgramFilesX86; rfid
0x1800cbf7b  call    cs:__imp_SHGetKnownFolderPath
0x1800cbf81  lea     r15, Source; "\\"
0x1800cbf88  test    eax, eax
0x1800cbf8a  js      loc_1800CC026
0x1800cbf90  mov     rdx, [rsp+170h+ppszPath]
0x1800cbf95  lea     rcx, [rbp+70h+Src]
0x1800cbf99  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cbf9e  nop
0x1800cbf9f  lea     rdx, [rbp+70h+Src]
0x1800cbfa3  lea     rcx, [rsp+170h+var_F8]
0x1800cbfa8  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cbfad  nop
0x1800cbfae  mov     rdx, rax
0x1800cbfb1  mov     rcx, r14
0x1800cbfb4  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cbfb9  nop
0x1800cbfba  lea     rcx, [rsp+170h+var_F8]
0x1800cbfbf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cbfc4  nop
0x1800cbfc5  lea     rcx, [rbp+70h+Src]
0x1800cbfc9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cbfce  mov     rdx, [rsp+170h+ppszPath]
0x1800cbfd3  lea     rcx, [rbp+70h+Src]
0x1800cbfd7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cbfdc  nop
0x1800cbfdd  lea     rdx, [rbp+70h+Src]
0x1800cbfe1  lea     rcx, [rbp+70h+var_B8]
0x1800cbfe5  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cbfea  nop
0x1800cbfeb  mov     r8, r15
0x1800cbfee  mov     rdx, rax
0x1800cbff1  lea     rcx, [rsp+170h+var_F8]
0x1800cbff6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800cbffb  nop
0x1800cbffc  mov     rdx, rax
0x1800cbfff  mov     rcx, r14
0x1800cc002  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cc007  nop
0x1800cc008  lea     rcx, [rsp+170h+var_F8]
0x1800cc00d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc012  nop
0x1800cc013  lea     rcx, [rbp+70h+var_B8]
0x1800cc017  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc01c  nop
0x1800cc01d  lea     rcx, [rbp+70h+Src]
0x1800cc021  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc026  mov     [rsp+170h+var_150], 0
0x1800cc02f  xor     edx, edx
0x1800cc031  lea     rcx, [rsp+170h+var_150]
0x1800cc036  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800cc03b  lea     r9, [rsp+170h+var_150]; ppszPath
0x1800cc040  xor     r8d, r8d; hToken
0x1800cc043  xor     edx, edx; dwFlags
0x1800cc045  lea     rcx, FOLDERID_ProgramFiles; rfid
0x1800cc04c  call    cs:__imp_SHGetKnownFolderPath
0x1800cc052  test    eax, eax
0x1800cc054  js      loc_1800CC185
0x1800cc05a  mov     rdx, [rsp+170h+var_150]
0x1800cc05f  lea     rcx, [rsp+170h+var_F8]
0x1800cc064  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cc069  nop
0x1800cc06a  lea     rdx, [rsp+170h+var_F8]
0x1800cc06f  lea     rcx, [rbp+70h+var_B8]
0x1800cc073  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cc078  nop
0x1800cc079  mov     rdx, rax
0x1800cc07c  mov     rcx, r14
0x1800cc07f  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cc084  nop
0x1800cc085  lea     rcx, [rbp+70h+var_B8]
0x1800cc089  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc08e  nop
0x1800cc08f  lea     rcx, [rsp+170h+var_F8]
0x1800cc094  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc099  mov     rdx, [rsp+170h+var_150]
0x1800cc09e  lea     rcx, [rsp+170h+var_F8]
0x1800cc0a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cc0a8  nop
0x1800cc0a9  lea     rdx, [rsp+170h+var_F8]
0x1800cc0ae  lea     rcx, [rbp+70h+var_78]
0x1800cc0b2  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cc0b7  nop
0x1800cc0b8  mov     r8, r15
0x1800cc0bb  mov     rdx, rax
0x1800cc0be  lea     rcx, [rbp+70h+var_B8]
0x1800cc0c2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800cc0c7  nop
0x1800cc0c8  mov     rdx, rax
0x1800cc0cb  mov     rcx, r14
0x1800cc0ce  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cc0d3  nop
0x1800cc0d4  lea     rcx, [rbp+70h+var_B8]
0x1800cc0d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc0dd  nop
0x1800cc0de  lea     rcx, [rbp+70h+var_78]
0x1800cc0e2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc0e7  nop
0x1800cc0e8  lea     rcx, [rsp+170h+var_F8]
0x1800cc0ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc0f2  mov     rdx, [rsp+170h+var_150]
0x1800cc0f7  lea     rcx, [rbp+70h+Src]
0x1800cc0fb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cc100  nop
0x1800cc101  mov     r8d, 0Ch
0x1800cc107  lea     rdx, aWindowsapps; "\\WindowsApps"
0x1800cc10e  lea     rcx, [rbp+70h+Src]; Src
0x1800cc112  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800cc117  lea     rdx, [rbp+70h+Src]
0x1800cc11b  lea     rcx, [rsp+170h+var_F8]
0x1800cc120  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cc125  nop
0x1800cc126  mov     rdx, rax
0x1800cc129  mov     rcx, r14
0x1800cc12c  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cc131  nop
0x1800cc132  lea     rcx, [rsp+170h+var_F8]
0x1800cc137  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc13c  lea     rdx, [rbp+70h+Src]
0x1800cc140  lea     rcx, [rbp+70h+var_B8]
0x1800cc144  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cc149  nop
0x1800cc14a  mov     r8, r15
0x1800cc14d  mov     rdx, rax
0x1800cc150  lea     rcx, [rsp+170h+var_F8]
0x1800cc155  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800cc15a  nop
0x1800cc15b  mov     rdx, rax
0x1800cc15e  mov     rcx, r14
0x1800cc161  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cc166  nop
0x1800cc167  lea     rcx, [rsp+170h+var_F8]
0x1800cc16c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc171  nop
0x1800cc172  lea     rcx, [rbp+70h+var_B8]
0x1800cc176  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc17b  nop
0x1800cc17c  lea     rcx, [rbp+70h+Src]
0x1800cc180  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc185  call    ?GetUserProfilePaths@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Utility::GetUserProfilePaths(void)
0x1800cc18a  mov     rbx, [rax]
0x1800cc18d  mov     rdi, [rax+8]
0x1800cc191  cmp     rbx, rdi
0x1800cc194  jz      loc_1800CC6D2
0x1800cc19a  lea     r12, asc_1801097AC; "\\."
0x1800cc1a1  mov     rdx, rbx
0x1800cc1a4  lea     rcx, [rsp+170h+var_118]
0x1800cc1a9  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cc1ae  nop
0x1800cc1af  mov     rdx, rax
0x1800cc1b2  mov     rcx, r14
0x1800cc1b5  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cc1ba  nop
0x1800cc1bb  lea     rcx, [rsp+170h+var_118]
0x1800cc1c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc1c5  mov     rdx, rbx
0x1800cc1c8  lea     rcx, [rsp+170h+var_138]
0x1800cc1cd  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cc1d2  nop
0x1800cc1d3  mov     r8, r15
0x1800cc1d6  mov     rdx, rax
0x1800cc1d9  lea     rcx, [rsp+170h+var_118]
0x1800cc1de  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800cc1e3  nop
0x1800cc1e4  mov     rdx, rax
0x1800cc1e7  mov     rcx, r14
0x1800cc1ea  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cc1ef  nop
0x1800cc1f0  lea     rcx, [rsp+170h+var_118]
0x1800cc1f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc1fa  nop
0x1800cc1fb  lea     rcx, [rsp+170h+var_138]
0x1800cc200  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc205  mov     rdx, rbx
0x1800cc208  lea     rcx, [rbp+70h+Src]
0x1800cc20c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800cc211  nop
0x1800cc212  mov     r8d, 8
0x1800cc218  lea     rdx, aAppdata; "\\AppData"
0x1800cc21f  lea     rcx, [rbp+70h+Src]; Src
0x1800cc223  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800cc228  lea     rdx, [rbp+70h+Src]
0x1800cc22c  lea     rcx, [rsp+170h+var_138]
0x1800cc231  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cc236  nop
0x1800cc237  mov     rdx, rax
0x1800cc23a  mov     rcx, r14
0x1800cc23d  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cc242  nop
0x1800cc243  lea     rcx, [rsp+170h+var_138]
0x1800cc248  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc24d  lea     rdx, [rbp+70h+Src]
0x1800cc251  lea     rcx, [rsp+170h+var_118]
0x1800cc256  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cc25b  nop
0x1800cc25c  mov     r8, r15
0x1800cc25f  mov     rdx, rax
0x1800cc262  lea     rcx, [rsp+170h+var_138]
0x1800cc267  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800cc26c  nop
0x1800cc26d  mov     rdx, rax
0x1800cc270  mov     rcx, r14
0x1800cc273  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cc278  nop
0x1800cc279  lea     rcx, [rsp+170h+var_138]
0x1800cc27e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc283  nop
0x1800cc284  lea     rcx, [rsp+170h+var_118]
0x1800cc289  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc28e  lea     rdx, [rbp+70h+Src]
0x1800cc292  lea     rcx, [rbp+70h+var_98]
0x1800cc296  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800cc29b  nop
0x1800cc29c  mov     r8d, 6
0x1800cc2a2  lea     rdx, aLocal; "\\Local"
0x1800cc2a9  lea     rcx, [rbp+70h+var_98]; Src
0x1800cc2ad  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800cc2b2  lea     rdx, [rbp+70h+var_98]
0x1800cc2b6  lea     rcx, [rsp+170h+var_138]
0x1800cc2bb  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cc2c0  nop
0x1800cc2c1  mov     rdx, rax
0x1800cc2c4  mov     rcx, r14
0x1800cc2c7  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cc2cc  nop
0x1800cc2cd  lea     rcx, [rsp+170h+var_138]
0x1800cc2d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc2d7  lea     rdx, [rbp+70h+var_98]
0x1800cc2db  lea     rcx, [rsp+170h+var_118]
0x1800cc2e0  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cc2e5  nop
0x1800cc2e6  mov     r8, r15
0x1800cc2e9  mov     rdx, rax
0x1800cc2ec  lea     rcx, [rsp+170h+var_138]
0x1800cc2f1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800cc2f6  nop
0x1800cc2f7  mov     rdx, rax
0x1800cc2fa  mov     rcx, r14
0x1800cc2fd  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cc302  nop
0x1800cc303  lea     rcx, [rsp+170h+var_138]
0x1800cc308  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc30d  nop
0x1800cc30e  lea     rcx, [rsp+170h+var_118]
0x1800cc313  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc318  lea     rdx, [rbp+70h+var_98]
0x1800cc31c  lea     rcx, [rsp+170h+var_118]
0x1800cc321  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cc326  nop
0x1800cc327  mov     r8, r12
0x1800cc32a  mov     rdx, rax
0x1800cc32d  lea     rcx, [rsp+170h+var_138]
0x1800cc332  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800cc337  nop
0x1800cc338  mov     rdx, rax
0x1800cc33b  mov     rcx, r14
0x1800cc33e  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cc343  nop
0x1800cc344  lea     rcx, [rsp+170h+var_138]
0x1800cc349  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc34e  nop
0x1800cc34f  lea     rcx, [rsp+170h+var_118]
0x1800cc354  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc359  lea     rdx, [rbp+70h+var_98]
0x1800cc35d  lea     rcx, [rsp+170h+var_F8]
0x1800cc362  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
  ... truncated ...
```
