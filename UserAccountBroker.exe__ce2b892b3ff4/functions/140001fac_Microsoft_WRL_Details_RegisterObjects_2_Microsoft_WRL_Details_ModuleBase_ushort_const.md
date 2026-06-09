# Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)

- ea: `0x140001fac`
- end: `0x1400022ea`
- name: `??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z`
- size: `830`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003eb4`

## callees

- `0x140001184`
- `0x14000164c`
- `0x140001fac`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RegisterObjects<2>(__int64 a1, __int64 a2)
{
  int v3; // edi
  unsigned __int64 v4; // r15
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // r13
  _QWORD *v7; // rcx
  unsigned int v8; // eax
  unsigned __int64 v9; // rax
  void *v10; // r14
  unsigned __int64 v11; // rax
  _QWORD *v12; // r12
  unsigned __int64 v13; // rax
  void *v14; // rax
  void *v15; // rcx
  __int64 v16; // rbx
  unsigned __int64 v17; // r14
  __int64 (__fastcall **v18)(__int64 *, _QWORD, GUID *, __int64 *); // rax
  __int64 v19; // r8
  int v20; // eax
  __int64 i; // rbp
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rbx
  unsigned int v24; // r8d
  unsigned __int64 v25; // r14
  _QWORD *v26; // r9
  unsigned int v27; // ecx
  unsigned __int64 v28; // rax
  _QWORD *v29; // r15
  __int64 v30; // rbp
  unsigned __int64 v31; // rdi
  void *Block; // [rsp+90h] [rbp+8h]
  __int64 v34; // [rsp+98h] [rbp+10h] BYREF
  void *v35; // [rsp+A0h] [rbp+18h]
  __int64 v36; // [rsp+A8h] [rbp+20h] BYREF

  v34 = a2;
  v3 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1) + 8;
  LODWORD(v5) = 0;
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
  v7 = (_QWORD *)v4;
  if ( v4 >= v6 )
    goto LABEL_35;
  do
  {
    v8 = v5 + 1;
    if ( !*v7 )
      v8 = v5;
    ++v7;
    v5 = v8;
  }
  while ( (unsigned __int64)v7 < v6 );
  if ( !v8 )
    goto LABEL_35;
  v9 = 4LL * v8;
  if ( !is_mul_ok(v5, 4u) )
    v9 = -1;
  v10 = operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  Block = v10;
  v11 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v11 = -1;
  v12 = operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  v13 = 16 * v5;
  if ( !is_mul_ok(v5, 0x10u) )
    v13 = -1;
  v14 = operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
  v35 = v14;
  v15 = v14;
  if ( v10 && v12 && v14 )
  {
    v16 = 0;
    v17 = v4;
    do
    {
      if ( v3 < 0 )
      {
        v10 = Block;
        goto LABEL_30;
      }
      v18 = *(__int64 (__fastcall ***)(__int64 *, _QWORD, GUID *, __int64 *))v17;
      if ( *(_QWORD *)v17 )
      {
        LODWORD(v34) = 2;
        v36 = 0;
        v3 = (*v18)(&v34, v18, &GUID_00000001_0000_0000_c000_000000000046, &v36);
        if ( v3 < 0 )
        {
          v15 = v35;
        }
        else
        {
          v12[v16] = v36;
          v19 = 2LL * (unsigned int)v16;
          v16 = (unsigned int)(v16 + 1);
          v15 = v35;
          *(_OWORD *)((char *)v35 + 8 * v19) = *(_OWORD *)*(_QWORD *)(*(_QWORD *)v17 + 8LL);
        }
      }
      v17 += 8LL;
    }
    while ( v17 < v6 );
    v10 = Block;
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, void *, _QWORD *, void *, _DWORD))(*(_QWORD *)a1 + 80LL))(
             a1,
             0,
             v15,
             v12,
             Block,
             v5);
      if ( v3 >= 0 )
      {
        v16 = 0;
        do
        {
          if ( *(_QWORD *)v4 )
          {
            v20 = *((_DWORD *)Block + v16);
            v16 = (unsigned int)(v16 + 1);
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v4 + 24LL) + 8LL) = v20;
          }
          v4 += 8LL;
        }
        while ( v4 < v6 );
      }
    }
LABEL_30:
    for ( i = 0; (unsigned int)i < (unsigned int)v16; i = (unsigned int)(i + 1) )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12[i] + 16LL))(v12[i]);
  }
  else
  {
    v3 = -2147024882;
  }
  operator delete(v10);
  operator delete(v35);
  operator delete(v12);
  if ( v3 >= 0 )
  {
LABEL_35:
    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1);
    v23 = v6 + 8;
    v24 = 0;
    v25 = v22;
    v26 = (_QWORD *)(v6 + 8);
    if ( v6 + 8 < v22 )
    {
      do
      {
        v27 = v24 + 1;
        if ( !*v26 )
          v27 = v24;
        ++v26;
        v24 = v27;
      }
      while ( (unsigned __int64)v26 < v22 );
      if ( v27 )
      {
        v28 = 8LL * v27;
        if ( !is_mul_ok(v27, 8u) )
          v28 = -1;
        v29 = operator new[](v28, (const struct std::nothrow_t *)&std::nothrow);
        if ( v29 )
        {
          v34 = 0;
          v30 = 0;
          v31 = v6 + 8;
          do
          {
            if ( *(_QWORD *)v31 )
            {
              v29[v30] = (*(__int64 (**)(void))(*(_QWORD *)v31 + 8LL))();
              v30 = (unsigned int)(v30 + 1);
            }
            v31 += 8LL;
          }
          while ( v31 < v25 );
          v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, __int64 *, _DWORD))(*(_QWORD *)a1 + 64LL))(
                 a1,
                 0,
                 v29,
                 &v34,
                 v30);
          if ( v3 >= 0 )
          {
            do
            {
              if ( *(_QWORD *)v23 )
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v23 + 24LL) + 8LL) = v34;
              v23 += 8LL;
            }
            while ( v23 < v25 );
          }
        }
        else
        {
          v3 = -2147024882;
        }
        operator delete(v29);
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140001fac  mov     [rsp+arg_8], rdx
0x140001fb1  push    rbx
0x140001fb2  push    rbp
0x140001fb3  push    rsi
0x140001fb4  push    rdi
0x140001fb5  push    r12
0x140001fb7  push    r13
0x140001fb9  push    r14
0x140001fbb  push    r15
0x140001fbd  sub     rsp, 48h
0x140001fc1  mov     rax, [rcx]
0x140001fc4  mov     rsi, rcx
0x140001fc7  xor     edi, edi
0x140001fc9  mov     rax, [rax+20h]
0x140001fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001fd2  mov     r15, rax
0x140001fd5  mov     rcx, rsi
0x140001fd8  mov     rax, [rsi]
0x140001fdb  mov     rax, [rax+28h]
0x140001fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001fe4  add     r15, 8
0x140001fe8  xor     ebp, ebp
0x140001fea  or      r12, 0FFFFFFFFFFFFFFFFh
0x140001fee  mov     r13, rax
0x140001ff1  mov     rcx, r15
0x140001ff4  cmp     r15, rax
0x140001ff7  jnb     loc_1400021E4
0x140001ffd  cmp     [rcx], rdi
0x140002000  lea     eax, [rbp+1]
0x140002003  cmovz   eax, ebp
0x140002006  add     rcx, 8
0x14000200a  mov     ebp, eax
0x14000200c  cmp     rcx, r13
0x14000200f  jb      short loc_140001FFD
0x140002011  test    eax, eax
0x140002013  jz      loc_1400021E4
0x140002019  mov     eax, 4
0x14000201e  mul     rbp
0x140002021  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140002028  cmovb   rax, r12
0x14000202c  mov     rcx, rax; unsigned __int64
0x14000202f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140002034  mov     r14, rax
0x140002037  mov     [rsp+88h+Block], rax
0x14000203f  mov     eax, 8
0x140002044  mul     rbp
0x140002047  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000204e  cmovb   rax, r12
0x140002052  mov     rcx, rax; unsigned __int64
0x140002055  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000205a  mov     r12, rax
0x14000205d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140002064  mov     eax, 10h
0x140002069  mul     rbp
0x14000206c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140002073  cmovb   rax, rcx
0x140002077  mov     rcx, rax; unsigned __int64
0x14000207a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000207f  mov     [rsp+88h+arg_10], rax
0x140002087  mov     rcx, rax
0x14000208a  test    r14, r14
0x14000208d  jz      loc_1400021B6
0x140002093  test    r12, r12
0x140002096  jz      loc_1400021B6
0x14000209c  test    rax, rax
0x14000209f  jz      loc_1400021B6
0x1400020a5  xor     ebx, ebx
0x1400020a7  mov     r14, r15
0x1400020aa  test    edi, edi
0x1400020ac  js      loc_140002190
0x1400020b2  mov     rax, [r14]
0x1400020b5  test    rax, rax
0x1400020b8  jz      short loc_14000212F
0x1400020ba  mov     dword ptr [rsp+88h+arg_8], 2
0x1400020c5  lea     r9, [rsp+88h+arg_18]
0x1400020cd  mov     [rsp+88h+arg_18], 0
0x1400020d9  lea     r8, _GUID_00000001_0000_0000_c000_000000000046
0x1400020e0  mov     rdx, rax
0x1400020e3  lea     rcx, [rsp+88h+arg_8]
0x1400020eb  mov     rax, [rax]
0x1400020ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020f3  mov     edi, eax
0x1400020f5  test    eax, eax
0x1400020f7  js      short loc_140002127
0x1400020f9  mov     rcx, [rsp+88h+arg_18]
0x140002101  mov     [r12+rbx*8], rcx
0x140002105  mov     rcx, [r14]
0x140002108  mov     r8d, ebx
0x14000210b  add     r8, r8
0x14000210e  inc     ebx
0x140002110  mov     rdx, [rcx+8]
0x140002114  mov     rcx, [rsp+88h+arg_10]
0x14000211c  movups  xmm0, xmmword ptr [rdx]
0x14000211f  movdqu  xmmword ptr [rcx+r8*8], xmm0
0x140002125  jmp     short loc_14000212F
0x140002127  mov     rcx, [rsp+88h+arg_10]
0x14000212f  add     r14, 8
0x140002133  cmp     r14, r13
0x140002136  jb      loc_1400020AA
0x14000213c  mov     r14, [rsp+88h+Block]
0x140002144  test    edi, edi
0x140002146  js      short loc_140002198
0x140002148  mov     rax, [rsi]
0x14000214b  mov     r8, rcx
0x14000214e  mov     [rsp+88h+var_60], ebp
0x140002152  mov     r9, r12
0x140002155  xor     edx, edx
0x140002157  mov     [rsp+88h+var_68], r14
0x14000215c  mov     rcx, rsi
0x14000215f  mov     rax, [rax+50h]
0x140002163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002168  mov     edi, eax
0x14000216a  test    eax, eax
0x14000216c  js      short loc_140002198
0x14000216e  xor     ebx, ebx
0x140002170  mov     rcx, [r15]
0x140002173  test    rcx, rcx
0x140002176  jz      short loc_140002185
0x140002178  mov     eax, [r14+rbx*4]
0x14000217c  inc     ebx
0x14000217e  mov     rcx, [rcx+18h]
0x140002182  mov     [rcx+8], eax
0x140002185  add     r15, 8
0x140002189  cmp     r15, r13
0x14000218c  jb      short loc_140002170
0x14000218e  jmp     short loc_140002198
0x140002190  mov     r14, [rsp+88h+Block]
0x140002198  xor     ebp, ebp
0x14000219a  test    ebx, ebx
0x14000219c  jz      short loc_1400021BB
0x14000219e  mov     rcx, [r12+rbp*8]
0x1400021a2  mov     rax, [rcx]
0x1400021a5  mov     rax, [rax+10h]
0x1400021a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400021ae  inc     ebp
0x1400021b0  cmp     ebp, ebx
0x1400021b2  jb      short loc_14000219E
0x1400021b4  jmp     short loc_1400021BB
0x1400021b6  mov     edi, 8007000Eh
0x1400021bb  mov     rcx, r14; Block
0x1400021be  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400021c3  mov     rcx, [rsp+88h+arg_10]; Block
0x1400021cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400021d0  mov     rcx, r12; Block
0x1400021d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400021d8  test    edi, edi
0x1400021da  js      loc_1400022D7
0x1400021e0  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400021e4  mov     rax, [rsi]
0x1400021e7  mov     rcx, rsi
0x1400021ea  mov     rax, [rax+30h]
0x1400021ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400021f3  lea     rbx, [r13+8]
0x1400021f7  xor     r8d, r8d
0x1400021fa  mov     r14, rax
0x1400021fd  mov     r9, rbx
0x140002200  cmp     rbx, rax
0x140002203  jnb     loc_1400022D7
0x140002209  cmp     qword ptr [r9], 0
0x14000220d  lea     ecx, [r8+1]
0x140002211  cmovz   ecx, r8d
0x140002215  add     r9, 8
0x140002219  mov     r8d, ecx
0x14000221c  cmp     r9, r14
0x14000221f  jb      short loc_140002209
0x140002221  test    ecx, ecx
0x140002223  jz      loc_1400022D7
0x140002229  mov     eax, 8
0x14000222e  mul     r8
0x140002231  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140002238  cmovb   rax, r12
0x14000223c  mov     rcx, rax; unsigned __int64
0x14000223f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140002244  mov     r15, rax
0x140002247  test    rax, rax
0x14000224a  jnz     short loc_140002253
0x14000224c  mov     edi, 8007000Eh
0x140002251  jmp     short loc_1400022CF
0x140002253  test    edi, edi
0x140002255  js      short loc_1400022CF
0x140002257  mov     [rsp+88h+arg_8], 0
0x140002263  xor     ebp, ebp
0x140002265  mov     rdi, rbx
0x140002268  mov     rax, [rdi]
0x14000226b  test    rax, rax
0x14000226e  jz      short loc_14000227F
0x140002270  mov     rax, [rax+8]
0x140002274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002279  mov     [r15+rbp*8], rax
0x14000227d  inc     ebp
0x14000227f  add     rdi, 8
0x140002283  cmp     rdi, r14
0x140002286  jb      short loc_140002268
0x140002288  mov     rax, [rsi]
0x14000228b  lea     r9, [rsp+88h+arg_8]
0x140002293  mov     r8, r15
0x140002296  mov     dword ptr [rsp+88h+var_68], ebp
0x14000229a  xor     edx, edx
0x14000229c  mov     rcx, rsi
0x14000229f  mov     rax, [rax+40h]
0x1400022a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022a8  mov     edi, eax
0x1400022aa  test    eax, eax
0x1400022ac  js      short loc_1400022CF
0x1400022ae  mov     rcx, [rbx]
0x1400022b1  test    rcx, rcx
0x1400022b4  jz      short loc_1400022C6
0x1400022b6  mov     rcx, [rcx+18h]
0x1400022ba  mov     rax, [rsp+88h+arg_8]
0x1400022c2  mov     [rcx+8], rax
0x1400022c6  add     rbx, 8
0x1400022ca  cmp     rbx, r14
0x1400022cd  jb      short loc_1400022AE
0x1400022cf  mov     rcx, r15; Block
0x1400022d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400022d7  mov     eax, edi
0x1400022d9  add     rsp, 48h
0x1400022dd  pop     r15
0x1400022df  pop     r14
0x1400022e1  pop     r13
0x1400022e3  pop     r12
0x1400022e5  pop     rdi
0x1400022e6  pop     rsi
0x1400022e7  pop     rbp
0x1400022e8  pop     rbx
0x1400022e9  retn
```
