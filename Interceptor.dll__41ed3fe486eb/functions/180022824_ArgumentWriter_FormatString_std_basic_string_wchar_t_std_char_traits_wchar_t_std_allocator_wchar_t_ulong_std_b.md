# ArgumentWriter::FormatString<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180022824`
- end: `0x18002291c`
- name: `??$FormatString@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@@ArgumentWriter@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WAEBV12@AEBK1@Z`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180022194`

## callees

- `0x1800041d4`
- `0x180022824`
- `0x180023028`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800228f1`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800228f1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800228f8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800228f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ArgumentWriter::FormatString<std::wstring,unsigned long,std::wstring>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v9; // rdx
  void *v10; // rcx
  void *Block[2]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v13; // [rsp+60h] [rbp-48h]
  unsigned __int64 v14; // [rsp+68h] [rbp-40h]

  *(_OWORD *)Block = 0;
  v13 = 0;
  v14 = 7;
  LOWORD(Block[0]) = 0;
  _mm_lfence();
  ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_K_Z___V___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(Block);
  v13 = 0;
  ArgumentWriter::FormatArguments<std::wstring,unsigned long,std::wstring>(a1, v9, L"", Block, a3, a4, a5);
  if ( v14 > 7 )
  {
    v10 = Block[0];
    if ( 2 * v14 + 2 >= 0x1000 )
    {
      v10 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v10 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v10);
  }
  return a1;
}

```

## disassembly

```asm
0x180022824  mov     r11, rsp
0x180022827  push    rbx
0x180022828  push    rbp
0x180022829  push    rsi
0x18002282a  push    rdi
0x18002282b  push    r14
0x18002282d  sub     rsp, 80h
0x180022834  mov     rax, cs:__security_cookie
0x18002283b  xor     rax, rsp
0x18002283e  mov     [rsp+0A8h+var_38], rax
0x180022843  mov     rsi, r9
0x180022846  mov     rdi, r8
0x180022849  mov     rbp, rcx
0x18002284c  mov     [rsp+0A8h+var_60], rcx
0x180022851  mov     rbx, [rsp+0A8h+arg_20]
0x180022859  xor     r14d, r14d
0x18002285c  xorps   xmm0, xmm0
0x18002285f  movups  xmmword ptr [rsp+0A8h+Block], xmm0
0x180022864  mov     [r11-48h], r14
0x180022868  mov     qword ptr [r11-40h], 7
0x180022870  mov     [r11-58h], r14w
0x180022875  lfence
0x180022878  lea     edx, [r14+16h]
0x18002287c  lea     rcx, [r11-58h]; Src
0x180022880  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x180022885  mov     [rsp+0A8h+var_48], r14
0x18002288a  mov     [rsp+0A8h+var_78], rbx
0x18002288f  mov     [rsp+0A8h+var_80], rsi
0x180022894  mov     [rsp+0A8h+Reserved], rdi
0x180022899  lea     r9, [rsp+0A8h+Block]
0x18002289e  lea     r8, aSDS+16h; ""
0x1800228a5  mov     rcx, rbp
0x1800228a8  call    ??$FormatArguments@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBV12@AEBK2@Z; ArgumentWriter::FormatArguments<std::wstring,ulong,std::wstring>(wchar_t const *,wchar_t const *,std::wstring &,std::wstring const &,ulong const &,std::wstring const &)
0x1800228ad  nop
0x1800228ae  mov     rax, [rsp+0A8h+var_40]
0x1800228b3  cmp     rax, 7
0x1800228b7  jbe     short loc_1800228FE
0x1800228b9  mov     rcx, [rsp+0A8h+Block]; Block
0x1800228be  mov     rdx, rcx
0x1800228c1  lea     rax, ds:2[rax*2]
0x1800228c9  cmp     rax, 1000h
0x1800228cf  jb      short loc_1800228F8
0x1800228d1  mov     rcx, [rcx-8]
0x1800228d5  sub     rdx, rcx
0x1800228d8  lea     rax, [rdx-8]
0x1800228dc  cmp     rax, 1Fh
0x1800228e0  jbe     short loc_1800228F8
0x1800228e2  mov     [rsp+0A8h+Reserved], r14; Reserved
0x1800228e7  xor     r9d, r9d; LineNo
0x1800228ea  xor     r8d, r8d; FileName
0x1800228ed  xor     edx, edx; FunctionName
0x1800228ef  xor     ecx, ecx; Expression
0x1800228f1  call    cs:__imp__invoke_watson
0x1800228f8  call    cs:__imp_free
0x1800228fe  mov     rax, rbp
0x180022901  mov     rcx, [rsp+0A8h+var_38]
0x180022906  xor     rcx, rsp; StackCookie
0x180022909  call    __security_check_cookie
0x18002290e  add     rsp, 80h
0x180022915  pop     r14
0x180022917  pop     rdi
0x180022918  pop     rsi
0x180022919  pop     rbp
0x18002291a  pop     rbx
0x18002291b  retn
```
