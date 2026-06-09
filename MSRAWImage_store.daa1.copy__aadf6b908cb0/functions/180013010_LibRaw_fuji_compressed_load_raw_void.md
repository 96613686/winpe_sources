# LibRaw::fuji_compressed_load_raw(void)

- ea: `0x180013010`
- end: `0x180013281`
- name: `?fuji_compressed_load_raw@LibRaw@@IEAAXXZ`
- size: `625`
- prototype: `void __fastcall(LibRaw *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002a00`
- `0x180003e4c`
- `0x180009220`
- `0x180009470`
- `0x180013010`
- `0x1800146a0`
- `0x1800b4010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LibRaw::fuji_compressed_load_raw(LibRaw *this)
{
  int v1; // ebp
  void *v2; // r13
  char *v4; // r15
  _QWORD *v5; // r12
  int v6; // esi
  int v7; // ebx
  __int64 v8; // rcx
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rbx
  __int64 v11; // r8
  char *v12; // rax
  int v13; // ecx
  int v14; // edx
  _QWORD *v15; // rcx
  char *v16; // rdx
  __int64 v17; // rax
  int pExceptionObject; // [rsp+40h] [rbp-E8h] BYREF
  _BYTE v19[128]; // [rsp+50h] [rbp-D8h] BYREF
  void *v20; // [rsp+D0h] [rbp-58h]

  v1 = 0;
  v2 = 0;
  LibRaw::init_fuji_compr(this, (struct fuji_compressed_params *)v19);
  v4 = (char *)LibRaw::malloc(this, 4LL * *((int *)this + 95392));
  v5 = LibRaw::malloc(this, 8LL * *((int *)this + 95392));
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
    *((_QWORD *)this + 47659),
    *((_QWORD *)this + 47680),
    0);
  v6 = 1;
  v7 = 4 * *((_DWORD *)this + 95392);
  if ( (*(unsigned int (__fastcall **)(_QWORD, char *, __int64, _QWORD))(**((_QWORD **)this + 47659) + 16LL))(
         *((_QWORD *)this + 47659),
         v4,
         1,
         v7) != v7 )
  {
    LibRaw::free(this, v4);
    LibRaw::free(this, v5);
    pExceptionObject = 4;
    throw (LibRaw_exceptions *)&pExceptionObject;
  }
  v8 = *((int *)this + 95392);
  v9 = (4 * v8 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
  if ( !*((_DWORD *)this + 95396) )
  {
    v10 = (int)(v8 * ((*((_DWORD *)this + 95391) + 15) & 0xFFFFFFF0));
    v2 = LibRaw::malloc(this, v10);
    (*(void (__fastcall **)(_QWORD, unsigned __int64, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
      *((_QWORD *)this + 47659),
      v9 + *((_QWORD *)this + 47680),
      0);
    (*(void (__fastcall **)(_QWORD, void *, __int64, unsigned __int64))(**((_QWORD **)this + 47659) + 16LL))(
      *((_QWORD *)this + 47659),
      v2,
      1,
      v10);
    v9 += v10;
  }
  *v5 = v9 + *((_QWORD *)this + 47680);
  v11 = *((unsigned int *)this + 95392);
  if ( (int)v11 > 0 )
  {
    v12 = v4 + 2;
    do
    {
      v13 = (unsigned __int8)*(v12 - 2);
      ++v1;
      v14 = (unsigned __int8)*(v12 - 1);
      v12 += 4;
      *(_DWORD *)(v12 - 6) = (unsigned __int8)*(v12 - 3)
                           | (((unsigned __int8)*(v12 - 4) | (((v13 << 8) | v14) << 8)) << 8);
      v11 = *((unsigned int *)this + 95392);
    }
    while ( v1 < (int)v11 );
  }
  if ( (int)v11 > 1 )
  {
    v15 = v5 + 1;
    v16 = v4;
    do
    {
      v17 = *(unsigned int *)v16;
      v16 += 4;
      ++v6;
      *v15 = *(v15 - 1) + v17;
      ++v15;
      v11 = *((unsigned int *)this + 95392);
    }
    while ( v6 < (int)v11 );
  }
  (*(void (__fastcall **)(LibRaw *, _BYTE *, __int64, _QWORD *, char *, void *))(*(_QWORD *)this + 136LL))(
    this,
    v19,
    v11,
    v5,
    v4,
    v2);
  LibRaw::free(this, v2);
  LibRaw::free(this, v4);
  LibRaw::free(this, v5);
  LibRaw::free(this, v20);
}

```

## disassembly

```asm
0x180013010  mov     [rsp+arg_10], rbx
0x180013015  mov     [rsp+arg_18], rbp
0x18001301a  push    rsi
0x18001301b  push    rdi
0x18001301c  push    r12
0x18001301e  push    r13
0x180013020  push    r15
0x180013022  sub     rsp, 100h
0x180013029  mov     rax, cs:__security_cookie
0x180013030  xor     rax, rsp
0x180013033  mov     [rsp+128h+var_38], rax
0x18001303b  xor     ebp, ebp
0x18001303d  lea     rdx, [rsp+128h+var_D8]; struct fuji_compressed_params *
0x180013042  mov     r13d, ebp
0x180013045  mov     rdi, rcx
0x180013048  call    ?init_fuji_compr@LibRaw@@IEAAXPEAUfuji_compressed_params@@@Z; LibRaw::init_fuji_compr(fuji_compressed_params *)
0x18001304d  movsxd  rdx, dword ptr [rdi+5D280h]
0x180013054  mov     rcx, rdi; this
0x180013057  shl     rdx, 2; unsigned __int64
0x18001305b  call    ?malloc@LibRaw@@IEAAPEAX_K@Z; LibRaw::malloc(unsigned __int64)
0x180013060  movsxd  rdx, dword ptr [rdi+5D280h]
0x180013067  mov     rcx, rdi; this
0x18001306a  shl     rdx, 3; unsigned __int64
0x18001306e  mov     r15, rax
0x180013071  call    ?malloc@LibRaw@@IEAAPEAX_K@Z; LibRaw::malloc(unsigned __int64)
0x180013076  mov     rcx, [rdi+5D158h]
0x18001307d  mov     r12, rax
0x180013080  mov     rdx, [rdi+5D200h]
0x180013087  xor     r8d, r8d
0x18001308a  mov     rax, [rcx]
0x18001308d  mov     rax, [rax+18h]
0x180013091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013096  mov     rcx, [rdi+5D158h]
0x18001309d  mov     esi, 1
0x1800130a2  mov     ebx, [rdi+5D280h]
0x1800130a8  mov     r8d, esi
0x1800130ab  shl     ebx, 2
0x1800130ae  mov     rdx, r15
0x1800130b1  movsxd  r9, ebx
0x1800130b4  mov     rax, [rcx]
0x1800130b7  mov     rax, [rax+10h]
0x1800130bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130c0  cmp     eax, ebx
0x1800130c2  jnz     loc_180013251
0x1800130c8  movsxd  rcx, dword ptr [rdi+5D280h]
0x1800130cf  mov     [rsp+128h+arg_8], r14
0x1800130d7  lea     r14, ds:0Fh[rcx*4]
0x1800130df  and     r14, 0FFFFFFFFFFFFFFF0h
0x1800130e3  cmp     [rdi+5D290h], ebp
0x1800130e9  jnz     short loc_18001314A
0x1800130eb  mov     eax, [rdi+5D27Ch]
0x1800130f1  add     eax, 0Fh
0x1800130f4  and     eax, 0FFFFFFF0h
0x1800130f7  imul    eax, ecx
0x1800130fa  mov     rcx, rdi; this
0x1800130fd  movsxd  rbx, eax
0x180013100  mov     rdx, rbx; unsigned __int64
0x180013103  call    ?malloc@LibRaw@@IEAAPEAX_K@Z; LibRaw::malloc(unsigned __int64)
0x180013108  mov     rcx, [rdi+5D158h]
0x18001310f  mov     r13, rax
0x180013112  mov     rdx, [rdi+5D200h]
0x180013119  add     rdx, r14
0x18001311c  mov     r8, [rcx]
0x18001311f  mov     rax, [r8+18h]
0x180013123  xor     r8d, r8d
0x180013126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001312b  mov     rcx, [rdi+5D158h]
0x180013132  mov     r9, rbx
0x180013135  mov     r8d, esi
0x180013138  mov     rdx, [rcx]
0x18001313b  mov     rax, [rdx+10h]
0x18001313f  mov     rdx, r13
0x180013142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013147  add     r14, rbx
0x18001314a  mov     rcx, [rdi+5D200h]
0x180013151  add     rcx, r14
0x180013154  mov     r14, [rsp+128h+arg_8]
0x18001315c  mov     [r12], rcx
0x180013160  mov     r8d, [rdi+5D280h]
0x180013167  test    r8d, r8d
0x18001316a  jle     short loc_1800131A4
0x18001316c  lea     rax, [r15+2]
0x180013170  movzx   ecx, byte ptr [rax-2]
0x180013174  inc     ebp
0x180013176  movzx   edx, byte ptr [rax-1]
0x18001317a  lea     rax, [rax+4]
0x18001317e  shl     ecx, 8
0x180013181  or      edx, ecx
0x180013183  movzx   ecx, byte ptr [rax-4]
0x180013187  shl     edx, 8
0x18001318a  or      edx, ecx
0x18001318c  movzx   ecx, byte ptr [rax-3]
0x180013190  shl     edx, 8
0x180013193  or      edx, ecx
0x180013195  mov     [rax-6], edx
0x180013198  mov     r8d, [rdi+5D280h]
0x18001319f  cmp     ebp, r8d
0x1800131a2  jl      short loc_180013170
0x1800131a4  cmp     r8d, esi
0x1800131a7  jle     short loc_1800131D0
0x1800131a9  lea     rcx, [r12+8]
0x1800131ae  mov     rdx, r15
0x1800131b1  mov     eax, [rdx]
0x1800131b3  lea     rdx, [rdx+4]
0x1800131b7  add     rax, [rcx-8]
0x1800131bb  inc     esi
0x1800131bd  mov     [rcx], rax
0x1800131c0  lea     rcx, [rcx+8]
0x1800131c4  mov     r8d, [rdi+5D280h]
0x1800131cb  cmp     esi, r8d
0x1800131ce  jl      short loc_1800131B1
0x1800131d0  mov     rax, [rdi]
0x1800131d3  lea     rdx, [rsp+128h+var_D8]
0x1800131d8  mov     [rsp+128h+var_100], r13
0x1800131dd  mov     r9, r12
0x1800131e0  mov     rcx, rdi
0x1800131e3  mov     [rsp+128h+var_108], r15
0x1800131e8  mov     rax, [rax+88h]
0x1800131ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131f4  mov     rdx, r13; void *
0x1800131f7  mov     rcx, rdi; this
0x1800131fa  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x1800131ff  mov     rdx, r15; void *
0x180013202  mov     rcx, rdi; this
0x180013205  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x18001320a  mov     rdx, r12; void *
0x18001320d  mov     rcx, rdi; this
0x180013210  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180013215  mov     rdx, [rsp+128h+var_58]; void *
0x18001321d  mov     rcx, rdi; this
0x180013220  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180013225  mov     rcx, [rsp+128h+var_38]
0x18001322d  xor     rcx, rsp; StackCookie
0x180013230  call    __security_check_cookie
0x180013235  lea     r11, [rsp+128h+var_28]
0x18001323d  mov     rbx, [r11+40h]
0x180013241  mov     rbp, [r11+48h]
0x180013245  mov     rsp, r11
0x180013248  pop     r15
0x18001324a  pop     r13
0x18001324c  pop     r12
0x18001324e  pop     rdi
0x18001324f  pop     rsi
0x180013250  retn
0x180013251  mov     rdx, r15; void *
0x180013254  mov     rcx, rdi; this
0x180013257  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x18001325c  mov     rdx, r12; void *
0x18001325f  mov     rcx, rdi; this
0x180013262  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180013267  lea     rdx, _TI1?AW4LibRaw_exceptions@@; pThrowInfo
0x18001326e  mov     [rsp+128h+pExceptionObject], 4
0x180013276  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18001327b  call    _CxxThrowException
```
