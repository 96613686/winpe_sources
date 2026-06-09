# ReadRepTree

- ea: `0x1800087b0`
- end: `0x180008a59`
- name: `ReadRepTree`
- size: `681`
- prototype: `_BOOL8 __fastcall(unsigned int *, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007c94`

## callees

- `0x180001400`
- `0x180001cae`
- `0x180008134`
- `0x1800087b0`
- `0x180008b3c`

## pseudocode

```c
_BOOL8 __fastcall ReadRepTree(unsigned int *a1, int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rdi
  unsigned int v9; // ebx
  __int64 v10; // rcx
  int j; // edi
  __int16 v12; // bx
  unsigned int v13; // r8d
  __int16 v14; // bx
  __int64 v15; // rax
  unsigned int v16; // ebx
  int v17; // eax
  int v18; // ecx
  int v19; // ebx
  unsigned int v20; // ebx
  int v21; // eax
  int v22; // ecx
  int v23; // ebx
  unsigned int v24; // ebx
  unsigned int v25; // r8d
  int v26; // eax
  int v27; // ecx
  int v28; // ebx
  __int16 v29; // bp
  unsigned int v30; // edx
  __int16 v31; // bp
  __int64 v32; // rax
  unsigned __int64 v33; // rdx
  _BYTE v35[32]; // [rsp+30h] [rbp-328h] BYREF
  _WORD v36[96]; // [rsp+50h] [rbp-308h] BYREF
  _WORD v37[256]; // [rsp+110h] [rbp-248h] BYREF

  for ( i = 0; i != 20; ++i )
  {
    v9 = *a1 >> 28;
    fillbuf((__int64)a1, 4);
    v35[i] = v9;
  }
  if ( a1[15] )
    return 0;
  make_table(v10, 20, (__int64)v35, 8u, (char *)v37, (__int64)v36);
  for ( j = 0; j < a2; ++j )
  {
    v12 = v37[(unsigned __int64)*a1 >> 24];
    if ( v12 < 0 )
    {
      v13 = 0x800000;
      do
      {
        v14 = -v12;
        v15 = 2 * v14 + 1LL;
        if ( (*a1 & v13) == 0 )
          v15 = 2 * v14;
        v13 >>= 1;
        v12 = v36[v15];
      }
      while ( v12 < 0 );
    }
    fillbuf((__int64)a1, v35[(unsigned __int16)v12]);
    if ( a1[15] )
      return 0;
    switch ( v12 )
    {
      case 17:
        v16 = *a1 >> 28;
        fillbuf((__int64)a1, 4);
        v17 = v16 + 4;
        v18 = j + v16 + 4;
        v19 = a2 - j;
        if ( v18 < a2 )
          v19 = v17;
        if ( v19 > 0 )
        {
          memset_0((void *)(a4 + j), 0, v19);
          do
          {
            --v19;
            ++j;
          }
          while ( v19 > 0 );
        }
        break;
      case 18:
        v20 = *a1 >> 27;
        fillbuf((__int64)a1, 5);
        v21 = v20 + 20;
        v22 = j + v20 + 20;
        v23 = a2 - j;
        if ( v22 < a2 )
          v23 = v21;
        if ( v23 > 0 )
        {
          memset_0((void *)(a4 + j), 0, v23);
          do
          {
            --v23;
            ++j;
          }
          while ( v23 > 0 );
        }
        break;
      case 19:
        v24 = *a1 >> 31;
        fillbuf((__int64)a1, 1);
        v25 = *a1;
        v26 = v24 + 4;
        v27 = j + v24 + 4;
        v28 = a2 - j;
        if ( v27 < a2 )
          v28 = v26;
        v29 = v37[(unsigned __int64)v25 >> 24];
        if ( v29 < 0 )
        {
          v30 = 0x800000;
          do
          {
            v31 = -v29;
            v32 = 2 * v31 + 1LL;
            if ( (v25 & v30) == 0 )
              v32 = 2 * v31;
            v30 >>= 1;
            v29 = v36[v32];
          }
          while ( v29 < 0 );
        }
        fillbuf((__int64)a1, v35[(unsigned __int16)v29]);
        if ( v28 > 0 )
        {
          v33 = *(unsigned __int8 *)(j + a3) - (unsigned __int64)(unsigned __int16)v29;
          LOBYTE(v33) = *((_BYTE *)&qword_18000BE30[2] + v33 + 1);
          memset_0((void *)(a4 + j), v33, v28);
          do
          {
            --v28;
            ++j;
          }
          while ( v28 > 0 );
        }
        break;
      default:
        *(_BYTE *)(j + a4) = *((_BYTE *)&qword_18000BE30[2]
                             + *(unsigned __int8 *)(j + a3)
                             - (unsigned __int64)(unsigned __int16)v12
                             + 1);
        continue;
    }
    --j;
  }
  return a1[15] == 0;
}

```

## disassembly

```asm
0x1800087b0  mov     [rsp+arg_8], rbx
0x1800087b5  push    rbp
0x1800087b6  push    rsi
0x1800087b7  push    rdi
0x1800087b8  push    r12
0x1800087ba  push    r13
0x1800087bc  push    r14
0x1800087be  push    r15
0x1800087c0  sub     rsp, 320h
0x1800087c7  mov     rax, cs:__security_cookie
0x1800087ce  xor     rax, rsp
0x1800087d1  mov     [rsp+358h+var_48], rax
0x1800087d9  xor     r13d, r13d
0x1800087dc  mov     r15, r9
0x1800087df  mov     edi, r13d
0x1800087e2  mov     r12, r8
0x1800087e5  mov     r14d, edx
0x1800087e8  mov     rsi, rcx
0x1800087eb  mov     ebx, [rsi]
0x1800087ed  mov     edx, 4
0x1800087f2  mov     rcx, rsi
0x1800087f5  shr     ebx, 1Ch
0x1800087f8  call    fillbuf
0x1800087fd  mov     [rsp+rdi+358h+var_328], bl
0x180008801  inc     rdi
0x180008804  cmp     rdi, 14h
0x180008808  jnz     short loc_1800087EB
0x18000880a  cmp     [rsi+3Ch], r13d
0x18000880e  jnz     loc_180008A2C
0x180008814  lea     rax, [rsp+358h+var_308]
0x180008819  mov     r9b, 8; int
0x18000881c  mov     [rsp+358h+var_330], rax; __int64
0x180008821  lea     r8, [rsp+358h+var_328]; int
0x180008826  lea     rax, [rsp+358h+var_248]
0x18000882e  mov     edx, edi; int
0x180008830  mov     [rsp+358h+var_338], rax; void *
0x180008835  call    make_table
0x18000883a  mov     edi, r13d
0x18000883d  test    r14d, r14d
0x180008840  jle     loc_180008A20
0x180008846  lea     rbp, qword_18000BE30
0x18000884d  mov     edx, [rsi]
0x18000884f  mov     eax, edx
0x180008851  shr     rax, 18h
0x180008855  movzx   ebx, [rsp+rax*2+358h+var_248]
0x18000885d  test    bx, bx
0x180008860  jns     short loc_18000888B
0x180008862  mov     r8d, 800000h
0x180008868  neg     bx
0x18000886b  movsx   eax, bx
0x18000886e  add     eax, eax
0x180008870  test    r8d, edx
0x180008873  movsxd  rcx, eax
0x180008876  lea     rax, [rcx+1]
0x18000887a  cmovz   rax, rcx
0x18000887e  shr     r8d, 1
0x180008881  movzx   ebx, [rsp+rax*2+358h+var_308]
0x180008886  test    bx, bx
0x180008889  js      short loc_180008868
0x18000888b  movzx   eax, bx
0x18000888e  mov     rcx, rsi
0x180008891  movzx   edx, [rsp+rax+358h+var_328]
0x180008896  call    fillbuf
0x18000889b  cmp     [rsi+3Ch], r13d
0x18000889f  jnz     loc_180008A2C
0x1800088a5  cmp     bx, 11h
0x1800088a9  jnz     short loc_1800088F5
0x1800088ab  mov     ebx, [rsi]
0x1800088ad  mov     edx, 4
0x1800088b2  mov     rcx, rsi
0x1800088b5  shr     ebx, 1Ch
0x1800088b8  call    fillbuf
0x1800088bd  lea     ecx, [rbx+4]
0x1800088c0  lea     eax, [rbx+4]
0x1800088c3  add     ecx, edi
0x1800088c5  mov     ebx, r14d
0x1800088c8  sub     ebx, edi
0x1800088ca  cmp     ecx, r14d
0x1800088cd  cmovl   ebx, eax
0x1800088d0  test    ebx, ebx
0x1800088d2  jle     loc_1800089FB
0x1800088d8  movsxd  rcx, edi
0x1800088db  xor     edx, edx; Val
0x1800088dd  add     rcx, r15; void *
0x1800088e0  movsxd  r8, ebx; Size
0x1800088e3  call    memset_0
0x1800088e8  dec     ebx
0x1800088ea  inc     edi
0x1800088ec  test    ebx, ebx
0x1800088ee  jg      short loc_1800088E8
0x1800088f0  jmp     loc_1800089FB
0x1800088f5  cmp     bx, 12h
0x1800088f9  jnz     short loc_180008945
0x1800088fb  mov     ebx, [rsi]
0x1800088fd  mov     edx, 5
0x180008902  mov     rcx, rsi
0x180008905  shr     ebx, 1Bh
0x180008908  call    fillbuf
0x18000890d  lea     ecx, [rbx+14h]
0x180008910  lea     eax, [rbx+14h]
0x180008913  add     ecx, edi
0x180008915  mov     ebx, r14d
0x180008918  sub     ebx, edi
0x18000891a  cmp     ecx, r14d
0x18000891d  cmovl   ebx, eax
0x180008920  test    ebx, ebx
0x180008922  jle     loc_1800089FB
0x180008928  movsxd  rcx, edi
0x18000892b  xor     edx, edx; Val
0x18000892d  add     rcx, r15; void *
0x180008930  movsxd  r8, ebx; Size
0x180008933  call    memset_0
0x180008938  dec     ebx
0x18000893a  inc     edi
0x18000893c  test    ebx, ebx
0x18000893e  jg      short loc_180008938
0x180008940  jmp     loc_1800089FB
0x180008945  cmp     bx, 13h
0x180008949  jnz     loc_1800089FF
0x18000894f  mov     ebx, [rsi]
0x180008951  mov     edx, 1
0x180008956  mov     rcx, rsi
0x180008959  shr     ebx, 1Fh
0x18000895c  call    fillbuf
0x180008961  mov     r8d, [rsi]
0x180008964  lea     ecx, [rbx+4]
0x180008967  lea     eax, [rbx+4]
0x18000896a  add     ecx, edi
0x18000896c  mov     ebx, r14d
0x18000896f  sub     ebx, edi
0x180008971  cmp     ecx, r14d
0x180008974  cmovl   ebx, eax
0x180008977  mov     eax, r8d
0x18000897a  shr     rax, 18h
0x18000897e  movzx   ebp, [rsp+rax*2+358h+var_248]
0x180008986  test    bp, bp
0x180008989  jns     short loc_1800089B2
0x18000898b  mov     edx, 800000h
0x180008990  neg     bp
0x180008993  movsx   eax, bp
0x180008996  add     eax, eax
0x180008998  test    edx, r8d
0x18000899b  movsxd  rcx, eax
0x18000899e  lea     rax, [rcx+1]
0x1800089a2  cmovz   rax, rcx
0x1800089a6  shr     edx, 1
0x1800089a8  movzx   ebp, [rsp+rax*2+358h+var_308]
0x1800089ad  test    bp, bp
0x1800089b0  js      short loc_180008990
0x1800089b2  movzx   eax, bp
0x1800089b5  mov     rcx, rsi
0x1800089b8  movzx   edx, [rsp+rax+358h+var_328]
0x1800089bd  call    fillbuf
0x1800089c2  test    ebx, ebx
0x1800089c4  jle     short loc_1800089F4
0x1800089c6  movzx   eax, bp
0x1800089c9  lea     rbp, qword_18000BE30
0x1800089d0  movsxd  rcx, edi
0x1800089d3  movsxd  r8, ebx; Size
0x1800089d6  movzx   edx, byte ptr [rcx+r12]
0x1800089db  add     rcx, r15; void *
0x1800089de  sub     rdx, rax
0x1800089e1  mov     dl, [rdx+rbp+11h]; Val
0x1800089e5  call    memset_0
0x1800089ea  dec     ebx
0x1800089ec  inc     edi
0x1800089ee  test    ebx, ebx
0x1800089f0  jg      short loc_1800089EA
0x1800089f2  jmp     short loc_1800089FB
0x1800089f4  lea     rbp, qword_18000BE30
0x1800089fb  dec     edi
0x1800089fd  jmp     short loc_180008A15
0x1800089ff  movsxd  rdx, edi
0x180008a02  movzx   eax, bx
0x180008a05  movzx   ecx, byte ptr [rdx+r12]
0x180008a0a  sub     rcx, rax
0x180008a0d  mov     al, [rcx+rbp+11h]
0x180008a11  mov     [rdx+r15], al
0x180008a15  inc     edi
0x180008a17  cmp     edi, r14d
0x180008a1a  jl      loc_18000884D
0x180008a20  cmp     [rsi+3Ch], r13d
0x180008a24  mov     eax, r13d
0x180008a27  setz    al
0x180008a2a  jmp     short loc_180008A2E
0x180008a2c  xor     eax, eax
0x180008a2e  mov     rcx, [rsp+358h+var_48]
0x180008a36  xor     rcx, rsp; StackCookie
0x180008a39  call    __security_check_cookie
0x180008a3e  mov     rbx, [rsp+358h+arg_8]
0x180008a46  add     rsp, 320h
0x180008a4d  pop     r15
0x180008a4f  pop     r14
0x180008a51  pop     r13
0x180008a53  pop     r12
0x180008a55  pop     rdi
0x180008a56  pop     rsi
0x180008a57  pop     rbp
0x180008a58  retn
```
