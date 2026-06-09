# Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::UserConsentRequiredForServiceHost(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)

- ea: `0x180057ab0`
- end: `0x180057bfb`
- name: `?UserConsentRequiredForServiceHost@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@QEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
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
- `0x180057ab0`
- `0x180058318`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180057b41`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180057b41`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180057b24`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180057b24`

## pseudocode

```c
char __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::UserConsentRequiredForServiceHost(
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
        (void *)0xCC,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
        v7);
    if ( !CheckTokenMembership(*a2, Sid, &IsMember) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
        v8);
    if ( IsMember )
    {
      v9 = *(_DWORD *)(std::unordered_map<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::at(
                         a1 + 232,
                         v15)
                     + 16);
      if ( !v9 )
      {
        v11 = *(_BYTE *)(a1 + 65);
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
  return *(_BYTE *)(a1 + 65);
}

```

## disassembly

```asm
0x180057ab0  mov     [rsp-18h+arg_10], rbx
0x180057ab5  mov     [rsp-18h+arg_18], rsi
0x180057aba  push    rbp
0x180057abb  push    rdi
0x180057abc  push    r14
0x180057abe  mov     rbp, rsp
0x180057ac1  sub     rsp, 60h
0x180057ac5  mov     rax, cs:__security_cookie
0x180057acc  xor     rax, rsp
0x180057acf  mov     [rbp+var_10], rax
0x180057ad3  mov     r14, rdx
0x180057ad6  mov     rsi, rcx
0x180057ad9  mov     [rbp+IsMember], 0
0x180057ae0  mov     rdi, [rcx+0F0h]
0x180057ae7  mov     rbx, [rdi]
0x180057aea  cmp     rbx, rdi
0x180057aed  jz      loc_180057BD7
0x180057af3  lea     rdx, [rbx+10h]
0x180057af7  lea     rcx, [rbp+var_30]
0x180057afb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180057b00  nop
0x180057b01  mov     [rbp+Sid], 0
0x180057b09  xor     edx, edx
0x180057b0b  lea     rcx, [rbp+Sid]
0x180057b0f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180057b14  lea     rcx, [rbp+var_30]
0x180057b18  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180057b1d  mov     rcx, rax; StringSid
0x180057b20  lea     rdx, [rbp+Sid]; Sid
0x180057b24  call    cs:__imp_ConvertStringSidToSidW
0x180057b2a  mov     rcx, [rbp+18h]; this
0x180057b2e  test    eax, eax
0x180057b30  jz      loc_180057BC5
0x180057b36  lea     r8, [rbp+IsMember]; IsMember
0x180057b3a  mov     rdx, [rbp+Sid]; SidToCheck
0x180057b3e  mov     rcx, [r14]; TokenHandle
0x180057b41  call    cs:__imp_CheckTokenMembership
0x180057b47  mov     rcx, [rbp+18h]; this
0x180057b4b  test    eax, eax
0x180057b4d  jz      short loc_180057BB3
0x180057b4f  cmp     [rbp+IsMember], 0
0x180057b53  jz      short loc_180057B76
0x180057b55  lea     rcx, [rsi+0E8h]
0x180057b5c  lea     rdx, [rbp+var_30]
0x180057b60  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@2@@std@@QEBAAEBVCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::unordered_map<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::at(std::wstring const &)
0x180057b65  mov     edx, [rax+10h]
0x180057b68  test    edx, edx
0x180057b6a  jz      short loc_180057B99
0x180057b6c  sub     edx, 1
0x180057b6f  jz      short loc_180057B95
0x180057b71  cmp     edx, 1
0x180057b74  jz      short loc_180057B91
0x180057b76  lea     rcx, [rbp+Sid]
0x180057b7a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180057b7f  nop
0x180057b80  lea     rcx, [rbp+var_30]
0x180057b84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057b89  mov     rbx, [rbx]
0x180057b8c  jmp     loc_180057AEA
0x180057b91  xor     ebx, ebx
0x180057b93  jmp     short loc_180057B9C
0x180057b95  mov     bl, 1
0x180057b97  jmp     short loc_180057B9C
0x180057b99  mov     bl, [rsi+41h]
0x180057b9c  lea     rcx, [rbp+Sid]
0x180057ba0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180057ba5  nop
0x180057ba6  lea     rcx, [rbp+var_30]
0x180057baa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057baf  mov     al, bl
0x180057bb1  jmp     short loc_180057BDA
0x180057bb3  lea     r8, aOnecoreBaseDev_16; "onecore\\base\\devices\\cam\\core\\capa"...
0x180057bba  mov     edx, 0CDh; void *
0x180057bbf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180057bc5  lea     r8, aOnecoreBaseDev_16; "onecore\\base\\devices\\cam\\core\\capa"...
0x180057bcc  mov     edx, 0CCh; void *
0x180057bd1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180057bd7  mov     al, [rsi+41h]
0x180057bda  mov     rcx, [rbp+var_10]
0x180057bde  xor     rcx, rsp; StackCookie
0x180057be1  call    __security_check_cookie
0x180057be6  lea     r11, [rsp+60h+var_s0]
0x180057beb  mov     rbx, [r11+30h]
0x180057bef  mov     rsi, [r11+38h]
0x180057bf3  mov     rsp, r11
0x180057bf6  pop     r14
0x180057bf8  pop     rdi
0x180057bf9  pop     rbp
0x180057bfa  retn
```
