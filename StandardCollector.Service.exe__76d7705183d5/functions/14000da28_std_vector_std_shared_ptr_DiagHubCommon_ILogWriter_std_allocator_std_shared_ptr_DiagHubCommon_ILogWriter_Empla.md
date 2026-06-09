# std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>::_Emplace_reallocate<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::shared_ptr<DiagHubCommon::ILogWriter> &&)

- ea: `0x14000da28`
- end: `0x14000dc62`
- name: `??$_Emplace_reallocate@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@1@QEAV21@$$QEAV21@@Z`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000a42c`

## callees

- `0x140002330`
- `0x140003474`
- `0x140003494`
- `0x14000d9b0`
- `0x14000da28`
- `0x14000dff0`
- `0x14001382c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x14000dc4f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x14000dc4f`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Emplace_reallocate<std::shared_ptr<DiagHubCommon::ILogWriter>>(
        __int64 *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rsi
  __int64 v6; // rbp
  _QWORD *v7; // rbx
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rcx
  __int64 v14; // r14
  _QWORD *v15; // r12
  _QWORD *v16; // rsi
  _QWORD *v17; // rcx
  _QWORD *v18; // r8
  _QWORD *v19; // rdx
  _QWORD *v20; // rdx
  _QWORD *v21; // rcx
  _QWORD *v22; // rcx
  _QWORD *v23; // rcx
  _QWORD v25[3]; // [rsp+38h] [rbp-60h] BYREF
  _QWORD *v26; // [rsp+50h] [rbp-48h]
  _QWORD *v27; // [rsp+58h] [rbp-40h]

  v3 = 0xFFFFFFFFFFFFFFFLL;
  v4 = (unsigned __int64)a2 - *a1;
  v6 = (a1[1] - *a1) >> 4;
  v7 = a2;
  if ( v6 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Xlength(a1, a2, a3);
  v9 = v6 + 1;
  v10 = (a1[2] - *a1) >> 4;
  v11 = v10 >> 1;
  if ( v10 <= 0xFFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v12 = v11 + v10;
    v13 = v9;
    if ( v12 >= v9 )
      v13 = v12;
    if ( v13 > 0xFFFFFFFFFFFFFFFLL )
      __scrt_throw_std_bad_array_new_length();
    v3 = v13;
  }
  _mm_lfence();
  v25[2] = v3;
  v25[0] = a1;
  v14 = std::_Allocate<16,std::_Default_allocate_traits>(16 * v3, v11, a3);
  v15 = (_QWORD *)((v4 & 0xFFFFFFFFFFFFFFF0uLL) + v14);
  *v15 = 0;
  v16 = v15 + 2;
  v15[1] = 0;
  *v15 = *a3;
  v17 = (_QWORD *)v14;
  v15[1] = a3[1];
  *a3 = 0;
  a3[1] = 0;
  v18 = (_QWORD *)a1[1];
  v19 = (_QWORD *)*a1;
  v27 = v15 + 2;
  v26 = v15;
  if ( v7 == v18 )
  {
    while ( v19 != v18 )
    {
      *v17 = 0;
      v17[1] = 0;
      *v17 = *v19;
      v17[1] = v19[1];
      v17 += 2;
      *v19 = 0;
      v19[1] = 0;
      v19 += 2;
    }
    v20 = v17;
  }
  else
  {
    while ( v19 != v7 )
    {
      *v17 = 0;
      v17[1] = 0;
      *v17 = *v19;
      v17[1] = v19[1];
      v17 += 2;
      *v19 = 0;
      v19[1] = 0;
      v19 += 2;
    }
    std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(v17, v17);
    v21 = (_QWORD *)a1[1];
    v26 = (_QWORD *)v14;
    while ( v7 != v21 )
    {
      *v16 = 0;
      v16[1] = 0;
      *v16 = *v7;
      v16[1] = v7[1];
      v16 += 2;
      *v7 = 0;
      v7[1] = 0;
      v7 += 2;
    }
    v20 = v16;
    v17 = v16;
  }
  std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(v17, v20);
  v22 = (_QWORD *)*a1;
  v25[1] = 0;
  if ( v22 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(v22, a1[1]);
    v23 = (_QWORD *)*a1;
    if ( ((a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
    {
      _mm_lfence();
      if ( (unsigned __int64)v23 - *(v23 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v23 = (_QWORD *)*(v23 - 1);
    }
    operator delete(v23);
  }
  _mm_lfence();
  *a1 = v14;
  a1[1] = v14 + 16 * v9;
  a1[2] = v14 + 16 * v3;
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Reallocation_guard::~_Reallocation_guard(v25);
  return v15;
}

```

## disassembly

```asm
0x14000da28  mov     [rsp+arg_18], rbx
0x14000da2d  push    rbp
0x14000da2e  push    rsi
0x14000da2f  push    rdi
0x14000da30  push    r12
0x14000da32  push    r13
0x14000da34  push    r14
0x14000da36  push    r15
0x14000da38  sub     rsp, 60h
0x14000da3c  mov     rbp, [rcx+8]
0x14000da40  mov     rsi, rdx
0x14000da43  sub     rbp, [rcx]
0x14000da46  mov     r15, 0FFFFFFFFFFFFFFFh
0x14000da50  sub     rsi, [rcx]
0x14000da53  mov     r13, r8
0x14000da56  sar     rbp, 4
0x14000da5a  mov     rbx, rdx
0x14000da5d  mov     rdi, rcx
0x14000da60  cmp     rbp, r15
0x14000da63  jz      loc_14000DC5C
0x14000da69  mov     rcx, [rcx+10h]
0x14000da6d  mov     rax, r15
0x14000da70  sub     rcx, [rdi]
0x14000da73  inc     rbp
0x14000da76  sar     rcx, 4
0x14000da7a  mov     rdx, rcx
0x14000da7d  shr     rdx, 1
0x14000da80  sub     rax, rdx
0x14000da83  cmp     rcx, rax
0x14000da86  ja      short loc_14000DAA2
0x14000da88  lea     rax, [rdx+rcx]
0x14000da8c  mov     rcx, rbp
0x14000da8f  cmp     rax, rbp
0x14000da92  cmovnb  rcx, rax
0x14000da96  cmp     rcx, r15
0x14000da99  ja      loc_14000DC56
0x14000da9f  mov     r15, rcx
0x14000daa2  lfence
0x14000daa5  mov     rax, r15
0x14000daa8  shl     rax, 4
0x14000daac  mov     rcx, rax
0x14000daaf  mov     [rsp+98h+var_68], rax
0x14000dab4  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14000dab9  and     rsi, 0FFFFFFFFFFFFFFF0h
0x14000dabd  mov     [rsp+98h+var_50], r15
0x14000dac2  xor     r15d, r15d
0x14000dac5  mov     [rsp+98h+var_60], rdi
0x14000daca  mov     r14, rax
0x14000dacd  lea     r12, [rsi+rax]
0x14000dad1  mov     [r12], r15
0x14000dad5  lea     rsi, [r12+10h]
0x14000dada  mov     [r12+8], r15
0x14000dadf  mov     rcx, [r13+0]
0x14000dae3  mov     [r12], rcx
0x14000dae7  mov     rcx, r14
0x14000daea  mov     rax, [r13+8]
0x14000daee  mov     [r12+8], rax
0x14000daf3  mov     [r13+0], r15
0x14000daf7  mov     [r13+8], r15
0x14000dafb  mov     r8, [rdi+8]
0x14000daff  mov     rdx, [rdi]
0x14000db02  mov     [rsp+98h+var_40], rsi
0x14000db07  mov     [rsp+98h+var_48], r12
0x14000db0c  cmp     rbx, r8
0x14000db0f  jnz     short loc_14000DB65
0x14000db11  jmp     short loc_14000DB37
0x14000db13  mov     [rcx], r15
0x14000db16  mov     [rcx+8], r15
0x14000db1a  mov     rax, [rdx]
0x14000db1d  mov     [rcx], rax
0x14000db20  mov     rax, [rdx+8]
0x14000db24  mov     [rcx+8], rax
0x14000db28  add     rcx, 10h
0x14000db2c  mov     [rdx], r15
0x14000db2f  mov     [rdx+8], r15
0x14000db33  add     rdx, 10h
0x14000db37  cmp     rdx, r8
0x14000db3a  jnz     short loc_14000DB13
0x14000db3c  mov     rdx, rcx
0x14000db3f  jmp     short loc_14000DBAC
0x14000db41  mov     [rcx], r15
0x14000db44  mov     [rcx+8], r15
0x14000db48  mov     rax, [rdx]
0x14000db4b  mov     [rcx], rax
0x14000db4e  mov     rax, [rdx+8]
0x14000db52  mov     [rcx+8], rax
0x14000db56  add     rcx, 10h
0x14000db5a  mov     [rdx], r15
0x14000db5d  mov     [rdx+8], r15
0x14000db61  add     rdx, 10h
0x14000db65  cmp     rdx, rbx
0x14000db68  jnz     short loc_14000DB41
0x14000db6a  mov     rdx, rcx
0x14000db6d  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(std::shared_ptr<DiagHubCommon::ILogWriter> *,std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>> &)
0x14000db72  mov     rcx, [rdi+8]
0x14000db76  mov     [rsp+98h+var_48], r14
0x14000db7b  jmp     short loc_14000DBA1
0x14000db7d  mov     [rsi], r15
0x14000db80  mov     [rsi+8], r15
0x14000db84  mov     rax, [rbx]
0x14000db87  mov     [rsi], rax
0x14000db8a  mov     rax, [rbx+8]
0x14000db8e  mov     [rsi+8], rax
0x14000db92  add     rsi, 10h
0x14000db96  mov     [rbx], r15
0x14000db99  mov     [rbx+8], r15
0x14000db9d  add     rbx, 10h
0x14000dba1  cmp     rbx, rcx
0x14000dba4  jnz     short loc_14000DB7D
0x14000dba6  mov     rdx, rsi
0x14000dba9  mov     rcx, rsi
0x14000dbac  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(std::shared_ptr<DiagHubCommon::ILogWriter> *,std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>> &)
0x14000dbb1  mov     rcx, [rdi]
0x14000dbb4  mov     [rsp+98h+var_58], r15
0x14000dbb9  test    rcx, rcx
0x14000dbbc  jz      short loc_14000DBFE
0x14000dbbe  mov     rdx, [rdi+8]
0x14000dbc2  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(std::shared_ptr<DiagHubCommon::ILogWriter> *,std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>> &)
0x14000dbc7  mov     rcx, [rdi]
0x14000dbca  mov     rdx, [rdi+10h]
0x14000dbce  sub     rdx, rcx
0x14000dbd1  and     rdx, 0FFFFFFFFFFFFFFF0h
0x14000dbd5  cmp     rdx, 1000h
0x14000dbdc  jb      short loc_14000DBF9
0x14000dbde  lfence
0x14000dbe1  mov     rax, [rcx-8]
0x14000dbe5  add     rdx, 27h ; '''
0x14000dbe9  sub     rcx, rax
0x14000dbec  sub     rcx, 8
0x14000dbf0  cmp     rcx, 1Fh
0x14000dbf4  ja      short loc_14000DC40
0x14000dbf6  mov     rcx, rax; Block
0x14000dbf9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000dbfe  lfence
0x14000dc01  mov     rcx, [rsp+98h+var_68]
0x14000dc06  mov     [rdi], r14
0x14000dc09  add     rcx, r14
0x14000dc0c  shl     rbp, 4
0x14000dc10  add     rbp, r14
0x14000dc13  mov     [rdi+8], rbp
0x14000dc17  mov     [rdi+10h], rcx
0x14000dc1b  lea     rcx, [rsp+98h+var_60]
0x14000dc20  call    ??1_Reallocation_guard@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Reallocation_guard::~_Reallocation_guard(void)
0x14000dc25  mov     rbx, [rsp+98h+arg_18]
0x14000dc2d  mov     rax, r12
0x14000dc30  add     rsp, 60h
0x14000dc34  pop     r15
0x14000dc36  pop     r14
0x14000dc38  pop     r13
0x14000dc3a  pop     r12
0x14000dc3c  pop     rdi
0x14000dc3d  pop     rsi
0x14000dc3e  pop     rbp
0x14000dc3f  retn
0x14000dc40  xor     r9d, r9d; LineNo
0x14000dc43  mov     [rsp+98h+Reserved], r15; Reserved
0x14000dc48  xor     r8d, r8d; FileName
0x14000dc4b  xor     edx, edx; FunctionName
0x14000dc4d  xor     ecx, ecx; Expression
0x14000dc4f  call    cs:__imp__invoke_watson
0x14000dc56  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x14000dc5c  call    ?_Xlength@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@CAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Xlength(void)
```
