# std::deque<std::thread,std::allocator<std::thread>>::_Emplace_back_internal<std::thread>(std::thread &&)

- ea: `0x18003cdcc`
- end: `0x18003cff1`
- name: `??$_Emplace_back_internal@Vthread@std@@@?$deque@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@AEAAX$$QEAVthread@1@@Z`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003b61c`

## callees

- `0x180009e14`
- `0x180009f84`
- `0x180016284`
- `0x18003cdcc`
- `0x18004a03c`
- `0x18004a078`

## import_xrefs

- `VCRUNTIME140!memset` at `0x18003cecb`
- `VCRUNTIME140!memset` at `0x18003cf0e`
- `VCRUNTIME140!memset` at `0x18003cecb`
- `VCRUNTIME140!memset` at `0x18003cf0e`
- `VCRUNTIME140!memmove` at `0x18003ce9a`
- `VCRUNTIME140!memmove` at `0x18003ceb5`
- `VCRUNTIME140!memmove` at `0x18003cee4`
- `VCRUNTIME140!memmove` at `0x18003ceff`
- `VCRUNTIME140!memmove` at `0x18003ce9a`
- `VCRUNTIME140!memmove` at `0x18003ceb5`
- `VCRUNTIME140!memmove` at `0x18003cee4`
- `VCRUNTIME140!memmove` at `0x18003ceff`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18003cfde`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18003cfde`

## pseudocode

```c
__int64 __fastcall std::deque<std::thread>::_Emplace_back_internal<std::thread>(_QWORD *a1, __int128 *a2)
{
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // r14
  unsigned __int64 v6; // rdi
  __int64 v7; // r15
  char *v8; // r12
  unsigned __int64 v9; // rcx
  char *v10; // rbp
  __int64 v11; // rax
  unsigned __int64 v12; // r14
  size_t v13; // rbx
  char *v14; // rbp
  const void *v15; // rdx
  size_t v16; // r8
  char *v17; // rcx
  _QWORD *v18; // rcx
  __int64 v19; // rdi
  __int64 v20; // rdi
  __int64 v21; // rbx
  __int64 result; // rax
  __int128 v23; // xmm1
  _OWORD *v24; // rdx

  v4 = a1[2];
  if ( v4 <= a1[4] + 1LL )
  {
    v5 = 1;
    if ( v4 )
      v5 = v4;
    while ( v5 == v4 || v5 < 8 )
    {
      if ( 0xFFFFFFFFFFFFFFFLL - v5 < v5 )
        std::deque<ATL::CComPtr<ITraceEvent>>::_Xlen();
      v5 *= 2LL;
    }
    v6 = a1[3];
    if ( v5 > 0x1FFFFFFFFFFFFFFFLL )
      __scrt_throw_std_bad_array_new_length();
    _mm_lfence();
    v7 = 8 * v6;
    v8 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(8 * v5);
    v9 = v5 >> 1;
    v10 = &v8[8 * v6];
    while ( v5 <= v9 )
      v5 *= 2LL;
    v11 = a1[2];
    v12 = v5 - v11;
    v13 = 8 * v11 - v7;
    memmove(v10, (const void *)(a1[1] + v7), v13);
    v14 = &v10[v13];
    _mm_lfence();
    v15 = (const void *)a1[1];
    if ( v6 > v12 )
    {
      memmove(v14, v15, 8 * v12);
      memmove(v8, (const void *)(8 * v12 + a1[1]), v7 - 8 * v12);
      v17 = &v8[v7 - 8 * v12];
      v16 = 8 * v12;
    }
    else
    {
      memmove(v14, v15, 8 * v6);
      memset(&v14[v7], 0, 8 * (v12 - v6));
      v16 = 8 * v6;
      v17 = v8;
    }
    memset(v17, 0, v16);
    v18 = (_QWORD *)a1[1];
    if ( v18 )
    {
      if ( (unsigned __int64)(8LL * a1[2]) >= 0x1000 )
      {
        if ( (unsigned __int64)v18 - *(v18 - 1) - 8 > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
        v18 = (_QWORD *)*(v18 - 1);
      }
      operator delete(v18);
    }
    a1[1] = v8;
    a1[2] += v12;
    v4 = a1[2];
  }
  v19 = a1[4];
  a1[3] &= v4 - 1;
  v20 = a1[3] + v19;
  v21 = v20 & (v4 - 1);
  if ( !*(_QWORD *)(a1[1] + 8 * v21) )
    *(_QWORD *)(a1[1] + 8 * v21) = operator new(0x10u);
  result = a1[1];
  v23 = *a2;
  v24 = *(_OWORD **)(result + 8 * (v20 & (a1[2] - 1LL)));
  *a2 = 0;
  *v24 = v23;
  ++a1[4];
  return result;
}

```

## disassembly

```asm
0x18003cdcc  mov     [rsp+arg_10], rbx
0x18003cdd1  push    rbp
0x18003cdd2  push    rsi
0x18003cdd3  push    rdi
0x18003cdd4  push    r12
0x18003cdd6  push    r13
0x18003cdd8  push    r14
0x18003cdda  push    r15
0x18003cddc  sub     rsp, 30h
0x18003cde0  mov     rsi, rcx
0x18003cde3  mov     r13, rdx
0x18003cde6  mov     rcx, [rcx+10h]
0x18003cdea  mov     rax, [rsi+20h]
0x18003cdee  inc     rax
0x18003cdf1  cmp     rcx, rax
0x18003cdf4  ja      loc_18003CF5B
0x18003cdfa  test    rcx, rcx
0x18003cdfd  mov     r14d, 1
0x18003ce03  cmovnz  r14, rcx
0x18003ce07  mov     rax, r14
0x18003ce0a  sub     rax, rcx
0x18003ce0d  cmp     rax, 1
0x18003ce11  jb      short loc_18003CE19
0x18003ce13  cmp     r14, 8
0x18003ce17  jnb     short loc_18003CE34
0x18003ce19  mov     rax, 0FFFFFFFFFFFFFFFh
0x18003ce23  sub     rax, r14
0x18003ce26  cmp     rax, r14
0x18003ce29  jb      loc_18003CFEB
0x18003ce2f  add     r14, r14
0x18003ce32  jmp     short loc_18003CE07
0x18003ce34  mov     rdi, [rsi+18h]
0x18003ce38  mov     rax, 1FFFFFFFFFFFFFFFh
0x18003ce42  cmp     r14, rax
0x18003ce45  ja      loc_18003CFE5
0x18003ce4b  lfence
0x18003ce4e  lea     rcx, ds:0[r14*8]
0x18003ce56  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003ce5b  lea     r15, ds:0[rdi*8]
0x18003ce63  mov     rcx, r14
0x18003ce66  mov     r12, rax
0x18003ce69  shr     rcx, 1
0x18003ce6c  lea     rbp, [r15+rax]
0x18003ce70  jmp     short loc_18003CE75
0x18003ce72  add     r14, r14
0x18003ce75  cmp     r14, rcx
0x18003ce78  jbe     short loc_18003CE72
0x18003ce7a  mov     rcx, [rsi+8]
0x18003ce7e  mov     rax, [rsi+10h]
0x18003ce82  sub     r14, rax
0x18003ce85  shl     rax, 3
0x18003ce89  lea     rdx, [rcx+r15]; Src
0x18003ce8d  sub     rax, rdx
0x18003ce90  lea     rbx, [rax+rcx]
0x18003ce94  mov     rcx, rbp; void *
0x18003ce97  mov     r8, rbx; Size
0x18003ce9a  call    cs:__imp_memmove
0x18003cea0  add     rbp, rbx
0x18003cea3  lfence
0x18003cea6  mov     rdx, [rsi+8]; Src
0x18003ceaa  mov     rcx, rbp; void *
0x18003cead  cmp     rdi, r14
0x18003ceb0  ja      short loc_18003CED9
0x18003ceb2  mov     r8, r15; Size
0x18003ceb5  call    cs:__imp_memmove
0x18003cebb  mov     r8, r14
0x18003cebe  lea     rcx, [r15+rbp]; void *
0x18003cec2  sub     r8, rdi
0x18003cec5  xor     edx, edx; Val
0x18003cec7  shl     r8, 3; Size
0x18003cecb  call    cs:__imp_memset
0x18003ced1  mov     r8, r15
0x18003ced4  mov     rcx, r12
0x18003ced7  jmp     short loc_18003CF0C
0x18003ced9  lea     rdi, ds:0[r14*8]
0x18003cee1  mov     r8, rdi; Size
0x18003cee4  call    cs:__imp_memmove
0x18003ceea  mov     rax, [rsi+8]
0x18003ceee  mov     rcx, r12; void *
0x18003cef1  lea     rdx, [rdi+rax]; Src
0x18003cef5  sub     rax, rdx
0x18003cef8  lea     rbx, [rax+r15]
0x18003cefc  mov     r8, rbx; Size
0x18003ceff  call    cs:__imp_memmove
0x18003cf05  lea     rcx, [r12+rbx]; void *
0x18003cf09  mov     r8, rdi; Size
0x18003cf0c  xor     edx, edx; Val
0x18003cf0e  call    cs:__imp_memset
0x18003cf14  mov     rcx, [rsi+8]
0x18003cf18  test    rcx, rcx
0x18003cf1b  jz      short loc_18003CF4F
0x18003cf1d  mov     rdx, [rsi+10h]
0x18003cf21  shl     rdx, 3
0x18003cf25  cmp     rdx, 1000h
0x18003cf2c  jb      short loc_18003CF4A
0x18003cf2e  mov     rax, [rcx-8]
0x18003cf32  add     rdx, 27h ; '''
0x18003cf36  sub     rcx, rax
0x18003cf39  sub     rcx, 8
0x18003cf3d  cmp     rcx, 1Fh
0x18003cf41  ja      loc_18003CFCB
0x18003cf47  mov     rcx, rax; Block
0x18003cf4a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003cf4f  mov     [rsi+8], r12
0x18003cf53  add     [rsi+10h], r14
0x18003cf57  mov     rcx, [rsi+10h]
0x18003cf5b  mov     rdi, [rsi+20h]
0x18003cf5f  lea     rbx, [rcx-1]
0x18003cf63  and     [rsi+18h], rbx
0x18003cf67  add     rdi, [rsi+18h]
0x18003cf6b  mov     rax, [rsi+8]
0x18003cf6f  and     rbx, rdi
0x18003cf72  cmp     qword ptr [rax+rbx*8], 0
0x18003cf77  jnz     short loc_18003CF8B
0x18003cf79  mov     ecx, 10h; Size
0x18003cf7e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003cf83  mov     rcx, [rsi+8]
0x18003cf87  mov     [rcx+rbx*8], rax
0x18003cf8b  mov     rcx, [rsi+10h]
0x18003cf8f  xorps   xmm0, xmm0
0x18003cf92  mov     rax, [rsi+8]
0x18003cf96  dec     rcx
0x18003cf99  movups  xmm1, xmmword ptr [r13+0]
0x18003cf9e  mov     rbx, [rsp+68h+arg_10]
0x18003cfa6  and     rcx, rdi
0x18003cfa9  mov     rdx, [rax+rcx*8]
0x18003cfad  movdqu  xmmword ptr [r13+0], xmm0
0x18003cfb3  movdqu  xmmword ptr [rdx], xmm1
0x18003cfb7  inc     qword ptr [rsi+20h]
0x18003cfbb  add     rsp, 30h
0x18003cfbf  pop     r15
0x18003cfc1  pop     r14
0x18003cfc3  pop     r13
0x18003cfc5  pop     r12
0x18003cfc7  pop     rdi
0x18003cfc8  pop     rsi
0x18003cfc9  pop     rbp
0x18003cfca  retn
0x18003cfcb  xor     r9d, r9d; LineNo
0x18003cfce  mov     [rsp+68h+Reserved], 0; Reserved
0x18003cfd7  xor     r8d, r8d; FileName
0x18003cfda  xor     edx, edx; FunctionName
0x18003cfdc  xor     ecx, ecx; Expression
0x18003cfde  call    cs:__imp__invoke_watson
0x18003cfe5  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18003cfeb  call    ?_Xlen@?$deque@V?$CComPtr@UITraceEvent@@@ATL@@V?$allocator@V?$CComPtr@UITraceEvent@@@ATL@@@std@@@std@@CAXXZ; std::deque<ATL::CComPtr<ITraceEvent>>::_Xlen(void)
```
