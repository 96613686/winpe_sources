# CommonUtils::IsCurrentUserAdmin

- ea: `0x1800b5ce8`
- end: `0x1800b5dd4`
- name: `CommonUtils::IsCurrentUserAdmin`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b6140`

## callees

- `0x18000c6e0`
- `0x18008cedc`
- `0x1800b456c`
- `0x1800b4684`
- `0x1800b5ce8`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x1800b5d7e`
- `ADVAPI32!CheckTokenMembership` at `0x1800b5d7e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800b5d5c`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800b5d5c`

## string_xrefs

- `0x1800b5d94`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\CommonUtils.h`

## pseudocode

```c
bool CommonUtils::IsCurrentUserAdmin()
{
  BOOL v0; // ebx
  const char *v1; // r9
  bool v2; // bl
  WINBOOL IsMember; // [rsp+68h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+1Fh] BYREF
  PSID *p_SidToCheck; // [rsp+78h] [rbp+27h] BYREF
  PSID v7; // [rsp+80h] [rbp+2Fh] BYREF
  char v8; // [rsp+88h] [rbp+37h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  p_SidToCheck = &SidToCheck;
  SidToCheck = 0;
  v7 = 0;
  v8 = 1;
  v0 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v7);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_SidToCheck);
  if ( v0 && (IsMember = 0, CheckTokenMembership(0, SidToCheck, &IsMember)) )
  {
    v2 = IsMember != 0;
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x37,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\CommonUtils.h",
      v1);
    v2 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SidToCheck);
  return v2;
}

```

## disassembly

```asm
0x1800b5ce8  mov     r11, rsp
0x1800b5ceb  mov     [r11+8], rbx
0x1800b5cef  mov     [r11+10h], rdi
0x1800b5cf3  push    rbp
0x1800b5cf4  lea     rbp, [r11-5Fh]
0x1800b5cf8  sub     rsp, 0A0h
0x1800b5cff  mov     rax, cs:__security_cookie
0x1800b5d06  xor     rax, rsp
0x1800b5d09  mov     [rbp+57h+var_10], rax
0x1800b5d0d  xor     edi, edi
0x1800b5d0f  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800b5d15  lea     rax, [rbp+57h+SidToCheck]
0x1800b5d19  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x1800b5d1c  mov     [rbp+57h+var_30], rax
0x1800b5d20  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800b5d24  lea     rax, [rbp+57h+var_28]
0x1800b5d28  mov     [rbp+57h+SidToCheck], rdi
0x1800b5d2c  mov     [r11-58h], rax
0x1800b5d30  lea     r8d, [rdi+20h]; nSubAuthority0
0x1800b5d34  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x1800b5d38  mov     r9d, 220h; nSubAuthority1
0x1800b5d3e  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x1800b5d42  mov     dl, 2; nSubAuthorityCount
0x1800b5d44  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x1800b5d48  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x1800b5d4c  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x1800b5d50  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x1800b5d54  mov     [rbp+57h+var_28], rdi
0x1800b5d58  mov     [rbp+57h+var_20], 1
0x1800b5d5c  call    cs:__imp_AllocateAndInitializeSid
0x1800b5d62  lea     rcx, [rbp+57h+var_30]
0x1800b5d66  mov     ebx, eax
0x1800b5d68  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800b5d6d  test    ebx, ebx
0x1800b5d6f  jz      short loc_1800B5D90
0x1800b5d71  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800b5d75  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800b5d79  xor     ecx, ecx; TokenHandle
0x1800b5d7b  mov     [rbp+57h+IsMember], edi
0x1800b5d7e  call    cs:__imp_CheckTokenMembership
0x1800b5d84  test    eax, eax
0x1800b5d86  jz      short loc_1800B5D90
0x1800b5d88  cmp     [rbp+57h+IsMember], edi
0x1800b5d8b  setnz   bl
0x1800b5d8e  jmp     short loc_1800B5DA8
0x1800b5d90  mov     rcx, [rbp+5Fh]; this
0x1800b5d94  lea     r8, aPcshellShellCl_33; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800b5d9b  mov     edx, 37h ; '7'; void *
0x1800b5da0  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800b5da5  mov     bl, dil
0x1800b5da8  lea     rcx, [rbp+57h+SidToCheck]
0x1800b5dac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800b5db1  mov     al, bl
0x1800b5db3  mov     rcx, [rbp+57h+var_10]
0x1800b5db7  xor     rcx, rsp; StackCookie
0x1800b5dba  call    __security_check_cookie
0x1800b5dbf  lea     r11, [rsp+0A0h+var_s0]
0x1800b5dc7  mov     rbx, [r11+10h]
0x1800b5dcb  mov     rdi, [r11+18h]
0x1800b5dcf  mov     rsp, r11
0x1800b5dd2  pop     rbp
0x1800b5dd3  retn
```
