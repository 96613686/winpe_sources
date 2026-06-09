# Em_AmrNB_Dec_gIIRFilter

- ea: `0x180007b6c`
- end: `0x180007c4b`
- name: `Em_AmrNB_Dec_gIIRFilter`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004dd0`
- `0x1800051e0`

## callees

- `0x180006764`
- `0x1800067ac`
- `0x180007b6c`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gIIRFilter(__int16 *a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  int v6; // edi
  __int64 v10; // rbx
  int v11; // ecx
  int v12; // ecx
  int v13; // r10d
  unsigned int v14; // eax
  int v15; // r10d
  int v16; // eax
  int v17; // edx
  int v18; // edx
  __int64 v19; // rdx
  _WORD v21[74]; // [rsp+34h] [rbp-94h]

  v6 = 0;
  v10 = 0;
  do
  {
    v11 = *a1 * *(__int16 *)(a2 + 2 * v10);
    if ( v11 == 0x40000000 )
      v12 = 0x7FFFFFFF;
    else
      v12 = 2 * v11;
    v13 = 1;
    do
    {
      v14 = Em_AmrNB_Dec_L_msu(v12, a1[v13], v21[(unsigned int)v6 - (unsigned __int64)(unsigned int)v13]);
      v13 = v15 + 1;
      v12 = v14;
    }
    while ( v13 <= 10 );
    v16 = Em_AmrNB_Dec_L_shl(v14, 3);
    v17 = v16 + 0x8000;
    if ( v16 >= 0 && (v16 ^ v17) < 0 )
      v17 = 0x7FFFFFFF;
    v18 = v17 >> 16;
    ++v6;
    v21[v10] = v18;
    *(_WORD *)(a6 + 2 * v10++) = v18;
  }
  while ( v6 < 40 );
  v19 = 0;
  do
  {
    *(_WORD *)(a3 + 2 * v19) = *(_WORD *)(a6 + 2 * v19 + 60);
    v19 = (unsigned int)(v19 + 1);
  }
  while ( (int)v19 < 10 );
  return 0;
}

```

## disassembly

```asm
0x180007b6c  push    rbx
0x180007b6e  push    rbp
0x180007b6f  push    rsi
0x180007b70  push    rdi
0x180007b71  push    r13
0x180007b73  push    r14
0x180007b75  push    r15
0x180007b77  sub     rsp, 90h
0x180007b7e  movups  xmm0, xmmword ptr [r8]
0x180007b82  mov     eax, [r8+10h]
0x180007b86  xor     edi, edi
0x180007b88  mov     rsi, [rsp+0C8h+arg_28]
0x180007b90  mov     r14, r8
0x180007b93  movups  [rsp+0C8h+var_A8], xmm0
0x180007b98  mov     rbp, rdx
0x180007b9b  mov     [rsp+0C8h+var_98], eax
0x180007b9f  mov     r15, rcx
0x180007ba2  xor     ebx, ebx
0x180007ba4  mov     r13d, 7FFFFFFFh
0x180007baa  movsx   ecx, word ptr [rbp+rbx*2+0]
0x180007baf  movsx   eax, word ptr [r15]
0x180007bb3  imul    ecx, eax
0x180007bb6  cmp     ecx, 40000000h
0x180007bbc  jz      short loc_180007BC2
0x180007bbe  add     ecx, ecx
0x180007bc0  jmp     short loc_180007BC5
0x180007bc2  mov     ecx, r13d
0x180007bc5  mov     r10d, 1
0x180007bcb  mov     eax, r10d
0x180007bce  mov     edx, r10d
0x180007bd1  mov     r8d, edi
0x180007bd4  sub     r8, rax
0x180007bd7  movzx   edx, word ptr [r15+rdx*2]
0x180007bdc  movzx   r8d, [rsp+r8*2+0C8h+var_94]
0x180007be2  call    Em_AmrNB_Dec_L_msu
0x180007be7  inc     r10d
0x180007bea  mov     ecx, eax
0x180007bec  cmp     r10d, 0Ah
0x180007bf0  jle     short loc_180007BCB
0x180007bf2  mov     edx, 3
0x180007bf7  call    Em_AmrNB_Dec_L_shl
0x180007bfc  lea     edx, [rax+8000h]
0x180007c02  test    eax, eax
0x180007c04  js      short loc_180007C0E
0x180007c06  mov     ecx, edx
0x180007c08  xor     ecx, eax
0x180007c0a  cmovl   edx, r13d
0x180007c0e  sar     edx, 10h
0x180007c11  inc     edi
0x180007c13  mov     [rsp+rbx*2+0C8h+var_94], dx
0x180007c18  mov     [rsi+rbx*2], dx
0x180007c1c  inc     rbx
0x180007c1f  cmp     edi, 28h ; '('
0x180007c22  jl      short loc_180007BAA
0x180007c24  xor     edx, edx
0x180007c26  movzx   eax, word ptr [rsi+rdx*2+3Ch]
0x180007c2b  mov     [r14+rdx*2], ax
0x180007c30  inc     edx
0x180007c32  cmp     edx, 0Ah
0x180007c35  jl      short loc_180007C26
0x180007c37  xor     eax, eax
0x180007c39  add     rsp, 90h
0x180007c40  pop     r15
0x180007c42  pop     r14
0x180007c44  pop     r13
0x180007c46  pop     rdi
0x180007c47  pop     rsi
0x180007c48  pop     rbp
0x180007c49  pop     rbx
0x180007c4a  retn
```
