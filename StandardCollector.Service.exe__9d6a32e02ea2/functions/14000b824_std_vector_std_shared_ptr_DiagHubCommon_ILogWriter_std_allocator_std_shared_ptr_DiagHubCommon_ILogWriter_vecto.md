# std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>> const &)

- ea: `0x14000b824`
- end: `0x14000b8fb`
- name: `??0?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@AEBV01@@Z`
- size: `215`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a298`
- `0x14000a42c`
- `0x14000f728`

## callees

- `0x140002330`
- `0x140003494`
- `0x14000b824`
- `0x14000d9b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  unsigned __int64 v5; // rsi
  size_t v6; // rsi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _QWORD *v9; // r8
  _QWORD *i; // rdx
  __int64 v11; // rax

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v5 = (__int64)(a2[1] - *a2) >> 4;
  if ( v5 )
  {
    if ( v5 > 0xFFFFFFFFFFFFFFFLL )
      std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Xlength(a1, a2, a3);
    _mm_lfence();
    v6 = 2 * v5;
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(v6 * 8);
    *a1 = v7;
    v8 = v7;
    a1[1] = v7;
    a1[2] = &v7[v6];
    v9 = (_QWORD *)a2[1];
    for ( i = (_QWORD *)*a2; i != v9; i += 2 )
    {
      *v8 = 0;
      v8[1] = 0;
      v11 = i[1];
      if ( v11 )
        _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
      *v8 = *i;
      v8[1] = i[1];
      v8 += 2;
    }
    std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>((__int64)v8, (__int64)v8);
    a1[1] = v8;
  }
  return a1;
}

```

## disassembly

```asm
0x14000b824  mov     [rsp+arg_10], rbx
0x14000b829  push    rsi
0x14000b82a  push    rdi
0x14000b82b  push    r14
0x14000b82d  sub     rsp, 20h
0x14000b831  mov     qword ptr [rcx], 0
0x14000b838  mov     r14, rdx
0x14000b83b  mov     qword ptr [rcx+8], 0
0x14000b843  mov     rdi, rcx
0x14000b846  mov     qword ptr [rcx+10h], 0
0x14000b84e  mov     rsi, [rdx+8]
0x14000b852  sub     rsi, [rdx]
0x14000b855  sar     rsi, 4
0x14000b859  test    rsi, rsi
0x14000b85c  jz      loc_14000B8E4
0x14000b862  mov     rax, 0FFFFFFFFFFFFFFFh
0x14000b86c  cmp     rsi, rax
0x14000b86f  ja      loc_14000B8F5
0x14000b875  lfence
0x14000b878  shl     rsi, 4
0x14000b87c  mov     rcx, rsi
0x14000b87f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14000b884  mov     [rdi], rax
0x14000b887  mov     rbx, rax
0x14000b88a  mov     [rdi+8], rax
0x14000b88e  add     rax, rsi
0x14000b891  mov     [rdi+10h], rax
0x14000b895  mov     r8, [r14+8]
0x14000b899  mov     rdx, [r14]
0x14000b89c  jmp     short loc_14000B8D0
0x14000b89e  mov     qword ptr [rbx], 0
0x14000b8a5  mov     qword ptr [rbx+8], 0
0x14000b8ad  mov     rax, [rdx+8]
0x14000b8b1  test    rax, rax
0x14000b8b4  jz      short loc_14000B8BA
0x14000b8b6  lock inc dword ptr [rax+8]
0x14000b8ba  mov     rax, [rdx]
0x14000b8bd  mov     [rbx], rax
0x14000b8c0  mov     rcx, [rdx+8]
0x14000b8c4  mov     [rbx+8], rcx
0x14000b8c8  add     rbx, 10h
0x14000b8cc  add     rdx, 10h
0x14000b8d0  cmp     rdx, r8
0x14000b8d3  jnz     short loc_14000B89E
0x14000b8d5  mov     rdx, rbx
0x14000b8d8  mov     rcx, rbx
0x14000b8db  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(std::shared_ptr<DiagHubCommon::ILogWriter> *,std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>> &)
0x14000b8e0  mov     [rdi+8], rbx
0x14000b8e4  mov     rbx, [rsp+38h+arg_10]
0x14000b8e9  mov     rax, rdi
0x14000b8ec  add     rsp, 20h
0x14000b8f0  pop     r14
0x14000b8f2  pop     rdi
0x14000b8f3  pop     rsi
0x14000b8f4  retn
0x14000b8f5  call    ?_Xlength@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@CAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Xlength(void)
```
