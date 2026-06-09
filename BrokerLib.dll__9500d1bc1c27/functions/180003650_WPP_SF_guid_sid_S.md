# WPP_SF__guid__sid_S

- ea: `0x180003650`
- end: `0x18000374f`
- name: `WPP_SF__guid__sid_S`
- size: `255`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid, __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800012cc`
- `0x180002e88`
- `0x180003760`
- `0x180008554`
- `0x180008668`
- `0x18001849c`
- `0x1800185f4`

## callees

- `0x180003650`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000372f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000372f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800036c1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180003722`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800036c1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180003722`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000370a`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000370a`

## pseudocode

```c
ULONG __fastcall WPP_SF__guid__sid_S(
        TRACEHANDLE LoggerHandle,
        USHORT a2,
        __int64 a3,
        __int64 a4,
        char *pSid,
        const wchar_t *a6)
{
  const wchar_t *v6; // rbx
  __int64 v10; // rax
  __int64 v12; // rbp
  const char *v13; // rdi
  DWORD LengthSid; // esi

  v6 = a6;
  if ( a6 )
  {
    v10 = -1;
    while ( a6[++v10] != 0 )
      ;
    v12 = 2 * v10 + 2;
  }
  else
  {
    v12 = 10;
  }
  v13 = pSid;
  if ( !a6 )
    v6 = L"NULL";
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
  }
  else
  {
    LengthSid = 5;
    if ( !pSid )
    {
LABEL_14:
      v13 = "NULL";
      return TraceMessage(
               LoggerHandle,
               0x2Bu,
               &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
               a2,
               a4,
               16,
               v13,
               LengthSid,
               v6,
               v12,
               0);
    }
  }
  if ( !IsValidSid(pSid) )
    goto LABEL_14;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
           a2,
           a4,
           16,
           v13,
           LengthSid,
           v6,
           v12,
           0);
}

```

## disassembly

```asm
0x180003650  push    rbx
0x180003652  push    rbp
0x180003653  push    rsi
0x180003654  push    rdi
0x180003655  push    r12
0x180003657  push    r14
0x180003659  push    r15
0x18000365b  sub     rsp, 60h
0x18000365f  mov     rbx, [rsp+98h+arg_28]
0x180003667  mov     r14, r9
0x18000366a  movzx   r15d, dx
0x18000366e  mov     r12, rcx
0x180003671  test    rbx, rbx
0x180003674  jz      loc_180003739
0x18000367a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003681  cmp     word ptr [rbx+rax*2+2], 0
0x180003687  lea     rax, [rax+1]
0x18000368b  jnz     short loc_180003681
0x18000368d  lea     rbp, ds:2[rax*2]
0x180003695  mov     rdi, [rsp+98h+pSid]
0x18000369d  lea     rax, aNull_0; "NULL"
0x1800036a4  test    rbx, rbx
0x1800036a7  cmovz   rbx, rax
0x1800036ab  test    rdi, rdi
0x1800036ae  jnz     short loc_18000371F
0x1800036b0  mov     esi, 5
0x1800036b5  test    rdi, rdi
0x1800036b8  jz      loc_180003743
0x1800036be  mov     rcx, rdi; pSid
0x1800036c1  call    cs:__imp_IsValidSid
0x1800036c7  test    eax, eax
0x1800036c9  jz      short loc_180003743
0x1800036cb  mov     [rsp+98h+var_48], 0
0x1800036d4  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids; MessageGuid
0x1800036db  mov     [rsp+98h+var_50], rbp
0x1800036e0  mov     r9d, r15d; MessageNumber
0x1800036e3  mov     [rsp+98h+var_58], rbx
0x1800036e8  mov     edx, 2Bh ; '+'; MessageFlags
0x1800036ed  mov     eax, esi
0x1800036ef  mov     rcx, r12; LoggerHandle
0x1800036f2  mov     [rsp+98h+var_60], rax
0x1800036f7  mov     [rsp+98h+var_68], rdi
0x1800036fc  mov     [rsp+98h+var_70], 10h
0x180003705  mov     [rsp+98h+var_78], r14
0x18000370a  call    cs:__imp_TraceMessage
0x180003710  add     rsp, 60h
0x180003714  pop     r15
0x180003716  pop     r14
0x180003718  pop     r12
0x18000371a  pop     rdi
0x18000371b  pop     rsi
0x18000371c  pop     rbp
0x18000371d  pop     rbx
0x18000371e  retn
0x18000371f  mov     rcx, rdi; pSid
0x180003722  call    cs:__imp_IsValidSid
0x180003728  test    eax, eax
0x18000372a  jz      short loc_1800036B0
0x18000372c  mov     rcx, rdi; pSid
0x18000372f  call    cs:__imp_GetLengthSid
0x180003735  mov     esi, eax
0x180003737  jmp     short loc_1800036BE
0x180003739  mov     ebp, 0Ah
0x18000373e  jmp     loc_180003695
0x180003743  lea     rdi, aNull; "NULL"
0x18000374a  jmp     loc_1800036CB
```
