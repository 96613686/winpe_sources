# std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)

- ea: `0x180010f98`
- end: `0x180011043`
- name: `?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `171`
- prototype: `void __fastcall(_BYTE *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001104c`

## callees

- `0x18000e418`
- `0x18000e700`
- `0x180010f98`
- `0x180011130`
- `0x180031010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180010ffa`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180010ffa`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180010fcd`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180010fcd`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001101d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180011032`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001101d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180011032`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180010f98  mov     [rsp+arg_10], rbx
0x180010f9d  mov     [rsp+arg_8], rdx
0x180010fa2  push    rdi
0x180010fa3  sub     rsp, 40h
0x180010fa7  mov     rdi, rdx
0x180010faa  mov     rbx, rcx
0x180010fad  lea     rdx, [rcx+20h]
0x180010fb1  lea     rcx, [rsp+48h+var_18]
0x180010fb6  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180010fbb  nop
0x180010fbc  xorps   xmm0, xmm0
0x180010fbf  movdqu  [rsp+48h+var_28], xmm0
0x180010fc5  mov     rdx, rdi
0x180010fc8  lea     rcx, [rsp+48h+var_28]
0x180010fcd  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180010fd3  lea     rax, [rsp+48h+var_28]
0x180010fd8  mov     [rsp+48h+arg_0], rax
0x180010fdd  cmp     byte ptr [rbx+0C1h], 0
0x180010fe4  jz      short loc_180010FF1
0x180010fe6  mov     ecx, 3
0x180010feb  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180010ff1  lea     rcx, [rbx+10h]
0x180010ff5  lea     rdx, [rsp+48h+var_28]
0x180010ffa  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180011000  mov     rax, [rbx]
0x180011003  xor     r8d, r8d
0x180011006  lea     rdx, [rsp+48h+var_18]
0x18001100b  mov     rcx, rbx
0x18001100e  mov     rax, [rax+28h]
0x180011012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011017  nop
0x180011018  lea     rcx, [rsp+48h+var_28]
0x18001101d  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180011023  nop
0x180011024  lea     rcx, [rsp+48h+var_18]
0x180011029  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18001102e  nop
0x18001102f  mov     rcx, rdi
0x180011032  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180011038  mov     rbx, [rsp+48h+arg_10]
0x18001103d  add     rsp, 40h
0x180011041  pop     rdi
0x180011042  retn
```
