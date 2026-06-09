# WPP_SF_S_sid_

- ea: `0x1800171bc`
- end: `0x18001728e`
- name: `WPP_SF_S_sid_`
- size: `210`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dc40`
- `0x18001ad04`
- `0x18001b80c`

## callees

- `0x1800171bc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180017279`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180017279`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800171eb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001720f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800171eb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001720f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800171f8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800171f8`

## pseudocode

```c
ULONG __fastcall WPP_SF_S_sid_(TRACEHANDLE LoggerHandle, USHORT a2, const GUID *a3, const wchar_t *a4, char *pSid)
{
  const char *v5; // rbx
  DWORD LengthSid; // esi
  __int64 v11; // rax
  __int64 v12; // rcx

  v5 = pSid;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
    goto LABEL_5;
  }
  LengthSid = 5;
  if ( pSid )
  {
LABEL_5:
    if ( IsValidSid(pSid) )
      goto LABEL_7;
  }
  v5 = "NULL";
LABEL_7:
  if ( a4 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a4[v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v12 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, a4, v12, v5, LengthSid, 0);
}

```

## disassembly

```asm
0x1800171bc  push    rbx
0x1800171be  push    rbp
0x1800171bf  push    rsi
0x1800171c0  push    rdi
0x1800171c1  push    r12
0x1800171c3  push    r14
0x1800171c5  push    r15
0x1800171c7  sub     rsp, 50h
0x1800171cb  mov     rbx, [rsp+88h+pSid]
0x1800171d3  xor     r12d, r12d
0x1800171d6  movzx   r14d, dx
0x1800171da  mov     rdi, r9
0x1800171dd  mov     rbp, r8
0x1800171e0  mov     r15, rcx
0x1800171e3  test    rbx, rbx
0x1800171e6  jz      short loc_180017202
0x1800171e8  mov     rcx, rbx; pSid
0x1800171eb  call    cs:__imp_IsValidSid
0x1800171f1  test    eax, eax
0x1800171f3  jz      short loc_180017202
0x1800171f5  mov     rcx, rbx; pSid
0x1800171f8  call    cs:__imp_GetLengthSid
0x1800171fe  mov     esi, eax
0x180017200  jmp     short loc_18001720C
0x180017202  mov     esi, 5
0x180017207  test    rbx, rbx
0x18001720a  jz      short loc_180017219
0x18001720c  mov     rcx, rbx; pSid
0x18001720f  call    cs:__imp_IsValidSid
0x180017215  test    eax, eax
0x180017217  jnz     short loc_180017220
0x180017219  lea     rbx, aNull; "NULL"
0x180017220  test    rdi, rdi
0x180017223  jz      short loc_18001723D
0x180017225  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017229  inc     rax
0x18001722c  cmp     [rdi+rax*2], r12w
0x180017231  jnz     short loc_180017229
0x180017233  lea     rcx, ds:2[rax*2]
0x18001723b  jmp     short loc_180017242
0x18001723d  mov     ecx, 0Ah
0x180017242  mov     [rsp+88h+var_48], r12
0x180017247  lea     rdx, aNull_0; "NULL"
0x18001724e  mov     eax, esi
0x180017250  test    rdi, rdi
0x180017253  mov     [rsp+88h+var_50], rax
0x180017258  mov     r9d, r14d; MessageNumber
0x18001725b  cmovz   rdi, rdx
0x18001725f  mov     [rsp+88h+var_58], rbx
0x180017264  mov     [rsp+88h+var_60], rcx
0x180017269  mov     r8, rbp; MessageGuid
0x18001726c  mov     rcx, r15; LoggerHandle
0x18001726f  mov     [rsp+88h+var_68], rdi
0x180017274  mov     edx, 2Bh ; '+'; MessageFlags
0x180017279  call    cs:__imp_TraceMessage
0x18001727f  add     rsp, 50h
0x180017283  pop     r15
0x180017285  pop     r14
0x180017287  pop     r12
0x180017289  pop     rdi
0x18001728a  pop     rsi
0x18001728b  pop     rbp
0x18001728c  pop     rbx
0x18001728d  retn
```
