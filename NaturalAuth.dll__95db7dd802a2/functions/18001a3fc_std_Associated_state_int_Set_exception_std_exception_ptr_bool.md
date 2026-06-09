# std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)

- ea: `0x18001a3fc`
- end: `0x18001a4a7`
- name: `?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180042e24`

## callees

- `0x180011e50`
- `0x180012aec`
- `0x18001a3fc`
- `0x18001a7fc`
- `0x180046010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001a481`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001a496`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001a481`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001a496`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001a431`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001a431`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18001a45e`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18001a45e`

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
0x18001a3fc  mov     [rsp+arg_10], rbx
0x18001a401  mov     [rsp+arg_8], rdx
0x18001a406  push    rdi
0x18001a407  sub     rsp, 40h
0x18001a40b  mov     rdi, rdx
0x18001a40e  mov     rbx, rcx
0x18001a411  lea     rdx, [rcx+20h]
0x18001a415  lea     rcx, [rsp+48h+var_18]
0x18001a41a  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001a41f  nop
0x18001a420  xorps   xmm0, xmm0
0x18001a423  movdqu  [rsp+48h+var_28], xmm0
0x18001a429  mov     rdx, rdi
0x18001a42c  lea     rcx, [rsp+48h+var_28]
0x18001a431  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001a437  lea     rax, [rsp+48h+var_28]
0x18001a43c  mov     [rsp+48h+arg_0], rax
0x18001a441  cmp     byte ptr [rbx+0C1h], 0
0x18001a448  jz      short loc_18001A455
0x18001a44a  mov     ecx, 3
0x18001a44f  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18001a455  lea     rcx, [rbx+10h]
0x18001a459  lea     rdx, [rsp+48h+var_28]
0x18001a45e  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18001a464  mov     rax, [rbx]
0x18001a467  xor     r8d, r8d
0x18001a46a  lea     rdx, [rsp+48h+var_18]
0x18001a46f  mov     rcx, rbx
0x18001a472  mov     rax, [rax+28h]
0x18001a476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a47b  nop
0x18001a47c  lea     rcx, [rsp+48h+var_28]
0x18001a481  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001a487  nop
0x18001a488  lea     rcx, [rsp+48h+var_18]
0x18001a48d  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001a492  nop
0x18001a493  mov     rcx, rdi
0x18001a496  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001a49c  mov     rbx, [rsp+48h+arg_10]
0x18001a4a1  add     rsp, 40h
0x18001a4a5  pop     rdi
0x18001a4a6  retn
```
