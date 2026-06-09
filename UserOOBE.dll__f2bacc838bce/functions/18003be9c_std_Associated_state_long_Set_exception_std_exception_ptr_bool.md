# std::_Associated_state<long>::_Set_exception(std::exception_ptr,bool)

- ea: `0x18003be9c`
- end: `0x18003bf47`
- name: `?_Set_exception@?$_Associated_state@J@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003bf50`

## callees

- `0x18001862c`
- `0x180018c30`
- `0x18001cb60`
- `0x18003be9c`
- `0x18004e010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003bf16`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003bf2b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003bf16`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003bf2b`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003bef3`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003bef3`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003bed1`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003bed1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::_Associated_state<long>::_Set_exception(_BYTE *a1, void *a2)
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
0x18003be9c  mov     [rsp+arg_10], rbx
0x18003bea1  mov     [rsp+arg_8], rdx
0x18003bea6  push    rdi
0x18003bea7  sub     rsp, 40h
0x18003beab  mov     rdi, rdx
0x18003beae  mov     rbx, rcx
0x18003beb1  lea     rdx, [rcx+20h]
0x18003beb5  lea     rcx, [rsp+48h+var_18]
0x18003beba  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18003bebf  nop
0x18003bec0  xorps   xmm0, xmm0
0x18003bec3  movdqu  [rsp+48h+var_28], xmm0
0x18003bec9  mov     rdx, rdi
0x18003becc  lea     rcx, [rsp+48h+var_28]
0x18003bed1  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003bed7  lea     rax, [rsp+48h+var_28]
0x18003bedc  mov     [rsp+48h+arg_0], rax
0x18003bee1  cmp     byte ptr [rbx+0C1h], 0
0x18003bee8  jnz     short loc_18003BF3C
0x18003beea  lea     rcx, [rbx+10h]
0x18003beee  lea     rdx, [rsp+48h+var_28]
0x18003bef3  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18003bef9  mov     rax, [rbx]
0x18003befc  xor     r8d, r8d
0x18003beff  lea     rdx, [rsp+48h+var_18]
0x18003bf04  mov     rcx, rbx
0x18003bf07  mov     rax, [rax+28h]
0x18003bf0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf10  nop
0x18003bf11  lea     rcx, [rsp+48h+var_28]
0x18003bf16  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003bf1c  nop
0x18003bf1d  lea     rcx, [rsp+48h+var_18]
0x18003bf22  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18003bf27  nop
0x18003bf28  mov     rcx, rdi
0x18003bf2b  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003bf31  mov     rbx, [rsp+48h+arg_10]
0x18003bf36  add     rsp, 40h
0x18003bf3a  pop     rdi
0x18003bf3b  retn
0x18003bf3c  mov     ecx, 3
0x18003bf41  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```
