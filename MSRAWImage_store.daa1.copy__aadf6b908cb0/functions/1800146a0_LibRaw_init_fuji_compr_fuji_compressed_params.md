# LibRaw::init_fuji_compr(fuji_compressed_params *)

- ea: `0x1800146a0`
- end: `0x180014963`
- name: `?init_fuji_compr@LibRaw@@IEAAXPEAUfuji_compressed_params@@@Z`
- size: `707`
- prototype: `void __fastcall(LibRaw *__hidden this, struct fuji_compressed_params *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013010`

## callees

- `0x1800090f0`
- `0x180009470`
- `0x1800146a0`
- `0x180014970`
- `0x180014cf0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LibRaw::init_fuji_compr(LibRaw *this, struct fuji_compressed_params *a2)
{
  int v2; // r9d
  int v4; // r8d
  int v6; // eax
  __int64 v7; // r14
  unsigned __int64 v8; // rdx
  int v9; // edx
  int v10; // edx
  int v11; // eax
  int v12; // edi
  signed __int8 *v13; // r8
  int v14; // esi
  int v15; // ecx
  int v16; // edx
  int v17; // edx
  signed __int8 *v18; // r8
  int v19; // ecx
  int v20; // edx
  int v21; // eax
  signed __int8 *v22; // r8
  int v23; // edx
  int v24; // eax
  int v25; // [rsp+20h] [rbp-38h] BYREF
  int v26; // [rsp+24h] [rbp-34h]
  int v27; // [rsp+28h] [rbp-30h]
  int v28; // [rsp+2Ch] [rbp-2Ch]
  int v29; // [rsp+30h] [rbp-28h]

  v2 = *((_DWORD *)this + 95393);
  v4 = *((_DWORD *)this + 95395);
  if ( v2 != 3 * (v2 / 3) && v4 == 16 || (v2 & 1) != 0 && !v4 )
    LibRaw::derror(this);
  v6 = 2 << *((_DWORD *)this + 95394);
  v7 = v6;
  v8 = v6;
  if ( !*((_DWORD *)this + 95396) )
    v8 = 3LL * v6;
  *((_QWORD *)a2 + 16) = LibRaw::malloc(this, v8);
  v9 = *((_DWORD *)this + 95393);
  if ( *((_DWORD *)this + 95395) == 16 )
    v10 = 2 * v9 / 3;
  else
    v10 = v9 >> 1;
  *((_WORD *)a2 + 74) = v10;
  *((_DWORD *)a2 + 35) = 64;
  v11 = (1 << *((_DWORD *)this + 95394)) - 1;
  *((_DWORD *)a2 + 36) = v11;
  if ( *((_DWORD *)this + 95396) )
  {
    *((_OWORD *)a2 + 2) = 0;
    *((_OWORD *)a2 + 3) = 0;
    *((_OWORD *)a2 + 4) = 0;
    *((_OWORD *)a2 + 5) = 0;
    *((_OWORD *)a2 + 6) = 0;
    *((_OWORD *)a2 + 7) = 0;
    *(_QWORD *)a2 = *((_QWORD *)a2 + 16);
    *((_DWORD *)a2 + 6) = -1;
    init_main_qtable(a2, 0);
  }
  else
  {
    *(_OWORD *)a2 = 0;
    v12 = 0;
    *((_OWORD *)a2 + 1) = 0;
    v13 = (signed __int8 *)*((_QWORD *)a2 + 16);
    v14 = v11;
    v29 = v11;
    v15 = 0;
    *((_QWORD *)a2 + 4) = v13;
    *((_DWORD *)a2 + 11) = v11 + 1;
    v16 = v11;
    v25 = 0;
    *(_QWORD *)((char *)a2 + 52) = 3;
    *((_DWORD *)a2 + 12) = 5;
    if ( v11 != -1 )
    {
      do
      {
        ++v15;
        v16 >>= 1;
      }
      while ( v16 );
    }
    *((_DWORD *)a2 + 10) = v15;
    v17 = 18;
    if ( v11 < 18 )
      v17 = 1;
    v26 = v17;
    if ( v11 >= 67 )
      v17 = 67;
    v27 = v17;
    if ( v11 >= 276 )
      v17 = 276;
    v28 = v17;
    setup_qlut(v13, &v25);
    v18 = (signed __int8 *)(v7 + *((_QWORD *)a2 + 4));
    *((_DWORD *)a2 + 22) = 1;
    *((_QWORD *)a2 + 8) = v18;
    *((_DWORD *)a2 + 20) = 6;
    v19 = 0;
    *((_DWORD *)a2 + 21) = 3;
    v20 = (v14 + 2) / 3;
    *((_DWORD *)a2 + 19) = v20 + 1;
    if ( v20 != -1 )
    {
      do
      {
        ++v19;
        v20 >>= 1;
      }
      while ( v20 );
    }
    *((_DWORD *)a2 + 18) = v19;
    v25 = 1;
    v21 = 21;
    if ( v14 < 21 )
      v21 = 2;
    v26 = v21;
    if ( v14 >= 72 )
      v21 = 72;
    v27 = v21;
    if ( v14 >= 283 )
      v21 = 283;
    v28 = v21;
    setup_qlut(v18, &v25);
    v22 = (signed __int8 *)(v7 + *((_QWORD *)a2 + 8));
    *((_DWORD *)a2 + 30) = 2;
    *((_QWORD *)a2 + 12) = v22;
    *((_DWORD *)a2 + 28) = 7;
    *((_DWORD *)a2 + 29) = 3;
    v23 = (v14 + 4) / 5;
    *((_DWORD *)a2 + 27) = v23 + 1;
    if ( v23 != -1 )
    {
      do
      {
        ++v12;
        v23 >>= 1;
      }
      while ( v23 );
    }
    *((_DWORD *)a2 + 26) = v12;
    v24 = 24;
    v25 = 2;
    if ( v14 < 24 )
      v24 = 3;
    v26 = v24;
    if ( v14 >= 77 )
      v24 = 77;
    v27 = v24;
    if ( v14 >= 290 )
      v24 = 290;
    v28 = v24;
    setup_qlut(v22, &v25);
  }
}

```

## disassembly

```asm
0x1800146a0  mov     [rsp+arg_10], rbx
0x1800146a5  mov     [rsp+arg_18], rbp
0x1800146aa  push    rdi
0x1800146ab  push    r12
0x1800146ad  push    r14
0x1800146af  sub     rsp, 40h
0x1800146b3  mov     r9d, [rcx+5D284h]
0x1800146ba  mov     rbx, rdx
0x1800146bd  mov     r8d, [rcx+5D28Ch]
0x1800146c4  mov     eax, 55555556h
0x1800146c9  imul    r9d
0x1800146cc  mov     rdi, rcx
0x1800146cf  mov     eax, edx
0x1800146d1  shr     eax, 1Fh
0x1800146d4  add     edx, eax
0x1800146d6  lea     ecx, [rdx+rdx*2]
0x1800146d9  cmp     r9d, ecx
0x1800146dc  jz      short loc_1800146E4
0x1800146de  cmp     r8d, 10h
0x1800146e2  jz      short loc_1800146EF
0x1800146e4  test    r9b, 1
0x1800146e8  jz      short loc_1800146F7
0x1800146ea  test    r8d, r8d
0x1800146ed  jnz     short loc_1800146F7
0x1800146ef  mov     rcx, rdi; this
0x1800146f2  call    ?derror@LibRaw@@IEAAXXZ; LibRaw::derror(void)
0x1800146f7  mov     ecx, [rdi+5D288h]
0x1800146fd  mov     ebp, 2
0x180014702  mov     eax, ebp
0x180014704  shl     eax, cl
0x180014706  cmp     dword ptr [rdi+5D290h], 0
0x18001470d  movsxd  r14, eax
0x180014710  mov     rdx, r14
0x180014713  jnz     short loc_180014719
0x180014715  lea     rdx, [r14+r14*2]; unsigned __int64
0x180014719  mov     rcx, rdi; this
0x18001471c  call    ?malloc@LibRaw@@IEAAPEAX_K@Z; LibRaw::malloc(unsigned __int64)
0x180014721  mov     [rbx+80h], rax
0x180014728  cmp     dword ptr [rdi+5D28Ch], 10h
0x18001472f  mov     edx, [rdi+5D284h]
0x180014735  jnz     short loc_18001474A
0x180014737  lea     ecx, [rdx+rdx]
0x18001473a  mov     eax, 55555556h
0x18001473f  imul    ecx
0x180014741  mov     eax, edx
0x180014743  shr     eax, 1Fh
0x180014746  add     edx, eax
0x180014748  jmp     short loc_18001474C
0x18001474a  sar     edx, 1
0x18001474c  mov     [rbx+94h], dx
0x180014753  mov     r12d, 1
0x180014759  mov     dword ptr [rbx+8Ch], 40h ; '@'
0x180014763  mov     eax, r12d
0x180014766  mov     ecx, [rdi+5D288h]
0x18001476c  xorps   xmm0, xmm0
0x18001476f  shl     eax, cl
0x180014771  dec     eax
0x180014773  mov     [rbx+90h], eax
0x180014779  cmp     dword ptr [rdi+5D290h], 0
0x180014780  jz      short loc_1800147BA
0x180014782  movups  xmmword ptr [rbx+20h], xmm0
0x180014786  xor     edx, edx; unsigned __int8
0x180014788  mov     rcx, rbx; struct fuji_compressed_params *
0x18001478b  movups  xmmword ptr [rbx+30h], xmm0
0x18001478f  movups  xmmword ptr [rbx+40h], xmm0
0x180014793  movups  xmmword ptr [rbx+50h], xmm0
0x180014797  movups  xmmword ptr [rbx+60h], xmm0
0x18001479b  movups  xmmword ptr [rbx+70h], xmm0
0x18001479f  mov     rax, [rbx+80h]
0x1800147a6  mov     [rbx], rax
0x1800147a9  mov     dword ptr [rbx+18h], 0FFFFFFFFh
0x1800147b0  call    ?init_main_qtable@@YAXPEAUfuji_compressed_params@@E@Z; init_main_qtable(fuji_compressed_params *,uchar)
0x1800147b5  jmp     loc_18001494F
0x1800147ba  movups  xmmword ptr [rbx], xmm0
0x1800147bd  xor     edi, edi
0x1800147bf  mov     [rsp+58h+arg_0], rsi
0x1800147c4  movups  xmmword ptr [rbx+10h], xmm0
0x1800147c8  mov     r8, [rbx+80h]
0x1800147cf  mov     esi, eax
0x1800147d1  mov     [rsp+58h+var_28], eax
0x1800147d5  mov     ecx, edi
0x1800147d7  add     eax, r12d
0x1800147da  mov     [rsp+58h+arg_8], r15
0x1800147df  mov     [rbx+20h], r8
0x1800147e3  mov     r15d, 3
0x1800147e9  mov     [rbx+2Ch], eax
0x1800147ec  mov     edx, esi
0x1800147ee  mov     [rsp+58h+var_38], edi
0x1800147f2  mov     qword ptr [rbx+34h], 3
0x1800147fa  mov     dword ptr [rbx+30h], 5
0x180014801  jz      short loc_180014809
0x180014803  inc     ecx
0x180014805  sar     edx, 1
0x180014807  jnz     short loc_180014803
0x180014809  mov     eax, 43h ; 'C'
0x18001480e  mov     [rbx+28h], ecx
0x180014811  mov     edx, 12h
0x180014816  mov     rcx, r8; signed __int8 *
0x180014819  cmp     esi, edx
0x18001481b  cmovl   edx, r12d
0x18001481f  cmp     esi, eax
0x180014821  mov     [rsp+58h+var_34], edx
0x180014825  cmovge  edx, eax
0x180014828  mov     eax, 114h
0x18001482d  mov     [rsp+58h+var_30], edx
0x180014831  cmp     esi, eax
0x180014833  cmovge  edx, eax
0x180014836  mov     [rsp+58h+var_2C], edx
0x18001483a  lea     rdx, [rsp+58h+var_38]; int *
0x18001483f  call    ?setup_qlut@@YAXPEACPEAH@Z; setup_qlut(signed char *,int *)
0x180014844  mov     r8, [rbx+20h]
0x180014848  lea     ecx, [rsi+2]
0x18001484b  add     r8, r14
0x18001484e  mov     [rbx+58h], r12d
0x180014852  mov     eax, 55555556h
0x180014857  mov     [rbx+40h], r8
0x18001485b  imul    ecx
0x18001485d  mov     dword ptr [rbx+50h], 6
0x180014864  mov     ecx, edi
0x180014866  mov     eax, edx
0x180014868  mov     [rbx+54h], r15d
0x18001486c  shr     eax, 1Fh
0x18001486f  add     edx, eax
0x180014871  lea     eax, [rdx+1]
0x180014874  mov     [rbx+4Ch], eax
0x180014877  test    eax, eax
0x180014879  jz      short loc_180014886
0x18001487b  nop     dword ptr [rax+rax+00h]
0x180014880  inc     ecx
0x180014882  sar     edx, 1
0x180014884  jnz     short loc_180014880
0x180014886  mov     [rbx+48h], ecx
0x180014889  lea     rdx, [rsp+58h+var_38]; int *
0x18001488e  mov     ecx, 48h ; 'H'
0x180014893  mov     [rsp+58h+var_38], r12d
0x180014898  mov     eax, 15h
0x18001489d  cmp     esi, eax
0x18001489f  cmovl   eax, ebp
0x1800148a2  cmp     esi, ecx
0x1800148a4  mov     [rsp+58h+var_34], eax
0x1800148a8  cmovge  eax, ecx
0x1800148ab  mov     ecx, 11Bh
0x1800148b0  cmp     esi, ecx
0x1800148b2  mov     [rsp+58h+var_30], eax
0x1800148b6  cmovge  eax, ecx
0x1800148b9  mov     rcx, r8; signed __int8 *
0x1800148bc  mov     [rsp+58h+var_2C], eax
0x1800148c0  call    ?setup_qlut@@YAXPEACPEAH@Z; setup_qlut(signed char *,int *)
0x1800148c5  mov     r8, [rbx+40h]
0x1800148c9  lea     ecx, [rsi+4]
0x1800148cc  add     r8, r14
0x1800148cf  mov     [rbx+78h], ebp
0x1800148d2  mov     eax, 66666667h
0x1800148d7  mov     [rbx+60h], r8
0x1800148db  imul    ecx
0x1800148dd  mov     dword ptr [rbx+70h], 7
0x1800148e4  sar     edx, 1
0x1800148e6  mov     eax, edx
0x1800148e8  mov     [rbx+74h], r15d
0x1800148ec  shr     eax, 1Fh
0x1800148ef  add     edx, eax
0x1800148f1  lea     eax, [rdx+1]
0x1800148f4  mov     [rbx+6Ch], eax
0x1800148f7  test    eax, eax
0x1800148f9  jz      short loc_180014906
0x1800148fb  nop     dword ptr [rax+rax+00h]
0x180014900  inc     edi
0x180014902  sar     edx, 1
0x180014904  jnz     short loc_180014900
0x180014906  mov     ecx, 4Dh ; 'M'
0x18001490b  mov     [rbx+68h], edi
0x18001490e  mov     eax, 18h
0x180014913  mov     [rsp+58h+var_38], ebp
0x180014917  cmp     esi, eax
0x180014919  lea     rdx, [rsp+58h+var_38]; int *
0x18001491e  cmovl   eax, r15d
0x180014922  cmp     esi, ecx
0x180014924  mov     [rsp+58h+var_34], eax
0x180014928  cmovge  eax, ecx
0x18001492b  mov     ecx, 122h
0x180014930  cmp     esi, ecx
0x180014932  mov     [rsp+58h+var_30], eax
0x180014936  cmovge  eax, ecx
0x180014939  mov     rcx, r8; signed __int8 *
0x18001493c  mov     [rsp+58h+var_2C], eax
0x180014940  call    ?setup_qlut@@YAXPEACPEAH@Z; setup_qlut(signed char *,int *)
0x180014945  mov     r15, [rsp+58h+arg_8]
0x18001494a  mov     rsi, [rsp+58h+arg_0]
0x18001494f  mov     rbx, [rsp+58h+arg_10]
0x180014954  mov     rbp, [rsp+58h+arg_18]
0x180014959  add     rsp, 40h
0x18001495d  pop     r14
0x18001495f  pop     r12
0x180014961  pop     rdi
0x180014962  retn
```
