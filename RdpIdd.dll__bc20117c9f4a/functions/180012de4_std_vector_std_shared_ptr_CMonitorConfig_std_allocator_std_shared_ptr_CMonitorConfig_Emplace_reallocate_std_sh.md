# std::vector<std::shared_ptr<CMonitorConfig>,std::allocator<std::shared_ptr<CMonitorConfig>>>::_Emplace_reallocate<std::shared_ptr<CMonitorConfig> const &>(std::shared_ptr<CMonitorConfig> * const,std::shared_ptr<CMonitorConfig> const &)

- ea: `0x180012de4`
- end: `0x180012f2b`
- name: `??$_Emplace_reallocate@AEBV?$shared_ptr@VCMonitorConfig@@@std@@@?$vector@V?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VCMonitorConfig@@@1@QEAV21@AEBV21@@Z`
- size: `327`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001a860`
- `0x18001adec`

## callees

- `0x1800086fc`
- `0x18000875c`
- `0x180012cd8`
- `0x180012de4`
- `0x180013204`
- `0x1800137ac`
- `0x180013bb0`
- `0x180015238`
- `0x180020f04`

## pseudocode

```c
unsigned __int64 __fastcall std::vector<std::shared_ptr<CMonitorConfig>>::_Emplace_reallocate<std::shared_ptr<CMonitorConfig> const &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rdi
  __int64 v5; // rsi
  __int64 v8; // r14
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 size_of; // rax
  __int64 v13; // rbp
  unsigned __int64 v14; // r13
  __int64 v15; // r14
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  _QWORD v20[3]; // [rsp+20h] [rbp-78h] BYREF
  __int64 v21; // [rsp+38h] [rbp-60h]
  unsigned __int64 v22; // [rsp+40h] [rbp-58h]

  v3 = 0xFFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 4;
  if ( v5 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<_RDP_MONITORCONFIG_MODE>::_Xlength();
  v8 = a2 - *a1;
  v9 = v5 + 1;
  v10 = (a1[2] - *a1) >> 4;
  v11 = v10 >> 1;
  if ( v10 <= 0xFFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v11 + v10;
    if ( v11 + v10 < v9 )
      v3 = v9;
  }
  size_of = std::_Get_size_of_n<16>(v3);
  v20[0] = a1;
  v20[2] = v3;
  v13 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v14 = (v8 & 0xFFFFFFFFFFFFFFF0uLL) + v13;
  v15 = v14 + 16;
  v22 = v14 + 16;
  std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(v14, a3);
  v16 = a1[1];
  v17 = *a1;
  v21 = v14;
  if ( a2 == v16 )
  {
    v15 = v13;
  }
  else
  {
    std::_Uninitialized_move<std::shared_ptr<CMonitorConfig> *,std::allocator<std::shared_ptr<CMonitorConfig>>>(
      v17,
      a2,
      v13,
      a1,
      v20[0]);
    v16 = a1[1];
    v17 = a2;
    v21 = v13;
  }
  std::_Uninitialized_move<std::shared_ptr<CMonitorConfig> *,std::allocator<std::shared_ptr<CMonitorConfig>>>(
    v17,
    v16,
    v15,
    a1,
    v20[0]);
  v18 = *a1;
  v20[1] = 0;
  if ( v18 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<CMonitorConfig>>>(v18, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL);
  }
  *a1 = v13;
  a1[1] = v13 + 16 * v9;
  a1[2] = v13 + 16 * v3;
  std::vector<std::shared_ptr<CMonitorConfig>>::_Reallocation_guard::~_Reallocation_guard(v20);
  return v14;
}

```

## disassembly

```asm
0x180012de4  push    rbx
0x180012de6  push    rbp
0x180012de7  push    rsi
0x180012de8  push    rdi
0x180012de9  push    r12
0x180012deb  push    r13
0x180012ded  push    r14
0x180012def  push    r15
0x180012df1  sub     rsp, 58h
0x180012df5  mov     rsi, [rcx+8]
0x180012df9  mov     rdi, 0FFFFFFFFFFFFFFFh
0x180012e03  sub     rsi, [rcx]
0x180012e06  mov     r12, r8
0x180012e09  sar     rsi, 4
0x180012e0d  mov     r15, rdx
0x180012e10  mov     rbx, rcx
0x180012e13  cmp     rsi, rdi
0x180012e16  jz      loc_180012F25
0x180012e1c  mov     r14, rdx
0x180012e1f  mov     rax, rdi
0x180012e22  sub     r14, [rcx]
0x180012e25  mov     rcx, [rcx+10h]
0x180012e29  inc     rsi
0x180012e2c  sub     rcx, [rbx]
0x180012e2f  sar     rcx, 4
0x180012e33  mov     rdx, rcx
0x180012e36  shr     rdx, 1
0x180012e39  sub     rax, rdx
0x180012e3c  cmp     rcx, rax
0x180012e3f  ja      short loc_180012E4C
0x180012e41  lea     rdi, [rdx+rcx]
0x180012e45  cmp     rdi, rsi
0x180012e48  cmovb   rdi, rsi
0x180012e4c  mov     rcx, rdi
0x180012e4f  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x180012e54  mov     rcx, rax
0x180012e57  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180012e5c  and     r14, 0FFFFFFFFFFFFFFF0h
0x180012e60  mov     [rsp+98h+var_78], rbx
0x180012e65  mov     rdx, r12
0x180012e68  mov     [rsp+98h+var_68], rdi
0x180012e6d  mov     rbp, rax
0x180012e70  lea     r13, [r14+rax]
0x180012e74  lea     r14, [r13+10h]
0x180012e78  mov     rcx, r13
0x180012e7b  mov     [rsp+98h+var_58], r14
0x180012e80  call    ??0?$shared_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x180012e85  mov     rdx, [rbx+8]
0x180012e89  mov     rcx, [rbx]
0x180012e8c  mov     [rsp+98h+var_60], r13
0x180012e91  cmp     r15, rdx
0x180012e94  jnz     short loc_180012E9B
0x180012e96  mov     r14, rbp
0x180012e99  jmp     short loc_180012EB5
0x180012e9b  mov     r9, rbx
0x180012e9e  mov     r8, rbp
0x180012ea1  mov     rdx, r15
0x180012ea4  call    ??$_Uninitialized_move@PEAV?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@YAPEAV?$shared_ptr@VCMonitorConfig@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<CMonitorConfig> *,std::allocator<std::shared_ptr<CMonitorConfig>>>(std::shared_ptr<CMonitorConfig> * const,std::shared_ptr<CMonitorConfig> * const,std::shared_ptr<CMonitorConfig> *,std::allocator<std::shared_ptr<CMonitorConfig>> &)
0x180012ea9  mov     rdx, [rbx+8]
0x180012ead  mov     rcx, r15
0x180012eb0  mov     [rsp+98h+var_60], rbp
0x180012eb5  mov     r9, rbx
0x180012eb8  mov     r8, r14
0x180012ebb  call    ??$_Uninitialized_move@PEAV?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@YAPEAV?$shared_ptr@VCMonitorConfig@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<CMonitorConfig> *,std::allocator<std::shared_ptr<CMonitorConfig>>>(std::shared_ptr<CMonitorConfig> * const,std::shared_ptr<CMonitorConfig> * const,std::shared_ptr<CMonitorConfig> *,std::allocator<std::shared_ptr<CMonitorConfig>> &)
0x180012ec0  mov     rcx, [rbx]
0x180012ec3  mov     [rsp+98h+var_70], 0
0x180012ecc  test    rcx, rcx
0x180012ecf  jz      short loc_180012EED
0x180012ed1  mov     rdx, [rbx+8]
0x180012ed5  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VCMonitorConfig@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<CMonitorConfig>>>(std::shared_ptr<CMonitorConfig> *,std::shared_ptr<CMonitorConfig> * const,std::allocator<std::shared_ptr<CMonitorConfig>> &)
0x180012eda  mov     rdx, [rbx+10h]
0x180012ede  sub     rdx, [rbx]
0x180012ee1  mov     rcx, [rbx]
0x180012ee4  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180012ee8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012eed  mov     [rbx], rbp
0x180012ef0  lea     rcx, [rsp+98h+var_78]
0x180012ef5  shl     rsi, 4
0x180012ef9  shl     rdi, 4
0x180012efd  add     rsi, rbp
0x180012f00  add     rdi, rbp
0x180012f03  mov     [rbx+8], rsi
0x180012f07  mov     [rbx+10h], rdi
0x180012f0b  call    ??1_Reallocation_guard@?$vector@V?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<CMonitorConfig>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180012f10  mov     rax, r13
0x180012f13  add     rsp, 58h
0x180012f17  pop     r15
0x180012f19  pop     r14
0x180012f1b  pop     r13
0x180012f1d  pop     r12
0x180012f1f  pop     rdi
0x180012f20  pop     rsi
0x180012f21  pop     rbp
0x180012f22  pop     rbx
0x180012f23  retn
0x180012f25  call    ?_Xlength@?$vector@U_RDP_MONITORCONFIG_MODE@@V?$allocator@U_RDP_MONITORCONFIG_MODE@@@std@@@std@@CAXXZ; std::vector<_RDP_MONITORCONFIG_MODE>::_Xlength(void)
```
