# ArgumentWriter::Format<wchar_t [64]>(wchar_t const *,unsigned __int64,wchar_t const (&)[64])

- ea: `0x180008c48`
- end: `0x180008d31`
- name: `??$Format@$$BY0EA@_W@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_KAEAY0EA@$$CB_W@Z`
- size: `233`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180007da8`
- `0x180008038`
- `0x180008198`

## callees

- `0x1800041d4`
- `0x180008c48`
- `0x180009244`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180008d09`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180008d09`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180008d10`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180008d10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall ArgumentWriter::Format<wchar_t [64]>(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4)
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
  ArgumentWriter::FormatArguments<wchar_t [64],>(a1, a2, &a2[v7], Block, a4);
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
0x180008c48  mov     r11, rsp
0x180008c4b  push    rbx
0x180008c4c  push    rbp
0x180008c4d  push    rsi
0x180008c4e  push    rdi
0x180008c4f  push    r14
0x180008c51  sub     rsp, 70h
0x180008c55  mov     rax, cs:__security_cookie
0x180008c5c  xor     rax, rsp
0x180008c5f  mov     [rsp+98h+var_38], rax
0x180008c64  mov     rbp, r9
0x180008c67  mov     rsi, rdx
0x180008c6a  mov     rbx, rcx
0x180008c6d  mov     [rsp+98h+var_60], rcx
0x180008c72  xor     r14d, r14d
0x180008c75  xorps   xmm0, xmm0
0x180008c78  movups  xmmword ptr [rsp+98h+Block], xmm0
0x180008c7d  mov     [r11-48h], r14
0x180008c81  mov     qword ptr [r11-40h], 7
0x180008c89  mov     [r11-58h], r14w
0x180008c8e  lea     rdi, [r8+r8]
0x180008c92  cmp     rdi, 7
0x180008c96  jbe     short loc_180008CAC
0x180008c98  lfence
0x180008c9b  mov     rdx, rdi
0x180008c9e  lea     rcx, [r11-58h]; Src
0x180008ca2  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x180008ca7  mov     [rsp+98h+var_48], r14
0x180008cac  lea     r8, [rdi+rsi]
0x180008cb0  mov     [rsp+98h+Reserved], rbp
0x180008cb5  lea     r9, [rsp+98h+Block]
0x180008cba  mov     rdx, rsi
0x180008cbd  mov     rcx, rbx
0x180008cc0  call    ??$FormatArguments@$$BY0EA@_W$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEAY0EA@$$CB_W@Z; ArgumentWriter::FormatArguments<wchar_t [64],>(wchar_t const *,wchar_t const *,std::wstring &,wchar_t const (&)[64])
0x180008cc5  nop
0x180008cc6  mov     rax, [rsp+98h+var_40]
0x180008ccb  cmp     rax, 7
0x180008ccf  jbe     short loc_180008D16
0x180008cd1  mov     rcx, [rsp+98h+Block]; Block
0x180008cd6  mov     rdx, rcx
0x180008cd9  lea     rax, ds:2[rax*2]
0x180008ce1  cmp     rax, 1000h
0x180008ce7  jb      short loc_180008D10
0x180008ce9  mov     rcx, [rcx-8]
0x180008ced  sub     rdx, rcx
0x180008cf0  lea     rax, [rdx-8]
0x180008cf4  cmp     rax, 1Fh
0x180008cf8  jbe     short loc_180008D10
0x180008cfa  mov     [rsp+98h+Reserved], r14; Reserved
0x180008cff  xor     r9d, r9d; LineNo
0x180008d02  xor     r8d, r8d; FileName
0x180008d05  xor     edx, edx; FunctionName
0x180008d07  xor     ecx, ecx; Expression
0x180008d09  call    cs:__imp__invoke_watson
0x180008d10  call    cs:__imp_free
0x180008d16  mov     rax, rbx
0x180008d19  mov     rcx, [rsp+98h+var_38]
0x180008d1e  xor     rcx, rsp; StackCookie
0x180008d21  call    __security_check_cookie
0x180008d26  add     rsp, 70h
0x180008d2a  pop     r14
0x180008d2c  pop     rdi
0x180008d2d  pop     rsi
0x180008d2e  pop     rbp
0x180008d2f  pop     rbx
0x180008d30  retn
```
