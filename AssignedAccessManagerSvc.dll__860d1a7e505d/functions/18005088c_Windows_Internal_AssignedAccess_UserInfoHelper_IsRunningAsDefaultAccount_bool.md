# Windows::Internal::AssignedAccess::UserInfoHelper::IsRunningAsDefaultAccount(bool &)

- ea: `0x18005088c`
- end: `0x18005097a`
- name: `?IsRunningAsDefaultAccount@UserInfoHelper@AssignedAccess@Internal@Windows@@SAJAEA_N@Z`
- size: `238`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008995c`

## callees

- `0x180006640`
- `0x18000b694`
- `0x18000b6b4`
- `0x18000f62c`
- `0x180010c98`
- `0x18002001c`
- `0x18004eca0`
- `0x180050658`
- `0x18005088c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800508b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800508b6`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18005093d`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18005093d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180050905`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180050905`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::UserInfoHelper::IsRunningAsDefaultAccount(
        bool *a1,
        __int64 a2,
        __int64 a3)
{
  HANDLE CurrentProcess; // rax
  int UserSidFromProcess; // eax
  unsigned int LastError; // ebx
  const WCHAR *v7; // rax
  const char *v8; // r9
  PSID Sid; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v11[32]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a1 = 0;
  std::wstring::wstring(v11, a2, a3);
  CurrentProcess = GetCurrentProcess();
  UserSidFromProcess = Windows::Internal::AssignedAccess::UserInfoHelper::GetUserSidFromProcess(CurrentProcess, v11);
  LastError = UserSidFromProcess;
  if ( UserSidFromProcess >= 0 )
  {
    Sid = 0;
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
    if ( ConvertStringSidToSidW(v7, &Sid) )
    {
      *a1 = IsWellKnownSid(Sid, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xA8,
                    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
                    v8);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
      (const char *)(unsigned int)UserSidFromProcess,
      (int)Sid);
  }
  std::wstring::_Tidy_deallocate(v11);
  return LastError;
}

```

## disassembly

```asm
0x18005088c  mov     [rsp+arg_8], rbx
0x180050891  push    rdi
0x180050892  sub     rsp, 50h
0x180050896  mov     rax, cs:__security_cookie
0x18005089d  xor     rax, rsp
0x1800508a0  mov     [rsp+58h+var_10], rax
0x1800508a5  mov     rdi, rcx
0x1800508a8  mov     byte ptr [rcx], 0
0x1800508ab  lea     rcx, [rsp+58h+var_30]
0x1800508b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800508b5  nop
0x1800508b6  call    cs:__imp_GetCurrentProcess
0x1800508bc  mov     rcx, rax
0x1800508bf  lea     rdx, [rsp+58h+var_30]
0x1800508c4  call    ?GetUserSidFromProcess@UserInfoHelper@AssignedAccess@Internal@Windows@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::AssignedAccess::UserInfoHelper::GetUserSidFromProcess(void *,std::wstring &)
0x1800508c9  mov     ebx, eax
0x1800508cb  test    eax, eax
0x1800508cd  jns     short loc_1800508EA
0x1800508cf  mov     rcx, [rsp+58h]; this
0x1800508d4  mov     r9d, eax; char *
0x1800508d7  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800508de  mov     edx, 0A5h; void *
0x1800508e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800508e8  jmp     short loc_180050956
0x1800508ea  mov     [rsp+58h+Sid], 0
0x1800508f3  lea     rcx, [rsp+58h+var_30]
0x1800508f8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800508fd  mov     rcx, rax; StringSid
0x180050900  lea     rdx, [rsp+58h+Sid]; Sid
0x180050905  call    cs:__imp_ConvertStringSidToSidW
0x18005090b  test    eax, eax
0x18005090d  jnz     short loc_180050933
0x18005090f  mov     rcx, [rsp+58h]; this
0x180050914  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005091b  mov     edx, 0A8h; void *
0x180050920  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180050925  mov     ebx, eax
0x180050927  lea     rcx, [rsp+58h+Sid]
0x18005092c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180050931  jmp     short loc_180050956
0x180050933  mov     edx, 6Eh ; 'n'; WellKnownSidType
0x180050938  mov     rcx, [rsp+58h+Sid]; pSid
0x18005093d  call    cs:__imp_IsWellKnownSid
0x180050943  test    eax, eax
0x180050945  setnz   al
0x180050948  mov     [rdi], al
0x18005094a  lea     rcx, [rsp+58h+Sid]
0x18005094f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180050954  xor     ebx, ebx
0x180050956  lea     rcx, [rsp+58h+var_30]
0x18005095b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180050960  mov     eax, ebx
0x180050962  mov     rcx, [rsp+58h+var_10]
0x180050967  xor     rcx, rsp; StackCookie
0x18005096a  call    __security_check_cookie
0x18005096f  mov     rbx, [rsp+58h+arg_8]
0x180050974  add     rsp, 50h
0x180050978  pop     rdi
0x180050979  retn
```
