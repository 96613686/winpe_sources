# EditAppContainerMask(_ACL *)

- ea: `0x18001218c`
- end: `0x180012281`
- name: `?EditAppContainerMask@@YAXPEAU_ACL@@@Z`
- size: `245`
- prototype: `void __fastcall(PACL pAcl)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001039c`

## callees

- `0x18001218c`
- `0x180026758`
- `0x180031960`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180012230`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180012230`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012246`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012246`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800121ee`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800121ee`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001226a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001226a`

## pseudocode

```c
void __fastcall EditAppContainerMask(PACL pAcl)
{
  DWORD i; // ebx
  PSID pSid1; // [rsp+60h] [rbp+17h] BYREF
  LPVOID pAce; // [rsp+68h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid1 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 3u, 0x1000u, 0, 0, 0, 0, 0, 0, &pSid1) )
  {
    for ( i = 0; i < pAcl->AceCount; ++i )
    {
      pAce = 0;
      if ( !GetAce(pAcl, i, &pAce) )
      {
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid1);
        return;
      }
      if ( EqualSid(pSid1, (char *)pAce + 8) && !*(_BYTE *)pAce )
      {
        *((_BYTE *)pAce + 1) = 2;
        *((_DWORD *)pAce + 1) = 131099;
        break;
      }
    }
  }
  if ( pSid1 )
    FreeSid(pSid1);
}

```

## disassembly

```asm
0x18001218c  push    rbp
0x18001218e  push    rbx
0x18001218f  push    rsi
0x180012190  push    rdi
0x180012191  lea     rbp, [rsp-3Fh]
0x180012196  sub     rsp, 88h
0x18001219d  mov     rax, cs:__security_cookie
0x1800121a4  xor     rax, rsp
0x1800121a7  mov     [rbp+57h+var_28], rax
0x1800121ab  xor     esi, esi
0x1800121ad  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 0F00h
0x1800121b3  lea     rax, [rbp+57h+pSid1]
0x1800121b7  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x1800121ba  mov     [rsp+0A0h+pSid], rax; pSid
0x1800121bf  mov     rdi, rcx
0x1800121c2  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x1800121c6  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800121ca  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x1800121ce  lea     r8d, [rsi+3]; nSubAuthority0
0x1800121d2  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x1800121d6  mov     r9d, 1000h; nSubAuthority1
0x1800121dc  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x1800121e0  mov     dl, 2; nSubAuthorityCount
0x1800121e2  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x1800121e6  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x1800121ea  mov     [rbp+57h+pSid1], rsi
0x1800121ee  call    cs:__imp_AllocateAndInitializeSid
0x1800121f4  test    eax, eax
0x1800121f6  jnz     short loc_180012219
0x1800121f8  mov     rcx, [rbp+57h+pSid1]; pSid
0x1800121fc  test    rcx, rcx
0x1800121ff  jnz     short loc_18001226A
0x180012201  mov     rcx, [rbp+57h+var_28]
0x180012205  xor     rcx, rsp; StackCookie
0x180012208  call    __security_check_cookie
0x18001220d  add     rsp, 88h
0x180012214  pop     rdi
0x180012215  pop     rsi
0x180012216  pop     rbx
0x180012217  pop     rbp
0x180012218  retn
0x180012219  mov     ebx, esi
0x18001221b  movzx   eax, word ptr [rdi+4]
0x18001221f  cmp     ebx, eax
0x180012221  jnb     short loc_1800121F8
0x180012223  lea     r8, [rbp+57h+pAce]; pAce
0x180012227  mov     [rbp+57h+pAce], rsi
0x18001222b  mov     edx, ebx; dwAceIndex
0x18001222d  mov     rcx, rdi; pAcl
0x180012230  call    cs:__imp_GetAce
0x180012236  test    eax, eax
0x180012238  jz      short loc_180012276
0x18001223a  mov     rdx, [rbp+57h+pAce]
0x18001223e  mov     rcx, [rbp+57h+pSid1]; pSid1
0x180012242  add     rdx, 8; pSid2
0x180012246  call    cs:__imp_EqualSid
0x18001224c  test    eax, eax
0x18001224e  jz      short loc_180012272
0x180012250  mov     rax, [rbp+57h+pAce]
0x180012254  cmp     [rax], sil
0x180012257  jnz     short loc_180012272
0x180012259  mov     byte ptr [rax+1], 2
0x18001225d  mov     rax, [rbp+57h+pAce]
0x180012261  mov     dword ptr [rax+4], 2001Bh
0x180012268  jmp     short loc_1800121F8
0x18001226a  call    cs:__imp_FreeSid
0x180012270  jmp     short loc_180012201
0x180012272  inc     ebx
0x180012274  jmp     short loc_18001221B
0x180012276  lea     rcx, [rbp+57h+pSid1]
0x18001227a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001227f  jmp     short loc_180012201
```
