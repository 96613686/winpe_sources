# WPP_SF__guid__sid_

- ea: `0x180001cbc`
- end: `0x180001d5d`
- name: `WPP_SF__guid__sid_`
- size: `161`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800026b4`
- `0x18000c970`

## callees

- `0x180001cbc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001ced`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001ced`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180001ce0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180001d04`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180001ce0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180001d04`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180001d43`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180001d43`

## pseudocode

```c
ULONG __fastcall WPP_SF__guid__sid_(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, __int64 a4, char *pSid)
{
  const char *v5; // rbx
  DWORD LengthSid; // edi

  v5 = pSid;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
  }
  else
  {
    LengthSid = 5;
    if ( !pSid )
    {
LABEL_7:
      v5 = "NULL";
      return TraceMessage(
               LoggerHandle,
               0x2Bu,
               &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
               a2,
               a4,
               16,
               v5,
               LengthSid,
               0);
    }
  }
  if ( !IsValidSid(pSid) )
    goto LABEL_7;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
           a2,
           a4,
           16,
           v5,
           LengthSid,
           0);
}

```

## disassembly

```asm
0x180001cbc  push    rbx
0x180001cbe  push    rbp
0x180001cbf  push    rsi
0x180001cc0  push    rdi
0x180001cc1  push    r14
0x180001cc3  sub     rsp, 50h
0x180001cc7  mov     rbx, [rsp+78h+pSid]
0x180001ccf  mov     rsi, r9
0x180001cd2  movzx   ebp, dx
0x180001cd5  mov     r14, rcx
0x180001cd8  test    rbx, rbx
0x180001cdb  jz      short loc_180001CF7
0x180001cdd  mov     rcx, rbx; pSid
0x180001ce0  call    cs:__imp_IsValidSid
0x180001ce6  test    eax, eax
0x180001ce8  jz      short loc_180001CF7
0x180001cea  mov     rcx, rbx; pSid
0x180001ced  call    cs:__imp_GetLengthSid
0x180001cf3  mov     edi, eax
0x180001cf5  jmp     short loc_180001D01
0x180001cf7  mov     edi, 5
0x180001cfc  test    rbx, rbx
0x180001cff  jz      short loc_180001D54
0x180001d01  mov     rcx, rbx; pSid
0x180001d04  call    cs:__imp_IsValidSid
0x180001d0a  test    eax, eax
0x180001d0c  jz      short loc_180001D54
0x180001d0e  mov     [rsp+78h+var_38], 0
0x180001d17  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids; MessageGuid
0x180001d1e  mov     eax, edi
0x180001d20  mov     r9d, ebp; MessageNumber
0x180001d23  mov     [rsp+78h+var_40], rax
0x180001d28  mov     edx, 2Bh ; '+'; MessageFlags
0x180001d2d  mov     [rsp+78h+var_48], rbx
0x180001d32  mov     rcx, r14; LoggerHandle
0x180001d35  mov     [rsp+78h+var_50], 10h
0x180001d3e  mov     [rsp+78h+var_58], rsi
0x180001d43  call    cs:__imp_TraceMessage
0x180001d49  add     rsp, 50h
0x180001d4d  pop     r14
0x180001d4f  pop     rdi
0x180001d50  pop     rsi
0x180001d51  pop     rbp
0x180001d52  pop     rbx
0x180001d53  retn
0x180001d54  lea     rbx, aNull; "NULL"
0x180001d5b  jmp     short loc_180001D0E
```
