# WPP_SF__guid__sid_S

- ea: `0x18001c00c`
- end: `0x18001c0fa`
- name: `WPP_SF__guid__sid_S`
- size: `238`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b3d0`
- `0x18000e880`
- `0x18001bcdc`
- `0x18001be34`

## callees

- `0x18001c00c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001c0e3`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001c0e3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001c073`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001c099`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001c073`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001c099`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001c082`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001c082`

## pseudocode

```c
ULONG __fastcall WPP_SF__guid__sid_S(
        TRACEHANDLE LoggerHandle,
        USHORT a2,
        const GUID *a3,
        __int64 a4,
        char *pSid,
        const wchar_t *a6)
{
  const wchar_t *v6; // rdi
  __int64 v11; // rax
  __int64 v12; // rbp
  const char *v13; // rbx
  DWORD LengthSid; // esi

  v6 = a6;
  if ( a6 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a6[v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v12 = 10;
  }
  v13 = pSid;
  if ( !a6 )
    v6 = L"NULL";
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
  }
  else
  {
    LengthSid = 5;
    if ( !pSid )
    {
LABEL_13:
      v13 = "NULL";
      return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, a4, 16, v13, LengthSid, v6, v12, 0);
    }
  }
  if ( !IsValidSid(pSid) )
    goto LABEL_13;
  return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, a4, 16, v13, LengthSid, v6, v12, 0);
}

```

## disassembly

```asm
0x18001c00c  push    rbx
0x18001c00e  push    rbp
0x18001c00f  push    rsi
0x18001c010  push    rdi
0x18001c011  push    r12
0x18001c013  push    r13
0x18001c015  push    r14
0x18001c017  push    r15
0x18001c019  sub     rsp, 68h
0x18001c01d  mov     rdi, [rsp+0A8h+arg_28]
0x18001c025  mov     r13, rcx
0x18001c028  xor     ecx, ecx
0x18001c02a  movzx   r12d, dx
0x18001c02e  mov     r14, r9
0x18001c031  mov     r15, r8
0x18001c034  test    rdi, rdi
0x18001c037  jz      short loc_18001C050
0x18001c039  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c03d  inc     rax
0x18001c040  cmp     [rdi+rax*2], cx
0x18001c044  jnz     short loc_18001C03D
0x18001c046  lea     rbp, ds:2[rax*2]
0x18001c04e  jmp     short loc_18001C055
0x18001c050  mov     ebp, 0Ah
0x18001c055  mov     rbx, [rsp+0A8h+pSid]
0x18001c05d  lea     rax, aNull_0; "NULL"
0x18001c064  test    rdi, rdi
0x18001c067  cmovz   rdi, rax
0x18001c06b  test    rbx, rbx
0x18001c06e  jz      short loc_18001C08C
0x18001c070  mov     rcx, rbx; pSid
0x18001c073  call    cs:__imp_IsValidSid
0x18001c079  xor     ecx, ecx
0x18001c07b  test    eax, eax
0x18001c07d  jz      short loc_18001C08C
0x18001c07f  mov     rcx, rbx; pSid
0x18001c082  call    cs:__imp_GetLengthSid
0x18001c088  mov     esi, eax
0x18001c08a  jmp     short loc_18001C096
0x18001c08c  mov     esi, 5
0x18001c091  test    rbx, rbx
0x18001c094  jz      short loc_18001C0A5
0x18001c096  mov     rcx, rbx; pSid
0x18001c099  call    cs:__imp_IsValidSid
0x18001c09f  xor     ecx, ecx
0x18001c0a1  test    eax, eax
0x18001c0a3  jnz     short loc_18001C0AC
0x18001c0a5  lea     rbx, aNull; "NULL"
0x18001c0ac  mov     [rsp+0A8h+var_58], rcx
0x18001c0b1  mov     r9d, r12d; MessageNumber
0x18001c0b4  mov     [rsp+0A8h+var_60], rbp
0x18001c0b9  mov     r8, r15; MessageGuid
0x18001c0bc  mov     [rsp+0A8h+var_68], rdi
0x18001c0c1  mov     edx, 2Bh ; '+'; MessageFlags
0x18001c0c6  mov     eax, esi
0x18001c0c8  mov     rcx, r13; LoggerHandle
0x18001c0cb  mov     [rsp+0A8h+var_70], rax
0x18001c0d0  mov     [rsp+0A8h+var_78], rbx
0x18001c0d5  mov     [rsp+0A8h+var_80], 10h
0x18001c0de  mov     [rsp+0A8h+var_88], r14
0x18001c0e3  call    cs:__imp_TraceMessage
0x18001c0e9  add     rsp, 68h
0x18001c0ed  pop     r15
0x18001c0ef  pop     r14
0x18001c0f1  pop     r13
0x18001c0f3  pop     r12
0x18001c0f5  pop     rdi
0x18001c0f6  pop     rsi
0x18001c0f7  pop     rbp
0x18001c0f8  pop     rbx
0x18001c0f9  retn
```
