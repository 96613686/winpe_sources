# Parse_Cmdline(ushort *,ushort * *,ushort *,int *,int *,int)

- ea: `0x180001390`
- end: `0x1800015c6`
- name: `?Parse_Cmdline@@YAXPEAGPEAPEAG0PEAH2H@Z`
- size: `566`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int16 **, unsigned __int16 *, int *, int *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x180001390`

## pseudocode

```c
void __fastcall Parse_Cmdline(
        unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned __int16 *a3,
        int *a4,
        int *a5,
        int a6)
{
  unsigned __int16 **v7; // r11
  unsigned __int16 **v8; // rbp
  int v9; // edx
  unsigned __int16 *v10; // r9
  unsigned __int16 v11; // ax
  int v12; // edx
  unsigned __int16 v13; // ax
  unsigned __int16 v14; // ax
  unsigned __int16 v15; // ax
  int v16; // ebx
  unsigned __int16 i; // r9
  unsigned __int16 v18; // ax
  int v19; // r9d
  bool v20; // zf
  int v21; // eax

  v7 = a2;
  *a4 = 1;
  v8 = &a2[((unsigned __int64)a6 >> 3) - 1];
  if ( a2 && a2 < v8 )
  {
    *a2 = a3;
    v7 = a2 + 1;
  }
  v9 = 0;
  if ( *a1 == 34 )
  {
    v14 = a1[1];
    ++a1;
    if ( v14 != 34 )
    {
      v19 = 0;
      do
      {
        v9 = v19;
        if ( !v14 )
          break;
        v9 = v19 + 2;
        if ( a3 )
          *a3++ = v14;
        v14 = a1[1];
        ++a1;
        v19 += 2;
      }
      while ( v14 != 34 );
    }
    *a5 = v9 + 2;
    if ( a3 )
      *a3++ = 0;
    if ( *a1 == 34 )
      ++a1;
  }
  else
  {
    do
    {
      v9 += 2;
      v10 = a1;
      if ( a3 )
        *a3++ = *a1;
      v11 = *a1++;
    }
    while ( v11 > 0x20u );
    *a5 = v9;
    if ( v11 )
    {
      if ( a3 )
        *(a3 - 1) = 0;
    }
    else
    {
      a1 = v10;
    }
  }
  v12 = 0;
  while ( 1 )
  {
    v13 = *a1;
    if ( !*a1 )
      break;
    while ( v13 == 9 || v13 == 32 )
    {
      v13 = a1[1];
      ++a1;
    }
    if ( !*a1 )
      break;
    if ( v7 && v7 < v8 )
      *v7++ = a3;
    ++*a4;
    while ( 1 )
    {
      v15 = *a1;
      v16 = 1;
      for ( i = 0; v15 == 92; ++i )
      {
        v15 = a1[1];
        ++a1;
      }
      if ( v15 == 34 )
      {
        if ( (i & 1) == 0 )
        {
          v16 = 0;
          if ( v12 )
          {
            v20 = a1[1] == 34;
            v12 = 0;
            if ( a1[1] == 34 )
              ++a1;
            LOBYTE(v16) = v20;
          }
          else
          {
            v12 = 1;
          }
        }
        i >>= 1;
      }
      if ( i )
      {
        v21 = *a5;
        do
        {
          --i;
          if ( a3 )
            *a3++ = 92;
          v21 += 2;
        }
        while ( i );
        *a5 = v21;
      }
      v18 = *a1;
      if ( !*a1 || !v12 && (v18 == 32 || v18 == 9) )
        break;
      if ( v16 )
      {
        if ( a3 )
          *a3++ = v18;
        *a5 += 2;
      }
      ++a1;
    }
    if ( a3 )
      *a3++ = 0;
    *a5 += 2;
  }
}

```

## disassembly

```asm
0x180001390  push    rbx
0x180001392  push    rbp
0x180001393  push    rsi
0x180001394  push    rdi
0x180001395  push    r14
0x180001397  push    r15
0x180001399  movsxd  rbp, [rsp+30h+arg_28]
0x18000139e  mov     rsi, r9
0x1800013a1  mov     rdi, [rsp+30h+arg_20]
0x1800013a6  mov     r11, rdx
0x1800013a9  shr     rbp, 3
0x1800013ad  dec     rbp
0x1800013b0  mov     dword ptr [r9], 1
0x1800013b7  lea     rbp, [rdx+rbp*8]
0x1800013bb  test    rdx, rdx
0x1800013be  jnz     short loc_180001422
0x1800013c0  xor     r10d, r10d
0x1800013c3  cmp     word ptr [rcx], 22h ; '"'
0x1800013c7  mov     edx, r10d
0x1800013ca  jz      short loc_180001430
0x1800013cc  nop     dword ptr [rax+00h]
0x1800013d0  add     edx, 2
0x1800013d3  mov     r9, rcx
0x1800013d6  test    r8, r8
0x1800013d9  jz      short loc_1800013E6
0x1800013db  movzx   eax, word ptr [rcx]
0x1800013de  mov     [r8], ax
0x1800013e2  add     r8, 2
0x1800013e6  movzx   eax, word ptr [rcx]
0x1800013e9  add     rcx, 2
0x1800013ed  cmp     ax, 20h ; ' '
0x1800013f1  ja      short loc_1800013D0
0x1800013f3  mov     [rdi], edx
0x1800013f5  test    ax, ax
0x1800013f8  jz      loc_180001553
0x1800013fe  test    r8, r8
0x180001401  jz      short loc_180001408
0x180001403  mov     [r8-2], r10w
0x180001408  mov     edx, r10d
0x18000140b  mov     r14d, 0FFFFh
0x180001411  movzx   eax, word ptr [rcx]
0x180001414  test    ax, ax
0x180001417  jnz     short loc_180001460
0x180001419  pop     r15
0x18000141b  pop     r14
0x18000141d  pop     rdi
0x18000141e  pop     rsi
0x18000141f  pop     rbp
0x180001420  pop     rbx
0x180001421  retn
0x180001422  cmp     r11, rbp
0x180001425  jnb     short loc_1800013C0
0x180001427  mov     [rdx], r8
0x18000142a  add     r11, 8
0x18000142e  jmp     short loc_1800013C0
0x180001430  movzx   eax, word ptr [rcx+2]
0x180001434  add     rcx, 2
0x180001438  cmp     ax, 22h ; '"'
0x18000143c  jnz     loc_180001510
0x180001442  lea     eax, [rdx+2]
0x180001445  mov     [rdi], eax
0x180001447  test    r8, r8
0x18000144a  jnz     loc_180001546
0x180001450  cmp     word ptr [rcx], 22h ; '"'
0x180001454  jnz     short loc_180001408
0x180001456  add     rcx, 2
0x18000145a  jmp     short loc_180001408
0x180001460  cmp     ax, 9
0x180001464  jz      loc_180001503
0x18000146a  cmp     ax, 20h ; ' '
0x18000146e  jz      loc_180001503
0x180001474  cmp     word ptr [rcx], 0
0x180001478  jz      short loc_180001419
0x18000147a  test    r11, r11
0x18000147d  jnz     short loc_1800014F2
0x18000147f  inc     dword ptr [rsi]
0x180001481  movzx   eax, word ptr [rcx]
0x180001484  mov     ebx, 1
0x180001489  movzx   r9d, r10w
0x18000148d  cmp     ax, 5Ch ; '\'
0x180001491  jz      loc_18000155B
0x180001497  cmp     ax, 22h ; '"'
0x18000149b  jz      loc_180001572
0x1800014a1  test    r9w, r9w
0x1800014a5  jnz     loc_1800015A1
0x1800014ab  movzx   eax, word ptr [rcx]
0x1800014ae  test    ax, ax
0x1800014b1  jnz     short loc_1800014C8
0x1800014b3  test    r8, r8
0x1800014b6  jz      short loc_1800014C0
0x1800014b8  mov     [r8], r10w
0x1800014bc  add     r8, 2
0x1800014c0  add     dword ptr [rdi], 2
0x1800014c3  jmp     loc_180001411
0x1800014c8  test    edx, edx
0x1800014ca  jnz     short loc_1800014D8
0x1800014cc  cmp     ax, 20h ; ' '
0x1800014d0  jz      short loc_1800014B3
0x1800014d2  cmp     ax, 9
0x1800014d6  jz      short loc_1800014B3
0x1800014d8  test    ebx, ebx
0x1800014da  jz      short loc_1800014EC
0x1800014dc  test    r8, r8
0x1800014df  jz      short loc_1800014E9
0x1800014e1  mov     [r8], ax
0x1800014e5  add     r8, 2
0x1800014e9  add     dword ptr [rdi], 2
0x1800014ec  add     rcx, 2
0x1800014f0  jmp     short loc_180001481
0x1800014f2  cmp     r11, rbp
0x1800014f5  jnb     short loc_18000147F
0x1800014f7  mov     [r11], r8
0x1800014fa  add     r11, 8
0x1800014fe  jmp     loc_18000147F
0x180001503  movzx   eax, word ptr [rcx+2]
0x180001507  add     rcx, 2
0x18000150b  jmp     loc_180001460
0x180001510  mov     r9d, r10d
0x180001513  mov     edx, r9d
0x180001516  test    ax, ax
0x180001519  jz      loc_180001442
0x18000151f  lea     edx, [r9+2]
0x180001523  test    r8, r8
0x180001526  jz      short loc_180001530
0x180001528  mov     [r8], ax
0x18000152c  add     r8, 2
0x180001530  movzx   eax, word ptr [rcx+2]
0x180001534  add     rcx, 2
0x180001538  mov     r9d, edx
0x18000153b  cmp     ax, 22h ; '"'
0x18000153f  jnz     short loc_180001513
0x180001541  jmp     loc_180001442
0x180001546  mov     [r8], r10w
0x18000154a  add     r8, 2
0x18000154e  jmp     loc_180001450
0x180001553  mov     rcx, r9
0x180001556  jmp     loc_180001408
0x18000155b  movzx   eax, word ptr [rcx+2]
0x18000155f  add     rcx, 2
0x180001563  inc     r9w
0x180001567  cmp     ax, 5Ch ; '\'
0x18000156b  jz      short loc_18000155B
0x18000156d  jmp     loc_180001497
0x180001572  test    bl, r9b
0x180001575  jnz     short loc_180001598
0x180001577  mov     ebx, r10d
0x18000157a  test    edx, edx
0x18000157c  jz      short loc_180001593
0x18000157e  cmp     word ptr [rcx+2], 22h ; '"'
0x180001583  lea     rax, [rcx+2]
0x180001587  mov     edx, r10d
0x18000158a  cmovz   rcx, rax
0x18000158e  setz    bl
0x180001591  jmp     short loc_180001598
0x180001593  mov     edx, 1
0x180001598  shr     r9w, 1
0x18000159c  jmp     loc_1800014A1
0x1800015a1  mov     eax, [rdi]
0x1800015a3  add     r9w, r14w
0x1800015a7  test    r8, r8
0x1800015aa  jz      short loc_1800015B6
0x1800015ac  mov     word ptr [r8], 5Ch ; '\'
0x1800015b2  add     r8, 2
0x1800015b6  add     eax, 2
0x1800015b9  test    r9w, r9w
0x1800015bd  jnz     short loc_1800015A3
0x1800015bf  mov     [rdi], eax
0x1800015c1  jmp     loc_1800014AB
```
