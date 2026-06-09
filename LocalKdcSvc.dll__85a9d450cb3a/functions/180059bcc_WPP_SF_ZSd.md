# WPP_SF_ZSd

- ea: `0x180059bcc`
- end: `0x180059cd7`
- name: `WPP_SF_ZSd`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180058454`

## callees

- `0x180059bcc`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180059cbf`
- `ntdll!EtwTraceMessage` at `0x180059cbf`

## string_xrefs

- `0x180059be5`: `onecore\ds\security\protocols\kerberos\server\refer.cxx`

## pseudocode

```c
__int64 WPP_SF_ZSd(__int64 a1, unsigned __int16 a2, _DWORD a3, int *a4, __int64 a5, ...)
{
  __int64 v5; // rax
  unsigned int v6; // r11d
  __int64 v8; // r10
  const wchar_t **v9; // rax
  __int64 v10; // rcx
  const wchar_t *v11; // rdx
  const wchar_t *v12; // r8
  __int64 v14; // [rsp+68h] [rbp-10h]
  __int64 v15; // [rsp+70h] [rbp-8h]
  va_list va; // [rsp+A8h] [rbp+30h] BYREF

  va_start(va, a5);
  v5 = -1;
  v6 = a2;
  do
    ++v5;
  while ( aOnecoreDsSecur_1[v5] );
  v8 = 2 * v5 + 2;
  v9 = (const wchar_t **)(a4 + 2);
  if ( a4 && *v9 )
  {
    if ( *(_WORD *)a4 )
      v10 = *(unsigned __int16 *)a4;
    else
      v10 = 16;
    v11 = *v9;
LABEL_11:
    v12 = L"(empty)";
    if ( *(_WORD *)a4 )
      v12 = v11;
    goto LABEL_16;
  }
  v10 = 14;
  if ( a4 )
  {
    v11 = *v9;
    if ( *v9 )
      goto LABEL_11;
  }
  v12 = L"(null)";
  if ( !a4 || !*v9 )
  {
    a4 = &dword_1800A1AEC;
    return EtwTraceMessage(
             a1,
             43,
             WPP_e5b28892b89032293cacd9153c3db07e_Traceguids,
             v6,
             a4,
             2,
             v12,
             v10,
             aOnecoreDsSecur_1,
             v8,
             va,
             4,
             0,
             v14,
             v15);
  }
LABEL_16:
  if ( !*(_WORD *)a4 )
    a4 = (int *)byte_1800A1AE8;
  return EtwTraceMessage(
           a1,
           43,
           WPP_e5b28892b89032293cacd9153c3db07e_Traceguids,
           v6,
           a4,
           2,
           v12,
           v10,
           aOnecoreDsSecur_1,
           v8,
           va,
           4,
           0,
           v14,
           v15);
}

```

## disassembly

```asm
0x180059bcc  mov     [rsp+arg_0], rbx
0x180059bd1  mov     [rsp+arg_8], rsi
0x180059bd6  push    rdi
0x180059bd7  sub     rsp, 70h
0x180059bdb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180059bdf  movzx   r11d, dx
0x180059be3  xor     edi, edi
0x180059be5  lea     rsi, aOnecoreDsSecur_1; "onecore\\ds\\security\\protocols\\kerbe"...
0x180059bec  mov     rbx, rcx
0x180059bef  inc     rax
0x180059bf2  cmp     [rsi+rax*2], di
0x180059bf6  jnz     short loc_180059BEF
0x180059bf8  lea     r10, ds:2[rax*2]
0x180059c00  lea     rax, [r9+8]
0x180059c04  test    r9, r9
0x180059c07  jz      short loc_180059C24
0x180059c09  cmp     [rax], rdi
0x180059c0c  jz      short loc_180059C24
0x180059c0e  cmp     [r9], di
0x180059c12  jz      short loc_180059C1A
0x180059c14  movzx   ecx, word ptr [r9]
0x180059c18  jmp     short loc_180059C1F
0x180059c1a  mov     ecx, 10h
0x180059c1f  mov     rdx, [rax]
0x180059c22  jmp     short loc_180059C36
0x180059c24  mov     ecx, 0Eh
0x180059c29  test    r9, r9
0x180059c2c  jz      short loc_180059C47
0x180059c2e  mov     rdx, [rax]
0x180059c31  test    rdx, rdx
0x180059c34  jz      short loc_180059C47
0x180059c36  cmp     [r9], di
0x180059c3a  lea     r8, aEmpty; "(empty)"
0x180059c41  cmovnz  r8, rdx
0x180059c45  jmp     short loc_180059C58
0x180059c47  lea     r8, aNull_0; "(null)"
0x180059c4e  test    r9, r9
0x180059c51  jz      short loc_180059C69
0x180059c53  cmp     [rax], rdi
0x180059c56  jz      short loc_180059C69
0x180059c58  cmp     [r9], di
0x180059c5c  lea     rax, byte_1800A1AE8
0x180059c63  cmovz   r9, rax
0x180059c67  jmp     short loc_180059C70
0x180059c69  lea     r9, dword_1800A1AEC
0x180059c70  mov     [rsp+78h+var_18], rdi
0x180059c75  lea     rax, [rsp+78h+arg_28]
0x180059c7d  mov     [rsp+78h+var_20], 4
0x180059c86  mov     edx, 2Bh ; '+'
0x180059c8b  mov     [rsp+78h+var_28], rax
0x180059c90  mov     [rsp+78h+var_30], r10
0x180059c95  mov     [rsp+78h+var_38], rsi
0x180059c9a  mov     [rsp+78h+var_40], rcx
0x180059c9f  mov     rcx, rbx
0x180059ca2  mov     [rsp+78h+var_48], r8
0x180059ca7  lea     r8, WPP_e5b28892b89032293cacd9153c3db07e_Traceguids
0x180059cae  mov     [rsp+78h+var_50], 2
0x180059cb7  mov     [rsp+78h+var_58], r9
0x180059cbc  mov     r9d, r11d
0x180059cbf  call    cs:__imp_EtwTraceMessage
0x180059cc5  lea     r11, [rsp+78h+var_8]
0x180059cca  mov     rbx, [r11+10h]
0x180059cce  mov     rsi, [r11+18h]
0x180059cd2  mov     rsp, r11
0x180059cd5  pop     rdi
0x180059cd6  retn
```
