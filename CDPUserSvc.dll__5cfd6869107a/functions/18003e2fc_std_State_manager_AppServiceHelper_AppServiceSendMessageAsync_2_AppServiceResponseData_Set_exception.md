# std::_State_manager__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_Set_exception

- ea: `0x18003e2fc`
- end: `0x18003e35b`
- name: `std::_State_manager__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_Set_exception`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001d5a4`

## callees

- `0x18003e248`
- `0x18003e2fc`
- `0x18003e418`
- `0x18003e914`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003e354`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003e333`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003e333`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_State_manager__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_Set_exception(
        __int64 a1,
        void *a2)
{
  const void *v3; // rdx
  _BYTE **v4; // rcx
  _BYTE *v5; // rbx
  __int128 v6; // [rsp+20h] [rbp-18h] BYREF

  if ( !(unsigned __int8)std::_State_manager__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::valid(a1) )
    std::_Throw_future_error2(4);
  v5 = *v4;
  v6 = 0;
  __ExceptionPtrCopy(&v6, v3);
  std::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_Set_exception(
    v5,
    &v6);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x18003e2fc  mov     [rsp+arg_0], rbx
0x18003e301  mov     [rsp+arg_8], rdx
0x18003e306  push    rdi
0x18003e307  sub     rsp, 30h
0x18003e30b  mov     rdi, rdx
0x18003e30e  call    std___State_manager__AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData___valid
0x18003e313  test    al, al
0x18003e315  jnz     short loc_18003E322
0x18003e317  mov     ecx, 4
0x18003e31c  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18003e322  mov     rbx, [rcx]
0x18003e325  xorps   xmm0, xmm0
0x18003e328  movdqu  [rsp+38h+var_18], xmm0
0x18003e32e  lea     rcx, [rsp+38h+var_18]
0x18003e333  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003e339  lea     rdx, [rsp+38h+var_18]
0x18003e33e  mov     rcx, rbx
0x18003e341  call    std___Associated_state__AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData____Set_exception
0x18003e346  nop
0x18003e347  mov     rcx, rdi
0x18003e34a  mov     rbx, [rsp+38h+arg_0]
0x18003e34f  add     rsp, 30h
0x18003e353  pop     rdi
0x18003e354  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
