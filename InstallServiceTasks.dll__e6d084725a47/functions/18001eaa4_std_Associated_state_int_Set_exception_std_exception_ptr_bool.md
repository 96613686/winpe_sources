# std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)

- ea: `0x18001eaa4`
- end: `0x18001eb4f`
- name: `?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004161a`

## callees

- `0x18001ab74`
- `0x18001b630`
- `0x18001eaa4`
- `0x18001ebc0`
- `0x180046010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18001eb06`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18001eb06`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001ead9`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001ead9`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001eb29`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001eb3e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001eb29`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001eb3e`

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
0x18001eaa4  mov     [rsp+arg_10], rbx
0x18001eaa9  mov     [rsp+arg_8], rdx
0x18001eaae  push    rdi
0x18001eaaf  sub     rsp, 40h
0x18001eab3  mov     rdi, rdx
0x18001eab6  mov     rbx, rcx
0x18001eab9  lea     rdx, [rcx+20h]
0x18001eabd  lea     rcx, [rsp+48h+var_18]
0x18001eac2  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18001eac7  nop
0x18001eac8  xorps   xmm0, xmm0
0x18001eacb  movdqu  [rsp+48h+var_28], xmm0
0x18001ead1  mov     rdx, rdi
0x18001ead4  lea     rcx, [rsp+48h+var_28]
0x18001ead9  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001eadf  lea     rax, [rsp+48h+var_28]
0x18001eae4  mov     [rsp+48h+arg_0], rax
0x18001eae9  cmp     byte ptr [rbx+0C1h], 0
0x18001eaf0  jz      short loc_18001EAFD
0x18001eaf2  mov     ecx, 3
0x18001eaf7  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18001eafd  lea     rcx, [rbx+10h]
0x18001eb01  lea     rdx, [rsp+48h+var_28]
0x18001eb06  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18001eb0c  mov     rax, [rbx]
0x18001eb0f  xor     r8d, r8d
0x18001eb12  lea     rdx, [rsp+48h+var_18]
0x18001eb17  mov     rcx, rbx
0x18001eb1a  mov     rax, [rax+28h]
0x18001eb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb23  nop
0x18001eb24  lea     rcx, [rsp+48h+var_28]
0x18001eb29  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001eb2f  nop
0x18001eb30  lea     rcx, [rsp+48h+var_18]
0x18001eb35  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001eb3a  nop
0x18001eb3b  mov     rcx, rdi
0x18001eb3e  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001eb44  mov     rbx, [rsp+48h+arg_10]
0x18001eb49  add     rsp, 40h
0x18001eb4d  pop     rdi
0x18001eb4e  retn
```
