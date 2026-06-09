# std::_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::_Set_exception(std::exception_ptr,bool)

- ea: `0x180058a30`
- end: `0x180058af4`
- name: `?_Set_exception@?$_Associated_state@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180058afc`

## callees

- `0x180056f10`
- `0x180057308`
- `0x180058a30`
- `0x180058b6c`
- `0x180080010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180058ac1`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180058adc`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180058ac1`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180058adc`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180058a65`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180058a65`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180058a98`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180058a98`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::_Set_exception(
        _BYTE *a1,
        void *a2)
{
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v5[24]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v5, a1 + 40);
  v4 = 0;
  __ExceptionPtrCopy(&v4, a2);
  if ( a1[201] )
    std::_Throw_future_error2(3);
  __ExceptionPtrAssign(a1 + 24, &v4);
  (*(void (__fastcall **)(_BYTE *, _BYTE *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v5, 0);
  __ExceptionPtrDestroy(&v4);
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v5);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x180058a30  mov     [rsp+arg_10], rbx
0x180058a35  mov     [rsp+arg_8], rdx
0x180058a3a  push    rdi
0x180058a3b  sub     rsp, 40h
0x180058a3f  mov     rdi, rdx
0x180058a42  mov     rbx, rcx
0x180058a45  lea     rdx, [rcx+28h]
0x180058a49  lea     rcx, [rsp+48h+var_18]
0x180058a4e  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180058a53  nop
0x180058a54  xorps   xmm0, xmm0
0x180058a57  movdqu  [rsp+48h+var_28], xmm0
0x180058a5d  mov     rdx, rdi
0x180058a60  lea     rcx, [rsp+48h+var_28]
0x180058a65  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180058a6c  nop     dword ptr [rax+rax+00h]
0x180058a71  lea     rax, [rsp+48h+var_28]
0x180058a76  mov     [rsp+48h+arg_0], rax
0x180058a7b  cmp     byte ptr [rbx+0C9h], 0
0x180058a82  jz      short loc_180058A8F
0x180058a84  mov     ecx, 3
0x180058a89  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180058a8f  lea     rcx, [rbx+18h]
0x180058a93  lea     rdx, [rsp+48h+var_28]
0x180058a98  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180058a9f  nop     dword ptr [rax+rax+00h]
0x180058aa4  mov     rax, [rbx]
0x180058aa7  xor     r8d, r8d
0x180058aaa  lea     rdx, [rsp+48h+var_18]
0x180058aaf  mov     rcx, rbx
0x180058ab2  mov     rax, [rax+28h]
0x180058ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058abb  nop
0x180058abc  lea     rcx, [rsp+48h+var_28]
0x180058ac1  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180058ac8  nop     dword ptr [rax+rax+00h]
0x180058acd  nop
0x180058ace  lea     rcx, [rsp+48h+var_18]
0x180058ad3  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180058ad8  nop
0x180058ad9  mov     rcx, rdi
0x180058adc  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180058ae3  nop     dword ptr [rax+rax+00h]
0x180058ae8  mov     rbx, [rsp+48h+arg_10]
0x180058aed  add     rsp, 40h
0x180058af1  pop     rdi
0x180058af2  retn
```
