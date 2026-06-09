# std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>>,void *> *,std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>>,void *> * const)

- ea: `0x180011188`
- end: `0x1800112b1`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `297`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800112e8`

## callees

- `0x18000f91c`
- `0x180010e64`
- `0x180011188`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v5; // r13
  _QWORD *v6; // r12
  __int64 v7; // rsi
  __int64 v8; // rax
  __int64 i; // r10
  __int64 v10; // r11
  __int64 v11; // r15
  __int64 v12; // rax
  bool v13; // bl
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r14
  __int64 v17; // r13
  bool v18; // bl
  _QWORD *v19; // rax
  _QWORD *v21; // [rsp+20h] [rbp-20h] BYREF
  _QWORD *v22; // [rsp+28h] [rbp-18h]
  __int64 v23; // [rsp+30h] [rbp-10h]
  __int64 v25; // [rsp+88h] [rbp+48h]
  __int64 v26; // [rsp+90h] [rbp+50h]

  if ( a2 != a3 )
  {
    v5 = *(_QWORD **)(a2 + 8);
    v6 = (_QWORD *)a1[1];
    v7 = a1[3];
    v23 = a2;
    v21 = a1 + 1;
    v22 = v5;
    v8 = std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>::operator()<unsigned long>(
           (__int64)a1,
           a2 + 16);
    v11 = 2 * (*(_QWORD *)(v10 + 48) & v8);
    v25 = *(_QWORD *)(v7 + 16 * (*(_QWORD *)(v10 + 48) & v8));
    v12 = *(_QWORD *)(v7 + 16 * (*(_QWORD *)(v10 + 48) & v8) + 8);
    v26 = v12;
    while ( 1 )
    {
      v13 = i == v12;
      std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Range_eraser::_Bump_erased(&v21);
      if ( v13 )
        break;
      i = v23;
      v12 = v26;
      if ( v23 == a3 )
      {
        if ( v25 == a2 )
          *(_QWORD *)(v7 + 8 * v11) = v23;
        goto LABEL_14;
      }
    }
    if ( v25 == a2 )
    {
      *(_QWORD *)(v7 + 8 * v11) = v6;
      v5 = v6;
    }
    *(_QWORD *)(v7 + 8 * v11 + 8) = v5;
    for ( i = v23; i != a3; *(_QWORD *)(v7 + 8 * v16 + 8) = v6 )
    {
      v15 = std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>::operator()<unsigned long>(
              v14,
              i + 16);
      v16 = 2 * (a1[6] & v15);
      v17 = *(_QWORD *)(v7 + 16 * (a1[6] & v15) + 8);
      while ( 1 )
      {
        v18 = i == v17;
        std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Range_eraser::_Bump_erased(&v21);
        i = v23;
        if ( v18 )
          break;
        if ( v23 == a3 )
        {
          *(_QWORD *)(v7 + 8 * v16) = v23;
          goto LABEL_14;
        }
      }
      *(_QWORD *)(v7 + 8 * v16) = v6;
    }
LABEL_14:
    v19 = v22;
    *v22 = i;
    *(_QWORD *)(i + 8) = v19;
  }
  return a3;
}

```

## disassembly

```asm
0x180011188  mov     [rsp-38h+arg_18], rbx
0x18001118d  mov     [rsp-38h+arg_0], rcx
0x180011192  push    rbp
0x180011193  push    rsi
0x180011194  push    rdi
0x180011195  push    r12
0x180011197  push    r13
0x180011199  push    r14
0x18001119b  push    r15
0x18001119d  mov     rbp, rsp
0x1800111a0  sub     rsp, 40h
0x1800111a4  mov     rdi, r8
0x1800111a7  mov     r14, rdx
0x1800111aa  mov     r11, rcx
0x1800111ad  cmp     rdx, r8
0x1800111b0  jz      loc_180011286
0x1800111b6  mov     r13, [rdx+8]
0x1800111ba  lea     rax, [rcx+8]
0x1800111be  mov     r12, [rax]
0x1800111c1  mov     r10, rdx
0x1800111c4  mov     rsi, [rcx+18h]
0x1800111c8  mov     [rbp+var_10], rdx
0x1800111cc  add     rdx, 10h
0x1800111d0  mov     [rbp+var_20], rax
0x1800111d4  mov     [rbp+var_18], r13
0x1800111d8  call    ??$?RK@?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@QEBA_KAEBK@Z; std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>::operator()<ulong>(ulong const &)
0x1800111dd  mov     r15, rax
0x1800111e0  and     r15, [r11+30h]
0x1800111e4  add     r15, r15
0x1800111e7  mov     rax, [rsi+r15*8]
0x1800111eb  mov     [rbp+arg_8], rax
0x1800111ef  mov     rax, [rsi+r15*8+8]
0x1800111f4  mov     [rbp+arg_10], rax
0x1800111f8  cmp     r10, rax
0x1800111fb  lea     rcx, [rbp+var_20]
0x1800111ff  setz    bl
0x180011202  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Range_eraser::_Bump_erased(void)
0x180011207  test    bl, bl
0x180011209  jnz     short loc_180011224
0x18001120b  mov     r10, [rbp+var_10]
0x18001120f  mov     rax, [rbp+arg_10]
0x180011213  cmp     r10, rdi
0x180011216  jnz     short loc_1800111F8
0x180011218  cmp     [rbp+arg_8], r14
0x18001121c  jnz     short loc_18001127B
0x18001121e  mov     [rsi+r15*8], r10
0x180011222  jmp     short loc_18001127B
0x180011224  cmp     [rbp+arg_8], r14
0x180011228  jnz     short loc_180011231
0x18001122a  mov     [rsi+r15*8], r12
0x18001122e  mov     r13, r12
0x180011231  mov     [rsi+r15*8+8], r13
0x180011236  mov     r10, [rbp+var_10]
0x18001123a  cmp     r10, rdi
0x18001123d  jz      short loc_18001127B
0x18001123f  mov     r15, [rbp+arg_0]
0x180011243  lea     rdx, [r10+10h]
0x180011247  call    ??$?RK@?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@QEBA_KAEBK@Z; std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>::operator()<ulong>(ulong const &)
0x18001124c  mov     r14, rax
0x18001124f  and     r14, [r15+30h]
0x180011253  add     r14, r14
0x180011256  mov     r13, [rsi+r14*8+8]
0x18001125b  cmp     r10, r13
0x18001125e  lea     rcx, [rbp+var_20]
0x180011262  setz    bl
0x180011265  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Range_eraser::_Bump_erased(void)
0x18001126a  mov     r10, [rbp+var_10]
0x18001126e  test    bl, bl
0x180011270  jnz     short loc_1800112A1
0x180011272  cmp     r10, rdi
0x180011275  jnz     short loc_18001125B
0x180011277  mov     [rsi+r14*8], r10
0x18001127b  mov     rax, [rbp+var_18]
0x18001127f  mov     [rax], r10
0x180011282  mov     [r10+8], rax
0x180011286  mov     rbx, [rsp+40h+arg_18]
0x18001128e  mov     rax, rdi
0x180011291  add     rsp, 40h
0x180011295  pop     r15
0x180011297  pop     r14
0x180011299  pop     r13
0x18001129b  pop     r12
0x18001129d  pop     rdi
0x18001129e  pop     rsi
0x18001129f  pop     rbp
0x1800112a0  retn
0x1800112a1  mov     [rsi+r14*8], r12
0x1800112a5  mov     [rsi+r14*8+8], r12
0x1800112aa  cmp     r10, rdi
0x1800112ad  jnz     short loc_180011243
0x1800112af  jmp     short loc_18001127B
```
