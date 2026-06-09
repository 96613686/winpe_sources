# ArgumentWriter::Format<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(wchar_t const *,unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800048a8`
- end: `0x180004991`
- name: `??$Format@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_KAEBV12@@Z`
- size: `233`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180003bb0`
- `0x1800063f4`
- `0x180021610`
- `0x180021e20`

## callees

- `0x1800041d4`
- `0x1800048a8`
- `0x180004b58`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004969`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004969`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004970`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004970`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 ArgumentWriter::Format<std::wstring>(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        __int64 a3,
        _QWORD *a4,
        ...)
{
  __int64 v7; // rdi
  void *v8; // rcx
  void *Block[2]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v11; // [rsp+50h] [rbp-48h]
  unsigned __int64 v12; // [rsp+58h] [rbp-40h]

  *(_OWORD *)Block = 0;
  v11 = 0;
  v12 = 7;
  LOWORD(Block[0]) = 0;
  v7 = a3;
  if ( (unsigned __int64)(2 * a3) > 7 )
  {
    _mm_lfence();
    ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_K_Z___V___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(Block);
    v11 = 0;
  }
  ArgumentWriter::FormatArguments<std::wstring,>(a1, a2, &a2[v7], Block, a4);
  if ( v12 > 7 )
  {
    v8 = Block[0];
    if ( 2 * v12 + 2 >= 0x1000 )
    {
      v8 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v8 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v8);
  }
  return a1;
}

```

## disassembly

```asm
0x1800048a8  mov     r11, rsp
0x1800048ab  push    rbx
0x1800048ac  push    rbp
0x1800048ad  push    rsi
0x1800048ae  push    rdi
0x1800048af  push    r14
0x1800048b1  sub     rsp, 70h
0x1800048b5  mov     rax, cs:__security_cookie
0x1800048bc  xor     rax, rsp
0x1800048bf  mov     [rsp+98h+var_38], rax
0x1800048c4  mov     rbp, r9
0x1800048c7  mov     rsi, rdx
0x1800048ca  mov     rbx, rcx
0x1800048cd  mov     [rsp+98h+var_60], rcx
0x1800048d2  xor     r14d, r14d
0x1800048d5  xorps   xmm0, xmm0
0x1800048d8  movups  xmmword ptr [rsp+98h+Block], xmm0
0x1800048dd  mov     [r11-48h], r14
0x1800048e1  mov     qword ptr [r11-40h], 7
0x1800048e9  mov     [r11-58h], r14w
0x1800048ee  lea     rdi, [r8+r8]
0x1800048f2  cmp     rdi, 7
0x1800048f6  jbe     short loc_18000490C
0x1800048f8  lfence
0x1800048fb  mov     rdx, rdi
0x1800048fe  lea     rcx, [r11-58h]; Src
0x180004902  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x180004907  mov     [rsp+98h+var_48], r14
0x18000490c  lea     r8, [rdi+rsi]
0x180004910  mov     [rsp+98h+Reserved], rbp
0x180004915  lea     r9, [rsp+98h+Block]
0x18000491a  mov     rdx, rsi
0x18000491d  mov     rcx, rbx
0x180004920  call    ??$FormatArguments@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBV12@@Z; ArgumentWriter::FormatArguments<std::wstring,>(wchar_t const *,wchar_t const *,std::wstring &,std::wstring const &)
0x180004925  nop
0x180004926  mov     rax, [rsp+98h+var_40]
0x18000492b  cmp     rax, 7
0x18000492f  jbe     short loc_180004976
0x180004931  mov     rcx, [rsp+98h+Block]; Block
0x180004936  mov     rdx, rcx
0x180004939  lea     rax, ds:2[rax*2]
0x180004941  cmp     rax, 1000h
0x180004947  jb      short loc_180004970
0x180004949  mov     rcx, [rcx-8]
0x18000494d  sub     rdx, rcx
0x180004950  lea     rax, [rdx-8]
0x180004954  cmp     rax, 1Fh
0x180004958  jbe     short loc_180004970
0x18000495a  mov     [rsp+98h+Reserved], r14; Reserved
0x18000495f  xor     r9d, r9d; LineNo
0x180004962  xor     r8d, r8d; FileName
0x180004965  xor     edx, edx; FunctionName
0x180004967  xor     ecx, ecx; Expression
0x180004969  call    cs:__imp__invoke_watson
0x180004970  call    cs:__imp_free
0x180004976  mov     rax, rbx
0x180004979  mov     rcx, [rsp+98h+var_38]
0x18000497e  xor     rcx, rsp; StackCookie
0x180004981  call    __security_check_cookie
0x180004986  add     rsp, 70h
0x18000498a  pop     r14
0x18000498c  pop     rdi
0x18000498d  pop     rsi
0x18000498e  pop     rbp
0x18000498f  pop     rbx
0x180004990  retn
```
