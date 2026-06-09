# Concurrency::streams::details::streambuf_state_manager<char>::sbumpc(void)

- ea: `0x180094210`
- end: `0x18009429a`
- name: `?sbumpc@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAAHXZ`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180091c50`
- `0x1800941b8`
- `0x180094210`
- `0x1800c0010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180094221`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180094221`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180094243`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180094243`

## pseudocode

```c
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<char>::sbumpc(__int64 a1)
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
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 296LL))(a1);
  return Concurrency::streams::details::streambuf_state_manager<char>::check_sync_read_eof(a1, v3);
}

```

## disassembly

```asm
0x180094210  mov     [rsp+arg_8], rbx
0x180094215  push    rdi
0x180094216  sub     rsp, 30h
0x18009421a  mov     rbx, rcx
0x18009421d  add     rcx, 18h
0x180094221  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180094228  nop     dword ptr [rax+rax+00h]
0x18009422d  test    al, al
0x18009422f  jz      short loc_18009425A
0x180094231  xorps   xmm0, xmm0
0x180094234  lea     rdx, [rbx+18h]
0x180094238  lea     rcx, [rsp+38h+var_18]
0x18009423d  movdqu  [rsp+38h+var_18], xmm0
0x180094243  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18009424a  nop     dword ptr [rax+rax+00h]
0x18009424f  lea     rcx, [rsp+38h+var_18]
0x180094254  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180094259  int     3; Trap to Debugger
0x18009425a  mov     rax, [rbx]
0x18009425d  mov     rcx, rbx
0x180094260  mov     rax, [rax+8]
0x180094264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094269  test    al, al
0x18009426b  jnz     short loc_180094272
0x18009426d  or      eax, 0FFFFFFFFh
0x180094270  jmp     short loc_18009428E
0x180094272  mov     rax, [rbx]
0x180094275  mov     rcx, rbx
0x180094278  mov     rax, [rax+128h]
0x18009427f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094284  mov     edx, eax
0x180094286  mov     rcx, rbx
0x180094289  call    ?check_sync_read_eof@?$streambuf_state_manager@D@details@streams@Concurrency@@AEAAHH@Z; Concurrency::streams::details::streambuf_state_manager<char>::check_sync_read_eof(int)
0x18009428e  mov     rbx, [rsp+38h+arg_8]
0x180094293  add     rsp, 30h
0x180094297  pop     rdi
0x180094298  retn
```
