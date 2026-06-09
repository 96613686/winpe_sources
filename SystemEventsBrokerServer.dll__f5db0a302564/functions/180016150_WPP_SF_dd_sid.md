# WPP_SF_dd_sid_

- ea: `0x180016150`
- end: `0x18001620a`
- name: `WPP_SF_dd_sid_`
- size: `186`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, char, PSID pSid)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ef0`
- `0x1800022b0`
- `0x180012b8c`
- `0x180016590`

## callees

- `0x180016150`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800161fb`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800161fb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180016173`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180016197`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180016173`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180016197`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180016180`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180016180`

## pseudocode

```c
ULONG __fastcall WPP_SF_dd_sid_(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, int a4, char a5, char *pSid)
{
  char *v6; // rbx
  DWORD LengthSid; // edi
  int v11; // [rsp+A8h] [rbp+20h] BYREF

  v11 = a4;
  v6 = pSid;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(v6);
  }
  else
  {
    LengthSid = 5;
    if ( !v6 )
    {
LABEL_6:
      v6 = "NULL";
      return TraceMessage(
               LoggerHandle,
               0x2Bu,
               &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
               a2,
               &v11,
               4,
               &a5,
               4,
               v6,
               LengthSid,
               0);
    }
  }
  if ( !IsValidSid(v6) )
    goto LABEL_6;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
           a2,
           &v11,
           4,
           &a5,
           4,
           v6,
           LengthSid,
           0);
}

```

## disassembly

```asm
0x180016150  mov     [rsp+arg_18], r9d
0x180016155  push    rbx
0x180016156  push    rbp
0x180016157  push    rsi
0x180016158  push    rdi
0x180016159  sub     rsp, 68h
0x18001615d  mov     rbx, [rsp+88h+pSid]
0x180016165  mov     rbp, rcx
0x180016168  movzx   esi, dx
0x18001616b  test    rbx, rbx
0x18001616e  jz      short loc_18001618A
0x180016170  mov     rcx, rbx; pSid
0x180016173  call    cs:__imp_IsValidSid
0x180016179  test    eax, eax
0x18001617b  jz      short loc_18001618A
0x18001617d  mov     rcx, rbx; pSid
0x180016180  call    cs:__imp_GetLengthSid
0x180016186  mov     edi, eax
0x180016188  jmp     short loc_180016194
0x18001618a  mov     edi, 5
0x18001618f  test    rbx, rbx
0x180016192  jz      short loc_1800161A1
0x180016194  mov     rcx, rbx; pSid
0x180016197  call    cs:__imp_IsValidSid
0x18001619d  test    eax, eax
0x18001619f  jnz     short loc_1800161A8
0x1800161a1  lea     rbx, aNull; "NULL"
0x1800161a8  mov     [rsp+88h+var_38], 0
0x1800161b1  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids; MessageGuid
0x1800161b8  mov     eax, edi
0x1800161ba  mov     r9d, esi; MessageNumber
0x1800161bd  mov     [rsp+88h+var_40], rax
0x1800161c2  mov     edx, 2Bh ; '+'; MessageFlags
0x1800161c7  mov     [rsp+88h+var_48], rbx
0x1800161cc  lea     rax, [rsp+88h+arg_20]
0x1800161d4  mov     [rsp+88h+var_50], 4
0x1800161dd  mov     rcx, rbp; LoggerHandle
0x1800161e0  mov     [rsp+88h+var_58], rax
0x1800161e5  lea     rax, [rsp+88h+arg_18]
0x1800161ed  mov     [rsp+88h+var_60], 4
0x1800161f6  mov     [rsp+88h+var_68], rax
0x1800161fb  call    cs:__imp_TraceMessage
0x180016201  add     rsp, 68h
0x180016205  pop     rdi
0x180016206  pop     rsi
0x180016207  pop     rbp
0x180016208  pop     rbx
0x180016209  retn
```
