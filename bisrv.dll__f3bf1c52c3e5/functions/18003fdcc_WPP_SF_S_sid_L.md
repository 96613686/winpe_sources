# WPP_SF_S_sid_L

- ea: `0x18003fdcc`
- end: `0x18003fec3`
- name: `WPP_SF_S_sid_L`
- size: `247`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid, char)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180044b34`
- `0x18004b460`

## callees

- `0x18003fdcc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003fea5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003fea5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003fe94`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003feb0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003fe94`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003feb0`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003fe77`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003fe77`

## pseudocode

```c
ULONG WPP_SF_S_sid_L(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, const wchar_t *a4, char *pSid, ...)
{
  const char *v5; // rbx
  DWORD LengthSid; // esi
  __int64 v10; // rax
  __int64 v11; // rcx
  va_list va; // [rsp+C8h] [rbp+30h] BYREF

  va_start(va, pSid);
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
LABEL_3:
      v5 = "NULL";
      goto LABEL_4;
    }
  }
  if ( !IsValidSid(pSid) )
    goto LABEL_3;
LABEL_4:
  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a4[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_e6b615a7d18a3fcf430735eb063d161f_Traceguids,
           a2,
           a4,
           v11,
           v5,
           LengthSid,
           va,
           4,
           0);
}

```

## disassembly

```asm
0x18003fdcc  push    rbx
0x18003fdce  push    rbp
0x18003fdcf  push    rsi
0x18003fdd0  push    rdi
0x18003fdd1  push    r14
0x18003fdd3  push    r15
0x18003fdd5  sub     rsp, 68h
0x18003fdd9  mov     rbx, [rsp+98h+pSid]
0x18003fde1  xor     r15d, r15d
0x18003fde4  movzx   ebp, dx
0x18003fde7  mov     rdi, r9
0x18003fdea  mov     r14, rcx
0x18003fded  test    rbx, rbx
0x18003fdf0  jnz     loc_18003FE91
0x18003fdf6  mov     esi, 5
0x18003fdfb  test    rbx, rbx
0x18003fdfe  jnz     loc_18003FEAD
0x18003fe04  lea     rbx, aNull; "NULL"
0x18003fe0b  test    rdi, rdi
0x18003fe0e  jz      short loc_18003FE8A
0x18003fe10  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003fe14  inc     rax
0x18003fe17  cmp     [rdi+rax*2], r15w
0x18003fe1c  jnz     short loc_18003FE14
0x18003fe1e  lea     rcx, ds:2[rax*2]
0x18003fe26  mov     [rsp+98h+var_48], r15
0x18003fe2b  lea     rdx, aNull_0; "NULL"
0x18003fe32  mov     [rsp+98h+var_50], 4
0x18003fe3b  lea     r8, WPP_e6b615a7d18a3fcf430735eb063d161f_Traceguids; MessageGuid
0x18003fe42  test    rdi, rdi
0x18003fe45  mov     eax, esi
0x18003fe47  mov     r9d, ebp; MessageNumber
0x18003fe4a  cmovz   rdi, rdx
0x18003fe4e  lea     rdx, [rsp+98h+arg_28]
0x18003fe56  mov     [rsp+98h+var_58], rdx
0x18003fe5b  mov     edx, 2Bh ; '+'; MessageFlags
0x18003fe60  mov     [rsp+98h+var_60], rax
0x18003fe65  mov     [rsp+98h+var_68], rbx
0x18003fe6a  mov     [rsp+98h+var_70], rcx
0x18003fe6f  mov     rcx, r14; LoggerHandle
0x18003fe72  mov     [rsp+98h+var_78], rdi
0x18003fe77  call    cs:__imp_TraceMessage
0x18003fe7d  add     rsp, 68h
0x18003fe81  pop     r15
0x18003fe83  pop     r14
0x18003fe85  pop     rdi
0x18003fe86  pop     rsi
0x18003fe87  pop     rbp
0x18003fe88  pop     rbx
0x18003fe89  retn
0x18003fe8a  mov     ecx, 0Ah
0x18003fe8f  jmp     short loc_18003FE26
0x18003fe91  mov     rcx, rbx; pSid
0x18003fe94  call    cs:__imp_IsValidSid
0x18003fe9a  test    eax, eax
0x18003fe9c  jz      loc_18003FDF6
0x18003fea2  mov     rcx, rbx; pSid
0x18003fea5  call    cs:__imp_GetLengthSid
0x18003feab  mov     esi, eax
0x18003fead  mov     rcx, rbx; pSid
0x18003feb0  call    cs:__imp_IsValidSid
0x18003feb6  test    eax, eax
0x18003feb8  jnz     loc_18003FE0B
0x18003febe  jmp     loc_18003FE04
```
