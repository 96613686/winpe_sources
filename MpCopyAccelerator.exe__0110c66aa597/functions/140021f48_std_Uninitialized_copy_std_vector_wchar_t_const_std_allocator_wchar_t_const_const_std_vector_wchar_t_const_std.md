# std::_Uninitialized_copy<std::vector<wchar_t const *,std::allocator<wchar_t const *>> const *,std::vector<wchar_t const *,std::allocator<wchar_t const *>> const *,std::allocator<std::vector<wchar_t const *,std::allocator<wchar_t const *>>>>(std::vector<wchar_t const *,std::allocator<wchar_t const *>> const *,std::vector<wchar_t const *,std::allocator<wchar_t const *>> const *,std::vector<wchar_t const *,std::allocator<wchar_t const *>> *,std::allocator<std::vector<wchar_t const *,std::allocator<wchar_t const *>>> &)

- ea: `0x140021f48`
- end: `0x140022063`
- name: `??$_Uninitialized_copy@PEBV?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@PEBV12@V?$allocator@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@2@@std@@YAPEAV?$vector@PEB_WV?$allocator@PEB_W@std@@@0@PEBV10@0PEAV10@AEAV?$allocator@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@0@@Z`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140022138`

## callees

- `0x140005da0`
- `0x140020454`
- `0x140021f48`
- `0x1400221f4`
- `0x140022db0`
- `0x140025080`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Uninitialized_copy<std::vector<wchar_t const *> const *,std::vector<wchar_t const *> const *,std::allocator<std::vector<wchar_t const *>>>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4)
{
  _QWORD *v4; // rdi
  __int64 v6; // rsi
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rbx
  char *v9; // r14
  size_t v10; // rcx
  char *v11; // rax
  signed __int64 v12; // rbx
  _QWORD v14[2]; // [rsp+20h] [rbp-38h] BYREF
  _QWORD *v15; // [rsp+30h] [rbp-28h]
  __int64 i; // [rsp+38h] [rbp-20h]

  v4 = a3;
  v6 = a1;
  v14[1] = a3;
  v15 = a3;
  for ( i = a4; v6 != a2; v6 += 24 )
  {
    *v4 = 0;
    v4[1] = 0;
    v4[2] = 0;
    v7 = (__int64)(*(_QWORD *)(v6 + 8) - *(_QWORD *)v6) >> 3;
    if ( v7 )
    {
      if ( v7 > 0x1FFFFFFFFFFFFFFFLL )
        std::vector<std::vector<wchar_t const *>>::_Xlength();
      v8 = 8 * v7;
      if ( 8 * v7 )
      {
        _mm_lfence();
        v10 = 8 * v7;
        if ( v8 < 0x1000 )
          v11 = (char *)operator new(v10);
        else
          v11 = (char *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v10);
        v9 = v11;
      }
      else
      {
        v9 = 0;
      }
      *v4 = v9;
      v4[1] = v9;
      v4[2] = &v9[v8];
      v12 = *(_QWORD *)(v6 + 8) - *(_QWORD *)v6;
      memmove(v9, *(const void **)v6, v12);
      v4[1] = &v9[8 * (v12 >> 3)];
      v14[0] = 0;
      std::_Tidy_guard<std::vector<wchar_t const *>>::~_Tidy_guard<std::vector<wchar_t const *>>(v14);
    }
    v4 += 3;
    v15 = v4;
  }
  return v4;
}

```

## disassembly

```asm
0x140021f48  mov     rax, rsp
0x140021f4b  mov     [rax+10h], rbx
0x140021f4f  mov     [rax+18h], rbp
0x140021f53  push    rsi
0x140021f54  push    rdi
0x140021f55  push    r14
0x140021f57  sub     rsp, 40h
0x140021f5b  mov     rdi, r8
0x140021f5e  mov     rbp, rdx
0x140021f61  mov     rsi, rcx
0x140021f64  xorps   xmm0, xmm0
0x140021f67  movups  xmmword ptr [rax-30h], xmm0
0x140021f6b  mov     [rax-30h], r8
0x140021f6f  mov     [rax-28h], r8
0x140021f73  mov     [rax-20h], r9
0x140021f77  cmp     rcx, rdx
0x140021f7a  jz      loc_140022047
0x140021f80  mov     qword ptr [rdi], 0
0x140021f87  mov     qword ptr [rdi+8], 0
0x140021f8f  mov     qword ptr [rdi+10h], 0
0x140021f97  mov     rax, [rsi+8]
0x140021f9b  sub     rax, [rsi]
0x140021f9e  sar     rax, 3
0x140021fa2  test    rax, rax
0x140021fa5  jz      loc_140022031
0x140021fab  mov     rcx, 1FFFFFFFFFFFFFFFh
0x140021fb5  cmp     rax, rcx
0x140021fb8  ja      loc_14002205D
0x140021fbe  lea     rbx, ds:0[rax*8]
0x140021fc6  test    rbx, rbx
0x140021fc9  jnz     short loc_140021FD0
0x140021fcb  xor     r14d, r14d
0x140021fce  jmp     short loc_140021FEE
0x140021fd0  lfence
0x140021fd3  mov     rcx, rbx; Size
0x140021fd6  cmp     rbx, 1000h
0x140021fdd  jb      short loc_140021FE6
0x140021fdf  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x140021fe4  jmp     short loc_140021FEB
0x140021fe6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140021feb  mov     r14, rax
0x140021fee  mov     [rdi], r14
0x140021ff1  mov     [rdi+8], r14
0x140021ff5  lea     rax, [rbx+r14]
0x140021ff9  mov     [rdi+10h], rax
0x140021ffd  mov     rbx, [rsi+8]
0x140022001  sub     rbx, [rsi]
0x140022004  mov     r8, rbx; Size
0x140022007  mov     rdx, [rsi]; Src
0x14002200a  mov     rcx, r14; void *
0x14002200d  call    memmove
0x140022012  sar     rbx, 3
0x140022016  lea     rax, [r14+rbx*8]
0x14002201a  mov     [rdi+8], rax
0x14002201e  mov     [rsp+58h+var_38], 0
0x140022027  lea     rcx, [rsp+58h+var_38]
0x14002202c  call    ??1?$_Tidy_guard@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<wchar_t const *>>::~_Tidy_guard<std::vector<wchar_t const *>>(void)
0x140022031  add     rdi, 18h
0x140022035  mov     [rsp+58h+var_28], rdi
0x14002203a  add     rsi, 18h
0x14002203e  cmp     rsi, rbp
0x140022041  jnz     loc_140021F80
0x140022047  mov     rax, rdi
0x14002204a  mov     rbx, [rsp+58h+arg_8]
0x14002204f  mov     rbp, [rsp+58h+arg_10]
0x140022054  add     rsp, 40h
0x140022058  pop     r14
0x14002205a  pop     rdi
0x14002205b  pop     rsi
0x14002205c  retn
0x14002205d  call    ?_Xlength@?$vector@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@V?$allocator@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@2@@std@@CAXXZ; std::vector<std::vector<wchar_t const *>>::_Xlength(void)
```
