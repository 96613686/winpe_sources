# IsRunningAsAdmin

- ea: `0x18006cdd4`
- end: `0x18006cea1`
- name: `IsRunningAsAdmin`
- size: `205`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006a9a0`

## callees

- `0x180007270`
- `0x180069b0c`
- `0x18006cdd4`
- `0x18006cf10`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18006ce58`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18006ce58`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006ce38`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006ce38`

## pseudocode

```c
__int64 __fastcall IsRunningAsAdmin(PBOOL IsMember)
{
  unsigned int v2; // ebx
  PSID SidToCheck; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v5; // [rsp+68h] [rbp-20h] BYREF

  *(_WORD *)&v5.Value[4] = 1280;
  *IsMember = 0;
  *(_DWORD *)v5.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&v5, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck)
    && SidToCheck
    && !CheckTokenMembership(0, SidToCheck, IsMember) )
  {
    v2 = IsUserAdmin(IsMember);
  }
  else
  {
    v2 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SidToCheck);
  return v2;
}

```

## disassembly

```asm
0x18006cdd4  mov     r11, rsp
0x18006cdd7  mov     [r11+10h], rbx
0x18006cddb  push    rdi
0x18006cddc  sub     rsp, 80h
0x18006cde3  mov     rax, cs:__security_cookie
0x18006cdea  xor     rax, rsp
0x18006cded  mov     [rsp+88h+var_18], rax
0x18006cdf2  xor     edi, edi
0x18006cdf4  mov     [rsp+88h+var_1C], 500h
0x18006cdfb  lea     rax, [r11-28h]
0x18006cdff  mov     [rcx], edi
0x18006ce01  mov     [r11-38h], rax
0x18006ce05  mov     rbx, rcx
0x18006ce08  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x18006ce0c  lea     rcx, [r11-20h]; pIdentifierAuthority
0x18006ce10  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x18006ce14  lea     r8d, [rdi+20h]; nSubAuthority0
0x18006ce18  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x18006ce1c  mov     r9d, 220h; nSubAuthority1
0x18006ce22  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x18006ce26  mov     dl, 2; nSubAuthorityCount
0x18006ce28  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x18006ce2c  mov     [rsp+88h+nSubAuthority2], edi; nSubAuthority2
0x18006ce30  mov     [rsp+88h+var_20], edi
0x18006ce34  mov     [r11-28h], rdi
0x18006ce38  call    cs:__imp_AllocateAndInitializeSid
0x18006ce3f  nop     dword ptr [rax+rax+00h]
0x18006ce44  cmp     eax, 1
0x18006ce47  jnz     short loc_18006CE74
0x18006ce49  mov     rdx, [rsp+88h+SidToCheck]; SidToCheck
0x18006ce4e  test    rdx, rdx
0x18006ce51  jz      short loc_18006CE74
0x18006ce53  mov     r8, rbx; IsMember
0x18006ce56  xor     ecx, ecx; TokenHandle
0x18006ce58  call    cs:__imp_CheckTokenMembership
0x18006ce5f  nop     dword ptr [rax+rax+00h]
0x18006ce64  test    eax, eax
0x18006ce66  jnz     short loc_18006CE74
0x18006ce68  mov     rcx, rbx
0x18006ce6b  call    IsUserAdmin
0x18006ce70  mov     ebx, eax
0x18006ce72  jmp     short loc_18006CE76
0x18006ce74  mov     ebx, edi
0x18006ce76  lea     rcx, [rsp+88h+SidToCheck]
0x18006ce7b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006ce80  mov     eax, ebx
0x18006ce82  mov     rcx, [rsp+88h+var_18]
0x18006ce87  xor     rcx, rsp; StackCookie
0x18006ce8a  call    __security_check_cookie
0x18006ce8f  mov     rbx, [rsp+88h+arg_8]
0x18006ce97  add     rsp, 80h
0x18006ce9e  pop     rdi
0x18006ce9f  retn
```
