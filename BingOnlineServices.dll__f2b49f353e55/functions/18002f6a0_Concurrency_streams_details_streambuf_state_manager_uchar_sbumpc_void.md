# Concurrency::streams::details::streambuf_state_manager<uchar>::sbumpc(void)

- ea: `0x18002f6a0`
- end: `0x18002f727`
- name: `?sbumpc@?$streambuf_state_manager@E@details@streams@Concurrency@@UEAAJXZ`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002f6a0`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18002f6b1`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18002f6b1`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002f6e2`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002f6e2`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002f6cd`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002f6cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<unsigned char>::sbumpc(_BYTE *a1)
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
  result = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)a1 + 296LL))(a1);
  a1[42] = (_DWORD)result == -1;
  return result;
}

```

## disassembly

```asm
0x18002f6a0  mov     [rsp+arg_8], rbx
0x18002f6a5  push    rdi
0x18002f6a6  sub     rsp, 30h
0x18002f6aa  mov     rbx, rcx
0x18002f6ad  add     rcx, 18h
0x18002f6b1  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18002f6b7  test    al, al
0x18002f6b9  jz      short loc_18002F6E9
0x18002f6bb  xorps   xmm0, xmm0
0x18002f6be  movdqu  [rsp+38h+var_18], xmm0
0x18002f6c4  lea     rdx, [rbx+18h]
0x18002f6c8  lea     rcx, [rsp+38h+var_18]
0x18002f6cd  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002f6d3  lea     rax, [rsp+38h+var_18]
0x18002f6d8  mov     [rsp+38h+arg_0], rax
0x18002f6dd  lea     rcx, [rsp+38h+var_18]
0x18002f6e2  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18002f6e8  nop
0x18002f6e9  mov     rax, [rbx]
0x18002f6ec  mov     rcx, rbx
0x18002f6ef  mov     rax, [rax+8]
0x18002f6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6f8  test    al, al
0x18002f6fa  jnz     short loc_18002F701
0x18002f6fc  or      eax, 0FFFFFFFFh
0x18002f6ff  jmp     short loc_18002F71C
0x18002f701  mov     rax, [rbx]
0x18002f704  mov     rcx, rbx
0x18002f707  mov     rax, [rax+128h]
0x18002f70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f713  cmp     eax, 0FFFFFFFFh
0x18002f716  setz    cl
0x18002f719  mov     [rbx+2Ah], cl
0x18002f71c  mov     rbx, [rsp+38h+arg_8]
0x18002f721  add     rsp, 30h
0x18002f725  pop     rdi
0x18002f726  retn
```
