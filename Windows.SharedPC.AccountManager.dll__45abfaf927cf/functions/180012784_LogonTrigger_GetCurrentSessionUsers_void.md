# LogonTrigger::GetCurrentSessionUsers(void)

- ea: `0x180012784`
- end: `0x180012953`
- name: `?GetCurrentSessionUsers@LogonTrigger@@SA?AV?$vector@U_SESSION_USER_CONTEXT@@V?$allocator@U_SESSION_USER_CONTEXT@@@std@@@std@@XZ`
- size: `463`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012f64`
- `0x1800133fc`

## callees

- `0x180003530`
- `0x18000402c`
- `0x1800041bc`
- `0x18000ccd4`
- `0x18000f454`
- `0x18001134c`
- `0x18001138c`
- `0x180011bb8`
- `0x180011d40`
- `0x180012534`
- `0x180012784`
- `0x180013040`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x1800127be`
- `ntdll!RtlIsMultiSessionSku` at `0x1800127be`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800127cc`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800127cc`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x1800127ee`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x1800127ee`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800128b7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800128b7`

## string_xrefs

- `0x1800127fc`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`
- `0x180012856`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`
- `0x18001288e`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`
- `0x1800128c8`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`

## pseudocode

```c
_QWORD *__fastcall LogonTrigger::GetCurrentSessionUsers(_QWORD *a1)
{
  const char *v2; // r9
  __int64 v3; // rdx
  int v5; // eax
  unsigned int i; // edi
  __int64 v7; // rdx
  int v9[2]; // [rsp+20h] [rbp-40h] BYREF
  _QWORD *v10; // [rsp+28h] [rbp-38h]
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  int v12; // [rsp+38h] [rbp-28h]
  int v13; // [rsp+3Ch] [rbp-24h]
  __int128 v14; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v10 = a1;
  std::vector<SessionUserInfo>::vector<SessionUserInfo>(a1);
  v9[1] = 1;
  if ( (unsigned __int8)RtlIsMultiSessionSku() || (unsigned __int8)RtlIsMultiUsersInSessionSku() )
  {
    if ( !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent()
      || !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
    {
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
        (const char *)0x8000FFFFLL,
        v9[0]);
    }
    v9[0] = 0;
    v11 = 0;
    v5 = UMgrEnumerateSessionUsers(v9, &v11);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD5,
        (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
        (const char *)(unsigned int)v5,
        v9[0]);
    for ( i = 0; i < v9[0]; ++i )
    {
      v14 = *(_OWORD *)(v11 + 16LL * i);
      if ( !IsWCOSSpecialAccount((const struct _SESSION_USER_CONTEXT *)&v14) )
      {
        v7 = a1[1];
        if ( v7 == a1[2] )
          std::vector<_SESSION_USER_CONTEXT>::_Emplace_reallocate<_SESSION_USER_CONTEXT const &>(a1, v7, &v14);
        else
          std::vector<_SESSION_USER_CONTEXT>::_Emplace_back_with_unused_capacity<_SESSION_USER_CONTEXT const &>(
            a1,
            &v14);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v11);
  }
  else
  {
    if ( !(unsigned __int8)IsQueryActiveSessionPresent() )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
        (const char *)0x8000FFFFLL,
        v9[0]);
    v9[0] = 0;
    if ( !(unsigned int)QueryActiveSession(v9) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xE4,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
        v2);
    v13 = 0;
    v11 = 0;
    v12 = v9[0];
    v3 = a1[1];
    if ( v3 == a1[2] )
      std::vector<_SESSION_USER_CONTEXT>::_Emplace_reallocate<_SESSION_USER_CONTEXT const &>(a1, v3, &v11);
    else
      std::vector<_SESSION_USER_CONTEXT>::_Emplace_back_with_unused_capacity<_SESSION_USER_CONTEXT const &>(a1, &v11);
  }
  return a1;
}

```

## disassembly

```asm
0x180012784  mov     [rsp-8+arg_8], rbx
0x180012789  mov     [rsp-8+arg_10], rdi
0x18001278e  push    rbp
0x18001278f  mov     rbp, rsp
0x180012792  sub     rsp, 60h
0x180012796  mov     rax, cs:__security_cookie
0x18001279d  xor     rax, rsp
0x1800127a0  mov     [rbp+var_10], rax
0x1800127a4  mov     rbx, rcx
0x1800127a7  mov     [rbp+var_38], rcx
0x1800127ab  mov     [rbp+var_3C], 0
0x1800127b2  call    ??0?$vector@USessionUserInfo@@V?$allocator@USessionUserInfo@@@std@@@std@@QEAA@XZ; std::vector<SessionUserInfo>::vector<SessionUserInfo>(void)
0x1800127b7  mov     [rbp+var_3C], 1
0x1800127be  call    cs:__imp_RtlIsMultiSessionSku
0x1800127c4  test    al, al
0x1800127c6  jnz     loc_180012868
0x1800127cc  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x1800127d2  test    al, al
0x1800127d4  jnz     loc_180012868
0x1800127da  call    IsQueryActiveSessionPresent
0x1800127df  test    al, al
0x1800127e1  jz      short loc_18001284C
0x1800127e3  mov     [rbp+var_40], 0
0x1800127ea  lea     rcx, [rbp+var_40]
0x1800127ee  call    cs:__imp_QueryActiveSession
0x1800127f4  test    eax, eax
0x1800127f6  jnz     short loc_18001280E
0x1800127f8  mov     rcx, [rbp+8]; this
0x1800127fc  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x180012803  mov     edx, 0E4h; void *
0x180012808  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001280e  mov     [rbp+var_24], 0
0x180012815  mov     [rbp+var_30], 0
0x18001281d  mov     eax, [rbp+var_40]
0x180012820  mov     [rbp+var_28], eax
0x180012823  mov     rdx, [rbx+8]
0x180012827  mov     rcx, rbx
0x18001282a  cmp     rdx, [rbx+10h]
0x18001282e  jz      short loc_18001283E
0x180012830  lea     rdx, [rbp+var_30]
0x180012834  call    ??$_Emplace_back_with_unused_capacity@AEBU_SESSION_USER_CONTEXT@@@?$vector@U_SESSION_USER_CONTEXT@@V?$allocator@U_SESSION_USER_CONTEXT@@@std@@@std@@AEAAAEAU_SESSION_USER_CONTEXT@@AEBU2@@Z; std::vector<_SESSION_USER_CONTEXT>::_Emplace_back_with_unused_capacity<_SESSION_USER_CONTEXT const &>(_SESSION_USER_CONTEXT const &)
0x180012839  jmp     loc_180012931
0x18001283e  lea     r8, [rbp+var_30]
0x180012842  call    ??$_Emplace_reallocate@AEBU_SESSION_USER_CONTEXT@@@?$vector@U_SESSION_USER_CONTEXT@@V?$allocator@U_SESSION_USER_CONTEXT@@@std@@@std@@AEAAPEAU_SESSION_USER_CONTEXT@@QEAU2@AEBU2@@Z; std::vector<_SESSION_USER_CONTEXT>::_Emplace_reallocate<_SESSION_USER_CONTEXT const &>(_SESSION_USER_CONTEXT * const,_SESSION_USER_CONTEXT const &)
0x180012847  jmp     loc_180012931
0x18001284c  mov     rcx, [rbp+8]; this
0x180012850  mov     r9d, 8000FFFFh; char *
0x180012856  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001285d  mov     edx, 0E2h; void *
0x180012862  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180012868  call    IsUMgrEnumerateSessionUsersPresent
0x18001286d  test    al, al
0x18001286f  jz      short loc_18001287E
0x180012871  call    IsUMgrEnumerateSessionUsersPresent
0x180012876  test    al, al
0x180012878  jz      short loc_18001287E
0x18001287a  mov     al, 1
0x18001287c  jmp     short loc_180012880
0x18001287e  xor     al, al
0x180012880  mov     rcx, [rbp+8]; this
0x180012884  test    al, al
0x180012886  jnz     short loc_1800128A0
0x180012888  mov     r9d, 8000FFFFh; char *
0x18001288e  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x180012895  mov     edx, 0D1h; void *
0x18001289a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800128a0  mov     [rbp+var_40], 0
0x1800128a7  mov     [rbp+var_30], 0
0x1800128af  lea     rdx, [rbp+var_30]
0x1800128b3  lea     rcx, [rbp+var_40]
0x1800128b7  call    cs:__imp_UMgrEnumerateSessionUsers
0x1800128bd  mov     rcx, [rbp+8]; this
0x1800128c1  test    eax, eax
0x1800128c3  jns     short loc_1800128DA
0x1800128c5  mov     r9d, eax; char *
0x1800128c8  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800128cf  mov     edx, 0D5h; void *
0x1800128d4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800128da  xor     edi, edi
0x1800128dc  cmp     [rbp+var_40], edi
0x1800128df  jbe     short loc_180012928
0x1800128e1  mov     ecx, edi
0x1800128e3  add     rcx, rcx
0x1800128e6  mov     rax, [rbp+var_30]
0x1800128ea  movups  xmm0, xmmword ptr [rax+rcx*8]
0x1800128ee  movdqu  [rbp+var_20], xmm0
0x1800128f3  lea     rcx, [rbp+var_20]; struct _SESSION_USER_CONTEXT *
0x1800128f7  call    ?IsWCOSSpecialAccount@@YA_NAEBU_SESSION_USER_CONTEXT@@@Z; IsWCOSSpecialAccount(_SESSION_USER_CONTEXT const &)
0x1800128fc  test    al, al
0x1800128fe  jnz     short loc_180012921
0x180012900  mov     rdx, [rbx+8]
0x180012904  mov     rcx, rbx
0x180012907  cmp     rdx, [rbx+10h]
0x18001290b  jz      short loc_180012918
0x18001290d  lea     rdx, [rbp+var_20]
0x180012911  call    ??$_Emplace_back_with_unused_capacity@AEBU_SESSION_USER_CONTEXT@@@?$vector@U_SESSION_USER_CONTEXT@@V?$allocator@U_SESSION_USER_CONTEXT@@@std@@@std@@AEAAAEAU_SESSION_USER_CONTEXT@@AEBU2@@Z; std::vector<_SESSION_USER_CONTEXT>::_Emplace_back_with_unused_capacity<_SESSION_USER_CONTEXT const &>(_SESSION_USER_CONTEXT const &)
0x180012916  jmp     short loc_180012921
0x180012918  lea     r8, [rbp+var_20]
0x18001291c  call    ??$_Emplace_reallocate@AEBU_SESSION_USER_CONTEXT@@@?$vector@U_SESSION_USER_CONTEXT@@V?$allocator@U_SESSION_USER_CONTEXT@@@std@@@std@@AEAAPEAU_SESSION_USER_CONTEXT@@QEAU2@AEBU2@@Z; std::vector<_SESSION_USER_CONTEXT>::_Emplace_reallocate<_SESSION_USER_CONTEXT const &>(_SESSION_USER_CONTEXT * const,_SESSION_USER_CONTEXT const &)
0x180012921  inc     edi
0x180012923  cmp     edi, [rbp+var_40]
0x180012926  jb      short loc_1800128E1
0x180012928  lea     rcx, [rbp+var_30]
0x18001292c  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x180012931  mov     rax, rbx
0x180012934  mov     rcx, [rbp+var_10]
0x180012938  xor     rcx, rsp; StackCookie
0x18001293b  call    __security_check_cookie
0x180012940  lea     r11, [rsp+60h+var_s0]
0x180012945  mov     rbx, [r11+18h]
0x180012949  mov     rdi, [r11+20h]
0x18001294d  mov     rsp, r11
0x180012950  pop     rbp
0x180012951  retn
```
