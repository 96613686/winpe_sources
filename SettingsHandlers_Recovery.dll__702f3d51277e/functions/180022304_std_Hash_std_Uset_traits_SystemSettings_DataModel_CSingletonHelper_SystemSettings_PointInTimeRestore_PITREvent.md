# std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::_Unchecked_erase(std::_List_node<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,void *> *,std::_List_node<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,void *> * const)

- ea: `0x180022304`
- end: `0x18002246e`
- name: `?_Unchecked_erase@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAAPEAU?$_List_node@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001282c`

## callees

- `0x18000282c`
- `0x180022304`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::_Unchecked_erase(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  __int64 v8; // r12
  __int64 v9; // r15
  _QWORD *v10; // r14
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r15
  void *v14; // rcx
  _QWORD *v15; // rbx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  unsigned __int64 i; // rdx
  __int64 v20; // rax
  void *v21; // rcx
  _QWORD *v22; // rbx
  _QWORD *v23; // [rsp+68h] [rbp+10h]
  _QWORD *v24; // [rsp+70h] [rbp+18h]
  _QWORD *v25; // [rsp+70h] [rbp+18h]
  _QWORD *v26; // [rsp+78h] [rbp+20h]

  if ( a2 != a3 )
  {
    v6 = (_QWORD *)a1[1];
    v7 = a2;
    v8 = a1[3];
    v9 = 0xCBF29CE484222325uLL;
    v10 = (_QWORD *)a2[1];
    v11 = 0;
    v23 = v6;
    do
    {
      v12 = *((unsigned __int8 *)a2 + v11 + 16);
      ++v11;
      v9 = 0x100000001B3LL * (v12 ^ v9);
    }
    while ( v11 < 8 );
    v13 = 2 * (a1[6] & v9);
    v24 = *(_QWORD **)(v8 + 8 * v13);
    v26 = *(_QWORD **)(v8 + 8 * v13 + 8);
    while ( 1 )
    {
      v14 = v7;
      v15 = v7;
      v7 = (_QWORD *)*v7;
      operator delete(v14);
      --a1[2];
      if ( v15 == v26 )
        break;
      if ( v7 == a3 )
      {
        if ( v24 == a2 )
LABEL_8:
          *(_QWORD *)(v8 + 8 * v13) = v7;
        goto LABEL_9;
      }
    }
    if ( v24 == a2 )
    {
      *(_QWORD *)(v8 + 8 * v13) = v23;
      v17 = v23;
    }
    else
    {
      v17 = v10;
    }
    *(_QWORD *)(v8 + 8 * v13 + 8) = v17;
    while ( v7 != a3 )
    {
      v18 = 0xCBF29CE484222325uLL;
      for ( i = 0; i < 8; ++i )
      {
        v20 = *((unsigned __int8 *)v7 + i + 16);
        v18 = 0x100000001B3LL * (v20 ^ v18);
      }
      v13 = 2 * (v18 & a1[6]);
      v25 = *(_QWORD **)(v8 + 16 * (v18 & a1[6]) + 8);
      while ( 1 )
      {
        v21 = v7;
        v22 = v7;
        v7 = (_QWORD *)*v7;
        operator delete(v21);
        --a1[2];
        if ( v22 == v25 )
          break;
        if ( v7 == a3 )
          goto LABEL_8;
      }
      *(_QWORD *)(v8 + 8 * v13) = v23;
      *(_QWORD *)(v8 + 8 * v13 + 8) = v23;
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
0x180022304  mov     [rsp+arg_0], rbx
0x180022309  push    rbp
0x18002230a  push    rsi
0x18002230b  push    rdi
0x18002230c  push    r12
0x18002230e  push    r13
0x180022310  push    r14
0x180022312  push    r15
0x180022314  sub     rsp, 20h
0x180022318  mov     rsi, r8
0x18002231b  mov     rbp, rdx
0x18002231e  mov     r13, rcx
0x180022321  cmp     rdx, r8
0x180022324  jz      loc_1800223B8
0x18002232a  mov     rax, [rcx+8]
0x18002232e  mov     rdi, rdx
0x180022331  mov     r12, [rcx+18h]
0x180022335  mov     r15, 0CBF29CE484222325h
0x18002233f  mov     r14, [rdx+8]
0x180022343  xor     ecx, ecx
0x180022345  mov     [rsp+58h+arg_8], rax
0x18002234a  mov     rdx, 100000001B3h
0x180022354  movzx   eax, byte ptr [rcx+rbp+10h]
0x180022359  inc     rcx
0x18002235c  xor     r15, rax
0x18002235f  imul    r15, rdx
0x180022363  cmp     rcx, 8
0x180022367  jb      short loc_180022354
0x180022369  and     r15, [r13+30h]
0x18002236d  add     r15, r15
0x180022370  mov     rax, [r12+r15*8]
0x180022374  mov     [rsp+58h+arg_10], rax
0x180022379  mov     rax, [r12+r15*8+8]
0x18002237e  mov     [rsp+58h+arg_18], rax
0x180022383  mov     rcx, rdi; Block
0x180022386  mov     rbx, rdi
0x180022389  mov     rdi, [rdi]
0x18002238c  mov     edx, 18h
0x180022391  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022396  dec     qword ptr [r13+10h]
0x18002239a  cmp     rbx, [rsp+58h+arg_18]
0x18002239f  jz      short loc_1800223D0
0x1800223a1  cmp     rdi, rsi
0x1800223a4  jnz     short loc_180022383
0x1800223a6  cmp     [rsp+58h+arg_10], rbp
0x1800223ab  jnz     short loc_1800223B1
0x1800223ad  mov     [r12+r15*8], rdi
0x1800223b1  mov     [r14], rdi
0x1800223b4  mov     [rdi+8], r14
0x1800223b8  mov     rbx, [rsp+58h+arg_0]
0x1800223bd  mov     rax, rsi
0x1800223c0  add     rsp, 20h
0x1800223c4  pop     r15
0x1800223c6  pop     r14
0x1800223c8  pop     r13
0x1800223ca  pop     r12
0x1800223cc  pop     rdi
0x1800223cd  pop     rsi
0x1800223ce  pop     rbp
0x1800223cf  retn
0x1800223d0  cmp     [rsp+58h+arg_10], rbp
0x1800223d5  jnz     short loc_1800223E5
0x1800223d7  mov     rbp, [rsp+58h+arg_8]
0x1800223dc  mov     [r12+r15*8], rbp
0x1800223e0  mov     rax, rbp
0x1800223e3  jmp     short loc_1800223E8
0x1800223e5  mov     rax, r14
0x1800223e8  mov     [r12+r15*8+8], rax
0x1800223ed  jmp     short loc_180022464
0x1800223ef  mov     rcx, 0CBF29CE484222325h
0x1800223f9  xor     edx, edx
0x1800223fb  mov     rbp, 100000001B3h
0x180022405  movzx   eax, byte ptr [rdi+rdx+10h]
0x18002240a  inc     rdx
0x18002240d  xor     rcx, rax
0x180022410  imul    rcx, rbp
0x180022414  cmp     rdx, 8
0x180022418  jb      short loc_180022405
0x18002241a  mov     r15, [r13+30h]
0x18002241e  mov     rbp, [rsp+58h+arg_8]
0x180022423  and     r15, rcx
0x180022426  add     r15, r15
0x180022429  mov     rax, [r12+r15*8+8]
0x18002242e  mov     [rsp+58h+arg_10], rax
0x180022433  mov     rcx, rdi; Block
0x180022436  mov     rbx, rdi
0x180022439  mov     rdi, [rdi]
0x18002243c  mov     edx, 18h
0x180022441  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022446  dec     qword ptr [r13+10h]
0x18002244a  cmp     rbx, [rsp+58h+arg_10]
0x18002244f  jz      short loc_18002245B
0x180022451  cmp     rdi, rsi
0x180022454  jnz     short loc_180022433
0x180022456  jmp     loc_1800223AD
0x18002245b  mov     [r12+r15*8], rbp
0x18002245f  mov     [r12+r15*8+8], rbp
0x180022464  cmp     rdi, rsi
0x180022467  jnz     short loc_1800223EF
0x180022469  jmp     loc_1800223B1
```
