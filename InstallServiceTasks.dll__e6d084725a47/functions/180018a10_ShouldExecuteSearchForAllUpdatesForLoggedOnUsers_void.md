# ShouldExecuteSearchForAllUpdatesForLoggedOnUsers(void)

- ea: `0x180018a10`
- end: `0x180018c0b`
- name: `?ShouldExecuteSearchForAllUpdatesForLoggedOnUsers@@YA_NXZ`
- size: `507`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180016044`

## callees

- `0x18000c520`
- `0x180012118`
- `0x180014300`
- `0x180014d48`
- `0x180015e78`
- `0x180015ed0`
- `0x1800170dc`
- `0x18001719c`
- `0x1800176e0`
- `0x180018a10`
- `0x180018c14`
- `0x180029190`
- `0x180034240`
- `0x180034498`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018aa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018aa5`

## string_xrefs

- `0x180018a5a`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x180018ad9`: `HasFrameworkUpdates`
- `0x180018abe`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State`
- `0x180018a39`: `OOBE completion time has lapsed 2 hours for AutoScanForUpdates to run.`
- `0x180018a4d`: `ShouldExecuteSearchForAllUpdatesForLoggedOnUsers`

## pseudocode

```c
char ShouldExecuteSearchForAllUpdatesForLoggedOnUsers(void)
{
  char result; // al
  const char *v1; // r9
  TokenHelpers *v2; // rcx
  HSTRING *LocalSystemSidString; // rbx
  Microsoft::WRL::Wrappers::Details **TokenSid; // rax
  HSTRING v5; // r8
  __int64 RegistryLocation; // rax
  __int64 v7; // rcx
  char v8; // bl
  unsigned __int64 v9; // rcx
  __int64 i; // rbx
  unsigned __int64 v11; // rdi
  char v12; // al
  _QWORD v13[2]; // [rsp+40h] [rbp-38h] BYREF
  __int128 v14; // [rsp+50h] [rbp-28h] BYREF
  __int64 v15; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HSTRING string; // [rsp+80h] [rbp+8h] BYREF

  try
  {
    result = IsOobeTwoHoursTimeLapsed();
    if ( result )
    {
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
        0x1D2u,
        "ShouldExecuteSearchForAllUpdatesForLoggedOnUsers",
        -1,
        L"OOBE completion time has lapsed 2 hours for AutoScanForUpdates to run.",
        0,
        0);
      TokenHelpers::GetSelfToken(v13);
      LocalSystemSidString = (HSTRING *)TokenHelpers::GetLocalSystemSidString(v2);
      TokenSid = (Microsoft::WRL::Wrappers::Details **)TokenHelpers::GetTokenSid(&string, v13);
      LODWORD(LocalSystemSidString) = Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                        *TokenSid,
                                        *LocalSystemSidString,
                                        v5);
      WindowsDeleteString(string);
      if ( (_DWORD)LocalSystemSidString )
      {
        LODWORD(string) = 0;
        RegistryLocation = _InitOnceAndGetRegistryLocation(
                             &qword_18006A458,
                             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State");
        if ( (unsigned int)Registry::GetValue<unsigned long>(v7, RegistryLocation, L"HasFrameworkUpdates", &string) == 1 )
        {
LABEL_5:
          v13[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
          Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v13);
          result = 1;
        }
        else
        {
          v8 = ShouldExecuteSearchForUser(v13);
          v13[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
          Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v13);
          result = v8;
        }
      }
      else
      {
        TokenHelpers::GetAllLoggedInUserTokens(&v14);
        __SET_PAIR__(v11, v9, v14);
        for ( i = v14; i != v11; i += 16 )
        {
          v12 = ShouldExecuteSearchForUser(i);
          v9 = v14;
          if ( v12 )
          {
            if ( (_QWORD)v14 )
            {
              std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>>(
                v14,
                *((_QWORD *)&v14 + 1));
              std::_Deallocate<16>(v14, (v15 - v14) & 0xFFFFFFFFFFFFFFF0uLL);
              v14 = 0;
              v15 = 0;
            }
            goto LABEL_5;
          }
        }
        if ( v9 )
        {
          ((void (*)(void))std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>>)();
          std::_Deallocate<16>(v14, (v15 - v14) & 0xFFFFFFFFFFFFFFF0uLL);
        }
        v13[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v13);
        result = 0;
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1E8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
      v1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180018a10  mov     [rsp+arg_8], rbx
0x180018a15  push    rdi
0x180018a16  sub     rsp, 70h
0x180018a1a  call    ?IsOobeTwoHoursTimeLapsed@@YA_NXZ; IsOobeTwoHoursTimeLapsed(void)
0x180018a1f  test    al, al
0x180018a21  jz      loc_180018BFC
0x180018a27  mov     [rsp+78h+var_40], 0; unsigned __int16 *
0x180018a30  mov     [rsp+78h+var_48], 0; char *
0x180018a39  lea     rax, aOobeCompletion; "OOBE completion time has lapsed 2 hours"...
0x180018a40  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x180018a45  mov     [rsp+78h+var_58], 0FFFFFFFFh; int
0x180018a4d  lea     r9, aShouldexecutes_1; "ShouldExecuteSearchForAllUpdatesForLogg"...
0x180018a54  mov     r8d, 1D2h; unsigned int
0x180018a5a  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x180018a61  mov     ecx, 3; unsigned int
0x180018a66  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180018a6b  lea     rcx, [rsp+78h+var_38]
0x180018a70  call    ?GetSelfToken@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; TokenHelpers::GetSelfToken(void)
0x180018a75  nop
0x180018a76  call    ?GetLocalSystemSidString@TokenHelpers@@YAAEBVHString@Wrappers@WRL@Microsoft@@XZ; TokenHelpers::GetLocalSystemSidString(void)
0x180018a7b  mov     rbx, rax
0x180018a7e  lea     rdx, [rsp+78h+var_38]
0x180018a83  lea     rcx, [rsp+78h+string]
0x180018a8b  call    ?GetTokenSid@TokenHelpers@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@345@@Z; TokenHelpers::GetTokenSid(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180018a90  mov     rdx, [rbx]; HSTRING
0x180018a93  mov     rcx, [rax]; this
0x180018a96  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180018a9b  mov     ebx, eax
0x180018a9d  mov     rcx, [rsp+78h+string]; string
0x180018aa5  call    cs:__imp_WindowsDeleteString
0x180018aab  test    ebx, ebx
0x180018aad  jz      loc_180018B33
0x180018ab3  mov     dword ptr [rsp+78h+string], 0
0x180018abe  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180018ac5  lea     rcx, qword_18006A458
0x180018acc  call    ?_InitOnceAndGetRegistryLocation@@YAPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; _InitOnceAndGetRegistryLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x180018ad1  lea     r9, [rsp+78h+string]
0x180018ad9  lea     r8, aHasframeworkup; "HasFrameworkUpdates"
0x180018ae0  mov     rdx, rax
0x180018ae3  call    ??$GetValue@K@Registry@@YAKPEAUHKEY__@@PEBG1$$QEAK@Z; Registry::GetValue<ulong>(HKEY__ *,ushort const *,ushort const *,ulong &&)
0x180018ae8  cmp     eax, 1
0x180018aeb  jnz     short loc_180018B0A
0x180018aed  lea     rcx, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180018af4  mov     [rsp+78h+var_38], rcx
0x180018af9  lea     rcx, [rsp+78h+var_38]
0x180018afe  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180018b03  mov     al, 1
0x180018b05  jmp     loc_180018BFC
0x180018b0a  lea     rcx, [rsp+78h+var_38]
0x180018b0f  call    ?ShouldExecuteSearchForUser@@YA_NAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; ShouldExecuteSearchForUser(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180018b14  mov     bl, al
0x180018b16  lea     rcx, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180018b1d  mov     [rsp+78h+var_38], rcx
0x180018b22  lea     rcx, [rsp+78h+var_38]
0x180018b27  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180018b2c  mov     al, bl
0x180018b2e  jmp     loc_180018BFC
0x180018b33  lea     rcx, [rsp+78h+var_28]
0x180018b38  call    ?GetAllLoggedInUserTokens@TokenHelpers@@YA?AV?$vector@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@XZ; TokenHelpers::GetAllLoggedInUserTokens(void)
0x180018b3d  mov     rcx, qword ptr [rsp+78h+var_28]
0x180018b42  mov     rbx, rcx
0x180018b45  mov     rdx, qword ptr [rsp+78h+var_28+8]
0x180018b4a  mov     rdi, rdx
0x180018b4d  cmp     rbx, rdi
0x180018b50  jz      short loc_180018BBF
0x180018b52  mov     rcx, rbx
0x180018b55  call    ?ShouldExecuteSearchForUser@@YA_NAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; ShouldExecuteSearchForUser(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180018b5a  mov     rcx, qword ptr [rsp+78h+var_28]
0x180018b5f  test    al, al
0x180018b61  jz      short loc_180018BB4
0x180018b63  test    rcx, rcx
0x180018b66  jz      short loc_180018B9A
0x180018b68  mov     rdx, qword ptr [rsp+78h+var_28+8]
0x180018b6d  call    ??$_Destroy_range@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@YAXPEAV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAV1234@AEAV?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>>(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> *,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> * const,std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>> &)
0x180018b72  mov     rcx, qword ptr [rsp+78h+var_28]
0x180018b77  mov     rdx, [rsp+78h+var_18]
0x180018b7c  sub     rdx, rcx
0x180018b7f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180018b83  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018b88  xorps   xmm0, xmm0
0x180018b8b  movdqu  [rsp+78h+var_28], xmm0
0x180018b91  mov     [rsp+78h+var_18], 0
0x180018b9a  lea     rcx, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180018ba1  mov     [rsp+78h+var_38], rcx
0x180018ba6  lea     rcx, [rsp+78h+var_38]
0x180018bab  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180018bb0  mov     al, 1
0x180018bb2  jmp     short loc_180018BFC
0x180018bb4  add     rbx, 10h
0x180018bb8  mov     rdx, qword ptr [rsp+78h+var_28+8]
0x180018bbd  jmp     short loc_180018B4D
0x180018bbf  test    rcx, rcx
0x180018bc2  jz      short loc_180018BE0
0x180018bc4  call    ??$_Destroy_range@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@YAXPEAV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAV1234@AEAV?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>>(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> *,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> * const,std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>> &)
0x180018bc9  mov     rcx, qword ptr [rsp+78h+var_28]
0x180018bce  mov     rdx, [rsp+78h+var_18]
0x180018bd3  sub     rdx, rcx
0x180018bd6  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180018bda  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018bdf  nop
0x180018be0  lea     rcx, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180018be7  mov     [rsp+78h+var_38], rcx
0x180018bec  lea     rcx, [rsp+78h+var_38]
0x180018bf1  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180018bf6  xor     al, al
0x180018bf8  jmp     short loc_180018BFC
0x180018bfa  xor     al, al
0x180018bfc  mov     rbx, [rsp+78h+arg_8]
0x180018c04  add     rsp, 70h
0x180018c08  pop     rdi
0x180018c09  retn
```
