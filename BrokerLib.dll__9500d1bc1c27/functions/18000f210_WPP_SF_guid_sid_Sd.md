# WPP_SF__guid__sid_Sd

- ea: `0x18000f210`
- end: `0x18000f328`
- name: `WPP_SF__guid__sid_Sd`
- size: `280`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid, __int64, char)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003a60`
- `0x18000efc4`
- `0x180014a7c`

## callees

- `0x18000f210`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f2ee`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f2ee`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000f2db`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000f2f9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000f2db`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000f2f9`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000f2c1`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000f2c1`

## pseudocode

```c
ULONG WPP_SF__guid__sid_Sd(
        TRACEHANDLE LoggerHandle,
        USHORT a2,
        const GUID *a3,
        __int64 a4,
        char *pSid,
        const wchar_t *a6,
        ...)
{
  const wchar_t *v6; // rdi
  __int64 v11; // rbp
  const char *v12; // rbx
  DWORD LengthSid; // esi
  __int64 v15; // rax
  va_list va; // [rsp+F0h] [rbp+38h] BYREF

  va_start(va, a6);
  v6 = a6;
  if ( a6 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a6[v15] );
    v11 = 2 * v15 + 2;
  }
  else
  {
    v11 = 10;
  }
  v12 = pSid;
  if ( !a6 )
    v6 = L"NULL";
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
LABEL_11:
    if ( IsValidSid(pSid) )
      return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, a4, 16, v12, LengthSid, v6, v11, va, 4, 0);
    goto LABEL_7;
  }
  LengthSid = 5;
  if ( pSid )
    goto LABEL_11;
LABEL_7:
  v12 = "NULL";
  return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, a4, 16, v12, LengthSid, v6, v11, va, 4, 0);
}

```

## disassembly

```asm
0x18000f210  push    rbx
0x18000f212  push    rbp
0x18000f213  push    rsi
0x18000f214  push    rdi
0x18000f215  push    r12
0x18000f217  push    r13
0x18000f219  push    r14
0x18000f21b  push    r15
0x18000f21d  sub     rsp, 78h
0x18000f221  mov     rdi, [rsp+0B8h+arg_28]
0x18000f229  mov     r13, rcx
0x18000f22c  xor     ecx, ecx
0x18000f22e  movzx   r12d, dx
0x18000f232  mov     r14, r9
0x18000f235  mov     r15, r8
0x18000f238  test    rdi, rdi
0x18000f23b  jnz     loc_18000F30E
0x18000f241  lea     ebp, [rdi+0Ah]
0x18000f244  mov     rbx, [rsp+0B8h+pSid]
0x18000f24c  lea     rax, aNull_0; "NULL"
0x18000f253  test    rdi, rdi
0x18000f256  cmovz   rdi, rax
0x18000f25a  test    rbx, rbx
0x18000f25d  jnz     short loc_18000F2D8
0x18000f25f  mov     esi, 5
0x18000f264  test    rbx, rbx
0x18000f267  jnz     loc_18000F2F6
0x18000f26d  lea     rbx, aNull; "NULL"
0x18000f274  mov     [rsp+0B8h+var_58], rcx
0x18000f279  mov     r9d, r12d; MessageNumber
0x18000f27c  mov     [rsp+0B8h+var_60], 4
0x18000f285  lea     rcx, [rsp+0B8h+arg_30]
0x18000f28d  mov     [rsp+0B8h+var_68], rcx
0x18000f292  mov     r8, r15; MessageGuid
0x18000f295  mov     [rsp+0B8h+var_70], rbp
0x18000f29a  mov     edx, 2Bh ; '+'; MessageFlags
0x18000f29f  mov     [rsp+0B8h+var_78], rdi
0x18000f2a4  mov     rcx, r13; LoggerHandle
0x18000f2a7  mov     eax, esi
0x18000f2a9  mov     [rsp+0B8h+var_80], rax
0x18000f2ae  mov     [rsp+0B8h+var_88], rbx
0x18000f2b3  mov     [rsp+0B8h+var_90], 10h
0x18000f2bc  mov     [rsp+0B8h+var_98], r14
0x18000f2c1  call    cs:__imp_TraceMessage
0x18000f2c7  add     rsp, 78h
0x18000f2cb  pop     r15
0x18000f2cd  pop     r14
0x18000f2cf  pop     r13
0x18000f2d1  pop     r12
0x18000f2d3  pop     rdi
0x18000f2d4  pop     rsi
0x18000f2d5  pop     rbp
0x18000f2d6  pop     rbx
0x18000f2d7  retn
0x18000f2d8  mov     rcx, rbx; pSid
0x18000f2db  call    cs:__imp_IsValidSid
0x18000f2e1  xor     ecx, ecx
0x18000f2e3  test    eax, eax
0x18000f2e5  jz      loc_18000F25F
0x18000f2eb  mov     rcx, rbx; pSid
0x18000f2ee  call    cs:__imp_GetLengthSid
0x18000f2f4  mov     esi, eax
0x18000f2f6  mov     rcx, rbx; pSid
0x18000f2f9  call    cs:__imp_IsValidSid
0x18000f2ff  xor     ecx, ecx
0x18000f301  test    eax, eax
0x18000f303  jnz     loc_18000F274
0x18000f309  jmp     loc_18000F26D
0x18000f30e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f312  inc     rax
0x18000f315  cmp     [rdi+rax*2], cx
0x18000f319  jnz     short loc_18000F312
0x18000f31b  lea     rbp, ds:2[rax*2]
0x18000f323  jmp     loc_18000F244
```
