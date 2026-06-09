# std::vector<Broker::ApplicationIdentity,std::allocator<Broker::ApplicationIdentity>>::_Emplace_reallocate<Broker::ApplicationIdentity>(Broker::ApplicationIdentity * const,Broker::ApplicationIdentity &&)

- ea: `0x180019d48`
- end: `0x180019e8e`
- name: `??$_Emplace_reallocate@UApplicationIdentity@Broker@@@?$vector@UApplicationIdentity@Broker@@V?$allocator@UApplicationIdentity@Broker@@@std@@@std@@AEAAPEAUApplicationIdentity@Broker@@QEAU23@$$QEAU23@@Z`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006540`

## callees

- `0x180004be0`
- `0x180004ca8`
- `0x180006a5c`
- `0x180006aa0`
- `0x180012d88`
- `0x180019d48`
- `0x180019e94`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180019d94`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180019d94`

## pseudocode

```c
__int64 __fastcall std::vector<Broker::ApplicationIdentity>::_Emplace_reallocate<Broker::ApplicationIdentity>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r15
  __int64 v4; // rbx
  __int64 v7; // rax
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  __int64 v13; // rsi
  __int64 v14; // r15
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  _QWORD *v19; // [rsp+20h] [rbp-78h] BYREF
  __int64 v20; // [rsp+30h] [rbp-68h]
  __int64 v21; // [rsp+38h] [rbp-60h]
  __int64 v22; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v4 = 0x2E8BA2E8BA2E8BALL;
  v7 = 0x2E8BA2E8BA2E8BA3LL * ((__int64)(a1[1] - *a1) >> 3);
  if ( v7 == 0x2E8BA2E8BA2E8BALL )
    std::_Xlength_error("vector too long");
  v9 = v7 + 1;
  v10 = 0x2E8BA2E8BA2E8BA3LL * ((a1[2] - v3) >> 3);
  if ( v10 <= 0x2E8BA2E8BA2E8BALL - (v10 >> 1) )
  {
    v11 = (v10 >> 1) + v10;
    v12 = v9;
    if ( v11 >= v9 )
      v12 = v11;
    if ( v12 > 0x2E8BA2E8BA2E8BALL )
      std::_Throw_bad_array_new_length();
    v4 = v12;
  }
  v13 = std::_Allocate<16,std::_Default_allocate_traits>(88 * v4);
  v19 = a1;
  v20 = v4;
  v14 = v13 + 88 * ((a2 - v3) / 88);
  v22 = v14 + 88;
  Broker::ApplicationIdentity::ApplicationIdentity(v14, a3);
  v15 = a1[1];
  v16 = v13;
  v17 = *a1;
  v21 = v14;
  if ( a2 != v15 )
  {
    std::_Uninitialized_move<Broker::ApplicationIdentity *>(v17, a2, v13);
    v15 = a1[1];
    v16 = v14 + 88;
    v17 = a2;
    v21 = v13;
  }
  std::_Uninitialized_move<Broker::ApplicationIdentity *>(v17, v15, v16);
  std::vector<Broker::ApplicationIdentity>::_Change_array(a1, v13, v9, v4, v19, 0, v20, v21, v22);
  std::vector<Broker::ApplicationIdentity>::_Reallocation_guard::~_Reallocation_guard(&v19);
  return v14;
}

```

## disassembly

```asm
0x180019d48  push    rbx
0x180019d4a  push    rbp
0x180019d4b  push    rsi
0x180019d4c  push    rdi
0x180019d4d  push    r12
0x180019d4f  push    r13
0x180019d51  push    r14
0x180019d53  push    r15
0x180019d55  sub     rsp, 58h
0x180019d59  mov     r15, [rcx]
0x180019d5c  mov     r12, 2E8BA2E8BA2E8BA3h
0x180019d66  mov     rax, [rcx+8]
0x180019d6a  mov     rbx, 2E8BA2E8BA2E8BAh
0x180019d74  sub     rax, r15
0x180019d77  mov     r13, r8
0x180019d7a  sar     rax, 3
0x180019d7e  mov     r14, rdx
0x180019d81  imul    rax, r12
0x180019d85  mov     rdi, rcx
0x180019d88  cmp     rax, rbx
0x180019d8b  jnz     short loc_180019D9B
0x180019d8d  lea     rcx, aVectorTooLong; "vector too long"
0x180019d94  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180019d9b  mov     rcx, [rcx+10h]
0x180019d9f  lea     rbp, [rax+1]
0x180019da3  sub     rcx, r15
0x180019da6  mov     rax, rbx
0x180019da9  sar     rcx, 3
0x180019dad  imul    rcx, r12
0x180019db1  mov     rdx, rcx
0x180019db4  shr     rdx, 1
0x180019db7  sub     rax, rdx
0x180019dba  cmp     rcx, rax
0x180019dbd  ja      short loc_180019DDB
0x180019dbf  lea     rax, [rdx+rcx]
0x180019dc3  mov     rcx, rbp
0x180019dc6  cmp     rax, rbp
0x180019dc9  cmovnb  rcx, rax
0x180019dcd  cmp     rcx, rbx
0x180019dd0  jbe     short loc_180019DD8
0x180019dd2  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180019dd8  mov     rbx, rcx
0x180019ddb  imul    rcx, rbx, 58h ; 'X'
0x180019ddf  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180019de4  mov     rsi, rax
0x180019de7  mov     [rsp+98h+var_78], rdi
0x180019dec  mov     rax, r12
0x180019def  mov     [rsp+98h+var_68], rbx
0x180019df4  mov     rcx, r14
0x180019df7  sub     rcx, r15
0x180019dfa  imul    rcx
0x180019dfd  sar     rdx, 4
0x180019e01  mov     rcx, rdx
0x180019e04  shr     rcx, 3Fh
0x180019e08  add     rdx, rcx
0x180019e0b  imul    r15, rdx, 58h ; 'X'
0x180019e0f  mov     rdx, r13
0x180019e12  add     r15, rsi
0x180019e15  mov     rcx, r15
0x180019e18  lea     r12, [r15+58h]
0x180019e1c  mov     [rsp+98h+var_58], r12
0x180019e21  call    ??0ApplicationIdentity@Broker@@QEAA@$$QEAU01@@Z; Broker::ApplicationIdentity::ApplicationIdentity(Broker::ApplicationIdentity &&)
0x180019e26  mov     rdx, [rdi+8]
0x180019e2a  mov     r8, rsi
0x180019e2d  mov     rcx, [rdi]
0x180019e30  mov     [rsp+98h+var_60], r15
0x180019e35  cmp     r14, rdx
0x180019e38  jz      short loc_180019E51
0x180019e3a  mov     rdx, r14
0x180019e3d  call    ??$_Uninitialized_move@PEAUApplicationIdentity@Broker@@V?$allocator@UApplicationIdentity@Broker@@@std@@@std@@YAPEAUApplicationIdentity@Broker@@QEAU12@0PEAU12@AEAV?$allocator@UApplicationIdentity@Broker@@@0@@Z; std::_Uninitialized_move<Broker::ApplicationIdentity *>(Broker::ApplicationIdentity * const,Broker::ApplicationIdentity * const,Broker::ApplicationIdentity *,std::allocator<Broker::ApplicationIdentity> &)
0x180019e42  mov     rdx, [rdi+8]
0x180019e46  mov     r8, r12
0x180019e49  mov     rcx, r14
0x180019e4c  mov     [rsp+98h+var_60], rsi
0x180019e51  call    ??$_Uninitialized_move@PEAUApplicationIdentity@Broker@@V?$allocator@UApplicationIdentity@Broker@@@std@@@std@@YAPEAUApplicationIdentity@Broker@@QEAU12@0PEAU12@AEAV?$allocator@UApplicationIdentity@Broker@@@0@@Z; std::_Uninitialized_move<Broker::ApplicationIdentity *>(Broker::ApplicationIdentity * const,Broker::ApplicationIdentity * const,Broker::ApplicationIdentity *,std::allocator<Broker::ApplicationIdentity> &)
0x180019e56  mov     r9, rbx
0x180019e59  mov     [rsp+98h+var_70], 0
0x180019e62  mov     r8, rbp
0x180019e65  mov     rdx, rsi
0x180019e68  mov     rcx, rdi
0x180019e6b  call    ?_Change_array@?$vector@UApplicationIdentity@Broker@@V?$allocator@UApplicationIdentity@Broker@@@std@@@std@@AEAAXQEAUApplicationIdentity@Broker@@_K1@Z; std::vector<Broker::ApplicationIdentity>::_Change_array(Broker::ApplicationIdentity * const,unsigned __int64,unsigned __int64)
0x180019e70  lea     rcx, [rsp+98h+var_78]
0x180019e75  call    ??1_Reallocation_guard@?$vector@UApplicationIdentity@Broker@@V?$allocator@UApplicationIdentity@Broker@@@std@@@std@@QEAA@XZ; std::vector<Broker::ApplicationIdentity>::_Reallocation_guard::~_Reallocation_guard(void)
0x180019e7a  mov     rax, r15
0x180019e7d  add     rsp, 58h
0x180019e81  pop     r15
0x180019e83  pop     r14
0x180019e85  pop     r13
0x180019e87  pop     r12
0x180019e89  pop     rdi
0x180019e8a  pop     rsi
0x180019e8b  pop     rbp
0x180019e8c  pop     rbx
0x180019e8d  retn
```
