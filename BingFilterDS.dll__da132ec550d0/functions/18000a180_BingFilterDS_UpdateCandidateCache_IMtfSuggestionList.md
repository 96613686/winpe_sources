# BingFilterDS::UpdateCandidateCache(IMtfSuggestionList *)

- ea: `0x18000a180`
- end: `0x18000a435`
- name: `?UpdateCandidateCache@BingFilterDS@@IEAAXPEAUIMtfSuggestionList@@@Z`
- size: `693`
- prototype: `void __fastcall(BingFilterDS *__hidden this, struct IMtfSuggestionList *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180009250`

## callees

- `0x18000a180`
- `0x18000ab4c`
- `0x18000ac8c`
- `0x18000ad10`
- `0x18000e010`

## string_xrefs

- `0x18000a417`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall BingFilterDS::UpdateCandidateCache(BingFilterDS *this, struct IMtfSuggestionList *a2)
{
  int v2; // eax
  unsigned int v3; // r8d
  const char *v4; // r9
  __int64 v5; // [rsp+0h] [rbp-58h] BYREF
  int v6[14]; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  try
  {
    v2 = (*(__int64 (**)(void))(*(_QWORD *)a2 + 24LL))();
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CB,
        (int)"mincore\\textinput\\dev\\mtf\\datasources\\bingfilterds\\lib\\bingfilterds.cpp",
        (const char *)(unsigned int)v2,
        v6[0]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, &v5, v3, v4);
  }
}

```

## disassembly

```asm
0x18000a180  mov     [rsp+arg_0], rbx
0x18000a185  push    rsi
0x18000a186  push    rdi
0x18000a187  push    r13
0x18000a189  push    r14
0x18000a18b  push    r15
0x18000a18d  sub     rsp, 30h
0x18000a191  mov     r15, rdx
0x18000a194  mov     rbx, rcx
0x18000a197  xor     r14d, r14d
0x18000a19a  mov     [rsp+58h+arg_8], r14d
0x18000a19f  mov     [rsp+58h+arg_8], r14d
0x18000a1a4  mov     rax, [rdx]
0x18000a1a7  lea     rdx, [rsp+58h+arg_8]
0x18000a1ac  mov     rcx, r15
0x18000a1af  mov     rax, [rax+18h]
0x18000a1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1b8  mov     rcx, [rsp+58h]; this
0x18000a1bd  test    eax, eax
0x18000a1bf  js      loc_18000A3EB
0x18000a1c5  cmp     [rsp+58h+arg_8], 0
0x18000a1ca  jbe     loc_18000A3D9
0x18000a1d0  mov     rsi, [rbx+20h]
0x18000a1d4  mov     rdi, [rbx+18h]
0x18000a1d8  jmp     short loc_18000A1F3
0x18000a1da  mov     rcx, [rdi]
0x18000a1dd  test    rcx, rcx
0x18000a1e0  jz      short loc_18000A1EF
0x18000a1e2  mov     rax, [rcx]
0x18000a1e5  mov     rax, [rax+10h]
0x18000a1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1ee  nop
0x18000a1ef  add     rdi, 8
0x18000a1f3  cmp     rdi, rsi
0x18000a1f6  jnz     short loc_18000A1DA
0x18000a1f8  mov     rax, [rbx+18h]
0x18000a1fc  mov     [rbx+20h], rax
0x18000a200  xor     edi, edi
0x18000a202  mov     r13, 1FFFFFFFFFFFFFFFh
0x18000a20c  cmp     edi, [rsp+58h+arg_8]
0x18000a210  jnb     loc_18000A3D9
0x18000a216  mov     rax, [r15]
0x18000a219  mov     [rsp+58h+arg_10], 0
0x18000a222  lea     r8, [rsp+58h+arg_10]
0x18000a227  mov     edx, edi
0x18000a229  mov     rcx, r15
0x18000a22c  mov     rax, [rax+20h]
0x18000a230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a235  mov     rcx, [rsp+58h]; this
0x18000a23a  test    eax, eax
0x18000a23c  js      loc_18000A400
0x18000a242  mov     rcx, [rsp+58h+arg_10]
0x18000a247  mov     qword ptr [rsp+58h+var_38], 0; int
0x18000a250  mov     rax, [rcx]
0x18000a253  lea     r8, [rsp+58h+var_38]
0x18000a258  lea     rdx, _GUID_c4445657_6908_45eb_a6b9_2f1ea4b2a03a
0x18000a25f  mov     rax, [rax]
0x18000a262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a267  mov     rcx, [rsp+58h]; this
0x18000a26c  test    eax, eax
0x18000a26e  js      loc_18000A414
0x18000a274  mov     r8, [rbx+20h]
0x18000a278  lea     rax, [rsp+58h+var_38]
0x18000a27d  cmp     rax, r8
0x18000a280  jnb     short loc_18000A291
0x18000a282  lea     rax, [rsp+58h+var_38]
0x18000a287  cmp     [rbx+18h], rax
0x18000a28b  ja      short loc_18000A291
0x18000a28d  mov     al, 1
0x18000a28f  jmp     short loc_18000A293
0x18000a291  xor     al, al
0x18000a293  mov     r9, [rbx+28h]
0x18000a297  test    al, al
0x18000a299  jz      loc_18000A326
0x18000a29f  mov     rsi, [rbx+18h]
0x18000a2a3  cmp     r8, r9
0x18000a2a6  jnz     short loc_18000A301
0x18000a2a8  mov     rax, r9
0x18000a2ab  sub     rax, r8
0x18000a2ae  sar     rax, 3
0x18000a2b2  cmp     rax, 1
0x18000a2b6  jnb     short loc_18000A301
0x18000a2b8  sub     r8, rsi
0x18000a2bb  sar     r8, 3
0x18000a2bf  mov     rax, r13
0x18000a2c2  sub     rax, r8
0x18000a2c5  cmp     rax, 1
0x18000a2c9  jb      loc_18000A429
0x18000a2cf  inc     r8
0x18000a2d2  sub     r9, rsi
0x18000a2d5  sar     r9, 3
0x18000a2d9  mov     rax, r9
0x18000a2dc  shr     rax, 1
0x18000a2df  mov     rcx, r13
0x18000a2e2  sub     rcx, rax
0x18000a2e5  add     rax, r9
0x18000a2e8  xor     edx, edx
0x18000a2ea  cmp     rcx, r9
0x18000a2ed  cmovnb  rdx, rax
0x18000a2f1  cmp     rdx, r8
0x18000a2f4  cmovb   rdx, r8
0x18000a2f8  lea     rcx, [rbx+18h]
0x18000a2fc  call    ?_Reallocate@?$vector@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@IEAAX_K@Z; std::vector<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>::_Reallocate(unsigned __int64)
0x18000a301  mov     r8, [rbx+20h]
0x18000a305  lea     rdx, [rsp+58h+var_38]
0x18000a30a  sub     rdx, rsi
0x18000a30d  sar     rdx, 3
0x18000a311  mov     rcx, [rbx+18h]
0x18000a315  mov     rax, [rcx+rdx*8]
0x18000a319  mov     qword ptr [rcx+rdx*8], 0
0x18000a321  mov     [r8], rax
0x18000a324  jmp     short loc_18000A39B
0x18000a326  cmp     r8, r9
0x18000a329  jnz     short loc_18000A386
0x18000a32b  mov     rax, r9
0x18000a32e  sub     rax, r8
0x18000a331  sar     rax, 3
0x18000a335  cmp     rax, 1
0x18000a339  jnb     short loc_18000A386
0x18000a33b  sub     r8, [rbx+18h]
0x18000a33f  sar     r8, 3
0x18000a343  mov     rax, r13
0x18000a346  sub     rax, r8
0x18000a349  cmp     rax, 1
0x18000a34d  jb      loc_18000A42E
0x18000a353  inc     r8
0x18000a356  sub     r9, [rbx+18h]
0x18000a35a  sar     r9, 3
0x18000a35e  mov     rax, r9
0x18000a361  shr     rax, 1
0x18000a364  mov     rcx, r13
0x18000a367  sub     rcx, rax
0x18000a36a  add     rax, r9
0x18000a36d  xor     edx, edx
0x18000a36f  cmp     rcx, r9
0x18000a372  cmovnb  rdx, rax
0x18000a376  cmp     rdx, r8
0x18000a379  cmovb   rdx, r8
0x18000a37d  lea     rcx, [rbx+18h]
0x18000a381  call    ?_Reallocate@?$vector@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@IEAAX_K@Z; std::vector<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>::_Reallocate(unsigned __int64)
0x18000a386  mov     rcx, qword ptr [rsp+58h+var_38]
0x18000a38b  mov     qword ptr [rsp+58h+var_38], 0
0x18000a394  mov     rax, [rbx+20h]
0x18000a398  mov     [rax], rcx
0x18000a39b  add     qword ptr [rbx+20h], 8
0x18000a3a0  or      r14d, 1
0x18000a3a4  mov     rcx, qword ptr [rsp+58h+var_38]
0x18000a3a9  test    rcx, rcx
0x18000a3ac  jz      short loc_18000A3BB
0x18000a3ae  mov     rax, [rcx]
0x18000a3b1  mov     rax, [rax+10h]
0x18000a3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3ba  nop
0x18000a3bb  mov     rcx, [rsp+58h+arg_10]
0x18000a3c0  test    rcx, rcx
0x18000a3c3  jz      short loc_18000A3D2
0x18000a3c5  mov     rax, [rcx]
0x18000a3c8  mov     rax, [rax+10h]
0x18000a3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d1  nop
0x18000a3d2  inc     edi
0x18000a3d4  jmp     loc_18000A20C
0x18000a3d9  mov     rbx, [rsp+58h+arg_0]
0x18000a3de  add     rsp, 30h
0x18000a3e2  pop     r15
0x18000a3e4  pop     r14
0x18000a3e6  pop     r13
0x18000a3e8  pop     rdi
0x18000a3e9  pop     rsi
0x18000a3ea  retn
0x18000a3eb  mov     r9d, eax; char *
0x18000a3ee  lea     r8, aMincoreTextinp; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18000a3f5  mov     edx, 1CBh; void *
0x18000a3fa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a400  mov     r9d, eax; char *
0x18000a403  lea     r8, aMincoreTextinp; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18000a40a  mov     edx, 1D3h; void *
0x18000a40f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a414  mov     r9d, eax; char *
0x18000a417  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a41e  mov     edx, 1CBEh; void *
0x18000a423  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a429  call    ?_Xlen@?$vector@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@IEBAXXZ; std::vector<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>::_Xlen(void)
0x18000a42e  call    ?_Xlen@?$vector@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@IEBAXXZ; std::vector<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>::_Xlen(void)
```
