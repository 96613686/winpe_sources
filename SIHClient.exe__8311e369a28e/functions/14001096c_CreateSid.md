# CreateSid

- ea: `0x14001096c`
- end: `0x140010a51`
- name: `CreateSid`
- size: `229`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003ee0`
- `0x14000de14`
- `0x14000debc`
- `0x1400105b0`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x14001096c`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140010a32`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140010a32`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140010a00`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140010a00`

## string_xrefs

- `0x1400109b0`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x140010a0e`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

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
0x14001096c  push    rbp
0x14001096e  push    rbx
0x14001096f  push    rdi
0x140010970  mov     rbp, rsp
0x140010973  sub     rsp, 80h
0x14001097a  mov     rax, cs:__security_cookie
0x140010981  xor     rax, rsp
0x140010984  mov     [rbp+var_10], rax
0x140010988  xor     edi, edi
0x14001098a  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x140010990  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x140010993  mov     eax, r9d
0x140010996  mov     [rbp+var_20], rdi
0x14001099a  mov     rbx, rcx
0x14001099d  test    rcx, rcx
0x1400109a0  jnz     short loc_1400109C3
0x1400109a2  mov     ebx, 80004003h
0x1400109a7  mov     edx, 279h; void *
0x1400109ac  mov     rcx, [rbp+18h]; this
0x1400109b0  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400109b7  mov     r9d, ebx; char *
0x1400109ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400109bf  mov     eax, ebx
0x1400109c1  jmp     short loc_140010A3A
0x1400109c3  cmp     dl, 2
0x1400109c6  jbe     short loc_1400109D4
0x1400109c8  mov     ebx, 80070057h
0x1400109cd  mov     edx, 27Bh; nSubAuthorityCount
0x1400109d2  jmp     short loc_1400109AC
0x1400109d4  mov     r9d, edi
0x1400109d7  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1400109db  cmovz   r9d, eax; nSubAuthority1
0x1400109df  lea     rax, [rbp+var_20]
0x1400109e3  mov     [rsp+80h+pSid], rax; pSid
0x1400109e8  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x1400109ec  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x1400109f0  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x1400109f4  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x1400109f8  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x1400109fc  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x140010a00  call    cs:__imp_AllocateAndInitializeSid
0x140010a06  test    eax, eax
0x140010a08  jnz     short loc_140010A21
0x140010a0a  mov     rcx, [rbp+18h]; this
0x140010a0e  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140010a15  mov     edx, 288h; void *
0x140010a1a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140010a1f  jmp     short loc_140010A3A
0x140010a21  mov     rcx, [rbp+var_20]
0x140010a25  xor     eax, eax
0x140010a27  lock cmpxchg [rbx], rcx
0x140010a2c  jz      short loc_140010A38
0x140010a2e  mov     rcx, [rbp+var_20]; pSid
0x140010a32  call    cs:__imp_FreeSid
0x140010a38  xor     eax, eax
0x140010a3a  mov     rcx, [rbp+var_10]
0x140010a3e  xor     rcx, rsp; StackCookie
0x140010a41  call    __security_check_cookie
0x140010a46  add     rsp, 80h
0x140010a4d  pop     rdi
0x140010a4e  pop     rbx
0x140010a4f  pop     rbp
0x140010a50  retn
```
