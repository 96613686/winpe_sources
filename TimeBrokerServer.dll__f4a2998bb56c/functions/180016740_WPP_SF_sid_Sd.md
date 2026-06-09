# WPP_SF__sid_Sd

- ea: `0x180016740`
- end: `0x180016823`
- name: `WPP_SF__sid_Sd`
- size: `227`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ef50`

## callees

- `0x180016740`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180016810`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180016810`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800167a3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800167a3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180016796`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800167ba`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180016796`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800167ba`

## pseudocode

```c
ULONG WPP_SF__sid_Sd(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, char *a4, const wchar_t *a5, ...)
{
  const wchar_t *v5; // rdi
  char *v6; // rbx
  __int64 v8; // rax
  __int64 v9; // rbp
  DWORD LengthSid; // esi
  va_list va; // [rsp+C8h] [rbp+30h] BYREF

  va_start(va, a5);
  v5 = a5;
  v6 = a4;
  if ( a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a5[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v6);
  }
  else
  {
    LengthSid = 5;
    if ( !v6 )
    {
LABEL_13:
      v6 = "NULL";
      return TraceMessage(
               LoggerHandle,
               0x2Bu,
               &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
               0x64u,
               v6,
               LengthSid,
               v5,
               v9,
               va,
               4,
               0);
    }
  }
  if ( !IsValidSid(v6) )
    goto LABEL_13;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
           0x64u,
           v6,
           LengthSid,
           v5,
           v9,
           va,
           4,
           0);
}

```

## disassembly

```asm
0x180016740  push    rbx
0x180016742  push    rbp
0x180016743  push    rsi
0x180016744  push    rdi
0x180016745  push    r14
0x180016747  push    r15
0x180016749  sub     rsp, 68h
0x18001674d  mov     rdi, [rsp+98h+arg_20]
0x180016755  xor     r15d, r15d
0x180016758  mov     rbx, r9
0x18001675b  mov     r14, rcx
0x18001675e  test    rdi, rdi
0x180016761  jz      short loc_18001677B
0x180016763  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016767  inc     rax
0x18001676a  cmp     [rdi+rax*2], r15w
0x18001676f  jnz     short loc_180016767
0x180016771  lea     rbp, ds:2[rax*2]
0x180016779  jmp     short loc_180016780
0x18001677b  mov     ebp, 0Ah
0x180016780  test    rdi, rdi
0x180016783  lea     rax, aNull_0; "NULL"
0x18001678a  cmovz   rdi, rax
0x18001678e  test    rbx, rbx
0x180016791  jz      short loc_1800167AD
0x180016793  mov     rcx, rbx; pSid
0x180016796  call    cs:__imp_IsValidSid
0x18001679c  test    eax, eax
0x18001679e  jz      short loc_1800167AD
0x1800167a0  mov     rcx, rbx; pSid
0x1800167a3  call    cs:__imp_GetLengthSid
0x1800167a9  mov     esi, eax
0x1800167ab  jmp     short loc_1800167B7
0x1800167ad  mov     esi, 5
0x1800167b2  test    rbx, rbx
0x1800167b5  jz      short loc_1800167C4
0x1800167b7  mov     rcx, rbx; pSid
0x1800167ba  call    cs:__imp_IsValidSid
0x1800167c0  test    eax, eax
0x1800167c2  jnz     short loc_1800167CB
0x1800167c4  lea     rbx, aNull; "NULL"
0x1800167cb  mov     [rsp+98h+var_48], r15
0x1800167d0  lea     rcx, [rsp+98h+arg_28]
0x1800167d8  mov     [rsp+98h+var_50], 4
0x1800167e1  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids; MessageGuid
0x1800167e8  mov     [rsp+98h+var_58], rcx
0x1800167ed  mov     r9d, 64h ; 'd'; MessageNumber
0x1800167f3  mov     [rsp+98h+var_60], rbp
0x1800167f8  mov     rcx, r14; LoggerHandle
0x1800167fb  mov     eax, esi
0x1800167fd  mov     [rsp+98h+var_68], rdi
0x180016802  mov     [rsp+98h+var_70], rax
0x180016807  lea     edx, [r9-39h]; MessageFlags
0x18001680b  mov     [rsp+98h+var_78], rbx
0x180016810  call    cs:__imp_TraceMessage
0x180016816  add     rsp, 68h
0x18001681a  pop     r15
0x18001681c  pop     r14
0x18001681e  pop     rdi
0x18001681f  pop     rsi
0x180016820  pop     rbp
0x180016821  pop     rbx
0x180016822  retn
```
