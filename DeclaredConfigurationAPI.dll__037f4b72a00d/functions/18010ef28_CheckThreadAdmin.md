# CheckThreadAdmin

- ea: `0x18010ef28`
- end: `0x18010f010`
- name: `CheckThreadAdmin`
- size: `232`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18010e4c0`

## callees

- `0x18000b9e0`
- `0x18010dee4`
- `0x18010ef28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010ef9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010efce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010ef9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010efce`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18010ef91`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18010ef91`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18010efc0`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18010efc0`

## pseudocode

```c
__int64 __fastcall CheckThreadAdmin(__int64 a1, __int64 a2)
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
0x18010ef28  mov     r11, rsp
0x18010ef2b  mov     [r11+18h], rbx
0x18010ef2f  mov     [r11+20h], rsi
0x18010ef33  push    rdi
0x18010ef34  sub     rsp, 80h
0x18010ef3b  mov     rax, cs:__security_cookie
0x18010ef42  xor     rax, rsp
0x18010ef45  mov     [rsp+88h+var_18], rax
0x18010ef4a  xor     esi, esi
0x18010ef4c  mov     [rsp+88h+var_1C], 500h
0x18010ef53  lea     rax, [r11-28h]
0x18010ef57  mov     [rsp+88h+var_20], esi
0x18010ef5b  mov     [r11-38h], rax
0x18010ef5f  mov     rdi, rdx
0x18010ef62  mov     [rsp+88h+nSubAuthority7], esi; nSubAuthority7
0x18010ef66  mov     rbx, rcx
0x18010ef69  mov     [rsp+88h+nSubAuthority6], esi; nSubAuthority6
0x18010ef6d  lea     r8d, [rsi+20h]; nSubAuthority0
0x18010ef71  mov     [rsp+88h+nSubAuthority5], esi; nSubAuthority5
0x18010ef75  lea     rcx, [r11-20h]; pIdentifierAuthority
0x18010ef79  mov     [rsp+88h+nSubAuthority4], esi; nSubAuthority4
0x18010ef7d  mov     r9d, 220h; nSubAuthority1
0x18010ef83  mov     [rsp+88h+nSubAuthority3], esi; nSubAuthority3
0x18010ef87  mov     dl, 2; nSubAuthorityCount
0x18010ef89  mov     [rsp+88h+nSubAuthority2], esi; nSubAuthority2
0x18010ef8d  mov     [r11-28h], rsi
0x18010ef91  call    cs:__imp_AllocateAndInitializeSid
0x18010ef97  test    eax, eax
0x18010ef99  jnz     short loc_18010EFB2
0x18010ef9b  call    cs:__imp_GetLastError
0x18010efa1  mov     ebx, eax
0x18010efa3  test    eax, eax
0x18010efa5  jle     short loc_18010EFE2
0x18010efa7  movzx   ebx, ax
0x18010efaa  or      ebx, 80070000h
0x18010efb0  jmp     short loc_18010EFE2
0x18010efb2  mov     rdx, [rsp+88h+var_28]
0x18010efb7  mov     r9, rdi
0x18010efba  xor     r8d, r8d
0x18010efbd  mov     rcx, rbx
0x18010efc0  call    cs:__imp_CheckTokenMembershipEx
0x18010efc6  test    eax, eax
0x18010efc8  jz      short loc_18010EFCE
0x18010efca  mov     ebx, esi
0x18010efcc  jmp     short loc_18010EFE2
0x18010efce  call    cs:__imp_GetLastError
0x18010efd4  test    eax, eax
0x18010efd6  jle     short loc_18010EFE0
0x18010efd8  movzx   eax, ax
0x18010efdb  or      eax, 80070000h
0x18010efe0  mov     ebx, eax
0x18010efe2  lea     rcx, [rsp+88h+var_28]
0x18010efe7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18010efec  mov     eax, ebx
0x18010efee  mov     rcx, [rsp+88h+var_18]
0x18010eff3  xor     rcx, rsp; StackCookie
0x18010eff6  call    __security_check_cookie
0x18010effb  lea     r11, [rsp+88h+var_8]
0x18010f003  mov     rbx, [r11+20h]
0x18010f007  mov     rsi, [r11+28h]
0x18010f00b  mov     rsp, r11
0x18010f00e  pop     rdi
0x18010f00f  retn
```
