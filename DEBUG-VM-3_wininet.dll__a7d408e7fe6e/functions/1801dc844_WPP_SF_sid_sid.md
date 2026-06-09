# WPP_SF__sid__sid_

- ea: `0x1801dc844`
- end: `0x1801dc911`
- name: `WPP_SF__sid__sid_`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801ab560`

## callees

- `0x1800fb5c0`
- `0x1801dc844`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801dc865`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801dc886`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801dc89f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801dc8be`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801dc865`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801dc886`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801dc89f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801dc8be`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801dc872`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801dc8ac`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801dc872`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801dc8ac`

## pseudocode

```c
__int64 __fastcall WPP_SF__sid__sid_(__int64 a1, __int64 a2, __int64 a3, char *a4, char *pSid)
{
  const char *v5; // rdi
  DWORD v7; // esi
  DWORD LengthSid; // ebp

  v5 = pSid;
  v7 = 5;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
  }
  else
  {
    LengthSid = 5;
    if ( !pSid )
    {
LABEL_6:
      v5 = "NULL";
      goto LABEL_7;
    }
  }
  if ( !IsValidSid(pSid) )
    goto LABEL_6;
LABEL_7:
  if ( !a4 )
    goto LABEL_11;
  if ( IsValidSid(a4) )
    v7 = GetLengthSid(a4);
  if ( !IsValidSid(a4) )
LABEL_11:
    a4 = "NULL";
  return FastWppTraceMessage(1036, 24, &WPP_f7214b1b865b30b0b4de32fceef4bdb0_Traceguids, a4, v7, v5, LengthSid, 0);
}

```

## disassembly

```asm
0x1801dc844  push    rbx
0x1801dc846  push    rbp
0x1801dc847  push    rsi
0x1801dc848  push    rdi
0x1801dc849  sub     rsp, 48h
0x1801dc84d  mov     rdi, [rsp+68h+pSid]
0x1801dc855  mov     rbx, r9
0x1801dc858  mov     esi, 5
0x1801dc85d  test    rdi, rdi
0x1801dc860  jz      short loc_1801DC87C
0x1801dc862  mov     rcx, rdi; pSid
0x1801dc865  call    cs:__imp_IsValidSid
0x1801dc86b  test    eax, eax
0x1801dc86d  jz      short loc_1801DC87C
0x1801dc86f  mov     rcx, rdi; pSid
0x1801dc872  call    cs:__imp_GetLengthSid
0x1801dc878  mov     ebp, eax
0x1801dc87a  jmp     short loc_1801DC883
0x1801dc87c  mov     ebp, esi
0x1801dc87e  test    rdi, rdi
0x1801dc881  jz      short loc_1801DC890
0x1801dc883  mov     rcx, rdi; pSid
0x1801dc886  call    cs:__imp_IsValidSid
0x1801dc88c  test    eax, eax
0x1801dc88e  jnz     short loc_1801DC897
0x1801dc890  lea     rdi, aNull_0; "NULL"
0x1801dc897  test    rbx, rbx
0x1801dc89a  jz      short loc_1801DC8C8
0x1801dc89c  mov     rcx, rbx; pSid
0x1801dc89f  call    cs:__imp_IsValidSid
0x1801dc8a5  test    eax, eax
0x1801dc8a7  jz      short loc_1801DC8B6
0x1801dc8a9  mov     rcx, rbx; pSid
0x1801dc8ac  call    cs:__imp_GetLengthSid
0x1801dc8b2  mov     esi, eax
0x1801dc8b4  jmp     short loc_1801DC8BB
0x1801dc8b6  test    rbx, rbx
0x1801dc8b9  jz      short loc_1801DC8C8
0x1801dc8bb  mov     rcx, rbx; pSid
0x1801dc8be  call    cs:__imp_IsValidSid
0x1801dc8c4  test    eax, eax
0x1801dc8c6  jnz     short loc_1801DC8CF
0x1801dc8c8  lea     rbx, aNull_0; "NULL"
0x1801dc8cf  mov     [rsp+68h+var_30], 0
0x1801dc8d8  lea     r8, WPP_f7214b1b865b30b0b4de32fceef4bdb0_Traceguids
0x1801dc8df  mov     ecx, esi
0x1801dc8e1  mov     r10d, 40Ch
0x1801dc8e7  mov     eax, ebp
0x1801dc8e9  mov     edx, 18h
0x1801dc8ee  mov     [rsp+68h+var_38], rax
0x1801dc8f3  mov     r9, rbx
0x1801dc8f6  mov     [rsp+68h+var_40], rdi
0x1801dc8fb  mov     [rsp+68h+var_48], rcx
0x1801dc900  mov     ecx, r10d
0x1801dc903  call    FastWppTraceMessage
0x1801dc908  add     rsp, 48h
0x1801dc90c  pop     rdi
0x1801dc90d  pop     rsi
0x1801dc90e  pop     rbp
0x1801dc90f  pop     rbx
0x1801dc910  retn
```
