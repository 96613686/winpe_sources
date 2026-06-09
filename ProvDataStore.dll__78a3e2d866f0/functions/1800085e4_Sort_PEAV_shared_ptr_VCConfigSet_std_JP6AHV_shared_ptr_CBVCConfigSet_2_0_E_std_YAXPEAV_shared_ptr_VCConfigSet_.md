# ??$_Sort@PEAV?$shared_ptr@VCConfigSet@@@std@@_JP6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@0_JP6AHV?$shared_ptr@$$CBVCConfigSet@@@0@2@_E@Z

- ea: `0x1800085e4`
- end: `0x1800089d6`
- name: `??$_Sort@PEAV?$shared_ptr@VCConfigSet@@@std@@_JP6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@0_JP6AHV?$shared_ptr@$$CBVCConfigSet@@@0@2@_E@Z`
- size: `1010`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, __int64, unsigned int (__fastcall *)(_QWORD *, _QWORD *))`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800085e4`
- `0x180009800`

## callees

- `0x180007d68`
- `0x180008368`
- `0x1800085e4`
- `0x1800089dc`
- `0x180009068`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ____Sort_PEAV__shared_ptr_VCConfigSet___std___JP6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSet___0_0_JP6AHV__shared_ptr___CBVCConfigSet___0_2__E_Z(
        __int64 *a1,
        __int64 *a2,
        __int64 a3,
        unsigned int (__fastcall *a4)(_QWORD *, _QWORD *))
{
  unsigned int (__fastcall *v4)(_QWORD *, _QWORD *); // r13
  __int64 *v6; // r14
  __int64 *v7; // rsi
  __int64 result; // rax
  __int64 *v9; // rdi
  __int64 *v10; // r15
  __int64 v11; // rbx
  __int64 v12; // r12
  __int64 *v13; // rdx
  volatile signed __int32 *v14; // rdi
  __int64 *v15; // rdi
  __int64 *v16; // r14
  volatile signed __int32 *v17; // rbx
  __int64 *v18; // rdi
  _QWORD *v19; // rbx
  _QWORD *v20; // rax
  __int64 *v21; // r12
  __int64 *v22; // rbx
  __int64 *v23; // r12
  __int64 *i; // r13
  _QWORD *v25; // rbx
  _QWORD *v26; // rax
  volatile signed __int32 *v27; // rbx
  __int128 v28; // [rsp+30h] [rbp-49h] BYREF
  __int128 v29; // [rsp+40h] [rbp-39h] BYREF
  __int128 v30; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v31; // [rsp+60h] [rbp-19h] BYREF
  __int64 *v32; // [rsp+68h] [rbp-11h]
  __int64 v33; // [rsp+70h] [rbp-9h] BYREF
  __int64 v34; // [rsp+80h] [rbp+7h] BYREF
  __int64 v35[8]; // [rsp+90h] [rbp+17h] BYREF

  v4 = a4;
  v6 = a2;
  v7 = a1;
  result = ((char *)a2 - (char *)a1) >> 4;
  if ( result <= 32 )
    goto LABEL_49;
  do
  {
    if ( a3 <= 0 )
      break;
    ____Unguarded_partition_PEAV__shared_ptr_VCConfigSet___std__P6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YA_AU__pair_PEAV__shared_ptr_VCConfigSet___std__PEAV12__0_PEAV__shared_ptr_VCConfigSet___0_0P6AHV__shared_ptr___CBVCConfigSet___0_1__E_Z(
      &v31,
      v7,
      v6,
      v4);
    a3 = a3 / 2 / 2 + a3 / 2;
    v9 = v32;
    v10 = v31;
    if ( (__int64)(((char *)v31 - (char *)v7) & 0xFFFFFFFFFFFFFFF0uLL) >= (__int64)(((char *)v6 - (char *)v32)
                                                                                  & 0xFFFFFFFFFFFFFFF0uLL) )
    {
      ____Sort_PEAV__shared_ptr_VCConfigSet___std___JP6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSet___0_0_JP6AHV__shared_ptr___CBVCConfigSet___0_2__E_Z(
        v32,
        v6,
        a3,
        v4);
      v6 = v10;
    }
    else
    {
      ____Sort_PEAV__shared_ptr_VCConfigSet___std___JP6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSet___0_0_JP6AHV__shared_ptr___CBVCConfigSet___0_2__E_Z(
        v7,
        v31,
        a3,
        v4);
      v7 = v9;
    }
    result = ((char *)v6 - (char *)v7) >> 4;
  }
  while ( result > 32 );
  if ( result <= 32 )
  {
LABEL_49:
    if ( result > 1 && v7 != v6 )
    {
      v18 = v7 + 2;
      while ( v18 != v6 )
      {
        v28 = 0;
        if ( &v28 != (__int128 *)v18 )
        {
          *((_QWORD *)&v28 + 1) = v18[1];
          v18[1] = 0;
          *(_QWORD *)&v28 = *v18;
          *v18 = 0;
        }
        v19 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v31, v7);
        v20 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v33, (__int64 *)&v28);
        if ( v4(v20, v19) )
        {
          v21 = v18 + 2;
          v22 = v18 + 2;
          while ( v18 != v7 )
          {
            v18 -= 2;
            v22 -= 2;
            std::shared_ptr<CConfigSet>::operator=(v22, v18);
          }
          result = std::shared_ptr<CConfigSet>::operator=(v7, &v28);
          v18 = v21;
        }
        else
        {
          v23 = v18;
          for ( i = v18; ; v23 = i )
          {
            i -= 2;
            v25 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v34, i);
            v26 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v35, (__int64 *)&v28);
            if ( !a4(v26, v25) )
              break;
            std::shared_ptr<CConfigSet>::operator=(v23, i);
          }
          result = std::shared_ptr<CConfigSet>::operator=(v23, &v28);
          v18 += 2;
          v4 = a4;
        }
        v27 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
        if ( *((_QWORD *)&v28 + 1) )
        {
          result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL));
          if ( !(_DWORD)result )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
            result = (unsigned int)_InterlockedDecrement(v27 + 3);
            if ( !(_DWORD)result )
              result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
          }
        }
      }
    }
  }
  else
  {
    v11 = ((char *)v6 - (char *)v7) >> 4;
    if ( v11 <= 1 || (result = v11 / 2, v12 = v11 / 2, v11 / 2 <= 0) )
    {
      v15 = v6;
      if ( v11 <= 1 )
        return result;
    }
    else
    {
      do
      {
        --v12;
        v13 = &v7[2 * v12];
        v29 = 0;
        if ( &v29 != (__int128 *)v13 )
        {
          *((_QWORD *)&v29 + 1) = v13[1];
          v13[1] = 0;
          *(_QWORD *)&v29 = *v13;
          *v13 = 0;
        }
        ____Adjust_heap_PEAV__shared_ptr_VCConfigSet___std___JV12_P6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSet___0__J1__QEAV10_P6AHV__shared_ptr___CBVCConfigSet___0_3__E_Z(
          (__int64)v7,
          v12,
          ((char *)v6 - (char *)v7) >> 4,
          (__int64 *)&v29,
          v4);
        v14 = (volatile signed __int32 *)*((_QWORD *)&v29 + 1);
        if ( *((_QWORD *)&v29 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
            if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
          }
        }
      }
      while ( v12 > 0 );
      v15 = v6;
    }
    v16 = v6 - 2;
    do
    {
      v30 = 0;
      if ( &v30 != (__int128 *)v16 )
      {
        *((_QWORD *)&v30 + 1) = v16[1];
        v16[1] = 0;
        *(_QWORD *)&v30 = *v16;
        *v16 = 0;
      }
      std::shared_ptr<CConfigSet>::operator=(v16, v7);
      ____Adjust_heap_PEAV__shared_ptr_VCConfigSet___std___JV12_P6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSet___0__J1__QEAV10_P6AHV__shared_ptr___CBVCConfigSet___0_3__E_Z(
        (__int64)v7,
        0,
        ((char *)v15 - (char *)v7 - 16) >> 4,
        (__int64 *)&v30,
        v4);
      v17 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
      if ( *((_QWORD *)&v30 + 1)
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
      v15 -= 2;
      v16 -= 2;
      result = ((char *)v15 - (char *)v7) & 0xFFFFFFFFFFFFFFF0uLL;
    }
    while ( result > 16 );
  }
  return result;
}

```

## disassembly

```asm
0x1800085e4  mov     [rsp-8+arg_8], rbx
0x1800085e9  mov     [rsp-8+arg_18], r9
0x1800085ee  push    rbp
0x1800085ef  push    rsi
0x1800085f0  push    rdi
0x1800085f1  push    r12
0x1800085f3  push    r13
0x1800085f5  push    r14
0x1800085f7  push    r15
0x1800085f9  lea     rbp, [rsp-27h]
0x1800085fe  sub     rsp, 0A0h
0x180008605  mov     r13, r9
0x180008608  mov     rbx, r8
0x18000860b  mov     r14, rdx
0x18000860e  mov     rsi, rcx
0x180008611  mov     rax, rdx
0x180008614  sub     rax, rcx
0x180008617  sar     rax, 4
0x18000861b  cmp     rax, 20h ; ' '
0x18000861f  jle     loc_18000885D
0x180008625  test    rbx, rbx
0x180008628  jle     loc_1800086B2
0x18000862e  mov     r9, r13
0x180008631  mov     r8, r14
0x180008634  mov     rdx, rsi
0x180008637  lea     rcx, [rbp+57h+var_70]
0x18000863b  call    ??$_Unguarded_partition@PEAV?$shared_ptr@VCConfigSet@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YA?AU?$pair@PEAV?$shared_ptr@VCConfigSet@@@std@@PEAV12@@0@PEAV?$shared_ptr@VCConfigSet@@@0@0P6AHV?$shared_ptr@$$CBVCConfigSet@@@0@1@_E@Z
0x180008640  mov     rax, rbx
0x180008643  cqo
0x180008645  sub     rax, rdx
0x180008648  sar     rax, 1
0x18000864b  mov     rbx, rax
0x18000864e  cqo
0x180008650  sub     rax, rdx
0x180008653  sar     rax, 1
0x180008656  add     rbx, rax
0x180008659  mov     rcx, r14
0x18000865c  mov     rdi, [rbp+57h+var_68]
0x180008660  sub     rcx, rdi
0x180008663  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180008667  mov     r15, [rbp+57h+var_70]
0x18000866b  mov     rax, r15
0x18000866e  sub     rax, rsi
0x180008671  and     rax, 0FFFFFFFFFFFFFFF0h
0x180008675  mov     r9, r13
0x180008678  mov     r8, rbx
0x18000867b  cmp     rax, rcx
0x18000867e  jge     short loc_180008690
0x180008680  mov     rdx, r15
0x180008683  mov     rcx, rsi
0x180008686  call    ??$_Sort@PEAV?$shared_ptr@VCConfigSet@@@std@@_JP6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@0_JP6AHV?$shared_ptr@$$CBVCConfigSet@@@0@2@_E@Z
0x18000868b  mov     rsi, rdi
0x18000868e  jmp     short loc_18000869E
0x180008690  mov     rdx, r14
0x180008693  mov     rcx, rdi
0x180008696  call    ??$_Sort@PEAV?$shared_ptr@VCConfigSet@@@std@@_JP6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@0_JP6AHV?$shared_ptr@$$CBVCConfigSet@@@0@2@_E@Z
0x18000869b  mov     r14, r15
0x18000869e  mov     rax, r14
0x1800086a1  sub     rax, rsi
0x1800086a4  sar     rax, 4
0x1800086a8  cmp     rax, 20h ; ' '
0x1800086ac  jg      loc_180008625
0x1800086b2  cmp     rax, 20h ; ' '
0x1800086b6  jle     loc_18000885D
0x1800086bc  mov     rbx, r14
0x1800086bf  sub     rbx, rsi
0x1800086c2  sar     rbx, 4
0x1800086c6  or      r15d, 0FFFFFFFFh
0x1800086ca  cmp     rbx, 1
0x1800086ce  jle     loc_18000878E
0x1800086d4  mov     rax, rbx
0x1800086d7  cqo
0x1800086d9  sub     rax, rdx
0x1800086dc  sar     rax, 1
0x1800086df  mov     r12, rax
0x1800086e2  test    rax, rax
0x1800086e5  jle     loc_18000878E
0x1800086eb  dec     r12
0x1800086ee  mov     rdx, r12
0x1800086f1  shl     rdx, 4
0x1800086f5  add     rdx, rsi
0x1800086f8  xorps   xmm0, xmm0
0x1800086fb  movdqu  [rbp+57h+var_90], xmm0
0x180008700  lea     rax, [rbp+57h+var_90]
0x180008704  cmp     rax, rdx
0x180008707  jz      short loc_180008727
0x180008709  mov     rax, [rdx+8]
0x18000870d  mov     qword ptr [rbp+57h+var_90+8], rax
0x180008711  mov     qword ptr [rdx+8], 0
0x180008719  mov     rax, [rdx]
0x18000871c  mov     qword ptr [rbp+57h+var_90], rax
0x180008720  mov     qword ptr [rdx], 0
0x180008727  mov     [rsp+0D0h+var_B0], r13
0x18000872c  lea     r9, [rbp+57h+var_90]
0x180008730  mov     r8, rbx
0x180008733  mov     rdx, r12
0x180008736  mov     rcx, rsi
0x180008739  call    ??$_Adjust_heap@PEAV?$shared_ptr@VCConfigSet@@@std@@_JV12@P6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@_J1$$QEAV10@P6AHV?$shared_ptr@$$CBVCConfigSet@@@0@3@_E@Z
0x18000873e  nop
0x18000873f  mov     rdi, qword ptr [rbp+57h+var_90+8]
0x180008743  test    rdi, rdi
0x180008746  jz      short loc_180008780
0x180008748  mov     eax, r15d
0x18000874b  lock xadd [rdi+8], eax
0x180008750  add     eax, r15d
0x180008753  jnz     short loc_180008780
0x180008755  mov     rax, [rdi]
0x180008758  mov     rcx, rdi
0x18000875b  mov     rax, [rax]
0x18000875e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008763  mov     eax, r15d
0x180008766  lock xadd [rdi+0Ch], eax
0x18000876b  add     eax, r15d
0x18000876e  jnz     short loc_180008780
0x180008770  mov     rax, [rdi]
0x180008773  mov     rcx, rdi
0x180008776  mov     rax, [rax+8]
0x18000877a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000877f  nop
0x180008780  test    r12, r12
0x180008783  jg      loc_1800086EB
0x180008789  mov     rdi, r14
0x18000878c  jmp     short loc_18000879B
0x18000878e  mov     rdi, r14
0x180008791  cmp     rbx, 1
0x180008795  jle     loc_1800089BB
0x18000879b  add     r14, 0FFFFFFFFFFFFFFF0h
0x18000879f  xorps   xmm0, xmm0
0x1800087a2  movdqu  [rbp+57h+var_80], xmm0
0x1800087a7  lea     rax, [rbp+57h+var_80]
0x1800087ab  cmp     rax, r14
0x1800087ae  jz      short loc_1800087CE
0x1800087b0  mov     rax, [r14+8]
0x1800087b4  mov     qword ptr [rbp+57h+var_80+8], rax
0x1800087b8  mov     qword ptr [r14+8], 0
0x1800087c0  mov     rax, [r14]
0x1800087c3  mov     qword ptr [rbp+57h+var_80], rax
0x1800087c7  mov     qword ptr [r14], 0
0x1800087ce  mov     rdx, rsi
0x1800087d1  mov     rcx, r14
0x1800087d4  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x1800087d9  mov     r8, rdi
0x1800087dc  sub     r8, rsi
0x1800087df  sub     r8, 10h
0x1800087e3  sar     r8, 4
0x1800087e7  mov     [rsp+0D0h+var_B0], r13
0x1800087ec  lea     r9, [rbp+57h+var_80]
0x1800087f0  xor     edx, edx
0x1800087f2  mov     rcx, rsi
0x1800087f5  call    ??$_Adjust_heap@PEAV?$shared_ptr@VCConfigSet@@@std@@_JV12@P6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@_J1$$QEAV10@P6AHV?$shared_ptr@$$CBVCConfigSet@@@0@3@_E@Z
0x1800087fa  nop
0x1800087fb  mov     rbx, qword ptr [rbp+57h+var_80+8]
0x1800087ff  test    rbx, rbx
0x180008802  jz      short loc_18000883C
0x180008804  mov     eax, r15d
0x180008807  lock xadd [rbx+8], eax
0x18000880c  add     eax, r15d
0x18000880f  jnz     short loc_18000883C
0x180008811  mov     rax, [rbx]
0x180008814  mov     rcx, rbx
0x180008817  mov     rax, [rax]
0x18000881a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000881f  mov     eax, r15d
0x180008822  lock xadd [rbx+0Ch], eax
0x180008827  add     eax, r15d
0x18000882a  jnz     short loc_18000883C
0x18000882c  mov     rax, [rbx]
0x18000882f  mov     rcx, rbx
0x180008832  mov     rax, [rax+8]
0x180008836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000883b  nop
0x18000883c  sub     rdi, 10h
0x180008840  sub     r14, 10h
0x180008844  mov     rax, rdi
0x180008847  sub     rax, rsi
0x18000884a  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000884e  cmp     rax, 10h
0x180008852  jg      loc_18000879F
0x180008858  jmp     loc_1800089BB
0x18000885d  cmp     rax, 1
0x180008861  jle     loc_1800089BB
0x180008867  cmp     rsi, r14
0x18000886a  jz      loc_1800089BB
0x180008870  lea     rdi, [rsi+10h]
0x180008874  cmp     rdi, r14
0x180008877  jz      loc_1800089BB
0x18000887d  or      r15d, 0FFFFFFFFh
0x180008881  xorps   xmm0, xmm0
0x180008884  movdqu  [rbp+57h+var_A0], xmm0
0x180008889  lea     rax, [rbp+57h+var_A0]
0x18000888d  cmp     rax, rdi
0x180008890  jz      short loc_1800088B0
0x180008892  mov     rax, [rdi+8]
0x180008896  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18000889a  mov     qword ptr [rdi+8], 0
0x1800088a2  mov     rax, [rdi]
0x1800088a5  mov     qword ptr [rbp+57h+var_A0], rax
0x1800088a9  mov     qword ptr [rdi], 0
0x1800088b0  mov     rdx, rsi
0x1800088b3  lea     rcx, [rbp+57h+var_70]
0x1800088b7  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x1800088bc  mov     rbx, rax
0x1800088bf  lea     rdx, [rbp+57h+var_A0]
0x1800088c3  lea     rcx, [rbp+57h+var_60]
0x1800088c7  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x1800088cc  mov     rdx, rbx
0x1800088cf  mov     rcx, rax
0x1800088d2  mov     rax, r13
0x1800088d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088da  test    eax, eax
0x1800088dc  jz      short loc_180008910
0x1800088de  lea     r12, [rdi+10h]
0x1800088e2  mov     rbx, r12
0x1800088e5  jmp     short loc_1800088FA
0x1800088e7  sub     rdi, 10h
0x1800088eb  sub     rbx, 10h
0x1800088ef  mov     rdx, rdi
0x1800088f2  mov     rcx, rbx
0x1800088f5  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x1800088fa  cmp     rdi, rsi
0x1800088fd  jnz     short loc_1800088E7
0x1800088ff  lea     rdx, [rbp+57h+var_A0]
0x180008903  mov     rcx, rsi
0x180008906  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000890b  mov     rdi, r12
0x18000890e  jmp     short loc_180008971
0x180008910  mov     r12, rdi
0x180008913  mov     r13, rdi
0x180008916  mov     r15, [rbp+57h+arg_18]
0x18000891a  sub     r13, 10h
0x18000891e  mov     rdx, r13
0x180008921  lea     rcx, [rbp+57h+var_50]
0x180008925  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000892a  mov     rbx, rax
0x18000892d  lea     rdx, [rbp+57h+var_A0]
0x180008931  lea     rcx, [rbp+57h+var_40]
0x180008935  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000893a  mov     rdx, rbx
0x18000893d  mov     rcx, rax
0x180008940  mov     rax, r15
0x180008943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008948  mov     rcx, r12
0x18000894b  test    eax, eax
0x18000894d  jz      short loc_18000895C
0x18000894f  mov     rdx, r13
0x180008952  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x180008957  mov     r12, r13
0x18000895a  jmp     short loc_18000891A
0x18000895c  lea     rdx, [rbp+57h+var_A0]
0x180008960  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x180008965  add     rdi, 10h
0x180008969  or      r15d, 0FFFFFFFFh
0x18000896d  mov     r13, [rbp+57h+arg_18]
0x180008971  mov     rbx, qword ptr [rbp+57h+var_A0+8]
0x180008975  test    rbx, rbx
0x180008978  jz      short loc_1800089B2
0x18000897a  mov     eax, r15d
0x18000897d  lock xadd [rbx+8], eax
0x180008982  add     eax, r15d
0x180008985  jnz     short loc_1800089B2
0x180008987  mov     rax, [rbx]
0x18000898a  mov     rcx, rbx
0x18000898d  mov     rax, [rax]
0x180008990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008995  mov     eax, r15d
0x180008998  lock xadd [rbx+0Ch], eax
0x18000899d  add     eax, r15d
0x1800089a0  jnz     short loc_1800089B2
0x1800089a2  mov     rax, [rbx]
0x1800089a5  mov     rcx, rbx
0x1800089a8  mov     rax, [rax+8]
0x1800089ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089b1  nop
0x1800089b2  cmp     rdi, r14
0x1800089b5  jnz     loc_180008881
0x1800089bb  mov     rbx, [rsp+0D0h+arg_8]
0x1800089c3  add     rsp, 0A0h
0x1800089ca  pop     r15
0x1800089cc  pop     r14
0x1800089ce  pop     r13
0x1800089d0  pop     r12
0x1800089d2  pop     rdi
0x1800089d3  pop     rsi
0x1800089d4  pop     rbp
0x1800089d5  retn
```
