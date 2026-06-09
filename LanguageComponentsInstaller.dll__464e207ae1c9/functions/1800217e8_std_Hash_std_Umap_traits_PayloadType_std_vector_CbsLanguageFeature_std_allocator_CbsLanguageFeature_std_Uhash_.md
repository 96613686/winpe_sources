# std::_Hash<std::_Umap_traits<PayloadType,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>,std::_Uhash_compare<PayloadType,std::hash<PayloadType>,std::equal_to<PayloadType>>,std::allocator<std::pair<PayloadType const,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<PayloadType const,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>>,void *> *,std::_List_node<std::pair<PayloadType const,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>>,void *> * const)

- ea: `0x1800217e8`
- end: `0x180021980`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@W4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@V?$_Uhash_compare@W4PayloadType@@U?$hash@W4PayloadType@@@std@@U?$equal_to@W4PayloadType@@@3@@3@V?$allocator@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@3@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `408`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800135d4`

## callees

- `0x180003a34`
- `0x180021590`
- `0x1800217e8`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<enum PayloadType,std::vector<CbsLanguageFeature>,std::_Uhash_compare<enum PayloadType,std::hash<enum PayloadType>,std::equal_to<enum PayloadType>>,std::allocator<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rsi
  __int64 v8; // r12
  __int64 v9; // r15
  _QWORD *v10; // r14
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r15
  __int64 v14; // rcx
  void *v15; // rbx
  _QWORD *v16; // r8
  _QWORD *v18; // rax
  __int64 v19; // rcx
  unsigned __int64 i; // rdx
  __int64 v21; // rax
  __int64 v22; // rcx
  void *v23; // rbx
  _QWORD *v24; // [rsp+20h] [rbp-68h]
  void *v25; // [rsp+28h] [rbp-60h]
  void *v26; // [rsp+28h] [rbp-60h]
  _QWORD *v27; // [rsp+30h] [rbp-58h]

  if ( a2 != a3 )
  {
    v6 = (_QWORD *)a1[1];
    v7 = a2;
    v8 = a1[3];
    v9 = 0xCBF29CE484222325uLL;
    v10 = (_QWORD *)a2[1];
    v11 = 0;
    v24 = v6;
    do
    {
      v12 = *((unsigned __int8 *)a2 + v11 + 16);
      ++v11;
      v9 = 0x100000001B3LL * (v12 ^ v9);
    }
    while ( v11 < 4 );
    v13 = 2 * (a1[6] & v9);
    v27 = *(_QWORD **)(v8 + 8 * v13);
    v25 = *(void **)(v8 + 8 * v13 + 8);
    while ( 1 )
    {
      v14 = (__int64)(v7 + 3);
      v15 = v7;
      v7 = (_QWORD *)*v7;
      std::vector<CbsLanguageFeature>::_Tidy(v14);
      operator delete(v15);
      v16 = a1;
      --a1[2];
      if ( v15 == v25 )
        break;
      if ( v7 == a3 )
      {
        if ( v27 == a2 )
LABEL_8:
          *(_QWORD *)(v8 + 8 * v13) = v7;
        goto LABEL_9;
      }
    }
    if ( v27 == a2 )
    {
      *(_QWORD *)(v8 + 8 * v13) = v24;
      v18 = v24;
    }
    else
    {
      v18 = v10;
    }
    *(_QWORD *)(v8 + 8 * v13 + 8) = v18;
    while ( v7 != a3 )
    {
      v19 = 0xCBF29CE484222325uLL;
      for ( i = 0; i < 4; ++i )
      {
        v21 = *((unsigned __int8 *)v7 + i + 16);
        v19 = 0x100000001B3LL * (v21 ^ v19);
      }
      v13 = 2 * (v19 & v16[6]);
      v26 = *(void **)(v8 + 16 * (v19 & v16[6]) + 8);
      while ( 1 )
      {
        v22 = (__int64)(v7 + 3);
        v23 = v7;
        v7 = (_QWORD *)*v7;
        std::vector<CbsLanguageFeature>::_Tidy(v22);
        operator delete(v23);
        v16 = a1;
        --a1[2];
        if ( v23 == v26 )
          break;
        if ( v7 == a3 )
          goto LABEL_8;
      }
      *(_QWORD *)(v8 + 8 * v13) = v24;
      *(_QWORD *)(v8 + 8 * v13 + 8) = v24;
    }
LABEL_9:
    *v10 = v7;
    v7[1] = v10;
  }
  return a3;
}

```

## disassembly

```asm
0x1800217e8  push    rbx
0x1800217ea  push    rbp
0x1800217eb  push    rsi
0x1800217ec  push    rdi
0x1800217ed  push    r12
0x1800217ef  push    r13
0x1800217f1  push    r14
0x1800217f3  push    r15
0x1800217f5  sub     rsp, 48h
0x1800217f9  mov     r13, rdx
0x1800217fc  mov     [rsp+88h+var_50], rcx
0x180021801  mov     rbp, r8
0x180021804  mov     rdx, rcx
0x180021807  cmp     r13, r8
0x18002180a  jz      loc_1800218B3
0x180021810  mov     rax, [rcx+8]
0x180021814  mov     rsi, r13
0x180021817  mov     r12, [rcx+18h]
0x18002181b  mov     r15, 0CBF29CE484222325h
0x180021825  mov     r14, [r13+8]
0x180021829  xor     ecx, ecx
0x18002182b  mov     [rsp+88h+var_68], rax
0x180021830  mov     r8, 100000001B3h
0x18002183a  movzx   eax, byte ptr [rcx+r13+10h]
0x180021840  inc     rcx
0x180021843  xor     r15, rax
0x180021846  imul    r15, r8
0x18002184a  cmp     rcx, 4
0x18002184e  jb      short loc_18002183A
0x180021850  and     r15, [rdx+30h]
0x180021854  add     r15, r15
0x180021857  mov     rax, [r12+r15*8]
0x18002185b  mov     [rsp+88h+var_58], rax
0x180021860  mov     rax, [r12+r15*8+8]
0x180021865  mov     [rsp+88h+var_60], rax
0x18002186a  mov     rcx, rsi
0x18002186d  mov     rdi, rsi
0x180021870  add     rcx, 18h
0x180021874  mov     rbx, rsi
0x180021877  mov     rsi, [rsi]
0x18002187a  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x18002187f  mov     edx, 30h ; '0'
0x180021884  mov     rcx, rbx; Block
0x180021887  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002188c  mov     r8, [rsp+88h+var_50]
0x180021891  dec     qword ptr [r8+10h]
0x180021895  cmp     rbx, [rsp+88h+var_60]
0x18002189a  jz      short loc_1800218C7
0x18002189c  cmp     rsi, rbp
0x18002189f  jnz     short loc_18002186A
0x1800218a1  cmp     [rsp+88h+var_58], r13
0x1800218a6  jnz     short loc_1800218AC
0x1800218a8  mov     [r12+r15*8], rsi
0x1800218ac  mov     [r14], rsi
0x1800218af  mov     [rsi+8], r14
0x1800218b3  mov     rax, rbp
0x1800218b6  add     rsp, 48h
0x1800218ba  pop     r15
0x1800218bc  pop     r14
0x1800218be  pop     r13
0x1800218c0  pop     r12
0x1800218c2  pop     rdi
0x1800218c3  pop     rsi
0x1800218c4  pop     rbp
0x1800218c5  pop     rbx
0x1800218c6  retn
0x1800218c7  cmp     [rsp+88h+var_58], r13
0x1800218cc  jnz     short loc_1800218DC
0x1800218ce  mov     r13, [rsp+88h+var_68]
0x1800218d3  mov     [r12+r15*8], r13
0x1800218d7  mov     rax, r13
0x1800218da  jmp     short loc_1800218DF
0x1800218dc  mov     rax, r14
0x1800218df  mov     [r12+r15*8+8], rax
0x1800218e4  jmp     loc_180021972
0x1800218e9  mov     rcx, 0CBF29CE484222325h
0x1800218f3  xor     edx, edx
0x1800218f5  mov     r13, 100000001B3h
0x1800218ff  movzx   eax, byte ptr [rsi+rdx+10h]
0x180021904  inc     rdx
0x180021907  xor     rcx, rax
0x18002190a  imul    rcx, r13
0x18002190e  cmp     rdx, 4
0x180021912  jb      short loc_1800218FF
0x180021914  mov     r15, [r8+30h]
0x180021918  mov     r13, [rsp+88h+var_68]
0x18002191d  and     r15, rcx
0x180021920  add     r15, r15
0x180021923  mov     rax, [r12+r15*8+8]
0x180021928  mov     [rsp+88h+var_60], rax
0x18002192d  mov     rcx, rsi
0x180021930  mov     rdi, rsi
0x180021933  add     rcx, 18h
0x180021937  mov     rbx, rsi
0x18002193a  mov     rsi, [rsi]
0x18002193d  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x180021942  mov     edx, 30h ; '0'
0x180021947  mov     rcx, rbx; Block
0x18002194a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002194f  mov     r8, [rsp+88h+var_50]
0x180021954  dec     qword ptr [r8+10h]
0x180021958  cmp     rbx, [rsp+88h+var_60]
0x18002195d  jz      short loc_180021969
0x18002195f  cmp     rsi, rbp
0x180021962  jnz     short loc_18002192D
0x180021964  jmp     loc_1800218A8
0x180021969  mov     [r12+r15*8], r13
0x18002196d  mov     [r12+r15*8+8], r13
0x180021972  cmp     rsi, rbp
0x180021975  jnz     loc_1800218E9
0x18002197b  jmp     loc_1800218AC
```
