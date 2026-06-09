# CheckThreadAdmin

- ea: `0x18004be14`
- end: `0x18004bf15`
- name: `CheckThreadAdmin`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004adbc`

## callees

- `0x180004eb0`
- `0x180017a64`
- `0x18004be14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004becc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004becc`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004be7d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004be7d`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18004beb8`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18004beb8`

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
0x18004be14  mov     r11, rsp
0x18004be17  mov     [r11+18h], rbx
0x18004be1b  mov     [r11+20h], rsi
0x18004be1f  push    rdi
0x18004be20  sub     rsp, 80h
0x18004be27  mov     rax, cs:__security_cookie
0x18004be2e  xor     rax, rsp
0x18004be31  mov     [rsp+88h+var_18], rax
0x18004be36  xor     esi, esi
0x18004be38  mov     [rsp+88h+var_1C], 500h
0x18004be3f  lea     rax, [r11-28h]
0x18004be43  mov     [rsp+88h+var_20], esi
0x18004be47  mov     [r11-38h], rax
0x18004be4b  mov     rdi, rdx
0x18004be4e  mov     [rsp+88h+nSubAuthority7], esi; nSubAuthority7
0x18004be52  mov     rbx, rcx
0x18004be55  mov     [rsp+88h+nSubAuthority6], esi; nSubAuthority6
0x18004be59  lea     r8d, [rsi+20h]; nSubAuthority0
0x18004be5d  mov     [rsp+88h+nSubAuthority5], esi; nSubAuthority5
0x18004be61  lea     rcx, [r11-20h]; pIdentifierAuthority
0x18004be65  mov     [rsp+88h+nSubAuthority4], esi; nSubAuthority4
0x18004be69  mov     r9d, 220h; nSubAuthority1
0x18004be6f  mov     [rsp+88h+nSubAuthority3], esi; nSubAuthority3
0x18004be73  mov     dl, 2; nSubAuthorityCount
0x18004be75  mov     [rsp+88h+nSubAuthority2], esi; nSubAuthority2
0x18004be79  mov     [r11-28h], rsi
0x18004be7d  call    cs:__imp_AllocateAndInitializeSid
0x18004be84  nop     dword ptr [rax+rax+00h]
0x18004be89  test    eax, eax
0x18004be8b  jnz     short loc_18004BEAA
0x18004be8d  call    cs:__imp_GetLastError
0x18004be94  nop     dword ptr [rax+rax+00h]
0x18004be99  mov     ebx, eax
0x18004be9b  test    eax, eax
0x18004be9d  jle     short loc_18004BEE6
0x18004be9f  movzx   ebx, ax
0x18004bea2  or      ebx, 80070000h
0x18004bea8  jmp     short loc_18004BEE6
0x18004beaa  mov     rdx, [rsp+88h+var_28]
0x18004beaf  mov     r9, rdi
0x18004beb2  xor     r8d, r8d
0x18004beb5  mov     rcx, rbx
0x18004beb8  call    cs:__imp_CheckTokenMembershipEx
0x18004bebf  nop     dword ptr [rax+rax+00h]
0x18004bec4  test    eax, eax
0x18004bec6  jz      short loc_18004BECC
0x18004bec8  mov     ebx, esi
0x18004beca  jmp     short loc_18004BEE6
0x18004becc  call    cs:__imp_GetLastError
0x18004bed3  nop     dword ptr [rax+rax+00h]
0x18004bed8  test    eax, eax
0x18004beda  jle     short loc_18004BEE4
0x18004bedc  movzx   eax, ax
0x18004bedf  or      eax, 80070000h
0x18004bee4  mov     ebx, eax
0x18004bee6  lea     rcx, [rsp+88h+var_28]
0x18004beeb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004bef0  mov     eax, ebx
0x18004bef2  mov     rcx, [rsp+88h+var_18]
0x18004bef7  xor     rcx, rsp; StackCookie
0x18004befa  call    __security_check_cookie
0x18004beff  lea     r11, [rsp+88h+var_8]
0x18004bf07  mov     rbx, [r11+20h]
0x18004bf0b  mov     rsi, [r11+28h]
0x18004bf0f  mov     rsp, r11
0x18004bf12  pop     rdi
0x18004bf13  retn
```
