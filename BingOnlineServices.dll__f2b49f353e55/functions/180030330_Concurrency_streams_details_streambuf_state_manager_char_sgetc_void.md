# Concurrency::streams::details::streambuf_state_manager<char>::sgetc(void)

- ea: `0x180030330`
- end: `0x1800303b7`
- name: `?sgetc@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAAHXZ`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180030330`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180030341`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180030341`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180030372`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180030372`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003035d`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003035d`

## pseudocode

```c
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<char>::sgetc(_BYTE *a1)
{
  __int64 result; // rax
  __int128 v3; // [rsp+20h] [rbp-18h] BYREF

  if ( __ExceptionPtrToBool(a1 + 24) )
  {
    v3 = 0;
    __ExceptionPtrCopy(&v3, a1 + 24);
    __ExceptionPtrRethrow(&v3);
  }
  if ( !(*(unsigned __int8 (__fastcall **)(_BYTE *))(*(_QWORD *)a1 + 8LL))(a1) )
    return 0xFFFFFFFFLL;
  result = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)a1 + 312LL))(a1);
  a1[42] = (_DWORD)result == -1;
  return result;
}

```

## disassembly

```asm
0x180030330  mov     [rsp+arg_8], rbx
0x180030335  push    rdi
0x180030336  sub     rsp, 30h
0x18003033a  mov     rbx, rcx
0x18003033d  add     rcx, 18h
0x180030341  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180030347  test    al, al
0x180030349  jz      short loc_180030379
0x18003034b  xorps   xmm0, xmm0
0x18003034e  movdqu  [rsp+38h+var_18], xmm0
0x180030354  lea     rdx, [rbx+18h]
0x180030358  lea     rcx, [rsp+38h+var_18]
0x18003035d  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180030363  lea     rax, [rsp+38h+var_18]
0x180030368  mov     [rsp+38h+arg_0], rax
0x18003036d  lea     rcx, [rsp+38h+var_18]
0x180030372  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180030378  nop
0x180030379  mov     rax, [rbx]
0x18003037c  mov     rcx, rbx
0x18003037f  mov     rax, [rax+8]
0x180030383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030388  test    al, al
0x18003038a  jnz     short loc_180030391
0x18003038c  or      eax, 0FFFFFFFFh
0x18003038f  jmp     short loc_1800303AC
0x180030391  mov     rax, [rbx]
0x180030394  mov     rcx, rbx
0x180030397  mov     rax, [rax+138h]
0x18003039e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303a3  cmp     eax, 0FFFFFFFFh
0x1800303a6  setz    cl
0x1800303a9  mov     [rbx+2Ah], cl
0x1800303ac  mov     rbx, [rsp+38h+arg_8]
0x1800303b1  add     rsp, 30h
0x1800303b5  pop     rdi
0x1800303b6  retn
```
