# CBounds::UpdateWithBezier(CMglPoint<double> const &,CMglPoint<double> const &,CMglPoint<double> const &,CMglPoint<double> const &)

- ea: `0x1004465d0`
- end: `0x10044687d`
- name: `?UpdateWithBezier@CBounds@@QEAAXAEBV?$CMglPoint@N@@000@Z`
- size: `685`
- prototype: `__int64 __usercall@<rax>(CBounds *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x100446ea0`

## callees

- `0x100446530`
- `0x1004465d0`
- `0x1004469e0`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100446627`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100446637`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100446659`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100446669`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100446755`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x10044683a`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100446627`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100446637`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100446659`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100446669`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x100446755`
- `api-ms-win-crt-math-l1-1-0!_isnan` at `0x10044683a`

## pseudocode

```c
char __fastcall CBounds::UpdateWithBezier(CBounds *this, double *a2, double *a3, double *a4, double *a5)
{
  bool v9; // zf
  int v10; // eax
  int v11; // eax
  int DerivativeZeros; // eax
  __int64 v13; // rsi
  __int64 v14; // rbp
  __int64 v15; // rdi
  double v16; // xmm4_8
  double v17; // xmm2_8
  double v18; // xmm5_8
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdi
  double v22; // xmm4_8
  double v23; // xmm2_8
  double v24; // xmm5_8
  __int128 X; // [rsp+30h] [rbp-58h] BYREF

  CBounds::UpdateWithPoint(this, a5);
  v9 = *((_BYTE *)this + 32) == 0;
  X = *(_OWORD *)a3;
  if ( !v9 || _isnan(*(double *)&X) || (v10 = _isnan(*((double *)&X + 1))) != 0 )
    LOBYTE(v10) = 1;
  *((_BYTE *)this + 32) = v10;
  X = *(_OWORD *)a4;
  if ( (_BYTE)v10 || _isnan(*(double *)&X) || (v11 = _isnan(*((double *)&X + 1))) != 0 )
    LOBYTE(v11) = 1;
  *((_BYTE *)this + 32) = v11;
  DerivativeZeros = CBounds::GetDerivativeZeros(this, *a2, *a3, *a4, *a5, (double *)&X);
  v13 = 0;
  v14 = DerivativeZeros;
  if ( DerivativeZeros > 0 )
  {
    v15 = 0;
    do
    {
      v16 = *((double *)&X + v15);
      v17 = 1.0 - v16;
      v18 = *a3 * 3.0 * v16 * (v17 * v17)
          + (1.0 - v16) * *a2 * (v17 * v17)
          + *a4 * 3.0 * (v16 * v16) * v17
          + v16 * *a5 * (v16 * v16);
      if ( *(double *)this <= v18 )
      {
        if ( v18 > *((double *)this + 1) )
          *((double *)this + 1) = v18;
      }
      else
      {
        *(double *)this = v18;
      }
      if ( *((_BYTE *)this + 32) || (v19 = _isnan(v18)) != 0 )
        LOBYTE(v19) = 1;
      ++v15;
      *((_BYTE *)this + 32) = v19;
    }
    while ( v15 < v14 );
  }
  v20 = CBounds::GetDerivativeZeros(this, a2[1], a3[1], a4[1], a5[1], (double *)&X);
  v21 = v20;
  if ( v20 > 0 )
  {
    do
    {
      v22 = *((double *)&X + v13);
      v23 = 1.0 - v22;
      v24 = a3[1] * 3.0 * v22 * (v23 * v23)
          + (1.0 - v22) * a2[1] * (v23 * v23)
          + a4[1] * 3.0 * (v22 * v22) * v23
          + v22 * a5[1] * (v22 * v22);
      if ( *((double *)this + 2) <= v24 )
      {
        if ( v24 > *((double *)this + 3) )
          *((double *)this + 3) = v24;
      }
      else
      {
        *((double *)this + 2) = v24;
      }
      if ( *((_BYTE *)this + 32) || (v20 = _isnan(v24)) != 0 )
        LOBYTE(v20) = 1;
      ++v13;
      *((_BYTE *)this + 32) = v20;
    }
    while ( v13 < v21 );
  }
  return v20;
}

```

## disassembly

```asm
0x1004465d0  mov     [rsp+arg_0], rbx
0x1004465d5  mov     [rsp+arg_8], rbp
0x1004465da  mov     [rsp+arg_10], rsi
0x1004465df  push    rdi
0x1004465e0  push    r12
0x1004465e2  push    r13
0x1004465e4  push    r14
0x1004465e6  push    r15
0x1004465e8  sub     rsp, 60h
0x1004465ec  mov     r12, [rsp+88h+arg_20]
0x1004465f4  mov     r13, rdx
0x1004465f7  mov     rdx, r12
0x1004465fa  movaps  [rsp+88h+var_38], xmm6
0x1004465ff  movaps  [rsp+88h+var_48], xmm7
0x100446604  mov     r14, r9
0x100446607  mov     r15, r8
0x10044660a  mov     rbx, rcx
0x10044660d  call    ?UpdateWithPoint@CBounds@@QEAAXAEBV?$CMglPoint@N@@@Z; CBounds::UpdateWithPoint(CMglPoint<double> const &)
0x100446612  cmp     byte ptr [rbx+20h], 0
0x100446616  movups  xmm0, xmmword ptr [r15]
0x10044661a  movaps  xmmword ptr [rsp+88h+X], xmm0
0x10044661f  jnz     short loc_100446641
0x100446621  movsd   xmm0, [rsp+88h+X]; X
0x100446627  call    cs:__imp__isnan
0x10044662d  test    eax, eax
0x10044662f  jnz     short loc_100446641
0x100446631  movsd   xmm0, [rsp+88h+X+8]; X
0x100446637  call    cs:__imp__isnan
0x10044663d  test    eax, eax
0x10044663f  jz      short loc_100446643
0x100446641  mov     al, 1
0x100446643  mov     [rbx+20h], al
0x100446646  movups  xmm0, xmmword ptr [r14]
0x10044664a  movaps  xmmword ptr [rsp+88h+X], xmm0
0x10044664f  test    al, al
0x100446651  jnz     short loc_100446673
0x100446653  movsd   xmm0, [rsp+88h+X]; X
0x100446659  call    cs:__imp__isnan
0x10044665f  test    eax, eax
0x100446661  jnz     short loc_100446673
0x100446663  movsd   xmm0, [rsp+88h+X+8]; X
0x100446669  call    cs:__imp__isnan
0x10044666f  test    eax, eax
0x100446671  jz      short loc_100446675
0x100446673  mov     al, 1
0x100446675  mov     [rbx+20h], al
0x100446678  mov     rcx, rbx; this
0x10044667b  movsd   xmm0, qword ptr [r12]
0x100446681  lea     rax, [rsp+88h+X]
0x100446686  movsd   xmm3, qword ptr [r14]; double
0x10044668b  movsd   xmm2, qword ptr [r15]; double
0x100446690  movsd   xmm1, qword ptr [r13+0]; double
0x100446696  mov     [rsp+88h+var_60], rax; double *
0x10044669b  movsd   [rsp+88h+var_68], xmm0; double
0x1004466a1  call    ?GetDerivativeZeros@CBounds@@IEAAHNNNNPEAN@Z; CBounds::GetDerivativeZeros(double,double,double,double,double *)
0x1004466a6  movsd   xmm7, cs:__real@3ff0000000000000
0x1004466ae  xor     esi, esi
0x1004466b0  movsd   xmm6, cs:__real@4008000000000000
0x1004466b8  movsxd  rbp, eax
0x1004466bb  test    eax, eax
0x1004466bd  jle     loc_100446770
0x1004466c3  mov     edi, esi
0x1004466c5  nop     word ptr [rax+rax+00000000h]
0x1004466d0  movsd   xmm4, [rsp+rdi*8+88h+X]
0x1004466d6  movaps  xmm2, xmm7
0x1004466d9  movsd   xmm5, qword ptr [r15]
0x1004466de  subsd   xmm2, xmm4
0x1004466e2  mulsd   xmm5, xmm6
0x1004466e6  movaps  xmm3, xmm4
0x1004466e9  mulsd   xmm3, xmm4
0x1004466ed  movaps  xmm1, xmm2
0x1004466f0  movaps  xmm0, xmm2
0x1004466f3  mulsd   xmm0, qword ptr [r13+0]
0x1004466f9  mulsd   xmm1, xmm2
0x1004466fd  mulsd   xmm5, xmm4
0x100446701  mulsd   xmm4, qword ptr [r12]
0x100446707  mulsd   xmm0, xmm1
0x10044670b  mulsd   xmm5, xmm1
0x10044670f  movsd   xmm1, qword ptr [r14]
0x100446714  mulsd   xmm1, xmm6
0x100446718  addsd   xmm5, xmm0
0x10044671c  mulsd   xmm4, xmm3
0x100446720  movsd   xmm0, qword ptr [rbx]
0x100446724  mulsd   xmm1, xmm3
0x100446728  mulsd   xmm1, xmm2
0x10044672c  addsd   xmm5, xmm1
0x100446730  addsd   xmm5, xmm4
0x100446734  comisd  xmm0, xmm5
0x100446738  jbe     short loc_100446740
0x10044673a  movsd   qword ptr [rbx], xmm5
0x10044673e  jmp     short loc_10044674C
0x100446740  comisd  xmm5, qword ptr [rbx+8]
0x100446745  jbe     short loc_10044674C
0x100446747  movsd   qword ptr [rbx+8], xmm5
0x10044674c  cmp     [rbx+20h], sil
0x100446750  jnz     short loc_10044675F
0x100446752  movaps  xmm0, xmm5; X
0x100446755  call    cs:__imp__isnan
0x10044675b  test    eax, eax
0x10044675d  jz      short loc_100446761
0x10044675f  mov     al, 1
0x100446761  inc     rdi
0x100446764  mov     [rbx+20h], al
0x100446767  cmp     rdi, rbp
0x10044676a  jl      loc_1004466D0
0x100446770  movsd   xmm0, qword ptr [r12+8]
0x100446777  lea     rax, [rsp+88h+X]
0x10044677c  movsd   xmm3, qword ptr [r14+8]; double
0x100446782  mov     rcx, rbx; this
0x100446785  movsd   xmm2, qword ptr [r15+8]; double
0x10044678b  movsd   xmm1, qword ptr [r13+8]; double
0x100446791  mov     [rsp+88h+var_60], rax; double *
0x100446796  movsd   [rsp+88h+var_68], xmm0; double
0x10044679c  call    ?GetDerivativeZeros@CBounds@@IEAAHNNNNPEAN@Z; CBounds::GetDerivativeZeros(double,double,double,double,double *)
0x1004467a1  movsxd  rdi, eax
0x1004467a4  test    eax, eax
0x1004467a6  jle     loc_100446855
0x1004467ac  nop     dword ptr [rax+00h]
0x1004467b0  movsd   xmm4, [rsp+rsi*8+88h+X]
0x1004467b6  movaps  xmm2, xmm7
0x1004467b9  movsd   xmm5, qword ptr [r15+8]
0x1004467bf  subsd   xmm2, xmm4
0x1004467c3  mulsd   xmm5, xmm6
0x1004467c7  movaps  xmm3, xmm4
0x1004467ca  mulsd   xmm3, xmm4
0x1004467ce  movaps  xmm1, xmm2
0x1004467d1  movaps  xmm0, xmm2
0x1004467d4  mulsd   xmm0, qword ptr [r13+8]
0x1004467da  mulsd   xmm1, xmm2
0x1004467de  mulsd   xmm5, xmm4
0x1004467e2  mulsd   xmm4, qword ptr [r12+8]
0x1004467e9  mulsd   xmm0, xmm1
0x1004467ed  mulsd   xmm5, xmm1
0x1004467f1  movsd   xmm1, qword ptr [r14+8]
0x1004467f7  mulsd   xmm1, xmm6
0x1004467fb  addsd   xmm5, xmm0
0x1004467ff  mulsd   xmm4, xmm3
0x100446803  movsd   xmm0, qword ptr [rbx+10h]
0x100446808  mulsd   xmm1, xmm3
0x10044680c  mulsd   xmm1, xmm2
0x100446810  addsd   xmm5, xmm1
0x100446814  addsd   xmm5, xmm4
0x100446818  comisd  xmm0, xmm5
0x10044681c  jbe     short loc_100446825
0x10044681e  movsd   qword ptr [rbx+10h], xmm5
0x100446823  jmp     short loc_100446831
0x100446825  comisd  xmm5, qword ptr [rbx+18h]
0x10044682a  jbe     short loc_100446831
0x10044682c  movsd   qword ptr [rbx+18h], xmm5
0x100446831  cmp     byte ptr [rbx+20h], 0
0x100446835  jnz     short loc_100446844
0x100446837  movaps  xmm0, xmm5; X
0x10044683a  call    cs:__imp__isnan
0x100446840  test    eax, eax
0x100446842  jz      short loc_100446846
0x100446844  mov     al, 1
0x100446846  inc     rsi
0x100446849  mov     [rbx+20h], al
0x10044684c  cmp     rsi, rdi
0x10044684f  jl      loc_1004467B0
0x100446855  movaps  xmm6, [rsp+88h+var_38]
0x10044685a  lea     r11, [rsp+88h+var_28]
0x10044685f  mov     rbx, [r11+30h]
0x100446863  mov     rbp, [r11+38h]
0x100446867  mov     rsi, [r11+40h]
0x10044686b  movaps  xmm7, [rsp+88h+var_48]
0x100446870  mov     rsp, r11
0x100446873  pop     r15
0x100446875  pop     r14
0x100446877  pop     r13
0x100446879  pop     r12
0x10044687b  pop     rdi
0x10044687c  retn
```
