# ArgumentWriter::FormatString<ushort,ushort,ushort,ushort,ushort,ushort,ulong>(wchar_t const *,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ulong const &)

- ea: `0x18002291c`
- end: `0x180022a70`
- name: `??$FormatString@GGGGGGK@ArgumentWriter@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WAEBG11111AEBK@Z`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180022290`

## callees

- `0x1800041d4`
- `0x18002291c`
- `0x180023280`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180022a35`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180022a35`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180022a3c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180022a3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ArgumentWriter::FormatString<unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned long>(
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
  ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned long>(
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
0x18002291c  mov     r11, rsp
0x18002291f  mov     [r11+10h], rbx
0x180022923  push    rbp
0x180022924  push    rsi
0x180022925  push    rdi
0x180022926  push    r12
0x180022928  push    r13
0x18002292a  push    r14
0x18002292c  push    r15
0x18002292e  sub     rsp, 0A0h
0x180022935  mov     rax, cs:__security_cookie
0x18002293c  xor     rax, rsp
0x18002293f  mov     [rsp+0D8h+var_48], rax
0x180022947  mov     r12, r9
0x18002294a  mov     r15, r8
0x18002294d  mov     r13, rcx
0x180022950  mov     [rsp+0D8h+var_70], rcx
0x180022955  mov     r14, [rsp+0D8h+arg_20]
0x18002295d  mov     rbp, [rsp+0D8h+arg_28]
0x180022965  mov     rsi, [rsp+0D8h+arg_30]
0x18002296d  mov     rdi, [rsp+0D8h+arg_38]
0x180022975  mov     rbx, [rsp+0D8h+arg_40]
0x18002297d  xor     eax, eax
0x18002297f  xorps   xmm0, xmm0
0x180022982  movups  xmmword ptr [rsp+0D8h+Block], xmm0
0x180022987  mov     [r11-58h], rax
0x18002298b  mov     qword ptr [r11-50h], 7
0x180022993  mov     word ptr [rsp+0D8h+Block], ax
0x180022998  lfence
0x18002299b  lea     edx, [rax+34h]
0x18002299e  lea     rcx, [r11-68h]; Src
0x1800229a2  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x1800229a7  mov     [rsp+0D8h+var_58], 0
0x1800229b3  mov     [rsp+0D8h+var_88], rbx
0x1800229b8  mov     [rsp+0D8h+var_90], rdi
0x1800229bd  mov     [rsp+0D8h+var_98], rsi
0x1800229c2  mov     [rsp+0D8h+var_A0], rbp
0x1800229c7  mov     [rsp+0D8h+var_A8], r14
0x1800229cc  mov     [rsp+0D8h+var_B0], r12
0x1800229d1  mov     [rsp+0D8h+Reserved], r15
0x1800229d6  lea     r9, [rsp+0D8h+Block]
0x1800229db  lea     r8, a04d02d02d02d02_0+34h; ""
0x1800229e2  mov     rcx, r13
0x1800229e5  call    ??$FormatArguments@GGGGGGK@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG22222AEBK@Z; ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort,ushort,ushort,ulong>(wchar_t const *,wchar_t const *,std::wstring &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ulong const &)
0x1800229ea  nop
0x1800229eb  mov     rax, [rsp+0D8h+var_50]
0x1800229f3  cmp     rax, 7
0x1800229f7  jbe     short loc_180022A42
0x1800229f9  mov     rcx, [rsp+0D8h+Block]; Block
0x1800229fe  mov     rdx, rcx
0x180022a01  lea     rax, ds:2[rax*2]
0x180022a09  cmp     rax, 1000h
0x180022a0f  jb      short loc_180022A3C
0x180022a11  mov     rcx, [rcx-8]
0x180022a15  sub     rdx, rcx
0x180022a18  lea     rax, [rdx-8]
0x180022a1c  cmp     rax, 1Fh
0x180022a20  jbe     short loc_180022A3C
0x180022a22  mov     [rsp+0D8h+Reserved], 0; Reserved
0x180022a2b  xor     r9d, r9d; LineNo
0x180022a2e  xor     r8d, r8d; FileName
0x180022a31  xor     edx, edx; FunctionName
0x180022a33  xor     ecx, ecx; Expression
0x180022a35  call    cs:__imp__invoke_watson
0x180022a3c  call    cs:__imp_free
0x180022a42  mov     rax, r13
0x180022a45  mov     rcx, [rsp+0D8h+var_48]
0x180022a4d  xor     rcx, rsp; StackCookie
0x180022a50  call    __security_check_cookie
0x180022a55  mov     rbx, [rsp+0D8h+arg_8]
0x180022a5d  add     rsp, 0A0h
0x180022a64  pop     r15
0x180022a66  pop     r14
0x180022a68  pop     r13
0x180022a6a  pop     r12
0x180022a6c  pop     rdi
0x180022a6d  pop     rsi
0x180022a6e  pop     rbp
0x180022a6f  retn
```
