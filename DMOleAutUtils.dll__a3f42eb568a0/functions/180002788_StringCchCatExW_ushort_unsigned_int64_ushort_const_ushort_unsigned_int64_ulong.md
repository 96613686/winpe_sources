# StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x180002788`
- end: `0x180002894`
- name: `?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `268`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002530`

## callees

- `0x180002788`

## pseudocode

```c
__int64 __fastcall StringCchCatExW(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  __int64 v5; // rbx
  __int64 v8; // r10
  unsigned __int16 *v9; // rax
  unsigned int v10; // r8d
  __int64 v11; // r9
  unsigned __int64 v12; // r10
  unsigned __int16 *v13; // rsi
  unsigned __int64 v14; // r8
  unsigned __int16 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  unsigned __int16 *v18; // rcx

  v5 = 2147483646;
  v8 = a2;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
    return (unsigned int)-2147024809;
  v9 = a1;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --a2;
  }
  while ( a2 );
  v10 = a2 == 0 ? 0x80070057 : 0;
  v11 = (v8 - a2) & -(__int64)(a2 != 0);
  if ( !a2 )
    return v10;
  v12 = v8 - v11;
  v13 = &a1[v11];
  if ( v12 > 1 )
  {
    v14 = v12;
    v15 = &a1[v11];
    v16 = 0;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v15++ = *a3++;
      --v5;
      ++v16;
      --v14;
    }
    while ( v14 );
    v17 = v16 - 1;
    if ( v14 )
      v17 = v16;
    v18 = v15 - 1;
    if ( v14 )
      v18 = v15;
    v13 += v17;
    v10 = v14 != 0 ? 0 : 0x8007007A;
    *v18 = 0;
    v12 -= v17;
    goto LABEL_19;
  }
  v10 = 0;
  if ( *a3 )
  {
    if ( a1 )
    {
      v10 = -2147024774;
      goto LABEL_19;
    }
    return (unsigned int)-2147024809;
  }
LABEL_19:
  if ( a4 )
    *a4 = v13;
  if ( a5 )
    *a5 = v12;
  return v10;
}

```

## disassembly

```asm
0x180002788  push    rbx
0x18000278a  push    rbp
0x18000278b  push    rsi
0x18000278c  push    rdi
0x18000278d  push    r14
0x18000278f  lea     rax, [rdx-1]
0x180002793  mov     ebx, 7FFFFFFEh
0x180002798  mov     r14, r9
0x18000279b  mov     r11, r8
0x18000279e  mov     r10, rdx
0x1800027a1  mov     rdi, rcx
0x1800027a4  cmp     rax, rbx
0x1800027a7  ja      loc_180002884
0x1800027ad  mov     rax, rcx
0x1800027b0  xor     ebp, ebp
0x1800027b2  cmp     [rax], bp
0x1800027b5  jz      short loc_1800027C1
0x1800027b7  add     rax, 2
0x1800027bb  sub     rdx, 1
0x1800027bf  jnz     short loc_1800027B2
0x1800027c1  mov     rax, rdx
0x1800027c4  mov     rcx, r10
0x1800027c7  neg     rax
0x1800027ca  mov     rax, rdx
0x1800027cd  sbb     r8d, r8d
0x1800027d0  sub     rcx, rdx
0x1800027d3  not     r8d
0x1800027d6  and     r8d, 80070057h
0x1800027dd  neg     rax
0x1800027e0  sbb     r9, r9
0x1800027e3  and     r9, rcx
0x1800027e6  test    rdx, rdx
0x1800027e9  jz      loc_18000288A
0x1800027ef  sub     r10, r9
0x1800027f2  lea     rsi, [rdi+r9*2]
0x1800027f6  cmp     r10, 1
0x1800027fa  ja      short loc_180002812
0x1800027fc  mov     r8d, ebp
0x1800027ff  cmp     [r11], bp
0x180002803  jz      short loc_18000286D
0x180002805  test    rdi, rdi
0x180002808  jz      short loc_180002884
0x18000280a  mov     r8d, 8007007Ah
0x180002810  jmp     short loc_18000286D
0x180002812  mov     r8, r10
0x180002815  mov     rax, rsi
0x180002818  mov     rcx, rbp
0x18000281b  test    rbx, rbx
0x18000281e  jz      short loc_180002840
0x180002820  movzx   edx, word ptr [r11]
0x180002824  test    dx, dx
0x180002827  jz      short loc_180002840
0x180002829  mov     [rax], dx
0x18000282c  add     r11, 2
0x180002830  add     rax, 2
0x180002834  dec     rbx
0x180002837  inc     rcx
0x18000283a  sub     r8, 1
0x18000283e  jnz     short loc_18000281B
0x180002840  test    r8, r8
0x180002843  lea     rdx, [rcx-1]
0x180002847  cmovnz  rdx, rcx
0x18000284b  lea     rcx, [rax-2]
0x18000284f  cmovnz  rcx, rax
0x180002853  neg     r8
0x180002856  mov     r8d, 8007007Ah
0x18000285c  sbb     eax, eax
0x18000285e  not     eax
0x180002860  lea     rsi, [rsi+rdx*2]
0x180002864  and     r8d, eax
0x180002867  mov     [rcx], bp
0x18000286a  sub     r10, rdx
0x18000286d  test    r14, r14
0x180002870  jz      short loc_180002875
0x180002872  mov     [r14], rsi
0x180002875  mov     rax, [rsp+28h+arg_20]
0x18000287a  test    rax, rax
0x18000287d  jz      short loc_18000288A
0x18000287f  mov     [rax], r10
0x180002882  jmp     short loc_18000288A
0x180002884  mov     r8d, 80070057h
0x18000288a  mov     eax, r8d
0x18000288d  pop     r14
0x18000288f  pop     rdi
0x180002890  pop     rsi
0x180002891  pop     rbp
0x180002892  pop     rbx
0x180002893  retn
```
