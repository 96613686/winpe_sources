# std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>::push_back(std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>> &&)

- ea: `0x1800114c8`
- end: `0x180011615`
- name: `?push_back@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@2@@Z`
- size: `333`
- prototype: `__int64 __fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800104e4`

## callees

- `0x18000cd9c`
- `0x180011204`
- `0x1800114c8`

## pseudocode

```c
__int64 __fastcall std::vector<std::unique_ptr<FilterAgent>>::push_back(__int64 *a1, __int64 *a2)
{
  unsigned __int64 v4; // rcx
  bool v5; // al
  __int64 v6; // r8
  __int64 v7; // rsi
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r8
  _QWORD *v12; // rdx
  __int64 v13; // rdi
  __int64 result; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // rdx
  _QWORD *v19; // rcx

  v4 = a1[1];
  v5 = (unsigned __int64)a2 < v4 && *a1 <= (unsigned __int64)a2;
  v6 = a1[2];
  if ( v5 )
  {
    v7 = *a1;
    if ( v4 == v6 && !((__int64)(v6 - v4) >> 3) )
    {
      v8 = (__int64)(v4 - v7) >> 3;
      if ( v8 == 0x1FFFFFFFFFFFFFFFLL )
        std::vector<std::unique_ptr<FilterAgent>>::_Xlen();
      v9 = v8 + 1;
      v10 = 0;
      v11 = (v6 - v7) >> 3;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v11 >> 1) >= v11 )
        v10 = v11 + (v11 >> 1);
      if ( v10 < v9 )
        v10 = v9;
      std::vector<std::unique_ptr<FilterAgent>>::_Reallocate((__int64)a1, v10);
    }
    v12 = (_QWORD *)a1[1];
    v13 = ((__int64)a2 - v7) >> 3;
    result = *(_QWORD *)(*a1 + 8 * v13);
    *(_QWORD *)(*a1 + 8 * v13) = 0;
    *v12 = result;
  }
  else
  {
    if ( v4 == v6 && !((__int64)(v6 - v4) >> 3) )
    {
      v15 = (__int64)(v4 - *a1) >> 3;
      if ( v15 == 0x1FFFFFFFFFFFFFFFLL )
        std::vector<std::unique_ptr<FilterAgent>>::_Xlen();
      v16 = v15 + 1;
      v17 = (v6 - *a1) >> 3;
      v18 = 0;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v17 >> 1) >= v17 )
        v18 = v17 + (v17 >> 1);
      if ( v18 < v16 )
        v18 = v16;
      std::vector<std::unique_ptr<FilterAgent>>::_Reallocate((__int64)a1, v18);
    }
    v19 = (_QWORD *)a1[1];
    result = *a2;
    *a2 = 0;
    *v19 = result;
  }
  a1[1] += 8;
  return result;
}

```

## disassembly

```asm
0x1800114c8  mov     [rsp+arg_0], rbx
0x1800114cd  mov     [rsp+arg_8], rsi
0x1800114d2  push    rdi
0x1800114d3  sub     rsp, 20h
0x1800114d7  mov     rbx, rcx
0x1800114da  mov     rdi, rdx
0x1800114dd  mov     rcx, [rcx+8]
0x1800114e1  cmp     rdx, rcx
0x1800114e4  jnb     short loc_1800114EF
0x1800114e6  cmp     [rbx], rdx
0x1800114e9  ja      short loc_1800114EF
0x1800114eb  mov     al, 1
0x1800114ed  jmp     short loc_1800114F1
0x1800114ef  xor     al, al
0x1800114f1  mov     r8, [rbx+10h]
0x1800114f5  test    al, al
0x1800114f7  jz      loc_180011583
0x1800114fd  mov     rsi, [rbx]
0x180011500  cmp     rcx, r8
0x180011503  jnz     short loc_180011564
0x180011505  mov     rax, r8
0x180011508  sub     rax, rcx
0x18001150b  sar     rax, 3
0x18001150f  cmp     rax, 1
0x180011513  jnb     short loc_180011564
0x180011515  sub     rcx, rsi
0x180011518  mov     r9, 1FFFFFFFFFFFFFFFh
0x180011522  sar     rcx, 3
0x180011526  mov     rax, r9
0x180011529  sub     rax, rcx
0x18001152c  cmp     rax, 1
0x180011530  jb      loc_18001160F
0x180011536  inc     rcx
0x180011539  xor     edx, edx
0x18001153b  sub     r8, rsi
0x18001153e  sar     r8, 3
0x180011542  mov     rax, r8
0x180011545  shr     rax, 1
0x180011548  sub     r9, rax
0x18001154b  add     rax, r8
0x18001154e  cmp     r9, r8
0x180011551  cmovnb  rdx, rax
0x180011555  cmp     rdx, rcx
0x180011558  cmovb   rdx, rcx
0x18001155c  mov     rcx, rbx
0x18001155f  call    ?_Reallocate@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<FilterAgent>>::_Reallocate(unsigned __int64)
0x180011564  mov     rcx, [rbx]
0x180011567  sub     rdi, rsi
0x18001156a  mov     rdx, [rbx+8]
0x18001156e  sar     rdi, 3
0x180011572  mov     rax, [rcx+rdi*8]
0x180011576  mov     qword ptr [rcx+rdi*8], 0
0x18001157e  mov     [rdx], rax
0x180011581  jmp     short loc_1800115F4
0x180011583  cmp     rcx, r8
0x180011586  jnz     short loc_1800115E3
0x180011588  mov     rax, r8
0x18001158b  sub     rax, rcx
0x18001158e  sar     rax, 3
0x180011592  cmp     rax, 1
0x180011596  jnb     short loc_1800115E3
0x180011598  sub     rcx, [rbx]
0x18001159b  mov     r9, 1FFFFFFFFFFFFFFFh
0x1800115a5  sar     rcx, 3
0x1800115a9  mov     rax, r9
0x1800115ac  sub     rax, rcx
0x1800115af  cmp     rax, 1
0x1800115b3  jb      short loc_180011609
0x1800115b5  sub     r8, [rbx]
0x1800115b8  inc     rcx
0x1800115bb  sar     r8, 3
0x1800115bf  xor     edx, edx
0x1800115c1  mov     rax, r8
0x1800115c4  shr     rax, 1
0x1800115c7  sub     r9, rax
0x1800115ca  add     rax, r8
0x1800115cd  cmp     r9, r8
0x1800115d0  cmovnb  rdx, rax
0x1800115d4  cmp     rdx, rcx
0x1800115d7  cmovb   rdx, rcx
0x1800115db  mov     rcx, rbx
0x1800115de  call    ?_Reallocate@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<FilterAgent>>::_Reallocate(unsigned __int64)
0x1800115e3  mov     rcx, [rbx+8]
0x1800115e7  mov     rax, [rdi]
0x1800115ea  mov     qword ptr [rdi], 0
0x1800115f1  mov     [rcx], rax
0x1800115f4  add     qword ptr [rbx+8], 8
0x1800115f9  mov     rbx, [rsp+28h+arg_0]
0x1800115fe  mov     rsi, [rsp+28h+arg_8]
0x180011603  add     rsp, 20h
0x180011607  pop     rdi
0x180011608  retn
0x180011609  call    ?_Xlen@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::unique_ptr<FilterAgent>>::_Xlen(void)
0x18001160f  call    ?_Xlen@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::unique_ptr<FilterAgent>>::_Xlen(void)
```
