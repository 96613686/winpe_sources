# std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)

- ea: `0x1800241b4`
- end: `0x18002425f`
- name: `?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `171`
- prototype: `void __fastcall(_BYTE *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180026b09`

## callees

- `0x18001d9e0`
- `0x18001e230`
- `0x1800241b4`
- `0x180024310`
- `0x180027010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180024216`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180024216`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800241e9`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800241e9`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180024239`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002424e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180024239`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002424e`

## pseudocode

```c
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
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>((__int64)v5);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x1800241b4  mov     [rsp+arg_10], rbx
0x1800241b9  mov     [rsp+arg_8], rdx
0x1800241be  push    rdi
0x1800241bf  sub     rsp, 40h
0x1800241c3  mov     rdi, rdx
0x1800241c6  mov     rbx, rcx
0x1800241c9  lea     rdx, [rcx+20h]
0x1800241cd  lea     rcx, [rsp+48h+var_18]
0x1800241d2  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x1800241d7  nop
0x1800241d8  xorps   xmm0, xmm0
0x1800241db  movdqu  [rsp+48h+var_28], xmm0
0x1800241e1  mov     rdx, rdi
0x1800241e4  lea     rcx, [rsp+48h+var_28]
0x1800241e9  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800241ef  lea     rax, [rsp+48h+var_28]
0x1800241f4  mov     [rsp+48h+arg_0], rax
0x1800241f9  cmp     byte ptr [rbx+0C1h], 0
0x180024200  jz      short loc_18002420D
0x180024202  mov     ecx, 3
0x180024207  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18002420d  lea     rcx, [rbx+10h]
0x180024211  lea     rdx, [rsp+48h+var_28]
0x180024216  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18002421c  mov     rax, [rbx]
0x18002421f  xor     r8d, r8d
0x180024222  lea     rdx, [rsp+48h+var_18]
0x180024227  mov     rcx, rbx
0x18002422a  mov     rax, [rax+28h]
0x18002422e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024233  nop
0x180024234  lea     rcx, [rsp+48h+var_28]
0x180024239  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002423f  nop
0x180024240  lea     rcx, [rsp+48h+var_18]
0x180024245  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18002424a  nop
0x18002424b  mov     rcx, rdi
0x18002424e  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180024254  mov     rbx, [rsp+48h+arg_10]
0x180024259  add     rsp, 40h
0x18002425d  pop     rdi
0x18002425e  retn
```
