# WPP_SF_S_sid_

- ea: `0x1800831a8`
- end: `0x180083276`
- name: `WPP_SF_S_sid_`
- size: `206`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004b460`
- `0x180082668`

## callees

- `0x1800831a8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800831de`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800831de`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800831d1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800831f5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800831d1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800831f5`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180083263`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180083263`

## pseudocode

```c
ULONG __fastcall WPP_SF_S_sid_(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, const wchar_t *a4, char *pSid)
{
  const char *v5; // rbx
  DWORD LengthSid; // esi
  __int64 v10; // rax
  __int64 v11; // rcx

  v5 = pSid;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
    goto LABEL_5;
  }
  LengthSid = 5;
  if ( pSid )
  {
LABEL_5:
    if ( IsValidSid(pSid) )
      goto LABEL_7;
  }
  v5 = "NULL";
LABEL_7:
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
           0);
}

```

## disassembly

```asm
0x1800831a8  push    rbx
0x1800831aa  push    rbp
0x1800831ab  push    rsi
0x1800831ac  push    rdi
0x1800831ad  push    r14
0x1800831af  push    r15
0x1800831b1  sub     rsp, 58h
0x1800831b5  mov     rbx, [rsp+88h+pSid]
0x1800831bd  xor     r15d, r15d
0x1800831c0  movzx   ebp, dx
0x1800831c3  mov     rdi, r9
0x1800831c6  mov     r14, rcx
0x1800831c9  test    rbx, rbx
0x1800831cc  jz      short loc_1800831E8
0x1800831ce  mov     rcx, rbx; pSid
0x1800831d1  call    cs:__imp_IsValidSid
0x1800831d7  test    eax, eax
0x1800831d9  jz      short loc_1800831E8
0x1800831db  mov     rcx, rbx; pSid
0x1800831de  call    cs:__imp_GetLengthSid
0x1800831e4  mov     esi, eax
0x1800831e6  jmp     short loc_1800831F2
0x1800831e8  mov     esi, 5
0x1800831ed  test    rbx, rbx
0x1800831f0  jz      short loc_1800831FF
0x1800831f2  mov     rcx, rbx; pSid
0x1800831f5  call    cs:__imp_IsValidSid
0x1800831fb  test    eax, eax
0x1800831fd  jnz     short loc_180083206
0x1800831ff  lea     rbx, aNull; "NULL"
0x180083206  test    rdi, rdi
0x180083209  jz      short loc_180083223
0x18008320b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008320f  inc     rax
0x180083212  cmp     [rdi+rax*2], r15w
0x180083217  jnz     short loc_18008320F
0x180083219  lea     rcx, ds:2[rax*2]
0x180083221  jmp     short loc_180083228
0x180083223  mov     ecx, 0Ah
0x180083228  mov     [rsp+88h+var_48], r15
0x18008322d  lea     rdx, aNull_0; "NULL"
0x180083234  mov     eax, esi
0x180083236  lea     r8, WPP_e6b615a7d18a3fcf430735eb063d161f_Traceguids; MessageGuid
0x18008323d  mov     [rsp+88h+var_50], rax
0x180083242  test    rdi, rdi
0x180083245  mov     [rsp+88h+var_58], rbx
0x18008324a  mov     r9d, ebp; MessageNumber
0x18008324d  mov     [rsp+88h+var_60], rcx
0x180083252  cmovz   rdi, rdx
0x180083256  mov     rcx, r14; LoggerHandle
0x180083259  mov     [rsp+88h+var_68], rdi
0x18008325e  mov     edx, 2Bh ; '+'; MessageFlags
0x180083263  call    cs:__imp_TraceMessage
0x180083269  add     rsp, 58h
0x18008326d  pop     r15
0x18008326f  pop     r14
0x180083271  pop     rdi
0x180083272  pop     rsi
0x180083273  pop     rbp
0x180083274  pop     rbx
0x180083275  retn
```
