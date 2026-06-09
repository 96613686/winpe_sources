# WPP_SF__sid_

- ea: `0x180076fc4`
- end: `0x180077049`
- name: `WPP_SF__sid_`
- size: `133`
- prototype: `__int64 __fastcall(TRACEHANDLE LoggerHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800761d4`

## callees

- `0x180076fc4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180076feb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180076feb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180076fde`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180077002`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180076fde`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180077002`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18007703a`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18007703a`

## pseudocode

```c
ULONG __fastcall WPP_SF__sid_(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, char *a4)
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
      return TraceMessage(LoggerHandle, 0x2Bu, &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids, a2, v5, LengthSid, 0);
    }
  }
  if ( !IsValidSid(v5) )
    goto LABEL_6;
  return TraceMessage(LoggerHandle, 0x2Bu, &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids, a2, v5, LengthSid, 0);
}

```

## disassembly

```asm
0x180076fc4  push    rbx
0x180076fc6  push    rbp
0x180076fc7  push    rsi
0x180076fc8  push    rdi
0x180076fc9  sub     rsp, 48h
0x180076fcd  movzx   esi, dx
0x180076fd0  mov     rbx, r9
0x180076fd3  mov     rbp, rcx
0x180076fd6  test    r9, r9
0x180076fd9  jz      short loc_180076FF5
0x180076fdb  mov     rcx, rbx; pSid
0x180076fde  call    cs:__imp_IsValidSid
0x180076fe4  test    eax, eax
0x180076fe6  jz      short loc_180076FF5
0x180076fe8  mov     rcx, rbx; pSid
0x180076feb  call    cs:__imp_GetLengthSid
0x180076ff1  mov     edi, eax
0x180076ff3  jmp     short loc_180076FFF
0x180076ff5  mov     edi, 5
0x180076ffa  test    rbx, rbx
0x180076ffd  jz      short loc_18007700C
0x180076fff  mov     rcx, rbx; pSid
0x180077002  call    cs:__imp_IsValidSid
0x180077008  test    eax, eax
0x18007700a  jnz     short loc_180077013
0x18007700c  lea     rbx, aNull; "NULL"
0x180077013  mov     eax, edi
0x180077015  lea     r8, WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids; MessageGuid
0x18007701c  mov     [rsp+68h+var_38], 0
0x180077025  mov     r9d, esi; MessageNumber
0x180077028  mov     [rsp+68h+var_40], rax
0x18007702d  mov     edx, 2Bh ; '+'; MessageFlags
0x180077032  mov     rcx, rbp; LoggerHandle
0x180077035  mov     [rsp+68h+var_48], rbx
0x18007703a  call    cs:__imp_TraceMessage
0x180077040  add     rsp, 48h
0x180077044  pop     rdi
0x180077045  pop     rsi
0x180077046  pop     rbp
0x180077047  pop     rbx
0x180077048  retn
```
