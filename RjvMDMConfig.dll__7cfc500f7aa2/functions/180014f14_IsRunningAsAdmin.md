# IsRunningAsAdmin

- ea: `0x180014f14`
- end: `0x180014fe1`
- name: `IsRunningAsAdmin`
- size: `205`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012b80`

## callees

- `0x180001c60`
- `0x180012a0c`
- `0x180014f14`
- `0x180015050`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180014f78`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180014f78`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180014f98`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180014f98`

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
0x180014f14  mov     r11, rsp
0x180014f17  mov     [r11+10h], rbx
0x180014f1b  push    rdi
0x180014f1c  sub     rsp, 80h
0x180014f23  mov     rax, cs:__security_cookie
0x180014f2a  xor     rax, rsp
0x180014f2d  mov     [rsp+88h+var_18], rax
0x180014f32  xor     edi, edi
0x180014f34  mov     [rsp+88h+var_1C], 500h
0x180014f3b  lea     rax, [r11-28h]
0x180014f3f  mov     [rcx], edi
0x180014f41  mov     [r11-38h], rax
0x180014f45  mov     rbx, rcx
0x180014f48  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x180014f4c  lea     rcx, [r11-20h]; pIdentifierAuthority
0x180014f50  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x180014f54  lea     r8d, [rdi+20h]; nSubAuthority0
0x180014f58  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x180014f5c  mov     r9d, 220h; nSubAuthority1
0x180014f62  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x180014f66  mov     dl, 2; nSubAuthorityCount
0x180014f68  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x180014f6c  mov     [rsp+88h+nSubAuthority2], edi; nSubAuthority2
0x180014f70  mov     [rsp+88h+var_20], edi
0x180014f74  mov     [r11-28h], rdi
0x180014f78  call    cs:__imp_AllocateAndInitializeSid
0x180014f7f  nop     dword ptr [rax+rax+00h]
0x180014f84  cmp     eax, 1
0x180014f87  jnz     short loc_180014FB4
0x180014f89  mov     rdx, [rsp+88h+SidToCheck]; SidToCheck
0x180014f8e  test    rdx, rdx
0x180014f91  jz      short loc_180014FB4
0x180014f93  mov     r8, rbx; IsMember
0x180014f96  xor     ecx, ecx; TokenHandle
0x180014f98  call    cs:__imp_CheckTokenMembership
0x180014f9f  nop     dword ptr [rax+rax+00h]
0x180014fa4  test    eax, eax
0x180014fa6  jnz     short loc_180014FB4
0x180014fa8  mov     rcx, rbx
0x180014fab  call    IsUserAdmin
0x180014fb0  mov     ebx, eax
0x180014fb2  jmp     short loc_180014FB6
0x180014fb4  mov     ebx, edi
0x180014fb6  lea     rcx, [rsp+88h+SidToCheck]
0x180014fbb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180014fc0  mov     eax, ebx
0x180014fc2  mov     rcx, [rsp+88h+var_18]
0x180014fc7  xor     rcx, rsp; StackCookie
0x180014fca  call    __security_check_cookie
0x180014fcf  mov     rbx, [rsp+88h+arg_8]
0x180014fd7  add     rsp, 80h
0x180014fde  pop     rdi
0x180014fdf  retn
```
