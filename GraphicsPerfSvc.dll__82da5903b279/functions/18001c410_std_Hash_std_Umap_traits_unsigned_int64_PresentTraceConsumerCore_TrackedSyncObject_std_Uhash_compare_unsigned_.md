# std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Unchecked_erase(std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *> *,std::_List_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>,void *> * const)

- ea: `0x18001c410`
- end: `0x18001c545`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `309`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c76c`

## callees

- `0x18001b468`
- `0x18001baec`
- `0x18001c410`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v6; // r13
  _QWORD *v7; // r12
  __int64 v8; // rsi
  __int64 appended; // rax
  __int64 i; // r11
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
    v6 = *(_QWORD **)(a2 + 8);
    v7 = (_QWORD *)a1[1];
    v8 = a1[3];
    v23 = a2;
    v21 = a1 + 1;
    v22 = v6;
    appended = std::_Fnv1a_append_bytes((__int64)a1, (const unsigned __int8 *const)(a2 + 16), 8u);
    v11 = 2 * (a1[6] & appended);
    v25 = *(_QWORD *)(v8 + 16 * (a1[6] & appended));
    v12 = *(_QWORD *)(v8 + 16 * (a1[6] & appended) + 8);
    v26 = v12;
    while ( 1 )
    {
      v13 = i == v12;
      std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Range_eraser::_Bump_erased(&v21);
      if ( v13 )
        break;
      i = v23;
      v12 = v26;
      if ( v23 == a3 )
      {
        if ( v25 == a2 )
          *(_QWORD *)(v8 + 8 * v11) = v23;
        goto LABEL_14;
      }
    }
    if ( v25 == a2 )
    {
      *(_QWORD *)(v8 + 8 * v11) = v7;
      v6 = v7;
    }
    *(_QWORD *)(v8 + 8 * v11 + 8) = v6;
    for ( i = v23; i != a3; *(_QWORD *)(v8 + 8 * v16 + 8) = v7 )
    {
      v15 = std::_Fnv1a_append_bytes(v14, (const unsigned __int8 *const)(i + 16), 8u);
      v16 = 2 * (a1[6] & v15);
      v17 = *(_QWORD *)(v8 + 16 * (a1[6] & v15) + 8);
      while ( 1 )
      {
        v18 = i == v17;
        std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Range_eraser::_Bump_erased(&v21);
        i = v23;
        if ( v18 )
          break;
        if ( v23 == a3 )
        {
          *(_QWORD *)(v8 + 8 * v16) = v23;
          goto LABEL_14;
        }
      }
      *(_QWORD *)(v8 + 8 * v16) = v7;
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
0x18001c410  mov     [rsp-38h+arg_18], rbx
0x18001c415  mov     [rsp-38h+arg_0], rcx
0x18001c41a  push    rbp
0x18001c41b  push    rsi
0x18001c41c  push    rdi
0x18001c41d  push    r12
0x18001c41f  push    r13
0x18001c421  push    r14
0x18001c423  push    r15
0x18001c425  mov     rbp, rsp
0x18001c428  sub     rsp, 40h
0x18001c42c  mov     rdi, r8
0x18001c42f  mov     r14, rdx
0x18001c432  mov     rbx, rcx
0x18001c435  cmp     rdx, r8
0x18001c438  jz      loc_18001C51A
0x18001c43e  mov     r13, [rdx+8]
0x18001c442  lea     rax, [rcx+8]
0x18001c446  mov     r12, [rax]
0x18001c449  mov     r11, rdx
0x18001c44c  mov     rsi, [rcx+18h]
0x18001c450  mov     r8d, 8; unsigned __int64
0x18001c456  mov     [rbp+var_10], rdx
0x18001c45a  add     rdx, 10h; unsigned __int8 *
0x18001c45e  mov     [rbp+var_20], rax
0x18001c462  mov     [rbp+var_18], r13
0x18001c466  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001c46b  mov     r15, rax
0x18001c46e  and     r15, [rbx+30h]
0x18001c472  add     r15, r15
0x18001c475  mov     rax, [rsi+r15*8]
0x18001c479  mov     [rbp+arg_8], rax
0x18001c47d  mov     rax, [rsi+r15*8+8]
0x18001c482  mov     [rbp+arg_10], rax
0x18001c486  cmp     r11, rax
0x18001c489  lea     rcx, [rbp+var_20]
0x18001c48d  setz    bl
0x18001c490  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Range_eraser::_Bump_erased(void)
0x18001c495  test    bl, bl
0x18001c497  jnz     short loc_18001C4B2
0x18001c499  mov     r11, [rbp+var_10]
0x18001c49d  mov     rax, [rbp+arg_10]
0x18001c4a1  cmp     r11, rdi
0x18001c4a4  jnz     short loc_18001C486
0x18001c4a6  cmp     [rbp+arg_8], r14
0x18001c4aa  jnz     short loc_18001C50F
0x18001c4ac  mov     [rsi+r15*8], r11
0x18001c4b0  jmp     short loc_18001C50F
0x18001c4b2  cmp     [rbp+arg_8], r14
0x18001c4b6  jnz     short loc_18001C4BF
0x18001c4b8  mov     [rsi+r15*8], r12
0x18001c4bc  mov     r13, r12
0x18001c4bf  mov     [rsi+r15*8+8], r13
0x18001c4c4  mov     r11, [rbp+var_10]
0x18001c4c8  cmp     r11, rdi
0x18001c4cb  jz      short loc_18001C50F
0x18001c4cd  mov     r15, [rbp+arg_0]
0x18001c4d1  lea     rdx, [r11+10h]; unsigned __int8 *
0x18001c4d5  mov     r8d, 8; unsigned __int64
0x18001c4db  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001c4e0  mov     r14, rax
0x18001c4e3  and     r14, [r15+30h]
0x18001c4e7  add     r14, r14
0x18001c4ea  mov     r13, [rsi+r14*8+8]
0x18001c4ef  cmp     r11, r13
0x18001c4f2  lea     rcx, [rbp+var_20]
0x18001c4f6  setz    bl
0x18001c4f9  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Range_eraser::_Bump_erased(void)
0x18001c4fe  mov     r11, [rbp+var_10]
0x18001c502  test    bl, bl
0x18001c504  jnz     short loc_18001C535
0x18001c506  cmp     r11, rdi
0x18001c509  jnz     short loc_18001C4EF
0x18001c50b  mov     [rsi+r14*8], r11
0x18001c50f  mov     rax, [rbp+var_18]
0x18001c513  mov     [rax], r11
0x18001c516  mov     [r11+8], rax
0x18001c51a  mov     rbx, [rsp+40h+arg_18]
0x18001c522  mov     rax, rdi
0x18001c525  add     rsp, 40h
0x18001c529  pop     r15
0x18001c52b  pop     r14
0x18001c52d  pop     r13
0x18001c52f  pop     r12
0x18001c531  pop     rdi
0x18001c532  pop     rsi
0x18001c533  pop     rbp
0x18001c534  retn
0x18001c535  mov     [rsi+r14*8], r12
0x18001c539  mov     [rsi+r14*8+8], r12
0x18001c53e  cmp     r11, rdi
0x18001c541  jnz     short loc_18001C4D1
0x18001c543  jmp     short loc_18001C50F
```
