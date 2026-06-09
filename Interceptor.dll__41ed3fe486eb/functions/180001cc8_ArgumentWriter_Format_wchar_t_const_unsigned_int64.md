# ArgumentWriter::Format(wchar_t const *,unsigned __int64)

- ea: `0x180001cc8`
- end: `0x180001dae`
- name: `?Format@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_K@Z`
- size: `230`
- prototype: ``
- caller_count: `15`
- callee_count: `4`
- tags: ``

## callers

- `0x180003a80`
- `0x180003b14`
- `0x180005c70`
- `0x180005e18`
- `0x18000635c`
- `0x180007e04`
- `0x1800084e8`
- `0x180008958`
- `0x180008bf0`
- `0x1800091e0`
- `0x180021c54`
- `0x180021cec`
- `0x180021d84`
- `0x180021eec`
- `0x1800220fc`

## callees

- `0x180001cc8`
- `0x180001db0`
- `0x1800041d4`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180001d81`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180001d81`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180001d88`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180001d88`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ArgumentWriter::Format(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdi
  void *v6; // rcx
  void *Block[2]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v9; // [rsp+50h] [rbp-38h]
  unsigned __int64 v10; // [rsp+58h] [rbp-30h]

  *(_OWORD *)Block = 0;
  v9 = 0;
  v10 = 7;
  LOWORD(Block[0]) = 0;
  v5 = 2 * a3;
  if ( (unsigned __int64)(2 * a3) > 7 )
  {
    _mm_lfence();
    ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_K_Z___V___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(Block);
    v9 = 0;
  }
  ArgumentWriter::FormatArguments(a1, a2, v5 + a2, Block);
  if ( v10 > 7 )
  {
    v6 = Block[0];
    if ( 2 * v10 + 2 >= 0x1000 )
    {
      v6 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v6 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v6);
  }
  return a1;
}

```

## disassembly

```asm
0x180001cc8  mov     r11, rsp
0x180001ccb  mov     [r11+20h], rbx
0x180001ccf  push    rbp
0x180001cd0  push    rsi
0x180001cd1  push    rdi
0x180001cd2  sub     rsp, 70h
0x180001cd6  mov     rax, cs:__security_cookie
0x180001cdd  xor     rax, rsp
0x180001ce0  mov     [rsp+88h+var_28], rax
0x180001ce5  mov     rsi, rdx
0x180001ce8  mov     rbx, rcx
0x180001ceb  mov     [rsp+88h+var_50], rcx
0x180001cf0  xor     ebp, ebp
0x180001cf2  xorps   xmm0, xmm0
0x180001cf5  movups  xmmword ptr [rsp+88h+Block], xmm0
0x180001cfa  mov     [r11-38h], rbp
0x180001cfe  mov     qword ptr [r11-30h], 7
0x180001d06  mov     word ptr [rsp+88h+Block], bp
0x180001d0b  lea     rdi, [r8+r8]
0x180001d0f  cmp     rdi, 7
0x180001d13  jbe     short loc_180001D29
0x180001d15  lfence
0x180001d18  mov     rdx, rdi
0x180001d1b  lea     rcx, [r11-48h]; Src
0x180001d1f  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x180001d24  mov     [rsp+88h+var_38], rbp
0x180001d29  lea     r8, [rdi+rsi]
0x180001d2d  lea     r9, [rsp+88h+Block]
0x180001d32  mov     rdx, rsi
0x180001d35  mov     rcx, rbx
0x180001d38  call    ?FormatArguments@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV23@@Z; ArgumentWriter::FormatArguments(wchar_t const *,wchar_t const *,std::wstring &)
0x180001d3d  nop
0x180001d3e  mov     rax, [rsp+88h+var_30]
0x180001d43  cmp     rax, 7
0x180001d47  jbe     short loc_180001D8E
0x180001d49  mov     rcx, [rsp+88h+Block]; Block
0x180001d4e  mov     rdx, rcx
0x180001d51  lea     rax, ds:2[rax*2]
0x180001d59  cmp     rax, 1000h
0x180001d5f  jb      short loc_180001D88
0x180001d61  mov     rcx, [rcx-8]
0x180001d65  sub     rdx, rcx
0x180001d68  lea     rax, [rdx-8]
0x180001d6c  cmp     rax, 1Fh
0x180001d70  jbe     short loc_180001D88
0x180001d72  mov     [rsp+88h+Reserved], rbp; Reserved
0x180001d77  xor     r9d, r9d; LineNo
0x180001d7a  xor     r8d, r8d; FileName
0x180001d7d  xor     edx, edx; FunctionName
0x180001d7f  xor     ecx, ecx; Expression
0x180001d81  call    cs:__imp__invoke_watson
0x180001d88  call    cs:__imp_free
0x180001d8e  mov     rax, rbx
0x180001d91  mov     rcx, [rsp+88h+var_28]
0x180001d96  xor     rcx, rsp; StackCookie
0x180001d99  call    __security_check_cookie
0x180001d9e  mov     rbx, [rsp+88h+arg_18]
0x180001da6  add     rsp, 70h
0x180001daa  pop     rdi
0x180001dab  pop     rsi
0x180001dac  pop     rbp
0x180001dad  retn
```
