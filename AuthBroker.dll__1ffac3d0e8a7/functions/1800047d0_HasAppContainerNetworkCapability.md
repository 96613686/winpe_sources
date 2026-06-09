# _HasAppContainerNetworkCapability

- ea: `0x1800047d0`
- end: `0x1800048b0`
- name: `_HasAppContainerNetworkCapability`
- size: `224`
- prototype: `int __fastcall(void *tokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002b20`

## callees

- `0x1800047d0`
- `0x180006d0c`
- `0x180020520`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000483f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000483f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180004869`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180004869`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180004856`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180004856`

## pseudocode

```c
_BOOL8 __fastcall HasAppContainerNetworkCapability(void *tokenHandle)
{
  int v3; // [rsp+60h] [rbp-28h] BYREF
  PSID pSid; // [rsp+68h] [rbp-20h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-18h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  v3 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  if ( !tokenHandle || !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 3u, 1u, 0, 0, 0, 0, 0, 0, &pSid) )
    return HasAppContainerCapability(tokenHandle, 2u);
  if ( !(unsigned int)CheckTokenCapability(tokenHandle, pSid, &v3) )
    v3 = 0;
  FreeSid(pSid);
  return v3 || HasAppContainerCapability(tokenHandle, 2u);
}

```

## disassembly

```asm
0x1800047d0  mov     [rsp+arg_8], rbx
0x1800047d5  push    rdi
0x1800047d6  sub     rsp, 80h
0x1800047dd  mov     rax, cs:__security_cookie
0x1800047e4  xor     rax, rsp
0x1800047e7  mov     [rsp+88h+var_10], rax
0x1800047ec  xor     edi, edi
0x1800047ee  mov     word ptr [rsp+88h+pIdentifierAuthority.Value+4], 0F00h
0x1800047f5  mov     [rsp+88h+var_28], edi
0x1800047f9  mov     rbx, tokenHandle
0x1800047fc  mov     dword ptr [rsp+88h+pIdentifierAuthority.Value], edi
0x180004800  mov     [rsp+88h+var_20], rdi
0x180004805  test    tokenHandle, tokenHandle
0x180004808  jz      short loc_18000487C
0x18000480a  lea     rax, [rsp+88h+var_20]
0x18000480f  mov     r9d, 1; nSubAuthority1
0x180004815  mov     [rsp+88h+pSid], rax; pSid
0x18000481a  lea     tokenHandle, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x18000481f  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x180004823  mov     r8d, 3; nSubAuthority0
0x180004829  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x18000482d  mov     dl, 2; nSubAuthorityCount
0x18000482f  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x180004833  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x180004837  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x18000483b  mov     [rsp+88h+nSubAuthority2], edi; nSubAuthority2
0x18000483f  call    cs:__imp_AllocateAndInitializeSid
0x180004845  test    eax, eax
0x180004847  jz      short loc_18000487C
0x180004849  mov     rdx, [rsp+88h+var_20]
0x18000484e  lea     r8, [rsp+88h+var_28]
0x180004853  mov     tokenHandle, rbx
0x180004856  call    cs:__imp_CheckTokenCapability
0x18000485c  test    eax, eax
0x18000485e  jnz     short loc_180004864
0x180004860  mov     [rsp+88h+var_28], edi
0x180004864  mov     tokenHandle, [rsp+88h+var_20]; pSid
0x180004869  call    cs:__imp_FreeSid
0x18000486f  cmp     [rsp+88h+var_28], edi
0x180004873  jz      short loc_18000487C
0x180004875  mov     eax, 1
0x18000487a  jmp     short loc_180004892
0x18000487c  mov     edx, 2; capabilityToCheck
0x180004881  mov     tokenHandle, rbx; tokenHandle
0x180004884  call    _HasAppContainerCapability
0x180004889  test    eax, eax
0x18000488b  mov     ecx, edi
0x18000488d  setnz   cl
0x180004890  mov     eax, ecx
0x180004892  mov     tokenHandle, [rsp+88h+var_10]
0x180004897  xor     tokenHandle, rsp; StackCookie
0x18000489a  call    __security_check_cookie
0x18000489f  mov     rbx, [rsp+88h+arg_8]
0x1800048a7  add     rsp, 80h
0x1800048ae  pop     rdi
0x1800048af  retn
```
