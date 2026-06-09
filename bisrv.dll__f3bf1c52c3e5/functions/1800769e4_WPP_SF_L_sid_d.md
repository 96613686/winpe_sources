# WPP_SF_L_sid_d

- ea: `0x1800769e4`
- end: `0x180076aa9`
- name: `WPP_SF_L_sid_d`
- size: `197`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180076918`

## callees

- `0x1800769e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180076a1b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180076a1b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180076a0e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180076a32`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180076a0e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180076a32`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180076a91`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180076a91`

## pseudocode

```c
ULONG WPP_SF_L_sid_d(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, __int64 a4, char *pSid, ...)
{
  const char *v5; // rbx
  DWORD LengthSid; // edi
  int v9[4]; // [rsp+60h] [rbp-18h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h] BYREF

  va_start(va, pSid);
  v5 = pSid;
  v9[0] = 9;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
  }
  else
  {
    LengthSid = 5;
    if ( !pSid )
    {
LABEL_6:
      v5 = "NULL";
      return TraceMessage(
               LoggerHandle,
               0x2Bu,
               &WPP_46212a5816a734aa0a47740a5c8b672c_Traceguids,
               0xBu,
               v9,
               4,
               v5,
               LengthSid,
               va,
               4,
               0);
    }
  }
  if ( !IsValidSid(pSid) )
    goto LABEL_6;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_46212a5816a734aa0a47740a5c8b672c_Traceguids,
           0xBu,
           v9,
           4,
           v5,
           LengthSid,
           va,
           4,
           0);
}

```

## disassembly

```asm
0x1800769e4  mov     [rsp+arg_0], rbx
0x1800769e9  mov     [rsp+arg_8], rsi
0x1800769ee  push    rdi
0x1800769ef  sub     rsp, 70h
0x1800769f3  mov     rbx, [rsp+78h+pSid]
0x1800769fb  mov     rsi, rcx
0x1800769fe  mov     [rsp+78h+var_18], 9
0x180076a06  test    rbx, rbx
0x180076a09  jz      short loc_180076A25
0x180076a0b  mov     rcx, rbx; pSid
0x180076a0e  call    cs:__imp_IsValidSid
0x180076a14  test    eax, eax
0x180076a16  jz      short loc_180076A25
0x180076a18  mov     rcx, rbx; pSid
0x180076a1b  call    cs:__imp_GetLengthSid
0x180076a21  mov     edi, eax
0x180076a23  jmp     short loc_180076A2F
0x180076a25  mov     edi, 5
0x180076a2a  test    rbx, rbx
0x180076a2d  jz      short loc_180076A3C
0x180076a2f  mov     rcx, rbx; pSid
0x180076a32  call    cs:__imp_IsValidSid
0x180076a38  test    eax, eax
0x180076a3a  jnz     short loc_180076A43
0x180076a3c  lea     rbx, aNull; "NULL"
0x180076a43  mov     [rsp+78h+var_28], 0
0x180076a4c  lea     rcx, [rsp+78h+arg_28]
0x180076a54  mov     r9d, 0Bh; MessageNumber
0x180076a5a  mov     eax, edi
0x180076a5c  lea     r8, WPP_46212a5816a734aa0a47740a5c8b672c_Traceguids; MessageGuid
0x180076a63  lea     edx, [r9-7]
0x180076a67  mov     [rsp+78h+var_30], rdx
0x180076a6c  mov     [rsp+78h+var_38], rcx
0x180076a71  mov     rcx, rsi; LoggerHandle
0x180076a74  mov     [rsp+78h+var_40], rax
0x180076a79  lea     rax, [rsp+78h+var_18]
0x180076a7e  mov     [rsp+78h+var_48], rbx
0x180076a83  mov     [rsp+78h+var_50], rdx
0x180076a88  lea     edx, [r9+20h]; MessageFlags
0x180076a8c  mov     [rsp+78h+var_58], rax
0x180076a91  call    cs:__imp_TraceMessage
0x180076a97  lea     r11, [rsp+78h+var_8]
0x180076a9c  mov     rbx, [r11+10h]
0x180076aa0  mov     rsi, [r11+18h]
0x180076aa4  mov     rsp, r11
0x180076aa7  pop     rdi
0x180076aa8  retn
```
