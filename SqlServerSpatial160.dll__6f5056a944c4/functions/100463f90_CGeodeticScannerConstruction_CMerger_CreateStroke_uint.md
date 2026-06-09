# CGeodeticScannerConstruction::CMerger::CreateStroke(uint)

- ea: `0x100463f90`
- end: `0x100464101`
- name: `?CreateStroke@CMerger@CGeodeticScannerConstruction@@AEAAJI@Z`
- size: `369`
- prototype: `__int64 __fastcall(CGeodeticScannerConstruction::CMerger *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x100463370`

## callees

- `0x100463f90`
- `0x100464110`
- `0x1004643b0`
- `0x100464670`

## pseudocode

```c
__int64 __fastcall CGeodeticScannerConstruction::CMerger::CreateStroke(
        CGeodeticScannerConstruction::CMerger *this,
        unsigned int a2)
{
  __int64 v3; // rbp
  __int64 v4; // rdi
  __int64 result; // rax
  __int64 v6; // rbx
  double *v7; // rdx
  double *v8; // rcx
  double v9; // xmm0_8
  double v10; // xmm1_8
  double v11; // [rsp+30h] [rbp-38h] BYREF
  double v12; // [rsp+38h] [rbp-30h]
  double v13; // [rsp+48h] [rbp-20h]
  double v14; // [rsp+50h] [rbp-18h]
  char v15; // [rsp+58h] [rbp-10h]

  v15 = 0;
  v3 = *(_QWORD *)(*((_QWORD *)this + 8) + 8LL * (a2 / *((_DWORD *)this + 19))) + 88LL * (a2 % *((_DWORD *)this + 19));
  v4 = v3;
  do
  {
    result = CGeodeticScannerConstruction::CSegment::Flush(
               (CGeodeticScannerConstruction::CSegment *)v4,
               *((const struct COriginalPoints **)this + 32),
               *((struct CGeometrySinkD **)this + 14),
               (CGeodeticScannerConstruction::CMerger *)((char *)this + 144),
               (struct CGeodeticScannerConstruction::OutputState *)&v11);
    if ( (int)result < 0 )
    {
      _mm_lfence();
      return result;
    }
    v6 = *(_QWORD *)(v4 + 48);
    if ( !v6 )
      break;
    v7 = *(double **)(v6 + 8);
    v8 = (double *)(*(_QWORD *)(v4 + 8) + 16LL * (unsigned int)(*(_DWORD *)(v4 + 4) - 1));
    v9 = v7[2 * (unsigned int)(*(_DWORD *)(v6 + 4) - 1)] - *v8;
    v10 = v7[2 * (unsigned int)(*(_DWORD *)(v6 + 4) - 1) + 1];
    if ( (v7[1] - v8[1]) * (v7[1] - v8[1]) + (*v7 - *v8) * (*v7 - *v8) > (v10 - v8[1]) * (v10 - v8[1]) + v9 * v9 )
      CGeodeticScannerConstruction::CSegment::Reverse(*(CGeodeticScannerConstruction::CSegment **)(v4 + 48));
    v4 = v6;
    if ( v6 == v3 || v13 == v11 && v14 == v12 )
      break;
  }
  while ( (*(_BYTE *)(v6 + 85) & 1) == 0 );
  _mm_lfence();
  if ( v13 == v11 && v14 == v12 )
    return CGeodeticScannerConstruction::CMerger::EndCurrentFigure(this, 1);
  else
    return CGeodeticScannerConstruction::CMerger::EndCurrentFigure(this, 0);
}

```

## disassembly

```asm
0x100463f90  mov     [rsp+arg_8], rbp
0x100463f95  mov     [rsp+arg_10], rsi
0x100463f9a  mov     [rsp+arg_18], rdi
0x100463f9f  push    r14
0x100463fa1  sub     rsp, 60h
0x100463fa5  mov     eax, edx
0x100463fa7  mov     [rsp+68h+var_10], 0
0x100463fac  xor     edx, edx
0x100463fae  mov     [rsp+68h+arg_0], rbx
0x100463fb3  div     dword ptr [rcx+4Ch]
0x100463fb6  mov     rsi, rcx
0x100463fb9  mov     r8d, edx
0x100463fbc  mov     edx, eax
0x100463fbe  mov     rax, [rcx+40h]
0x100463fc2  imul    rbp, r8, 58h ; 'X'
0x100463fc6  add     rbp, [rax+rdx*8]
0x100463fca  mov     rdi, rbp
0x100463fcd  nop     dword ptr [rax]
0x100463fd0  mov     r8, [rsi+70h]; struct CGeometrySinkD *
0x100463fd4  lea     rax, [rsp+68h+var_38]
0x100463fd9  mov     rdx, [rsi+100h]; struct COriginalPoints *
0x100463fe0  lea     r9, [rsi+90h]; struct CAttributes *
0x100463fe7  mov     rcx, rdi; this
0x100463fea  mov     [rsp+68h+var_48], rax; struct CGeodeticScannerConstruction::OutputState *
0x100463fef  call    ?Flush@CSegment@CGeodeticScannerConstruction@@QEAAJPEBVCOriginalPoints@@PEAVCGeometrySinkD@@AEAVCAttributes@@AEAUOutputState@2@@Z; CGeodeticScannerConstruction::CSegment::Flush(COriginalPoints const *,CGeometrySinkD *,CAttributes &,CGeodeticScannerConstruction::OutputState &)
0x100463ff4  test    eax, eax
0x100463ff6  js      loc_1004640E2
0x100463ffc  mov     rbx, [rdi+30h]
0x100464000  test    rbx, rbx
0x100464003  jz      loc_1004640A7
0x100464009  mov     rdx, [rbx+8]
0x10046400d  mov     ecx, [rdi+4]
0x100464010  dec     ecx
0x100464012  shl     rcx, 4
0x100464016  add     rcx, [rdi+8]
0x10046401a  movsd   xmm4, qword ptr [rdx]
0x10046401e  movsd   xmm3, qword ptr [rdx+8]
0x100464023  movsd   xmm1, qword ptr [rcx]
0x100464027  movsd   xmm2, qword ptr [rcx+8]
0x10046402c  subsd   xmm4, xmm1
0x100464030  mov     ecx, [rbx+4]
0x100464033  subsd   xmm3, xmm2
0x100464037  dec     ecx
0x100464039  add     rcx, rcx
0x10046403c  mulsd   xmm4, xmm4
0x100464040  movsd   xmm0, qword ptr [rdx+rcx*8]
0x100464045  subsd   xmm0, xmm1
0x100464049  mulsd   xmm3, xmm3
0x10046404d  movsd   xmm1, qword ptr [rdx+rcx*8+8]
0x100464053  subsd   xmm1, xmm2
0x100464057  mulsd   xmm0, xmm0
0x10046405b  addsd   xmm3, xmm4
0x10046405f  mulsd   xmm1, xmm1
0x100464063  addsd   xmm1, xmm0
0x100464067  comisd  xmm3, xmm1
0x10046406b  jbe     short loc_100464075
0x10046406d  mov     rcx, rbx; this
0x100464070  call    ?Reverse@CSegment@CGeodeticScannerConstruction@@QEAAXXZ; CGeodeticScannerConstruction::CSegment::Reverse(void)
0x100464075  mov     rdi, rbx
0x100464078  cmp     rbx, rbp
0x10046407b  jz      short loc_1004640A7
0x10046407d  movsd   xmm0, [rsp+68h+var_20]
0x100464083  ucomisd xmm0, [rsp+68h+var_38]
0x100464089  jp      short loc_10046409D
0x10046408b  jnz     short loc_10046409D
0x10046408d  movsd   xmm0, [rsp+68h+var_18]
0x100464093  ucomisd xmm0, [rsp+68h+var_30]
0x100464099  jp      short loc_10046409D
0x10046409b  jz      short loc_1004640A7
0x10046409d  test    byte ptr [rbx+55h], 1
0x1004640a1  jz      loc_100463FD0
0x1004640a7  lfence
0x1004640aa  movsd   xmm0, [rsp+68h+var_20]
0x1004640b0  ucomisd xmm0, [rsp+68h+var_38]
0x1004640b6  jp      short loc_1004640D6
0x1004640b8  jnz     short loc_1004640D6
0x1004640ba  movsd   xmm0, [rsp+68h+var_18]
0x1004640c0  ucomisd xmm0, [rsp+68h+var_30]
0x1004640c6  jp      short loc_1004640D6
0x1004640c8  jnz     short loc_1004640D6
0x1004640ca  mov     dl, 1; bool
0x1004640cc  mov     rcx, rsi; this
0x1004640cf  call    ?EndCurrentFigure@CMerger@CGeodeticScannerConstruction@@AEAAJ_N@Z; CGeodeticScannerConstruction::CMerger::EndCurrentFigure(bool)
0x1004640d4  jmp     short loc_1004640E5
0x1004640d6  xor     dl, dl; bool
0x1004640d8  mov     rcx, rsi; this
0x1004640db  call    ?EndCurrentFigure@CMerger@CGeodeticScannerConstruction@@AEAAJ_N@Z; CGeodeticScannerConstruction::CMerger::EndCurrentFigure(bool)
0x1004640e0  jmp     short loc_1004640E5
0x1004640e2  lfence
0x1004640e5  mov     rbx, [rsp+68h+arg_0]
0x1004640ea  lea     r11, [rsp+68h+var_8]
0x1004640ef  mov     rbp, [r11+18h]
0x1004640f3  mov     rsi, [r11+20h]
0x1004640f7  mov     rdi, [r11+28h]
0x1004640fb  mov     rsp, r11
0x1004640fe  pop     r14
0x100464100  retn
```
