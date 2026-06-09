# WaasMedic::TakeOwnershipAndRestoreSD(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x180029d14`
- end: `0x180029e0e`
- name: `?TakeOwnershipAndRestoreSD@WaasMedic@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004c298`
- `0x18004ca5c`

## callees

- `0x180003bb0`
- `0x180009a34`
- `0x180009a54`
- `0x180029d14`
- `0x180031224`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180029d7d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180029d7d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029da7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029dec`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029da7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029dec`

## pseudocode

```c
__int64 __fastcall WaasMedic::TakeOwnershipAndRestoreSD(HKEY *a1, const WCHAR *a2, void *a3)
{
  const char *v6; // r9
  unsigned int LastError; // ebx
  int v9; // eax
  DWORD nSubAuthority2; // [rsp+20h] [rbp-60h]
  PSID pSid; // [rsp+60h] [rbp-20h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xD7D,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\regutil.cpp",
                  v6);
LABEL_3:
    if ( pSid )
      FreeSid(pSid);
    return LastError;
  }
  v9 = WaasMedic::SetRegOwnershipAndDACL((__int64)&pSid, a1, a2, a3);
  LastError = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7F,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\regutil.cpp",
      (const char *)(unsigned int)v9,
      nSubAuthority2);
    goto LABEL_3;
  }
  if ( pSid )
    FreeSid(pSid);
  return 0;
}

```

## disassembly

```asm
0x180029d14  mov     r11, rsp
0x180029d17  push    rbp
0x180029d18  push    rbx
0x180029d19  push    rsi
0x180029d1a  push    rdi
0x180029d1b  push    r14
0x180029d1d  mov     rbp, rsp
0x180029d20  sub     rsp, 80h
0x180029d27  mov     rax, cs:__security_cookie
0x180029d2e  xor     rax, rsp
0x180029d31  mov     [rbp+var_10], rax
0x180029d35  xor     r14d, r14d
0x180029d38  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180029d3e  lea     rax, [rbp+pSid]
0x180029d42  mov     dword ptr [rbp+pIdentifierAuthority.Value], r14d
0x180029d46  mov     [r11-58h], rax
0x180029d4a  mov     rsi, r8
0x180029d4d  mov     [r11-60h], r14d
0x180029d51  mov     rdi, rdx
0x180029d54  mov     [r11-68h], r14d
0x180029d58  lea     r8d, [r14+12h]; nSubAuthority0
0x180029d5c  mov     [r11-70h], r14d
0x180029d60  mov     rbx, rcx
0x180029d63  mov     [r11-78h], r14d
0x180029d67  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180029d6b  mov     [r11-80h], r14d
0x180029d6f  xor     r9d, r9d; nSubAuthority1
0x180029d72  mov     dl, 1; nSubAuthorityCount
0x180029d74  mov     [rsp+80h+nSubAuthority2], r14d; int
0x180029d79  mov     [rbp+pSid], r14
0x180029d7d  call    cs:__imp_AllocateAndInitializeSid
0x180029d83  test    eax, eax
0x180029d85  jnz     short loc_180029DB1
0x180029d87  mov     rcx, [rbp+28h]; this
0x180029d8b  lea     r8, aOnecoreEnduser_30; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180029d92  mov     edx, 0D7Dh; void *
0x180029d97  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180029d9c  mov     ebx, eax
0x180029d9e  mov     rcx, [rbp+pSid]; pSid
0x180029da2  test    rcx, rcx
0x180029da5  jz      short loc_180029DAD
0x180029da7  call    cs:__imp_FreeSid
0x180029dad  mov     eax, ebx
0x180029daf  jmp     short loc_180029DF4
0x180029db1  mov     r9, rsi
0x180029db4  lea     rcx, [rbp+pSid]
0x180029db8  mov     r8, rdi
0x180029dbb  mov     rdx, rbx
0x180029dbe  call    ?SetRegOwnershipAndDACL@WaasMedic@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; WaasMedic::SetRegOwnershipAndDACL(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,void *)
0x180029dc3  mov     ebx, eax
0x180029dc5  test    eax, eax
0x180029dc7  jns     short loc_180029DE3
0x180029dc9  mov     rcx, [rbp+28h]; this
0x180029dcd  lea     r8, aOnecoreEnduser_30; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180029dd4  mov     r9d, eax; char *
0x180029dd7  mov     edx, 0D7Fh; void *
0x180029ddc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029de1  jmp     short loc_180029D9E
0x180029de3  mov     rcx, [rbp+pSid]; pSid
0x180029de7  test    rcx, rcx
0x180029dea  jz      short loc_180029DF2
0x180029dec  call    cs:__imp_FreeSid
0x180029df2  xor     eax, eax
0x180029df4  mov     rcx, [rbp+var_10]
0x180029df8  xor     rcx, rsp; StackCookie
0x180029dfb  call    __security_check_cookie
0x180029e00  add     rsp, 80h
0x180029e07  pop     r14
0x180029e09  pop     rdi
0x180029e0a  pop     rsi
0x180029e0b  pop     rbx
0x180029e0c  pop     rbp
0x180029e0d  retn
```
