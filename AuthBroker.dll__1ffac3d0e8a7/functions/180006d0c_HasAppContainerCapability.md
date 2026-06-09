# _HasAppContainerCapability

- ea: `0x180006d0c`
- end: `0x180006dd0`
- name: `_HasAppContainerCapability`
- size: `196`
- prototype: `int __fastcall(void *tokenHandle, unsigned int capabilityToCheck)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002b20`
- `0x1800047d0`
- `0x180011034`

## callees

- `0x180006d0c`
- `0x180020520`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006d77`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006d77`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006d9d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006d9d`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180006d8c`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180006d8c`

## pseudocode

```c
_BOOL8 __fastcall HasAppContainerCapability(void *tokenHandle, DWORD capabilityToCheck)
{
  int hasCapability; // [rsp+60h] [rbp-20h] BYREF
  void *pSid; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY AppAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&AppAuthority.Value[4] = 3840;
  hasCapability = 0;
  *(_DWORD *)AppAuthority.Value = 0;
  pSid = 0;
  if ( !tokenHandle || !AllocateAndInitializeSid(&AppAuthority, 2u, 3u, capabilityToCheck, 0, 0, 0, 0, 0, 0, &pSid) )
    return 0;
  if ( !(unsigned int)CheckTokenCapability(tokenHandle, pSid, &hasCapability) )
    hasCapability = 0;
  FreeSid(pSid);
  return hasCapability != 0;
}

```

## disassembly

```asm
0x180006d0c  mov     [rsp-8+arg_10], rbx
0x180006d11  mov     [rsp-8+arg_18], rdi
0x180006d16  push    rbp
0x180006d17  mov     rbp, rsp
0x180006d1a  sub     rsp, 80h
0x180006d21  mov     rax, cs:__security_cookie
0x180006d28  xor     rax, rsp
0x180006d2b  mov     [rbp+var_8], rax
0x180006d2f  xor     edi, edi
0x180006d31  mov     word ptr [rbp+AppAuthority.Value+4], 0F00h
0x180006d37  mov     [rbp+hasCapability], edi
0x180006d3a  mov     rbx, tokenHandle
0x180006d3d  mov     dword ptr [rbp+AppAuthority.Value], edi
0x180006d40  mov     [rbp+pSid], rdi
0x180006d44  test    tokenHandle, tokenHandle
0x180006d47  jz      short loc_180006DAD
0x180006d49  lea     rax, [rbp+pSid]
0x180006d4d  mov     r9d, capabilityToCheck; nSubAuthority1
0x180006d50  mov     [rsp+80h+var_30], rax; pSid
0x180006d55  lea     r8d, [rdi+3]; nSubAuthority0
0x180006d59  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180006d5d  lea     tokenHandle, [rbp+AppAuthority]; pIdentifierAuthority
0x180006d61  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180006d65  mov     dl, 2; nSubAuthorityCount
0x180006d67  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x180006d6b  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180006d6f  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x180006d73  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180006d77  call    cs:__imp_AllocateAndInitializeSid
0x180006d7d  test    eax, eax
0x180006d7f  jz      short loc_180006DAD
0x180006d81  mov     rdx, [rbp+pSid]
0x180006d85  lea     r8, [rbp+hasCapability]
0x180006d89  mov     tokenHandle, rbx
0x180006d8c  call    cs:__imp_CheckTokenCapability
0x180006d92  test    eax, eax
0x180006d94  jnz     short loc_180006D99
0x180006d96  mov     [rbp+hasCapability], edi
0x180006d99  mov     tokenHandle, [rbp+pSid]; pSid
0x180006d9d  call    cs:__imp_FreeSid
0x180006da3  cmp     [rbp+hasCapability], edi
0x180006da6  mov     eax, edi
0x180006da8  setnz   al
0x180006dab  jmp     short loc_180006DAF
0x180006dad  xor     eax, eax
0x180006daf  mov     tokenHandle, [rbp+var_8]
0x180006db3  xor     tokenHandle, rsp; StackCookie
0x180006db6  call    __security_check_cookie
0x180006dbb  lea     r11, [rsp+80h+var_s0]
0x180006dc3  mov     rbx, [r11+20h]
0x180006dc7  mov     rdi, [r11+28h]
0x180006dcb  mov     rsp, r11
0x180006dce  pop     rbp
0x180006dcf  retn
```
