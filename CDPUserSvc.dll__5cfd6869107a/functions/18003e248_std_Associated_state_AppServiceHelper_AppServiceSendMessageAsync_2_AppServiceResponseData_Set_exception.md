# std::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_Set_exception

- ea: `0x18003e248`
- end: `0x18003e2f3`
- name: `std::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_Set_exception`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18003e2fc`

## callees

- `0x18001d678`
- `0x180025114`
- `0x18003e248`
- `0x18003e418`
- `0x180064010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003e2cd`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003e2e2`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003e2cd`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003e2e2`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003e27d`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003e27d`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003e2aa`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003e2aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_Set_exception(
        _BYTE *a1,
        void *a2)
{
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v5[24]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v5, a1 + 56);
  v4 = 0;
  __ExceptionPtrCopy(&v4, a2);
  if ( a1[217] )
    std::_Throw_future_error2(3);
  __ExceptionPtrAssign(a1 + 40, &v4);
  (*(void (__fastcall **)(_BYTE *, _BYTE *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v5, 0);
  __ExceptionPtrDestroy(&v4);
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v5);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x18003e248  mov     [rsp+arg_10], rbx
0x18003e24d  mov     [rsp+arg_8], rdx
0x18003e252  push    rdi
0x18003e253  sub     rsp, 40h
0x18003e257  mov     rdi, rdx
0x18003e25a  mov     rbx, rcx
0x18003e25d  lea     rdx, [rcx+38h]
0x18003e261  lea     rcx, [rsp+48h+var_18]
0x18003e266  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18003e26b  nop
0x18003e26c  xorps   xmm0, xmm0
0x18003e26f  movdqu  [rsp+48h+var_28], xmm0
0x18003e275  mov     rdx, rdi
0x18003e278  lea     rcx, [rsp+48h+var_28]
0x18003e27d  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003e283  lea     rax, [rsp+48h+var_28]
0x18003e288  mov     [rsp+48h+arg_0], rax
0x18003e28d  cmp     byte ptr [rbx+0D9h], 0
0x18003e294  jz      short loc_18003E2A1
0x18003e296  mov     ecx, 3
0x18003e29b  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18003e2a1  lea     rcx, [rbx+28h]
0x18003e2a5  lea     rdx, [rsp+48h+var_28]
0x18003e2aa  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18003e2b0  mov     rax, [rbx]
0x18003e2b3  xor     r8d, r8d
0x18003e2b6  lea     rdx, [rsp+48h+var_18]
0x18003e2bb  mov     rcx, rbx
0x18003e2be  mov     rax, [rax+28h]
0x18003e2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2c7  nop
0x18003e2c8  lea     rcx, [rsp+48h+var_28]
0x18003e2cd  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003e2d3  nop
0x18003e2d4  lea     rcx, [rsp+48h+var_18]
0x18003e2d9  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18003e2de  nop
0x18003e2df  mov     rcx, rdi
0x18003e2e2  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003e2e8  mov     rbx, [rsp+48h+arg_10]
0x18003e2ed  add     rsp, 40h
0x18003e2f1  pop     rdi
0x18003e2f2  retn
```
