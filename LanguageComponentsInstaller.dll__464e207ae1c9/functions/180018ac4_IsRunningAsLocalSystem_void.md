# IsRunningAsLocalSystem(void)

- ea: `0x180018ac4`
- end: `0x180018b86`
- name: `?IsRunningAsLocalSystem@@YA_NXZ`
- size: `194`
- prototype: `char(void)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bc70`
- `0x180013c74`
- `0x18001844c`
- `0x18001b5b4`
- `0x18001d0f0`

## callees

- `0x180003520`
- `0x180018ac4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180018b36`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180018b36`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180018b1f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180018b1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018b4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018b61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018b4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018b61`

## pseudocode

```c
char IsRunningAsLocalSystem(void)
{
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-20h] BYREF
  WINBOOL IsMember; // [rsp+68h] [rbp-18h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck)
    && (IsMember = 0, CheckTokenMembership(0, SidToCheck, &IsMember))
    && IsMember )
  {
    if ( SidToCheck )
      LocalFree(SidToCheck);
    return 1;
  }
  else
  {
    if ( SidToCheck )
      LocalFree(SidToCheck);
    return 0;
  }
}

```

## disassembly

```asm
0x180018ac4  mov     [rsp-8+arg_0], rbx
0x180018ac9  push    rbp
0x180018aca  mov     rbp, rsp
0x180018acd  sub     rsp, 80h
0x180018ad4  mov     rax, cs:__security_cookie
0x180018adb  xor     rax, rsp
0x180018ade  mov     [rbp+var_8], rax
0x180018ae2  xor     ebx, ebx
0x180018ae4  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180018aea  lea     rax, [rbp+SidToCheck]
0x180018aee  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x180018af1  mov     [rsp+80h+pSid], rax; pSid
0x180018af6  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180018afa  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x180018afe  xor     r9d, r9d; nSubAuthority1
0x180018b01  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x180018b05  lea     r8d, [rbx+12h]; nSubAuthority0
0x180018b09  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x180018b0d  mov     dl, 1; nSubAuthorityCount
0x180018b0f  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x180018b13  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x180018b17  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x180018b1b  mov     [rbp+SidToCheck], rbx
0x180018b1f  call    cs:__imp_AllocateAndInitializeSid
0x180018b25  test    eax, eax
0x180018b27  jz      short loc_180018B58
0x180018b29  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180018b2d  lea     r8, [rbp+IsMember]; IsMember
0x180018b31  xor     ecx, ecx; TokenHandle
0x180018b33  mov     [rbp+IsMember], ebx
0x180018b36  call    cs:__imp_CheckTokenMembership
0x180018b3c  test    eax, eax
0x180018b3e  jz      short loc_180018B58
0x180018b40  cmp     [rbp+IsMember], ebx
0x180018b43  jz      short loc_180018B58
0x180018b45  mov     rcx, [rbp+SidToCheck]; hMem
0x180018b49  test    rcx, rcx
0x180018b4c  jz      short loc_180018B54
0x180018b4e  call    cs:__imp_LocalFree
0x180018b54  mov     al, 1
0x180018b56  jmp     short loc_180018B69
0x180018b58  mov     rcx, [rbp+SidToCheck]; hMem
0x180018b5c  test    rcx, rcx
0x180018b5f  jz      short loc_180018B67
0x180018b61  call    cs:__imp_LocalFree
0x180018b67  xor     al, al
0x180018b69  mov     rcx, [rbp+var_8]
0x180018b6d  xor     rcx, rsp; StackCookie
0x180018b70  call    __security_check_cookie
0x180018b75  mov     rbx, [rsp+80h+arg_0]
0x180018b7d  add     rsp, 80h
0x180018b84  pop     rbp
0x180018b85  retn
```
