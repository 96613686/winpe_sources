# WPP_SF__sid_d

- ea: `0x18001f4d8`
- end: `0x18001f57f`
- name: `WPP_SF__sid_d`
- size: `167`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800022b0`

## callees

- `0x18001f4d8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001f569`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001f569`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f4f5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f519`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f4f5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f519`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f502`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f502`

## pseudocode

```c
ULONG WPP_SF__sid_d(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, char *a4, ...)
{
  char *v4; // rbx
  DWORD LengthSid; // edi
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v4 = a4;
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v4);
  }
  else
  {
    LengthSid = 5;
    if ( !v4 )
    {
LABEL_6:
      v4 = "NULL";
      return TraceMessage(
               LoggerHandle,
               0x2Bu,
               &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
               0x46u,
               v4,
               LengthSid,
               va,
               4,
               0);
    }
  }
  if ( !IsValidSid(v4) )
    goto LABEL_6;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
           0x46u,
           v4,
           LengthSid,
           va,
           4,
           0);
}

```

## disassembly

```asm
0x18001f4d8  mov     [rsp+arg_0], rbx
0x18001f4dd  mov     [rsp+arg_8], rsi
0x18001f4e2  push    rdi
0x18001f4e3  sub     rsp, 50h
0x18001f4e7  mov     rbx, r9
0x18001f4ea  mov     rsi, rcx
0x18001f4ed  test    r9, r9
0x18001f4f0  jz      short loc_18001F50C
0x18001f4f2  mov     rcx, rbx; pSid
0x18001f4f5  call    cs:__imp_IsValidSid
0x18001f4fb  test    eax, eax
0x18001f4fd  jz      short loc_18001F50C
0x18001f4ff  mov     rcx, rbx; pSid
0x18001f502  call    cs:__imp_GetLengthSid
0x18001f508  mov     edi, eax
0x18001f50a  jmp     short loc_18001F516
0x18001f50c  mov     edi, 5
0x18001f511  test    rbx, rbx
0x18001f514  jz      short loc_18001F523
0x18001f516  mov     rcx, rbx; pSid
0x18001f519  call    cs:__imp_IsValidSid
0x18001f51f  test    eax, eax
0x18001f521  jnz     short loc_18001F52A
0x18001f523  lea     rbx, aNull; "NULL"
0x18001f52a  mov     [rsp+58h+var_18], 0
0x18001f533  lea     rcx, [rsp+58h+arg_20]
0x18001f53b  mov     [rsp+58h+var_20], 4
0x18001f544  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids; MessageGuid
0x18001f54b  mov     [rsp+58h+var_28], rcx
0x18001f550  mov     r9d, 46h ; 'F'; MessageNumber
0x18001f556  mov     eax, edi
0x18001f558  mov     rcx, rsi; LoggerHandle
0x18001f55b  mov     [rsp+58h+var_30], rax
0x18001f560  mov     [rsp+58h+var_38], rbx
0x18001f565  lea     edx, [r9-1Bh]; MessageFlags
0x18001f569  call    cs:__imp_TraceMessage
0x18001f56f  mov     rbx, [rsp+58h+arg_0]
0x18001f574  mov     rsi, [rsp+58h+arg_8]
0x18001f579  add     rsp, 50h
0x18001f57d  pop     rdi
0x18001f57e  retn
```
