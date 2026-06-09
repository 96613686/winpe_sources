# Concurrency::streams::details::streambuf_state_manager<char>::scopy(char *,unsigned __int64)

- ea: `0x1800942e0`
- end: `0x180094368`
- name: `?scopy@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAA_KPEAD_K@Z`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800941b8`
- `0x1800942e0`
- `0x1800c0010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800942f6`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800942f6`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180094318`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180094318`

## pseudocode

```c
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<char>::scopy(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _OWORD v7[3]; // [rsp+20h] [rbp-38h] BYREF

  if ( __ExceptionPtrToBool((const void *)(a1 + 24)) )
  {
    v7[0] = 0;
    __ExceptionPtrCopy(v7, (const void *)(a1 + 24));
    std::rethrow_exception(v7);
    __debugbreak();
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1) )
    return (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 344LL))(a1, a2, a3);
  else
    return 0;
}

```

## disassembly

```asm
0x1800942e0  push    rbx
0x1800942e2  push    rbp
0x1800942e3  push    rsi
0x1800942e4  push    rdi
0x1800942e5  sub     rsp, 38h
0x1800942e9  mov     rbx, rcx
0x1800942ec  mov     rsi, r8
0x1800942ef  add     rcx, 18h
0x1800942f3  mov     rbp, rdx
0x1800942f6  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800942fd  nop     dword ptr [rax+rax+00h]
0x180094302  test    al, al
0x180094304  jz      short loc_18009432F
0x180094306  xorps   xmm0, xmm0
0x180094309  lea     rdx, [rbx+18h]
0x18009430d  lea     rcx, [rsp+58h+var_38]
0x180094312  movdqu  [rsp+58h+var_38], xmm0
0x180094318  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18009431f  nop     dword ptr [rax+rax+00h]
0x180094324  lea     rcx, [rsp+58h+var_38]
0x180094329  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x18009432e  int     3; Trap to Debugger
0x18009432f  mov     rax, [rbx]
0x180094332  mov     rcx, rbx
0x180094335  mov     rax, [rax+8]
0x180094339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009433e  test    al, al
0x180094340  jnz     short loc_180094346
0x180094342  xor     eax, eax
0x180094344  jmp     short loc_18009435E
0x180094346  mov     rax, [rbx]
0x180094349  mov     r8, rsi
0x18009434c  mov     rdx, rbp
0x18009434f  mov     rcx, rbx
0x180094352  mov     rax, [rax+158h]
0x180094359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009435e  add     rsp, 38h
0x180094362  pop     rdi
0x180094363  pop     rsi
0x180094364  pop     rbp
0x180094365  pop     rbx
0x180094366  retn
```
