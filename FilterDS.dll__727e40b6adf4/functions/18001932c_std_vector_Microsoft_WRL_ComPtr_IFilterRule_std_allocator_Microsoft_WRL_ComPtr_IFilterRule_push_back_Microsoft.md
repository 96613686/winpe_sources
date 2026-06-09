# std::vector<Microsoft::WRL::ComPtr<IFilterRule>,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>::push_back(Microsoft::WRL::ComPtr<IFilterRule> const &)

- ea: `0x18001932c`
- end: `0x18001948e`
- name: `?push_back@?$vector@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@QEAAXAEBV?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@Z`
- size: `354`
- prototype: `__int64 *__fastcall(void **, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017840`

## callees

- `0x18000cd9c`
- `0x1800191c0`
- `0x18001932c`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::push_back(void **a1, __int64 *a2)
{
  unsigned __int64 v4; // rcx
  bool v5; // al
  _BYTE *v6; // r8
  _BYTE *v7; // rsi
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 *result; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // rdx
  __int64 v18; // rcx

  v4 = (unsigned __int64)a1[1];
  v5 = (unsigned __int64)a2 < v4 && *a1 <= a2;
  v6 = a1[2];
  if ( v5 )
  {
    v7 = *a1;
    if ( (_BYTE *)v4 == v6 && !((__int64)&v6[-v4] >> 3) )
    {
      v8 = (__int64)(v4 - (_QWORD)v7) >> 3;
      if ( v8 == 0x1FFFFFFFFFFFFFFFLL )
        std::vector<std::unique_ptr<FilterAgent>>::_Xlen();
      v9 = v8 + 1;
      v10 = (v6 - v7) >> 3;
      v11 = 0;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) >= v10 )
        v11 = v10 + (v10 >> 1);
      if ( v11 < v9 )
        v11 = v9;
      std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::_Reallocate(a1, v11);
    }
    v12 = *((_QWORD *)*a1 + (((char *)a2 - v7) >> 3));
    result = (__int64 *)a1[1];
    *result = v12;
    if ( v12 )
      result = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  }
  else
  {
    if ( (_BYTE *)v4 == v6 && !((__int64)&v6[-v4] >> 3) )
    {
      v14 = (__int64)(v4 - (_QWORD)*a1) >> 3;
      if ( v14 == 0x1FFFFFFFFFFFFFFFLL )
        std::vector<std::unique_ptr<FilterAgent>>::_Xlen();
      v15 = v14 + 1;
      v16 = (v6 - (_BYTE *)*a1) >> 3;
      v17 = 0;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v16 >> 1) >= v16 )
        v17 = v16 + (v16 >> 1);
      if ( v17 < v15 )
        v17 = v15;
      std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::_Reallocate(a1, v17);
    }
    v18 = *a2;
    result = (__int64 *)a1[1];
    *result = *a2;
    if ( v18 )
      result = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
  }
  a1[1] = (char *)a1[1] + 8;
  return result;
}

```

## disassembly

```asm
0x18001932c  mov     [rsp+arg_0], rbx
0x180019331  mov     [rsp+arg_8], rsi
0x180019336  push    rdi
0x180019337  sub     rsp, 20h
0x18001933b  mov     rdi, rdx
0x18001933e  mov     rbx, rcx
0x180019341  mov     rcx, [rcx+8]
0x180019345  cmp     rdx, rcx
0x180019348  jnb     short loc_180019353
0x18001934a  cmp     [rbx], rdx
0x18001934d  ja      short loc_180019353
0x18001934f  mov     al, 1
0x180019351  jmp     short loc_180019355
0x180019353  xor     al, al
0x180019355  mov     r8, [rbx+10h]
0x180019359  test    al, al
0x18001935b  jz      loc_1800193F1
0x180019361  mov     rsi, [rbx]
0x180019364  cmp     rcx, r8
0x180019367  jnz     short loc_1800193C8
0x180019369  mov     rax, r8
0x18001936c  sub     rax, rcx
0x18001936f  sar     rax, 3
0x180019373  cmp     rax, 1
0x180019377  jnb     short loc_1800193C8
0x180019379  sub     rcx, rsi
0x18001937c  sar     rcx, 3
0x180019380  mov     r9, 1FFFFFFFFFFFFFFFh
0x18001938a  mov     rax, r9
0x18001938d  sub     rax, rcx
0x180019390  cmp     rax, 1
0x180019394  jb      loc_180019488
0x18001939a  inc     rcx
0x18001939d  sub     r8, rsi
0x1800193a0  sar     r8, 3
0x1800193a4  mov     rax, r8
0x1800193a7  shr     rax, 1
0x1800193aa  sub     r9, rax
0x1800193ad  add     rax, r8
0x1800193b0  xor     edx, edx
0x1800193b2  cmp     r9, r8
0x1800193b5  cmovnb  rdx, rax
0x1800193b9  cmp     rdx, rcx
0x1800193bc  cmovb   rdx, rcx
0x1800193c0  mov     rcx, rbx
0x1800193c3  call    ?_Reallocate@?$vector@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@IEAAX_K@Z; std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::_Reallocate(unsigned __int64)
0x1800193c8  sub     rdi, rsi
0x1800193cb  sar     rdi, 3
0x1800193cf  mov     rax, [rbx]
0x1800193d2  mov     rcx, [rax+rdi*8]
0x1800193d6  mov     rax, [rbx+8]
0x1800193da  mov     [rax], rcx
0x1800193dd  test    rcx, rcx
0x1800193e0  jz      short loc_1800193EF
0x1800193e2  mov     rax, [rcx]
0x1800193e5  mov     rax, [rax+8]
0x1800193e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193ee  nop
0x1800193ef  jmp     short loc_18001946D
0x1800193f1  cmp     rcx, r8
0x1800193f4  jnz     short loc_180019451
0x1800193f6  mov     rax, r8
0x1800193f9  sub     rax, rcx
0x1800193fc  sar     rax, 3
0x180019400  cmp     rax, 1
0x180019404  jnb     short loc_180019451
0x180019406  sub     rcx, [rbx]
0x180019409  sar     rcx, 3
0x18001940d  mov     r9, 1FFFFFFFFFFFFFFFh
0x180019417  mov     rax, r9
0x18001941a  sub     rax, rcx
0x18001941d  cmp     rax, 1
0x180019421  jb      short loc_180019482
0x180019423  inc     rcx
0x180019426  sub     r8, [rbx]
0x180019429  sar     r8, 3
0x18001942d  mov     rax, r8
0x180019430  shr     rax, 1
0x180019433  sub     r9, rax
0x180019436  add     rax, r8
0x180019439  xor     edx, edx
0x18001943b  cmp     r9, r8
0x18001943e  cmovnb  rdx, rax
0x180019442  cmp     rdx, rcx
0x180019445  cmovb   rdx, rcx
0x180019449  mov     rcx, rbx
0x18001944c  call    ?_Reallocate@?$vector@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@IEAAX_K@Z; std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::_Reallocate(unsigned __int64)
0x180019451  mov     rcx, [rdi]
0x180019454  mov     rax, [rbx+8]
0x180019458  mov     [rax], rcx
0x18001945b  test    rcx, rcx
0x18001945e  jz      short loc_18001946D
0x180019460  mov     rax, [rcx]
0x180019463  mov     rax, [rax+8]
0x180019467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001946c  nop
0x18001946d  add     qword ptr [rbx+8], 8
0x180019472  mov     rbx, [rsp+28h+arg_0]
0x180019477  mov     rsi, [rsp+28h+arg_8]
0x18001947c  add     rsp, 20h
0x180019480  pop     rdi
0x180019481  retn
0x180019482  call    ?_Xlen@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::unique_ptr<FilterAgent>>::_Xlen(void)
0x180019488  call    ?_Xlen@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::unique_ptr<FilterAgent>>::_Xlen(void)
```
