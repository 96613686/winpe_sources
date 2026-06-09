# WPP_SF__sid_S

- ea: `0x18001f3fc`
- end: `0x18001f4d2`
- name: `WPP_SF__sid_S`
- size: `214`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c0b0`
- `0x180010560`

## callees

- `0x18001f3fc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001f4bb`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001f4bb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f45d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f481`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f45d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f481`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f46a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f46a`

## pseudocode

```c
ULONG __fastcall WPP_SF__sid_S(TRACEHANDLE LoggerHandle, USHORT a2, const GUID *a3, char *a4, const wchar_t *a5)
{
  const wchar_t *v5; // rdi
  char *v7; // rbx
  __int64 v10; // rax
  __int64 v11; // rbp
  DWORD LengthSid; // esi

  v5 = a5;
  v7 = a4;
  if ( a5 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a5[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v7);
  }
  else
  {
    LengthSid = 5;
    if ( !v7 )
    {
LABEL_13:
      v7 = "NULL";
      return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, v7, LengthSid, v5, v11, 0);
    }
  }
  if ( !IsValidSid(v7) )
    goto LABEL_13;
  return TraceMessage(LoggerHandle, 0x2Bu, a3, a2, v7, LengthSid, v5, v11, 0);
}

```

## disassembly

```asm
0x18001f3fc  push    rbx
0x18001f3fe  push    rbp
0x18001f3ff  push    rsi
0x18001f400  push    rdi
0x18001f401  push    r12
0x18001f403  push    r13
0x18001f405  push    r14
0x18001f407  push    r15
0x18001f409  sub     rsp, 58h
0x18001f40d  mov     rdi, [rsp+98h+arg_20]
0x18001f415  xor     r13d, r13d
0x18001f418  movzx   r15d, dx
0x18001f41c  mov     rbx, r9
0x18001f41f  mov     r14, r8
0x18001f422  mov     r12, rcx
0x18001f425  test    rdi, rdi
0x18001f428  jz      short loc_18001F442
0x18001f42a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f42e  inc     rax
0x18001f431  cmp     [rdi+rax*2], r13w
0x18001f436  jnz     short loc_18001F42E
0x18001f438  lea     rbp, ds:2[rax*2]
0x18001f440  jmp     short loc_18001F447
0x18001f442  mov     ebp, 0Ah
0x18001f447  test    rdi, rdi
0x18001f44a  lea     rax, aNull_0; "NULL"
0x18001f451  cmovz   rdi, rax
0x18001f455  test    rbx, rbx
0x18001f458  jz      short loc_18001F474
0x18001f45a  mov     rcx, rbx; pSid
0x18001f45d  call    cs:__imp_IsValidSid
0x18001f463  test    eax, eax
0x18001f465  jz      short loc_18001F474
0x18001f467  mov     rcx, rbx; pSid
0x18001f46a  call    cs:__imp_GetLengthSid
0x18001f470  mov     esi, eax
0x18001f472  jmp     short loc_18001F47E
0x18001f474  mov     esi, 5
0x18001f479  test    rbx, rbx
0x18001f47c  jz      short loc_18001F48B
0x18001f47e  mov     rcx, rbx; pSid
0x18001f481  call    cs:__imp_IsValidSid
0x18001f487  test    eax, eax
0x18001f489  jnz     short loc_18001F492
0x18001f48b  lea     rbx, aNull; "NULL"
0x18001f492  mov     [rsp+98h+var_58], r13
0x18001f497  mov     r9d, r15d; MessageNumber
0x18001f49a  mov     [rsp+98h+var_60], rbp
0x18001f49f  mov     r8, r14; MessageGuid
0x18001f4a2  mov     eax, esi
0x18001f4a4  mov     edx, 2Bh ; '+'; MessageFlags
0x18001f4a9  mov     [rsp+98h+var_68], rdi
0x18001f4ae  mov     rcx, r12; LoggerHandle
0x18001f4b1  mov     [rsp+98h+var_70], rax
0x18001f4b6  mov     [rsp+98h+var_78], rbx
0x18001f4bb  call    cs:__imp_TraceMessage
0x18001f4c1  add     rsp, 58h
0x18001f4c5  pop     r15
0x18001f4c7  pop     r14
0x18001f4c9  pop     r13
0x18001f4cb  pop     r12
0x18001f4cd  pop     rdi
0x18001f4ce  pop     rsi
0x18001f4cf  pop     rbp
0x18001f4d0  pop     rbx
0x18001f4d1  retn
```
