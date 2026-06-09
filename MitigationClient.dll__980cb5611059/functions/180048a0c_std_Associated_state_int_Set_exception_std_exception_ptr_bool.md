# std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)

- ea: `0x180048a0c`
- end: `0x180048ab7`
- name: `?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180059bae`

## callees

- `0x1800466bc`
- `0x180046d5c`
- `0x180048a0c`
- `0x180048b20`
- `0x18005c010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180048a41`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180048a41`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180048a91`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180048aa6`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180048a91`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180048aa6`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180048a6e`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180048a6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::_Associated_state<int>::_Set_exception(_BYTE *a1, void *a2)
{
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v5[24]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v5, a1 + 32);
  v4 = 0;
  __ExceptionPtrCopy(&v4, a2);
  if ( a1[193] )
    std::_Throw_future_error2(3);
  __ExceptionPtrAssign(a1 + 16, &v4);
  (*(void (__fastcall **)(_BYTE *, _BYTE *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v5, 0);
  __ExceptionPtrDestroy(&v4);
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v5);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x180048a0c  mov     [rsp+arg_10], rbx
0x180048a11  mov     [rsp+arg_8], rdx
0x180048a16  push    rdi
0x180048a17  sub     rsp, 40h
0x180048a1b  mov     rdi, rdx
0x180048a1e  mov     rbx, rcx
0x180048a21  lea     rdx, [rcx+20h]
0x180048a25  lea     rcx, [rsp+48h+var_18]
0x180048a2a  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180048a2f  nop
0x180048a30  xorps   xmm0, xmm0
0x180048a33  movdqu  [rsp+48h+var_28], xmm0
0x180048a39  mov     rdx, rdi
0x180048a3c  lea     rcx, [rsp+48h+var_28]
0x180048a41  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180048a47  lea     rax, [rsp+48h+var_28]
0x180048a4c  mov     [rsp+48h+arg_0], rax
0x180048a51  cmp     byte ptr [rbx+0C1h], 0
0x180048a58  jz      short loc_180048A65
0x180048a5a  mov     ecx, 3
0x180048a5f  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180048a65  lea     rcx, [rbx+10h]
0x180048a69  lea     rdx, [rsp+48h+var_28]
0x180048a6e  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180048a74  mov     rax, [rbx]
0x180048a77  xor     r8d, r8d
0x180048a7a  lea     rdx, [rsp+48h+var_18]
0x180048a7f  mov     rcx, rbx
0x180048a82  mov     rax, [rax+28h]
0x180048a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a8b  nop
0x180048a8c  lea     rcx, [rsp+48h+var_28]
0x180048a91  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180048a97  nop
0x180048a98  lea     rcx, [rsp+48h+var_18]
0x180048a9d  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180048aa2  nop
0x180048aa3  mov     rcx, rdi
0x180048aa6  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180048aac  mov     rbx, [rsp+48h+arg_10]
0x180048ab1  add     rsp, 40h
0x180048ab5  pop     rdi
0x180048ab6  retn
```
