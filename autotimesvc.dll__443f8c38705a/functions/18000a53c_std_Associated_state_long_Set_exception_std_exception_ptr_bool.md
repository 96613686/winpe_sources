# std::_Associated_state<long>::_Set_exception(std::exception_ptr,bool)

- ea: `0x18000a53c`
- end: `0x18000a5e7`
- name: `?_Set_exception@?$_Associated_state@J@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `171`
- prototype: `void __fastcall(_BYTE *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a5f0`

## callees

- `0x180004e9c`
- `0x1800057b4`
- `0x18000a53c`
- `0x18000a6d0`
- `0x180012010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000a571`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000a571`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18000a59e`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18000a59e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18000a5c1`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18000a5d6`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18000a5c1`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18000a5d6`

## pseudocode

```c
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
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>((__int64)v5);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x18000a53c  mov     [rsp+arg_10], rbx
0x18000a541  mov     [rsp+arg_8], rdx
0x18000a546  push    rdi
0x18000a547  sub     rsp, 40h
0x18000a54b  mov     rdi, rdx
0x18000a54e  mov     rbx, rcx
0x18000a551  lea     rdx, [rcx+20h]
0x18000a555  lea     rcx, [rsp+48h+var_18]
0x18000a55a  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18000a55f  nop
0x18000a560  xorps   xmm0, xmm0
0x18000a563  movdqu  [rsp+48h+var_28], xmm0
0x18000a569  mov     rdx, rdi
0x18000a56c  lea     rcx, [rsp+48h+var_28]
0x18000a571  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18000a577  lea     rax, [rsp+48h+var_28]
0x18000a57c  mov     [rsp+48h+arg_0], rax
0x18000a581  cmp     byte ptr [rbx+0C1h], 0
0x18000a588  jz      short loc_18000A595
0x18000a58a  mov     ecx, 3
0x18000a58f  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18000a595  lea     rcx, [rbx+10h]
0x18000a599  lea     rdx, [rsp+48h+var_28]
0x18000a59e  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18000a5a4  mov     rax, [rbx]
0x18000a5a7  xor     r8d, r8d
0x18000a5aa  lea     rdx, [rsp+48h+var_18]
0x18000a5af  mov     rcx, rbx
0x18000a5b2  mov     rax, [rax+28h]
0x18000a5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5bb  nop
0x18000a5bc  lea     rcx, [rsp+48h+var_28]
0x18000a5c1  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18000a5c7  nop
0x18000a5c8  lea     rcx, [rsp+48h+var_18]
0x18000a5cd  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18000a5d2  nop
0x18000a5d3  mov     rcx, rdi
0x18000a5d6  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18000a5dc  mov     rbx, [rsp+48h+arg_10]
0x18000a5e1  add     rsp, 40h
0x18000a5e5  pop     rdi
0x18000a5e6  retn
```
