# Windows::Internal::Management::Provision::ConfigurationSession::CheckThreadAdmin(void *,int *)

- ea: `0x18006b8f0`
- end: `0x18006b9d8`
- name: `?CheckThreadAdmin@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEAXPEAH@Z`
- size: `232`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006b72c`

## callees

- `0x180004d50`
- `0x180017264`
- `0x18006b8f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b996`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006b959`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006b959`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18006b988`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18006b988`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Management::Provision::ConfigurationSession::CheckThreadAdmin(void *a1, int *a2)
{
  signed int v4; // eax
  unsigned int v5; // ebx
  signed int LastError; // eax
  PSID v8; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v9; // [rsp+68h] [rbp-20h] BYREF

  *(_WORD *)&v9.Value[4] = 1280;
  *(_DWORD *)v9.Value = 0;
  v8 = 0;
  if ( AllocateAndInitializeSid(&v9, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v8) )
  {
    if ( (unsigned int)CheckTokenMembershipEx(a1, v8, 0, a2) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v5 = LastError;
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v8);
  return v5;
}

```

## disassembly

```asm
0x18006b8f0  mov     r11, rsp
0x18006b8f3  mov     [r11+18h], rbx
0x18006b8f7  mov     [r11+20h], rsi
0x18006b8fb  push    rdi
0x18006b8fc  sub     rsp, 80h
0x18006b903  mov     rax, cs:__security_cookie
0x18006b90a  xor     rax, rsp
0x18006b90d  mov     [rsp+88h+var_18], rax
0x18006b912  xor     esi, esi
0x18006b914  mov     [rsp+88h+var_1C], 500h
0x18006b91b  lea     rax, [r11-28h]
0x18006b91f  mov     [rsp+88h+var_20], esi
0x18006b923  mov     [r11-38h], rax
0x18006b927  mov     rdi, rdx
0x18006b92a  mov     [rsp+88h+nSubAuthority7], esi; nSubAuthority7
0x18006b92e  mov     rbx, rcx
0x18006b931  mov     [rsp+88h+nSubAuthority6], esi; nSubAuthority6
0x18006b935  lea     r8d, [rsi+20h]; nSubAuthority0
0x18006b939  mov     [rsp+88h+nSubAuthority5], esi; nSubAuthority5
0x18006b93d  lea     rcx, [r11-20h]; pIdentifierAuthority
0x18006b941  mov     [rsp+88h+nSubAuthority4], esi; nSubAuthority4
0x18006b945  mov     r9d, 220h; nSubAuthority1
0x18006b94b  mov     [rsp+88h+nSubAuthority3], esi; nSubAuthority3
0x18006b94f  mov     dl, 2; nSubAuthorityCount
0x18006b951  mov     [rsp+88h+nSubAuthority2], esi; nSubAuthority2
0x18006b955  mov     [r11-28h], rsi
0x18006b959  call    cs:__imp_AllocateAndInitializeSid
0x18006b95f  test    eax, eax
0x18006b961  jnz     short loc_18006B97A
0x18006b963  call    cs:__imp_GetLastError
0x18006b969  mov     ebx, eax
0x18006b96b  test    eax, eax
0x18006b96d  jle     short loc_18006B9AA
0x18006b96f  movzx   ebx, ax
0x18006b972  or      ebx, 80070000h
0x18006b978  jmp     short loc_18006B9AA
0x18006b97a  mov     rdx, [rsp+88h+var_28]
0x18006b97f  mov     r9, rdi
0x18006b982  xor     r8d, r8d
0x18006b985  mov     rcx, rbx
0x18006b988  call    cs:__imp_CheckTokenMembershipEx
0x18006b98e  test    eax, eax
0x18006b990  jz      short loc_18006B996
0x18006b992  mov     ebx, esi
0x18006b994  jmp     short loc_18006B9AA
0x18006b996  call    cs:__imp_GetLastError
0x18006b99c  test    eax, eax
0x18006b99e  jle     short loc_18006B9A8
0x18006b9a0  movzx   eax, ax
0x18006b9a3  or      eax, 80070000h
0x18006b9a8  mov     ebx, eax
0x18006b9aa  lea     rcx, [rsp+88h+var_28]
0x18006b9af  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006b9b4  mov     eax, ebx
0x18006b9b6  mov     rcx, [rsp+88h+var_18]
0x18006b9bb  xor     rcx, rsp; StackCookie
0x18006b9be  call    __security_check_cookie
0x18006b9c3  lea     r11, [rsp+88h+var_8]
0x18006b9cb  mov     rbx, [r11+20h]
0x18006b9cf  mov     rsi, [r11+28h]
0x18006b9d3  mov     rsp, r11
0x18006b9d6  pop     rdi
0x18006b9d7  retn
```
