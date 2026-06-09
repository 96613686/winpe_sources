# _WinBioFuture::OrphanBioSessions_::_1_::catch$7

- ea: `0x18007f57f`
- end: `0x18007f62e`
- name: `_WinBioFuture::OrphanBioSessions_::_1_::catch$7`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18005869c`
- `0x180058afc`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18007f60f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18007f60f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18007f5f2`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18007f5f2`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007f5b3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007f5b3`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18007f5c3`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18007f5c3`

## pseudocode

```c
__int64 __fastcall WinBioFuture::OrphanBioSessions_::_1_::catch_7(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 state_for_set; // rbx

  v3 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 168) + 8LL)
                 + 8 * (*(_QWORD *)(*(_QWORD *)(a2 + 168) + 24LL) & (*(_QWORD *)(*(_QWORD *)(a2 + 168) + 16LL) - 1LL)));
  *(_OWORD *)(a2 + 88) = 0;
  __ExceptionPtrCreate((void *)(a2 + 88));
  __ExceptionPtrCurrentException((void *)(a2 + 88));
  *(_QWORD *)(a2 + 72) = a2 + 88;
  state_for_set = std::_Promise<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::_Get_state_for_set(v3);
  *(_OWORD *)(a2 + 104) = 0;
  __ExceptionPtrCopy((void *)(a2 + 104), (const void *)(a2 + 88));
  std::_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::_Set_exception(
    state_for_set,
    a2 + 104);
  __ExceptionPtrDestroy((void *)(a2 + 88));
  return 0;
}

```

## disassembly

```asm
0x18007f57f  mov     [rsp+arg_8], rdx
0x18007f584  push    rbx
0x18007f585  push    rbp
0x18007f586  sub     rsp, 38h
0x18007f58a  mov     rbp, rdx
0x18007f58d  mov     rax, [rbp+0A8h]
0x18007f594  mov     rcx, [rax+10h]
0x18007f598  dec     rcx
0x18007f59b  and     rcx, [rax+18h]
0x18007f59f  mov     rax, [rax+8]
0x18007f5a3  mov     rbx, [rax+rcx*8]
0x18007f5a7  xorps   xmm0, xmm0
0x18007f5aa  movdqu  xmmword ptr [rbp+58h], xmm0
0x18007f5af  lea     rcx, [rbp+58h]
0x18007f5b3  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18007f5ba  nop     dword ptr [rax+rax+00h]
0x18007f5bf  lea     rcx, [rbp+58h]
0x18007f5c3  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18007f5ca  nop     dword ptr [rax+rax+00h]
0x18007f5cf  lea     rax, [rbp+58h]
0x18007f5d3  mov     [rbp+48h], rax
0x18007f5d7  mov     rcx, rbx
0x18007f5da  call    ?_Get_state_for_set@?$_Promise@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@QEAAAEAV?$_State_manager@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@2@XZ; std::_Promise<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::_Get_state_for_set(void)
0x18007f5df  mov     rbx, rax
0x18007f5e2  xorps   xmm0, xmm0
0x18007f5e5  movdqu  xmmword ptr [rbp+68h], xmm0
0x18007f5ea  lea     rdx, [rbp+58h]
0x18007f5ee  lea     rcx, [rbp+68h]
0x18007f5f2  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18007f5f9  nop     dword ptr [rax+rax+00h]
0x18007f5fe  lea     rdx, [rbp+68h]
0x18007f602  mov     rcx, rbx
0x18007f605  call    ?_Set_exception@?$_State_manager@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@QEAAXVexception_ptr@2@_N@Z; std::_State_manager<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::_Set_exception(std::exception_ptr,bool)
0x18007f60a  nop
0x18007f60b  lea     rcx, [rbp+58h]
0x18007f60f  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18007f616  nop     dword ptr [rax+rax+00h]
0x18007f61b  nop
0x18007f61c  mov     rax, 0
0x18007f626  add     rsp, 38h
0x18007f62a  pop     rbp
0x18007f62b  pop     rbx
0x18007f62c  retn
```
