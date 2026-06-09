# WPP_SF__sid_d

- ea: `0x18000fe88`
- end: `0x18000ff28`
- name: `WPP_SF__sid_d`
- size: `160`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, char)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d94`
- `0x180006540`
- `0x1800088c8`
- `0x18000c970`
- `0x18000ccbc`

## callees

- `0x18000fe88`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000feb4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000feb4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000fea7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000fecb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000fea7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000fecb`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ff0e`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ff0e`

## pseudocode

```c
ULONG WPP_SF__sid_d(TRACEHANDLE LoggerHandle, USHORT a2, const GUID *a3, char *a4, ...)
{
  char *v5; // rbx
  DWORD LengthSid; // edi
  va_list va; // [rsp+A0h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v5);
  }
  else
  {
    LengthSid = 5;
    if ( !v5 )
    {
LABEL_7:
      v5 = "NULL";
      return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, v5, LengthSid, va, 4, 0);
    }
  }
  if ( !IsValidSid(v5) )
    goto LABEL_7;
  return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, v5, LengthSid, va, 4, 0);
}

```

## disassembly

```asm
0x18000fe88  push    rbx
0x18000fe8a  push    rbp
0x18000fe8b  push    rsi
0x18000fe8c  push    rdi
0x18000fe8d  push    r14
0x18000fe8f  sub     rsp, 50h
0x18000fe93  movzx   ebp, dx
0x18000fe96  mov     rbx, r9
0x18000fe99  mov     rsi, r8
0x18000fe9c  mov     r14, rcx
0x18000fe9f  test    r9, r9
0x18000fea2  jz      short loc_18000FEBE
0x18000fea4  mov     rcx, rbx; pSid
0x18000fea7  call    cs:__imp_IsValidSid
0x18000fead  test    eax, eax
0x18000feaf  jz      short loc_18000FEBE
0x18000feb1  mov     rcx, rbx; pSid
0x18000feb4  call    cs:__imp_GetLengthSid
0x18000feba  mov     edi, eax
0x18000febc  jmp     short loc_18000FEC8
0x18000febe  mov     edi, 5
0x18000fec3  test    rbx, rbx
0x18000fec6  jz      short loc_18000FF1F
0x18000fec8  mov     rcx, rbx; pSid
0x18000fecb  call    cs:__imp_IsValidSid
0x18000fed1  test    eax, eax
0x18000fed3  jz      short loc_18000FF1F
0x18000fed5  mov     [rsp+78h+var_38], 0
0x18000fede  lea     rcx, [rsp+78h+arg_20]
0x18000fee6  mov     [rsp+78h+var_40], 4
0x18000feef  mov     r9d, ebp; MessageNumber
0x18000fef2  mov     [rsp+78h+var_48], rcx
0x18000fef7  mov     r8, rsi; MessageGuid
0x18000fefa  mov     eax, edi
0x18000fefc  mov     rcx, r14; LoggerHandle
0x18000feff  mov     [rsp+78h+var_50], rax
0x18000ff04  mov     edx, 2Bh ; '+'; MessageFlags
0x18000ff09  mov     [rsp+78h+var_58], rbx
0x18000ff0e  call    cs:__imp_TraceMessage
0x18000ff14  add     rsp, 50h
0x18000ff18  pop     r14
0x18000ff1a  pop     rdi
0x18000ff1b  pop     rsi
0x18000ff1c  pop     rbp
0x18000ff1d  pop     rbx
0x18000ff1e  retn
0x18000ff1f  lea     rbx, aNull; "NULL"
0x18000ff26  jmp     short loc_18000FED5
```
