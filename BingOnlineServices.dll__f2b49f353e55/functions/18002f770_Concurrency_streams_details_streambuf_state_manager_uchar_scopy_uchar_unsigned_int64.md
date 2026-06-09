# Concurrency::streams::details::streambuf_state_manager<uchar>::scopy(uchar *,unsigned __int64)

- ea: `0x18002f770`
- end: `0x18002f7f6`
- name: `?scopy@?$streambuf_state_manager@E@details@streams@Concurrency@@UEAA_KPEAE_K@Z`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002f770`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18002f786`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18002f786`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002f7b7`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002f7b7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002f7a2`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002f7a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<unsigned char>::scopy(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _OWORD v7[3]; // [rsp+20h] [rbp-38h] BYREF

  if ( __ExceptionPtrToBool((const void *)(a1 + 24)) )
  {
    v7[0] = 0;
    __ExceptionPtrCopy(v7, (const void *)(a1 + 24));
    __ExceptionPtrRethrow(v7);
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1) )
    return (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 344LL))(a1, a2, a3);
  else
    return 0;
}

```

## disassembly

```asm
0x18002f770  push    rbx
0x18002f772  push    rbp
0x18002f773  push    rsi
0x18002f774  push    rdi
0x18002f775  sub     rsp, 38h
0x18002f779  mov     rsi, r8
0x18002f77c  mov     rbp, rdx
0x18002f77f  mov     rbx, rcx
0x18002f782  add     rcx, 18h
0x18002f786  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18002f78c  test    al, al
0x18002f78e  jz      short loc_18002F7BE
0x18002f790  xorps   xmm0, xmm0
0x18002f793  movdqu  [rsp+58h+var_38], xmm0
0x18002f799  lea     rdx, [rbx+18h]
0x18002f79d  lea     rcx, [rsp+58h+var_38]
0x18002f7a2  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002f7a8  lea     rax, [rsp+58h+var_38]
0x18002f7ad  mov     [rsp+58h+arg_0], rax
0x18002f7b2  lea     rcx, [rsp+58h+var_38]
0x18002f7b7  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18002f7bd  nop
0x18002f7be  mov     rax, [rbx]
0x18002f7c1  mov     rcx, rbx
0x18002f7c4  mov     rax, [rax+8]
0x18002f7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7cd  test    al, al
0x18002f7cf  jnz     short loc_18002F7D5
0x18002f7d1  xor     eax, eax
0x18002f7d3  jmp     short loc_18002F7ED
0x18002f7d5  mov     rax, [rbx]
0x18002f7d8  mov     r8, rsi
0x18002f7db  mov     rdx, rbp
0x18002f7de  mov     rcx, rbx
0x18002f7e1  mov     rax, [rax+158h]
0x18002f7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7ed  add     rsp, 38h
0x18002f7f1  pop     rdi
0x18002f7f2  pop     rsi
0x18002f7f3  pop     rbp
0x18002f7f4  pop     rbx
0x18002f7f5  retn
```
