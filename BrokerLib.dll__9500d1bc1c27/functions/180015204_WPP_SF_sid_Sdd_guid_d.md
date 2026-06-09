# WPP_SF__sid_Sdd_guid_d

- ea: `0x180015204`
- end: `0x180015331`
- name: `WPP_SF__sid_Sdd_guid_d`
- size: `301`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64, char, char, __int64, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800150bc`

## callees

- `0x180015204`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015270`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015270`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015263`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015287`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015263`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015287`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180015319`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180015319`

## pseudocode

```c
ULONG WPP_SF__sid_Sdd_guid_d(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, char *a4, const wchar_t *a5, ...)
{
  const wchar_t *v5; // rdi
  char *v6; // rbx
  __int64 v8; // rax
  __int64 v9; // rbp
  DWORD LengthSid; // esi
  __int64 v12; // [rsp+F8h] [rbp+30h] BYREF
  va_list va; // [rsp+F8h] [rbp+30h]
  __int64 v14; // [rsp+100h] [rbp+38h] BYREF
  va_list va1; // [rsp+100h] [rbp+38h]
  __int64 v16; // [rsp+108h] [rbp+40h]
  va_list va2; // [rsp+110h] [rbp+48h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v12 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v14 = va_arg(va2, _QWORD);
  v16 = va_arg(va2, _QWORD);
  v5 = a5;
  v6 = a4;
  if ( a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a5[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v6);
  }
  else
  {
    LengthSid = 5;
    if ( !v6 )
    {
LABEL_13:
      v6 = "NULL";
      return TraceMessage(
               LoggerHandle,
               0x2Bu,
               &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids,
               0xAu,
               v6,
               LengthSid,
               v5,
               v9,
               va,
               4,
               va1,
               4,
               v16,
               16,
               va2,
               4,
               0);
    }
  }
  if ( !IsValidSid(v6) )
    goto LABEL_13;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids,
           0xAu,
           v6,
           LengthSid,
           v5,
           v9,
           va,
           4,
           va1,
           4,
           v16,
           16,
           va2,
           4,
           0);
}

```

## disassembly

```asm
0x180015204  push    rbx
0x180015206  push    rbp
0x180015207  push    rsi
0x180015208  push    rdi
0x180015209  push    r12
0x18001520b  push    r14
0x18001520d  push    r15
0x18001520f  sub     rsp, 90h
0x180015216  mov     rdi, [rsp+0C8h+arg_20]
0x18001521e  xor     r15d, r15d
0x180015221  mov     rbx, r9
0x180015224  mov     r14, rcx
0x180015227  mov     r12d, 0Ah
0x18001522d  test    rdi, rdi
0x180015230  jz      short loc_18001524A
0x180015232  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015236  inc     rax
0x180015239  cmp     [rdi+rax*2], r15w
0x18001523e  jnz     short loc_180015236
0x180015240  lea     rbp, ds:2[rax*2]
0x180015248  jmp     short loc_18001524D
0x18001524a  mov     rbp, r12
0x18001524d  test    rdi, rdi
0x180015250  lea     rax, aNull_0; "NULL"
0x180015257  cmovz   rdi, rax
0x18001525b  test    rbx, rbx
0x18001525e  jz      short loc_18001527A
0x180015260  mov     rcx, rbx; pSid
0x180015263  call    cs:__imp_IsValidSid
0x180015269  test    eax, eax
0x18001526b  jz      short loc_18001527A
0x18001526d  mov     rcx, rbx; pSid
0x180015270  call    cs:__imp_GetLengthSid
0x180015276  mov     esi, eax
0x180015278  jmp     short loc_180015284
0x18001527a  mov     esi, 5
0x18001527f  test    rbx, rbx
0x180015282  jz      short loc_180015291
0x180015284  mov     rcx, rbx; pSid
0x180015287  call    cs:__imp_IsValidSid
0x18001528d  test    eax, eax
0x18001528f  jnz     short loc_180015298
0x180015291  lea     rbx, aNull; "NULL"
0x180015298  mov     [rsp+0C8h+var_48], r15
0x1800152a0  lea     rax, [rsp+0C8h+arg_40]
0x1800152a8  mov     edx, 4
0x1800152ad  mov     ecx, esi
0x1800152af  mov     [rsp+0C8h+var_50], rdx
0x1800152b4  lea     r8, WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids; MessageGuid
0x1800152bb  mov     [rsp+0C8h+var_58], rax
0x1800152c0  mov     r9d, r12d; MessageNumber
0x1800152c3  mov     rax, [rsp+0C8h+arg_38]
0x1800152cb  mov     [rsp+0C8h+var_60], 10h
0x1800152d4  mov     [rsp+0C8h+var_68], rax
0x1800152d9  lea     rax, [rsp+0C8h+arg_30]
0x1800152e1  mov     [rsp+0C8h+var_70], rdx
0x1800152e6  mov     [rsp+0C8h+var_78], rax
0x1800152eb  lea     rax, [rsp+0C8h+arg_28]
0x1800152f3  mov     [rsp+0C8h+var_80], rdx
0x1800152f8  mov     edx, 2Bh ; '+'; MessageFlags
0x1800152fd  mov     [rsp+0C8h+var_88], rax
0x180015302  mov     [rsp+0C8h+var_90], rbp
0x180015307  mov     [rsp+0C8h+var_98], rdi
0x18001530c  mov     [rsp+0C8h+var_A0], rcx
0x180015311  mov     rcx, r14; LoggerHandle
0x180015314  mov     [rsp+0C8h+var_A8], rbx
0x180015319  call    cs:__imp_TraceMessage
0x18001531f  add     rsp, 90h
0x180015326  pop     r15
0x180015328  pop     r14
0x18001532a  pop     r12
0x18001532c  pop     rdi
0x18001532d  pop     rsi
0x18001532e  pop     rbp
0x18001532f  pop     rbx
0x180015330  retn
```
