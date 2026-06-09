# WPP_SF_DZSd

- ea: `0x1800597cc`
- end: `0x1800598fe`
- name: `WPP_SF_DZSd`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180058454`

## callees

- `0x1800597cc`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x1800598e3`
- `ntdll!EtwTraceMessage` at `0x1800598e3`

## string_xrefs

- `0x1800597ea`: `onecore\ds\security\protocols\kerberos\server\refer.cxx`

## pseudocode

```c
__int64 __fastcall WPP_SF_DZSd(__int64 a1, __int64 a2, __int64 a3, int a4, _WORD *a5)
{
  __int64 v5; // rax
  __int64 v7; // r10
  int *v8; // rax
  const wchar_t **v9; // rcx
  __int64 v10; // rdx
  const wchar_t *v11; // r8
  const wchar_t *v12; // r9
  int v14[4]; // [rsp+80h] [rbp-18h] BYREF
  int v15; // [rsp+B8h] [rbp+20h] BYREF

  v15 = a4;
  v14[0] = 1330;
  v5 = -1;
  do
    ++v5;
  while ( aOnecoreDsSecur_1[v5] );
  v7 = 2 * v5 + 2;
  v8 = (int *)a5;
  v9 = (const wchar_t **)(a5 + 4);
  if ( a5 && *v9 )
  {
    if ( *a5 )
      v10 = (unsigned __int16)*a5;
    else
      v10 = 16;
    v11 = *v9;
LABEL_11:
    v12 = L"(empty)";
    if ( *a5 )
      v12 = v11;
    goto LABEL_16;
  }
  v10 = 14;
  if ( a5 )
  {
    v11 = *v9;
    if ( *v9 )
      goto LABEL_11;
  }
  v12 = L"(null)";
  if ( !a5 || !*v9 )
  {
    v8 = &dword_1800A1AEC;
    return EtwTraceMessage(
             a1,
             43,
             WPP_e5b28892b89032293cacd9153c3db07e_Traceguids,
             27,
             &v15,
             4,
             v8,
             2,
             v12,
             v10,
             aOnecoreDsSecur_1,
             v7,
             v14,
             4,
             0);
  }
LABEL_16:
  if ( !*a5 )
    v8 = (int *)byte_1800A1AE8;
  return EtwTraceMessage(
           a1,
           43,
           WPP_e5b28892b89032293cacd9153c3db07e_Traceguids,
           27,
           &v15,
           4,
           v8,
           2,
           v12,
           v10,
           aOnecoreDsSecur_1,
           v7,
           v14,
           4,
           0);
}

```

## disassembly

```asm
0x1800597cc  mov     rax, rsp
0x1800597cf  mov     [rax+8], rbx
0x1800597d3  mov     [rax+10h], rsi
0x1800597d7  mov     [rax+20h], r9d
0x1800597db  push    rdi
0x1800597dc  sub     rsp, 90h
0x1800597e3  mov     dword ptr [rax-18h], 532h
0x1800597ea  lea     rsi, aOnecoreDsSecur_1; "onecore\\ds\\security\\protocols\\kerbe"...
0x1800597f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800597f5  mov     r11, rcx
0x1800597f8  xor     edi, edi
0x1800597fa  inc     rax
0x1800597fd  cmp     [rsi+rax*2], di
0x180059801  jnz     short loc_1800597FA
0x180059803  lea     r10, ds:2[rax*2]
0x18005980b  mov     rax, [rsp+98h+arg_20]
0x180059813  lea     rcx, [rax+8]
0x180059817  test    rax, rax
0x18005981a  jz      short loc_180059835
0x18005981c  cmp     [rcx], rdi
0x18005981f  jz      short loc_180059835
0x180059821  cmp     [rax], di
0x180059824  jz      short loc_18005982B
0x180059826  movzx   edx, word ptr [rax]
0x180059829  jmp     short loc_180059830
0x18005982b  mov     edx, 10h
0x180059830  mov     r8, [rcx]
0x180059833  jmp     short loc_180059847
0x180059835  mov     edx, 0Eh
0x18005983a  test    rax, rax
0x18005983d  jz      short loc_180059857
0x18005983f  mov     r8, [rcx]
0x180059842  test    r8, r8
0x180059845  jz      short loc_180059857
0x180059847  cmp     [rax], di
0x18005984a  lea     r9, aEmpty; "(empty)"
0x180059851  cmovnz  r9, r8
0x180059855  jmp     short loc_180059868
0x180059857  lea     r9, aNull_0; "(null)"
0x18005985e  test    rax, rax
0x180059861  jz      short loc_180059878
0x180059863  cmp     [rcx], rdi
0x180059866  jz      short loc_180059878
0x180059868  cmp     [rax], di
0x18005986b  lea     rcx, byte_1800A1AE8
0x180059872  cmovz   rax, rcx
0x180059876  jmp     short loc_18005987F
0x180059878  lea     rax, dword_1800A1AEC
0x18005987f  mov     [rsp+98h+var_28], rdi
0x180059884  lea     rcx, [rsp+98h+var_18]
0x18005988c  mov     ebx, 1Bh
0x180059891  lea     r8d, [rbx-17h]
0x180059895  mov     [rsp+98h+var_30], r8
0x18005989a  mov     [rsp+98h+var_38], rcx
0x18005989f  mov     rcx, r11
0x1800598a2  mov     [rsp+98h+var_40], r10
0x1800598a7  mov     [rsp+98h+var_48], rsi
0x1800598ac  mov     [rsp+98h+var_50], rdx
0x1800598b1  lea     edx, [rbx+10h]
0x1800598b4  mov     [rsp+98h+var_58], r9
0x1800598b9  mov     r9d, ebx
0x1800598bc  mov     [rsp+98h+var_60], 2
0x1800598c5  mov     [rsp+98h+var_68], rax
0x1800598ca  lea     rax, [rsp+98h+arg_18]
0x1800598d2  mov     [rsp+98h+var_70], r8
0x1800598d7  lea     r8, WPP_e5b28892b89032293cacd9153c3db07e_Traceguids
0x1800598de  mov     [rsp+98h+var_78], rax
0x1800598e3  call    cs:__imp_EtwTraceMessage
0x1800598e9  lea     r11, [rsp+98h+var_8]
0x1800598f1  mov     rbx, [r11+10h]
0x1800598f5  mov     rsi, [r11+18h]
0x1800598f9  mov     rsp, r11
0x1800598fc  pop     rdi
0x1800598fd  retn
```
