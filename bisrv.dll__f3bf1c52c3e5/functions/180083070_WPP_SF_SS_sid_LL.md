# WPP_SF_SS_sid_LL

- ea: `0x180083070`
- end: `0x1800831a1`
- name: `WPP_SF_SS_sid_LL`
- size: `305`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64, PSID pSid, char, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800828f0`

## callees

- `0x180083070`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800830a4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800830a4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180083097`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800830bb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180083097`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800830bb`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18008318d`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18008318d`

## pseudocode

```c
ULONG WPP_SF_SS_sid_LL(
        TRACEHANDLE LoggerHandle,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        const wchar_t *a5,
        char *pSid,
        ...)
{
  const char *v6; // rbx
  DWORD LengthSid; // esi
  const wchar_t *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v16; // [rsp+E0h] [rbp+38h] BYREF
  va_list va; // [rsp+E0h] [rbp+38h]
  va_list va1; // [rsp+E8h] [rbp+40h] BYREF

  va_start(va1, pSid);
  va_start(va, pSid);
  v16 = va_arg(va1, _QWORD);
  v6 = pSid;
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
  v6 = "NULL";
LABEL_7:
  v10 = a5;
  v11 = -1;
  v12 = 10;
  if ( a5 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a5[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v14 = 10;
  }
  if ( !a5 )
    v10 = L"NULL";
  if ( a4 )
  {
    do
      ++v11;
    while ( a4[v11] );
    v12 = 2 * v11 + 2;
  }
  if ( !a4 )
    a4 = L"NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_e6b615a7d18a3fcf430735eb063d161f_Traceguids,
           0x15u,
           a4,
           v12,
           v10,
           v14,
           v6,
           LengthSid,
           va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x180083070  push    rbx
0x180083072  push    rbp
0x180083073  push    rsi
0x180083074  push    rdi
0x180083075  push    r14
0x180083077  sub     rsp, 80h
0x18008307e  mov     rbx, [rsp+0A8h+pSid]
0x180083086  xor     r14d, r14d
0x180083089  mov     rdi, r9
0x18008308c  mov     rbp, rcx
0x18008308f  test    rbx, rbx
0x180083092  jz      short loc_1800830AE
0x180083094  mov     rcx, rbx; pSid
0x180083097  call    cs:__imp_IsValidSid
0x18008309d  test    eax, eax
0x18008309f  jz      short loc_1800830AE
0x1800830a1  mov     rcx, rbx; pSid
0x1800830a4  call    cs:__imp_GetLengthSid
0x1800830aa  mov     esi, eax
0x1800830ac  jmp     short loc_1800830B8
0x1800830ae  mov     esi, 5
0x1800830b3  test    rbx, rbx
0x1800830b6  jz      short loc_1800830C5
0x1800830b8  mov     rcx, rbx; pSid
0x1800830bb  call    cs:__imp_IsValidSid
0x1800830c1  test    eax, eax
0x1800830c3  jnz     short loc_1800830CC
0x1800830c5  lea     rbx, aNull; "NULL"
0x1800830cc  mov     rcx, [rsp+0A8h+arg_20]
0x1800830d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800830d8  mov     r8d, 0Ah
0x1800830de  test    rcx, rcx
0x1800830e1  jz      short loc_1800830FA
0x1800830e3  mov     rdx, rax
0x1800830e6  inc     rdx
0x1800830e9  cmp     [rcx+rdx*2], r14w
0x1800830ee  jnz     short loc_1800830E6
0x1800830f0  lea     rdx, ds:2[rdx*2]
0x1800830f8  jmp     short loc_1800830FD
0x1800830fa  mov     rdx, r8
0x1800830fd  test    rcx, rcx
0x180083100  lea     r9, aNull_0; "NULL"
0x180083107  cmovz   rcx, r9
0x18008310b  test    rdi, rdi
0x18008310e  jz      short loc_180083122
0x180083110  inc     rax
0x180083113  cmp     [rdi+rax*2], r14w
0x180083118  jnz     short loc_180083110
0x18008311a  lea     r8, ds:2[rax*2]
0x180083122  mov     [rsp+0A8h+var_38], r14
0x180083127  mov     r11d, 15h
0x18008312d  test    rdi, rdi
0x180083130  mov     eax, esi
0x180083132  cmovz   rdi, r9
0x180083136  lea     r9, [rsp+0A8h+arg_38]
0x18008313e  lea     r10d, [r11-11h]
0x180083142  mov     [rsp+0A8h+var_40], r10
0x180083147  mov     [rsp+0A8h+var_48], r9
0x18008314c  lea     r9, [rsp+0A8h+arg_30]
0x180083154  mov     [rsp+0A8h+var_50], r10
0x180083159  mov     [rsp+0A8h+var_58], r9
0x18008315e  mov     r9d, r11d; MessageNumber
0x180083161  mov     [rsp+0A8h+var_60], rax
0x180083166  mov     [rsp+0A8h+var_68], rbx
0x18008316b  mov     [rsp+0A8h+var_70], rdx
0x180083170  lea     edx, [r11+16h]; MessageFlags
0x180083174  mov     [rsp+0A8h+var_78], rcx
0x180083179  mov     rcx, rbp; LoggerHandle
0x18008317c  mov     [rsp+0A8h+var_80], r8
0x180083181  lea     r8, WPP_e6b615a7d18a3fcf430735eb063d161f_Traceguids; MessageGuid
0x180083188  mov     [rsp+0A8h+var_88], rdi
0x18008318d  call    cs:__imp_TraceMessage
0x180083193  add     rsp, 80h
0x18008319a  pop     r14
0x18008319c  pop     rdi
0x18008319d  pop     rsi
0x18008319e  pop     rbp
0x18008319f  pop     rbx
0x1800831a0  retn
```
