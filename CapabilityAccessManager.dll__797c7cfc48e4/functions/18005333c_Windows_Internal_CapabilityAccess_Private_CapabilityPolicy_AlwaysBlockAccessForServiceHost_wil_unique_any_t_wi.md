# Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::AlwaysBlockAccessForServiceHost(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)

- ea: `0x18005333c`
- end: `0x180053487`
- name: `?AlwaysBlockAccessForServiceHost@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@QEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006874c`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x1800257a4`
- `0x180029408`
- `0x18002f260`
- `0x180039e9c`
- `0x18004657c`
- `0x18005333c`
- `0x180058318`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800533cd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800533cd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800533b0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800533b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::AlwaysBlockAccessForServiceHost(
        __int64 a1,
        HANDLE *a2)
{
  _QWORD **v4; // rdi
  _QWORD *i; // rbx
  const WCHAR *v6; // rax
  const char *v7; // r9
  const char *v8; // r9
  int v9; // edx
  int v10; // edx
  char v11; // bl
  WINBOOL IsMember; // [rsp+20h] [rbp-40h] BYREF
  PSID Sid; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+30h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  IsMember = 0;
  v4 = *(_QWORD ***)(a1 + 240);
  for ( i = *v4; i != v4; i = (_QWORD *)*i )
  {
    std::wstring::wstring(v15, i + 2);
    Sid = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &Sid,
      0);
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
    if ( !ConvertStringSidToSidW(v6, &Sid) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x17B,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
        v7);
    if ( !CheckTokenMembership(*a2, Sid, &IsMember) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x17C,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
        v8);
    if ( IsMember )
    {
      v9 = *(_DWORD *)(std::unordered_map<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::at(
                         a1 + 232,
                         v15)
                     + 36);
      if ( !v9 )
      {
        v11 = *(_BYTE *)(a1 + 45);
        goto LABEL_13;
      }
      v10 = v9 - 1;
      if ( !v10 )
      {
        v11 = 1;
        goto LABEL_13;
      }
      if ( v10 == 1 )
      {
        v11 = 0;
LABEL_13:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
        std::wstring::_Tidy_deallocate(v15);
        return v11;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
    std::wstring::_Tidy_deallocate(v15);
  }
  return *(_BYTE *)(a1 + 45);
}

```

## disassembly

```asm
0x18005333c  mov     [rsp-18h+arg_10], rbx
0x180053341  mov     [rsp-18h+arg_18], rsi
0x180053346  push    rbp
0x180053347  push    rdi
0x180053348  push    r14
0x18005334a  mov     rbp, rsp
0x18005334d  sub     rsp, 60h
0x180053351  mov     rax, cs:__security_cookie
0x180053358  xor     rax, rsp
0x18005335b  mov     [rbp+var_10], rax
0x18005335f  mov     r14, rdx
0x180053362  mov     rsi, rcx
0x180053365  mov     [rbp+IsMember], 0
0x18005336c  mov     rdi, [rcx+0F0h]
0x180053373  mov     rbx, [rdi]
0x180053376  cmp     rbx, rdi
0x180053379  jz      loc_180053463
0x18005337f  lea     rdx, [rbx+10h]
0x180053383  lea     rcx, [rbp+var_30]
0x180053387  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005338c  nop
0x18005338d  mov     [rbp+Sid], 0
0x180053395  xor     edx, edx
0x180053397  lea     rcx, [rbp+Sid]
0x18005339b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800533a0  lea     rcx, [rbp+var_30]
0x1800533a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800533a9  mov     rcx, rax; StringSid
0x1800533ac  lea     rdx, [rbp+Sid]; Sid
0x1800533b0  call    cs:__imp_ConvertStringSidToSidW
0x1800533b6  mov     rcx, [rbp+18h]; this
0x1800533ba  test    eax, eax
0x1800533bc  jz      loc_180053451
0x1800533c2  lea     r8, [rbp+IsMember]; IsMember
0x1800533c6  mov     rdx, [rbp+Sid]; SidToCheck
0x1800533ca  mov     rcx, [r14]; TokenHandle
0x1800533cd  call    cs:__imp_CheckTokenMembership
0x1800533d3  mov     rcx, [rbp+18h]; this
0x1800533d7  test    eax, eax
0x1800533d9  jz      short loc_18005343F
0x1800533db  cmp     [rbp+IsMember], 0
0x1800533df  jz      short loc_180053402
0x1800533e1  lea     rcx, [rsi+0E8h]
0x1800533e8  lea     rdx, [rbp+var_30]
0x1800533ec  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@2@@std@@QEBAAEBVCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::unordered_map<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::at(std::wstring const &)
0x1800533f1  mov     edx, [rax+24h]
0x1800533f4  test    edx, edx
0x1800533f6  jz      short loc_180053425
0x1800533f8  sub     edx, 1
0x1800533fb  jz      short loc_180053421
0x1800533fd  cmp     edx, 1
0x180053400  jz      short loc_18005341D
0x180053402  lea     rcx, [rbp+Sid]
0x180053406  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005340b  nop
0x18005340c  lea     rcx, [rbp+var_30]
0x180053410  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180053415  mov     rbx, [rbx]
0x180053418  jmp     loc_180053376
0x18005341d  xor     ebx, ebx
0x18005341f  jmp     short loc_180053428
0x180053421  mov     bl, 1
0x180053423  jmp     short loc_180053428
0x180053425  mov     bl, [rsi+2Dh]
0x180053428  lea     rcx, [rbp+Sid]
0x18005342c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180053431  nop
0x180053432  lea     rcx, [rbp+var_30]
0x180053436  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005343b  mov     al, bl
0x18005343d  jmp     short loc_180053466
0x18005343f  lea     r8, aOnecoreBaseDev_16; "onecore\\base\\devices\\cam\\core\\capa"...
0x180053446  mov     edx, 17Ch; void *
0x18005344b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180053451  lea     r8, aOnecoreBaseDev_16; "onecore\\base\\devices\\cam\\core\\capa"...
0x180053458  mov     edx, 17Bh; void *
0x18005345d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180053463  mov     al, [rsi+2Dh]
0x180053466  mov     rcx, [rbp+var_10]
0x18005346a  xor     rcx, rsp; StackCookie
0x18005346d  call    __security_check_cookie
0x180053472  lea     r11, [rsp+60h+var_s0]
0x180053477  mov     rbx, [r11+30h]
0x18005347b  mov     rsi, [r11+38h]
0x18005347f  mov     rsp, r11
0x180053482  pop     r14
0x180053484  pop     rdi
0x180053485  pop     rbp
0x180053486  retn
```
