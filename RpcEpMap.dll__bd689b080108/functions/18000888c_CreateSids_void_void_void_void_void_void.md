# CreateSids(void * *,void * *,void * *,void * *,void * *,void * *)

- ea: `0x18000888c`
- end: `0x180008b40`
- name: `?CreateSids@@YAHPEAPEAX00000@Z`
- size: `692`
- prototype: `__int64 __fastcall(PSID *pSid, PSID *, PSID *, PSID *, PSID *, PSID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008b80`

## callees

- `0x18000888c`
- `0x18000a980`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008962`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800089c9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800089d5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008a21`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008a2d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008a39`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008a88`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008a94`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008aa0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008aac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008af8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008b04`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008b10`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008b1c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008b28`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008962`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800089c9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800089d5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008a21`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008a2d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008a39`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008a88`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008a94`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008aa0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008aac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008af8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008b04`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008b10`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008b1c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008b28`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000891b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180008955`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800089bc`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180008a14`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180008a7b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180008aea`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000891b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180008955`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800089bc`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180008a14`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180008a7b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180008aea`

## pseudocode

```c
__int64 __fastcall CreateSids(PSID *pSid, PSID *a2, PSID *a3, PSID *a4, PSID *a5, PSID *a6)
{
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-19h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v12; // [rsp+68h] [rbp-11h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v13; // [rsp+70h] [rbp-9h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v13.Value = 0;
  *(_WORD *)&v13.Value[4] = 256;
  *(_DWORD *)v12.Value = 0;
  *(_WORD *)&v12.Value[4] = 3840;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, pSid) )
    return 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, a2) )
  {
    FreeSid(*pSid);
    *pSid = 0;
    return 0;
  }
  if ( !AllocateAndInitializeSid(&v13, 1u, 0, 0, 0, 0, 0, 0, 0, 0, a3) )
  {
    FreeSid(*pSid);
    *pSid = 0;
    FreeSid(*a2);
    *a2 = 0;
    return 0;
  }
  if ( !AllocateAndInitializeSid(&v12, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, a4) )
  {
    FreeSid(*pSid);
    *pSid = 0;
    FreeSid(*a2);
    *a2 = 0;
    FreeSid(*a3);
    *a3 = 0;
    return 0;
  }
  if ( !AllocateAndInitializeSid(&v12, 2u, 2u, 2u, 0, 0, 0, 0, 0, 0, a5) )
  {
    FreeSid(*pSid);
    *pSid = 0;
    FreeSid(*a2);
    *a2 = 0;
    FreeSid(*a3);
    *a3 = 0;
    FreeSid(*a4);
    *a4 = 0;
    return 0;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 7u, 0, 0, 0, 0, 0, 0, 0, a6) )
  {
    __debugbreak();
    FreeSid(*pSid);
    *pSid = 0;
    FreeSid(*a2);
    *a2 = 0;
    FreeSid(*a3);
    *a3 = 0;
    FreeSid(*a4);
    *a4 = 0;
    FreeSid(*a5);
    *a5 = 0;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000888c  push    rbp
0x18000888e  push    rbx
0x18000888f  push    rsi
0x180008890  push    rdi
0x180008891  push    r12
0x180008893  push    r13
0x180008895  push    r14
0x180008897  push    r15
0x180008899  lea     rbp, [rsp-0Fh]
0x18000889e  sub     rsp, 88h
0x1800088a5  mov     rax, cs:__security_cookie
0x1800088ac  xor     rax, rsp
0x1800088af  mov     [rbp+47h+var_48], rax
0x1800088b3  mov     r15, [rbp+47h+arg_20]
0x1800088b7  xor     r13d, r13d
0x1800088ba  mov     r12, [rbp+47h+arg_28]
0x1800088be  mov     r14, r9
0x1800088c1  mov     [rsp+0C0h+pSid], rcx; pSid
0x1800088c6  mov     rsi, r8
0x1800088c9  mov     [rsp+0C0h+nSubAuthority7], r13d; nSubAuthority7
0x1800088ce  mov     rdi, rdx
0x1800088d1  mov     [rsp+0C0h+nSubAuthority6], r13d; nSubAuthority6
0x1800088d6  lea     r8d, [r13+20h]; nSubAuthority0
0x1800088da  mov     [rsp+0C0h+nSubAuthority5], r13d; nSubAuthority5
0x1800088df  mov     rbx, rcx
0x1800088e2  mov     [rsp+0C0h+nSubAuthority4], r13d; nSubAuthority4
0x1800088e7  lea     rcx, [rbp+47h+pIdentifierAuthority]; pIdentifierAuthority
0x1800088eb  mov     [rsp+0C0h+nSubAuthority3], r13d; nSubAuthority3
0x1800088f0  mov     r9d, 220h; nSubAuthority1
0x1800088f6  mov     dl, 2; nSubAuthorityCount
0x1800088f8  mov     [rsp+0C0h+nSubAuthority2], r13d; nSubAuthority2
0x1800088fd  mov     dword ptr [rbp+47h+pIdentifierAuthority.Value], r13d
0x180008901  mov     word ptr [rbp+47h+pIdentifierAuthority.Value+4], 500h
0x180008907  mov     dword ptr [rbp+47h+var_50.Value], r13d
0x18000890b  mov     word ptr [rbp+47h+var_50.Value+4], 100h
0x180008911  mov     dword ptr [rbp+47h+var_58.Value], r13d
0x180008915  mov     word ptr [rbp+47h+var_58.Value+4], 0F00h
0x18000891b  call    cs:__imp_AllocateAndInitializeSid
0x180008921  test    eax, eax
0x180008923  jz      short loc_18000896B
0x180008925  mov     [rsp+0C0h+pSid], rdi; pSid
0x18000892a  lea     r8d, [r13+12h]; nSubAuthority0
0x18000892e  mov     [rsp+0C0h+nSubAuthority7], r13d; nSubAuthority7
0x180008933  lea     rcx, [rbp+47h+pIdentifierAuthority]; pIdentifierAuthority
0x180008937  mov     [rsp+0C0h+nSubAuthority6], r13d; nSubAuthority6
0x18000893c  xor     r9d, r9d; nSubAuthority1
0x18000893f  mov     [rsp+0C0h+nSubAuthority5], r13d; nSubAuthority5
0x180008944  mov     dl, 1; nSubAuthorityCount
0x180008946  mov     [rsp+0C0h+nSubAuthority4], r13d; nSubAuthority4
0x18000894b  mov     [rsp+0C0h+nSubAuthority3], r13d; nSubAuthority3
0x180008950  mov     [rsp+0C0h+nSubAuthority2], r13d; nSubAuthority2
0x180008955  call    cs:__imp_AllocateAndInitializeSid
0x18000895b  test    eax, eax
0x18000895d  jnz     short loc_18000898D
0x18000895f  mov     rcx, [rbx]; pSid
0x180008962  call    cs:__imp_FreeSid
0x180008968  mov     [rbx], r13
0x18000896b  xor     eax, eax
0x18000896d  mov     rcx, [rbp+47h+var_48]
0x180008971  xor     rcx, rsp; StackCookie
0x180008974  call    __security_check_cookie
0x180008979  add     rsp, 88h
0x180008980  pop     r15
0x180008982  pop     r14
0x180008984  pop     r13
0x180008986  pop     r12
0x180008988  pop     rdi
0x180008989  pop     rsi
0x18000898a  pop     rbx
0x18000898b  pop     rbp
0x18000898c  retn
0x18000898d  mov     [rsp+0C0h+pSid], rsi; pSid
0x180008992  lea     rcx, [rbp+47h+var_50]; pIdentifierAuthority
0x180008996  mov     [rsp+0C0h+nSubAuthority7], r13d; nSubAuthority7
0x18000899b  xor     r9d, r9d; nSubAuthority1
0x18000899e  mov     [rsp+0C0h+nSubAuthority6], r13d; nSubAuthority6
0x1800089a3  xor     r8d, r8d; nSubAuthority0
0x1800089a6  mov     [rsp+0C0h+nSubAuthority5], r13d; nSubAuthority5
0x1800089ab  mov     dl, 1; nSubAuthorityCount
0x1800089ad  mov     [rsp+0C0h+nSubAuthority4], r13d; nSubAuthority4
0x1800089b2  mov     [rsp+0C0h+nSubAuthority3], r13d; nSubAuthority3
0x1800089b7  mov     [rsp+0C0h+nSubAuthority2], r13d; nSubAuthority2
0x1800089bc  call    cs:__imp_AllocateAndInitializeSid
0x1800089c2  test    eax, eax
0x1800089c4  jnz     short loc_1800089E0
0x1800089c6  mov     rcx, [rbx]; pSid
0x1800089c9  call    cs:__imp_FreeSid
0x1800089cf  mov     [rbx], r13
0x1800089d2  mov     rcx, [rdi]; pSid
0x1800089d5  call    cs:__imp_FreeSid
0x1800089db  mov     [rdi], r13
0x1800089de  jmp     short loc_18000896B
0x1800089e0  mov     [rsp+0C0h+pSid], r14; pSid
0x1800089e5  lea     rcx, [rbp+47h+var_58]; pIdentifierAuthority
0x1800089e9  mov     [rsp+0C0h+nSubAuthority7], r13d; nSubAuthority7
0x1800089ee  mov     r9d, 1; nSubAuthority1
0x1800089f4  mov     [rsp+0C0h+nSubAuthority6], r13d; nSubAuthority6
0x1800089f9  mov     [rsp+0C0h+nSubAuthority5], r13d; nSubAuthority5
0x1800089fe  mov     [rsp+0C0h+nSubAuthority4], r13d; nSubAuthority4
0x180008a03  lea     r8d, [r9+1]; nSubAuthority0
0x180008a07  mov     [rsp+0C0h+nSubAuthority3], r13d; nSubAuthority3
0x180008a0c  mov     dl, r8b; nSubAuthorityCount
0x180008a0f  mov     [rsp+0C0h+nSubAuthority2], r13d; nSubAuthority2
0x180008a14  call    cs:__imp_AllocateAndInitializeSid
0x180008a1a  test    eax, eax
0x180008a1c  jnz     short loc_180008A47
0x180008a1e  mov     rcx, [rbx]; pSid
0x180008a21  call    cs:__imp_FreeSid
0x180008a27  mov     [rbx], r13
0x180008a2a  mov     rcx, [rdi]; pSid
0x180008a2d  call    cs:__imp_FreeSid
0x180008a33  mov     [rdi], r13
0x180008a36  mov     rcx, [rsi]; pSid
0x180008a39  call    cs:__imp_FreeSid
0x180008a3f  mov     [rsi], r13
0x180008a42  jmp     loc_18000896B
0x180008a47  mov     [rsp+0C0h+pSid], r15; pSid
0x180008a4c  lea     rcx, [rbp+47h+var_58]; pIdentifierAuthority
0x180008a50  mov     [rsp+0C0h+nSubAuthority7], r13d; nSubAuthority7
0x180008a55  mov     eax, 2
0x180008a5a  mov     [rsp+0C0h+nSubAuthority6], r13d; nSubAuthority6
0x180008a5f  mov     r9d, eax; nSubAuthority1
0x180008a62  mov     [rsp+0C0h+nSubAuthority5], r13d; nSubAuthority5
0x180008a67  mov     r8d, eax; nSubAuthority0
0x180008a6a  mov     [rsp+0C0h+nSubAuthority4], r13d; nSubAuthority4
0x180008a6f  mov     dl, al; nSubAuthorityCount
0x180008a71  mov     [rsp+0C0h+nSubAuthority3], r13d; nSubAuthority3
0x180008a76  mov     [rsp+0C0h+nSubAuthority2], r13d; nSubAuthority2
0x180008a7b  call    cs:__imp_AllocateAndInitializeSid
0x180008a81  test    eax, eax
0x180008a83  jnz     short loc_180008ABA
0x180008a85  mov     rcx, [rbx]; pSid
0x180008a88  call    cs:__imp_FreeSid
0x180008a8e  mov     [rbx], r13
0x180008a91  mov     rcx, [rdi]; pSid
0x180008a94  call    cs:__imp_FreeSid
0x180008a9a  mov     [rdi], r13
0x180008a9d  mov     rcx, [rsi]; pSid
0x180008aa0  call    cs:__imp_FreeSid
0x180008aa6  mov     [rsi], r13
0x180008aa9  mov     rcx, [r14]; pSid
0x180008aac  call    cs:__imp_FreeSid
0x180008ab2  mov     [r14], r13
0x180008ab5  jmp     loc_18000896B
0x180008aba  mov     [rsp+0C0h+pSid], r12; pSid
0x180008abf  lea     rcx, [rbp+47h+pIdentifierAuthority]; pIdentifierAuthority
0x180008ac3  mov     [rsp+0C0h+nSubAuthority7], r13d; nSubAuthority7
0x180008ac8  xor     r9d, r9d; nSubAuthority1
0x180008acb  mov     [rsp+0C0h+nSubAuthority6], r13d; nSubAuthority6
0x180008ad0  mov     dl, 1; nSubAuthorityCount
0x180008ad2  mov     [rsp+0C0h+nSubAuthority5], r13d; nSubAuthority5
0x180008ad7  mov     [rsp+0C0h+nSubAuthority4], r13d; nSubAuthority4
0x180008adc  mov     [rsp+0C0h+nSubAuthority3], r13d; nSubAuthority3
0x180008ae1  lea     r8d, [r9+7]; nSubAuthority0
0x180008ae5  mov     [rsp+0C0h+nSubAuthority2], r13d; nSubAuthority2
0x180008aea  call    cs:__imp_AllocateAndInitializeSid
0x180008af0  test    eax, eax
0x180008af2  jnz     short loc_180008B36
0x180008af4  int     3; Trap to Debugger
0x180008af5  mov     rcx, [rbx]; pSid
0x180008af8  call    cs:__imp_FreeSid
0x180008afe  mov     [rbx], r13
0x180008b01  mov     rcx, [rdi]; pSid
0x180008b04  call    cs:__imp_FreeSid
0x180008b0a  mov     [rdi], r13
0x180008b0d  mov     rcx, [rsi]; pSid
0x180008b10  call    cs:__imp_FreeSid
0x180008b16  mov     [rsi], r13
0x180008b19  mov     rcx, [r14]; pSid
0x180008b1c  call    cs:__imp_FreeSid
0x180008b22  mov     [r14], r13
0x180008b25  mov     rcx, [r15]; pSid
0x180008b28  call    cs:__imp_FreeSid
0x180008b2e  mov     [r15], r13
0x180008b31  jmp     loc_18000896B
0x180008b36  mov     eax, 1
0x180008b3b  jmp     loc_18000896D
```
