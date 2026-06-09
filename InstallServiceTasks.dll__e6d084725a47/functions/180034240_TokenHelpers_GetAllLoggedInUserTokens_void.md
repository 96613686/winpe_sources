# TokenHelpers::GetAllLoggedInUserTokens(void)

- ea: `0x180034240`
- end: `0x18003448f`
- name: `?GetAllLoggedInUserTokens@TokenHelpers@@YA?AV?$vector@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@XZ`
- size: `591`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `16`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800150ac`
- `0x180017b80`
- `0x180018a10`
- `0x180027178`

## callees

- `0x180010150`
- `0x180012118`
- `0x180015e78`
- `0x18001aba0`
- `0x180033e38`
- `0x180033e60`
- `0x180033fa8`
- `0x1800340b8`
- `0x1800340d0`
- `0x1800340ec`
- `0x180034104`
- `0x180034174`
- `0x180034194`
- `0x180034240`
- `0x1800346f8`
- `0x180034784`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180034302`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180034302`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800343f6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800343f6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18003429f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18003429f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x180034335`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x180034335`

## string_xrefs

- `0x1800342b0`: `onecoreuap\enduser\winstore\servicescommon\lib\tokenhelpers.cpp`
- `0x1800343b2`: `onecoreuap\enduser\winstore\servicescommon\lib\tokenhelpers.cpp`
- `0x18003447d`: `onecoreuap\enduser\winstore\servicescommon\lib\tokenhelpers.cpp`
- `0x180034395`: `No DSMA token found`
- `0x1800343a5`: `TokenHelpers::GetAllLoggedInUserTokens`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall TokenHelpers::GetAllLoggedInUserTokens(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // r8
  int v5; // eax
  TokenHelpers *v6; // rcx
  _BOOL8 IsDSMASupported; // rdi
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rdx
  _QWORD *v11; // rdi
  __int64 i; // rsi
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rdx
  int v17; // [rsp+20h] [rbp-60h]
  _QWORD *v18; // [rsp+48h] [rbp-38h] BYREF
  __int64 v19; // [rsp+50h] [rbp-30h]
  void **v20; // [rsp+58h] [rbp-28h] BYREF
  __int64 v21; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v22[3]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  __int64 v24; // [rsp+A8h] [rbp+28h] BYREF

  std::vector<Microsoft::WRL::ComPtr<AppInstallItemTracker>>::vector<Microsoft::WRL::ComPtr<AppInstallItemTracker>>(a1);
  wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>(&v18);
  v2 = wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::operator&(&v18);
  v3 = wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address<unsigned long>(
         &v18,
         v22,
         v2);
  v5 = UMgrEnumerateSessionUsers(v3 + 8, v4);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\tokenhelpers.cpp",
      (const char *)(unsigned int)v5,
      v17);
  wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<unsigned long>::~size_address_ptr<unsigned long>(v22);
  IsDSMASupported = TokenHelpers::IsDSMASupported(v6);
  v24 = IsDSMASupported + v19;
  if ( IsDSMASupported + v19 > (unsigned __int64)((__int64)(a1[2] - *a1) >> 4) )
  {
    if ( (unsigned __int64)(IsDSMASupported + v19) > 0xFFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector too long");
    std::vector<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>::_Reallocate<0>(
      a1,
      &v24);
  }
  if ( IsDSMASupported )
  {
    v20 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    v21 = 0;
    v8 = UMgrQueryDefaultAccountToken(&v21);
    if ( v8 < 0 )
    {
      if ( v8 != -2147023584 )
        LogSimpleMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\servicescommon\\lib\\tokenhelpers.cpp",
          0x75u,
          "TokenHelpers::GetAllLoggedInUserTokens",
          v8,
          L"No DSMA token found",
          0,
          0);
    }
    else
    {
      v9 = TokenHelpers::DuplicateTokenWithRequiredPrivileges(v22, &v20);
      v10 = a1[1];
      if ( v10 == a1[2] )
        std::vector<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>(
          a1,
          v10,
          v9);
      else
        std::vector<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>::_Emplace_back_with_unused_capacity<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>(
          a1,
          v9);
      v22[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v22);
    }
    v20 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v20);
  }
  v11 = v18;
  for ( i = wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::end(&v18);
        v11 != (_QWORD *)i;
        v11 += 2 )
  {
    v20 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    v21 = 0;
    v13 = UMgrQueryUserToken(*v11, &v21);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\tokenhelpers.cpp",
        (const char *)(unsigned int)v13,
        v17);
    v14 = TokenHelpers::DuplicateTokenWithRequiredPrivileges(v22, &v20);
    v15 = a1[1];
    if ( v15 == a1[2] )
      std::vector<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>(
        a1,
        v15,
        v14);
    else
      std::vector<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>::_Emplace_back_with_unused_capacity<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>(
        a1,
        v14);
    v22[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v22);
    v20 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v20);
  }
  wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>(&v18);
  return a1;
}

```

## disassembly

```asm
0x180034240  mov     [rsp-18h+arg_10], rbx
0x180034245  mov     [rsp-18h+arg_18], rsi
0x18003424a  mov     [rsp-18h+arg_0], rcx
0x18003424f  push    rbp
0x180034250  push    rdi
0x180034251  push    r14
0x180034253  mov     rbp, rsp
0x180034256  sub     rsp, 80h
0x18003425d  mov     rbx, rcx
0x180034260  mov     [rbp+var_40], 0
0x180034267  call    ??0?$vector@V?$ComPtr@VAppInstallItemTracker@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VAppInstallItemTracker@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<AppInstallItemTracker>>::vector<Microsoft::WRL::ComPtr<AppInstallItemTracker>>(void)
0x18003426c  mov     esi, 1
0x180034271  mov     [rbp+var_40], esi
0x180034274  lea     rcx, [rbp+var_38]
0x180034278  call    ??0?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>(void)
0x18003427d  nop
0x18003427e  lea     rcx, [rbp+var_38]
0x180034282  call    ??I?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAPEAPEAU_SESSION_USER_CONTEXT@@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::operator&(void)
0x180034287  mov     r8, rax
0x18003428a  lea     rdx, [rbp+var_18]
0x18003428e  lea     rcx, [rbp+var_38]
0x180034292  call    ??$size_address@K@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA?AU?$size_address_ptr@K@01@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address<ulong>(void)
0x180034297  nop
0x180034298  lea     rcx, [rax+8]
0x18003429c  mov     rdx, r8
0x18003429f  call    cs:__imp_UMgrEnumerateSessionUsers
0x1800342a5  mov     rcx, [rbp+18h]; this
0x1800342a9  test    eax, eax
0x1800342ab  jns     short loc_1800342C0
0x1800342ad  mov     r9d, eax; char *
0x1800342b0  lea     r8, aOnecoreuapEndu_2; "onecoreuap\\enduser\\winstore\\services"...
0x1800342b7  lea     edx, [rsi+62h]; void *
0x1800342ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800342c0  lea     rcx, [rbp+var_18]
0x1800342c4  call    ??1?$size_address_ptr@K@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<ulong>::~size_address_ptr<ulong>(void)
0x1800342c9  call    ?IsDSMASupported@TokenHelpers@@YA_NXZ; TokenHelpers::IsDSMASupported(void)
0x1800342ce  movzx   edi, al
0x1800342d1  mov     rcx, [rbp+var_30]
0x1800342d5  add     rcx, rdi
0x1800342d8  mov     [rbp+arg_8], rcx
0x1800342dc  mov     rax, [rbx+10h]
0x1800342e0  sub     rax, [rbx]
0x1800342e3  sar     rax, 4
0x1800342e7  cmp     rcx, rax
0x1800342ea  jbe     short loc_180034315
0x1800342ec  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800342f6  cmp     rcx, rax
0x1800342f9  jbe     short loc_180034309
0x1800342fb  lea     rcx, aVectorTooLong; "vector too long"
0x180034302  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180034309  lea     rdx, [rbp+arg_8]
0x18003430d  mov     rcx, rbx
0x180034310  call    ??$_Reallocate@$0A@@?$vector@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@AEAAXAEA_K@Z; std::vector<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>::_Reallocate<0>(unsigned __int64 &)
0x180034315  lea     r14, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18003431c  test    dil, dil
0x18003431f  jz      loc_1800343CE
0x180034325  mov     [rbp+var_28], r14
0x180034329  mov     [rbp+var_20], 0
0x180034331  lea     rcx, [rbp+var_20]
0x180034335  call    cs:__imp_UMgrQueryDefaultAccountToken
0x18003433b  test    eax, eax
0x18003433d  js      short loc_18003437C
0x18003433f  lea     rdx, [rbp+var_28]
0x180034343  lea     rcx, [rbp+var_18]
0x180034347  call    ?DuplicateTokenWithRequiredPrivileges@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@AEBV2345@@Z; TokenHelpers::DuplicateTokenWithRequiredPrivileges(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x18003434c  nop
0x18003434d  mov     rdx, [rbx+8]
0x180034351  mov     rcx, rbx
0x180034354  cmp     rdx, [rbx+10h]
0x180034358  jz      short loc_180034364
0x18003435a  mov     rdx, rax
0x18003435d  call    ??$_Emplace_back_with_unused_capacity@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@?$vector@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@AEAAAEAV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@$$QEAV2345@@Z; std::vector<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>::_Emplace_back_with_unused_capacity<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> &&)
0x180034362  jmp     short loc_18003436D
0x180034364  mov     r8, rax
0x180034367  call    ??$_Emplace_reallocate@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@?$vector@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAV2345@$$QEAV2345@@Z; std::vector<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> * const,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> &&)
0x18003436c  nop
0x18003436d  mov     [rbp+var_18], r14
0x180034371  lea     rcx, [rbp+var_18]
0x180034375  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18003437a  jmp     short loc_1800343C1
0x18003437c  cmp     eax, 80070520h
0x180034381  jz      short loc_1800343C1
0x180034383  mov     [rsp+80h+var_48], 0; unsigned __int16 *
0x18003438c  mov     [rsp+80h+var_50], 0; char *
0x180034395  lea     rdx, aNoDsmaTokenFou; "No DSMA token found"
0x18003439c  mov     [rsp+80h+var_58], rdx; unsigned __int16 *
0x1800343a1  mov     [rsp+80h+var_60], eax; int
0x1800343a5  lea     r9, aTokenhelpersGe; "TokenHelpers::GetAllLoggedInUserTokens"
0x1800343ac  mov     r8d, 75h ; 'u'; unsigned int
0x1800343b2  lea     rdx, aOnecoreuapEndu_2; "onecoreuap\\enduser\\winstore\\services"...
0x1800343b9  mov     ecx, esi; unsigned int
0x1800343bb  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800343c0  nop
0x1800343c1  mov     [rbp+var_28], r14
0x1800343c5  lea     rcx, [rbp+var_28]
0x1800343c9  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x1800343ce  mov     rdi, [rbp+var_38]
0x1800343d2  lea     rcx, [rbp+var_38]
0x1800343d6  call    ?end@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAPEAU_SESSION_USER_CONTEXT@@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::end(void)
0x1800343db  mov     rsi, rax
0x1800343de  cmp     rdi, rax
0x1800343e1  jz      short loc_180034456
0x1800343e3  mov     [rbp+var_28], r14
0x1800343e7  mov     [rbp+var_20], 0
0x1800343ef  lea     rdx, [rbp+var_20]
0x1800343f3  mov     rcx, [rdi]
0x1800343f6  call    cs:__imp_UMgrQueryUserToken
0x1800343fc  mov     rcx, [rbp+18h]; this
0x180034400  test    eax, eax
0x180034402  js      short loc_18003447A
0x180034404  lea     rdx, [rbp+var_28]
0x180034408  lea     rcx, [rbp+var_18]
0x18003440c  call    ?DuplicateTokenWithRequiredPrivileges@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@AEBV2345@@Z; TokenHelpers::DuplicateTokenWithRequiredPrivileges(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180034411  nop
0x180034412  mov     rdx, [rbx+8]
0x180034416  mov     rcx, rbx
0x180034419  cmp     rdx, [rbx+10h]
0x18003441d  jz      short loc_180034429
0x18003441f  mov     rdx, rax
0x180034422  call    ??$_Emplace_back_with_unused_capacity@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@?$vector@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@AEAAAEAV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@$$QEAV2345@@Z; std::vector<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>::_Emplace_back_with_unused_capacity<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> &&)
0x180034427  jmp     short loc_180034432
0x180034429  mov     r8, rax
0x18003442c  call    ??$_Emplace_reallocate@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@?$vector@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAV2345@$$QEAV2345@@Z; std::vector<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> * const,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> &&)
0x180034431  nop
0x180034432  mov     [rbp+var_18], r14
0x180034436  lea     rcx, [rbp+var_18]
0x18003443a  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18003443f  nop
0x180034440  mov     [rbp+var_28], r14
0x180034444  lea     rcx, [rbp+var_28]
0x180034448  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18003444d  add     rdi, 10h
0x180034451  cmp     rdi, rsi
0x180034454  jnz     short loc_1800343E3
0x180034456  lea     rcx, [rbp+var_38]
0x18003445a  call    ??1?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>(void)
0x18003445f  mov     rax, rbx
0x180034462  lea     r11, [rsp+80h+var_s0]
0x18003446a  mov     rbx, [r11+30h]
0x18003446e  mov     rsi, [r11+38h]
0x180034472  mov     rsp, r11
0x180034475  pop     r14
0x180034477  pop     rdi
0x180034478  pop     rbp
0x180034479  retn
0x18003447a  mov     r9d, eax; char *
0x18003447d  lea     r8, aOnecoreuapEndu_2; "onecoreuap\\enduser\\winstore\\services"...
0x180034484  mov     edx, 7Eh ; '~'; void *
0x180034489  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
