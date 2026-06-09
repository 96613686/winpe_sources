# WPP_SF__sid_S_guid_DDd

- ea: `0x1800191d0`
- end: `0x1800192f6`
- name: `WPP_SF__sid_S_guid_DDd`
- size: `294`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64, __int64, char, char, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b0f0`

## callees

- `0x1800191d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019236`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019236`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180019229`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001924d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180019229`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001924d`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800192e0`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800192e0`

## pseudocode

```c
ULONG WPP_SF__sid_S_guid_DDd(
        TRACEHANDLE LoggerHandle,
        __int64 a2,
        __int64 a3,
        char *a4,
        const wchar_t *a5,
        __int64 a6,
        ...)
{
  const wchar_t *v6; // rdi
  char *v7; // rbx
  __int64 v9; // rax
  __int64 v10; // rbp
  DWORD LengthSid; // esi
  __int64 v13; // [rsp+100h] [rbp+38h] BYREF
  va_list va; // [rsp+100h] [rbp+38h]
  __int64 v15; // [rsp+108h] [rbp+40h] BYREF
  va_list va1; // [rsp+108h] [rbp+40h]
  va_list va2; // [rsp+110h] [rbp+48h] BYREF

  va_start(va2, a6);
  va_start(va1, a6);
  va_start(va, a6);
  v13 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v15 = va_arg(va2, _QWORD);
  v6 = a5;
  v7 = a4;
  if ( a5 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a5[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  if ( !a5 )
    v6 = L"NULL";
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
      return TraceMessage(
               LoggerHandle,
               0x2Bu,
               &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
               0x28u,
               v7,
               LengthSid,
               v6,
               v10,
               a6,
               16,
               va,
               4,
               va1,
               4,
               va2,
               4,
               0);
    }
  }
  if ( !IsValidSid(v7) )
    goto LABEL_13;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
           0x28u,
           v7,
           LengthSid,
           v6,
           v10,
           a6,
           16,
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
0x1800191d0  push    rbx
0x1800191d2  push    rbp
0x1800191d3  push    rsi
0x1800191d4  push    rdi
0x1800191d5  push    r14
0x1800191d7  push    r15
0x1800191d9  sub     rsp, 98h
0x1800191e0  mov     rdi, [rsp+0C8h+arg_20]
0x1800191e8  xor     r15d, r15d
0x1800191eb  mov     rbx, r9
0x1800191ee  mov     r14, rcx
0x1800191f1  test    rdi, rdi
0x1800191f4  jz      short loc_18001920E
0x1800191f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800191fa  inc     rax
0x1800191fd  cmp     [rdi+rax*2], r15w
0x180019202  jnz     short loc_1800191FA
0x180019204  lea     rbp, ds:2[rax*2]
0x18001920c  jmp     short loc_180019213
0x18001920e  mov     ebp, 0Ah
0x180019213  test    rdi, rdi
0x180019216  lea     rax, aNull_0; "NULL"
0x18001921d  cmovz   rdi, rax
0x180019221  test    rbx, rbx
0x180019224  jz      short loc_180019240
0x180019226  mov     rcx, rbx; pSid
0x180019229  call    cs:__imp_IsValidSid
0x18001922f  test    eax, eax
0x180019231  jz      short loc_180019240
0x180019233  mov     rcx, rbx; pSid
0x180019236  call    cs:__imp_GetLengthSid
0x18001923c  mov     esi, eax
0x18001923e  jmp     short loc_18001924A
0x180019240  mov     esi, 5
0x180019245  test    rbx, rbx
0x180019248  jz      short loc_180019257
0x18001924a  mov     rcx, rbx; pSid
0x18001924d  call    cs:__imp_IsValidSid
0x180019253  test    eax, eax
0x180019255  jnz     short loc_18001925E
0x180019257  lea     rbx, aNull; "NULL"
0x18001925e  mov     [rsp+0C8h+var_48], r15
0x180019266  lea     rax, [rsp+0C8h+arg_40]
0x18001926e  mov     r9d, 28h ; '('; MessageNumber
0x180019274  mov     ecx, esi
0x180019276  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids; MessageGuid
0x18001927d  lea     edx, [r9-24h]
0x180019281  mov     [rsp+0C8h+var_50], rdx
0x180019286  mov     [rsp+0C8h+var_58], rax
0x18001928b  lea     rax, [rsp+0C8h+arg_38]
0x180019293  mov     [rsp+0C8h+var_60], rdx
0x180019298  mov     [rsp+0C8h+var_68], rax
0x18001929d  lea     rax, [rsp+0C8h+arg_30]
0x1800192a5  mov     [rsp+0C8h+var_70], rdx
0x1800192aa  lea     edx, [r9+3]; MessageFlags
0x1800192ae  mov     [rsp+0C8h+var_78], rax
0x1800192b3  mov     rax, [rsp+0C8h+arg_28]
0x1800192bb  mov     [rsp+0C8h+var_80], 10h
0x1800192c4  mov     [rsp+0C8h+var_88], rax
0x1800192c9  mov     [rsp+0C8h+var_90], rbp
0x1800192ce  mov     [rsp+0C8h+var_98], rdi
0x1800192d3  mov     [rsp+0C8h+var_A0], rcx
0x1800192d8  mov     rcx, r14; LoggerHandle
0x1800192db  mov     [rsp+0C8h+var_A8], rbx
0x1800192e0  call    cs:__imp_TraceMessage
0x1800192e6  add     rsp, 98h
0x1800192ed  pop     r15
0x1800192ef  pop     r14
0x1800192f1  pop     rdi
0x1800192f2  pop     rsi
0x1800192f3  pop     rbp
0x1800192f4  pop     rbx
0x1800192f5  retn
```
