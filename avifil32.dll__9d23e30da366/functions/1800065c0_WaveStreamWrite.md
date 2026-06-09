# WaveStreamWrite

- ea: `0x1800065c0`
- end: `0x1800066b4`
- name: `WaveStreamWrite`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800065c0`
- `0x180014960`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000667a`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000667a`
- `WINMM!mmioSeek` at `0x180006627`
- `WINMM!mmioSeek` at `0x180006627`

## pseudocode

```c
__int64 __fastcall WaveStreamWrite(
        __int64 a1,
        int a2,
        int a3,
        char *a4,
        unsigned int a5,
        int a6,
        _DWORD *a7,
        unsigned int *a8)
{
  int v10; // edi
  int *v13; // rsi
  LONG v14; // edx
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // edx
  int v18; // r8d
  unsigned int v19; // eax
  int v20; // edi
  int v21; // ecx
  int v22; // edx

  v10 = a2;
  if ( (*(_BYTE *)(a1 + 296) & 3) == 0 )
    return 2147762290LL;
  v13 = (int *)(a1 + 104);
  if ( a2 < 0 )
    v10 = *v13 + *(_DWORD *)(a1 + 100);
  *(_DWORD *)(a1 + 292) = 1;
  v14 = *(_DWORD *)(a1 + 60) + *(_DWORD *)(a1 + 120) * v10;
  v15 = *(_QWORD *)(a1 + 40);
  v16 = *(_QWORD *)(v15 + 16);
  if ( v16 )
    *(_DWORD *)(v16 + 372) = v14;
  else
    mmioSeek(*(HMMIO *)(v15 + 8), v14, 0);
  if ( shfileWrite(*(_QWORD *)(a1 + 40), a4, a5) != a5 )
    return 2147762286LL;
  v17 = *v13;
  v18 = *(_DWORD *)(a1 + 96);
  if ( *v13 <= v10 + a3 )
    v17 = v10 + a3;
  v19 = *(_DWORD *)(a1 + 52);
  v20 = *(_DWORD *)(a1 + 120) * v10;
  *v13 = v17;
  if ( v19 <= v20 + a5 )
    v19 = v20 + a5;
  v21 = 1000 * v17;
  v22 = *(_DWORD *)(a1 + 92);
  *(_DWORD *)(a1 + 52) = v19;
  *(_DWORD *)(a1 + 356) = MulDiv(v21, v22, v18);
  if ( a7 )
    *a7 = a3;
  if ( a8 )
    *a8 = a5;
  return 0;
}

```

## disassembly

```asm
0x1800065c0  push    rbx
0x1800065c2  push    rbp
0x1800065c3  push    rsi
0x1800065c4  push    rdi
0x1800065c5  push    r14
0x1800065c7  push    r15
0x1800065c9  sub     rsp, 28h
0x1800065cd  test    byte ptr [rcx+128h], 3
0x1800065d4  mov     r15, r9
0x1800065d7  mov     r14d, r8d
0x1800065da  mov     edi, edx
0x1800065dc  mov     rbx, rcx
0x1800065df  jnz     short loc_1800065EB
0x1800065e1  mov     eax, 80044072h
0x1800065e6  jmp     loc_1800066A7
0x1800065eb  lea     rsi, [rcx+68h]
0x1800065ef  test    edx, edx
0x1800065f1  jns     short loc_1800065F8
0x1800065f3  mov     edi, [rcx+64h]
0x1800065f6  add     edi, [rsi]
0x1800065f8  mov     dword ptr [rcx+124h], 1
0x180006602  mov     edx, edi
0x180006604  imul    edx, [rcx+78h]
0x180006608  add     edx, [rcx+3Ch]; lOffset
0x18000660b  mov     rcx, [rcx+28h]
0x18000660f  mov     rax, [rcx+10h]
0x180006613  test    rax, rax
0x180006616  jz      short loc_180006620
0x180006618  mov     [rax+174h], edx
0x18000661e  jmp     short loc_18000662D
0x180006620  mov     rcx, [rcx+8]; hmmio
0x180006624  xor     r8d, r8d; iOrigin
0x180006627  call    cs:__imp_mmioSeek
0x18000662d  mov     ebp, [rsp+58h+arg_20]
0x180006634  mov     rdx, r15
0x180006637  mov     rcx, [rbx+28h]
0x18000663b  mov     r8d, ebp
0x18000663e  call    shfileWrite
0x180006643  cmp     eax, ebp
0x180006645  jz      short loc_18000664E
0x180006647  mov     eax, 8004406Eh
0x18000664c  jmp     short loc_1800066A7
0x18000664e  mov     edx, [rsi]
0x180006650  lea     eax, [rdi+r14]
0x180006654  mov     r8d, [rbx+60h]; nDenominator
0x180006658  cmp     edx, eax
0x18000665a  cmovle  edx, eax
0x18000665d  mov     eax, [rbx+34h]
0x180006660  imul    edi, [rbx+78h]
0x180006664  mov     [rsi], edx
0x180006666  lea     ecx, [rdi+rbp]
0x180006669  cmp     eax, ecx
0x18000666b  cmovbe  eax, ecx
0x18000666e  imul    ecx, edx, 3E8h; nNumber
0x180006674  mov     edx, [rbx+5Ch]; nNumerator
0x180006677  mov     [rbx+34h], eax
0x18000667a  call    cs:__imp_MulDiv
0x180006680  mov     [rbx+164h], eax
0x180006686  mov     rax, [rsp+58h+arg_30]
0x18000668e  test    rax, rax
0x180006691  jz      short loc_180006696
0x180006693  mov     [rax], r14d
0x180006696  mov     rax, [rsp+58h+arg_38]
0x18000669e  test    rax, rax
0x1800066a1  jz      short loc_1800066A5
0x1800066a3  mov     [rax], ebp
0x1800066a5  xor     eax, eax
0x1800066a7  add     rsp, 28h
0x1800066ab  pop     r15
0x1800066ad  pop     r14
0x1800066af  pop     rdi
0x1800066b0  pop     rsi
0x1800066b1  pop     rbp
0x1800066b2  pop     rbx
0x1800066b3  retn
```
