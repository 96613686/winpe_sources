# std::vector<std::shared_ptr<PluginPendingMessage>,std::allocator<std::shared_ptr<PluginPendingMessage>>>::_Emplace_reallocate<std::shared_ptr<PluginPendingMessage> const &>(std::shared_ptr<PluginPendingMessage> * const,std::shared_ptr<PluginPendingMessage> const &)

- ea: `0x18001e3f0`
- end: `0x18001e6fb`
- name: `??$_Emplace_reallocate@AEBV?$shared_ptr@UPluginPendingMessage@@@std@@@?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UPluginPendingMessage@@@1@QEAV21@AEBV21@@Z`
- size: `779`
- prototype: `char *__fastcall(char **, char *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800269a4`

## callees

- `0x180001900`
- `0x18000193c`
- `0x1800056c4`
- `0x1800056ec`
- `0x18001e3f0`
- `0x18001fd4c`
- `0x1800203e4`
- `0x180035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char *__fastcall std::vector<std::shared_ptr<PluginPendingMessage>>::_Emplace_reallocate<std::shared_ptr<PluginPendingMessage> const &>(
        char **a1,
        char *a2,
        _QWORD *a3)
{
  __int64 v4; // r9
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rdx
  __int64 v8; // r13
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // r15
  _QWORD *v11; // rdi
  void *v12; // rax
  __int64 v13; // r12
  _QWORD *v14; // rdx
  __int64 v15; // rax
  char *v16; // r8
  char *v17; // rcx
  _QWORD *v18; // rdx
  __int64 v19; // r12
  char *v20; // rdx
  _QWORD *v21; // rcx
  char *v22; // r14
  char *v23; // rax
  volatile signed __int32 *v24; // rsi
  char *v25; // rax
  char *v26; // rcx
  _QWORD *v28; // [rsp+20h] [rbp-40h] BYREF
  _QWORD *v29; // [rsp+28h] [rbp-38h]
  char **v30; // [rsp+30h] [rbp-30h]
  _QWORD v31[3]; // [rsp+38h] [rbp-28h] BYREF
  char *v32; // [rsp+50h] [rbp-10h]
  _QWORD *v33; // [rsp+58h] [rbp-8h]
  char *v34; // [rsp+A0h] [rbp+40h]
  char *v35; // [rsp+A0h] [rbp+40h]

  v34 = *a1;
  v4 = (a1[1] - *a1) >> 4;
  if ( v4 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<ATL::CComVariant>::_Xlength();
  v6 = (a1[2] - *a1) >> 4;
  v7 = v6 >> 1;
  if ( v6 > 0xFFFFFFFFFFFFFFFLL - (v6 >> 1) )
    goto LABEL_43;
  v8 = v4 + 1;
  v9 = v4 + 1;
  if ( v6 + v7 >= v4 + 1 )
    v9 = v6 + v7;
  if ( v9 > 0xFFFFFFFFFFFFFFFLL )
    goto LABEL_43;
  v10 = 16 * v9;
  if ( !(16 * v9) )
  {
    v11 = 0;
    goto LABEL_13;
  }
  if ( v10 < 0x1000 )
  {
    v11 = operator new(16 * v9);
    goto LABEL_13;
  }
  if ( v10 + 39 < v10 )
LABEL_43:
    __scrt_throw_std_bad_array_new_length();
  v12 = operator new(v10 + 39);
  if ( !v12 )
    goto LABEL_38;
  v11 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v11 - 1) = v12;
LABEL_13:
  v13 = (a2 - v34) >> 4;
  v31[2] = v9;
  v14 = &v11[2 * v13];
  v31[0] = a1;
  *v14 = 0;
  v33 = v14 + 2;
  v14[1] = 0;
  v15 = a3[1];
  if ( v15 )
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
  *v14 = *a3;
  v14[1] = a3[1];
  v16 = a1[1];
  v17 = *a1;
  v32 = (char *)&v11[2 * ((a2 - v34) >> 4)];
  v18 = v11;
  v30 = a1;
  v29 = v11;
  if ( a2 == v16 )
  {
    if ( v17 != v16 )
    {
      do
      {
        *v18 = 0;
        v18[1] = 0;
        *v18 = *(_QWORD *)v17;
        v18[1] = *((_QWORD *)v17 + 1);
        v18 += 2;
        *(_QWORD *)v17 = 0;
        *((_QWORD *)v17 + 1) = 0;
        v17 += 16;
      }
      while ( v17 != v16 );
      v29 = v18;
    }
    v28 = v18;
    std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<PluginPendingMessage>>>::~_Uninitialized_backout_al<std::allocator<std::shared_ptr<PluginPendingMessage>>>(&v28);
    v19 = 2 * v13;
  }
  else
  {
    if ( v17 != a2 )
    {
      do
      {
        *v18 = 0;
        v18[1] = 0;
        *v18 = *(_QWORD *)v17;
        v18[1] = *((_QWORD *)v17 + 1);
        v18 += 2;
        *(_QWORD *)v17 = 0;
        *((_QWORD *)v17 + 1) = 0;
        v17 += 16;
      }
      while ( v17 != a2 );
      v29 = v18;
    }
    v28 = v18;
    std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<PluginPendingMessage>>>::~_Uninitialized_backout_al<std::allocator<std::shared_ptr<PluginPendingMessage>>>(&v28);
    v20 = a1[1];
    v19 = 2 * v13;
    v32 = (char *)v11;
    v30 = a1;
    v21 = &v11[v19 + 2];
    v29 = v21;
    if ( a2 != v20 )
    {
      do
      {
        *v21 = 0;
        v21[1] = 0;
        *v21 = *(_QWORD *)a2;
        v21[1] = *((_QWORD *)a2 + 1);
        v21 += 2;
        *(_QWORD *)a2 = 0;
        *((_QWORD *)a2 + 1) = 0;
        a2 += 16;
      }
      while ( a2 != v20 );
      v29 = v21;
    }
    v28 = v21;
    std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<PluginPendingMessage>>>::~_Uninitialized_backout_al<std::allocator<std::shared_ptr<PluginPendingMessage>>>(&v28);
  }
  v31[1] = 0;
  v22 = *a1;
  if ( *a1 )
  {
    v35 = a1[1];
    if ( v22 != v35 )
    {
      v23 = a1[1];
      do
      {
        v24 = (volatile signed __int32 *)*((_QWORD *)v22 + 1);
        if ( v24 )
        {
          if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
            if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
          }
          v23 = v35;
        }
        v22 += 16;
      }
      while ( v22 != v23 );
    }
    v25 = *a1;
    if ( ((a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
    {
      v26 = *a1;
    }
    else
    {
      v26 = (char *)*((_QWORD *)v25 - 1);
      if ( (unsigned __int64)(v25 - v26 - 8) > 0x1F )
LABEL_38:
        __fastfail(5u);
    }
    operator delete(v26);
  }
  *a1 = (char *)v11;
  a1[1] = (char *)&v11[2 * v8];
  a1[2] = (char *)&v11[v10 / 8];
  std::vector<std::shared_ptr<PluginPendingMessage>>::_Reallocation_guard::~_Reallocation_guard(v31);
  return (char *)&v11[v19];
}

```

## disassembly

```asm
0x18001e3f0  mov     [rsp-38h+arg_8], rbx
0x18001e3f5  mov     [rsp-38h+arg_10], r8
0x18001e3fa  push    rbp
0x18001e3fb  push    rsi
0x18001e3fc  push    rdi
0x18001e3fd  push    r12
0x18001e3ff  push    r13
0x18001e401  push    r14
0x18001e403  push    r15
0x18001e405  mov     rbp, rsp
0x18001e408  sub     rsp, 60h
0x18001e40c  mov     rax, [rcx]
0x18001e40f  mov     r8, 0FFFFFFFFFFFFFFFh
0x18001e419  mov     r9, [rcx+8]
0x18001e41d  mov     rsi, rdx
0x18001e420  sub     r9, rax
0x18001e423  mov     [rbp+arg_0], rax
0x18001e427  sar     r9, 4
0x18001e42b  mov     rbx, rcx
0x18001e42e  cmp     r9, r8
0x18001e431  jz      loc_18001E6EF
0x18001e437  mov     rcx, [rcx+10h]
0x18001e43b  sub     rcx, rax
0x18001e43e  mov     rax, r8
0x18001e441  sar     rcx, 4
0x18001e445  mov     rdx, rcx
0x18001e448  shr     rdx, 1
0x18001e44b  sub     rax, rdx
0x18001e44e  cmp     rcx, rax
0x18001e451  ja      loc_18001E6F5
0x18001e457  lea     r13, [r9+1]
0x18001e45b  lea     rax, [rcx+rdx]
0x18001e45f  mov     r14, r13
0x18001e462  cmp     rax, r13
0x18001e465  cmovnb  r14, rax
0x18001e469  cmp     r14, r8
0x18001e46c  ja      loc_18001E6F5
0x18001e472  mov     r15, r14
0x18001e475  shl     r15, 4
0x18001e479  test    r15, r15
0x18001e47c  jnz     short loc_18001E482
0x18001e47e  xor     edi, edi
0x18001e480  jmp     short loc_18001E4BF
0x18001e482  cmp     r15, 1000h
0x18001e489  jb      short loc_18001E4B4
0x18001e48b  lea     rcx, [r15+27h]; Size
0x18001e48f  cmp     rcx, r15
0x18001e492  jbe     loc_18001E6F5
0x18001e498  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e49d  test    rax, rax
0x18001e4a0  jz      loc_18001E6A5
0x18001e4a6  lea     rdi, [rax+27h]
0x18001e4aa  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18001e4ae  mov     [rdi-8], rax
0x18001e4b2  jmp     short loc_18001E4BF
0x18001e4b4  mov     rcx, r15; Size
0x18001e4b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e4bc  mov     rdi, rax
0x18001e4bf  mov     rcx, [rbp+arg_10]
0x18001e4c3  mov     r12, rsi
0x18001e4c6  sub     r12, [rbp+arg_0]
0x18001e4ca  sar     r12, 4
0x18001e4ce  mov     rdx, r12
0x18001e4d1  mov     [rbp+var_18], r14
0x18001e4d5  xor     r14d, r14d
0x18001e4d8  shl     rdx, 4
0x18001e4dc  add     rdx, rdi
0x18001e4df  mov     [rbp+var_28], rbx
0x18001e4e3  lea     rax, [rdx+10h]
0x18001e4e7  mov     [rdx], r14
0x18001e4ea  mov     [rbp+var_8], rax
0x18001e4ee  mov     [rdx+8], r14
0x18001e4f2  mov     rax, [rcx+8]
0x18001e4f6  test    rax, rax
0x18001e4f9  jz      short loc_18001E4FF
0x18001e4fb  lock inc dword ptr [rax+8]
0x18001e4ff  mov     rax, [rcx]
0x18001e502  mov     [rdx], rax
0x18001e505  mov     rax, [rcx+8]
0x18001e509  mov     [rdx+8], rax
0x18001e50d  mov     r8, [rbx+8]
0x18001e511  mov     rcx, [rbx]
0x18001e514  mov     [rbp+var_10], rdx
0x18001e518  mov     rdx, rdi
0x18001e51b  mov     [rbp+var_30], rbx
0x18001e51f  mov     [rbp+var_38], rdx
0x18001e523  cmp     rsi, r8
0x18001e526  jnz     short loc_18001E570
0x18001e528  cmp     rcx, r8
0x18001e52b  jz      short loc_18001E55A
0x18001e52d  mov     [rdx], r14
0x18001e530  mov     [rdx+8], r14
0x18001e534  mov     rax, [rcx]
0x18001e537  mov     [rdx], rax
0x18001e53a  mov     rax, [rcx+8]
0x18001e53e  mov     [rdx+8], rax
0x18001e542  add     rdx, 10h
0x18001e546  mov     [rcx], r14
0x18001e549  mov     [rcx+8], r14
0x18001e54d  add     rcx, 10h
0x18001e551  cmp     rcx, r8
0x18001e554  jnz     short loc_18001E52D
0x18001e556  mov     [rbp+var_38], rdx
0x18001e55a  lea     rcx, [rbp+var_40]
0x18001e55e  mov     [rbp+var_40], rdx
0x18001e562  call    ??1?$_Uninitialized_backout_al@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@std@@@std@@QEAA@XZ; std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<PluginPendingMessage>>>::~_Uninitialized_backout_al<std::allocator<std::shared_ptr<PluginPendingMessage>>>(void)
0x18001e567  shl     r12, 4
0x18001e56b  jmp     loc_18001E60A
0x18001e570  cmp     rcx, rsi
0x18001e573  jz      short loc_18001E5A2
0x18001e575  mov     [rdx], r14
0x18001e578  mov     [rdx+8], r14
0x18001e57c  mov     rax, [rcx]
0x18001e57f  mov     [rdx], rax
0x18001e582  mov     rax, [rcx+8]
0x18001e586  mov     [rdx+8], rax
0x18001e58a  add     rdx, 10h
0x18001e58e  mov     [rcx], r14
0x18001e591  mov     [rcx+8], r14
0x18001e595  add     rcx, 10h
0x18001e599  cmp     rcx, rsi
0x18001e59c  jnz     short loc_18001E575
0x18001e59e  mov     [rbp+var_38], rdx
0x18001e5a2  lea     rcx, [rbp+var_40]
0x18001e5a6  mov     [rbp+var_40], rdx
0x18001e5aa  call    ??1?$_Uninitialized_backout_al@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@std@@@std@@QEAA@XZ; std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<PluginPendingMessage>>>::~_Uninitialized_backout_al<std::allocator<std::shared_ptr<PluginPendingMessage>>>(void)
0x18001e5af  mov     rdx, [rbx+8]
0x18001e5b3  shl     r12, 4
0x18001e5b7  mov     [rbp+var_10], rdi
0x18001e5bb  mov     [rbp+var_30], rbx
0x18001e5bf  lea     rcx, [r12+10h]
0x18001e5c4  add     rcx, rdi
0x18001e5c7  mov     [rbp+var_38], rcx
0x18001e5cb  cmp     rsi, rdx
0x18001e5ce  jz      short loc_18001E5FD
0x18001e5d0  mov     [rcx], r14
0x18001e5d3  mov     [rcx+8], r14
0x18001e5d7  mov     rax, [rsi]
0x18001e5da  mov     [rcx], rax
0x18001e5dd  mov     rax, [rsi+8]
0x18001e5e1  mov     [rcx+8], rax
0x18001e5e5  add     rcx, 10h
0x18001e5e9  mov     [rsi], r14
0x18001e5ec  mov     [rsi+8], r14
0x18001e5f0  add     rsi, 10h
0x18001e5f4  cmp     rsi, rdx
0x18001e5f7  jnz     short loc_18001E5D0
0x18001e5f9  mov     [rbp+var_38], rcx
0x18001e5fd  mov     [rbp+var_40], rcx
0x18001e601  lea     rcx, [rbp+var_40]
0x18001e605  call    ??1?$_Uninitialized_backout_al@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@std@@@std@@QEAA@XZ; std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<PluginPendingMessage>>>::~_Uninitialized_backout_al<std::allocator<std::shared_ptr<PluginPendingMessage>>>(void)
0x18001e60a  mov     [rbp+var_20], r14
0x18001e60e  mov     r14, [rbx]
0x18001e611  test    r14, r14
0x18001e614  jz      loc_18001E6B4
0x18001e61a  mov     rsi, [rbx+8]
0x18001e61e  mov     [rbp+arg_0], rsi
0x18001e622  cmp     r14, rsi
0x18001e625  jz      short loc_18001E677
0x18001e627  mov     rax, rsi
0x18001e62a  mov     rsi, [r14+8]
0x18001e62e  test    rsi, rsi
0x18001e631  jz      short loc_18001E66E
0x18001e633  or      eax, 0FFFFFFFFh
0x18001e636  lock xadd [rsi+8], eax
0x18001e63b  cmp     eax, 1
0x18001e63e  jnz     short loc_18001E66A
0x18001e640  mov     rax, [rsi]
0x18001e643  mov     rcx, rsi
0x18001e646  mov     rax, [rax]
0x18001e649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e64e  or      eax, 0FFFFFFFFh
0x18001e651  lock xadd [rsi+0Ch], eax
0x18001e656  cmp     eax, 1
0x18001e659  jnz     short loc_18001E66A
0x18001e65b  mov     rax, [rsi]
0x18001e65e  mov     rcx, rsi
0x18001e661  mov     rax, [rax+8]
0x18001e665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e66a  mov     rax, [rbp+arg_0]
0x18001e66e  add     r14, 10h
0x18001e672  cmp     r14, rax
0x18001e675  jnz     short loc_18001E62A
0x18001e677  mov     rax, [rbx]
0x18001e67a  mov     rdx, [rbx+10h]
0x18001e67e  sub     rdx, rax
0x18001e681  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001e685  cmp     rdx, 1000h
0x18001e68c  jb      short loc_18001E6AC
0x18001e68e  mov     rcx, [rax-8]
0x18001e692  sub     rax, rcx
0x18001e695  sub     rax, 8
0x18001e699  cmp     rax, 1Fh
0x18001e69d  ja      short loc_18001E6A5
0x18001e69f  add     rdx, 27h ; '''
0x18001e6a3  jmp     short loc_18001E6AF
0x18001e6a5  mov     ecx, 5
0x18001e6aa  int     29h; Win8: RtlFailFast(ecx)
0x18001e6ac  mov     rcx, rax; Block
0x18001e6af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e6b4  mov     [rbx], rdi
0x18001e6b7  lea     rax, [r15+rdi]
0x18001e6bb  shl     r13, 4
0x18001e6bf  lea     rcx, [rbp+var_28]
0x18001e6c3  add     r13, rdi
0x18001e6c6  mov     [rbx+8], r13
0x18001e6ca  mov     [rbx+10h], rax
0x18001e6ce  call    ??1_Reallocation_guard@?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PluginPendingMessage>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001e6d3  mov     rbx, [rsp+60h+arg_8]
0x18001e6db  lea     rax, [rdi+r12]
0x18001e6df  add     rsp, 60h
0x18001e6e3  pop     r15
0x18001e6e5  pop     r14
0x18001e6e7  pop     r13
0x18001e6e9  pop     r12
0x18001e6eb  pop     rdi
0x18001e6ec  pop     rsi
0x18001e6ed  pop     rbp
0x18001e6ee  retn
0x18001e6ef  call    ?_Xlength@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@CAXXZ; std::vector<ATL::CComVariant>::_Xlength(void)
0x18001e6f5  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
