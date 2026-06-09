# KerbLoadDH(void)

- ea: `0x1800799bc`
- end: `0x180079a30`
- name: `?KerbLoadDH@@YAHXZ`
- size: `116`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18003a5fc`
- `0x180078408`
- `0x180079228`

## callees

- `0x1800799bc`
- `0x180079a38`
- `0x180079bf4`
- `0x180085138`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180079a02`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180079a02`

## pseudocode

```c
__int64 KerbLoadDH(void)
{
  unsigned int ModpDH; // ebx
  __int64 v1; // rdi
  __int64 v2; // rsi

  ModpDH = KerbLoadModpDH();
  if ( !ModpDH )
    goto LABEL_8;
  if ( !KerbGetGlobalECDHEmpheralAlg() )
  {
LABEL_7:
    ModpDH = 0;
LABEL_8:
    KerbUnLoadDH();
    return ModpDH;
  }
  v1 = 0;
  ModpDH = 1;
  while ( (unsigned int)v1 < 3 )
  {
    v2 = 9 * v1;
    if ( BCryptOpenAlgorithmProvider(
           (BCRYPT_ALG_HANDLE *)&qword_1800B2190[9 * v1],
           (LPCWSTR)*(&KerbGlobalECCNamedCurves + 9 * v1 + 3),
           0,
           0) < 0 )
      goto LABEL_7;
    v1 = (unsigned int)(v1 + 1);
    *(&KerbGlobalECCNamedCurves + v2 + 6) = (struct _KERB_ECC_CURVE_INFO near *)*((_QWORD *)KerbGetGlobalECDHEmpheralAlg()
                                                                                + 1);
  }
  return ModpDH;
}

```

## disassembly

```asm
0x1800799bc  push    rbx
0x1800799be  push    rbp
0x1800799bf  push    rsi
0x1800799c0  push    rdi
0x1800799c1  sub     rsp, 28h
0x1800799c5  call    ?KerbLoadModpDH@@YAHXZ; KerbLoadModpDH(void)
0x1800799ca  mov     ebx, eax
0x1800799cc  test    eax, eax
0x1800799ce  jz      short loc_180079A20
0x1800799d0  call    ?KerbGetGlobalECDHEmpheralAlg@@YAPEAUKERB_ALGORITHM_IDENTIFIER@@XZ; KerbGetGlobalECDHEmpheralAlg(void)
0x1800799d5  test    rax, rax
0x1800799d8  jz      short loc_180079A1E
0x1800799da  xor     edi, edi
0x1800799dc  lea     rbp, ?KerbGlobalECCNamedCurves@@3PAU_KERB_ECC_CURVE_INFO@@A; _KERB_ECC_CURVE_INFO near * KerbGlobalECCNamedCurves
0x1800799e3  lea     ebx, [rdi+1]
0x1800799e6  cmp     edi, 3
0x1800799e9  jnb     short loc_180079A25
0x1800799eb  lea     rsi, [rdi+rdi*8]
0x1800799ef  xor     r9d, r9d; dwFlags
0x1800799f2  mov     rdx, [rbp+rsi*8+18h]; pszAlgId
0x1800799f7  lea     rcx, [rbp+20h]
0x1800799fb  lea     rcx, [rcx+rsi*8]; phAlgorithm
0x1800799ff  xor     r8d, r8d; pszImplementation
0x180079a02  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180079a08  test    eax, eax
0x180079a0a  js      short loc_180079A1E
0x180079a0c  call    ?KerbGetGlobalECDHEmpheralAlg@@YAPEAUKERB_ALGORITHM_IDENTIFIER@@XZ; KerbGetGlobalECDHEmpheralAlg(void)
0x180079a11  add     edi, ebx
0x180079a13  mov     rax, [rax+8]
0x180079a17  mov     [rbp+rsi*8+30h], rax
0x180079a1c  jmp     short loc_1800799E6
0x180079a1e  xor     ebx, ebx
0x180079a20  call    ?KerbUnLoadDH@@YAXXZ; KerbUnLoadDH(void)
0x180079a25  mov     eax, ebx
0x180079a27  add     rsp, 28h
0x180079a2b  pop     rdi
0x180079a2c  pop     rsi
0x180079a2d  pop     rbp
0x180079a2e  pop     rbx
0x180079a2f  retn
```
