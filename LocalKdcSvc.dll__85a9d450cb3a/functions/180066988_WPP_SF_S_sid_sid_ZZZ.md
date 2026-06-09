# WPP_SF_S_sid__sid_ZZZ

- ea: `0x180066988`
- end: `0x180066d0a`
- name: `WPP_SF_S_sid__sid_ZZZ`
- size: `898`
- prototype: `__int64 __fastcall(int, int, int, int, PSID, PSID pSid, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005cdac`

## callees

- `0x180066988`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180066b7c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180066bc6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180066b7c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180066bc6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180066b6c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180066b92`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180066bb6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180066bd9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180066b6c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180066b92`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180066bb6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180066bd9`
- `ntdll!EtwTraceMessage` at `0x180066ce9`
- `ntdll!EtwTraceMessage` at `0x180066ce9`

## pseudocode

```c
__int64 __fastcall WPP_SF_S_sid__sid_ZZZ(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        char *a5,
        char *pSid,
        int *a7,
        int *a8,
        _WORD *a9)
{
  int *v9; // r14
  const wchar_t *v11; // r8
  __int64 v13; // rdx
  const wchar_t **v14; // rax
  const wchar_t *v15; // rcx
  const wchar_t *v16; // r9
  const wchar_t **v17; // rax
  const wchar_t *v18; // rcx
  const wchar_t *v19; // r13
  const wchar_t **v20; // rax
  const wchar_t *v21; // rcx
  const char *v22; // rdi
  DWORD v23; // r15d
  DWORD LengthSid; // r12d
  const char *v25; // rbx
  const wchar_t *v26; // r9
  __int64 v27; // rax
  __int64 v28; // rdx
  const wchar_t *v30; // [rsp+C0h] [rbp-48h]
  __int64 v32; // [rsp+120h] [rbp+18h]
  __int64 v34; // [rsp+140h] [rbp+38h]
  __int64 v35; // [rsp+148h] [rbp+40h]
  const wchar_t *v36; // [rsp+150h] [rbp+48h]

  v9 = (int *)a9;
  v11 = L"(empty)";
  v13 = 16;
  v35 = 16;
  v14 = (const wchar_t **)(a9 + 4);
  if ( a9 && *v14 )
  {
    if ( *a9 )
      v32 = (unsigned __int16)*a9;
    else
      v32 = 16;
    v15 = *v14;
    goto LABEL_9;
  }
  v32 = 14;
  if ( a9 )
  {
    v15 = *v14;
    if ( *v14 )
    {
LABEL_9:
      v16 = L"(empty)";
      if ( *a9 )
        v16 = v15;
      v36 = v16;
      goto LABEL_15;
    }
  }
  else
  {
    v32 = 14;
  }
  v36 = L"(null)";
  if ( !v9 || !*v14 )
  {
    v9 = &dword_1800A1AEC;
    goto LABEL_19;
  }
LABEL_15:
  if ( !*(_WORD *)v9 )
    v9 = (int *)byte_1800A1AE8;
LABEL_19:
  v17 = (const wchar_t **)(a8 + 2);
  if ( a8 && *v17 )
  {
    if ( *(_WORD *)a8 )
      v13 = *(unsigned __int16 *)a8;
    v18 = *v17;
    v34 = v13;
    goto LABEL_26;
  }
  v34 = 14;
  if ( a8 )
  {
    v18 = *v17;
    if ( *v17 )
    {
LABEL_26:
      v19 = L"(empty)";
      if ( *(_WORD *)a8 )
        v19 = v18;
      goto LABEL_32;
    }
  }
  else
  {
    v34 = 14;
  }
  v19 = L"(null)";
  if ( !a8 || !*v17 )
  {
    a8 = &dword_1800A1AEC;
    goto LABEL_36;
  }
LABEL_32:
  if ( !*(_WORD *)a8 )
    a8 = (int *)byte_1800A1AE8;
LABEL_36:
  v20 = (const wchar_t **)(a7 + 2);
  if ( a7 && *v20 )
  {
    if ( *(_WORD *)a7 )
      v35 = *(unsigned __int16 *)a7;
    v21 = *v20;
    goto LABEL_43;
  }
  v35 = 14;
  if ( a7 )
  {
    v21 = *v20;
    if ( *v20 )
    {
LABEL_43:
      if ( *(_WORD *)a7 )
        v11 = v21;
      v30 = v11;
      goto LABEL_49;
    }
  }
  else
  {
    v35 = 14;
  }
  v30 = L"(null)";
  if ( !a7 || !*v20 )
  {
    a7 = &dword_1800A1AEC;
    goto LABEL_53;
  }
LABEL_49:
  if ( !*(_WORD *)a7 )
    a7 = (int *)byte_1800A1AE8;
LABEL_53:
  v22 = pSid;
  v23 = 5;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
  }
  else
  {
    LengthSid = 5;
    if ( !pSid )
    {
LABEL_58:
      v22 = "NULL";
      goto LABEL_59;
    }
  }
  if ( !IsValidSid(pSid) )
    goto LABEL_58;
LABEL_59:
  v25 = a5;
  if ( !a5 )
    goto LABEL_63;
  if ( IsValidSid(a5) )
    v23 = GetLengthSid(a5);
  if ( !IsValidSid(a5) )
LABEL_63:
    v25 = "NULL";
  v26 = a4;
  if ( a4 )
  {
    v27 = -1;
    do
      ++v27;
    while ( a4[v27] );
    v28 = 2 * v27 + 2;
  }
  else
  {
    v28 = 10;
  }
  if ( !a4 )
    v26 = L"NULL";
  return EtwTraceMessage(
           a1,
           43,
           WPP_b168486f65343579948eb0cc9cf7c178_Traceguids,
           174,
           v26,
           v28,
           v25,
           v23,
           v22,
           LengthSid,
           a7,
           2,
           v30,
           v35,
           a8,
           2,
           v19,
           v34,
           v9,
           2,
           v36,
           v32,
           0);
}

```

## disassembly

```asm
0x180066988  mov     rax, rsp
0x18006698b  mov     [rax+10h], rbx
0x18006698f  mov     [rax+20h], r9
0x180066993  mov     [rax+18h], r8
0x180066997  mov     [rax+8], rcx
0x18006699b  push    rbp
0x18006699c  push    rsi
0x18006699d  push    rdi
0x18006699e  push    r12
0x1800669a0  push    r13
0x1800669a2  push    r14
0x1800669a4  push    r15
0x1800669a6  sub     rsp, 0D0h
0x1800669ad  mov     r14, [rsp+108h+arg_40]
0x1800669b5  lea     rbx, dword_1800A1AEC
0x1800669bc  mov     rbp, [rsp+108h+arg_38]
0x1800669c4  lea     r8, aEmpty; "(empty)"
0x1800669cb  mov     rsi, [rsp+108h+arg_30]
0x1800669d3  lea     r15, byte_1800A1AE8
0x1800669da  mov     edx, 10h
0x1800669df  lea     rdi, aNull_0; "(null)"
0x1800669e6  xor     r10d, r10d
0x1800669e9  mov     [rsp+108h+arg_38], rdx
0x1800669f1  lea     rax, [r14+8]
0x1800669f5  lea     r11d, [rdx-2]
0x1800669f9  test    r14, r14
0x1800669fc  jz      short loc_180066A27
0x1800669fe  cmp     [rax], r10
0x180066a01  jz      short loc_180066A27
0x180066a03  cmp     [r14], r10w
0x180066a07  jz      short loc_180066A1A
0x180066a09  movzx   r10d, word ptr [r14]
0x180066a0d  mov     [rsp+108h+arg_10], r10
0x180066a15  xor     r10d, r10d
0x180066a18  jmp     short loc_180066A22
0x180066a1a  mov     [rsp+108h+arg_10], rdx
0x180066a22  mov     rcx, [rax]
0x180066a25  jmp     short loc_180066A3C
0x180066a27  mov     [rsp+108h+arg_10], r11
0x180066a2f  test    r14, r14
0x180066a32  jz      short loc_180066A51
0x180066a34  mov     rcx, [rax]
0x180066a37  test    rcx, rcx
0x180066a3a  jz      short loc_180066A59
0x180066a3c  cmp     [r14], r10w
0x180066a40  mov     r9, r8
0x180066a43  cmovnz  r9, rcx
0x180066a47  mov     [rsp+108h+arg_40], r9
0x180066a4f  jmp     short loc_180066A6B
0x180066a51  mov     [rsp+108h+arg_10], r11
0x180066a59  mov     [rsp+108h+arg_40], rdi
0x180066a61  test    r14, r14
0x180066a64  jz      short loc_180066A75
0x180066a66  cmp     [rax], r10
0x180066a69  jz      short loc_180066A75
0x180066a6b  cmp     [r14], r10w
0x180066a6f  cmovz   r14, r15
0x180066a73  jmp     short loc_180066A78
0x180066a75  mov     r14, rbx
0x180066a78  lea     rax, [rbp+8]
0x180066a7c  test    rbp, rbp
0x180066a7f  jz      short loc_180066A9E
0x180066a81  cmp     [rax], r10
0x180066a84  jz      short loc_180066A9E
0x180066a86  cmp     [rbp+0], r10w
0x180066a8b  jz      short loc_180066A91
0x180066a8d  movzx   edx, word ptr [rbp+0]
0x180066a91  mov     rcx, [rax]
0x180066a94  mov     [rsp+108h+arg_30], rdx
0x180066a9c  jmp     short loc_180066AB3
0x180066a9e  mov     [rsp+108h+arg_30], r11
0x180066aa6  test    rbp, rbp
0x180066aa9  jz      short loc_180066AC1
0x180066aab  mov     rcx, [rax]
0x180066aae  test    rcx, rcx
0x180066ab1  jz      short loc_180066AC9
0x180066ab3  cmp     [rbp+0], r10w
0x180066ab8  mov     r13, r8
0x180066abb  cmovnz  r13, rcx
0x180066abf  jmp     short loc_180066AD6
0x180066ac1  mov     [rsp+108h+arg_30], r11
0x180066ac9  mov     r13, rdi
0x180066acc  test    rbp, rbp
0x180066acf  jz      short loc_180066AE1
0x180066ad1  cmp     [rax], r10
0x180066ad4  jz      short loc_180066AE1
0x180066ad6  cmp     [rbp+0], r10w
0x180066adb  cmovz   rbp, r15
0x180066adf  jmp     short loc_180066AE4
0x180066ae1  mov     rbp, rbx
0x180066ae4  lea     rax, [rsi+8]
0x180066ae8  test    rsi, rsi
0x180066aeb  jz      short loc_180066B08
0x180066aed  cmp     [rax], r10
0x180066af0  jz      short loc_180066B08
0x180066af2  cmp     [rsi], r10w
0x180066af6  jz      short loc_180066B03
0x180066af8  movzx   edx, word ptr [rsi]
0x180066afb  mov     [rsp+108h+arg_38], rdx
0x180066b03  mov     rcx, [rax]
0x180066b06  jmp     short loc_180066B1D
0x180066b08  mov     [rsp+108h+arg_38], r11
0x180066b10  test    rsi, rsi
0x180066b13  jz      short loc_180066B2F
0x180066b15  mov     rcx, [rax]
0x180066b18  test    rcx, rcx
0x180066b1b  jz      short loc_180066B37
0x180066b1d  cmp     [rsi], r10w
0x180066b21  cmovnz  r8, rcx
0x180066b25  mov     [rsp+108h+var_48], r8
0x180066b2d  jmp     short loc_180066B49
0x180066b2f  mov     [rsp+108h+arg_38], r11
0x180066b37  mov     [rsp+108h+var_48], rdi
0x180066b3f  test    rsi, rsi
0x180066b42  jz      short loc_180066B53
0x180066b44  cmp     [rax], r10
0x180066b47  jz      short loc_180066B53
0x180066b49  cmp     [rsi], r10w
0x180066b4d  cmovz   rsi, r15
0x180066b51  jmp     short loc_180066B56
0x180066b53  mov     rsi, rbx
0x180066b56  mov     rdi, [rsp+108h+pSid]
0x180066b5e  mov     r15d, 5
0x180066b64  test    rdi, rdi
0x180066b67  jz      short loc_180066B87
0x180066b69  mov     rcx, rdi; pSid
0x180066b6c  call    cs:__imp_IsValidSid
0x180066b72  xor     r10d, r10d
0x180066b75  test    eax, eax
0x180066b77  jz      short loc_180066B87
0x180066b79  mov     rcx, rdi; pSid
0x180066b7c  call    cs:__imp_GetLengthSid
0x180066b82  mov     r12d, eax
0x180066b85  jmp     short loc_180066B8F
0x180066b87  mov     r12d, r15d
0x180066b8a  test    rdi, rdi
0x180066b8d  jz      short loc_180066B9F
0x180066b8f  mov     rcx, rdi; pSid
0x180066b92  call    cs:__imp_IsValidSid
0x180066b98  xor     r10d, r10d
0x180066b9b  test    eax, eax
0x180066b9d  jnz     short loc_180066BA6
0x180066b9f  lea     rdi, aNull; "NULL"
0x180066ba6  mov     rbx, [rsp+108h+arg_20]
0x180066bae  test    rbx, rbx
0x180066bb1  jz      short loc_180066BE6
0x180066bb3  mov     rcx, rbx; pSid
0x180066bb6  call    cs:__imp_IsValidSid
0x180066bbc  xor     r10d, r10d
0x180066bbf  test    eax, eax
0x180066bc1  jz      short loc_180066BD1
0x180066bc3  mov     rcx, rbx; pSid
0x180066bc6  call    cs:__imp_GetLengthSid
0x180066bcc  mov     r15d, eax
0x180066bcf  jmp     short loc_180066BD6
0x180066bd1  test    rbx, rbx
0x180066bd4  jz      short loc_180066BE6
0x180066bd6  mov     rcx, rbx; pSid
0x180066bd9  call    cs:__imp_IsValidSid
0x180066bdf  xor     r10d, r10d
0x180066be2  test    eax, eax
0x180066be4  jnz     short loc_180066BED
0x180066be6  lea     rbx, aNull; "NULL"
0x180066bed  mov     r9, [rsp+108h+arg_18]
0x180066bf5  test    r9, r9
0x180066bf8  jz      short loc_180066C12
0x180066bfa  or      rax, 0FFFFFFFFFFFFFFFFh
0x180066bfe  inc     rax
0x180066c01  cmp     [r9+rax*2], r10w
0x180066c06  jnz     short loc_180066BFE
0x180066c08  lea     rdx, ds:2[rax*2]
0x180066c10  jmp     short loc_180066C17
0x180066c12  mov     edx, 0Ah
0x180066c17  mov     [rsp+108h+var_58], r10
0x180066c1f  lea     r8, aNull_1; "NULL"
0x180066c26  mov     r10d, 2
0x180066c2c  mov     eax, r12d
0x180066c2f  test    r9, r9
0x180066c32  mov     ecx, r15d
0x180066c35  mov     r11d, 0AEh
0x180066c3b  cmovz   r9, r8
0x180066c3f  mov     r8, [rsp+108h+arg_10]
0x180066c47  mov     [rsp+108h+var_60], r8
0x180066c4f  mov     r8, [rsp+108h+arg_40]
0x180066c57  mov     [rsp+108h+var_68], r8
0x180066c5f  mov     r8, [rsp+108h+arg_30]
0x180066c67  mov     [rsp+108h+var_70], r10
0x180066c6f  mov     [rsp+108h+var_78], r14
0x180066c77  mov     [rsp+108h+var_80], r8
0x180066c7f  mov     r8, [rsp+108h+arg_38]
0x180066c87  mov     [rsp+108h+var_88], r13
0x180066c8f  mov     [rsp+108h+var_90], r10
0x180066c94  mov     [rsp+108h+var_98], rbp
0x180066c99  mov     [rsp+108h+var_A0], r8
0x180066c9e  mov     r8, [rsp+108h+var_48]
0x180066ca6  mov     [rsp+108h+var_A8], r8
0x180066cab  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x180066cb2  mov     [rsp+108h+var_B0], r10
0x180066cb7  mov     [rsp+108h+var_B8], rsi
0x180066cbc  mov     [rsp+108h+var_C0], rax
0x180066cc1  mov     [rsp+108h+var_C8], rdi
0x180066cc6  mov     [rsp+108h+var_D0], rcx
0x180066ccb  mov     rcx, [rsp+108h+arg_0]
0x180066cd3  mov     [rsp+108h+var_D8], rbx
0x180066cd8  mov     [rsp+108h+var_E0], rdx
0x180066cdd  lea     edx, [r10+29h]
0x180066ce1  mov     [rsp+108h+var_E8], r9
0x180066ce6  mov     r9d, r11d
0x180066ce9  call    cs:__imp_EtwTraceMessage
0x180066cef  mov     rbx, [rsp+108h+arg_8]
0x180066cf7  add     rsp, 0D0h
0x180066cfe  pop     r15
0x180066d00  pop     r14
0x180066d02  pop     r13
0x180066d04  pop     r12
0x180066d06  pop     rdi
0x180066d07  pop     rsi
0x180066d08  pop     rbp
0x180066d09  retn
```
