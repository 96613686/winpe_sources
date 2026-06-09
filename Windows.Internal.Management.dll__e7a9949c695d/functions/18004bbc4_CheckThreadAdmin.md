# CheckThreadAdmin

- ea: `0x18004bbc4`
- end: `0x18004bcac`
- name: `CheckThreadAdmin`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004abc0`

## callees

- `0x180004d50`
- `0x180017264`
- `0x18004bbc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bc37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bc6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bc37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bc6a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004bc2d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004bc2d`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18004bc5c`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18004bc5c`

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
0x18004bbc4  mov     r11, rsp
0x18004bbc7  mov     [r11+18h], rbx
0x18004bbcb  mov     [r11+20h], rsi
0x18004bbcf  push    rdi
0x18004bbd0  sub     rsp, 80h
0x18004bbd7  mov     rax, cs:__security_cookie
0x18004bbde  xor     rax, rsp
0x18004bbe1  mov     [rsp+88h+var_18], rax
0x18004bbe6  xor     esi, esi
0x18004bbe8  mov     [rsp+88h+var_1C], 500h
0x18004bbef  lea     rax, [r11-28h]
0x18004bbf3  mov     [rsp+88h+var_20], esi
0x18004bbf7  mov     [r11-38h], rax
0x18004bbfb  mov     rdi, rdx
0x18004bbfe  mov     [rsp+88h+nSubAuthority7], esi; nSubAuthority7
0x18004bc02  mov     rbx, rcx
0x18004bc05  mov     [rsp+88h+nSubAuthority6], esi; nSubAuthority6
0x18004bc09  lea     r8d, [rsi+20h]; nSubAuthority0
0x18004bc0d  mov     [rsp+88h+nSubAuthority5], esi; nSubAuthority5
0x18004bc11  lea     rcx, [r11-20h]; pIdentifierAuthority
0x18004bc15  mov     [rsp+88h+nSubAuthority4], esi; nSubAuthority4
0x18004bc19  mov     r9d, 220h; nSubAuthority1
0x18004bc1f  mov     [rsp+88h+nSubAuthority3], esi; nSubAuthority3
0x18004bc23  mov     dl, 2; nSubAuthorityCount
0x18004bc25  mov     [rsp+88h+nSubAuthority2], esi; nSubAuthority2
0x18004bc29  mov     [r11-28h], rsi
0x18004bc2d  call    cs:__imp_AllocateAndInitializeSid
0x18004bc33  test    eax, eax
0x18004bc35  jnz     short loc_18004BC4E
0x18004bc37  call    cs:__imp_GetLastError
0x18004bc3d  mov     ebx, eax
0x18004bc3f  test    eax, eax
0x18004bc41  jle     short loc_18004BC7E
0x18004bc43  movzx   ebx, ax
0x18004bc46  or      ebx, 80070000h
0x18004bc4c  jmp     short loc_18004BC7E
0x18004bc4e  mov     rdx, [rsp+88h+var_28]
0x18004bc53  mov     r9, rdi
0x18004bc56  xor     r8d, r8d
0x18004bc59  mov     rcx, rbx
0x18004bc5c  call    cs:__imp_CheckTokenMembershipEx
0x18004bc62  test    eax, eax
0x18004bc64  jz      short loc_18004BC6A
0x18004bc66  mov     ebx, esi
0x18004bc68  jmp     short loc_18004BC7E
0x18004bc6a  call    cs:__imp_GetLastError
0x18004bc70  test    eax, eax
0x18004bc72  jle     short loc_18004BC7C
0x18004bc74  movzx   eax, ax
0x18004bc77  or      eax, 80070000h
0x18004bc7c  mov     ebx, eax
0x18004bc7e  lea     rcx, [rsp+88h+var_28]
0x18004bc83  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004bc88  mov     eax, ebx
0x18004bc8a  mov     rcx, [rsp+88h+var_18]
0x18004bc8f  xor     rcx, rsp; StackCookie
0x18004bc92  call    __security_check_cookie
0x18004bc97  lea     r11, [rsp+88h+var_8]
0x18004bc9f  mov     rbx, [r11+20h]
0x18004bca3  mov     rsi, [r11+28h]
0x18004bca7  mov     rsp, r11
0x18004bcaa  pop     rdi
0x18004bcab  retn
```
