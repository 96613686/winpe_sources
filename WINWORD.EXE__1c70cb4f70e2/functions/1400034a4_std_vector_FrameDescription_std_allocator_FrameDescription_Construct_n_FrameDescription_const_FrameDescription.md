# std::vector<FrameDescription,std::allocator<FrameDescription>>::_Construct_n<FrameDescription * const &,FrameDescription * const &>(unsigned __int64,FrameDescription * const &,FrameDescription * const &)

- ea: `0x1400034a4`
- end: `0x140003549`
- name: `??$_Construct_n@AEBQEAUFrameDescription@@AEBQEAU1@@?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@AEAAX_KAEBQEAUFrameDescription@@1@Z`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000354c`
- `0x140003a50`

## callees

- `0x140003151`
- `0x140003430`
- `0x1400034a4`

## import_xrefs

- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400034e4`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400034e4`

## pseudocode

```c
void __fastcall std::vector<FrameDescription>::_Construct_n<FrameDescription * const &,FrameDescription * const &>(
        _QWORD *a1,
        unsigned __int64 a2,
        const void **a3,
        _QWORD *a4)
{
  __int64 v7; // rbx
  char *v8; // rax
  char *v9; // rdi
  size_t v10; // rbx

  if ( a2 )
  {
    if ( a2 > 0xFFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector too long");
    v7 = 16 * a2;
    v8 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(16 * a2);
    *a1 = v8;
    v9 = v8;
    a1[1] = v8;
    a1[2] = &v8[v7];
    v10 = *a4 - (_QWORD)*a3;
    memmove_0(v8, *a3, v10);
    a1[1] = &v9[v10 & 0xFFFFFFFFFFFFFFF0uLL];
  }
}

```

## disassembly

```asm
0x1400034a4  test    rdx, rdx
0x1400034a7  jz      locret_140003548
0x1400034ad  mov     [rsp+arg_8], rbx
0x1400034b2  mov     [rsp+arg_10], rsi
0x1400034b7  mov     [rsp+arg_18], r14
0x1400034bc  push    r15
0x1400034be  sub     rsp, 20h
0x1400034c2  mov     rax, 0FFFFFFFFFFFFFFFh
0x1400034cc  mov     r14, r9
0x1400034cf  mov     r15, r8
0x1400034d2  mov     rbx, rdx
0x1400034d5  mov     rsi, rcx
0x1400034d8  cmp     rdx, rax
0x1400034db  jbe     short loc_1400034EB
0x1400034dd  lea     rcx, aVectorTooLong; "vector too long"
0x1400034e4  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1400034eb  shl     rbx, 4
0x1400034ef  mov     rcx, rbx
0x1400034f2  mov     [rsp+28h+arg_0], rdi
0x1400034f7  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1400034fc  mov     [rsi], rax
0x1400034ff  mov     rdi, rax
0x140003502  mov     [rsi+8], rax
0x140003506  lea     rcx, [rbx+rax]
0x14000350a  mov     [rsi+10h], rcx
0x14000350e  mov     rcx, rax; void *
0x140003511  mov     rdx, [r15]; Src
0x140003514  mov     rbx, [r14]
0x140003517  sub     rbx, rdx
0x14000351a  mov     r8, rbx; Size
0x14000351d  call    memmove_0
0x140003522  mov     r14, [rsp+28h+arg_18]
0x140003527  and     rbx, 0FFFFFFFFFFFFFFF0h
0x14000352b  lea     rax, [rbx+rdi]
0x14000352f  mov     rdi, [rsp+28h+arg_0]
0x140003534  mov     rbx, [rsp+28h+arg_8]
0x140003539  mov     [rsi+8], rax
0x14000353d  mov     rsi, [rsp+28h+arg_10]
0x140003542  add     rsp, 20h
0x140003546  pop     r15
0x140003548  retn
```
