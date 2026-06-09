# std::_Associated_state<NgcIsoPregenPool::PregenKey>::_Get_value(bool)

- ea: `0x18004c4c0`
- end: `0x18004c5a9`
- name: `?_Get_value@?$_Associated_state@UPregenKey@NgcIsoPregenPool@@@std@@UEAAAEAUPregenKey@NgcIsoPregenPool@@_N@Z`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180047cd0`
- `0x180048240`
- `0x18004c4c0`
- `0x18004c88c`
- `0x18004cb24`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18004c54f`
- `msvcp_win!_Cnd_wait` at `0x18004c54f`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18004c52c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18004c58c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18004c52c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18004c58c`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18004c501`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18004c561`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18004c501`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18004c561`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004c51a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004c57a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004c51a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004c57a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state<NgcIsoPregenPool::PregenKey>::_Get_value(__int64 a1, char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  _Mtx_t v7[3]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v7, a1 + 72);
  v4 = (_BYTE *)(a1 + 224);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 56)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 56));
    __ExceptionPtrRethrow(&v6);
  }
  *v4 = 1;
  std::_Associated_state<NgcIsoPregenPool::PregenKey>::_Maybe_run_deferred_function(a1, v7);
  while ( !*(_DWORD *)(a1 + 228) )
    _Cnd_wait((_Cnd_t)(a1 + 152), v7[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 56)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 56));
    __ExceptionPtrRethrow(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v7);
  return a1 + 16;
}

```

## disassembly

```asm
0x18004c4c0  push    rbp
0x18004c4c2  push    rbx
0x18004c4c3  push    rsi
0x18004c4c4  push    rdi
0x18004c4c5  mov     rbp, rsp
0x18004c4c8  sub     rsp, 48h
0x18004c4cc  mov     bl, dl
0x18004c4ce  mov     rdi, rcx
0x18004c4d1  lea     rdx, [rcx+48h]
0x18004c4d5  lea     rcx, [rbp+var_18]
0x18004c4d9  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18004c4de  nop
0x18004c4df  lea     rsi, [rdi+0E0h]
0x18004c4e6  test    bl, bl
0x18004c4e8  jz      short loc_18004C4FA
0x18004c4ea  cmp     byte ptr [rsi], 0
0x18004c4ed  jz      short loc_18004C4FA
0x18004c4ef  mov     ecx, 2
0x18004c4f4  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18004c4fa  lea     rbx, [rdi+38h]
0x18004c4fe  mov     rcx, rbx
0x18004c501  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18004c507  test    al, al
0x18004c509  jz      short loc_18004C533
0x18004c50b  xorps   xmm0, xmm0
0x18004c50e  movdqu  [rbp+var_28], xmm0
0x18004c513  mov     rdx, rbx
0x18004c516  lea     rcx, [rbp+var_28]
0x18004c51a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18004c520  lea     rax, [rbp+var_28]
0x18004c524  mov     [rbp+arg_0], rax
0x18004c528  lea     rcx, [rbp+var_28]
0x18004c52c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18004c532  nop
0x18004c533  mov     byte ptr [rsi], 1
0x18004c536  lea     rdx, [rbp+var_18]
0x18004c53a  mov     rcx, rdi
0x18004c53d  call    ?_Maybe_run_deferred_function@?$_Associated_state@UPregenKey@NgcIsoPregenPool@@@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<NgcIsoPregenPool::PregenKey>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x18004c542  jmp     short loc_18004C555
0x18004c544  mov     rdx, [rbp+var_18]; _Mtx_t
0x18004c548  lea     rcx, [rdi+98h]; _Cnd_t
0x18004c54f  call    cs:__imp__Cnd_wait
0x18004c555  cmp     dword ptr [rdi+0E4h], 0
0x18004c55c  jz      short loc_18004C544
0x18004c55e  mov     rcx, rbx
0x18004c561  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18004c567  test    al, al
0x18004c569  jz      short loc_18004C593
0x18004c56b  xorps   xmm0, xmm0
0x18004c56e  movdqu  [rbp+var_28], xmm0
0x18004c573  mov     rdx, rbx
0x18004c576  lea     rcx, [rbp+var_28]
0x18004c57a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18004c580  lea     rax, [rbp+var_28]
0x18004c584  mov     [rbp+arg_0], rax
0x18004c588  lea     rcx, [rbp+var_28]
0x18004c58c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18004c592  nop
0x18004c593  lea     rcx, [rbp+var_18]
0x18004c597  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18004c59c  lea     rax, [rdi+10h]
0x18004c5a0  add     rsp, 48h
0x18004c5a4  pop     rdi
0x18004c5a5  pop     rsi
0x18004c5a6  pop     rbx
0x18004c5a7  pop     rbp
0x18004c5a8  retn
```
