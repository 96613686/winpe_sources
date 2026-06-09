# WPP_SF__sid_

- ea: `0x18001f36c`
- end: `0x18001f3f4`
- name: `WPP_SF__sid_`
- size: `136`
- prototype: `__int64 __fastcall(TRACEHANDLE LoggerHandle)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019c1c`
- `0x180019dac`
- `0x18001e998`

## callees

- `0x18001f36c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001f3e3`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001f3e3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f38b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f3af`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f38b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f3af`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f398`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f398`

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
LABEL_6:
      v5 = "NULL";
      return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, v5, LengthSid, 0);
    }
  }
  if ( !IsValidSid(v5) )
    goto LABEL_6;
  return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, v5, LengthSid, 0);
}

```

## disassembly

```asm
0x18001f36c  push    rbx
0x18001f36e  push    rbp
0x18001f36f  push    rsi
0x18001f370  push    rdi
0x18001f371  push    r14
0x18001f373  sub     rsp, 40h
0x18001f377  movzx   ebp, dx
0x18001f37a  mov     rbx, r9
0x18001f37d  mov     rsi, r8
0x18001f380  mov     r14, rcx
0x18001f383  test    r9, r9
0x18001f386  jz      short loc_18001F3A2
0x18001f388  mov     rcx, rbx; pSid
0x18001f38b  call    cs:__imp_IsValidSid
0x18001f391  test    eax, eax
0x18001f393  jz      short loc_18001F3A2
0x18001f395  mov     rcx, rbx; pSid
0x18001f398  call    cs:__imp_GetLengthSid
0x18001f39e  mov     edi, eax
0x18001f3a0  jmp     short loc_18001F3AC
0x18001f3a2  mov     edi, 5
0x18001f3a7  test    rbx, rbx
0x18001f3aa  jz      short loc_18001F3B9
0x18001f3ac  mov     rcx, rbx; pSid
0x18001f3af  call    cs:__imp_IsValidSid
0x18001f3b5  test    eax, eax
0x18001f3b7  jnz     short loc_18001F3C0
0x18001f3b9  lea     rbx, aNull; "NULL"
0x18001f3c0  mov     eax, edi
0x18001f3c2  mov     r9d, ebp; MessageNumber
0x18001f3c5  mov     [rsp+68h+var_38], 0
0x18001f3ce  mov     r8, rsi; MessageGuid
0x18001f3d1  mov     [rsp+68h+var_40], rax
0x18001f3d6  mov     edx, 2Bh ; '+'; MessageFlags
0x18001f3db  mov     rcx, r14; LoggerHandle
0x18001f3de  mov     [rsp+68h+var_48], rbx
0x18001f3e3  call    cs:__imp_TraceMessage
0x18001f3e9  add     rsp, 40h
0x18001f3ed  pop     r14
0x18001f3ef  pop     rdi
0x18001f3f0  pop     rsi
0x18001f3f1  pop     rbp
0x18001f3f2  pop     rbx
0x18001f3f3  retn
```
