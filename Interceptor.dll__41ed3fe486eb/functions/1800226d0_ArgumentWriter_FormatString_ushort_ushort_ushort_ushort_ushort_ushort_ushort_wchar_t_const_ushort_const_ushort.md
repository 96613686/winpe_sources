# ArgumentWriter::FormatString<ushort,ushort,ushort,ushort,ushort,ushort,ushort>(wchar_t const *,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &)

- ea: `0x1800226d0`
- end: `0x180022824`
- name: `??$FormatString@GGGGGGG@ArgumentWriter@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WAEBG111111@Z`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180020c88`

## callees

- `0x1800041d4`
- `0x1800226d0`
- `0x180022e00`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800227e9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800227e9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800227f0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800227f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ArgumentWriter::FormatString<unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v17; // rdx
  void *v18; // rcx
  void *Block[2]; // [rsp+70h] [rbp-68h] BYREF
  __int64 v21; // [rsp+80h] [rbp-58h]
  unsigned __int64 v22; // [rsp+88h] [rbp-50h]

  *(_OWORD *)Block = 0;
  v21 = 0;
  v22 = 7;
  LOWORD(Block[0]) = 0;
  _mm_lfence();
  ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_K_Z___V___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(Block);
  v21 = 0;
  ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
    a1,
    v17,
    L"",
    Block,
    a3,
    a4,
    a5,
    a6,
    a7,
    a8,
    a9);
  if ( v22 > 7 )
  {
    v18 = Block[0];
    if ( 2 * v22 + 2 >= 0x1000 )
    {
      v18 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v18 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v18);
  }
  return a1;
}

```

## disassembly

```asm
0x1800226d0  mov     r11, rsp
0x1800226d3  mov     [r11+10h], rbx
0x1800226d7  push    rbp
0x1800226d8  push    rsi
0x1800226d9  push    rdi
0x1800226da  push    r12
0x1800226dc  push    r13
0x1800226de  push    r14
0x1800226e0  push    r15
0x1800226e2  sub     rsp, 0A0h
0x1800226e9  mov     rax, cs:__security_cookie
0x1800226f0  xor     rax, rsp
0x1800226f3  mov     [rsp+0D8h+var_48], rax
0x1800226fb  mov     r12, r9
0x1800226fe  mov     r15, r8
0x180022701  mov     r13, rcx
0x180022704  mov     [rsp+0D8h+var_70], rcx
0x180022709  mov     r14, [rsp+0D8h+arg_20]
0x180022711  mov     rbp, [rsp+0D8h+arg_28]
0x180022719  mov     rsi, [rsp+0D8h+arg_30]
0x180022721  mov     rdi, [rsp+0D8h+arg_38]
0x180022729  mov     rbx, [rsp+0D8h+arg_40]
0x180022731  xor     eax, eax
0x180022733  xorps   xmm0, xmm0
0x180022736  movups  xmmword ptr [rsp+0D8h+Block], xmm0
0x18002273b  mov     [r11-58h], rax
0x18002273f  mov     qword ptr [r11-50h], 7
0x180022747  mov     word ptr [rsp+0D8h+Block], ax
0x18002274c  lfence
0x18002274f  lea     edx, [rax+44h]
0x180022752  lea     rcx, [r11-68h]; Src
0x180022756  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x18002275b  mov     [rsp+0D8h+var_58], 0
0x180022767  mov     [rsp+0D8h+var_88], rbx
0x18002276c  mov     [rsp+0D8h+var_90], rdi
0x180022771  mov     [rsp+0D8h+var_98], rsi
0x180022776  mov     [rsp+0D8h+var_A0], rbp
0x18002277b  mov     [rsp+0D8h+var_A8], r14
0x180022780  mov     [rsp+0D8h+var_B0], r12
0x180022785  mov     [rsp+0D8h+Reserved], r15
0x18002278a  lea     r9, [rsp+0D8h+Block]
0x18002278f  lea     r8, a04d02d02d02d02+44h; ""
0x180022796  mov     rcx, r13
0x180022799  call    ??$FormatArguments@GGGGGGG@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG222222@Z; ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort,ushort,ushort,ushort>(wchar_t const *,wchar_t const *,std::wstring &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &)
0x18002279e  nop
0x18002279f  mov     rax, [rsp+0D8h+var_50]
0x1800227a7  cmp     rax, 7
0x1800227ab  jbe     short loc_1800227F6
0x1800227ad  mov     rcx, [rsp+0D8h+Block]; Block
0x1800227b2  mov     rdx, rcx
0x1800227b5  lea     rax, ds:2[rax*2]
0x1800227bd  cmp     rax, 1000h
0x1800227c3  jb      short loc_1800227F0
0x1800227c5  mov     rcx, [rcx-8]
0x1800227c9  sub     rdx, rcx
0x1800227cc  lea     rax, [rdx-8]
0x1800227d0  cmp     rax, 1Fh
0x1800227d4  jbe     short loc_1800227F0
0x1800227d6  mov     [rsp+0D8h+Reserved], 0; Reserved
0x1800227df  xor     r9d, r9d; LineNo
0x1800227e2  xor     r8d, r8d; FileName
0x1800227e5  xor     edx, edx; FunctionName
0x1800227e7  xor     ecx, ecx; Expression
0x1800227e9  call    cs:__imp__invoke_watson
0x1800227f0  call    cs:__imp_free
0x1800227f6  mov     rax, r13
0x1800227f9  mov     rcx, [rsp+0D8h+var_48]
0x180022801  xor     rcx, rsp; StackCookie
0x180022804  call    __security_check_cookie
0x180022809  mov     rbx, [rsp+0D8h+arg_8]
0x180022811  add     rsp, 0A0h
0x180022818  pop     r15
0x18002281a  pop     r14
0x18002281c  pop     r13
0x18002281e  pop     r12
0x180022820  pop     rdi
0x180022821  pop     rsi
0x180022822  pop     rbp
0x180022823  retn
```
