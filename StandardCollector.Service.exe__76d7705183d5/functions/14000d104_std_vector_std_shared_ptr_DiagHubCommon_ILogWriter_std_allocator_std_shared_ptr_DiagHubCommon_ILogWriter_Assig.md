# std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>::_Assign_counted_range<std::shared_ptr<DiagHubCommon::ILogWriter> *>(std::shared_ptr<DiagHubCommon::ILogWriter> *,unsigned __int64)

- ea: `0x14000d104`
- end: `0x14000d303`
- name: `??$_Assign_counted_range@PEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@1@_K@Z`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a42c`

## callees

- `0x14000d104`
- `0x14000d9b0`
- `0x14000dec8`
- `0x140014c70`

## pseudocode

```c
__int64 __fastcall std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Assign_counted_range<std::shared_ptr<DiagHubCommon::ILogWriter> *>(
        __int64 *a1,
        char *a2,
        unsigned __int64 a3)
{
  char *v3; // rsi
  unsigned __int64 v4; // rdi
  char *v5; // r14
  char *v7; // rbx
  _QWORD *v8; // r14
  __int64 v9; // rax
  char *v10; // rdx
  unsigned __int64 v11; // rbp
  _QWORD *v12; // rbp
  volatile signed __int32 *v13; // r14
  __int64 v14; // rcx
  __int64 result; // rax
  __int64 v16; // rax
  volatile signed __int32 *v17; // rbx
  __int64 v18; // rcx
  unsigned __int64 v19; // rdi
  _QWORD *v20; // rcx
  signed __int64 v21; // rdx

  v3 = (char *)*a1;
  v4 = a3;
  v5 = a2;
  if ( a3 > (a1[2] - *a1) >> 4 )
  {
    _mm_lfence();
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Clear_and_reserve_geometric(a1, a3, a3);
    v7 = (char *)*a1;
    if ( v4 )
    {
      v8 = v5 + 8;
      do
      {
        *(_QWORD *)v7 = 0;
        *((_QWORD *)v7 + 1) = 0;
        if ( *v8 )
          _InterlockedIncrement((volatile signed __int32 *)(*v8 + 8LL));
        *(_QWORD *)v7 = *(v8 - 1);
        v9 = *v8;
        v8 += 2;
        *((_QWORD *)v7 + 1) = v9;
        v7 += 16;
        --v4;
      }
      while ( v4 );
    }
LABEL_7:
    v10 = v7;
    goto LABEL_19;
  }
  v7 = (char *)a1[1];
  v11 = (v7 - v3) >> 4;
  if ( a3 > v11 )
  {
    while ( v3 != v7 )
    {
      v16 = *((_QWORD *)v5 + 1);
      if ( v16 )
        _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
      v17 = (volatile signed __int32 *)*((_QWORD *)v3 + 1);
      v18 = *((_QWORD *)v5 + 1);
      *(_QWORD *)v3 = *(_QWORD *)v5;
      *((_QWORD *)v3 + 1) = v18;
      if ( v17 )
      {
        if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        }
      }
      v7 = (char *)a1[1];
      v3 += 16;
      v5 += 16;
    }
    v19 = v4 - v11;
    if ( v19 )
    {
      v20 = v5 + 8;
      v21 = v7 - v5;
      do
      {
        *(_QWORD *)v7 = 0;
        *(_QWORD *)((char *)v20 + v21) = 0;
        if ( *v20 )
          _InterlockedIncrement((volatile signed __int32 *)(*v20 + 8LL));
        *(_QWORD *)v7 = *(v20 - 1);
        v7 += 16;
        *(_QWORD *)((char *)v20 + v21) = *v20;
        v20 += 2;
        --v19;
      }
      while ( v19 );
    }
    goto LABEL_7;
  }
  _mm_lfence();
  v7 = &v3[16 * a3];
  if ( a3 )
  {
    v12 = a2 + 8;
    do
    {
      if ( *v12 )
        _InterlockedIncrement((volatile signed __int32 *)(*v12 + 8LL));
      v13 = (volatile signed __int32 *)*((_QWORD *)v3 + 1);
      v14 = *v12;
      *(_QWORD *)v3 = *(v12 - 1);
      *((_QWORD *)v3 + 1) = v14;
      if ( v13 )
      {
        if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
      v3 += 16;
      v12 += 2;
      --v4;
    }
    while ( v4 );
  }
  v10 = (char *)a1[1];
LABEL_19:
  result = std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(v7, v10);
  a1[1] = (__int64)v7;
  return result;
}

```

## disassembly

```asm
0x14000d104  mov     [rsp+arg_18], rbx
0x14000d109  push    rbp
0x14000d10a  push    rsi
0x14000d10b  push    rdi
0x14000d10c  push    r12
0x14000d10e  push    r14
0x14000d110  sub     rsp, 20h
0x14000d114  mov     rsi, [rcx]
0x14000d117  mov     rdi, r8
0x14000d11a  mov     rax, [rcx+10h]
0x14000d11e  mov     r14, rdx
0x14000d121  sub     rax, rsi
0x14000d124  mov     r12, rcx
0x14000d127  sar     rax, 4
0x14000d12b  cmp     r8, rax
0x14000d12e  jbe     short loc_14000D187
0x14000d130  lfence
0x14000d133  mov     rdx, r8
0x14000d136  call    ?_Clear_and_reserve_geometric@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAX_K@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Clear_and_reserve_geometric(unsigned __int64)
0x14000d13b  mov     rbx, [r12]
0x14000d13f  test    rdi, rdi
0x14000d142  jz      short loc_14000D17F
0x14000d144  add     r14, 8
0x14000d148  mov     qword ptr [rbx], 0
0x14000d14f  mov     qword ptr [rbx+8], 0
0x14000d157  mov     rax, [r14]
0x14000d15a  test    rax, rax
0x14000d15d  jz      short loc_14000D163
0x14000d15f  lock inc dword ptr [rax+8]
0x14000d163  mov     rax, [r14-8]
0x14000d167  mov     [rbx], rax
0x14000d16a  mov     rax, [r14]
0x14000d16d  add     r14, 10h
0x14000d171  mov     [rbx+8], rax
0x14000d175  add     rbx, 10h
0x14000d179  sub     rdi, 1
0x14000d17d  jnz     short loc_14000D148
0x14000d17f  mov     rdx, rbx
0x14000d182  jmp     loc_14000D227
0x14000d187  mov     rbx, [rcx+8]
0x14000d18b  mov     rbp, rbx
0x14000d18e  sub     rbp, rsi
0x14000d191  sar     rbp, 4
0x14000d195  cmp     rdi, rbp
0x14000d198  ja      loc_14000D2AF
0x14000d19e  lfence
0x14000d1a1  mov     rbx, rdi
0x14000d1a4  shl     rbx, 4
0x14000d1a8  add     rbx, rsi
0x14000d1ab  test    rdi, rdi
0x14000d1ae  jz      short loc_14000D222
0x14000d1b0  lea     rbp, [rdx+8]
0x14000d1b4  mov     rax, [rbp+0]
0x14000d1b8  test    rax, rax
0x14000d1bb  jz      short loc_14000D1C1
0x14000d1bd  lock inc dword ptr [rax+8]
0x14000d1c1  mov     r14, [rsi+8]
0x14000d1c5  mov     rcx, [rbp+0]
0x14000d1c9  mov     rax, [rbp-8]
0x14000d1cd  mov     [rsi], rax
0x14000d1d0  mov     [rsi+8], rcx
0x14000d1d4  test    r14, r14
0x14000d1d7  jz      short loc_14000D214
0x14000d1d9  or      eax, 0FFFFFFFFh
0x14000d1dc  lock xadd [r14+8], eax
0x14000d1e2  cmp     eax, 1
0x14000d1e5  jnz     short loc_14000D214
0x14000d1e7  mov     rax, [r14]
0x14000d1ea  mov     rcx, r14
0x14000d1ed  mov     rax, [rax]
0x14000d1f0  call    cs:__guard_dispatch_icall_fptr
0x14000d1f6  or      eax, 0FFFFFFFFh
0x14000d1f9  lock xadd [r14+0Ch], eax
0x14000d1ff  cmp     eax, 1
0x14000d202  jnz     short loc_14000D214
0x14000d204  mov     rax, [r14]
0x14000d207  mov     rcx, r14
0x14000d20a  mov     rax, [rax+8]
0x14000d20e  call    cs:__guard_dispatch_icall_fptr
0x14000d214  add     rsi, 10h
0x14000d218  add     rbp, 10h
0x14000d21c  sub     rdi, 1
0x14000d220  jnz     short loc_14000D1B4
0x14000d222  mov     rdx, [r12+8]
0x14000d227  mov     rcx, rbx
0x14000d22a  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(std::shared_ptr<DiagHubCommon::ILogWriter> *,std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>> &)
0x14000d22f  mov     [r12+8], rbx
0x14000d234  mov     rbx, [rsp+48h+arg_18]
0x14000d239  add     rsp, 20h
0x14000d23d  pop     r14
0x14000d23f  pop     r12
0x14000d241  pop     rdi
0x14000d242  pop     rsi
0x14000d243  pop     rbp
0x14000d244  retn
0x14000d245  mov     rax, [r14+8]
0x14000d249  test    rax, rax
0x14000d24c  jz      short loc_14000D252
0x14000d24e  lock inc dword ptr [rax+8]
0x14000d252  mov     rbx, [rsi+8]
0x14000d256  mov     rcx, [r14+8]
0x14000d25a  mov     rax, [r14]
0x14000d25d  mov     [rsi], rax
0x14000d260  mov     [rsi+8], rcx
0x14000d264  test    rbx, rbx
0x14000d267  jz      short loc_14000D2A2
0x14000d269  or      eax, 0FFFFFFFFh
0x14000d26c  lock xadd [rbx+8], eax
0x14000d271  cmp     eax, 1
0x14000d274  jnz     short loc_14000D2A2
0x14000d276  mov     rax, [rbx]
0x14000d279  mov     rcx, rbx
0x14000d27c  mov     rax, [rax]
0x14000d27f  call    cs:__guard_dispatch_icall_fptr
0x14000d285  or      eax, 0FFFFFFFFh
0x14000d288  lock xadd [rbx+0Ch], eax
0x14000d28d  cmp     eax, 1
0x14000d290  jnz     short loc_14000D2A2
0x14000d292  mov     rax, [rbx]
0x14000d295  mov     rcx, rbx
0x14000d298  mov     rax, [rax+8]
0x14000d29c  call    cs:__guard_dispatch_icall_fptr
0x14000d2a2  mov     rbx, [r12+8]
0x14000d2a7  add     rsi, 10h
0x14000d2ab  add     r14, 10h
0x14000d2af  cmp     rsi, rbx
0x14000d2b2  jnz     short loc_14000D245
0x14000d2b4  sub     rdi, rbp
0x14000d2b7  jz      loc_14000D17F
0x14000d2bd  mov     rdx, rbx
0x14000d2c0  lea     rcx, [r14+8]
0x14000d2c4  sub     rdx, r14
0x14000d2c7  mov     qword ptr [rbx], 0
0x14000d2ce  mov     qword ptr [rdx+rcx], 0
0x14000d2d6  mov     rax, [rcx]
0x14000d2d9  test    rax, rax
0x14000d2dc  jz      short loc_14000D2E2
0x14000d2de  lock inc dword ptr [rax+8]
0x14000d2e2  mov     rax, [rcx-8]
0x14000d2e6  mov     [rbx], rax
0x14000d2e9  add     rbx, 10h
0x14000d2ed  mov     rax, [rcx]
0x14000d2f0  mov     [rdx+rcx], rax
0x14000d2f4  add     rcx, 10h
0x14000d2f8  sub     rdi, 1
0x14000d2fc  jnz     short loc_14000D2C7
0x14000d2fe  jmp     loc_14000D17F
```
