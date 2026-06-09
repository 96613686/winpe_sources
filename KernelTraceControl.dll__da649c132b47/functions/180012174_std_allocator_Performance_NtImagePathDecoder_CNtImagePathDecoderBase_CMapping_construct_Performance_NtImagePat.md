# std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::construct(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)

- ea: `0x180012174`
- end: `0x180012202`
- name: `?construct@?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@QEAAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@AEBU3456@@Z`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001210c`
- `0x180012204`

## callees

- `0x180012174`
- `0x180013934`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_UNKNOWN **__fastcall std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::construct(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _UNKNOWN **result; // rax
  _UNKNOWN *retaddr; // [rsp+38h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a2 )
  {
    *(_QWORD *)(a2 + 32) = 7;
    *(_QWORD *)(a2 + 24) = 0;
    *(_WORD *)(a2 + 8) = 0;
    std::wstring::assign(a2, a3, 0, -1);
    *(_QWORD *)(a2 + 72) = 7;
    *(_QWORD *)(a2 + 64) = 0;
    *(_WORD *)(a2 + 48) = 0;
    return (_UNKNOWN **)std::wstring::assign(a2 + 40, a3 + 40, 0, -1);
  }
  return result;
}

```

## disassembly

```asm
0x180012174  mov     rax, rsp
0x180012177  mov     [rax+8], rcx
0x18001217b  push    r14
0x18001217d  sub     rsp, 30h
0x180012181  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x180012189  mov     [rax+18h], rbx
0x18001218d  mov     [rax+20h], rdi
0x180012191  mov     rdi, r8
0x180012194  mov     rbx, rdx
0x180012197  mov     [rax+8], rdx
0x18001219b  mov     [rax+10h], rdx
0x18001219f  xor     r14d, r14d
0x1800121a2  test    rdx, rdx
0x1800121a5  jz      short loc_1800121F1
0x1800121a7  mov     qword ptr [rdx+20h], 7
0x1800121af  mov     [rdx+18h], r14
0x1800121b3  mov     [rdx+8], r14w
0x1800121b8  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800121bc  xor     r8d, r8d
0x1800121bf  mov     rdx, rdi
0x1800121c2  mov     rcx, rbx
0x1800121c5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800121ca  nop
0x1800121cb  lea     rcx, [rbx+28h]
0x1800121cf  mov     qword ptr [rcx+20h], 7
0x1800121d7  mov     [rcx+18h], r14
0x1800121db  mov     [rcx+8], r14w
0x1800121e0  lea     rdx, [rdi+28h]
0x1800121e4  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800121e8  xor     r8d, r8d
0x1800121eb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800121f0  nop
0x1800121f1  mov     rbx, [rsp+38h+arg_10]
0x1800121f6  mov     rdi, [rsp+38h+arg_18]
0x1800121fb  add     rsp, 30h
0x1800121ff  pop     r14
0x180012201  retn
```
