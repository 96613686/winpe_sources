# WPP_SF_d_sid_

- ea: `0x18001f588`
- end: `0x18001f636`
- name: `WPP_SF_d_sid_`
- size: `174`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016590`

## callees

- `0x18001f588`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001f620`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001f620`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f5af`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f5d3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f5af`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f5d3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f5bc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f5bc`

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
               &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
               0x3Bu,
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
           &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
           0x3Bu,
           &v9,
           4,
           v5,
           LengthSid,
           0);
}

```

## disassembly

```asm
0x18001f588  mov     [rsp+arg_0], rbx
0x18001f58d  mov     [rsp+arg_8], rsi
0x18001f592  mov     [rsp+arg_18], r9d
0x18001f597  push    rdi
0x18001f598  sub     rsp, 50h
0x18001f59c  mov     rbx, [rsp+58h+pSid]
0x18001f5a4  mov     rsi, rcx
0x18001f5a7  test    rbx, rbx
0x18001f5aa  jz      short loc_18001F5C6
0x18001f5ac  mov     rcx, rbx; pSid
0x18001f5af  call    cs:__imp_IsValidSid
0x18001f5b5  test    eax, eax
0x18001f5b7  jz      short loc_18001F5C6
0x18001f5b9  mov     rcx, rbx; pSid
0x18001f5bc  call    cs:__imp_GetLengthSid
0x18001f5c2  mov     edi, eax
0x18001f5c4  jmp     short loc_18001F5D0
0x18001f5c6  mov     edi, 5
0x18001f5cb  test    rbx, rbx
0x18001f5ce  jz      short loc_18001F5DD
0x18001f5d0  mov     rcx, rbx; pSid
0x18001f5d3  call    cs:__imp_IsValidSid
0x18001f5d9  test    eax, eax
0x18001f5db  jnz     short loc_18001F5E4
0x18001f5dd  lea     rbx, aNull; "NULL"
0x18001f5e4  mov     [rsp+58h+var_18], 0
0x18001f5ed  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids; MessageGuid
0x18001f5f4  mov     r9d, 3Bh ; ';'; MessageNumber
0x18001f5fa  mov     eax, edi
0x18001f5fc  mov     [rsp+58h+var_20], rax
0x18001f601  mov     rcx, rsi; LoggerHandle
0x18001f604  mov     [rsp+58h+var_28], rbx
0x18001f609  lea     rax, [rsp+58h+arg_18]
0x18001f60e  mov     [rsp+58h+var_30], 4
0x18001f617  lea     edx, [r9-10h]; MessageFlags
0x18001f61b  mov     [rsp+58h+var_38], rax
0x18001f620  call    cs:__imp_TraceMessage
0x18001f626  mov     rbx, [rsp+58h+arg_0]
0x18001f62b  mov     rsi, [rsp+58h+arg_8]
0x18001f630  add     rsp, 50h
0x18001f634  pop     rdi
0x18001f635  retn
```
