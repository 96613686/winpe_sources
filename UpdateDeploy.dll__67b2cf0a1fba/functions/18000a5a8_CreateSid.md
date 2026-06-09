# CreateSid

- ea: `0x18000a5a8`
- end: `0x18000a68d`
- name: `CreateSid`
- size: `229`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009f84`
- `0x18000dff4`
- `0x18000e094`
- `0x18000e134`
- `0x18000e1dc`
- `0x18000e280`
- `0x18000e494`
- `0x18000e538`
- `0x18000e5dc`
- `0x180018124`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000a5a8`
- `0x180061960`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000a66e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000a66e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000a63c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000a63c`

## string_xrefs

- `0x18000a5ec`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x18000a64a`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

## pseudocode

```c
__int64 __fastcall CreateSid(volatile signed __int64 *a1, BYTE a2, DWORD a3, DWORD a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  DWORD v9; // r9d
  const char *v10; // r9
  DWORD nSubAuthority2; // [rsp+20h] [rbp-60h]
  PSID pSid; // [rsp+60h] [rbp-20h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  if ( !a1 )
  {
    v6 = -2147467261;
    v7 = 633;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)v6,
      nSubAuthority2);
    return v6;
  }
  if ( a2 > 2u )
  {
    v6 = -2147024809;
    v7 = 635;
    goto LABEL_3;
  }
  v9 = 0;
  if ( a2 == 2 )
    v9 = a4;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, a2, a3, v9, 0, 0, 0, 0, 0, 0, &pSid) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x288,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
             v10);
  if ( _InterlockedCompareExchange64(a1, (signed __int64)pSid, 0) )
    FreeSid(pSid);
  return 0;
}

```

## disassembly

```asm
0x18000a5a8  push    rbp
0x18000a5aa  push    rbx
0x18000a5ab  push    rdi
0x18000a5ac  mov     rbp, rsp
0x18000a5af  sub     rsp, 80h
0x18000a5b6  mov     rax, cs:__security_cookie
0x18000a5bd  xor     rax, rsp
0x18000a5c0  mov     [rbp+var_10], rax
0x18000a5c4  xor     edi, edi
0x18000a5c6  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18000a5cc  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x18000a5cf  mov     eax, r9d
0x18000a5d2  mov     [rbp+var_20], rdi
0x18000a5d6  mov     rbx, rcx
0x18000a5d9  test    rcx, rcx
0x18000a5dc  jnz     short loc_18000A5FF
0x18000a5de  mov     ebx, 80004003h
0x18000a5e3  mov     edx, 279h; void *
0x18000a5e8  mov     rcx, [rbp+18h]; this
0x18000a5ec  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000a5f3  mov     r9d, ebx; char *
0x18000a5f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5fb  mov     eax, ebx
0x18000a5fd  jmp     short loc_18000A676
0x18000a5ff  cmp     dl, 2
0x18000a602  jbe     short loc_18000A610
0x18000a604  mov     ebx, 80070057h
0x18000a609  mov     edx, 27Bh; nSubAuthorityCount
0x18000a60e  jmp     short loc_18000A5E8
0x18000a610  mov     r9d, edi
0x18000a613  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18000a617  cmovz   r9d, eax; nSubAuthority1
0x18000a61b  lea     rax, [rbp+var_20]
0x18000a61f  mov     [rsp+80h+pSid], rax; pSid
0x18000a624  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x18000a628  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x18000a62c  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x18000a630  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x18000a634  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x18000a638  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x18000a63c  call    cs:__imp_AllocateAndInitializeSid
0x18000a642  test    eax, eax
0x18000a644  jnz     short loc_18000A65D
0x18000a646  mov     rcx, [rbp+18h]; this
0x18000a64a  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000a651  mov     edx, 288h; void *
0x18000a656  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a65b  jmp     short loc_18000A676
0x18000a65d  mov     rcx, [rbp+var_20]
0x18000a661  xor     eax, eax
0x18000a663  lock cmpxchg [rbx], rcx
0x18000a668  jz      short loc_18000A674
0x18000a66a  mov     rcx, [rbp+var_20]; pSid
0x18000a66e  call    cs:__imp_FreeSid
0x18000a674  xor     eax, eax
0x18000a676  mov     rcx, [rbp+var_10]
0x18000a67a  xor     rcx, rsp; StackCookie
0x18000a67d  call    __security_check_cookie
0x18000a682  add     rsp, 80h
0x18000a689  pop     rdi
0x18000a68a  pop     rbx
0x18000a68b  pop     rbp
0x18000a68c  retn
```
