# std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)

- ea: `0x18001c9b4`
- end: `0x18001ca5f`
- name: `?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001ca68`

## callees

- `0x18001862c`
- `0x180018c30`
- `0x18001c9b4`
- `0x18001cb60`
- `0x18004e010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001ca39`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001ca4e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001ca39`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001ca4e`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18001ca16`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18001ca16`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001c9e9`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001c9e9`

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
0x18001c9b4  mov     [rsp+arg_10], rbx
0x18001c9b9  mov     [rsp+arg_8], rdx
0x18001c9be  push    rdi
0x18001c9bf  sub     rsp, 40h
0x18001c9c3  mov     rdi, rdx
0x18001c9c6  mov     rbx, rcx
0x18001c9c9  lea     rdx, [rcx+20h]
0x18001c9cd  lea     rcx, [rsp+48h+var_18]
0x18001c9d2  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001c9d7  nop
0x18001c9d8  xorps   xmm0, xmm0
0x18001c9db  movdqu  [rsp+48h+var_28], xmm0
0x18001c9e1  mov     rdx, rdi
0x18001c9e4  lea     rcx, [rsp+48h+var_28]
0x18001c9e9  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001c9ef  lea     rax, [rsp+48h+var_28]
0x18001c9f4  mov     [rsp+48h+arg_0], rax
0x18001c9f9  cmp     byte ptr [rbx+0C1h], 0
0x18001ca00  jz      short loc_18001CA0D
0x18001ca02  mov     ecx, 3
0x18001ca07  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18001ca0d  lea     rcx, [rbx+10h]
0x18001ca11  lea     rdx, [rsp+48h+var_28]
0x18001ca16  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18001ca1c  mov     rax, [rbx]
0x18001ca1f  xor     r8d, r8d
0x18001ca22  lea     rdx, [rsp+48h+var_18]
0x18001ca27  mov     rcx, rbx
0x18001ca2a  mov     rax, [rax+28h]
0x18001ca2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca33  nop
0x18001ca34  lea     rcx, [rsp+48h+var_28]
0x18001ca39  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001ca3f  nop
0x18001ca40  lea     rcx, [rsp+48h+var_18]
0x18001ca45  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001ca4a  nop
0x18001ca4b  mov     rcx, rdi
0x18001ca4e  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001ca54  mov     rbx, [rsp+48h+arg_10]
0x18001ca59  add     rsp, 40h
0x18001ca5d  pop     rdi
0x18001ca5e  retn
```
