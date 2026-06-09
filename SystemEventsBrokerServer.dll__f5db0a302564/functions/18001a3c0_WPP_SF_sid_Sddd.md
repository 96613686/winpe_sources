# WPP_SF__sid_Sddd

- ea: `0x18001a3c0`
- end: `0x18001a4d4`
- name: `WPP_SF__sid_Sddd`
- size: `276`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64, char, char, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006e00`

## callees

- `0x18001a3c0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001a4bc`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001a4bc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a41f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a443`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a41f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a443`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a42c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a42c`

## pseudocode

```c
ULONG WPP_SF__sid_Sddd(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, char *a4, const wchar_t *a5, ...)
{
  const wchar_t *v5; // rdi
  char *v6; // rbx
  __int64 v8; // rax
  __int64 v9; // rbp
  DWORD LengthSid; // esi
  __int64 v12; // [rsp+E8h] [rbp+30h] BYREF
  va_list va; // [rsp+E8h] [rbp+30h]
  __int64 v14; // [rsp+F0h] [rbp+38h] BYREF
  va_list va1; // [rsp+F0h] [rbp+38h]
  va_list va2; // [rsp+F8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v12 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v14 = va_arg(va2, _QWORD);
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
               &WPP_20b8a5fb926c301eb1fcdafac32fa047_Traceguids,
               0xAu,
               v6,
               LengthSid,
               v5,
               v9,
               va,
               4,
               va1,
               4,
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
           &WPP_20b8a5fb926c301eb1fcdafac32fa047_Traceguids,
           0xAu,
           v6,
           LengthSid,
           v5,
           v9,
           va,
           4,
           va1,
           4,
           va2,
           4,
           0);
}

```

## disassembly

```asm
0x18001a3c0  push    rbx
0x18001a3c2  push    rbp
0x18001a3c3  push    rsi
0x18001a3c4  push    rdi
0x18001a3c5  push    r12
0x18001a3c7  push    r14
0x18001a3c9  push    r15
0x18001a3cb  sub     rsp, 80h
0x18001a3d2  mov     rdi, [rsp+0B8h+arg_20]
0x18001a3da  xor     r15d, r15d
0x18001a3dd  mov     rbx, r9
0x18001a3e0  mov     r14, rcx
0x18001a3e3  mov     r12d, 0Ah
0x18001a3e9  test    rdi, rdi
0x18001a3ec  jz      short loc_18001A406
0x18001a3ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a3f2  inc     rax
0x18001a3f5  cmp     [rdi+rax*2], r15w
0x18001a3fa  jnz     short loc_18001A3F2
0x18001a3fc  lea     rbp, ds:2[rax*2]
0x18001a404  jmp     short loc_18001A409
0x18001a406  mov     rbp, r12
0x18001a409  test    rdi, rdi
0x18001a40c  lea     rax, aNull_0; "NULL"
0x18001a413  cmovz   rdi, rax
0x18001a417  test    rbx, rbx
0x18001a41a  jz      short loc_18001A436
0x18001a41c  mov     rcx, rbx; pSid
0x18001a41f  call    cs:__imp_IsValidSid
0x18001a425  test    eax, eax
0x18001a427  jz      short loc_18001A436
0x18001a429  mov     rcx, rbx; pSid
0x18001a42c  call    cs:__imp_GetLengthSid
0x18001a432  mov     esi, eax
0x18001a434  jmp     short loc_18001A440
0x18001a436  mov     esi, 5
0x18001a43b  test    rbx, rbx
0x18001a43e  jz      short loc_18001A44D
0x18001a440  mov     rcx, rbx; pSid
0x18001a443  call    cs:__imp_IsValidSid
0x18001a449  test    eax, eax
0x18001a44b  jnz     short loc_18001A454
0x18001a44d  lea     rbx, aNull; "NULL"
0x18001a454  mov     [rsp+0B8h+var_48], r15
0x18001a459  lea     rcx, [rsp+0B8h+arg_38]
0x18001a461  mov     edx, 4
0x18001a466  mov     eax, esi
0x18001a468  mov     [rsp+0B8h+var_50], rdx
0x18001a46d  lea     r8, WPP_20b8a5fb926c301eb1fcdafac32fa047_Traceguids; MessageGuid
0x18001a474  mov     [rsp+0B8h+var_58], rcx
0x18001a479  mov     r9d, r12d; MessageNumber
0x18001a47c  mov     [rsp+0B8h+var_60], rdx
0x18001a481  lea     rcx, [rsp+0B8h+arg_30]
0x18001a489  mov     [rsp+0B8h+var_68], rcx
0x18001a48e  lea     rcx, [rsp+0B8h+arg_28]
0x18001a496  mov     [rsp+0B8h+var_70], rdx
0x18001a49b  mov     edx, 2Bh ; '+'; MessageFlags
0x18001a4a0  mov     [rsp+0B8h+var_78], rcx
0x18001a4a5  mov     rcx, r14; LoggerHandle
0x18001a4a8  mov     [rsp+0B8h+var_80], rbp
0x18001a4ad  mov     [rsp+0B8h+var_88], rdi
0x18001a4b2  mov     [rsp+0B8h+var_90], rax
0x18001a4b7  mov     [rsp+0B8h+var_98], rbx
0x18001a4bc  call    cs:__imp_TraceMessage
0x18001a4c2  add     rsp, 80h
0x18001a4c9  pop     r15
0x18001a4cb  pop     r14
0x18001a4cd  pop     r12
0x18001a4cf  pop     rdi
0x18001a4d0  pop     rsi
0x18001a4d1  pop     rbp
0x18001a4d2  pop     rbx
0x18001a4d3  retn
```
