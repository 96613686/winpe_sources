# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::GetUserSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140025698`
- end: `0x140025762`
- name: `?GetUserSid@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140025884`

## callees

- `0x140002d18`
- `0x14000e010`
- `0x140024300`
- `0x1400251a8`
- `0x140025560`
- `0x1400255f0`
- `0x140025698`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400256de`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400256de`

## string_xrefs

- `0x1400256f7`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::GetUserSid(
        __int64 a1)
{
  BOOL v2; // ebx
  const char *v3; // r9
  unsigned int LastError; // ebx
  void *v5; // rcx
  void *v6; // rcx
  __int64 *v8; // [rsp+20h] [rbp-20h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-18h] BYREF
  char v10; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  void *Block; // [rsp+58h] [rbp+18h] BYREF
  __int64 v13; // [rsp+60h] [rbp+20h] BYREF

  v13 = 0;
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block);
  v8 = &v13;
  StringSid = 0;
  v10 = 1;
  v2 = ConvertSidToStringSidW(*(PSID *)Block, &StringSid);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v8);
  if ( v2 )
  {
    std::wstring::assign(a1, v13);
    v6 = Block;
    Block = 0;
    if ( v6 )
      operator delete(v6);
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xC4,
                  (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
                  v3);
    v5 = Block;
    Block = 0;
    if ( v5 )
      operator delete(v5);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
  return LastError;
}

```

## disassembly

```asm
0x140025698  mov     [rsp-8+arg_0], rbx
0x14002569d  mov     [rsp-8+arg_18], rdi
0x1400256a2  push    rbp
0x1400256a3  mov     rbp, rsp
0x1400256a6  sub     rsp, 40h
0x1400256aa  mov     rdi, rcx
0x1400256ad  mov     [rbp+arg_10], 0
0x1400256b5  lea     rcx, [rbp+Block]
0x1400256b9  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x1400256be  nop
0x1400256bf  lea     rax, [rbp+arg_10]
0x1400256c3  mov     [rbp+var_20], rax
0x1400256c7  mov     [rbp+StringSid], 0
0x1400256cf  mov     [rbp+var_10], 1
0x1400256d3  lea     rdx, [rbp+StringSid]; StringSid
0x1400256d7  mov     rcx, [rbp+Block]
0x1400256db  mov     rcx, [rcx]; Sid
0x1400256de  call    cs:__imp_ConvertSidToStringSidW
0x1400256e4  mov     ebx, eax
0x1400256e6  lea     rcx, [rbp+var_20]
0x1400256ea  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1400256ef  test    ebx, ebx
0x1400256f1  jnz     short loc_140025722
0x1400256f3  mov     rcx, [rbp+8]; this
0x1400256f7  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400256fe  mov     edx, 0C4h; void *
0x140025703  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140025708  mov     ebx, eax
0x14002570a  mov     rcx, [rbp+Block]; Block
0x14002570e  mov     [rbp+Block], 0
0x140025716  test    rcx, rcx
0x140025719  jz      short loc_140025747
0x14002571b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140025720  jmp     short loc_140025747
0x140025722  mov     rdx, [rbp+arg_10]
0x140025726  mov     rcx, rdi
0x140025729  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x14002572e  nop
0x14002572f  mov     rcx, [rbp+Block]; Block
0x140025733  mov     [rbp+Block], 0
0x14002573b  test    rcx, rcx
0x14002573e  jz      short loc_140025745
0x140025740  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140025745  xor     ebx, ebx
0x140025747  lea     rcx, [rbp+arg_10]
0x14002574b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140025750  mov     eax, ebx
0x140025752  mov     rbx, [rsp+40h+arg_0]
0x140025757  mov     rdi, [rsp+40h+arg_18]
0x14002575c  add     rsp, 40h
0x140025760  pop     rbp
0x140025761  retn
```
