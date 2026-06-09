# Windows::Internal::Management::Provision::ConfigurationSession::CheckThreadAdmin(void *,int *)

- ea: `0x18006cbb0`
- end: `0x18006ccb1`
- name: `?CheckThreadAdmin@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEAXPEAH@Z`
- size: `257`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006c9cc`

## callees

- `0x180004eb0`
- `0x180017a64`
- `0x18006cbb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cc29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cc68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cc29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cc68`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006cc19`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006cc19`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18006cc54`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18006cc54`

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
0x18006cbb0  mov     r11, rsp
0x18006cbb3  mov     [r11+18h], rbx
0x18006cbb7  mov     [r11+20h], rsi
0x18006cbbb  push    rdi
0x18006cbbc  sub     rsp, 80h
0x18006cbc3  mov     rax, cs:__security_cookie
0x18006cbca  xor     rax, rsp
0x18006cbcd  mov     [rsp+88h+var_18], rax
0x18006cbd2  xor     esi, esi
0x18006cbd4  mov     [rsp+88h+var_1C], 500h
0x18006cbdb  lea     rax, [r11-28h]
0x18006cbdf  mov     [rsp+88h+var_20], esi
0x18006cbe3  mov     [r11-38h], rax
0x18006cbe7  mov     rdi, rdx
0x18006cbea  mov     [rsp+88h+nSubAuthority7], esi; nSubAuthority7
0x18006cbee  mov     rbx, rcx
0x18006cbf1  mov     [rsp+88h+nSubAuthority6], esi; nSubAuthority6
0x18006cbf5  lea     r8d, [rsi+20h]; nSubAuthority0
0x18006cbf9  mov     [rsp+88h+nSubAuthority5], esi; nSubAuthority5
0x18006cbfd  lea     rcx, [r11-20h]; pIdentifierAuthority
0x18006cc01  mov     [rsp+88h+nSubAuthority4], esi; nSubAuthority4
0x18006cc05  mov     r9d, 220h; nSubAuthority1
0x18006cc0b  mov     [rsp+88h+nSubAuthority3], esi; nSubAuthority3
0x18006cc0f  mov     dl, 2; nSubAuthorityCount
0x18006cc11  mov     [rsp+88h+nSubAuthority2], esi; nSubAuthority2
0x18006cc15  mov     [r11-28h], rsi
0x18006cc19  call    cs:__imp_AllocateAndInitializeSid
0x18006cc20  nop     dword ptr [rax+rax+00h]
0x18006cc25  test    eax, eax
0x18006cc27  jnz     short loc_18006CC46
0x18006cc29  call    cs:__imp_GetLastError
0x18006cc30  nop     dword ptr [rax+rax+00h]
0x18006cc35  mov     ebx, eax
0x18006cc37  test    eax, eax
0x18006cc39  jle     short loc_18006CC82
0x18006cc3b  movzx   ebx, ax
0x18006cc3e  or      ebx, 80070000h
0x18006cc44  jmp     short loc_18006CC82
0x18006cc46  mov     rdx, [rsp+88h+var_28]
0x18006cc4b  mov     r9, rdi
0x18006cc4e  xor     r8d, r8d
0x18006cc51  mov     rcx, rbx
0x18006cc54  call    cs:__imp_CheckTokenMembershipEx
0x18006cc5b  nop     dword ptr [rax+rax+00h]
0x18006cc60  test    eax, eax
0x18006cc62  jz      short loc_18006CC68
0x18006cc64  mov     ebx, esi
0x18006cc66  jmp     short loc_18006CC82
0x18006cc68  call    cs:__imp_GetLastError
0x18006cc6f  nop     dword ptr [rax+rax+00h]
0x18006cc74  test    eax, eax
0x18006cc76  jle     short loc_18006CC80
0x18006cc78  movzx   eax, ax
0x18006cc7b  or      eax, 80070000h
0x18006cc80  mov     ebx, eax
0x18006cc82  lea     rcx, [rsp+88h+var_28]
0x18006cc87  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006cc8c  mov     eax, ebx
0x18006cc8e  mov     rcx, [rsp+88h+var_18]
0x18006cc93  xor     rcx, rsp; StackCookie
0x18006cc96  call    __security_check_cookie
0x18006cc9b  lea     r11, [rsp+88h+var_8]
0x18006cca3  mov     rbx, [r11+20h]
0x18006cca7  mov     rsi, [r11+28h]
0x18006ccab  mov     rsp, r11
0x18006ccae  pop     rdi
0x18006ccaf  retn
```
