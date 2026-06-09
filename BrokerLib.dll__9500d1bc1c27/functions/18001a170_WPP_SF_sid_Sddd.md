# WPP_SF__sid_Sddd

- ea: `0x18001a170`
- end: `0x18001a284`
- name: `WPP_SF__sid_Sddd`
- size: `276`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64, char, char, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800119f4`

## callees

- `0x18001a170`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a1dc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a1dc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a1cf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a1f3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a1cf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a1f3`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001a26c`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001a26c`

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
0x18001a170  push    rbx
0x18001a172  push    rbp
0x18001a173  push    rsi
0x18001a174  push    rdi
0x18001a175  push    r12
0x18001a177  push    r14
0x18001a179  push    r15
0x18001a17b  sub     rsp, 80h
0x18001a182  mov     rdi, [rsp+0B8h+arg_20]
0x18001a18a  xor     r15d, r15d
0x18001a18d  mov     rbx, r9
0x18001a190  mov     r14, rcx
0x18001a193  mov     r12d, 0Ah
0x18001a199  test    rdi, rdi
0x18001a19c  jz      short loc_18001A1B6
0x18001a19e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a1a2  inc     rax
0x18001a1a5  cmp     [rdi+rax*2], r15w
0x18001a1aa  jnz     short loc_18001A1A2
0x18001a1ac  lea     rbp, ds:2[rax*2]
0x18001a1b4  jmp     short loc_18001A1B9
0x18001a1b6  mov     rbp, r12
0x18001a1b9  test    rdi, rdi
0x18001a1bc  lea     rax, aNull_0; "NULL"
0x18001a1c3  cmovz   rdi, rax
0x18001a1c7  test    rbx, rbx
0x18001a1ca  jz      short loc_18001A1E6
0x18001a1cc  mov     rcx, rbx; pSid
0x18001a1cf  call    cs:__imp_IsValidSid
0x18001a1d5  test    eax, eax
0x18001a1d7  jz      short loc_18001A1E6
0x18001a1d9  mov     rcx, rbx; pSid
0x18001a1dc  call    cs:__imp_GetLengthSid
0x18001a1e2  mov     esi, eax
0x18001a1e4  jmp     short loc_18001A1F0
0x18001a1e6  mov     esi, 5
0x18001a1eb  test    rbx, rbx
0x18001a1ee  jz      short loc_18001A1FD
0x18001a1f0  mov     rcx, rbx; pSid
0x18001a1f3  call    cs:__imp_IsValidSid
0x18001a1f9  test    eax, eax
0x18001a1fb  jnz     short loc_18001A204
0x18001a1fd  lea     rbx, aNull; "NULL"
0x18001a204  mov     [rsp+0B8h+var_48], r15
0x18001a209  lea     rcx, [rsp+0B8h+arg_38]
0x18001a211  mov     edx, 4
0x18001a216  mov     eax, esi
0x18001a218  mov     [rsp+0B8h+var_50], rdx
0x18001a21d  lea     r8, WPP_20b8a5fb926c301eb1fcdafac32fa047_Traceguids; MessageGuid
0x18001a224  mov     [rsp+0B8h+var_58], rcx
0x18001a229  mov     r9d, r12d; MessageNumber
0x18001a22c  mov     [rsp+0B8h+var_60], rdx
0x18001a231  lea     rcx, [rsp+0B8h+arg_30]
0x18001a239  mov     [rsp+0B8h+var_68], rcx
0x18001a23e  lea     rcx, [rsp+0B8h+arg_28]
0x18001a246  mov     [rsp+0B8h+var_70], rdx
0x18001a24b  mov     edx, 2Bh ; '+'; MessageFlags
0x18001a250  mov     [rsp+0B8h+var_78], rcx
0x18001a255  mov     rcx, r14; LoggerHandle
0x18001a258  mov     [rsp+0B8h+var_80], rbp
0x18001a25d  mov     [rsp+0B8h+var_88], rdi
0x18001a262  mov     [rsp+0B8h+var_90], rax
0x18001a267  mov     [rsp+0B8h+var_98], rbx
0x18001a26c  call    cs:__imp_TraceMessage
0x18001a272  add     rsp, 80h
0x18001a279  pop     r15
0x18001a27b  pop     r14
0x18001a27d  pop     r12
0x18001a27f  pop     rdi
0x18001a280  pop     rsi
0x18001a281  pop     rbp
0x18001a282  pop     rbx
0x18001a283  retn
```
