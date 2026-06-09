# WPP_SF_ZDsd

- ea: `0x180059abc`
- end: `0x180059bc3`
- name: `WPP_SF_ZDsd`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180057fb4`

## callees

- `0x180059abc`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180059bb4`
- `ntdll!EtwTraceMessage` at `0x180059bb4`

## string_xrefs

- `0x180059b64`: `onecore\ds\security\protocols\kerberos\server\refer.cxx`

## pseudocode

```c
__int64 WPP_SF_ZDsd(__int64 a1, __int64 a2, __int64 a3, int *a4, ...)
{
  const wchar_t **v4; // rax
  __int64 v6; // rcx
  const wchar_t *v7; // rdx
  const wchar_t *v8; // r8
  int v10[6]; // [rsp+80h] [rbp-18h] BYREF
  va_list va; // [rsp+C0h] [rbp+28h] BYREF

  va_start(va, a4);
  v10[0] = 799;
  v4 = (const wchar_t **)(a4 + 2);
  if ( a4 && *v4 )
  {
    if ( *(_WORD *)a4 )
      v6 = *(unsigned __int16 *)a4;
    else
      v6 = 16;
    v7 = *v4;
LABEL_9:
    v8 = L"(empty)";
    if ( *(_WORD *)a4 )
      v8 = v7;
    goto LABEL_14;
  }
  v6 = 14;
  if ( a4 )
  {
    v7 = *v4;
    if ( *v4 )
      goto LABEL_9;
  }
  v8 = L"(null)";
  if ( !a4 || !*v4 )
  {
    a4 = &dword_1800A1AEC;
    return EtwTraceMessage(
             a1,
             43,
             WPP_e5b28892b89032293cacd9153c3db07e_Traceguids,
             24,
             a4,
             2,
             v8,
             v6,
             va,
             4,
             "onecore\\ds\\security\\protocols\\kerberos\\server\\refer.cxx",
             56,
             v10,
             4,
             0);
  }
LABEL_14:
  if ( !*(_WORD *)a4 )
    a4 = (int *)byte_1800A1AE8;
  return EtwTraceMessage(
           a1,
           43,
           WPP_e5b28892b89032293cacd9153c3db07e_Traceguids,
           24,
           a4,
           2,
           v8,
           v6,
           va,
           4,
           "onecore\\ds\\security\\protocols\\kerberos\\server\\refer.cxx",
           56,
           v10,
           4,
           0);
}

```

## disassembly

```asm
0x180059abc  mov     rax, rsp
0x180059abf  push    rbx
0x180059ac0  sub     rsp, 90h
0x180059ac7  xor     ebx, ebx
0x180059ac9  mov     dword ptr [rax-18h], 31Fh
0x180059ad0  lea     rax, [r9+8]
0x180059ad4  mov     r10, rcx
0x180059ad7  test    r9, r9
0x180059ada  jz      short loc_180059AF7
0x180059adc  cmp     [rax], rbx
0x180059adf  jz      short loc_180059AF7
0x180059ae1  cmp     [r9], bx
0x180059ae5  jz      short loc_180059AED
0x180059ae7  movzx   ecx, word ptr [r9]
0x180059aeb  jmp     short loc_180059AF2
0x180059aed  mov     ecx, 10h
0x180059af2  mov     rdx, [rax]
0x180059af5  jmp     short loc_180059B09
0x180059af7  mov     ecx, 0Eh
0x180059afc  test    r9, r9
0x180059aff  jz      short loc_180059B1A
0x180059b01  mov     rdx, [rax]
0x180059b04  test    rdx, rdx
0x180059b07  jz      short loc_180059B1A
0x180059b09  cmp     [r9], bx
0x180059b0d  lea     r8, aEmpty; "(empty)"
0x180059b14  cmovnz  r8, rdx
0x180059b18  jmp     short loc_180059B2B
0x180059b1a  lea     r8, aNull_0; "(null)"
0x180059b21  test    r9, r9
0x180059b24  jz      short loc_180059B3C
0x180059b26  cmp     [rax], rbx
0x180059b29  jz      short loc_180059B3C
0x180059b2b  cmp     [r9], bx
0x180059b2f  lea     rax, byte_1800A1AE8
0x180059b36  cmovz   r9, rax
0x180059b3a  jmp     short loc_180059B43
0x180059b3c  lea     r9, dword_1800A1AEC
0x180059b43  mov     [rsp+98h+var_28], rbx
0x180059b48  lea     rax, [rsp+98h+var_18]
0x180059b50  mov     r11d, 18h
0x180059b56  lea     edx, [r11-14h]
0x180059b5a  mov     [rsp+98h+var_30], rdx
0x180059b5f  mov     [rsp+98h+var_38], rax
0x180059b64  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\protocols\\kerbe"...
0x180059b6b  mov     [rsp+98h+var_40], 38h ; '8'
0x180059b74  mov     [rsp+98h+var_48], rax
0x180059b79  lea     rax, [rsp+98h+arg_20]
0x180059b81  mov     [rsp+98h+var_50], rdx
0x180059b86  lea     edx, [r11+13h]
0x180059b8a  mov     [rsp+98h+var_58], rax
0x180059b8f  mov     [rsp+98h+var_60], rcx
0x180059b94  mov     rcx, r10
0x180059b97  mov     [rsp+98h+var_68], r8
0x180059b9c  lea     r8, WPP_e5b28892b89032293cacd9153c3db07e_Traceguids
0x180059ba3  mov     [rsp+98h+var_70], 2
0x180059bac  mov     [rsp+98h+var_78], r9
0x180059bb1  mov     r9d, r11d
0x180059bb4  call    cs:__imp_EtwTraceMessage
0x180059bba  add     rsp, 90h
0x180059bc1  pop     rbx
0x180059bc2  retn
```
