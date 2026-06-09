# std::vector<std::shared_ptr<CConfigSet>,std::allocator<std::shared_ptr<CConfigSet>>>::push_back(std::shared_ptr<CConfigSet> const &)

- ea: `0x18000f790`
- end: `0x18000f98f`
- name: `?push_back@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@QEAAXAEBV?$shared_ptr@VCConfigSet@@@2@@Z`
- size: `511`
- prototype: `char __fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e184`

## callees

- `0x18000a1c4`
- `0x18000a398`
- `0x18000f790`
- `0x180012010`

## pseudocode

```c
char __fastcall std::vector<std::shared_ptr<CConfigSet>>::push_back(__int64 *a1, __int64 *a2)
{
  unsigned __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // rsi
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rdi
  _QWORD *v13; // r14
  __int64 v14; // rbp
  __int64 v15; // r15
  volatile signed __int32 *v16; // rsi
  bool v17; // zf
  __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // rdx
  _QWORD *v22; // r14
  __int64 v23; // rbp
  __int64 v24; // r15
  volatile signed __int32 *v25; // rsi

  v4 = a1[1];
  LOBYTE(v5) = (unsigned __int64)a2 < v4 && *a1 <= (unsigned __int64)a2;
  v6 = a1[2];
  if ( (_BYTE)v5 )
  {
    v7 = *a1;
    if ( v4 == v6 && !((__int64)(v6 - v4) >> 4) )
    {
      v8 = (__int64)(v4 - v7) >> 4;
      if ( v8 == 0xFFFFFFFFFFFFFFFLL )
        std::vector<std::shared_ptr<CConfigSource>>::_Xlen();
      v9 = v8 + 1;
      v10 = (v6 - v7) >> 4;
      v11 = 0;
      if ( 0xFFFFFFFFFFFFFFFLL - (v10 >> 1) >= v10 )
        v11 = v10 + (v10 >> 1);
      if ( v11 < v9 )
        v11 = v9;
      std::vector<std::shared_ptr<CConfigSet>>::_Reallocate((__int64)a1, v11);
    }
    v12 = ((unsigned __int64)a2 - v7) & 0xFFFFFFFFFFFFFFF0uLL;
    v5 = *a1;
    v13 = (_QWORD *)a1[1];
    *v13 = 0;
    v13[1] = 0;
    v14 = *(_QWORD *)(v12 + v5 + 8);
    v15 = *(_QWORD *)(v12 + v5);
    if ( v14 )
      _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
    v16 = (volatile signed __int32 *)v13[1];
    if ( v16 )
    {
      LODWORD(v5) = _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF);
      v17 = (_DWORD)v5 == 1;
      LOBYTE(v5) = v5 - 1;
      if ( v17 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        LODWORD(v5) = _InterlockedDecrement(v16 + 3);
        if ( !(_DWORD)v5 )
          LOBYTE(v5) = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    v13[1] = v14;
    *v13 = v15;
  }
  else
  {
    if ( v4 == v6 )
    {
      v5 = (__int64)(v6 - v4) >> 4;
      if ( !v5 )
      {
        v18 = (__int64)(v4 - *a1) >> 4;
        if ( v18 == 0xFFFFFFFFFFFFFFFLL )
          std::vector<std::shared_ptr<CConfigSource>>::_Xlen();
        v19 = v18 + 1;
        v20 = (v6 - *a1) >> 4;
        v21 = 0;
        if ( 0xFFFFFFFFFFFFFFFLL - (v20 >> 1) >= v20 )
          v21 = v20 + (v20 >> 1);
        if ( v21 < v19 )
          v21 = v19;
        LOBYTE(v5) = (unsigned __int8)std::vector<std::shared_ptr<CConfigSet>>::_Reallocate((__int64)a1, v21);
      }
    }
    v22 = (_QWORD *)a1[1];
    *v22 = 0;
    v22[1] = 0;
    v23 = a2[1];
    v24 = *a2;
    if ( v23 )
      _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
    v25 = (volatile signed __int32 *)v22[1];
    if ( v25 )
    {
      LODWORD(v5) = _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF);
      v17 = (_DWORD)v5 == 1;
      LOBYTE(v5) = v5 - 1;
      if ( v17 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
        LODWORD(v5) = _InterlockedDecrement(v25 + 3);
        if ( !(_DWORD)v5 )
          LOBYTE(v5) = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
      }
    }
    v22[1] = v23;
    *v22 = v24;
  }
  a1[1] += 16;
  return v5;
}

```

## disassembly

```asm
0x18000f790  push    rbx
0x18000f792  push    rbp
0x18000f793  push    rsi
0x18000f794  push    rdi
0x18000f795  push    r14
0x18000f797  push    r15
0x18000f799  sub     rsp, 28h
0x18000f79d  mov     rdi, rdx
0x18000f7a0  mov     rbx, rcx
0x18000f7a3  mov     rcx, [rcx+8]
0x18000f7a7  cmp     rdx, rcx
0x18000f7aa  jnb     short loc_18000F7B5
0x18000f7ac  cmp     [rbx], rdx
0x18000f7af  ja      short loc_18000F7B5
0x18000f7b1  mov     al, 1
0x18000f7b3  jmp     short loc_18000F7B7
0x18000f7b5  xor     al, al
0x18000f7b7  mov     r8, [rbx+10h]
0x18000f7bb  test    al, al
0x18000f7bd  jz      loc_18000F8A4
0x18000f7c3  mov     rsi, [rbx]
0x18000f7c6  cmp     rcx, r8
0x18000f7c9  jnz     short loc_18000F82A
0x18000f7cb  mov     rax, r8
0x18000f7ce  sub     rax, rcx
0x18000f7d1  sar     rax, 4
0x18000f7d5  cmp     rax, 1
0x18000f7d9  jnb     short loc_18000F82A
0x18000f7db  sub     rcx, rsi
0x18000f7de  sar     rcx, 4
0x18000f7e2  mov     r9, 0FFFFFFFFFFFFFFFh
0x18000f7ec  mov     rax, r9
0x18000f7ef  sub     rax, rcx
0x18000f7f2  cmp     rax, 1
0x18000f7f6  jb      loc_18000F989
0x18000f7fc  inc     rcx
0x18000f7ff  sub     r8, rsi
0x18000f802  sar     r8, 4
0x18000f806  mov     rax, r8
0x18000f809  shr     rax, 1
0x18000f80c  sub     r9, rax
0x18000f80f  add     rax, r8
0x18000f812  xor     edx, edx
0x18000f814  cmp     r9, r8
0x18000f817  cmovnb  rdx, rax
0x18000f81b  cmp     rdx, rcx
0x18000f81e  cmovb   rdx, rcx
0x18000f822  mov     rcx, rbx
0x18000f825  call    ?_Reallocate@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::shared_ptr<CConfigSet>>::_Reallocate(unsigned __int64)
0x18000f82a  sub     rdi, rsi
0x18000f82d  and     rdi, 0FFFFFFFFFFFFFFF0h
0x18000f831  mov     rax, [rbx]
0x18000f834  mov     r14, [rbx+8]
0x18000f838  mov     qword ptr [r14], 0
0x18000f83f  mov     qword ptr [r14+8], 0
0x18000f847  mov     rbp, [rdi+rax+8]
0x18000f84c  mov     r15, [rdi+rax]
0x18000f850  test    rbp, rbp
0x18000f853  jz      short loc_18000F859
0x18000f855  lock inc dword ptr [rbp+8]
0x18000f859  mov     rsi, [r14+8]
0x18000f85d  test    rsi, rsi
0x18000f860  jz      short loc_18000F898
0x18000f862  or      edi, 0FFFFFFFFh
0x18000f865  mov     eax, edi
0x18000f867  lock xadd [rsi+8], eax
0x18000f86c  add     eax, edi
0x18000f86e  jnz     short loc_18000F898
0x18000f870  mov     rax, [rsi]
0x18000f873  mov     rcx, rsi
0x18000f876  mov     rax, [rax]
0x18000f879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f87e  mov     eax, edi
0x18000f880  lock xadd [rsi+0Ch], eax
0x18000f885  add     eax, edi
0x18000f887  jnz     short loc_18000F898
0x18000f889  mov     rax, [rsi]
0x18000f88c  mov     rcx, rsi
0x18000f88f  mov     rax, [rax+8]
0x18000f893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f898  mov     [r14+8], rbp
0x18000f89c  mov     [r14], r15
0x18000f89f  jmp     loc_18000F971
0x18000f8a4  cmp     rcx, r8
0x18000f8a7  jnz     short loc_18000F908
0x18000f8a9  mov     rax, r8
0x18000f8ac  sub     rax, rcx
0x18000f8af  sar     rax, 4
0x18000f8b3  cmp     rax, 1
0x18000f8b7  jnb     short loc_18000F908
0x18000f8b9  sub     rcx, [rbx]
0x18000f8bc  sar     rcx, 4
0x18000f8c0  mov     r9, 0FFFFFFFFFFFFFFFh
0x18000f8ca  mov     rax, r9
0x18000f8cd  sub     rax, rcx
0x18000f8d0  cmp     rax, 1
0x18000f8d4  jb      loc_18000F983
0x18000f8da  inc     rcx
0x18000f8dd  sub     r8, [rbx]
0x18000f8e0  sar     r8, 4
0x18000f8e4  mov     rax, r8
0x18000f8e7  shr     rax, 1
0x18000f8ea  sub     r9, rax
0x18000f8ed  add     rax, r8
0x18000f8f0  xor     edx, edx
0x18000f8f2  cmp     r9, r8
0x18000f8f5  cmovnb  rdx, rax
0x18000f8f9  cmp     rdx, rcx
0x18000f8fc  cmovb   rdx, rcx
0x18000f900  mov     rcx, rbx
0x18000f903  call    ?_Reallocate@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::shared_ptr<CConfigSet>>::_Reallocate(unsigned __int64)
0x18000f908  mov     r14, [rbx+8]
0x18000f90c  mov     qword ptr [r14], 0
0x18000f913  mov     qword ptr [r14+8], 0
0x18000f91b  mov     rbp, [rdi+8]
0x18000f91f  mov     r15, [rdi]
0x18000f922  test    rbp, rbp
0x18000f925  jz      short loc_18000F92B
0x18000f927  lock inc dword ptr [rbp+8]
0x18000f92b  mov     rsi, [r14+8]
0x18000f92f  test    rsi, rsi
0x18000f932  jz      short loc_18000F96A
0x18000f934  or      edi, 0FFFFFFFFh
0x18000f937  mov     eax, edi
0x18000f939  lock xadd [rsi+8], eax
0x18000f93e  add     eax, edi
0x18000f940  jnz     short loc_18000F96A
0x18000f942  mov     rax, [rsi]
0x18000f945  mov     rcx, rsi
0x18000f948  mov     rax, [rax]
0x18000f94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f950  mov     eax, edi
0x18000f952  lock xadd [rsi+0Ch], eax
0x18000f957  add     eax, edi
0x18000f959  jnz     short loc_18000F96A
0x18000f95b  mov     rax, [rsi]
0x18000f95e  mov     rcx, rsi
0x18000f961  mov     rax, [rax+8]
0x18000f965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f96a  mov     [r14+8], rbp
0x18000f96e  mov     [r14], r15
0x18000f971  add     qword ptr [rbx+8], 10h
0x18000f976  add     rsp, 28h
0x18000f97a  pop     r15
0x18000f97c  pop     r14
0x18000f97e  pop     rdi
0x18000f97f  pop     rsi
0x18000f980  pop     rbp
0x18000f981  pop     rbx
0x18000f982  retn
0x18000f983  call    ?_Xlen@?$vector@V?$shared_ptr@VCConfigSource@@@std@@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@2@@std@@IEBAXXZ; std::vector<std::shared_ptr<CConfigSource>>::_Xlen(void)
0x18000f989  call    ?_Xlen@?$vector@V?$shared_ptr@VCConfigSource@@@std@@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@2@@std@@IEBAXXZ; std::vector<std::shared_ptr<CConfigSource>>::_Xlen(void)
```
