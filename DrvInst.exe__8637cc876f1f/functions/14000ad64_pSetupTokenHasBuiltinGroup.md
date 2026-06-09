# pSetupTokenHasBuiltinGroup

- ea: `0x14000ad64`
- end: `0x14000ae1c`
- name: `pSetupTokenHasBuiltinGroup`
- size: `184`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, DWORD nSubAuthority1)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140022330`
- `0x140022bc8`

## callees

- `0x14000ad64`
- `0x14000ae24`
- `0x140045f30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000adf5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000adf5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000adc6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14000adc6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14000add4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14000add4`

## pseudocode

```c
__int64 __fastcall pSetupTokenHasBuiltinGroup(HANDLE TokenHandle, DWORD nSubAuthority1)
{
  unsigned int HasGroupSID; // ebx
  PSID SidToCheck; // [rsp+60h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  HasGroupSID = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, nSubAuthority1, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( IsValidSid(SidToCheck) )
      HasGroupSID = pSetupTokenHasGroupSID(TokenHandle, SidToCheck);
    if ( SidToCheck )
      FreeSid(SidToCheck);
  }
  return HasGroupSID;
}

```

## disassembly

```asm
0x14000ad64  mov     [rsp-18h+arg_10], rbx
0x14000ad69  push    rbp
0x14000ad6a  push    rsi
0x14000ad6b  push    rdi
0x14000ad6c  mov     rbp, rsp
0x14000ad6f  sub     rsp, 80h
0x14000ad76  mov     rax, cs:__security_cookie
0x14000ad7d  xor     rax, rsp
0x14000ad80  mov     [rbp+var_10], rax
0x14000ad84  xor     esi, esi
0x14000ad86  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x14000ad8c  lea     rax, [rbp+SidToCheck]
0x14000ad90  mov     dword ptr [rbp+pIdentifierAuthority.Value], esi
0x14000ad93  mov     [rsp+80h+pSid], rax; pSid
0x14000ad98  mov     rdi, rcx
0x14000ad9b  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x14000ad9f  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x14000ada3  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x14000ada7  lea     r8d, [rsi+20h]; nSubAuthority0
0x14000adab  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x14000adaf  mov     r9d, edx; nSubAuthority1
0x14000adb2  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x14000adb6  mov     dl, 2; nSubAuthorityCount
0x14000adb8  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x14000adbc  mov     ebx, esi
0x14000adbe  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x14000adc2  mov     [rbp+SidToCheck], rsi
0x14000adc6  call    cs:__imp_AllocateAndInitializeSid
0x14000adcc  test    eax, eax
0x14000adce  jz      short loc_14000ADFB
0x14000add0  mov     rcx, [rbp+SidToCheck]; pSid
0x14000add4  call    cs:__imp_IsValidSid
0x14000adda  test    eax, eax
0x14000addc  jz      short loc_14000ADEC
0x14000adde  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x14000ade2  mov     rcx, rdi; TokenHandle
0x14000ade5  call    pSetupTokenHasGroupSID
0x14000adea  mov     ebx, eax
0x14000adec  mov     rcx, [rbp+SidToCheck]; pSid
0x14000adf0  test    rcx, rcx
0x14000adf3  jz      short loc_14000ADFB
0x14000adf5  call    cs:__imp_FreeSid
0x14000adfb  mov     eax, ebx
0x14000adfd  mov     rcx, [rbp+var_10]
0x14000ae01  xor     rcx, rsp; StackCookie
0x14000ae04  call    __security_check_cookie
0x14000ae09  mov     rbx, [rsp+80h+arg_10]
0x14000ae11  add     rsp, 80h
0x14000ae18  pop     rdi
0x14000ae19  pop     rsi
0x14000ae1a  pop     rbp
0x14000ae1b  retn
```
