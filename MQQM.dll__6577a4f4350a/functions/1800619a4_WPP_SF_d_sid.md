# WPP_SF_d_sid_

- ea: `0x1800619a4`
- end: `0x180061a52`
- name: `WPP_SF_d_sid_`
- size: `174`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180061024`

## callees

- `0x1800619a4`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180061a3c`
- `ADVAPI32!TraceMessage` at `0x180061a3c`
- `ADVAPI32!GetLengthSid` at `0x1800619d8`
- `ADVAPI32!GetLengthSid` at `0x1800619d8`
- `ADVAPI32!IsValidSid` at `0x1800619cb`
- `ADVAPI32!IsValidSid` at `0x1800619ef`
- `ADVAPI32!IsValidSid` at `0x1800619cb`
- `ADVAPI32!IsValidSid` at `0x1800619ef`

## pseudocode

```c
ULONG __fastcall WPP_SF_d_sid_(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, int a4, char *pSid)
{
  char *v5; // rbx
  DWORD LengthSid; // edi
  int v9; // [rsp+78h] [rbp+20h] BYREF

  v9 = a4;
  v5 = pSid;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(v5);
  }
  else
  {
    LengthSid = 5;
    if ( !v5 )
    {
LABEL_6:
      v5 = "NULL";
      return TraceMessage(
               LoggerHandle,
               0x2Bu,
               &WPP_54588dc237b33a312ac4912f3ef61e5f_Traceguids,
               0xBu,
               &v9,
               4,
               v5,
               LengthSid,
               0);
    }
  }
  if ( !IsValidSid(v5) )
    goto LABEL_6;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_54588dc237b33a312ac4912f3ef61e5f_Traceguids,
           0xBu,
           &v9,
           4,
           v5,
           LengthSid,
           0);
}

```

## disassembly

```asm
0x1800619a4  mov     [rsp+arg_0], rbx
0x1800619a9  mov     [rsp+arg_8], rsi
0x1800619ae  mov     [rsp+arg_18], r9d
0x1800619b3  push    rdi
0x1800619b4  sub     rsp, 50h
0x1800619b8  mov     rbx, [rsp+58h+pSid]
0x1800619c0  mov     rsi, rcx
0x1800619c3  test    rbx, rbx
0x1800619c6  jz      short loc_1800619E2
0x1800619c8  mov     rcx, rbx; pSid
0x1800619cb  call    cs:__imp_IsValidSid
0x1800619d1  test    eax, eax
0x1800619d3  jz      short loc_1800619E2
0x1800619d5  mov     rcx, rbx; pSid
0x1800619d8  call    cs:__imp_GetLengthSid
0x1800619de  mov     edi, eax
0x1800619e0  jmp     short loc_1800619EC
0x1800619e2  mov     edi, 5
0x1800619e7  test    rbx, rbx
0x1800619ea  jz      short loc_1800619F9
0x1800619ec  mov     rcx, rbx; pSid
0x1800619ef  call    cs:__imp_IsValidSid
0x1800619f5  test    eax, eax
0x1800619f7  jnz     short loc_180061A00
0x1800619f9  lea     rbx, aNull; "NULL"
0x180061a00  mov     [rsp+58h+var_18], 0
0x180061a09  lea     r8, WPP_54588dc237b33a312ac4912f3ef61e5f_Traceguids; MessageGuid
0x180061a10  mov     r9d, 0Bh; MessageNumber
0x180061a16  mov     eax, edi
0x180061a18  mov     [rsp+58h+var_20], rax
0x180061a1d  mov     rcx, rsi; LoggerHandle
0x180061a20  mov     [rsp+58h+var_28], rbx
0x180061a25  lea     rax, [rsp+58h+arg_18]
0x180061a2a  mov     [rsp+58h+var_30], 4
0x180061a33  lea     edx, [r9+20h]; MessageFlags
0x180061a37  mov     [rsp+58h+var_38], rax
0x180061a3c  call    cs:__imp_TraceMessage
0x180061a42  mov     rbx, [rsp+58h+arg_0]
0x180061a47  mov     rsi, [rsp+58h+arg_8]
0x180061a4c  add     rsp, 50h
0x180061a50  pop     rdi
0x180061a51  retn
```
