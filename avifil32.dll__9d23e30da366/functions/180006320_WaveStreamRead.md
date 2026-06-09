# WaveStreamRead

- ea: `0x180006320`
- end: `0x180006453`
- name: `WaveStreamRead`
- size: `307`
- prototype: `__int64 __fastcall(__int64, int, int, char *, int, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006320`
- `0x180014880`

## import_xrefs

- `WINMM!mmioSeek` at `0x1800063f0`
- `WINMM!mmioSeek` at `0x1800063f0`

## pseudocode

```c
__int64 __fastcall WaveStreamRead(__int64 a1, int a2, int a3, char *a4, int a5, unsigned int *a6, int *a7)
{
  int v7; // ebx
  int v10; // edi
  int v11; // eax
  unsigned int *v12; // rax
  unsigned int v13; // edi
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  LONG v17; // ebp
  LONG v18; // eax

  v7 = a3;
  if ( a2 >= 0 && a2 <= *(_DWORD *)(a1 + 104) )
  {
    if ( a2 + a3 > *(_DWORD *)(a1 + 104) )
      v7 = *(_DWORD *)(a1 + 104) - a2;
    v10 = *(_DWORD *)(a1 + 120);
    if ( !a4 )
    {
      if ( a5 <= 0 )
      {
        if ( v7 > 0 )
          goto LABEL_11;
      }
      else if ( v7 > 0 )
      {
        v11 = a5 / v10;
        if ( v7 < a5 / v10 )
          v11 = v7;
        goto LABEL_10;
      }
      v11 = a5 / v10;
LABEL_10:
      v7 = v11;
LABEL_11:
      v12 = a6;
      if ( !a6 )
        goto LABEL_14;
      v13 = v7 * v10;
      goto LABEL_13;
    }
    v14 = a5 / v10;
    if ( v7 > 0 && v7 < v14 )
      v14 = v7;
    v7 = v14;
    if ( !a5 )
      goto LABEL_11;
    if ( a5 >= v10 )
    {
      v15 = *(_QWORD *)(a1 + 40);
      v16 = *(_QWORD *)(v15 + 16);
      v17 = *(_DWORD *)(a1 + 60) + a2 * v10;
      if ( v16 )
      {
        *(_DWORD *)(v16 + 372) = v17;
        v18 = *(_DWORD *)(*(_QWORD *)(v15 + 16) + 372LL);
      }
      else
      {
        v18 = mmioSeek(*(HMMIO *)(v15 + 8), v17, 0);
      }
      if ( v18 == v17 )
      {
        v13 = v7 * v10;
        if ( shfileRead(*(_QWORD *)(a1 + 40), a4, v13) == v13 )
        {
          v12 = a6;
          if ( !a6 )
          {
LABEL_14:
            if ( a7 )
              *a7 = v7;
            return 0;
          }
LABEL_13:
          *v12 = v13;
          goto LABEL_14;
        }
      }
    }
  }
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  return 0;
}

```

## disassembly

```asm
0x180006320  push    rbx
0x180006322  push    rbp
0x180006323  push    rsi
0x180006324  push    rdi
0x180006325  push    r14
0x180006327  sub     rsp, 20h
0x18000632b  mov     ebx, r8d
0x18000632e  mov     r8d, edx
0x180006331  mov     r14, r9
0x180006334  mov     rsi, rcx
0x180006337  test    edx, edx
0x180006339  js      loc_180006423
0x18000633f  cmp     edx, [rcx+68h]
0x180006342  jg      loc_180006423
0x180006348  lea     eax, [rdx+rbx]
0x18000634b  cmp     eax, [rcx+68h]
0x18000634e  jle     short loc_180006355
0x180006350  mov     ebx, [rcx+68h]
0x180006353  sub     ebx, edx
0x180006355  mov     edi, [rcx+78h]
0x180006358  test    r14, r14
0x18000635b  jnz     short loc_1800063A3
0x18000635d  mov     eax, [rsp+48h+arg_20]
0x180006361  test    eax, eax
0x180006363  jle     short loc_18000639A
0x180006365  test    ebx, ebx
0x180006367  jle     short loc_18000639E
0x180006369  cdq
0x18000636a  idiv    edi
0x18000636c  cmp     ebx, eax
0x18000636e  cmovl   eax, ebx
0x180006371  mov     ebx, eax
0x180006373  mov     rax, [rsp+48h+arg_28]
0x180006378  test    rax, rax
0x18000637b  jz      short loc_180006382
0x18000637d  imul    edi, ebx
0x180006380  mov     [rax], edi
0x180006382  mov     rax, [rsp+48h+arg_30]
0x18000638a  test    rax, rax
0x18000638d  jz      loc_180006446
0x180006393  mov     [rax], ebx
0x180006395  jmp     loc_180006446
0x18000639a  test    ebx, ebx
0x18000639c  jg      short loc_180006373
0x18000639e  cdq
0x18000639f  idiv    edi
0x1800063a1  jmp     short loc_180006371
0x1800063a3  mov     ecx, [rsp+48h+arg_20]
0x1800063a7  mov     eax, ecx
0x1800063a9  cdq
0x1800063aa  idiv    edi
0x1800063ac  test    ebx, ebx
0x1800063ae  jle     short loc_1800063B5
0x1800063b0  cmp     ebx, eax
0x1800063b2  cmovl   eax, ebx
0x1800063b5  mov     ebx, eax
0x1800063b7  test    ecx, ecx
0x1800063b9  jz      short loc_180006373
0x1800063bb  cmp     ecx, edi
0x1800063bd  jl      short loc_180006423
0x1800063bf  mov     rcx, [rsi+28h]
0x1800063c3  mov     ebp, edi
0x1800063c5  imul    ebp, r8d
0x1800063c9  mov     rax, [rcx+10h]
0x1800063cd  add     ebp, [rsi+3Ch]
0x1800063d0  test    rax, rax
0x1800063d3  jz      short loc_1800063E7
0x1800063d5  mov     [rax+174h], ebp
0x1800063db  mov     rax, [rcx+10h]
0x1800063df  mov     eax, [rax+174h]
0x1800063e5  jmp     short loc_1800063F6
0x1800063e7  mov     rcx, [rcx+8]; hmmio
0x1800063eb  xor     r8d, r8d; iOrigin
0x1800063ee  mov     edx, ebp; lOffset
0x1800063f0  call    cs:__imp_mmioSeek
0x1800063f6  cmp     eax, ebp
0x1800063f8  jnz     short loc_180006423
0x1800063fa  mov     rcx, [rsi+28h]
0x1800063fe  mov     rdx, r14
0x180006401  imul    edi, ebx
0x180006404  mov     r8d, edi
0x180006407  call    shfileRead
0x18000640c  cmp     eax, edi
0x18000640e  jnz     short loc_180006423
0x180006410  mov     rax, [rsp+48h+arg_28]
0x180006415  test    rax, rax
0x180006418  jz      loc_180006382
0x18000641e  jmp     loc_180006380
0x180006423  mov     rax, [rsp+48h+arg_28]
0x180006428  test    rax, rax
0x18000642b  jz      short loc_180006433
0x18000642d  mov     dword ptr [rax], 0
0x180006433  mov     rax, [rsp+48h+arg_30]
0x18000643b  test    rax, rax
0x18000643e  jz      short loc_180006446
0x180006440  mov     dword ptr [rax], 0
0x180006446  xor     eax, eax
0x180006448  add     rsp, 20h
0x18000644c  pop     r14
0x18000644e  pop     rdi
0x18000644f  pop     rsi
0x180006450  pop     rbp
0x180006451  pop     rbx
0x180006452  retn
```
