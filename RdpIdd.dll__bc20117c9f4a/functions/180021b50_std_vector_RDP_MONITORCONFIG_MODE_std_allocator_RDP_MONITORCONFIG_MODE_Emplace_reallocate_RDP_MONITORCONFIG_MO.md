# std::vector<_RDP_MONITORCONFIG_MODE,std::allocator<_RDP_MONITORCONFIG_MODE>>::_Emplace_reallocate<_RDP_MONITORCONFIG_MODE const &>(_RDP_MONITORCONFIG_MODE * const,_RDP_MONITORCONFIG_MODE const &)

- ea: `0x180021b50`
- end: `0x180021c85`
- name: `??$_Emplace_reallocate@AEBU_RDP_MONITORCONFIG_MODE@@@?$vector@U_RDP_MONITORCONFIG_MODE@@V?$allocator@U_RDP_MONITORCONFIG_MODE@@@std@@@std@@AEAAPEAU_RDP_MONITORCONFIG_MODE@@QEAU2@AEBU2@@Z`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180021f78`

## callees

- `0x1800086fc`
- `0x18000bdcc`
- `0x180020f04`
- `0x180021b50`
- `0x180021d8c`
- `0x1800225c4`
- `0x180022e54`
- `0x180022ee8`

## pseudocode

```c
_OWORD *__fastcall std::vector<_RDP_MONITORCONFIG_MODE>::_Emplace_reallocate<_RDP_MONITORCONFIG_MODE const &>(
        _QWORD *a1,
        __int64 a2,
        __int128 *a3)
{
  __int64 v3; // r15
  __int64 v6; // rax
  __int64 v8; // r14
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // r10
  __int64 v12; // rax
  __int128 v13; // xmm0
  __int64 v14; // rdi
  _OWORD *v15; // r15
  __int128 v16; // xmm1
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *v20; // [rsp+20h] [rbp-78h] BYREF
  unsigned __int64 v21; // [rsp+30h] [rbp-68h]
  _OWORD *v22; // [rsp+38h] [rbp-60h]
  char *v23; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v6 = 0x2E8BA2E8BA2E8BA3LL * ((__int64)(a1[1] - *a1) >> 2);
  if ( v6 == 0x5D1745D1745D174LL )
    std::vector<_RDP_MONITORCONFIG_MODE>::_Xlength();
  v8 = v6 + 1;
  v9 = std::vector<_RDP_MONITORCONFIG_MODE>::_Calculate_growth(a1, v6 + 1);
  v10 = v9;
  if ( v9 > v11 )
    std::_Throw_bad_array_new_length();
  v12 = std::_Allocate<16,std::_Default_allocate_traits>(44 * v9);
  v13 = *a3;
  v14 = v12;
  v20 = a1;
  v21 = v10;
  v15 = (_OWORD *)(v12 + 44 * ((a2 - v3) / 44));
  v22 = v15;
  *v15 = v13;
  v16 = a3[1];
  v23 = (char *)v15 + 44;
  v15[1] = v16;
  *(_OWORD *)((char *)v15 + 28) = *(__int128 *)((char *)a3 + 28);
  v17 = a1[1];
  v18 = *a1;
  if ( a2 != v17 )
  {
    std::_Uninitialized_move<_RDP_MONITORCONFIG_MODE *>(v18, a2);
    v17 = a1[1];
    v18 = a2;
    v22 = (_OWORD *)v14;
  }
  std::_Uninitialized_move<_RDP_MONITORCONFIG_MODE *>(v18, v17);
  std::vector<_RDP_MONITORCONFIG_MODE>::_Change_array(a1, v14, v8, v10, v20, 0, v21, v22, v23);
  std::vector<_RDP_MONITORCONFIG_MODE>::_Reallocation_guard::~_Reallocation_guard(&v20);
  return v15;
}

```

## disassembly

```asm
0x180021b50  push    rbx
0x180021b52  push    rbp
0x180021b53  push    rsi
0x180021b54  push    rdi
0x180021b55  push    r12
0x180021b57  push    r13
0x180021b59  push    r14
0x180021b5b  push    r15
0x180021b5d  sub     rsp, 58h
0x180021b61  mov     r15, [rcx]
0x180021b64  mov     r13, 2E8BA2E8BA2E8BA3h
0x180021b6e  mov     rax, [rcx+8]
0x180021b72  mov     r10, 5D1745D1745D174h
0x180021b7c  sub     rax, r15
0x180021b7f  mov     r12, r8
0x180021b82  sar     rax, 2
0x180021b86  mov     rbp, rdx
0x180021b89  imul    rax, r13
0x180021b8d  mov     rbx, rcx
0x180021b90  cmp     rax, r10
0x180021b93  jz      loc_180021C7F
0x180021b99  lea     r14, [rax+1]
0x180021b9d  mov     rdx, r14
0x180021ba0  call    ?_Calculate_growth@?$vector@U_RDP_MONITORCONFIG_MODE@@V?$allocator@U_RDP_MONITORCONFIG_MODE@@@std@@@std@@AEBA_K_K@Z; std::vector<_RDP_MONITORCONFIG_MODE>::_Calculate_growth(unsigned __int64)
0x180021ba5  mov     rsi, rax
0x180021ba8  cmp     rax, r10
0x180021bab  ja      loc_180021C79
0x180021bb1  imul    rcx, rsi, 2Ch ; ','
0x180021bb5  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180021bba  movups  xmm0, xmmword ptr [r12]
0x180021bbf  mov     rdi, rax
0x180021bc2  mov     [rsp+98h+var_78], rbx
0x180021bc7  mov     rax, r13
0x180021bca  mov     [rsp+98h+var_68], rsi
0x180021bcf  mov     rcx, rbp
0x180021bd2  mov     r8, rdi
0x180021bd5  sub     rcx, r15
0x180021bd8  imul    rcx
0x180021bdb  sar     rdx, 3
0x180021bdf  mov     rcx, rdx
0x180021be2  shr     rcx, 3Fh
0x180021be6  add     rdx, rcx
0x180021be9  imul    r15, rdx, 2Ch ; ','
0x180021bed  add     r15, rdi
0x180021bf0  mov     [rsp+98h+var_60], r15
0x180021bf5  movups  xmmword ptr [r15], xmm0
0x180021bf9  lea     r13, [r15+2Ch]
0x180021bfd  movups  xmm1, xmmword ptr [r12+10h]
0x180021c03  mov     [rsp+98h+var_58], r13
0x180021c08  movups  xmmword ptr [r15+10h], xmm1
0x180021c0d  movups  xmm0, xmmword ptr [r12+1Ch]
0x180021c13  movups  xmmword ptr [r15+1Ch], xmm0
0x180021c18  mov     rdx, [rbx+8]
0x180021c1c  mov     rcx, [rbx]
0x180021c1f  cmp     rbp, rdx
0x180021c22  jz      short loc_180021C3B
0x180021c24  mov     rdx, rbp
0x180021c27  call    ??$_Uninitialized_move@PEAU_RDP_MONITORCONFIG_MODE@@V?$allocator@U_RDP_MONITORCONFIG_MODE@@@std@@@std@@YAPEAU_RDP_MONITORCONFIG_MODE@@QEAU1@0PEAU1@AEAV?$allocator@U_RDP_MONITORCONFIG_MODE@@@0@@Z; std::_Uninitialized_move<_RDP_MONITORCONFIG_MODE *>(_RDP_MONITORCONFIG_MODE * const,_RDP_MONITORCONFIG_MODE * const,_RDP_MONITORCONFIG_MODE *,std::allocator<_RDP_MONITORCONFIG_MODE> &)
0x180021c2c  mov     rdx, [rbx+8]
0x180021c30  mov     r8, r13
0x180021c33  mov     rcx, rbp
0x180021c36  mov     [rsp+98h+var_60], rdi
0x180021c3b  call    ??$_Uninitialized_move@PEAU_RDP_MONITORCONFIG_MODE@@V?$allocator@U_RDP_MONITORCONFIG_MODE@@@std@@@std@@YAPEAU_RDP_MONITORCONFIG_MODE@@QEAU1@0PEAU1@AEAV?$allocator@U_RDP_MONITORCONFIG_MODE@@@0@@Z; std::_Uninitialized_move<_RDP_MONITORCONFIG_MODE *>(_RDP_MONITORCONFIG_MODE * const,_RDP_MONITORCONFIG_MODE * const,_RDP_MONITORCONFIG_MODE *,std::allocator<_RDP_MONITORCONFIG_MODE> &)
0x180021c40  mov     r9, rsi
0x180021c43  mov     [rsp+98h+var_70], 0
0x180021c4c  mov     r8, r14
0x180021c4f  mov     rdx, rdi
0x180021c52  mov     rcx, rbx
0x180021c55  call    ?_Change_array@?$vector@U_RDP_MONITORCONFIG_MODE@@V?$allocator@U_RDP_MONITORCONFIG_MODE@@@std@@@std@@AEAAXQEAU_RDP_MONITORCONFIG_MODE@@_K1@Z; std::vector<_RDP_MONITORCONFIG_MODE>::_Change_array(_RDP_MONITORCONFIG_MODE * const,unsigned __int64,unsigned __int64)
0x180021c5a  lea     rcx, [rsp+98h+var_78]
0x180021c5f  call    ??1_Reallocation_guard@?$vector@U_RDP_MONITORCONFIG_MODE@@V?$allocator@U_RDP_MONITORCONFIG_MODE@@@std@@@std@@QEAA@XZ; std::vector<_RDP_MONITORCONFIG_MODE>::_Reallocation_guard::~_Reallocation_guard(void)
0x180021c64  mov     rax, r15
0x180021c67  add     rsp, 58h
0x180021c6b  pop     r15
0x180021c6d  pop     r14
0x180021c6f  pop     r13
0x180021c71  pop     r12
0x180021c73  pop     rdi
0x180021c74  pop     rsi
0x180021c75  pop     rbp
0x180021c76  pop     rbx
0x180021c77  retn
0x180021c79  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180021c7f  call    ?_Xlength@?$vector@U_RDP_MONITORCONFIG_MODE@@V?$allocator@U_RDP_MONITORCONFIG_MODE@@@std@@@std@@CAXXZ; std::vector<_RDP_MONITORCONFIG_MODE>::_Xlength(void)
```
