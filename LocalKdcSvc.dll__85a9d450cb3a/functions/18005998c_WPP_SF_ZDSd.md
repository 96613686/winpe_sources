# WPP_SF_ZDSd

- ea: `0x18005998c`
- end: `0x180059ab5`
- name: `WPP_SF_ZDSd`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180058454`

## callees

- `0x18005998c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180059a9a`
- `ntdll!EtwTraceMessage` at `0x180059a9a`

## string_xrefs

- `0x1800599a6`: `onecore\ds\security\protocols\kerberos\server\refer.cxx`

## pseudocode

```c
__int64 WPP_SF_ZDSd(__int64 a1, __int64 a2, __int64 a3, int *a4, ...)
{
  __int64 v4; // rax
  __int64 v6; // r10
  const wchar_t **v7; // rax
  __int64 v8; // rcx
  const wchar_t *v9; // rdx
  const wchar_t *v10; // r8
  int v12[4]; // [rsp+80h] [rbp-18h] BYREF
  va_list va; // [rsp+C0h] [rbp+28h] BYREF

  va_start(va, a4);
  v12[0] = 1306;
  v4 = -1;
  do
    ++v4;
  while ( aOnecoreDsSecur_1[v4] );
  v6 = 2 * v4 + 2;
  v7 = (const wchar_t **)(a4 + 2);
  if ( a4 && *v7 )
  {
    if ( *(_WORD *)a4 )
      v8 = *(unsigned __int16 *)a4;
    else
      v8 = 16;
    v9 = *v7;
LABEL_11:
    v10 = L"(empty)";
    if ( *(_WORD *)a4 )
      v10 = v9;
    goto LABEL_16;
  }
  v8 = 14;
  if ( a4 )
  {
    v9 = *v7;
    if ( *v7 )
      goto LABEL_11;
  }
  v10 = L"(null)";
  if ( !a4 || !*v7 )
  {
    a4 = &dword_1800A1AEC;
    return EtwTraceMessage(
             a1,
             43,
             WPP_e5b28892b89032293cacd9153c3db07e_Traceguids,
             26,
             a4,
             2,
             v10,
             v8,
             va,
             4,
             aOnecoreDsSecur_1,
             v6,
             v12,
             4,
             0);
  }
LABEL_16:
  if ( !*(_WORD *)a4 )
    a4 = (int *)byte_1800A1AE8;
  return EtwTraceMessage(
           a1,
           43,
           WPP_e5b28892b89032293cacd9153c3db07e_Traceguids,
           26,
           a4,
           2,
           v10,
           v8,
           va,
           4,
           aOnecoreDsSecur_1,
           v6,
           v12,
           4,
           0);
}

```

## disassembly

```asm
0x18005998c  mov     rax, rsp
0x18005998f  mov     [rax+8], rbx
0x180059993  mov     [rax+10h], rsi
0x180059997  push    rdi
0x180059998  sub     rsp, 90h
0x18005999f  mov     dword ptr [rax-18h], 51Ah
0x1800599a6  lea     rsi, aOnecoreDsSecur_1; "onecore\\ds\\security\\protocols\\kerbe"...
0x1800599ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800599b1  mov     r11, rcx
0x1800599b4  xor     edi, edi
0x1800599b6  inc     rax
0x1800599b9  cmp     [rsi+rax*2], di
0x1800599bd  jnz     short loc_1800599B6
0x1800599bf  lea     r10, ds:2[rax*2]
0x1800599c7  lea     rax, [r9+8]
0x1800599cb  test    r9, r9
0x1800599ce  jz      short loc_1800599EB
0x1800599d0  cmp     [rax], rdi
0x1800599d3  jz      short loc_1800599EB
0x1800599d5  cmp     [r9], di
0x1800599d9  jz      short loc_1800599E1
0x1800599db  movzx   ecx, word ptr [r9]
0x1800599df  jmp     short loc_1800599E6
0x1800599e1  mov     ecx, 10h
0x1800599e6  mov     rdx, [rax]
0x1800599e9  jmp     short loc_1800599FD
0x1800599eb  mov     ecx, 0Eh
0x1800599f0  test    r9, r9
0x1800599f3  jz      short loc_180059A0E
0x1800599f5  mov     rdx, [rax]
0x1800599f8  test    rdx, rdx
0x1800599fb  jz      short loc_180059A0E
0x1800599fd  cmp     [r9], di
0x180059a01  lea     r8, aEmpty; "(empty)"
0x180059a08  cmovnz  r8, rdx
0x180059a0c  jmp     short loc_180059A1F
0x180059a0e  lea     r8, aNull_0; "(null)"
0x180059a15  test    r9, r9
0x180059a18  jz      short loc_180059A30
0x180059a1a  cmp     [rax], rdi
0x180059a1d  jz      short loc_180059A30
0x180059a1f  cmp     [r9], di
0x180059a23  lea     rax, byte_1800A1AE8
0x180059a2a  cmovz   r9, rax
0x180059a2e  jmp     short loc_180059A37
0x180059a30  lea     r9, dword_1800A1AEC
0x180059a37  mov     [rsp+98h+var_28], rdi
0x180059a3c  lea     rax, [rsp+98h+var_18]
0x180059a44  mov     ebx, 1Ah
0x180059a49  lea     edx, [rbx-16h]
0x180059a4c  mov     [rsp+98h+var_30], rdx
0x180059a51  mov     [rsp+98h+var_38], rax
0x180059a56  lea     rax, [rsp+98h+arg_20]
0x180059a5e  mov     [rsp+98h+var_40], r10
0x180059a63  mov     [rsp+98h+var_48], rsi
0x180059a68  mov     [rsp+98h+var_50], rdx
0x180059a6d  lea     edx, [rbx+11h]
0x180059a70  mov     [rsp+98h+var_58], rax
0x180059a75  mov     [rsp+98h+var_60], rcx
0x180059a7a  mov     rcx, r11
0x180059a7d  mov     [rsp+98h+var_68], r8
0x180059a82  lea     r8, WPP_e5b28892b89032293cacd9153c3db07e_Traceguids
0x180059a89  mov     [rsp+98h+var_70], 2
0x180059a92  mov     [rsp+98h+var_78], r9
0x180059a97  mov     r9d, ebx
0x180059a9a  call    cs:__imp_EtwTraceMessage
0x180059aa0  lea     r11, [rsp+98h+var_8]
0x180059aa8  mov     rbx, [r11+10h]
0x180059aac  mov     rsi, [r11+18h]
0x180059ab0  mov     rsp, r11
0x180059ab3  pop     rdi
0x180059ab4  retn
```
