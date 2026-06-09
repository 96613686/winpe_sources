# ??$_Sort@PEAV?$shared_ptr@VCConfigSource@@@std@@_JP6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@0_JP6AHV?$shared_ptr@$$CBVCConfigSource@@@0@2@_E@Z

- ea: `0x18000a9f0`
- end: `0x18000ada3`
- name: `??$_Sort@PEAV?$shared_ptr@VCConfigSource@@@std@@_JP6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@0_JP6AHV?$shared_ptr@$$CBVCConfigSource@@@0@2@_E@Z`
- size: `947`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a9f0`
- `0x18000b31c`

## callees

- `0x180007d68`
- `0x180009068`
- `0x18000a6e0`
- `0x18000a9f0`
- `0x18000adac`
- `0x18000b270`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ____Sort_PEAV__shared_ptr_VCConfigSource___std___JP6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSource___0_0_JP6AHV__shared_ptr___CBVCConfigSource___0_2__E_Z(
        __int64 *a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 *v4; // r14
  __int64 *v5; // rsi
  __int64 result; // rax
  __int64 *v7; // rdi
  __int64 *v8; // r15
  __int64 v9; // rbx
  __int64 v10; // r12
  __int64 *v11; // rdx
  volatile signed __int32 *v12; // rdi
  __int64 *v13; // rdi
  __int64 *v14; // r14
  volatile signed __int32 *v15; // rbx
  __int64 *v16; // rdi
  _QWORD *v17; // rbx
  _QWORD *v18; // rax
  __int64 *v19; // r12
  __int64 *v20; // rbx
  __int64 *v21; // r13
  __int64 *i; // r12
  _QWORD *v23; // rbx
  _QWORD *v24; // rax
  volatile signed __int32 *v25; // rbx
  __int128 v26; // [rsp+30h] [rbp-59h] BYREF
  __int128 v27; // [rsp+40h] [rbp-49h] BYREF
  __int128 v28; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v29; // [rsp+60h] [rbp-29h] BYREF
  __int64 *v30; // [rsp+68h] [rbp-21h]
  __int64 v31; // [rsp+70h] [rbp-19h] BYREF
  __int64 v32; // [rsp+80h] [rbp-9h] BYREF
  __int64 v33[10]; // [rsp+90h] [rbp+7h] BYREF

  v4 = a2;
  v5 = a1;
  result = ((char *)a2 - (char *)a1) >> 4;
  if ( result <= 32 )
    goto LABEL_49;
  do
  {
    if ( a3 <= 0 )
      break;
    ____Unguarded_partition_PEAV__shared_ptr_VCConfigSource___std__P6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YA_AU__pair_PEAV__shared_ptr_VCConfigSource___std__PEAV12__0_PEAV__shared_ptr_VCConfigSource___0_0P6AHV__shared_ptr___CBVCConfigSource___0_1__E_Z(
      &v29,
      v5,
      v4);
    a3 = a3 / 2 / 2 + a3 / 2;
    v7 = v30;
    v8 = v29;
    if ( (__int64)(((char *)v29 - (char *)v5) & 0xFFFFFFFFFFFFFFF0uLL) >= (__int64)(((char *)v4 - (char *)v30)
                                                                                  & 0xFFFFFFFFFFFFFFF0uLL) )
    {
      ____Sort_PEAV__shared_ptr_VCConfigSource___std___JP6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSource___0_0_JP6AHV__shared_ptr___CBVCConfigSource___0_2__E_Z(
        v30,
        v4,
        a3,
        CompareSourceElements);
      v4 = v8;
    }
    else
    {
      ____Sort_PEAV__shared_ptr_VCConfigSource___std___JP6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSource___0_0_JP6AHV__shared_ptr___CBVCConfigSource___0_2__E_Z(
        v5,
        v29,
        a3,
        CompareSourceElements);
      v5 = v7;
    }
    result = ((char *)v4 - (char *)v5) >> 4;
  }
  while ( result > 32 );
  if ( result <= 32 )
  {
LABEL_49:
    if ( result > 1 && v5 != v4 )
    {
      v16 = v5 + 2;
      while ( v16 != v4 )
      {
        v26 = 0;
        if ( &v26 != (__int128 *)v16 )
        {
          *((_QWORD *)&v26 + 1) = v16[1];
          v16[1] = 0;
          *(_QWORD *)&v26 = *v16;
          *v16 = 0;
        }
        v17 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v29, v5);
        v18 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v31, (__int64 *)&v26);
        if ( (unsigned int)CompareSourceElements(v18, v17) )
        {
          v19 = v16 + 2;
          v20 = v16 + 2;
          while ( v16 != v5 )
          {
            v16 -= 2;
            v20 -= 2;
            std::shared_ptr<CConfigSet>::operator=(v20, v16);
          }
          result = std::shared_ptr<CConfigSet>::operator=(v5, &v26);
          v16 = v19;
        }
        else
        {
          v21 = v16;
          for ( i = v16; ; v21 = i )
          {
            i -= 2;
            v23 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v32, i);
            v24 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v33, (__int64 *)&v26);
            if ( !(unsigned int)CompareSourceElements(v24, v23) )
              break;
            std::shared_ptr<CConfigSet>::operator=(v21, i);
          }
          result = std::shared_ptr<CConfigSet>::operator=(v21, &v26);
          v16 += 2;
        }
        v25 = (volatile signed __int32 *)*((_QWORD *)&v26 + 1);
        if ( *((_QWORD *)&v26 + 1) )
        {
          result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 8LL));
          if ( !(_DWORD)result )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            result = (unsigned int)_InterlockedDecrement(v25 + 3);
            if ( !(_DWORD)result )
              result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
      }
    }
  }
  else
  {
    v9 = ((char *)v4 - (char *)v5) >> 4;
    if ( v9 <= 1 || (result = v9 / 2, v10 = v9 / 2, v9 / 2 <= 0) )
    {
      v13 = v4;
      if ( v9 <= 1 )
        return result;
    }
    else
    {
      do
      {
        --v10;
        v11 = &v5[2 * v10];
        v27 = 0;
        if ( &v27 != (__int128 *)v11 )
        {
          *((_QWORD *)&v27 + 1) = v11[1];
          v11[1] = 0;
          *(_QWORD *)&v27 = *v11;
          *v11 = 0;
        }
        ____Adjust_heap_PEAV__shared_ptr_VCConfigSource___std___JV12_P6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSource___0__J1__QEAV10_P6AHV__shared_ptr___CBVCConfigSource___0_3__E_Z(
          (__int64)v5,
          v10,
          ((char *)v4 - (char *)v5) >> 4,
          (__int64 *)&v27);
        v12 = (volatile signed __int32 *)*((_QWORD *)&v27 + 1);
        if ( *((_QWORD *)&v27 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v27 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
            if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
          }
        }
      }
      while ( v10 > 0 );
      v13 = v4;
    }
    v14 = v4 - 2;
    do
    {
      v28 = 0;
      if ( &v28 != (__int128 *)v14 )
      {
        *((_QWORD *)&v28 + 1) = v14[1];
        v14[1] = 0;
        *(_QWORD *)&v28 = *v14;
        *v14 = 0;
      }
      std::shared_ptr<CConfigSet>::operator=(v14, v5);
      ____Adjust_heap_PEAV__shared_ptr_VCConfigSource___std___JV12_P6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSource___0__J1__QEAV10_P6AHV__shared_ptr___CBVCConfigSource___0_3__E_Z(
        (__int64)v5,
        0,
        ((char *)v13 - (char *)v5 - 16) >> 4,
        (__int64 *)&v28);
      v15 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
      if ( *((_QWORD *)&v28 + 1)
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
      v13 -= 2;
      v14 -= 2;
      result = ((char *)v13 - (char *)v5) & 0xFFFFFFFFFFFFFFF0uLL;
    }
    while ( result > 16 );
  }
  return result;
}

```

## disassembly

```asm
0x18000a9f0  push    rbp
0x18000a9f2  push    rbx
0x18000a9f3  push    rsi
0x18000a9f4  push    rdi
0x18000a9f5  push    r12
0x18000a9f7  push    r13
0x18000a9f9  push    r14
0x18000a9fb  push    r15
0x18000a9fd  lea     rbp, [rsp-1Fh]
0x18000aa02  sub     rsp, 0A8h
0x18000aa09  mov     rbx, r8
0x18000aa0c  mov     r14, rdx
0x18000aa0f  mov     rsi, rcx
0x18000aa12  mov     rax, rdx
0x18000aa15  sub     rax, rcx
0x18000aa18  sar     rax, 4
0x18000aa1c  xor     r13d, r13d
0x18000aa1f  cmp     rax, 20h ; ' '
0x18000aa23  jle     loc_18000AC48
0x18000aa29  test    rbx, rbx
0x18000aa2c  jle     loc_18000AAB7
0x18000aa32  mov     r8, r14
0x18000aa35  mov     rdx, rsi
0x18000aa38  lea     rcx, [rbp+57h+var_80]
0x18000aa3c  call    ??$_Unguarded_partition@PEAV?$shared_ptr@VCConfigSource@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YA?AU?$pair@PEAV?$shared_ptr@VCConfigSource@@@std@@PEAV12@@0@PEAV?$shared_ptr@VCConfigSource@@@0@0P6AHV?$shared_ptr@$$CBVCConfigSource@@@0@1@_E@Z
0x18000aa41  mov     rax, rbx
0x18000aa44  cqo
0x18000aa46  sub     rax, rdx
0x18000aa49  sar     rax, 1
0x18000aa4c  mov     rbx, rax
0x18000aa4f  cqo
0x18000aa51  sub     rax, rdx
0x18000aa54  sar     rax, 1
0x18000aa57  add     rbx, rax
0x18000aa5a  mov     rcx, r14
0x18000aa5d  mov     rdi, [rbp+57h+var_78]
0x18000aa61  sub     rcx, rdi
0x18000aa64  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000aa68  mov     r15, [rbp+57h+var_80]
0x18000aa6c  mov     rax, r15
0x18000aa6f  sub     rax, rsi
0x18000aa72  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000aa76  lea     r9, ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000aa7d  mov     r8, rbx
0x18000aa80  cmp     rax, rcx
0x18000aa83  jge     short loc_18000AA95
0x18000aa85  mov     rdx, r15
0x18000aa88  mov     rcx, rsi
0x18000aa8b  call    ??$_Sort@PEAV?$shared_ptr@VCConfigSource@@@std@@_JP6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@0_JP6AHV?$shared_ptr@$$CBVCConfigSource@@@0@2@_E@Z
0x18000aa90  mov     rsi, rdi
0x18000aa93  jmp     short loc_18000AAA3
0x18000aa95  mov     rdx, r14
0x18000aa98  mov     rcx, rdi
0x18000aa9b  call    ??$_Sort@PEAV?$shared_ptr@VCConfigSource@@@std@@_JP6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@0_JP6AHV?$shared_ptr@$$CBVCConfigSource@@@0@2@_E@Z
0x18000aaa0  mov     r14, r15
0x18000aaa3  mov     rax, r14
0x18000aaa6  sub     rax, rsi
0x18000aaa9  sar     rax, 4
0x18000aaad  cmp     rax, 20h ; ' '
0x18000aab1  jg      loc_18000AA29
0x18000aab7  cmp     rax, 20h ; ' '
0x18000aabb  jle     loc_18000AC48
0x18000aac1  mov     rbx, r14
0x18000aac4  sub     rbx, rsi
0x18000aac7  sar     rbx, 4
0x18000aacb  or      r15d, 0FFFFFFFFh
0x18000aacf  cmp     rbx, 1
0x18000aad3  jle     loc_18000AB86
0x18000aad9  mov     rax, rbx
0x18000aadc  cqo
0x18000aade  sub     rax, rdx
0x18000aae1  sar     rax, 1
0x18000aae4  mov     r12, rax
0x18000aae7  test    rax, rax
0x18000aaea  jle     loc_18000AB86
0x18000aaf0  dec     r12
0x18000aaf3  mov     rdx, r12
0x18000aaf6  shl     rdx, 4
0x18000aafa  add     rdx, rsi
0x18000aafd  xorps   xmm0, xmm0
0x18000ab00  movdqu  [rbp+57h+var_A0], xmm0
0x18000ab05  lea     rax, [rbp+57h+var_A0]
0x18000ab09  cmp     rax, rdx
0x18000ab0c  jz      short loc_18000AB24
0x18000ab0e  mov     rax, [rdx+8]
0x18000ab12  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18000ab16  mov     [rdx+8], r13
0x18000ab1a  mov     rax, [rdx]
0x18000ab1d  mov     qword ptr [rbp+57h+var_A0], rax
0x18000ab21  mov     [rdx], r13
0x18000ab24  lea     r9, [rbp+57h+var_A0]
0x18000ab28  mov     r8, rbx
0x18000ab2b  mov     rdx, r12
0x18000ab2e  mov     rcx, rsi
0x18000ab31  call    ??$_Adjust_heap@PEAV?$shared_ptr@VCConfigSource@@@std@@_JV12@P6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@_J1$$QEAV10@P6AHV?$shared_ptr@$$CBVCConfigSource@@@0@3@_E@Z
0x18000ab36  nop
0x18000ab37  mov     rdi, qword ptr [rbp+57h+var_A0+8]
0x18000ab3b  test    rdi, rdi
0x18000ab3e  jz      short loc_18000AB78
0x18000ab40  mov     eax, r15d
0x18000ab43  lock xadd [rdi+8], eax
0x18000ab48  add     eax, r15d
0x18000ab4b  jnz     short loc_18000AB78
0x18000ab4d  mov     rax, [rdi]
0x18000ab50  mov     rcx, rdi
0x18000ab53  mov     rax, [rax]
0x18000ab56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab5b  mov     eax, r15d
0x18000ab5e  lock xadd [rdi+0Ch], eax
0x18000ab63  add     eax, r15d
0x18000ab66  jnz     short loc_18000AB78
0x18000ab68  mov     rax, [rdi]
0x18000ab6b  mov     rcx, rdi
0x18000ab6e  mov     rax, [rax+8]
0x18000ab72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab77  nop
0x18000ab78  test    r12, r12
0x18000ab7b  jg      loc_18000AAF0
0x18000ab81  mov     rdi, r14
0x18000ab84  jmp     short loc_18000AB93
0x18000ab86  mov     rdi, r14
0x18000ab89  cmp     rbx, 1
0x18000ab8d  jle     loc_18000AD8F
0x18000ab93  add     r14, 0FFFFFFFFFFFFFFF0h
0x18000ab97  xorps   xmm0, xmm0
0x18000ab9a  movdqu  [rbp+57h+var_90], xmm0
0x18000ab9f  lea     rax, [rbp+57h+var_90]
0x18000aba3  cmp     rax, r14
0x18000aba6  jz      short loc_18000ABBE
0x18000aba8  mov     rax, [r14+8]
0x18000abac  mov     qword ptr [rbp+57h+var_90+8], rax
0x18000abb0  mov     [r14+8], r13
0x18000abb4  mov     rax, [r14]
0x18000abb7  mov     qword ptr [rbp+57h+var_90], rax
0x18000abbb  mov     [r14], r13
0x18000abbe  mov     rdx, rsi
0x18000abc1  mov     rcx, r14
0x18000abc4  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000abc9  mov     r8, rdi
0x18000abcc  sub     r8, rsi
0x18000abcf  sub     r8, 10h
0x18000abd3  sar     r8, 4
0x18000abd7  lea     r9, [rbp+57h+var_90]
0x18000abdb  xor     edx, edx
0x18000abdd  mov     rcx, rsi
0x18000abe0  call    ??$_Adjust_heap@PEAV?$shared_ptr@VCConfigSource@@@std@@_JV12@P6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@_J1$$QEAV10@P6AHV?$shared_ptr@$$CBVCConfigSource@@@0@3@_E@Z
0x18000abe5  nop
0x18000abe6  mov     rbx, qword ptr [rbp+57h+var_90+8]
0x18000abea  test    rbx, rbx
0x18000abed  jz      short loc_18000AC27
0x18000abef  mov     eax, r15d
0x18000abf2  lock xadd [rbx+8], eax
0x18000abf7  add     eax, r15d
0x18000abfa  jnz     short loc_18000AC27
0x18000abfc  mov     rax, [rbx]
0x18000abff  mov     rcx, rbx
0x18000ac02  mov     rax, [rax]
0x18000ac05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac0a  mov     eax, r15d
0x18000ac0d  lock xadd [rbx+0Ch], eax
0x18000ac12  add     eax, r15d
0x18000ac15  jnz     short loc_18000AC27
0x18000ac17  mov     rax, [rbx]
0x18000ac1a  mov     rcx, rbx
0x18000ac1d  mov     rax, [rax+8]
0x18000ac21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac26  nop
0x18000ac27  sub     rdi, 10h
0x18000ac2b  sub     r14, 10h
0x18000ac2f  mov     rax, rdi
0x18000ac32  sub     rax, rsi
0x18000ac35  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000ac39  cmp     rax, 10h
0x18000ac3d  jg      loc_18000AB97
0x18000ac43  jmp     loc_18000AD8F
0x18000ac48  cmp     rax, 1
0x18000ac4c  jle     loc_18000AD8F
0x18000ac52  cmp     rsi, r14
0x18000ac55  jz      loc_18000AD8F
0x18000ac5b  lea     rdi, [rsi+10h]
0x18000ac5f  cmp     rdi, r14
0x18000ac62  jz      loc_18000AD8F
0x18000ac68  or      r15d, 0FFFFFFFFh
0x18000ac6c  xorps   xmm0, xmm0
0x18000ac6f  movdqu  [rbp+57h+var_B0], xmm0
0x18000ac74  lea     rax, [rbp+57h+var_B0]
0x18000ac78  cmp     rax, rdi
0x18000ac7b  jz      short loc_18000AC93
0x18000ac7d  mov     rax, [rdi+8]
0x18000ac81  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18000ac85  mov     [rdi+8], r13
0x18000ac89  mov     rax, [rdi]
0x18000ac8c  mov     qword ptr [rbp+57h+var_B0], rax
0x18000ac90  mov     [rdi], r13
0x18000ac93  mov     rdx, rsi
0x18000ac96  lea     rcx, [rbp+57h+var_80]
0x18000ac9a  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000ac9f  mov     rbx, rax
0x18000aca2  lea     rdx, [rbp+57h+var_B0]
0x18000aca6  lea     rcx, [rbp+57h+var_70]
0x18000acaa  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000acaf  mov     rdx, rbx
0x18000acb2  mov     rcx, rax
0x18000acb5  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000acba  test    eax, eax
0x18000acbc  jz      short loc_18000ACF0
0x18000acbe  lea     r12, [rdi+10h]
0x18000acc2  mov     rbx, r12
0x18000acc5  jmp     short loc_18000ACDA
0x18000acc7  sub     rdi, 10h
0x18000accb  sub     rbx, 10h
0x18000accf  mov     rdx, rdi
0x18000acd2  mov     rcx, rbx
0x18000acd5  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000acda  cmp     rdi, rsi
0x18000acdd  jnz     short loc_18000ACC7
0x18000acdf  lea     rdx, [rbp+57h+var_B0]
0x18000ace3  mov     rcx, rsi
0x18000ace6  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000aceb  mov     rdi, r12
0x18000acee  jmp     short loc_18000AD45
0x18000acf0  mov     r13, rdi
0x18000acf3  mov     r12, rdi
0x18000acf6  sub     r12, 10h
0x18000acfa  mov     rdx, r12
0x18000acfd  lea     rcx, [rbp+57h+var_60]
0x18000ad01  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000ad06  mov     rbx, rax
0x18000ad09  lea     rdx, [rbp+57h+var_B0]
0x18000ad0d  lea     rcx, [rbp+57h+var_50]
0x18000ad11  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000ad16  mov     rdx, rbx
0x18000ad19  mov     rcx, rax
0x18000ad1c  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000ad21  mov     rcx, r13
0x18000ad24  test    eax, eax
0x18000ad26  jz      short loc_18000AD35
0x18000ad28  mov     rdx, r12
0x18000ad2b  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000ad30  mov     r13, r12
0x18000ad33  jmp     short loc_18000ACF6
0x18000ad35  lea     rdx, [rbp+57h+var_B0]
0x18000ad39  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000ad3e  add     rdi, 10h
0x18000ad42  xor     r13d, r13d
0x18000ad45  mov     rbx, qword ptr [rbp+57h+var_B0+8]
0x18000ad49  test    rbx, rbx
0x18000ad4c  jz      short loc_18000AD86
0x18000ad4e  mov     eax, r15d
0x18000ad51  lock xadd [rbx+8], eax
0x18000ad56  add     eax, r15d
0x18000ad59  jnz     short loc_18000AD86
0x18000ad5b  mov     rax, [rbx]
0x18000ad5e  mov     rcx, rbx
0x18000ad61  mov     rax, [rax]
0x18000ad64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad69  mov     eax, r15d
0x18000ad6c  lock xadd [rbx+0Ch], eax
0x18000ad71  add     eax, r15d
0x18000ad74  jnz     short loc_18000AD86
0x18000ad76  mov     rax, [rbx]
0x18000ad79  mov     rcx, rbx
0x18000ad7c  mov     rax, [rax+8]
0x18000ad80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad85  nop
0x18000ad86  cmp     rdi, r14
0x18000ad89  jnz     loc_18000AC6C
0x18000ad8f  add     rsp, 0A8h
0x18000ad96  pop     r15
0x18000ad98  pop     r14
0x18000ad9a  pop     r13
0x18000ad9c  pop     r12
0x18000ad9e  pop     rdi
0x18000ad9f  pop     rsi
0x18000ada0  pop     rbx
0x18000ada1  pop     rbp
0x18000ada2  retn
```
