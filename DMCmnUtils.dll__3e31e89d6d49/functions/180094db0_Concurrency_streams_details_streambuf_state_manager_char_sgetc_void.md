# Concurrency::streams::details::streambuf_state_manager<char>::sgetc(void)

- ea: `0x180094db0`
- end: `0x180094e3a`
- name: `?sgetc@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAAHXZ`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180091c50`
- `0x1800941b8`
- `0x180094db0`
- `0x1800c0010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180094dc1`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180094dc1`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180094de3`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180094de3`

## pseudocode

```c
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<char>::sgetc(__int64 a1)
{
  unsigned int v3; // eax
  __int128 v4; // [rsp+20h] [rbp-18h] BYREF

  if ( __ExceptionPtrToBool((const void *)(a1 + 24)) )
  {
    v4 = 0;
    __ExceptionPtrCopy(&v4, (const void *)(a1 + 24));
    std::rethrow_exception(&v4);
    __debugbreak();
  }
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1) )
    return 0xFFFFFFFFLL;
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 312LL))(a1);
  return Concurrency::streams::details::streambuf_state_manager<char>::check_sync_read_eof(a1, v3);
}

```

## disassembly

```asm
0x180094db0  mov     [rsp+arg_8], rbx
0x180094db5  push    rdi
0x180094db6  sub     rsp, 30h
0x180094dba  mov     rbx, rcx
0x180094dbd  add     rcx, 18h
0x180094dc1  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180094dc8  nop     dword ptr [rax+rax+00h]
0x180094dcd  test    al, al
0x180094dcf  jz      short loc_180094DFA
0x180094dd1  xorps   xmm0, xmm0
0x180094dd4  lea     rdx, [rbx+18h]
0x180094dd8  lea     rcx, [rsp+38h+var_18]
0x180094ddd  movdqu  [rsp+38h+var_18], xmm0
0x180094de3  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180094dea  nop     dword ptr [rax+rax+00h]
0x180094def  lea     rcx, [rsp+38h+var_18]
0x180094df4  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180094df9  int     3; Trap to Debugger
0x180094dfa  mov     rax, [rbx]
0x180094dfd  mov     rcx, rbx
0x180094e00  mov     rax, [rax+8]
0x180094e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094e09  test    al, al
0x180094e0b  jnz     short loc_180094E12
0x180094e0d  or      eax, 0FFFFFFFFh
0x180094e10  jmp     short loc_180094E2E
0x180094e12  mov     rax, [rbx]
0x180094e15  mov     rcx, rbx
0x180094e18  mov     rax, [rax+138h]
0x180094e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094e24  mov     edx, eax
0x180094e26  mov     rcx, rbx
0x180094e29  call    ?check_sync_read_eof@?$streambuf_state_manager@D@details@streams@Concurrency@@AEAAHH@Z; Concurrency::streams::details::streambuf_state_manager<char>::check_sync_read_eof(int)
0x180094e2e  mov     rbx, [rsp+38h+arg_8]
0x180094e33  add     rsp, 30h
0x180094e37  pop     rdi
0x180094e38  retn
```
