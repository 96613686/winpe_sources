# TiffRecoverGoodPages

- ea: `0x180009070`
- end: `0x18000919a`
- name: `TiffRecoverGoodPages`
- size: `298`
- prototype: `_BOOL8 __fastcall(const WCHAR *, _DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007cd0`
- `0x1800087a0`
- `0x180009070`
- `0x18000ac38`
- `0x18000b604`
- `0x180016794`

## string_xrefs

- `0x180009121`: `TiffRecoverGoodPages: %s: Unexpected Compression type %d\n`

## pseudocode

```c
_BOOL8 __fastcall TiffRecoverGoodPages(const WCHAR *a1, _DWORD *a2, _DWORD *a3)
{
  _DWORD *v4; // rax
  BOOL v6; // r14d

  if ( !a1 || !a2 || !a3 )
    return 0;
  *a2 = 0;
  *a3 = 0;
  v4 = (_DWORD *)TiffOpen(a1);
  if ( !v4 )
  {
    *a3 = 0;
    return 0;
  }
  *a3 = 0;
  v6 = v4[392] != 0;
  TiffClose(v4);
  return v6;
}

```

## disassembly

```asm
0x180009070  push    rbp
0x180009072  push    rsi
0x180009073  push    rdi
0x180009074  push    r12
0x180009076  push    r14
0x180009078  push    r15
0x18000907a  mov     rbp, rsp
0x18000907d  sub     rsp, 68h
0x180009081  xorps   xmm0, xmm0
0x180009084  mov     rdi, r8
0x180009087  mov     r12, rdx
0x18000908a  movups  [rbp+var_48], xmm0
0x18000908e  movups  [rbp+var_38], xmm0
0x180009092  test    rcx, rcx
0x180009095  jz      short loc_1800090CA
0x180009097  test    rdx, rdx
0x18000909a  jz      short loc_1800090CA
0x18000909c  test    r8, r8
0x18000909f  jz      short loc_1800090CA
0x1800090a1  mov     dword ptr [rdx], 0
0x1800090a7  mov     r9d, 2
0x1800090ad  mov     dword ptr [r8], 0
0x1800090b4  lea     rdx, [rbp+var_48]
0x1800090b8  xor     r8d, r8d
0x1800090bb  call    TiffOpen
0x1800090c0  mov     rsi, rax
0x1800090c3  test    rax, rax
0x1800090c6  jnz     short loc_1800090DA
0x1800090c8  mov     [rdi], eax
0x1800090ca  xor     eax, eax
0x1800090cc  add     rsp, 68h
0x1800090d0  pop     r15
0x1800090d2  pop     r14
0x1800090d4  pop     r12
0x1800090d6  pop     rdi
0x1800090d7  pop     rsi
0x1800090d8  pop     rbp
0x1800090d9  retn
0x1800090da  mov     r15d, dword ptr [rbp+var_48+8]
0x1800090de  mov     [rdi], r15d
0x1800090e1  cmp     dword ptr [rax+620h], 0
0x1800090e8  jz      short loc_1800090F5
0x1800090ea  mov     r14d, 1
0x1800090f0  jmp     loc_18000918A
0x1800090f5  xor     r14d, r14d
0x1800090f8  cmp     r15d, 1
0x1800090fc  jb      loc_18000918A
0x180009102  mov     r8d, [rax+354h]
0x180009109  lea     ecx, [r14+1]
0x18000910d  mov     eax, r8d
0x180009110  sub     eax, 2
0x180009113  jz      short loc_180009150
0x180009115  sub     eax, ecx
0x180009117  jz      short loc_18000912F
0x180009119  cmp     eax, ecx
0x18000911b  jz      short loc_180009179
0x18000911d  lea     rdx, [rsi+2Ch]
0x180009121  lea     rcx, aTiffrecovergoo_0; "TiffRecoverGoodPages: %s: Unexpected Co"...
0x180009128  call    fax_dprintf
0x18000912d  jmp     short loc_18000918A
0x18000912f  movups  xmm0, [rbp+var_48]
0x180009133  xor     r8d, r8d
0x180009136  lea     rdx, [rbp+var_28]
0x18000913a  movups  xmm1, [rbp+var_38]
0x18000913e  mov     rcx, rsi
0x180009141  movaps  [rbp+var_28], xmm0
0x180009145  movaps  [rbp+var_18], xmm1
0x180009149  call    PostProcessMrToMmr
0x18000914e  jmp     short loc_18000916F
0x180009150  movups  xmm0, [rbp+var_48]
0x180009154  xor     r8d, r8d
0x180009157  lea     rdx, [rbp+var_28]
0x18000915b  movups  xmm1, [rbp+var_38]
0x18000915f  mov     rcx, rsi
0x180009162  movaps  [rbp+var_28], xmm0
0x180009166  movaps  [rbp+var_18], xmm1
0x18000916a  call    PostProcessMhToMmr
0x18000916f  test    eax, eax
0x180009171  jz      loc_1800090CA
0x180009177  xor     ecx, ecx
0x180009179  mov     [r12], r15d
0x18000917d  mov     r14d, 1
0x180009183  inc     dword ptr [rdi]
0x180009185  cmp     ecx, r14d
0x180009188  jnz     short loc_180009192
0x18000918a  mov     rcx, rsi; lpMem
0x18000918d  call    TiffClose
0x180009192  mov     eax, r14d
0x180009195  jmp     loc_1800090CC
```
