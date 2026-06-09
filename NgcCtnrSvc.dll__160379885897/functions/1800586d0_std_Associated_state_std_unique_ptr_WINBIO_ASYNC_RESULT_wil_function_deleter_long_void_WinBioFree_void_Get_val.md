# std::_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::_Get_value(bool)

- ea: `0x1800586d0`
- end: `0x1800587e1`
- name: `?_Get_value@?$_Associated_state@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@UEAAAEAV?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@2@_N@Z`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180056f10`
- `0x180057308`
- `0x1800586d0`
- `0x1800589b4`
- `0x180058b6c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180058730`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800587a5`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180058730`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800587a5`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180058748`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800587bd`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180058748`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800587bd`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180058711`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180058786`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180058711`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180058786`
- `msvcp_win!_Cnd_wait` at `0x18005876e`
- `msvcp_win!_Cnd_wait` at `0x18005876e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::_Get_value(
        __int64 a1,
        char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  _Mtx_t v7[3]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v7, a1 + 40);
  v4 = (_BYTE *)(a1 + 192);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 24)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 24));
    __ExceptionPtrRethrow(&v6);
  }
  *v4 = 1;
  std::_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::_Maybe_run_deferred_function(
    a1,
    v7);
  while ( !*(_DWORD *)(a1 + 196) )
    _Cnd_wait((_Cnd_t)(a1 + 120), v7[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 24)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 24));
    __ExceptionPtrRethrow(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v7);
  return a1 + 16;
}

```

## disassembly

```asm
0x1800586d0  push    rbp
0x1800586d2  push    rbx
0x1800586d3  push    rsi
0x1800586d4  push    rdi
0x1800586d5  mov     rbp, rsp
0x1800586d8  sub     rsp, 48h
0x1800586dc  mov     bl, dl
0x1800586de  mov     rdi, rcx
0x1800586e1  lea     rdx, [rcx+28h]
0x1800586e5  lea     rcx, [rbp+var_18]
0x1800586e9  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x1800586ee  nop
0x1800586ef  lea     rsi, [rdi+0C0h]
0x1800586f6  test    bl, bl
0x1800586f8  jz      short loc_18005870A
0x1800586fa  cmp     byte ptr [rsi], 0
0x1800586fd  jz      short loc_18005870A
0x1800586ff  mov     ecx, 2
0x180058704  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18005870a  lea     rbx, [rdi+18h]
0x18005870e  mov     rcx, rbx
0x180058711  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180058718  nop     dword ptr [rax+rax+00h]
0x18005871d  test    al, al
0x18005871f  jz      short loc_180058755
0x180058721  xorps   xmm0, xmm0
0x180058724  movdqu  [rbp+var_28], xmm0
0x180058729  mov     rdx, rbx
0x18005872c  lea     rcx, [rbp+var_28]
0x180058730  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180058737  nop     dword ptr [rax+rax+00h]
0x18005873c  lea     rax, [rbp+var_28]
0x180058740  mov     [rbp+arg_0], rax
0x180058744  lea     rcx, [rbp+var_28]
0x180058748  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18005874f  nop     dword ptr [rax+rax+00h]
0x180058754  nop
0x180058755  mov     byte ptr [rsi], 1
0x180058758  lea     rdx, [rbp+var_18]
0x18005875c  mov     rcx, rdi
0x18005875f  call    ?_Maybe_run_deferred_function@?$_Associated_state@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x180058764  jmp     short loc_18005877A
0x180058766  mov     rdx, [rbp+var_18]; _Mtx_t
0x18005876a  lea     rcx, [rdi+78h]; _Cnd_t
0x18005876e  call    cs:__imp__Cnd_wait
0x180058775  nop     dword ptr [rax+rax+00h]
0x18005877a  cmp     dword ptr [rdi+0C4h], 0
0x180058781  jz      short loc_180058766
0x180058783  mov     rcx, rbx
0x180058786  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18005878d  nop     dword ptr [rax+rax+00h]
0x180058792  test    al, al
0x180058794  jz      short loc_1800587CA
0x180058796  xorps   xmm0, xmm0
0x180058799  movdqu  [rbp+var_28], xmm0
0x18005879e  mov     rdx, rbx
0x1800587a1  lea     rcx, [rbp+var_28]
0x1800587a5  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800587ac  nop     dword ptr [rax+rax+00h]
0x1800587b1  lea     rax, [rbp+var_28]
0x1800587b5  mov     [rbp+arg_0], rax
0x1800587b9  lea     rcx, [rbp+var_28]
0x1800587bd  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800587c4  nop     dword ptr [rax+rax+00h]
0x1800587c9  nop
0x1800587ca  lea     rcx, [rbp+var_18]
0x1800587ce  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1800587d3  lea     rax, [rdi+10h]
0x1800587d7  add     rsp, 48h
0x1800587db  pop     rdi
0x1800587dc  pop     rsi
0x1800587dd  pop     rbx
0x1800587de  pop     rbp
0x1800587df  retn
```
