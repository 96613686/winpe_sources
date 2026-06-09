# WPP_SF__sid_

- ea: `0x180008dd8`
- end: `0x180008e62`
- name: `WPP_SF__sid_`
- size: `138`
- prototype: `__int64 __fastcall(TRACEHANDLE LoggerHandle)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d94`
- `0x1800026b4`
- `0x1800088c8`
- `0x18000c970`

## callees

- `0x180008dd8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008e58`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008e58`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180008e01`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180008e4b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180008e01`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180008e4b`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180008e2e`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180008e2e`

## pseudocode

```c
ULONG __fastcall WPP_SF__sid_(TRACEHANDLE LoggerHandle, USHORT a2, const GUID *a3, char *a4)
{
  char *v5; // rbx
  DWORD LengthSid; // edi

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
LABEL_5:
      v5 = "NULL";
      return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, v5, LengthSid, 0);
    }
  }
  if ( !IsValidSid(v5) )
    goto LABEL_5;
  return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, v5, LengthSid, 0);
}

```

## disassembly

```asm
0x180008dd8  push    rbx
0x180008dda  push    rbp
0x180008ddb  push    rsi
0x180008ddc  push    rdi
0x180008ddd  push    r14
0x180008ddf  sub     rsp, 40h
0x180008de3  movzx   ebp, dx
0x180008de6  mov     rbx, r9
0x180008de9  mov     rsi, r8
0x180008dec  mov     r14, rcx
0x180008def  test    r9, r9
0x180008df2  jnz     short loc_180008E48
0x180008df4  mov     edi, 5
0x180008df9  test    rbx, rbx
0x180008dfc  jz      short loc_180008E3F
0x180008dfe  mov     rcx, rbx; pSid
0x180008e01  call    cs:__imp_IsValidSid
0x180008e07  test    eax, eax
0x180008e09  jz      short loc_180008E3F
0x180008e0b  mov     eax, edi
0x180008e0d  mov     r9d, ebp; MessageNumber
0x180008e10  mov     [rsp+68h+var_38], 0
0x180008e19  mov     r8, rsi; MessageGuid
0x180008e1c  mov     [rsp+68h+var_40], rax
0x180008e21  mov     edx, 2Bh ; '+'; MessageFlags
0x180008e26  mov     rcx, r14; LoggerHandle
0x180008e29  mov     [rsp+68h+var_48], rbx
0x180008e2e  call    cs:__imp_TraceMessage
0x180008e34  add     rsp, 40h
0x180008e38  pop     r14
0x180008e3a  pop     rdi
0x180008e3b  pop     rsi
0x180008e3c  pop     rbp
0x180008e3d  pop     rbx
0x180008e3e  retn
0x180008e3f  lea     rbx, aNull; "NULL"
0x180008e46  jmp     short loc_180008E0B
0x180008e48  mov     rcx, rbx; pSid
0x180008e4b  call    cs:__imp_IsValidSid
0x180008e51  test    eax, eax
0x180008e53  jz      short loc_180008DF4
0x180008e55  mov     rcx, rbx; pSid
0x180008e58  call    cs:__imp_GetLengthSid
0x180008e5e  mov     edi, eax
0x180008e60  jmp     short loc_180008DFE
```
