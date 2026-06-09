# std::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_Get_value

- ea: `0x18003e0d0`
- end: `0x18003e1b9`
- name: `std::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_Get_value`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18001d678`
- `0x180025114`
- `0x18003e0d0`
- `0x18003e21c`
- `0x18003e418`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003e111`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003e171`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003e111`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003e171`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003e13c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003e19c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003e13c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003e19c`
- `msvcp_win!_Cnd_wait` at `0x18003e15f`
- `msvcp_win!_Cnd_wait` at `0x18003e15f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003e12a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003e18a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003e12a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003e18a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_Get_value(
        __int64 a1,
        char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  _Mtx_t v7[3]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v7, a1 + 56);
  v4 = (_BYTE *)(a1 + 208);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 40)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 40));
    __ExceptionPtrRethrow(&v6);
  }
  *v4 = 1;
  std::_Associated_state__AppServiceHelper::AppServiceSendMessageAsync_::_2_::AppServiceResponseData_::_Maybe_run_deferred_function(
    a1,
    v7);
  while ( !*(_DWORD *)(a1 + 212) )
    _Cnd_wait((_Cnd_t)(a1 + 136), v7[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 40)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 40));
    __ExceptionPtrRethrow(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v7);
  return a1 + 16;
}

```

## disassembly

```asm
0x18003e0d0  push    rbp
0x18003e0d2  push    rbx
0x18003e0d3  push    rsi
0x18003e0d4  push    rdi
0x18003e0d5  mov     rbp, rsp
0x18003e0d8  sub     rsp, 48h
0x18003e0dc  mov     bl, dl
0x18003e0de  mov     rdi, rcx
0x18003e0e1  lea     rdx, [rcx+38h]
0x18003e0e5  lea     rcx, [rbp+var_18]
0x18003e0e9  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18003e0ee  nop
0x18003e0ef  lea     rsi, [rdi+0D0h]
0x18003e0f6  test    bl, bl
0x18003e0f8  jz      short loc_18003E10A
0x18003e0fa  cmp     byte ptr [rsi], 0
0x18003e0fd  jz      short loc_18003E10A
0x18003e0ff  mov     ecx, 2
0x18003e104  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18003e10a  lea     rbx, [rdi+28h]
0x18003e10e  mov     rcx, rbx
0x18003e111  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18003e117  test    al, al
0x18003e119  jz      short loc_18003E143
0x18003e11b  xorps   xmm0, xmm0
0x18003e11e  movdqu  [rbp+var_28], xmm0
0x18003e123  mov     rdx, rbx
0x18003e126  lea     rcx, [rbp+var_28]
0x18003e12a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003e130  lea     rax, [rbp+var_28]
0x18003e134  mov     [rbp+arg_0], rax
0x18003e138  lea     rcx, [rbp+var_28]
0x18003e13c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18003e142  nop
0x18003e143  mov     byte ptr [rsi], 1
0x18003e146  lea     rdx, [rbp+var_18]
0x18003e14a  mov     rcx, rdi
0x18003e14d  call    std___Associated_state__AppServiceHelper__AppServiceSendMessageAsync____2___AppServiceResponseData____Maybe_run_deferred_function
0x18003e152  jmp     short loc_18003E165
0x18003e154  mov     rdx, [rbp+var_18]; _Mtx_t
0x18003e158  lea     rcx, [rdi+88h]; _Cnd_t
0x18003e15f  call    cs:__imp__Cnd_wait
0x18003e165  cmp     dword ptr [rdi+0D4h], 0
0x18003e16c  jz      short loc_18003E154
0x18003e16e  mov     rcx, rbx
0x18003e171  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18003e177  test    al, al
0x18003e179  jz      short loc_18003E1A3
0x18003e17b  xorps   xmm0, xmm0
0x18003e17e  movdqu  [rbp+var_28], xmm0
0x18003e183  mov     rdx, rbx
0x18003e186  lea     rcx, [rbp+var_28]
0x18003e18a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003e190  lea     rax, [rbp+var_28]
0x18003e194  mov     [rbp+arg_0], rax
0x18003e198  lea     rcx, [rbp+var_28]
0x18003e19c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18003e1a2  nop
0x18003e1a3  lea     rcx, [rbp+var_18]
0x18003e1a7  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18003e1ac  lea     rax, [rdi+10h]
0x18003e1b0  add     rsp, 48h
0x18003e1b4  pop     rdi
0x18003e1b5  pop     rsi
0x18003e1b6  pop     rbx
0x18003e1b7  pop     rbp
0x18003e1b8  retn
```
