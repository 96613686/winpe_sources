# CDecomposeRectangle::SweepAndPruneDecompose(IDisplayList &)

- ea: `0x18001b3a8`
- end: `0x18001b645`
- name: `?SweepAndPruneDecompose@CDecomposeRectangle@@QEAAXAEAUIDisplayList@@@Z`
- size: `669`
- prototype: `void __fastcall(CDecomposeRectangle *__hidden this, struct IDisplayList *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001425c`

## callees

- `0x18000e174`
- `0x180011fb8`
- `0x180015940`
- `0x180015aac`
- `0x18001ad1c`
- `0x18001ae14`
- `0x18001aef8`
- `0x18001b3a8`
- `0x18001b7a0`
- `0x18001b810`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDecomposeRectangle::SweepAndPruneDecompose(CDecomposeRectangle *this, struct IDisplayList *a2)
{
  __int64 v4; // r8
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rsi
  __int64 v8; // rdx
  float v9; // xmm9_4
  __int64 v10; // rdx
  __int64 v11; // rax
  int v12; // r9d
  _DWORD *v13; // r15
  unsigned __int64 v14; // rdx
  float v15; // xmm8_4
  __int64 v16; // r8
  int v17; // r14d
  float **v18; // rax
  float *v19; // rbx
  float v20; // xmm2_4
  float v21; // xmm1_4
  float v22; // xmm6_4
  float v23; // xmm7_4
  _QWORD *v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // r8
  _QWORD *v27; // rax
  __int64 v28; // [rsp+38h] [rbp-99h] BYREF
  __int64 v29; // [rsp+40h] [rbp-91h]
  _DWORD v30[4]; // [rsp+50h] [rbp-81h] BYREF
  _DWORD v31[3]; // [rsp+60h] [rbp-71h] BYREF
  _DWORD v32[3]; // [rsp+6Ch] [rbp-65h] BYREF
  _DWORD v33[4]; // [rsp+78h] [rbp-59h] BYREF
  _BYTE v34[8]; // [rsp+88h] [rbp-49h] BYREF
  _BYTE v35[8]; // [rsp+90h] [rbp-41h] BYREF
  _BYTE v36[8]; // [rsp+98h] [rbp-39h] BYREF
  _BYTE v37[8]; // [rsp+A0h] [rbp-31h] BYREF
  _BYTE v38[8]; // [rsp+A8h] [rbp-29h] BYREF
  _BYTE v39[72]; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v40; // [rsp+140h] [rbp+6Fh] BYREF
  char v41; // [rsp+148h] [rbp+77h] BYREF
  char v42; // [rsp+150h] [rbp+7Fh] BYREF

  std::vector<CCoordinate>::vector<CCoordinate>(&v28, a2);
  v5 = *(_QWORD *)std::vector<tagRGBQUAD>::begin(this, &v41, v4);
  v7 = *(_QWORD *)std::vector<CCoordinate>::end(v6, &v40);
  v8 = *(unsigned int *)(v5 + 4);
  LODWORD(v8) = v8 & 0x7FFFFFFF;
  v9 = *(float *)((*(__int64 (__fastcall **)(struct IDisplayList *, __int64))(*(_QWORD *)a2 + 8LL))(a2, v8) + 4);
  while ( v5 != v7 )
  {
    v10 = *(unsigned int *)(v5 + 4);
    LODWORD(v10) = v10 & 0x7FFFFFFF;
    v11 = (*(__int64 (__fastcall **)(struct IDisplayList *, __int64))(*(_QWORD *)a2 + 8LL))(a2, v10);
    v13 = (_DWORD *)v11;
    v14 = -(__int64)(*(_DWORD *)(v5 + 4) >> 31 != 0) & 0xFFFFFFFFFFFFFFF8uLL;
    v15 = *(float *)(v11 + v14 + 12);
    if ( v28 == v29 )
      v9 = *(float *)(v11 + v14 + 12);
    if ( v9 != v15
      && v28 != v29
      && !(unsigned __int8)CDecomposeRectangle::IsSegmentContained(
                             v28,
                             (unsigned int)&v28,
                             *(_DWORD *)(v5 + 4) >> 31,
                             v12,
                             *(int *)(v5 + 4) < 0) )
    {
      v17 = 1;
      v18 = (float **)std::vector<tagRGBQUAD>::begin(&v28, &v42, v16);
      v19 = *v18;
      v20 = **v18;
      v21 = (*v18)[1];
      while ( 1 )
      {
        v19 += 3;
        if ( v19 == *(float **)std::vector<CCoordinate>::end(&v28, v34) )
          break;
        v22 = *v19;
        v23 = v19[1];
        if ( v20 == *v19 )
          v21 = fmaxf(v23, v21);
        if ( v22 > v20 && v21 >= v22 )
          v21 = fmaxf(v23, v21);
        if ( v22 > v21 )
        {
          ++v17;
          *(float *)v31 = v20;
          *(float *)&v31[1] = v21;
          v31[2] = 1;
          std::vector<CSegment>::push_back((char *)this + 24, v31);
          v20 = v22;
          v21 = v23;
        }
      }
      *(float *)v32 = v20;
      *(float *)&v32[1] = v21;
      v32[2] = 1;
      std::vector<CSegment>::push_back((char *)this + 24, v32);
      *(float *)v33 = v9;
      *(float *)&v33[1] = v15;
      v33[2] = v17;
      std::vector<CSegment>::push_back((char *)this + 48, v33);
      v9 = v15;
    }
    v30[0] = *v13;
    v30[1] = v13[2];
    v30[2] = 1;
    v24 = (_QWORD *)std::vector<CCoordinate>::end(&v28, v35);
    v25 = (_QWORD *)std::vector<tagRGBQUAD>::begin(&v28, v36, *v24);
    std::lower_bound<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CSegment>>>,CSegment>(
      &v40,
      *v25,
      v26,
      v30);
    if ( *(int *)(v5 + 4) >= 0 )
    {
      v27 = (_QWORD *)std::vector<CCoordinate>::end(&v28, v38);
      if ( v40 != *v27 )
        std::vector<CSegment>::erase(&v28, v39);
    }
    else
    {
      std::vector<CSegment>::emplace<CSegment const &>(&v28, v37, v40, v30);
    }
    v5 += 8;
  }
  std::vector<CSegment>::_Tidy(&v28);
}

```

## disassembly

```asm
0x18001b3a8  mov     rax, rsp
0x18001b3ab  mov     [rax+8], rbx
0x18001b3af  push    rbp
0x18001b3b0  push    rsi
0x18001b3b1  push    rdi
0x18001b3b2  push    r12
0x18001b3b4  push    r13
0x18001b3b6  push    r14
0x18001b3b8  push    r15
0x18001b3ba  lea     rbp, [rax-5Fh]
0x18001b3be  sub     rsp, 0F0h
0x18001b3c5  movaps  xmmword ptr [rax-48h], xmm6
0x18001b3c9  movaps  xmmword ptr [rax-58h], xmm7
0x18001b3cd  movaps  xmmword ptr [rax-68h], xmm8
0x18001b3d2  movaps  xmmword ptr [rax-78h], xmm9
0x18001b3d7  mov     r12, rdx
0x18001b3da  mov     r13, rcx
0x18001b3dd  lea     rcx, [rsp+120h+var_F0]
0x18001b3e2  call    ??0?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA@XZ; std::vector<CCoordinate>::vector<CCoordinate>(void)
0x18001b3e7  nop
0x18001b3e8  lea     rdx, [rbp+57h+arg_10]
0x18001b3ec  mov     rcx, r13
0x18001b3ef  call    ?begin@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UtagRGBQUAD@@@std@@@std@@@2@XZ; std::vector<tagRGBQUAD>::begin(void)
0x18001b3f4  mov     rdi, [rax]
0x18001b3f7  lea     rdx, [rbp+57h+arg_8]
0x18001b3fb  call    ?end@?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCCoordinate@@@std@@@std@@@2@XZ; std::vector<CCoordinate>::end(void)
0x18001b400  mov     rsi, [rax]
0x18001b403  mov     rax, [r12]
0x18001b407  mov     edx, [rdi+4]
0x18001b40a  btr     edx, 1Fh
0x18001b40e  mov     rcx, r12
0x18001b411  mov     rax, [rax+8]
0x18001b415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b41a  movss   xmm9, dword ptr [rax+4]
0x18001b420  cmp     rdi, rsi
0x18001b423  jz      loc_18001B60C
0x18001b429  mov     rax, [r12]
0x18001b42d  mov     edx, [rdi+4]
0x18001b430  btr     edx, 1Fh
0x18001b434  mov     rcx, r12
0x18001b437  mov     rax, [rax+8]
0x18001b43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b440  mov     r15, rax
0x18001b443  mov     r8d, [rdi+4]
0x18001b447  shr     r8d, 1Fh
0x18001b44b  mov     ecx, r8d
0x18001b44e  neg     ecx
0x18001b450  sbb     rdx, rdx
0x18001b453  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001b457  movss   xmm8, dword ptr [rax+rdx+0Ch]
0x18001b45e  mov     rcx, [rsp+120h+var_F0]
0x18001b463  cmp     rcx, [rsp+120h+var_E8]
0x18001b468  jnz     short loc_18001B46E
0x18001b46a  movaps  xmm9, xmm8
0x18001b46e  ucomiss xmm9, xmm8
0x18001b472  jp      short loc_18001B47A
0x18001b474  jz      loc_18001B577
0x18001b47a  cmp     rcx, [rsp+120h+var_E8]
0x18001b47f  jz      loc_18001B577
0x18001b485  mov     [rsp+120h+var_100], r8b
0x18001b48a  movss   xmm3, dword ptr [rax+8]
0x18001b48f  movss   xmm2, dword ptr [rax]
0x18001b493  lea     rdx, [rsp+120h+var_F0]
0x18001b498  call    ?IsSegmentContained@CDecomposeRectangle@@AEAA_NAEAV?$vector@UCSegment@@V?$allocator@UCSegment@@@std@@@std@@MM_N@Z; CDecomposeRectangle::IsSegmentContained(std::vector<CSegment> &,float,float,bool)
0x18001b49d  test    al, al
0x18001b49f  jnz     loc_18001B577
0x18001b4a5  mov     r14d, 1
0x18001b4ab  lea     rdx, [rbp+57h+arg_18]
0x18001b4af  lea     rcx, [rsp+120h+var_F0]
0x18001b4b4  call    ?begin@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UtagRGBQUAD@@@std@@@std@@@2@XZ; std::vector<tagRGBQUAD>::begin(void)
0x18001b4b9  mov     rbx, [rax]
0x18001b4bc  movss   xmm2, dword ptr [rbx]
0x18001b4c0  movss   xmm1, dword ptr [rbx+4]
0x18001b4c5  add     rbx, 0Ch
0x18001b4c9  lea     rdx, [rbp+57h+var_A0]
0x18001b4cd  lea     rcx, [rsp+120h+var_F0]
0x18001b4d2  call    ?end@?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCCoordinate@@@std@@@std@@@2@XZ; std::vector<CCoordinate>::end(void)
0x18001b4d7  cmp     rbx, [rax]
0x18001b4da  jz      short loc_18001B538
0x18001b4dc  movss   xmm6, dword ptr [rbx]
0x18001b4e0  movss   xmm7, dword ptr [rbx+4]
0x18001b4e5  ucomiss xmm2, xmm6
0x18001b4e8  jp      short loc_18001B4F6
0x18001b4ea  jnz     short loc_18001B4F6
0x18001b4ec  movaps  xmm0, xmm7
0x18001b4ef  maxss   xmm0, xmm1
0x18001b4f3  movaps  xmm1, xmm0
0x18001b4f6  comiss  xmm6, xmm2
0x18001b4f9  jbe     short loc_18001B50A
0x18001b4fb  comiss  xmm1, xmm6
0x18001b4fe  jb      short loc_18001B50A
0x18001b500  movaps  xmm0, xmm7
0x18001b503  maxss   xmm0, xmm1
0x18001b507  movaps  xmm1, xmm0
0x18001b50a  comiss  xmm6, xmm1
0x18001b50d  jbe     short loc_18001B4C5
0x18001b50f  inc     r14d
0x18001b512  movss   [rbp+57h+var_C8], xmm2
0x18001b517  movss   [rbp+57h+var_C4], xmm1
0x18001b51c  mov     [rbp+57h+var_C0], 1
0x18001b523  lea     rcx, [r13+18h]
0x18001b527  lea     rdx, [rbp+57h+var_C8]
0x18001b52b  call    ?push_back@?$vector@UCSegment@@V?$allocator@UCSegment@@@std@@@std@@QEAAX$$QEAUCSegment@@@Z; std::vector<CSegment>::push_back(CSegment &&)
0x18001b530  movaps  xmm2, xmm6
0x18001b533  movaps  xmm1, xmm7
0x18001b536  jmp     short loc_18001B4C5
0x18001b538  movss   [rbp+57h+var_BC], xmm2
0x18001b53d  movss   [rbp+57h+var_B8], xmm1
0x18001b542  mov     [rbp+57h+var_B4], 1
0x18001b549  lea     rcx, [r13+18h]
0x18001b54d  lea     rdx, [rbp+57h+var_BC]
0x18001b551  call    ?push_back@?$vector@UCSegment@@V?$allocator@UCSegment@@@std@@@std@@QEAAX$$QEAUCSegment@@@Z; std::vector<CSegment>::push_back(CSegment &&)
0x18001b556  movss   [rbp+57h+var_B0], xmm9
0x18001b55c  movss   [rbp+57h+var_AC], xmm8
0x18001b562  mov     [rbp+57h+var_A8], r14d
0x18001b566  lea     rcx, [r13+30h]
0x18001b56a  lea     rdx, [rbp+57h+var_B0]
0x18001b56e  call    ?push_back@?$vector@UCSegment@@V?$allocator@UCSegment@@@std@@@std@@QEAAX$$QEAUCSegment@@@Z; std::vector<CSegment>::push_back(CSegment &&)
0x18001b573  movaps  xmm9, xmm8
0x18001b577  movss   xmm0, dword ptr [r15]
0x18001b57c  movss   [rsp+120h+var_D8], xmm0
0x18001b582  movss   xmm1, dword ptr [r15+8]
0x18001b588  movss   [rbp+57h+var_D4], xmm1
0x18001b58d  mov     [rbp+57h+var_D0], 1
0x18001b594  lea     rdx, [rbp+57h+var_98]
0x18001b598  lea     rcx, [rsp+120h+var_F0]
0x18001b59d  call    ?end@?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCCoordinate@@@std@@@std@@@2@XZ; std::vector<CCoordinate>::end(void)
0x18001b5a2  mov     r8, [rax]
0x18001b5a5  lea     rdx, [rbp+57h+var_90]
0x18001b5a9  lea     rcx, [rsp+120h+var_F0]
0x18001b5ae  call    ?begin@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UtagRGBQUAD@@@std@@@std@@@2@XZ; std::vector<tagRGBQUAD>::begin(void)
0x18001b5b3  lea     r9, [rsp+120h+var_D8]
0x18001b5b8  mov     rdx, [rax]
0x18001b5bb  lea     rcx, [rbp+57h+arg_8]
0x18001b5bf  call    ??$lower_bound@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCSegment@@@std@@@std@@@std@@UCSegment@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCSegment@@@std@@@std@@@0@V10@0AEBUCSegment@@@Z; std::lower_bound<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CSegment>>>,CSegment>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CSegment>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CSegment>>>,CSegment const &)
0x18001b5c4  lea     rcx, [rsp+120h+var_F0]
0x18001b5c9  cmp     dword ptr [rdi+4], 0
0x18001b5cd  jge     short loc_18001B5E3
0x18001b5cf  lea     r9, [rsp+120h+var_D8]
0x18001b5d4  mov     r8, [rbp+57h+arg_8]
0x18001b5d8  lea     rdx, [rbp+57h+var_88]
0x18001b5dc  call    ??$emplace@AEBUCSegment@@@?$vector@UCSegment@@V?$allocator@UCSegment@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCSegment@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UCSegment@@@std@@@std@@@1@AEBUCSegment@@@Z; std::vector<CSegment>::emplace<CSegment const &>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CSegment>>>,CSegment const &)
0x18001b5e1  jmp     short loc_18001B603
0x18001b5e3  lea     rdx, [rbp+57h+var_80]
0x18001b5e7  call    ?end@?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCCoordinate@@@std@@@std@@@2@XZ; std::vector<CCoordinate>::end(void)
0x18001b5ec  mov     r8, [rbp+57h+arg_8]
0x18001b5f0  cmp     r8, [rax]
0x18001b5f3  jz      short loc_18001B603
0x18001b5f5  lea     rdx, [rbp+57h+var_78]
0x18001b5f9  lea     rcx, [rsp+120h+var_F0]
0x18001b5fe  call    ?erase@?$vector@UCSegment@@V?$allocator@UCSegment@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCSegment@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UCSegment@@@std@@@std@@@2@@Z; std::vector<CSegment>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CSegment>>>)
0x18001b603  add     rdi, 8
0x18001b607  jmp     loc_18001B420
0x18001b60c  lea     rcx, [rsp+120h+var_F0]
0x18001b611  call    ?_Tidy@?$vector@UCSegment@@V?$allocator@UCSegment@@@std@@@std@@AEAAXXZ; std::vector<CSegment>::_Tidy(void)
0x18001b616  lea     r11, [rsp+120h+var_30]
0x18001b61e  mov     rbx, [r11+40h]
0x18001b622  movaps  xmm6, xmmword ptr [r11-10h]
0x18001b627  movaps  xmm7, xmmword ptr [r11-20h]
0x18001b62c  movaps  xmm8, xmmword ptr [r11-30h]
0x18001b631  movaps  xmm9, xmmword ptr [r11-40h]
0x18001b636  mov     rsp, r11
0x18001b639  pop     r15
0x18001b63b  pop     r14
0x18001b63d  pop     r13
0x18001b63f  pop     r12
0x18001b641  pop     rdi
0x18001b642  pop     rsi
0x18001b643  pop     rbp
0x18001b644  retn
```
